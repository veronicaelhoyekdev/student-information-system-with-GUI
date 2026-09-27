# Student Information System

Desktop university management application built with **Java 17, JavaFX, and JDBC**, providing role-based interfaces for students, instructors, and administrators.

## Overview

Student Information System is a Java desktop application for managing academic courses, users, and enrollments through a graphical interface.

The application combines a JavaFX user interface with a relational database accessed through JDBC. Different workflows are provided according to the authenticated user's role, separating student, instructor, and administrative functionality.

## Features

### Students

- User authentication
- Browse available courses
- View course information
- Enroll in courses
- Manage enrolled courses
- Access student-specific academic information

### Instructors

- Instructor authentication
- Access assigned courses
- Manage course-related information
- View student enrollment data

### Administration

- Administrative access
- Course management
- Instructor management
- Student and enrollment management
- Academic data administration

## Tech Stack

| Area | Technology |
| --- | --- |
| Language | Java 17 |
| Desktop UI | JavaFX |
| Database Access | JDBC |
| Database | Relational SQL database |
| Build | Maven |
| Testing | JUnit 5 |

## Architecture

The application separates the graphical interface from database communication:

```text id="3k7jxp"
JavaFX UI
    │
    ▼
Application Logic
    │
    ▼
Database Service
    │
    ▼
JDBC
    │
    ▼
Relational Database
```

Database operations use JDBC and prepared statements to interact with students, instructors, courses, and enrollment data.

## Role-Based Interface

Authentication determines the interface and functionality available to the current user.

```text id="rq4b7s"
                Authentication
                     │
          ┌──────────┼──────────┐
          ▼          ▼          ▼
       Student   Instructor    Admin
          │          │          │
          └──── Role-specific ──┘
                 functionality
```

This provides separate workflows while maintaining a shared database and application layer.

## Database Integration

The application uses JDBC for relational data access.

Database operations include:

- User authentication
- Student and instructor retrieval
- Course creation and retrieval
- Course enrollment
- Enrollment management
- Instructor-course relationships

Parameterized `PreparedStatement` queries are used for database operations.

## Project Structure

```text id="fb3r84"
.
├── src/
│   └── main/
│       ├── java/
│       │   ├── StudentInformationSystemApplication.java
│       │   ├── StudentInformationSystemController.java
│       │   ├── DatabaseService.java
│       │   └── module-info.java
│       │
│       └── resources/
│           └── ...                 # JavaFX resources and assets
│
├── pom.xml
├── mvnw
├── mvnw.cmd
└── .gitignore
```

## Getting Started

### Prerequisites

- Java 17
- Maven or the included Maven Wrapper
- A compatible SQL database configured with the application's expected schema

### Run with Maven

On macOS or Linux:

```bash id="7vq3he"
./mvnw clean javafx:run
```

On Windows:

```bash id="xgph5m"
mvnw.cmd clean javafx:run
```

A compatible database connection must be configured before database-dependent functionality can be used.

## Project Context

Academic software engineering project focused on desktop application development, graphical user interfaces, relational database integration, JDBC, role-based workflows, and persistent academic data management.

## Author

**Veronica El Hoyek**  
Software & AI Engineer

Portfolio: https://veronica-el-hoyek.vercel.app/  
GitHub: https://github.com/veronica-el-hoyek