# CONNECT+24

CONNECT+24 is a lightweight, single-page room chat app built with plain HTML/CSS/JavaScript and Firebase.

Users can join a room, exchange text messages, and share images/videos in real time.

## Features

- Room-based chat (`#room-name`)
- Anonymous sign-in with Firebase Auth
- Real-time messages with Cloud Firestore
- Image/video uploads with Firebase Storage
- Presence indicator ("Online now")
- Local-only "Clear chat" option
- Mobile-friendly UI

## Tech Stack

- HTML + CSS + vanilla JavaScript
- Firebase:
  - Authentication
  - Cloud Firestore
  - Cloud Storage
- GitHub Pages (deployment via workflow)

## Project Structure

```text
.
├── index.html                  # Full app UI + logic
└── .github/workflows/static.yml # GitHub Pages deployment workflow
```

## Setup

1. Create a Firebase project.
2. Enable **Authentication** with **Anonymous** provider.
3. Create a **Cloud Firestore** database.
4. Enable **Cloud Storage**.
5. Open `index.html` and replace the `firebaseConfig` object values:

```js
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "000000000000",
  appId: "YOUR_APP_ID"
};
```

## Run Locally

Because this is a static app, you can run it with any static server from the repository root:

```bash
python -m http.server 8080
```

Then open: `http://localhost:8080`

## Deployment

This repository includes a GitHub Actions workflow at:

`.github/workflows/static.yml`

On pushes to `main`, it deploys the repository as static content to GitHub Pages.

## Usage

1. Enter your name.
2. Enter a room code (example: `friends`).
3. Join and start chatting.
4. Use 📎 to share images/videos.

## Notes

- "Clear chat" clears messages only on the current device using local storage.
- Upload size is limited to 20 MB per file.
- If uploads are unavailable, ensure Firebase Storage is enabled and configured correctly.
