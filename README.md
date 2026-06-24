# Library-Management_Web-application

Library Management System
A full-stack web application for managing a library's books, publishers, members, and lending activity, built from an entity-relationship design covering five core entities: Book, Publisher, Admin, Member, and Book Issue (loan records).
Overview
The system supports two types of users with distinct experiences:

Administrators manage the library's catalog end-to-end — adding and editing books and publishers, maintaining member and admin accounts, and tracking which books are currently on loan, overdue, or returned.
Members can create their own accounts, browse books that are currently available, borrow a book with one click, and view and return their own active loans — without needing an admin to process every transaction.

Authentication is role-based: a single login page lets a user sign in as either a Member or an Admin, and each role is routed to its own dashboard with only the actions relevant to it.
Key Features

Full CRUD management of books, publishers, members, and admin accounts
Book lending workflow: issue a book, track its due/return status, and mark it returned
Member self-service: registration, login, browsing available titles, self-issuing a loan, and self-returning a book
Relational integrity enforced at the database level (a book belongs to a publisher; a loan record links a book, a member, and the admin who processed it)


Tech Stack
LayerTechnologyFrontendHTML, CSS, vanilla JavaScript (no framework)BackendASP.NET Core Web API (.NET 8), Entity Framework CoreDatabaseMicrosoft SQL Server

Architecture

The application follows a classic three-tier structure: a static HTML/CSS/JS client communicates with an ASP.NET Core Web API over REST endpoints (JSON), and the API persists data through Entity Framework Core to a SQL Server database whose schema mirrors the original ER diagram, including foreign-key relationships between publishers→books and books/admins/members→loan records.
