#include <iostream>
#include <string>
using namespace std;

class Hotel {
private:
    int roomNo;
    string name;
    int days;
    float bill;

public:
    void bookRoom() {
        cout << "Enter Room Number: ";
        cin >> roomNo;

        cout << "Enter Customer Name: ";
        cin.ignore();
        getline(cin, name);

        cout << "Enter Number of Days: ";
        cin >> days;

        bill = days * 1000; // Room charge per day
        cout << "Room booked successfully!\n";
    }

    void showDetails() {
        cout << "\nCustomer Name: " << name << endl;
        cout << "Room Number: " << roomNo << endl;
        cout << "Days Stayed: " << days << endl;
        cout << "Total Bill: Rs. " << bill << endl;
    }

    void checkout() {
        cout << "\nCheckout Details\n";
        showDetails();
        cout << "Thank you for staying!\n";
    }
};

int main() {
    Hotel h;
    int choice;

    do {
        cout << "\n--- HOTEL MANAGEMENT SYSTEM ---\n";
        cout << "1. Book Room\n";
        cout << "2. View Customer Details\n";
        cout << "3. Checkout\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch(choice) {
            case 1:
                h.bookRoom();
                break;

            case 2:
                h.showDetails();
                break;

            case 3:
                h.checkout();
                break;

            case 4:
                cout << "Exiting program...\n";
                break;

            default:
                cout << "Invalid choice!\n";
        }

    } while(choice != 4);

    return 0;
}
