# Grocery Store Management System

## Overview

The **Grocery Store Management System** is a web application designed to manage products, orders, and units of measurement (UOM) for a grocery store. The application is built using Python with Flask for the web server and MySQL for the database.

## Project Structure

- `server.py`: The main Flask application file that provides RESTful API endpoints for managing products and orders.
- `products_dao.py`: Data Access Object (DAO) for managing product-related database operations.
- `orderrs_dao.py`: DAO for managing order-related database operations.
- `sql_connection.py`: Provides a singleton MySQL connection for the application.
- `uom_dao.py`: DAO for managing units of measurement.
- `sidebar-menu.css`: CSS file for styling the sidebar menu component of the application.

## Installation

### Prerequisites

Ensure you have Python and MySQL installed on your system.

### Setting Up the Environment

1. **Clone the Repository**

   ```bash
   git clone https://github.com/your-username/grocery-store-management-system.git
   cd grocery-store-management-system
Create a Virtual Environment

bash
Copy code
python -m venv venv
Activate the Virtual Environment

On Windows:

bash
Copy code
venv\Scripts\activate
On macOS/Linux:

bash
Copy code
source venv/bin/activate
Install Dependencies

bash
Copy code
pip install -r requirements.txt
Configure the Database

Update the sql_connection.py file with your MySQL database credentials.
Ensure the following tables exist in your grocery_store database:
products
uom
orders
order_details
Usage
Run the Flask Server

bash
Copy code
python server.py
The server will start on port 5000.

API Endpoints

GET /getUOM: Retrieve all units of measurement.
GET /getProducts: Retrieve all products.
POST /insertProduct: Insert a new product. Requires JSON payload with product_name, uom_id, and price_per_unit.
GET /getAllOrders: Retrieve all orders with their details.
POST /insertOrder: Insert a new order. Requires JSON payload with customer_name, grand_total, and order_details.
POST /deleteProduct: Delete a product by product_id.
File Descriptions
server.py: Defines the Flask application and routes for API endpoints. It uses the DAO modules to interact with the database and provides responses in JSON format.

products_dao.py: Contains functions for managing product-related database operations, such as retrieving all products, inserting new products, and deleting products.

orderrs_dao.py: Contains functions for managing order-related database operations, including inserting orders, retrieving order details, and fetching all orders.

sql_connection.py: Manages the MySQL database connection. It ensures that a single connection is used throughout the application.

uom_dao.py: Provides functionality to retrieve all units of measurement from the database.

sidebar-menu.css: Styles the sidebar menu component, including layout, colors, hover effects, and responsiveness.
