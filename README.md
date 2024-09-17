# Medical Clinic Information System

## Table of Contents
1. [Introduction](#introduction)
2. [ER Model Diagram](#er-model-diagram)
3. [Patient Management](#patient-management)
4. [Clinical Operations](#clinical-operations)
5. [Prescription and Inventory Management](#prescription-and-inventory-management)
6. [Tables and Functionality](#tables-and-functionality)
   - [Patients](#patients)
   - [Medical Records](#medical-records)
   - [Appointments](#appointments)
   - [Doctors](#doctors)
   - [Prescriptions](#prescriptions)
   - [Staff](#staff)
   - [Inventory](#inventory)
   - [Feedback](#feedback)
   - [Emergency Handover](#emergency-handover)
7. [Basic Functions](#basic-functions)
8. [Volume of Data the Application Will Handle](#volume-of-data-the-application-will-handle)

## Introduction
Millions of medical clinics globally rely on information systems to improve their operations and reduce administrative burdens. Our team has developed the **A1: Medical Clinic Information System**, designed to solve prevalent issues in clinics like data security, real-time access, patient involvement, and more. This system enhances traditional clinic systems with added functionality such as patient feedback management and emergency handovers.

The project is structured around three main categories:
1. **Patient Management**: Manages patient information, medical records, and emergency handovers.
2. **Clinical Operations**: Manages clinic staff, appointments, and feedback.
3. **Prescription and Inventory Management**: Oversees prescriptions and inventory.

## ER Model Diagram

The ER model diagram for the Medical Clinic Information System is shown below:

<img src="./A2%20ER%20Model_white.jpg" alt="ER Model Diagram" width="800" height="600" />

## Patient Management
This module centralizes patient data, including personal information, medical records, and emergency handovers. This data is crucial for personalized medical care, making it accessible to doctors and clinical staff in real time.

## Clinical Operations
Handles daily clinic functions such as managing doctors and staff schedules, tracking appointments, and gathering feedback from patients. Streamlining these operations helps increase efficiency and improve patient care.

## Prescription and Inventory Management
Ensures accurate tracking of prescriptions and medical inventory, preventing shortages and enabling quick replenishment. This module also supports the management of medication information for each patient.

## Tables and Functionality

### Patients
Stores all necessary patient information.
- **Fields**: `PatientID (P)`, `FirstName`, `LastName`, `DOB`, `Weight`, `Height`, `Gender`, `PhoneNum`, `Problem`, `Insurance`, `EmergencyContact`.
- **Functionality**: Facilitates accurate patient demographics and contact info retrieval.

### Medical Records
Centralizes all medical history and treatment records for each patient.
- **Fields**: `RecordID (P)`, `PatientID (F)`, `PrescriptionID (F)`, `Treatments`, `Allergies`, `History`, `AppointmentLog`, `BradenScale`, `DARatingScale`, `MedicalImagery`.
- **Functionality**: Tracks patient medical history for informed treatment decisions.

### Appointments
Records scheduled, canceled, and completed appointments.
- **Fields**: `AppointmentID (P)`, `PrescriptionID (F)`, `PatientID (F)`, `DoctorID (F)`, `Consultations`, `BookingTime`, `InitialDiagnosis`, `Status`.
- **Functionality**: Facilitates appointment scheduling and patient-doctor interactions.

### Doctors
Stores all information related to clinic doctors.
- **Fields**: `DoctorID (P)`, `RecordID (F)`, `FirstName`, `LastName`, `PhoneNum`, `Address`, `Specialization`, `PatientHistory`, `ShiftID`, `ShiftIn`, `ShiftOut`, `EmergencyContact`.
- **Functionality**: Assigns doctors to patients, manages shift schedules, and tracks availability.

### Prescriptions
Contains all prescriptions issued to patients.
- **Fields**: `PrescriptionID (P)`, `PatientID (F)`, `DoctorID (F)`, `Medication`, `Dosage`, `StartDate`, `EndDate`, `Notes`, `Quantity`, `Refills`.
- **Functionality**: Tracks prescriptions to ensure patients receive the correct medication.

### Staff
Contains details about clinic staff (excluding doctors).
- **Fields**: `StaffID (P)`, `FirstName`, `LastName`, `PhoneNum`, `Address`, `Role`, `ShiftID`, `ShiftIn`, `ShiftOut`, `EmergencyContact`.
- **Functionality**: Helps manage staff schedules and resource allocation.

### Inventory
Manages clinic inventory, ensuring availability of essential items.
- **Fields**: `ItemID (P)`, `ItemOut`, `ItemIn`, `ItemName`, `Quantity`, `Supplier`, `Waste`.
- **Functionality**: Tracks item quantities and suppliers, ensuring optimal stock levels.

### Feedback
Captures patient feedback to assess clinic performance.
- **Fields**: `FeedbackID (P)`, `PatientID (F)`, `DoctorID (F)`, `Date`, `Rating`, `Comments`.
- **Functionality**: Collects feedback for service improvement and quality assurance.

### Emergency Handover
Manages emergency patient transfers to external facilities.
- **Fields**: `RecordID (P)`, `PatientID (F)`, `DoctorID (F)`, `ClinicName`, `Description`, `Facility`, `Date`.
- **Functionality**: Facilitates the transfer of patients to other medical facilities during emergencies.

## Basic Functions
The system supports several key functions to streamline clinic operations:
- **Add New Patient**: Registers a new patient in the system.
- **Prescribe Medication**: Issues prescriptions to patients, tracking dosage and refill info.
- **Schedule Appointments**: Allows staff to create, confirm, or cancel appointments.
- **Check Stock**: Monitors and manages inventory levels.
- **Register Stock**: Registers new stock, triggering replenishment orders as needed.
- **Handover Patient**: Manages emergency patient transfers with detailed medical information.

## Volume of Data the Application Will Handle
The system is designed to handle the following estimated volumes of data:
- **Patients**: ~830 records
- **Medical Records**: ~8,300 records
- **Appointments**: ~4,150 appointments annually
- **Doctors**: ~8 records
- **Prescriptions**: ~16,500 prescriptions per year
- **Staff**: ~16 records
- **Inventory**: ~41 items with transaction history
- **Feedback**: ~833 feedback entries annually
- **Emergency Handovers**: ~83 handovers annually

Overall, the system is designed to manage a large volume of data efficiently, ensuring scalability and performance for growing clinics.
