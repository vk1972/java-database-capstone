## MySQL Database Design

### Table: patients
- id: INT, Primary Key, Auto Increment
- name: VARCHAR(30)

### Table: doctors 
- id: INT, Primary Key, Auto Increment
- name: VARCHAR(3 - 100)
- speciality: VARCHAR(3 - 50)
- email: VARCHAR(30), not mull
- password: VARCHAR(30), not null
- phone: VARCHAR(30)

### Table: availableTimes
- doctor_id: INT, Foreign Key → doctors(id)
- availableTime

### Table: admin
- id: INT, Primary Key, Auto Increment
- username: VARCHAR(100)
- password: VARCHAR(30)

### Table: clinic_locations
- id: INT, Primary Key, Auto Increment
- location: VARCHAR(30)

### Table: payments
- id: INT, Primary Key, Auto Increment
- amount: DECIMAL(1000, 2)

### Table: appointments
- id: INT, Primary Key, Auto Increment
- doctor_id: INT, Foreign Key → doctors(id)
- patient_id: INT, Foreign Key → patients(id)
- appointment_time: DATETIME, Not Null
- status: INT (0 = Scheduled, 1 = Completed, 2 = Cancelled)

## MongoDB Collection Design

### Collection: prescriptions
json
{
  "_id": "ObjectId('64abc123456')",
  "patientName": "John Smith",
  "appointmentId": 51,
  "medication": "Paracetamol",
  "dosage": "500mg",
  "doctorNotes": "Take 1 tablet every 6 hours.",
  "refillCount": 2,
  "pharmacy": {
    "name": "Walgreens SF",
    "location": "Market Street"
  }
}
