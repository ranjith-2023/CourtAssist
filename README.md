# ⚖️ Court Assist: Hearing Reminder System

**Court Assist** is a robust full-stack solution designed to bridge the gap between legal proceedings and timely information. It allows **Litigants** and **Advocates** to manage case details and receive automated reminders via **Email, SMS, and Background Push Notifications**, ensuring no hearing date is ever overlooked.

---

## 🌟 Key Features

* **Case Tracking:** Add and manage case numbers, parties involved, and upcoming hearing dates.
* **Intelligent Scheduling:** Automated backend tasks that scan for upcoming dates and trigger alerts.
* **Multi-Channel Alerts:**
* **EmailJS:** Professional email summaries of upcoming hearings.
* **SMS Gateway:** High-priority text alerts for immediate updates.
* **Firebase FCM:** Background push notifications sent directly to the device.


* **Data Extraction:** Specialized logic to handle and format date-sensitive case information.
* **Role-Based Access:** Distinct workflows for Advocates managing multiple clients and individual Litigants.

---

## 🛠️ Tech Stack

| Layer | Technology |
| --- | --- |
| **Frontend** | React.js, Tailwind CSS, Firebase (Client SDK), EmailJS |
| **Backend** | Java, Spring Boot, Spring Scheduler, Spring Data JPA |
| **Database** | MySQL |
| **Notification Services** | Firebase Cloud Messaging (FCM), SMS Gateway API |
| **Version Control** | Git |

---

## 📂 Project Structure

```text
CourtAssist/
├── client/                # React.js application
│   ├── public/            # Service workers (Firebase)
│   └── src/               # Components, Context, and Services
├── server/                # Spring Boot application
│   ├── src/main/java/     # Controllers, Models, Services, and Schedulers
│   └── src/main/resources/ # Application properties and SQL scripts
└── README.md

```

---

## 🚀 Getting Started

### Prerequisites

* **Java 17+** & **Maven**
* **Node.js** (v16 or higher)
* **MySQL Server**
* **Firebase Account** (for Cloud Messaging)

### 1. Database Setup

Create a database named `court_assist` in MySQL:

```sql
CREATE DATABASE court_assist;

```

### 2. Backend Configuration (Spring Boot)

Navigate to `server/src/main/resources/application.properties` and configure:

* MySQL credentials (`spring.datasource.username`/`password`)
* SMS Gateway API keys
* Firebase Admin SDK credentials

```bash
cd server
mvn clean install
mvn spring-boot:run

```

### 3. Frontend Configuration (React)

Navigate to the `client` directory and install dependencies:

```bash
cd client
npm install

```

Configure your `.env` file with:

* `REACT_APP_FIREBASE_KEY`
* `REACT_APP_EMAILJS_SERVICE_ID`

```bash
npm start

```

---

## ⚙️ How it Works: The Notification Engine

The heart of Court Assist is the **Scheduled Notification Engine**:

1. **Scanner:** A Spring Boot `@Scheduled` task runs daily to check for hearings occurring in the next 24–48 hours.
2. **Extractor:** The system extracts the user's contact preferences and case details.
3. **Broadcaster:** * **SMS & Email** are sent immediately for the next-day reminder.
* **Firebase FCM** sends a data payload to the registered device token to trigger a background notification.



---

## 📝 License

Distributed under the MIT License. See `LICENSE` for more information.

---

## 👤 Contact

**Ranjith** - [GitHub Profile](https://www.google.com/search?q=https://github.com/ranjith-2023)

**Project Link:** [https://github.com/ranjith-2023/CourtAssist](https://www.google.com/search?q=https://github.com/ranjith-2023/CourtAssist)

---
