# library-book-management
Instructions to Run the Library Book Management System

                                  1. Project Overview

The Library Book Management System is a web-based application designed to handle common library operations such as adding books, issuing and returning books, and generating reports.
The project consists of two main parts:

Frontend – the user interface (HTML, CSS, JavaScript)

Backend – the server and database logic (Node.js, Express, MySQL)

                                  2.Software Requirements

To run this project, you need:

Node.js and npm (for backend)

MySQL Database Server

A code editor (like VS Code)

A web browser (like Chrome)

Git (optional, for uploading to GitHub)

                                  3. Setting Up the Database

Open MySQL Workbench or phpMyAdmin.

Create a new database, for example: library_db.

Inside this database, create tables such as:

admins (for login credentials)

books (for book details)

members (for users)

issue_return (for tracking issued and returned books)

Insert one admin record (e.g., username: admin, password: 12345) for testing.

This database will store all the data your website uses.

                                4.Setting Up the Backend (Server)

The backend is built using Node.js and Express.js.

Open the backend folder in VS Code.

Inside the project, the main file is usually called server.js.

It connects to the MySQL database.

It contains routes (API endpoints) for login, adding books, issuing books, returning books, and viewing reports.

The backend runs on a local server (e.g., http://localhost:5000).

When the server starts successfully, it will display messages such as:

“MySQL Connected”

“Server running on port 5000”

                                  5.Setting Up the Frontend

The frontend consists of HTML, CSS, and JavaScript files such as:

login.html – for admin login

dashboard.html – shows total books, issued books, etc.

addBook.html – form to add a new book

issueReturn.html – to issue and return books

reports.html – to view reports

Each page has JavaScript code that communicates with the backend through fetch() API calls.

Example: When you click “Add Book,” it sends book details to the backend server (/add-book) which stores them in MySQL.

The frontend is opened directly in a browser or served using a simple local server (like Live Server in VS Code).

                                      6.Running the Project
Step 1 — Start MySQL

Make sure your MySQL server is running and the library_db database exists.

Step 2 — Start the Backend Server

Open the backend folder in VS Code.

Start the Node.js server (e.g., run node server.js in the terminal).

Wait until the message “Server running on port 5000” appears.

Step 3 — Open the Frontend

Open login.html in your browser (using VS Code Live Server or file explorer).

Enter the admin username and password (e.g., admin / 12345).

After successful login, it redirects to the dashboard.

                                          7.Using the Application

Login Page – The admin logs in using valid credentials.

Dashboard Page – Displays total books, issued books, available books, and total members.

Add Book Page – The admin can add new books with book ID, title, author, etc.

Issue & Return Page – Allows issuing books to members and recording returns.

Report Page – Displays records of all issued and returned books.

All these operations interact with the database in real time through the backend API.

                                          8. Verifying the Data

After performing operations (add, issue, return), check your MySQL database tables.

The data should be updated automatically (e.g., book status changes to “Issued” or “Available”).

                                         9.Common Issues and Solutions
                                         
 | Issue                        | Cause                      | Solution                                                             |
| ---------------------------- | -------------------------- | -------------------------------------------------------------------- |
| Server not starting          | Missing modules            | Install required packages (express, mysql2, cors, body-parser)       |
| “Cannot connect to database” | Wrong credentials in db.js | Check MySQL username, password, and database name                    |
| CORS error                   | Browser blocked request    | Use `app.use(cors())` in backend                                     |
| Fetch API not working        | Wrong API URL              | Make sure the backend port matches (usually `http://localhost:5000`) |
| Login not working            | Wrong admin record         | Verify username and password in `admins` table                       |
    


                                             10.Summary

The backend (Node.js + MySQL) handles data and logic.

The frontend (HTML + CSS + JS) provides the interface for users.

Both communicate through REST APIs using HTTP requests.

The admin manages all operations directly through the web interface.
