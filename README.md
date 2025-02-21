# E-Commerce Price Tracker Bot

This E-Commerce Price Tracker Bot monitors product prices and availability on e-commerce websites like Amazon and eBay. It sends notifications via email and SMS when the price of a product drops significantly below the average price or when a product that was out of stock becomes available again.

## Features

- Scrapes product data from e-commerce websites.
- Calculates the average price of products.
- Sends email and SMS notifications when a deal is found.
- Sends email and SMS notifications when a product becomes available.
- Configurable via a JSON file.

## Requirements

- Python 3.6+
- Required Python libraries:
  - `requests`
  - `beautifulsoup4`
  - `smtplib`
  - `twilio`
  - `statistics`

## Installation

1. **Clone the Repository or Download the Script**:
   - Clone the repository or download the script file `ecom_price_tracker.py`.

2. **Install the Required Python Libraries**:
   - Open a terminal or command prompt and run the following command to install the required libraries:
     ```sh
     pip install requests beautifulsoup4 twilio
     ```

3. **Create a Configuration File**:
   - Create a file named [config.json](http://_vscodecontentref_/0) in the same directory as the script and add the following content, replacing the placeholders with your actual values:
     ```json
     {
         "urls": [
             "https://www.amazon.com/s?k=laptops",
             "https://www.ebay.com/sch/i.html?_nkw=laptops"
         ],
         "threshold_price": 500.00,
         "check_interval": 3600,
         "email": {
             "smtp_server": "smtp.your-email-provider.com",
             "smtp_port": 587,
             "username": "your-email@example.com",
             "password": "your-email-password",
             "from_email": "your-email@example.com",
             "to_email": "recipient-email@example.com"
         },
         "twilio": {
             "account_sid": "your-twilio-account-sid",
             "auth_token": "your-twilio-auth-token",
             "from_phone": "+1234567890",
             "to_phone": "+0987654321"
         }
     }
     ```

## Running the Script

1. **Save the Script**:
   - Save the script to a file named `ecom_price_tracker.py`.

2. **Run the Script**:
   - Open a terminal or command prompt, navigate to the directory where the script is saved, and run the following command:
     ```sh
     python ecom_price_tracker.py
     ```

3. **Monitor Prices and Availability**:
   - The script will continuously check the prices and availability of the products at the specified URLs and send email and SMS notifications if the prices drop significantly below the average price or if the products become available.

### Example Output
Fetching data from https://www.amazon.com/s?k=laptops&page=1 Fetching data from https://www.amazon.com/s?k=laptops&page=2 Fetching data from https://www.amazon.com/s?k=laptops&page=3 Fetching data from https://www.ebay.com/sch/i.html?_nkw=laptops&page=1 Fetching data from https://www.ebay.com/sch/i.html?_nkw=laptops&page=2 Fetching data from https://www.ebay.com/sch/i.html?_nkw=laptops&page=3 Deal found! Laptop XYZ is now $350.00 Email sent for Laptop XYZ at $350.00 SMS sent for Laptop XYZ at $350.00

