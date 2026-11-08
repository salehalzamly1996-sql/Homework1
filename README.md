public class BankAccount {
    private String accountHolder;
    private int accountNumber;
    private double balance;

    // 1. Constructor
    public BankAccount(String accountHolder, int accountNumber, double initialBalance) {
        this.accountHolder = accountHolder;
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }

    // 2. Accessor methods
    public String getAccountHolder() {
        return accountHolder;
    }

    public int getAccountNumber() {
        return accountNumber;
    }

    public double getBalance() {
        return balance;
    }

    // 3. Deposit method
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    // 4. Withdraw method
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        }
    }

    // 5. Calculate interest method
    public double calculateInterest(double annualInterestRate) {
        return balance * annualInterestRate;
    }

    // 6. Display account info method
    public void displayAccountInfo(double annualInterestRate) {
        double interest = calculateInterest(annualInterestRate);
        System.out.println("Account Holder: " + accountHolder);
        System.out.println("Account Number: " + accountNumber);
        System.out.println("Current Balance: " + balance);
        System.out.println("Annual Interest: " + interest);
    }

    // Main Method
    public static void main(String[] args) {
        // Create a BankAccount object with an initial balance of 1500.0
        BankAccount account = new BankAccount("Ahmad", 1001, 1500.0);

        // Deposit 300.0 into the account
        account.deposit(300.0);

        // Withdraw 250.0 from the account
        account.withdraw(250.0);

        // Display the final account information with 4% interest rate (0.04)
        account.displayAccountInfo(0.04);
    }
}
