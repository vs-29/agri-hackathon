# Agri-Seva

A farm-to-buyer marketplace built at [hackathon name, year] by a team of [N]. Farmers list their produce, and buyers find produce near them, filtered by distance and price, without a middleman.

<!-- Add screenshots: save them in a docs/ folder and uncomment.
![Buyer home page with map](docs/buyer-home.png)
![Farmer product listing](docs/farmer-products.png)
-->

## My role

[One or two sentences on what you built, for example: "I built the farmer app's product listing and image upload flow, and the products API (create, update, delete and filtered search)."]


## Features

**Farmer app (`farmer/`)**
- Sign up and log in
- Add produce with a title, description, quantity, unit, price, category and photo
- Edit and delete your own listings

**Buyer app (`buyer/`)**
- Landing page, sign-up and login
- Pick a location with Google Places autocomplete or an India map by state
- Browse and search produce, filtered by distance from you and by maximum price

**API (`backend/`)**
- REST endpoints for users, products and buyers
- JWT authentication, with passwords hashed using bcrypt
- Image uploads with Multer
- Farm addresses converted to coordinates with the Google Maps Geocoding API, so products can be searched by distance

## Tech stack

| Part | Built with |
|---|---|
| Farmer and buyer apps | React, React Router, React Bootstrap, Formik and Yup (buyer), react-simple-maps |
| API | Node.js, Express, Mongoose, express-validator, Multer, JSON Web Tokens, bcryptjs |
| Database | MongoDB |
| External APIs | Google Maps Geocoding and Places |

## Project structure

```
agri-hackathon/
├── farmer/      farmer app (React)
├── buyer/       buyer app (React)
├── backend/     REST API (Express + MongoDB)
│   ├── controllers/   users, products, buyers
│   ├── middleware/    auth check, file upload
│   ├── models/        User, Product
│   ├── routes/
│   └── util/          geocoding helper
└── dashboard/   static admin dashboard page
```

## Run it locally

Requires Node.js, a MongoDB database and a Google Maps API key with Geocoding and Places enabled.

### 1. API

```bash
cd backend
npm install
npm start
```

The API runs on `http://localhost:3001`. Set your MongoDB connection string and Google Maps API key before starting. [Update this step once they are moved into a `.env` file.]

### 2. Farmer app

```bash
cd farmer
npm install
npm start
```

### 3. Buyer app

```bash
cd buyer
npm install
npm start
```

Both apps use port 3000 by default. Start one, then answer **yes** when the second asks to use another port.

## Credits

Forked from [memyselfandglitch/agri-hackathon](https://github.com/memyselfandglitch/agri-hackathon), the team's original repository.
