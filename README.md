# 📍 HAUtogo: Real-Time Faculty Tracking and Class Management

**HAUtogo** is a mobile application developed for the Holy Angel University (HAU) community, focusing on real-time location tracking for professors and personalized schedule management for both students and faculty. Built with Flutter, it utilizes Supabase for secure backend services.

## 🌟 Project Overview

HAUtogo aims to improve campus efficiency by solving two core issues: locating faculty and providing easy access to class timetables. The application intelligently uses **Geofencing** and **Role-Based Logic** to deliver highly relevant and accurate information to every user.

---

## ✨ Main Features

### 1. Real-Time Professor Location Tracking
- **Automatic Broadcasting:** Professors' locations are automatically updated to the database when they are within the defined HAU campus geofence.
- **Student Finder:** Students can search for and view the live location marker of any professor currently on campus.
- **Fix Highlight:** Location updates are robust, resolving initial database errors by correctly mapping the `current_building` and `current_room` columns.

### 2. Role-Based Schedule Management
- **Personalized Timetables:** A dedicated Schedule Page displays a clean, weekly view of classes.
- **Data Differentiation:**
    - **Students:** View their scheduled classes by querying the `students_schedules` table.
    - **Professors:** View their teaching assignments by querying the `schedules` table.

### 3. Navigation and Utility Aids
- **Next Class Info:** Home screen panel displays the time and location of the user's next scheduled class.
- **Professor Navigator:** Professors gain access to a **'Navigate Next Room'** button which instantly centers the map on their next class assignment's location.

### 4. Authentication Suite
- Secure **Login/Logout** functionality.
- Robust **Forgot Password** utility utilizing Supabase email authentication for recovery.
- **Change Password** feature available from the Profile Page.

---

## 🛠️ Technical Stack

| Category | Technology/Tool | Purpose |
| :--- | :--- | :--- |
| **Framework** | Flutter (Dart) | Cross-platform mobile development. |
| **Backend** | Supabase | Authentication, Database, and Realtime services. |
| **Mapping** | `flutter_map`, `latlong2` | Map rendering and coordinate handling. |
| **Location** | `geolocator` | Real-time GPS and Geofencing. |
| **State/UI** | `sliding_up_panel`, `logger` | Dynamic home screen panel and application logging. |

---

## ⚙️ Installation and Setup

### Prerequisites

1.  Flutter SDK installed and configured.
2.  A Supabase project instance with necessary tables (`professors`, `schedules`, `students_schedules`) and RLS (Row Level Security) enabled.

### Steps

1.  **Clone the Repository:**
    ```bash
    git clone [YOUR_REPOSITORY_URL]
    cd hautogo
    ```

2.  **Install Dependencies:**
    ```bash
    flutter pub get
    ```

3.  **Configure Supabase Credentials:**
    Update your application's initialization code (likely in `main.dart`) with your unique Supabase Project URL and Anon Key.

4.  **Run the Application:**
    ```bash
    flutter run
    ```
    *Note: Location permissions must be granted on the device for professor tracking to function.*

---
---

## ✨ Extra Updates & Quality of Life Improvements

These improvements focus on visual branding, user experience, and enhancing the security and reliability of the authentication flows.

### 1. Brand Integration and Visual Identity 🎨
* **Logo Implementation:** The official Holy Angel University (HAU) logo and branding have been integrated across the primary application screens and top navigation bars, ensuring brand consistency.
* **Color Theme:** The application uses a custom theme based on HAU's core colors: **Maroon/Red** (`#550000`) for primary buttons and backgrounds, and **Gold/Yellow** (`#EFBF04`) for selected elements and accents (as seen in `mainPage.dart`).

### 2. Enhanced Authentication Flow and Security 🔒
The password management process is fully implemented across multiple dedicated screens for maximum security and user guidance:

| Screen / Flow | Purpose | Files Involved |
| :--- | :--- | :--- |
| **In-App Password Change** | Allows logged-in users to update their password from the Profile page. | `changePass.dart` |
| **Password Reset (Forgot)** | Initiates the email-based password reset process. | `forgotPass.dart`, `passReset.dart` |
| **Set New Password** | Screen where users land from the reset email link to securely set a new password. | `setNewPass.dart` |
| **Success Feedback** | A dedicated screen that provides clear success confirmation and automatically redirects the user back to the login screen after a successful password update. | `successPassUpd.dart` |

### 3. UI/UX Refinements
* **Modern Navigation:** The `BottomNavigationBar` in `mainPage.dart` uses a shifting type with a custom rounded border (`ClipRRect` and `Radius.circular(100)`), providing a distinct and modern feel.
* **Input Reliability:** Implemented robust form validation and state management in login and password screens (`login.dart`, `forgotPass.dart`) to ensure correct inputs and prevent accidental multiple submissions via loading indicators (`CircularProgressIndicator`).

## 📚 Source Code & Large Files

### Source Code
- All essential source code files (including `README.md`) are contained within this repository.

### Large Files (APKs, Documentation, Presentation)
- Compiled Android APKs, project ZIP archives, and related documentation are available for download in the designated Google Drive folder:
  
  [Download all files here](https://drive.google.com/drive/folders/1au4Zn_Bt1TGJEYeN3BgZAMmLZeEfKwgi?usp=sharing)
