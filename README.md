# Online Auction CRUD Operation

This is a *CRUD (Create, Read, Update, Delete)* application for an Online Auction system. The project is built using *Java, **Servlet, **JDBC, and **MySQL, and developed in the **Eclipse IDE. The MySQL database is integrated using the **MySQL Connector JAR*.

---

## Features
- Create auction items and bidders.
- View auction items and bidder details.
- Update auction details.
- Delete auction entries.

---

## Tech Stack

### Backend
- *Java*: Core logic and servlet implementation.
- *JDBC*: Database connectivity.
- *Servlet*: Handles HTTP requests and responses.

### Database
- *MySQL*: Stores auction and bidder information.
- *MySQL Connector JAR*: For database connectivity.

### IDE
- *Eclipse*: Development environment.

### Frontend
- *HTML/CSS*: For designing the user interface.

---

## Prerequisites

1. *Eclipse IDE* installed on your system.
2. *MySQL Server* installed and running.
3. *MySQL Connector JAR* file.
4. Basic understanding of Java, Servlets, and SQL.

---

## Database Setup

1. Create a database named auction_db in MySQL.
2. Use the following script to create the necessary tables:

sql
CREATE DATABASE auction_db;
USE auction_db;

CREATE TABLE auction_items (
    item_id INT AUTO_INCREMENT PRIMARY KEY,
    item_name VARCHAR(100) NOT NULL,
    starting_price DECIMAL(10, 2) NOT NULL,
    end_date DATE NOT NULL
);

CREATE TABLE bidders (
    bidder_id INT AUTO_INCREMENT PRIMARY KEY,
    bidder_name VARCHAR(100) NOT NULL,
    contact_number VARCHAR(15) NOT NULL
);


3. Insert sample data (optional):

sql
INSERT INTO auction_items (item_name, starting_price, end_date) 
VALUES ('Antique Vase', 1000.00, '2024-12-31');

INSERT INTO bidders (bidder_name, contact_number) 
VALUES ('John Doe', '1234567890');


---

## Project Structure


OnlineAuctionCRUD
|
|-- src
|   |-- com.auction
|       |-- AddItemServlet.java
|       |-- ViewItemsServlet.java
|       |-- UpdateItemServlet.java
|       |-- DeleteItemServlet.java
|       |-- DatabaseConnection.java
|
|-- WebContent
|   |-- index.html
|   |-- add-item.html
|   |-- view-items.html
|   |-- update-item.html
|   |-- delete-item.html
|-- WEB-INF
    |-- web.xml
|
|-- lib
    |-- mysql-connector-java-x.x.x.jar


---

## Configuration Steps

1. Clone this repository or download the ZIP.
2. Open Eclipse IDE and import the project.
3. Place the *MySQL Connector JAR* file in the lib folder.
4. Configure the DatabaseConnection.java file with your MySQL credentials:

java
package com.auction;

import java.sql.Connection;
import java.sql.DriverManager;

public class DatabaseConnection {
    private static final String URL = "jdbc:mysql://localhost:3306/auction_db";
    private static final String USER = "root";
    private static final String PASSWORD = "your_password";

    public static Connection getConnection() throws Exception {
        Class.forName("com.mysql.cj.jdbc.Driver");
        return DriverManager.getConnection(URL, USER, PASSWORD);
    }
}


5. Deploy the project on a Tomcat server (or any servlet container).
6. Access the application from your browser.

---

## Usage

1. *Add Items*: Navigate to the add-item.html page and fill in the auction item details.
2. *View Items*: Use the view-items.html page to see all listed auction items.
3. *Update Items*: Modify details through the update-item.html page.
4. *Delete Items*: Remove auction items using the delete-item.html page.

---

## Screenshots

1. *Home Page*:
   - Description of the auction system.
   - Navigation to CRUD operations.

2. *Add Item Page*:
   - Form for adding auction items.

3. *View Items Page*:
   - Table displaying all auction items.

4. *Update Item Page*:
   - Form for updating auction item details.

5. *Delete Item Page*:
   - Option to remove auction items.

---

## Future Enhancements
- Add user authentication.
- Implement live bidding functionality.
- Enhance the UI with modern frameworks (e.g., Bootstrap).

---

## Contributors
- [Your Name]

---

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
