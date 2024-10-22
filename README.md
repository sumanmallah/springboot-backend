# Spring Boot Backend Application

This is a Spring Boot backend application that connects to a MySQL database and provides APIs for CRUD (Create, Read, Update, Delete) operations for managing employees.

## Prerequisites

Before running the application, ensure that you have the following installed:

- **Java 8 or higher**: [Download Java](https://www.oracle.com/java/technologies/javase-downloads.html)
- **Maven**: [Download Maven](https://maven.apache.org/download.cgi)
- **MySQL (version 8.x recommended)**: [Download MySQL](https://dev.mysql.com/downloads/)
- **Git**: [Download Git](https://git-scm.com/downloads)

## Setup Instructions

### 1. Clone the Repository

Clone this repository to your local machine using Git:

```bash
git clone https://github.com/yourusername/springboot-backend.git
```
2. Configure MySQL Database
Create a MySQL database named ems:

sql
Copy code
CREATE DATABASE ems;
3. Update application.properties
Navigate to the src/main/resources/application.properties file and update the following properties with your MySQL credentials:

properties
Copy code
# Application name
spring.application.name=springboot-backend

# MySQL Database connection configuration
spring.datasource.url=jdbc:mysql://localhost:3306/ems?useSSL=false
spring.datasource.username=YOUR_MYSQL_USERNAME
spring.datasource.password=YOUR_MYSQL_PASSWORD

# Hibernate dialect and auto DDL updates
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
spring.jpa.hibernate.ddl-auto=update
Replace YOUR_MYSQL_USERNAME and YOUR_MYSQL_PASSWORD with your actual MySQL credentials.

4. Build the Project
To build the project, navigate to the project directory and run Maven commands to clean and install dependencies:

bash
Copy code
cd springboot-backend
mvn clean install
This will download all necessary dependencies, compile the code, and prepare the project for running.

5. Run the Application
After the build is complete, you can start the Spring Boot application by running:

bash
Copy code
mvn spring-boot:run
The application should now be running on http://localhost:8080.

6. API Endpoints
The following are the available API endpoints for managing employees:

GET /api/employees: Retrieve a list of all employees.
GET /api/employees/{id}: Retrieve an employee by their ID.
POST /api/employees: Create a new employee.
PUT /api/employees/{id}: Update the details of an existing employee.
DELETE /api/employees/{id}: Delete an employee by their ID.
7. Accessing the Application
Once the server is running, you can access the API using Postman, curl, or any HTTP client at:

bash
Copy code
http://localhost:8080/api/employees
Replace /employees with other endpoints as needed to interact with the application.

8. Troubleshooting
Database connection issues: If you encounter any errors related to the database connection, make sure that:

MySQL is running on localhost:3306, or update spring.datasource.url if it's on a different host/port.
The username and password provided in the application.properties file are correct.
MySQL not running: Ensure that your MySQL server is running and that the ems database exists. You can check this by running:

bash
Copy code
mysql -u YOUR_MYSQL_USERNAME -p
SHOW DATABASES;
9. Running Tests
To run unit tests or integration tests (if available in the project), you can use the following Maven command:

bash
Copy code
mvn test
This will execute any test classes or methods that are part of the project.
