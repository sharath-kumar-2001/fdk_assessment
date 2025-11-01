# 💼 Expense Management System (FastAPI + Streamlit)

A minimal **SaaS-style Expense Management System** built with **FastAPI** (backend) and **Streamlit** (frontend).  
It helps organizations manage employee expense submissions, approvals, and dynamic workflows.

---

## 🚀 Features

| Role | Capabilities |
|------|---------------|
| 👨‍💼 **Employee** | Submit expenses, view status, and track approvals |
| 🧾 **Approver / Manager** | Approve or reject employee expenses |
| 🛠️ **Admin** | Configure workflows, view all expense statuses |

---

## 🧩 Tech Stack

- **Backend:** FastAPI  
- **Frontend:** Streamlit  
- **Database:** SQLite (via SQLAlchemy ORM)  
- **Auth:** OAuth2 + JWT  
- **Password Hashing:** Passlib (bcrypt)

---

## 📁 Project Structure

expense-management-system/
│
├── backend/
│ ├── main.py
│ ├── db_setup.py
│ ├── models.py
│ ├── schema.py
│ ├── routers/
│ │ ├── auth.py
│ │ ├── expenses.py
│ │ ├── approvals.py
│ │ └── workflows.py
│ ├── requirements.txt
│ └── .env
│
└── frontend/
├── app.py
└── requirements.txt

🔗 API Endpoints
👤 Authentication (/auth)
Method	Endpoint	Description
POST	/auth/register	Register new user
POST	/auth/login	Login and receive JWT token
💰 Expenses (/expenses)
Method	Endpoint	Description
POST	/expenses/submit	Submit new expense
GET	/expenses/my	View personal expenses
✅ Approvals (/approvals)
Method	Endpoint	Description
GET	/approvals/pending	View pending approvals
GET	/approvals/approved	View approved/rejected expenses
PATCH	/approvals/{step_id}/approve	Approve expense
PATCH	/approvals/{step_id}/reject	Reject expense
⚙️ Workflows (/workflows)
Method	Endpoint	Description
GET	/workflows/	View all workflows
POST	/workflows/	Create new workflow

UI Overview
Page	Description
Login	Authenticate via /auth/login
Submit Expense	Employees create new expenses
My Expenses	Employees view their submissions
Pending Approvals	Approvers view pending requests
Approved / Rejected	Approvers see history
Workflows	Admin can configure workflows
🔐 Example Login Workflow

Login using credentials

Employees → Go to “Submit Expense”

Approvers → Go to “Pending Approvals”

Admins → Configure workflow under “Workflows”

Track everything seamlessly 🎯

# 🩺 Clinic & Expense Management Systems

A combined repository featuring two independent FastAPI-based SaaS products:

1. 🏥 **Clinic Management System** — built to help doctors manage appointments, patients, and availability.  
2. 💼 **Expense Management System** — built to help employees submit and track expenses with multi-level approval.

Both systems are modular, API-driven, and ready for frontend integration (React / Streamlit).

---

## 🧩 Tech Stack (Common)

- **Backend Framework:** FastAPI  
- **Database:** SQLite (via SQLAlchemy ORM)  
- **Authentication:** JWT (OAuth2PasswordBearer)  
- **Frontend:** Streamlit (or React alternative)  
- **Hashing:** Passlib (bcrypt)

---

# 🏥 Clinic Management System

## 📘 Overview

The **Clinic Management System** allows individual doctors to manage:
- Doctor registration and login
- Doctor availability schedules
- Appointment booking and tracking
- Patient appointment management

---

## 📁 Project Structure

clinic-system/
│
├── backend/
│ ├── main.py
│ ├── db_setup.py
│ ├── models.py
│ ├── schema.py
│ ├── routers.py
│ ├── requirements.txt
│ └── .env
│
└── frontend/
├── app.py (Streamlit frontend)
└── requirements.txt

API Endpoints
👨‍⚕️ Doctor Routes (/doctors)
Method	Endpoint	Description
POST	/doctors/doctor_info	Register new doctor
GET	/doctors/doctors_list	List all doctors
GET	/doctors/availability/{doctor_id}	Get doctor’s availability
POST	/doctors/appointments/{doctor_id}	Book appointment
PATCH	/doctors/appointments/{appointment_id}/{status}	Update appointment status
🔐 Auth (/auth)
Method	Endpoint	Description
POST	/auth/register	Register a user (doctor or patient)
POST	/auth/login	User login and token generation

