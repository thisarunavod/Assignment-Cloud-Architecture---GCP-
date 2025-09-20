# Cloud-Enabled Deployment in Action with GCP
### H K T Navod (IJSE - galle branch - 2301682011, thisarunavod@gmail.com)

This project demonstrates a cloud-enabled deployment implementation using Google Cloud Platform (GCP), featuring a Spring Boot microservice backend and a React TypeScript frontend application.

## Project Overview

This assignment showcases the deployment and integration of:

- **Course Service**: A Spring Boot microservice for course management
- **Frontend App**: A React TypeScript application with Material-UI components

## 🎥 Demo Video

Watch the complete demonstration of the running course service and frontend app with GCP database deployment:

**[📹 Screen Recording - Course Service & Frontend App with GCP Deployment](https://drive.google.com/file/d/1oEoCqVqGx9wB0CFaINgioE7NRNgr0a7s/view?usp=sharing)**

## 🏗️ Architecture

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   Frontend App  │────│  Course Service  │────│   GCP Database  │
│   (React/TS)    │    │  (Spring Boot)   │    │   (MySQL)       │
│   Port: 5173    │    │   Port: 8081     │    │   IP: 34.27.220.119 │
└─────────────────┘    └──────────────────┘    └─────────────────┘
```

## 📁 Project Structure
```
cloud-enabled-deployment-in-action-with-GCP/
├── course-service/          # Spring Boot microservice
├── frontend-app/           # React TypeScript application
├── media-service/          # Additional microservice
├── student-service/        # Additional microservice
└── README.md
```

## 🚀 Course Service

### Technology Stack

- **Framework**: Spring Boot 3.x
- **Database**: MySQL (hosted on GCP)
- **ORM**: Spring Data JPA with Hibernate
- **API**: Spring Data REST
- **Build Tool**: Maven
- **Language**: Java

### Key Features

- RESTful API for course management
- Automatic database schema management
- Input validation with Bean Validation
- CORS configuration for frontend integration
- Entity validation and conflict handling

### Course Entity Structure

```java
@Entity
public class Course {
    @Id
    private String id;           // Course ID (e.g., "HDSE")
    private String name;         // Course name
    private String duration;     // Course duration
}
```

### Configuration

- **Local Development**: Port 8081
- **GCP Database**: `jdbc:mysql://34.27.220.119/eca_courses`
- **Profile**: Active profile set to `gcp`

### API Endpoints

- `GET /courses` - Retrieve all courses
- `POST /courses` - Create a new course
- `GET /courses/{id}` - Retrieve a specific course
- `PUT /courses/{id}` - Update a course
- `DELETE /courses/{id}` - Delete a course

### Dependencies

- Spring Boot Starter Web
- Spring Boot Starter Data JPA
- Spring Boot Starter Data REST
- MySQL Connector
- Spring Boot Starter Validation
- Lombok
- Spring Boot DevTools

## 🎨 Frontend App

### Technology Stack

- **Framework**: React 18.2.0 with TypeScript
- **Build Tool**: Vite 5.0.0
- **UI Library**: Material-UI (MUI) 5.14.20
- **Routing**: React Router DOM 6.20.1
- **HTTP Client**: Axios 1.6.2
- **File Handling**: React Dropzone 14.2.3

### Key Features

- Modern Material Design interface
- Responsive navigation system
- Course management functionality
- Student management interface
- Media gallery with file upload
- RESTful API integration

### Application Structure

```
frontend-app/src/
├── components/
│   └── Navigation.tsx          # Main navigation component
├── pages/
│   ├── Dashboard.tsx           # Home dashboard
│   ├── CourseManagement.tsx    # Course CRUD operations
│   ├── StudentManagement.tsx   # Student management
│   └── MediaGallery.tsx        # Media file management
├── services/
│   └── api.ts                  # API service layer
└── App.tsx                     # Main application component
```

### Pages Overview

1. **Dashboard**: Overview and statistics
2. **Course Management**: Full CRUD operations for courses
3. **Student Management**: Student enrollment and management
4. **Media Gallery**: File upload and media management

### Development Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run lint` - Run ESLint
- `npm run preview` - Preview production build

## 🌐 Deployment Configuration

### GCP Database Setup

- **Database Type**: MySQL
- **Host**: 34.27.220.119
- **Database Name**: eca_courses
- **Connection**: JDBC with automatic database creation

### Network Configuration

- **Course Service**: Exposed on port 8081
- **Frontend App**: Development server on port 5173
- **CORS**: Configured for cross-origin requests

## 🔧 Getting Started

### Prerequisites

- Java 17+
- Node.js 18+
- Maven 3.6+
- MySQL access to GCP database

### Running the Course Service

```bash
cd course-service
mvn spring-boot:run
```

### Running the Frontend App

```bash
cd frontend-app
npm install
npm run dev
```

### Access Points

- **Course Service API**: http://localhost:8081
- **Frontend Application**: http://localhost:5173
- **Course API Endpoint**: http://localhost:8081/courses

## 📊 Database Schema

The course service automatically creates and manages the following table:

```sql
CREATE TABLE course (
    id VARCHAR(255) PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    duration VARCHAR(255) NOT NULL
);
```

## 🔒 Security & Validation

- Input validation using Bean Validation annotations
- Pattern matching for course ID and name fields
- Duplicate course ID prevention
- CORS configuration for secure cross-origin requests

## 🎯 Assignment Objectives Achieved

✅ **Microservice Architecture**: Implemented Spring Boot course service  
✅ **Frontend Integration**: React TypeScript application with Material-UI  
✅ **Cloud Deployment**: GCP database integration  
✅ **RESTful API**: Complete CRUD operations  
✅ **Modern UI/UX**: Responsive design with Material Design principles  
✅ **Database Management**: JPA/Hibernate with automatic schema management  
✅ **Cross-Origin Support**: CORS configuration for frontend-backend communication

## 📝 Notes

- The application uses the `gcp` profile for cloud database configuration
- Local database configuration is commented out in `application.properties`
- Frontend communicates with backend through RESTful APIs
- All services are container-ready and cloud-deployable

---

**Assignment Submission**: Cloud-Enabled Deployment in Action with GCP  
**Technologies**: Spring Boot, React, TypeScript, Material-UI, GCP, MySQL  
**Demo Video**: [📹 Watch the complete demonstration](https://drive.google.com/file/d/1oEoCqVqGx9wB0CFaINgioE7NRNgr0a7s/view?usp=sharing)
