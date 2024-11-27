# BookFlo - Library Management System V2

<div align="center">
  <img src="https://github.com/user-attachments/assets/c7b45c0f-ade7-45e6-8bef-b3703e4c8a18" alt="Screenshot" width="444">
</div>

**BookFlo** is a multi-user application designed to issue, grant/revoke, and maintain e-books across various sections, like an online library. This project demonstrates an efficient, scalable, and interactive library management system built using Flask, SQLite, and other frameworks.

---

### Frameworks and Tools Used
- **Backend**: Flask
- **Database**: SQLite
- **Frontend**: Bootstrap and Jinja2 templates
- **Caching and Batch Jobs**: Redis and Celery
- **Additional Libraries**: ChartJS (optional, for graphs and charts)

---

## Features

### Roles
1. **Librarian**:
   - Maintains sections and e-books.
   - Monitors user activities and manages e-book access.
   - Grants/revokes access to e-books.
2. **General User**:
   - Can browse sections, request e-books, and return them.
   - Provides feedback and ratings for e-books.

### Core Functionalities
1. **Admin Login and User Login (RBAC)**:
   - Role-based access control implemented using Flask security or JWT.
   - Differentiates between librarian and general users.

2. **Librarian Dashboard**:
   - Displays statistics like active users, grant requests, issued/revoked books.

3. **Section Management**:
   - Create, update, and delete sections for organizing e-books.

4. **E-book Management**:
   - Add, edit, and delete e-books within specific sections.

5. **Search Functionality**:
   - Users can search for sections and e-books by title, author, etc.

6. **Scheduled Batch Jobs**:
   - **Daily Reminders**: Sends email notifications to users for overdue books.
   - **Monthly Reports**: HTML reports for librarians detailing activity and statistics.

7. **User-Triggered Jobs**:
   - CSV export of issued/returned e-books.

8. **Performance and Caching**:
   - API performance optimized with Redis caching and cache expiry.

---

## Steps to Use the Application

### 1. Create Virtual Environment
   ```bash
   python -m virtualenv myenv
```
### 2. Activate Virtual Environment
   ```bash
   source myenv/bin/activate
```
### 3. Install Required Packages
   ```bash
   pip install -r requirements.txt
```
### 4. Set the Flask Entry Point
   ```bash
   export FLASK_APP=main
```
### 5. Start the Server
   ```bash
   flask run --debug
```
### 6. Migrate Database
   ```bash
   python3 setup_db.py
```

---

## Caching and Batch Jobs

### 1. Start Redis Server
   ```bash
   redis-server
```
### 2. Start Celery Worker
   ```bash
   celery -A main:celery_app worker --loglevel INFO
```
### 3. Start Celery Beat Scheduler
   ```bash
   celery -A main:celery_app beat --loglevel INFO
```

