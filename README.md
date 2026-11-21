
    
class BankAccount:
    def __init__(self, name, balance=0):
        self.name = name
        self.balance = balance

    def check_balance(self):
        print(f"{self.name}'s balance is ₹{self.balance}")

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print(f"Deposit successful! New balance: ₹{self.balance}")
        else:
            print("Invalid deposit amount!")

    def withdraw(self, amount):
        if amount <= 0:
            print("Invalid withdrawal amount!")
        elif amount > self.balance:
            print("Insufficient funds!")
        else:
            self.balance -= amount
            print(f"Withdrawal successful! New balance: ₹{self.balance}")

account1 = BankAccount("Vishnu", 5000)

while True:
    print("\n===== BANK ATM =====")
    print("1. Check Balance")
    print("2. Deposit Money")
    print("3. Withdraw Money")
    print("4. Exit")


    choice = input("Enter your choice: ")
    

    if choice == "1":
        account1.check_balance()
    elif choice == "2":
        try:
            amount = float(input("Enter the amount to deposit: "))
            account1.deposit(amount)
        except ValueError:
            print("Invalid input! Please enter a valid number.")
    elif choice == "3":
        try:
            amount = float(input("Enter the amount to withdraw: "))
            account1.withdraw(amount)
        except ValueError:
            print("Invalid input! Please enter a valid number.")            

    elif choice == "4":
        print("Thank you for using our ATM. Have a great day!")
        break

    else:
        print("Invalid choice! Please select 1-4.")
        
        

