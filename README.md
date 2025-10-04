# Hospital Management System (SQL Project)

Hospitals are an essential part of human life. They provide the best possible medical facilities to people suffering from different types of illnesses, which may be caused due to climate change, work pressure, emotional trauma, stress, and many other factors.  

Since hospitals interact with a large number of patients and staff on a daily basis, it becomes very difficult to maintain records and day-to-day activities manually. To overcome this problem, a **Hospital Management Database** is required to keep track of all activities in a structured manner.

The aim of this project is to demonstrate how data related to hospital operations can be stored, managed, and retrieved efficiently using **MySQL Database Management System**. By storing information in a relational database, hospital tasks such as doctor management, patient history, diagnoses, and procedures can be handled easily and in an organized way.

---

## 🎯 Objectives of the Project
- Maintain information about doctors, nurses, departments, patients, and procedures.  
- Manage doctor affiliations with different departments.  
- Keep records of patient diagnoses, prescriptions, and medical history.  
- Provide efficient and quick retrieval of data for analysis and reporting.  
- Eliminate redundancy and ensure data integrity through **primary and foreign key constraints**.  

---

## 🗂️ Database Design

The database contains the following **7 tables**:

1. **Physician** – stores details of doctors working in the hospital.  
2. **Department** – stores all the departments and their heads.  
3. **Affiliated_with** – stores the relationship between physicians and departments.  
4. **Nurse** – stores details of nurses working in the hospital.  
5. **Patient** – stores patient personal details and their primary physician.  
6. **Patient_Diagnosis** – stores patient diagnosis information and prescriptions.  
7. **Procedures** – stores details of various hospital procedures/tests.  

---

## 🛠️ Technology Used
- **Database**: MySQL  
- **Language**: SQL  
- **Features**:  
  - Table creation with constraints (Primary Key, Foreign Key).  
  - Data insertion for realistic hospital scenarios.  
  - Queries to retrieve and analyze hospital data.  

---

## 📌 Example Queries
Some sample queries that can be run on this database:  

```sql
-- List all physicians working in the hospital
SELECT * FROM Physician;

-- Find all patients diagnosed with Asthma
SELECT p.name, p.surname, d.Diagnosis, d.Prescription
FROM Patient p
JOIN Patient_Diagnosis d ON p.patient_id = d.Patient_ID
WHERE d.Diagnosis = 'Asthma';

-- Show all doctors affiliated with the Surgery department
SELECT phy.name, dept.dept_name
FROM Physician phy
JOIN affiliated_with aw ON phy.employeeid = aw.physicianid
JOIN Department dept ON dept.department_id = aw.departmentid
WHERE dept.dept_name = 'Surgery';

-- List all procedures with cost greater than 3000
SELECT * FROM procedures WHERE cost > 3000;
