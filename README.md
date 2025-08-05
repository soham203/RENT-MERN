# RentEase

A full-stack property rental and management platform, allowing users to register as renters or owners, post and book properties, and manage bookings. Includes admin features for user and property management.

---

## Table of Contents
- [Features](#features)
- [Project Structure](#project-structure)
- [Tech Stack](#tech-stack)
- [Setup & Installation](#setup--installation)
- [Environment Variables](#environment-variables)
- [API Overview](#api-overview)
- [Frontend Overview](#frontend-overview)
- [Backend Overview](#backend-overview)
- [Screenshots](#screenshots)
- [License](#license)

---

## Features
- User registration/login (Renter, Owner, Admin)
- Owners can post, edit, and delete properties with images
- Renters can browse, filter, and book properties
- Admins can manage users, properties, and bookings
- Password reset functionality
- JWT-based authentication
- Responsive UI with filtering and modals

---

## Project Structure
```
Project Rent/
  client/      # React frontend
  server/      # Node.js/Express backend
```

---

## Tech Stack
- **Frontend:** React, React Router, Bootstrap, MUI, Ant Design, Axios
- **Backend:** Node.js, Express, MongoDB, Mongoose, JWT, Multer, BcryptJS, Dotenv, Nodemon

---

## Setup & Installation

### Prerequisites
- Node.js (v14+ recommended)
- MongoDB instance (local or cloud)

### 1. Clone the repository
```bash
git clone <repo-url>
cd Project\ Rent
```

### 2. Install dependencies
```bash
cd client
npm install
cd ../server
npm install
```

### 3. Environment Variables
Create a `.env` file in the `server/` directory:
```
MONGO_DB=<your-mongodb-connection-string>
JWT_KEY=<your-jwt-secret>
PORT=8001
```

### 4. Start the development servers
- **Backend:**
  ```bash
  cd server
  npm start
  ```
- **Frontend:**
  ```bash
  cd client
  npm start
  ```

---

## Environment Variables
- `MONGO_DB`: MongoDB connection string
- `JWT_KEY`: Secret key for JWT
- `PORT`: (optional) Port for backend (default: 8001)

---

## API Overview

### User APIs (`/api/user`)
- `POST /register` — Register as Renter/Owner
- `POST /login` — Login
- `POST /forgotpassword` — Reset password
- `GET /getAllProperties` — List all properties
- `POST /getuserdata` — Get user data (auth required)
- `POST /bookinghandle/:propertyid` — Book a property (auth required)
- `GET /getallbookings` — Get all bookings for a user (auth required)

### Owner APIs (`/api/owner`)
- `POST /postproperty` — Add property (auth required, multipart)
- `GET /getallproperties` — List owner properties (auth required)
- `DELETE /deleteproperty/:propertyid` — Delete property (auth required)
- `PATCH /updateproperty/:propertyid` — Update property (auth required, multipart)
- `GET /getallbookings` — Owner's bookings (auth required)
- `POST /handlebookingstatus` — Change booking/property status (auth required)

### Admin APIs (`/api/admin`)
- `GET /getallusers` — List all users (auth required)
- `POST /handlestatus` — Grant/ungrant owner status (auth required)
- `GET /getallproperties` — List all properties (auth required)
- `GET /getallbookings` — List all bookings (auth required)

---

## Frontend Overview
- **Home Page:** Carousel, property listings, navigation
- **Authentication:** Login, Register, Forgot Password (with role selection)
- **Renter:** Browse/filter properties, book, view bookings
- **Owner:** Add/edit/delete properties, view/manage bookings
- **Admin:** Manage users (grant/ungrant owners), view all properties/bookings
- **UI:** Responsive, uses Bootstrap, MUI, Ant Design

---

## Backend Overview
- **Express server** (`server/index.js`)
- **MongoDB models:** User, Property, Booking
- **Authentication:** JWT, bcrypt password hashing
- **File uploads:** Multer for property images
- **Routes:** Modularized for user, owner, admin
- **Environment config:** Dotenv

---

## Screenshots

<img width="1919" height="972" alt="Screenshot 2025-08-05 153243" src="https://github.com/user-attachments/assets/3202e503-1ec2-411d-aa6e-4c387cb440b4" />
<img width="1919" height="964" alt="Screenshot 2025-08-05 153251" src="https://github.com/user-attachments/assets/3ab7d18f-5a44-4bd9-92d7-92fa9607f67c" />
<img width="1919" height="971" alt="Screenshot 2025-08-05 153330" src="https://github.com/user-attachments/assets/91396bdc-3c49-4c1e-9dca-2977f8382222" />
<img width="1919" height="969" alt="Screenshot 2025-08-05 153532" src="https://github.com/user-attachments/assets/01e7a1e8-fc3b-4bb8-8925-77c3858536a3" />
