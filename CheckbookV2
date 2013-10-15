/* 
Name: Renato Recio 
Program Status: Complete
Program Function: Modified checkbook balancing program
				  Designed to process bank accounts using check 
				  processing, Deposit processing, and End-of-Month
				  processing.
*/
#include <iomanip>
#include <iostream>
#include <cmath>
using namespace std;

//Declare methods
float processCheck(float, float, float,float, int); //check processing method
float processDeposit(float, float, float); //deposit processing method
float endProgram(float, float); //end the program method



int main ()
{

  float balance; //will be used to store balance, -1 for initial flag
  char transactionType; //transaction type (Valid types: C D E)
  float transactionAmount;
  int exit = 0; //used to exit the program
  float totalServiceCharge; // used to store total service charges
  const float serviceCharge = 0.25; // constant for each service charge
  int below_eight_hundred = 0; //if account balance falls below 800, this becomes 1
  //Get initial balance
  cout << "Checkbook Balancing Program\n\n";
  cout << "Enter the beginning balance: ";
  
  
  cin >> balance;

  //Round balance to 2 decimal places
  floor(balance*pow(10,2))/pow(10,2);
  

	
  	while ( exit == 0){
		
		//user input 
  		cout << "\nEnter a transaction: ";
  		cin >> transactionType ; //User enters a transaction type
  	
  		//check case
  		if (transactionType == 'C'){
  			cin >> transactionAmount; //User enters the amount
  		    totalServiceCharge += serviceCharge;
  			floor(totalServiceCharge*pow(10,2))/pow(10,2);
  			balance = processCheck(balance, serviceCharge, totalServiceCharge, transactionAmount, below_eight_hundred);
  			if (balance < 800 && below_eight_hundred == 0){
  			totalServiceCharge += 5;
  			below_eight_hundred = 1;
  		}
  		   if (balance < 0)
  		   totalServiceCharge +=25;
  		}
  		//deposit case
  		else if (transactionType == 'D'){
  			cin >> transactionAmount; //User enters the amount
  			if (transactionAmount < 0)
  			cout << "Enter a valid transaction. \n";
  			else
  			balance = processDeposit(balance, totalServiceCharge, transactionAmount);
  		
  		}
		//end of month case
  		else if (transactionType == 'E'){
  			cout << "Processing end of month";
  			endProgram(balance, totalServiceCharge);
  			exit = 1;
			}		
		else 
			cout << "Enter a valid transaction type. \n";
  		}
  return 0;
}


//Process check method, returns new balance
float processCheck(float balance, float serviceCharge, float totalServiceCharge, float transactionAmount, int below_eight_hundred){
	

	
	//process the check
	cout << "Processing check for $" << transactionAmount;
	balance -= transactionAmount;
	floor(balance*pow(10,2))/pow(10,2);
	cout << "\nBalance: $"; 
	cout << setprecision(2) << fixed << balance;
	cout << "\nService charge: $" << serviceCharge;
	cout << " for a check";
	
	//If below 800, apply service charge
	if (balance < 800 && below_eight_hundred == 0){
		cout << "\nService charge: $5.00 balance below $800.00";
		totalServiceCharge += 5.0;
	}
	
	//If negative balance, apply service charge
	if (balance < 0){
		cout << "\nService charge: $25.00 negative account balance";
		totalServiceCharge += 25;
	}
	
	//totals
	cout << "\nTotal service charges: $" ;
	cout << setprecision(2) << fixed << totalServiceCharge;
	cout << "\n";
	return balance;
}

//Process deposit method, returns new balance 
float processDeposit(float balance, float totalServiceCharge, float transactionAmount){

	// while loop maintains a positive amount
	while (transactionAmount <= -1 ){
		transactionAmount = 1;
	cin >> transactionAmount;
	if (!(transactionAmount > 0))
	cout << "\nPlease enter a positive number: ";
	}

	//process deposit
	cout << "Processing deposit for $" << transactionAmount;
	balance += transactionAmount;
	floor(balance*pow(10,2))/pow(10,2);
	cout << "\nBalance: $";
	cout << setprecision(2) << fixed << balance;
	cout << "\nTotal service charges: $";
	cout << setprecision(2) << fixed << totalServiceCharge;
	cout << "\n";
	return balance;
}

//End program
float endProgram(float balance, float totalServiceCharge){
	balance -= totalServiceCharge;
	cout << "\nFinal balance: $";
	cout << setprecision(2) << fixed << balance;
	return balance;
}
