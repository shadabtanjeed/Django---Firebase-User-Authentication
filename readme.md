# **Django + Firebase User Authentication**

A simple authentication boilerplate using Django, Firebase Authentication, HTML and CSS.

## Demo

https://github.com/user-attachments/assets/7d045a1a-c934-404d-a112-62b5e5157825

## Directory Structure
```markdown
├── django_project/
│   ├── __init__.py
│   ├── firebase.py           # Firebase configuration and initialization
│   ├── settings.py           # Project settings
│   ├── urls.py               # URL routing
│   ├── wsgi.py
│   └── serviceAccountKey.json
├── user_authentication/
│   ├── __init__.py
│   ├── urls.py               # Authentication app URL routing
│   ├── views.py              # Auth views
│   └── templates/
│       ├── login_page.html
│       └── signup_page.html
├── home_page/
│   ├── __init__.py
│   ├── urls.py
│   ├── views.py
│   └── templates/
│       ├── home_page.html    # Landing page after successful login + Logout function
├── .env                      # Environment variables
└── requirements.txt
```

## Prerequisites

* Python 3.8+
* pip
* Firebase Account

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/shadabtanjeed/Django-Firebase-User-Authentication-Boilerplate
   cd Django-Firebase-User-Authentication-Boilerplate
   ```

   Create virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Firebase Setup
    * Go to Firebase Console
    * Create a new project
    * Enable Authentication
    * Add web app to get configuration
    * Download service account key
    * Enable email/password based authentication

4. Environment Configuration
    * Create a `.env` file with the following variables:
        ```bash
        FIREBASE_API_KEY=your_api_key
        FIREBASE_AUTH_DOMAIN=your_auth_domain
        FIREBASE_PROJECT_ID=your_project_id
        FIREBASE_STORAGE_BUCKET=your_storage_bucket
        FIREBASE_MESSAGING_SENDER_ID=your_messaging_sender_id
        FIREBASE_APP_ID=your_app_id
        ```

5. Add `serviceAccountKey.json` file
    * Download the service key json file from firebase:
         * Go to project settings -> Service Accounts -> Generate Private Key
    * Rename it as `serviceAccountKey.json`.
    * Put it in the directory: `django_project`

6. Run the server
   ```bash
   python manage.py runserver
   ```

## Note
   * Due to firebase's limitation with python integration, the signup is handled by backend in the function `signup_view` function whereas the login is handled at client side in `login_view` function.
   * As the authentication system is based on email identifier, "@email.com" is appended at the end of the username while interating with Firebase.
