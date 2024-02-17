# DSML-
PROJECTS
class BankAccount:
    def __init__(self, user_name, balance=0):
        self.user_name = user_name
        self.balance = balance
# function  to deposit money
    def deposit(self, amount):
        self.balance = + amount
        print("Amount deposited =Rs.", amount, "\nNet balance =Rs.", self.balance)
# function to  withdraw  money
    def withdraw(self, amount):
        if amount > self.balance:
            print("No Sufficient Balance")
        else:
            self.balance =self.balance - amount
            print("Amount withdrawn = Rs.", amount, "Current Balance = Rs.", self.balance)

# function to display balance
    def display(self):
        print("Current Balance = Rs.", self.balance)

# main function to receive data from user
    def main(self):
        details = {}
        print("Welcome to XYZ Banking System")
        print("------------------------------")
        for i in range(10):
            print("""please select an Option :
                     1.Create Account
                     2.Login
                     3.Exit""")
            print("**************************")
            option = int(input("Enter your Option :"))
            if option == 1:
                full_name = input("Enter your Full Name:")
                user_name = input("Enter your User Name :")
                password = input("Enter your Password:")
                email_id = input("Enter your Email ID:")
                account_no = input("Enter your Account No. :")
                mobile_no = input("Enter your Mobile No.:")
                if user_name in details:
                    print("User Name exist")
                else:
                    details[full_name] = BankAccount('Full Name')
                    details[password] = BankAccount('Password')
                    details[user_name] = BankAccount('UserName')
                    details[email_id] = BankAccount('Email ID')
                    details[account_no] = BankAccount('Account No.')
                    details[mobile_no] = BankAccount('Mobile No.')
                    print("Account created")
                    print("***********************************")
            elif option == 2:
                user_name = input("User Name :")
                password = input("Password :")
                if user_name in details:

                    account = details[user_name]
                    account = details[password]

                    print("Welcome!,", user_name)
                    for j in range(10):
                        print("""Please choose an Option to avail Our service:
                                 1.check balance
                                 2.Deposit
                                 3.Withdraw
                                 4.Logout""")
                        print("********************************")
                        choose = input("Enter the Option:")
                        if choose == '1':
                          print("Your current Balance is,Rs.", self.balance)
                        elif choose == '2':
                            account_no = input("Enter your Account Number:")
                            details[account_no] = BankAccount('Account.No')
                            amount_deposited = float(input("Enter the amount to be deposited:Rs."))
                            account.deposit(amount_deposited)
                            print("********************************")
                        elif choose == '3':
                            account_no = input("Enter your Account Number:")
                            amount = float(input("Enter the amount to be debited : Rs."))
                            account.withdraw(amount)
                            print("********************************")
                        elif choose == '4':
                            print("You are successfully logged out")
                            print("********************************")
                            break
                        else:
                            print("Invalid option")
                else:
                    print("Details not found")
            elif option == 3:
                print("Thank you! Have a Good Day!")
                print("********************************")
                break

            else:
                print("Invalid Option")
# function calling
b = BankAccount('User Name')
b.main()








