# Smart Campus Hub

## 1. REST API
1.  Introduction:
    -   Brief overview of the School Management Website and its core features.
    -   Explanation of the purpose and benefits of the API.
2.  Authentication and Authorization:

    -   How to obtain API keys or tokens for authentication.
    -   Explanation of authorization levels for different endpoints.
3.  Base URL and Endpoints:

    -   Base URL for API requests.
    -   List of available endpoints, categorized by features (Attendance, Progress Reports, Fee management, etc.).
4.  Request and Response Formats:

    -   Description of the supported request methods (GET, POST, PUT, DELETE).
    -   Examples of request payloads and response structures in JSON format.
5.  Common Request Headers:

    -   List of headers to include in API requests (e.g., Content-Type, Authorization).
6.  Error Handling:

    -   Explanation of possible error responses and their corresponding HTTP status codes.
    -   Sample error response formats.
7.  Attendance API:

    -   Explanation of endpoints related to attendance tracking.
    -   Details about request parameters and expected responses.
    -   Sample request and response examples for each endpoint.
8.  Progress Reports API:

    -   Explanation of endpoints for accessing student progress reports.
    -   Details about request parameters and expected responses.
    -   Sample request and response examples for each endpoint.
9.  Fee Management API:

    -   Explanation of endpoints for handling fee-related operations.
    -   Details about request parameters and expected responses.
    -   Sample request and response examples for each endpoint.
10. Sample Workflows:
    -   Step-by-step examples of how to use the API for common tasks (e.g., marking attendance, retrieving progress reports, processing fee payments).



## 2. User Interface

### Key Features 

#### Attendance Tracking
-   Intuitive interface for marking student attendance.
-   Visual cues for attendance status.
-   Interactive calendar for selecting dates.

#### Progress Reports
-   Access to comprehensive progress reports for individual students.
-   Graphical representations of academic performance.
-   User-friendly layout for easy navigation.

#### Fee Management
-   Efficient fee payment and management interface.
-   Display of pending and paid fees.
-   Clear breakdown of fee components.

  
### Design Principles 
-   Simplicity: Our UI design follows a clean and intuitive layout to ensure ease of use for all users.
-   Consistency: Consistent use of colours, typography, and components creates a unified and recognizable interface.
-   User-Centered Design: The UI is designed with the user's needs and tasks in mind, enhancing the overall user experience.

### Technologies Used
-   Angular: Front-end framework for building dynamic and responsive UI components.
-   JavaScript: Programming language used for interactive and dynamic behaviours.
-   Bootstrap: CSS framework for consistent styling and responsive design.
-   CSS3: Styling language for customizing the appearance of UI elements.


   
## 3. Schema Structure
- students:
  - student_id (Primary Key)
  - first_name
  - last_name
  - date_of_birth
  - gender
  - contact_number
  - email
  - address
  

- teachers:
  - teacher_id (Primary Key)
  - first_name
  - last_name
  - date_of_birth
  - gender
  - contact_number
  - email
  - address
  - subject_taught

- courses:
  - course_id (Primary Key)
  - course_name
  - description
  
- classes:
  - class_id (Primary Key)
  - class_name
  - teacher_id (Foreign Key to teachers table)

- subjects:
  - subject_id (Primary Key)
  - subject_name
  - teacher_id (Foreign Key to teachers table)

- attendance:
  - attendance_id (Primary Key)
  - student_id (Foreign Key to students table)
  - class_id (Foreign Key to classes table)
  - date
  - status (e.g., "present," "absent")

- exams:
  - exam_id (Primary Key)
  - subject_id (Foreign Key to subjects table)
  - date
  - start_time
  - end_time

- results:
  - result_id (Primary Key)
  - exam_id (Foreign Key to exams table)
  - student_id (Foreign Key to students table)
  - score
  - grade

- fees:
  - fee_id (Primary Key)
  - course_id (Foreign Key to courses table)
  - amount
  - due_date

- payments:
  - payment_id (Primary Key)
  - student_id (Foreign Key to students table)
  - amount
  - payment_date

- timetable:
  - timetable_id (Primary Key)
  - class_id (Foreign Key to classes table)
  - subject_id (Foreign Key to subjects table)
  - teacher_id (Foreign Key to teachers table)
  - day_of_week
  - time_slot

- library:
  - book_id (Primary Key)
  - title
  - author
  - publication_year
  - availability_status


