# Homies Chat

A simple real-time chat application built with Javascript and Firebase. It allows users to sign in with their Google accounts and chat instantly in a group. This project is designed to help understand how APIs and Firebase Realtime Database work in web development.

Live Demo: [Homies Chat](https://superchat-70bbc.web.app/)

## Technologies Used

- **JavaScript**: Used for all the frontend -> backend functionalities.
- **Firebase**: Backend-as-a-Service (BaaS) used for authentication (Google Sign-In) and storing messages in Firebase Realtime Database.
- **Google Authentication**: Sign-in through Google to authenticate users.

## Features

- **Google Authentication**: Sign in with Google to join the chat.
- **Real-time Messaging**: Chat messages are updated in real time using Firebase Realtime Database.
- **Group Chat**: A single group where all authenticated users can chat instantly.

## Setup Instructions

### Step 1: Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/rajeshcse02/homies-chat
cd homies-chat
```

### Step 2: Install Dependencies

1. **Navigate to the project folder**:

   ```bash
   cd frontend
   ```

2. **Install dependencies**:

   ```bash
   npm install
   ```

### Step 3: Set up Firebase

1. Go to the [Firebase Console](https://console.firebase.google.com/).
2. Create a new project if you haven't already.
3. Set up Firebase Authentication:
   - In the Firebase console, go to **Authentication** and enable **Google** as a sign-in provider.
4. Set up Firebase Realtime Database:
   - Go to **Database** in the Firebase console and choose **Realtime Database**.
   - Create a new database and set its rules to allow read/write operations during development:
   
     ```json
     {
       "rules": {
         ".read": "auth != null",
         ".write": "auth != null"
       }
     }
     ```

5. Create a `.env` file in the root of the project and add the Firebase configuration keys:

   ```env
   FIREBASE_API_KEY=your-firebase-api-key
   FIREBASE_AUTH_DOMAIN=your-firebase-auth-domain
   FIREBASE_PROJECT_ID=your-firebase-project-id
   FIREBASE_APP_ID=your-firebase-app-id
   ```

   - You can find these keys in the Firebase console under **Project Settings** > **General** > **Your apps** > **Firebase SDK snippet**.

### Step 4: Run the Application

1. **Start the React development server**:

   ```bash
   npm start
   ```

2. Open the app in your browser at `http://localhost:3000`.

### Step 5: Google Sign-In

Once the app is running, you will be prompted to sign in with Google. After signing in, you can start chatting in the group!

## Deployment

This app is deployed using Firebase Hosting. You can deploy it to your Firebase project by following these steps:

1. **Install Firebase CLI** (if not already installed):

   ```bash
   npm install -g firebase-tools
   ```

2. **Log in to Firebase**:

   ```bash
   firebase login
   ```

3. **Initialize Firebase Hosting**:

   ```bash
   firebase init hosting
   ```

   Choose the Firebase project you want to deploy to, and configure it to use `build` as the public directory.

4. **Build the React app**:

   ```bash
   npm run build
   ```

5. **Deploy to Firebase Hosting**:

   ```bash
   firebase deploy
   ```

## Contributing

Feel free to fork this repository and submit pull requests with bug fixes, improvements, or new features.

## License

This project is open source.
