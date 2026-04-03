# Fusion Electronics: A MERN-Stack E-commerce Application

Welcome to **Fusion Electronics**, a **MERN-Stack E-commerce Application**! This project is a working demo of a full-stack web application that was built using the MERN stack (MongoDB, Express.js, React.js, Node.js). Additionally, it also includes features such as user authentication, checkout process, product recommendations with vector search, and more!

It also aims to provide a comprehensive example of building a modern e-commerce platform, covering frontend user interface, backend server logic, database management, and integration with third-party libraries. Let's dive in!

<p align="center">
  <a href="https://fusion-ecommerce-app.vercel.app/" target="_blank">
    <img src="docs/logo.png" alt="Fusion Electronics Logo" style="border-radius: 10px" width="35%"/>
  </a>
</p>

## Table of Contents

1. [Introduction](#introduction)
2. [Live Deployment](#live-deployment)
3. [User Interface](#user-interface)
   - [Home Page](#home-page)
   - [Full Product List](#full-product-list)
   - [Cart Page](#cart-page)
   - [Checkout Page](#checkout-page)
4. [Features](#features)
5. [Technologies Used](#technologies-used)
6. [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
7. [Project Structure](#project-structure)
8. [Running the Application](#running-the-application)
9. [Product Recommendations with Vector Database](#product-recommendations-with-vector-database)
10. [Testing the APIs](#testing-the-apis)
11. [Unit & Integration Testing](#unit--integration-testing)
    - [Backend Tests](#backend-tests)
    - [Frontend Tests](#frontend-tests)
12. [Swagger API Documentation](#swagger-api-documentation)
13. [OpenAPI Specification](#openapi-specification)
    - [Using the `openapi.yaml` File](#using-the-openapiyaml-file)
14. [Deployment](#deployment)
15. [Containerization](#containerization)
16. [GitHub Actions & CI/CD](#github-actions--cicd)
17. [Contributing](#contributing)
18. [License](#license)
19. [Creator](#creator)

## Introduction

This project is a demonstration of building an e-commerce application using the MERN stack, which consists of MongoDB (database), Express.js (server), React.js (frontend), and Node.js (runtime environment). The application allows users to browse products, add them to a shopping cart, proceed to checkout, and simulate the order processing. It includes comprehensive validations for user inputs and simulates the checkout process on the backend.

The application is designed to be user-friendly and responsive, providing a seamless shopping experience. It also includes features such as product search, user authentication, and order confirmation. Additionally, it uses Pinecone (with optional Weaviate support) for product recommendations based on vector search, enhancing the user experience by suggesting relevant products.

<p align="center">
  <a href="https://react.dev">
    <img src="https://img.shields.io/badge/React-18.x-61DAFB?logo=react&logoColor=white" alt="React badge" />
  </a>
  <a href="https://nodejs.org/">
    <img src="https://img.shields.io/badge/Node.js-18.x-339933?logo=node.js&logoColor=white" alt="Node.js badge" />
  </a>
  <a href="https://expressjs.com/">
    <img src="https://img.shields.io/badge/Express-4.x-000000?logo=express&logoColor=white" alt="Express badge" />
  </a>
  <a href="https://www.mongodb.com/">
    <img src="https://img.shields.io/badge/MongoDB-6.x-47A248?logo=mongodb&logoColor=white" alt="MongoDB badge" />
  </a>
  <a href="https://jestjs.io/">
    <img src="https://img.shields.io/badge/Jest-29.x-C21325?logo=jest&logoColor=white" alt="Jest badge" />
  </a>
  <a href="https://mui.com/">
    <img src="https://img.shields.io/badge/Material--UI-5.x-007FFF?logo=mui&logoColor=white" alt="Material UI badge" />
  </a>
  <a href="https://weaviate.io/">
    <img src="https://img.shields.io/badge/Weaviate-Vector%20Database-FF6F00?logo=weblate&logoColor=white" alt="Weaviate badge" />
  </a>
  <a href="https://www.pinecone.io/">
    <img src="https://img.shields.io/badge/Pinecone-Vector%20Database-0f9d58?logo=pinecone&logoColor=white" alt="Pinecone badge" />
  </a>
  <a href="https://https://ai.meta.com/tools/faiss/">
    <img src="https://img.shields.io/badge/FAISS-Vector%20Search-00A4FF?logo=facebook&logoColor=white" alt="FAISS badge" />
  </a>
  <a href="https://www.langchain.com">
    <img src="https://img.shields.io/badge/LangChain-LLM%20Framework-00A4FF?logo=langchain&logoColor=white" alt="LangChain badge" />
  </a>
  <a href="https://www.npmjs.com/">
    <img src="https://img.shields.io/badge/npm-Node%20Package%20Manager-CB3837?logo=npm&logoColor=white" alt="npm badge" />
  </a>
  <a href="https://kubernetes.io/">
    <img src="https://img.shields.io/badge/Kubernetes-Container%20Orchestration-326CE5?logo=kubernetes&logoColor=white" alt="Kubernetes badge" />
  </a>
  <a href="https://aws.amazon.com/">
    <img src="https://img.shields.io/badge/AWS-Cloud%20Platform-FF9900?logo=amazonaws&logoColor=white" alt="AWS badge" />
  </a>
  <a href="https://vercel.com/">
    <img src="https://img.shields.io/badge/Vercel-Deploy-000000?logo=vercel&logoColor=white" alt="Vercel badge" />
  </a>
  <a href="https://www.render.com/">
    <img src="https://img.shields.io/badge/Render-Deploy-46E3B7?logo=render&logoColor=white" alt="Render badge" />
  </a>
  <a href="https://swagger.io/">
    <img src="https://img.shields.io/badge/Swagger-API%20Docs-85EA2D?logo=swagger&logoColor=black" alt="Swagger badge" />
  </a>
  <a href="https://www.docker.com/">
    <img src="https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker&logoColor=white" alt="Docker badge" />
  </a>
  <a href="https://jestjs.io/">
    <img src="https://img.shields.io/badge/Jest-Testing-C21325?logo=jest&logoColor=white" alt="Jest badge" />
  </a>
  <a href="https://reactjs.org/">
    <img src="https://img.shields.io/badge/React%20Testing%20Library-Testing-FF4088?logo=react&logoColor=white" alt="React Testing Library badge" />
  </a>
  <a href="https://git-scm.com/">
    <img src="https://img.shields.io/badge/Git-VersionControl-F05032?logo=git&logoColor=white" alt="Git badge" />
  </a>
  <a href="https://www.postman.com/">
    <img src="https://img.shields.io/badge/Postman-API%20Testing-FF6C37?logo=postman&logoColor=white" alt="Postman badge" />
  </a>
  <a href="https://axios-http.com/">
    <img src="https://img.shields.io/badge/Axios-HTTP%20Client-5A29E4?logo=axios&logoColor=white" alt="Axios badge" />
  </a>
  <a href="https://reactrouter.com/">
    <img src="https://img.shields.io/badge/React%20Router-Routing-DD0031?logo=reactrouter&logoColor=white" alt="React Router badge" />
  </a>
  <a href="https://babel.io/">
    <img src="https://img.shields.io/badge/Babel-Transpiler-F9DC3E?logo=babel&logoColor=black" alt="Babel badge" />
  </a>
  <a href="https://webpack.js.org/">
    <img src="https://img.shields.io/badge/Webpack-Bundler-8DD6F9?logo=webpack&logoColor=black" alt="Webpack badge" />
  </a>
  <a href="https://craco.js.org/">
    <img src="https://img.shields.io/badge/CRACO-Configuration-61DAFB?logo=react&logoColor=white" alt="CRACO badge" />
  </a>
  <a href="https://react-hook-form.com/">
    <img src="https://img.shields.io/badge/React%20Hook%20Form-Forms-EC5990?logo=reacthookform&logoColor=white" alt="React Hook Form badge" />
  </a>
  <a href="https://fkhadra.github.io/react-toastify/">
    <img src="https://img.shields.io/badge/React%20Toastify-Notifications-FF8800?logo=react&logoColor=white" alt="React Toastify badge" />
  </a>
  <a href="https://www.npmjs.com/package/react-credit-cards-2">
    <img src="https://img.shields.io/badge/React%20Credit%20Cards-Credit%20Card-FFCA28?logo=creditcard&logoColor=black" alt="React Credit Cards badge" />
  </a>
</p>

## Live Deployment

The application is deployed live on Vercel. You can access it at the following URL: **[Fusion Electronics App](https://fusion-ecommerce-app.vercel.app).**

The **primary** backend server is deployed on Vercel and can be accessed at the following URL: **[Fusion Electronics API](https://fusion-electronics-api.vercel.app/)**.

The **backup** backend server is deployed on Render and can be accessed at the following URL: **[Fusion Electronics API](https://fusion-electronics-api.vercel.app/).**

> [!IMPORTANT]
> **Note**: The backend server may take a few seconds to wake up if it has been inactive for a while. For your information, it is hosted on the free tier of Render, with 0.1 CPU and 512 MB of memory only, so it may take a bit longer to respond to requests, especially after periods of inactivity.

> [!CAUTION]
> **Warning**: The vector recommendation pipeline relies on Pinecone's serverless index (free tier). Please make sure your Pinecone project has enough credits and remains active; otherwise, recommendation calls may fall back to heuristic suggestions. You can always run the application locally and provision your own Pinecone and/or Weaviate instances—see [Product Recommendations with Vector Database](#product-recommendations-with-vector-database) for setup details.

## User Interface

### Home Page

<p align="center">
    <img src="docs/home-ui.png" alt="Fusion Electronics Homepage" style="border-radius: 10px" width="100%"/>
</p>

### Recommended Products (based on user interaction)

<p align="center">
    <img src="docs/recommended-products-ui.png" alt="Fusion Electronics Recommended Products" style="border-radius: 10px" width="100%"/>
</p>

### Full Product List

<p align="center">
    <img src="docs/products-ui.png" alt="Fusion Electronics Products List" style="border-radius: 10px" width="100%"/>
</p>

### Search Results

<p align="center">
    <img src="docs/search-results-ui.png" alt="Fusion Electronics Search Results" style="border-radius: 10px" width="100%"/>
</p>

### Product Details Page

<p align="center">
    <img src="docs/product-details-ui.png" alt="Fusion Electronics Product Details Page" style="border-radius: 10px" width="100%"/>
</p>

### Cart Page

<p align="center">
    <img src="docs/cart-ui.png" alt="Fusion Electronics Cart Page" style="border-radius: 10px" width="100%"/>
</p>

### Checkout Page

<p align="center">
    <img src="docs/checkout-ui.png" alt="Fusion Electronics Checkout Page" style="border-radius: 10px" width="100%"/>
</p>

### Support Page

<p align="center">
    <img src="docs/support-ui.png" alt="Fusion Electronics Support Page" style="border-radius: 10px" width="100%"/>
</p>

### About Page

<p align="center">
    <img src="docs/about-ui.png" alt="Fusion Electronics About Page" style="border-radius: 10px" width="100%"/>
</p>

### Order Confirmation

<p align="center">
    <img src="docs/order-ui.png" alt="Fusion Electronics Order Success Page" style="border-radius: 10px" width="100%"/>
</p>

### Order Tracking

<p align="center">
    <img src="docs/order-tracking-ui.png" alt="Fusion Electronics Order Tracking Page" style="border-radius: 10px" width="100%"/>
</p>

### Shipping & Returns

<p align="center">
    <img src="docs/shipping-ui.png" alt="Fusion Electronics Shipping & Returns Page" style="border-radius: 10px" width="100%"/>
</p>

### Terms of Service

<p align="center">
    <img src="docs/terms-ui.png" alt="Fusion Electronics Terms of Service Page" style="border-radius: 10px" width="100%"/>
</p>

### Privacy Policy

<p align="center">
    <img src="docs/privacy-ui.png" alt="Fusion Electronics Privacy Policy Page" style="border-radius: 10px" width="100%"/>
</p>

### Login Page

<p align="center">
    <img src="docs/login-ui.png" alt="Fusion Electronics Login Page" style="border-radius: 10px" width="100%"/>
</p>

### Register Page

<p align="center">
    <img src="docs/register-ui.png" alt="Fusion Electronics Register Page" style="border-radius: 10px" width="100%"/>
</p>

### Forgot Password Page

<p align="center">
    <img src="docs/forgot-password-ui.png" alt="Fusion Electronics Forgot Password Page" style="border-radius: 10px" width="100%"/>
</p>

### Reset Password Page

<p align="center">
    <img src="docs/reset-password-ui.png" alt="Fusion Electronics Reset Password Page" style="border-radius: 10px" width="100%"/>
</p>

### Footer

<p align="center">
    <img src="docs/footer.png" alt="Fusion Electronics Footer" style="border-radius: 10px" width="100%"/>
</p>

## Features

- **Product Management:**
    - View a list of products.
    - View detailed product information.
    - Add products to the shopping cart.

- **Shopping Cart:**
    - View items in the shopping cart.
    - Remove items from the cart.
    - Calculate total amount of items in the cart.

- **Checkout Process:**
    - Enter billing, shipping, and payment information.
    - **Client-side credit card validation:**
        - Luhn algorithm validation for card number verification
        - Automatic card type detection (Visa, Mastercard, Amex, Discover, Diners Club, JCB)
        - Real-time validation with visual error feedback
        - Expiry date validation (checks for valid month and ensures card hasn't expired)
        - CVC validation (3 digits for most cards, 4 for American Express)
        - Email format validation
    - Simulate the order creation process on the backend.
    - Receive confirmation of order success.

> [!TIP]
> When testing the checkout process, you can use the following test credit card number: `4242 4242 4242 4242` with any future expiry date and any CVC code. This is because we use Luhn algorithm validation for card number verification only, and no actual payment processing is done.

- **User Authentication:**
    - User registration and login.
    - Password hashing for security.
    - Protected routes for authenticated users.
    - JWT-based authentication.
    - Forgot and reset password functionality.
    - User profile management (view and update profile information).
    - Order history (view past orders).

- **Product Recommendations:**
    - Vector-based product recommendations using Pinecone (with optional Weaviate support).
    - Similar products displayed on product detail pages.

- **Search Functionality:**
    - Search products by name, description, brand, or category.
    - Real-time search suggestions.
    - Filter and sort search results.
    - Pagination for search results.
    - Debounced search input to optimize performance.

- **Order Tracking:**
    - View order status and details.
    - Get estimated delivery date and tracking information.

- **Terms of Service & Privacy Policy:**
    - Inform users about terms of service and privacy policy.

- **Support Page:**
    - Provide contact information and support resources.
    - FAQ section.
    - Contact form for user inquiries.

- **Responsive Design:**
    - Mobile-friendly layout.
    - Responsive components for various screen sizes.

## Technologies Used

- **Frontend:**
    - React.js
    - Material-UI for styling
    - Axios for API requests
    - `react-credit-cards-2` for credit card visualization
    - `react-router-dom` for routing
    - `react-hook-form` for form validation
    - `react-toastify` for toast notifications
    - Jest and React Testing Library for testing

- **Backend:**
    - Node.js
    - Express.js
    - MongoDB (with Mongoose ODM)
    - Axios for external API requests
    - JsonWebToken for user authentication
    - Bcrypt for password hashing
    - Dotenv for environment variables
    - Cors for cross-origin resource sharing
    - Swagger for API documentation
    - Nodemon for server hot-reloading
    - **Middleware**: JWT for securing API endpoints
    - **Pinecone** and **Weaviate** for product recommendations with vector databases
    - **FAISS & LangChain** for efficient similarity search
    - Jest for unit and integration testing
    - Supertest for API endpoint testing
    - Cross-env for setting environment variables in scripts

- **Development Tools:**
    - Jetbrains WebStorm (IDE)
    - Postman (for API testing)
    - Git (version control)
    - npm (package manager)
    - Docker (for containerization)
    - GitHub Actions (for CI/CD)
    - Vercel and Render (for deployment)

## Project Structure

The project is organized into two main "stacks": The backend is in the `backend` directory that hosts all product & order data and the frontend is in the `root` directory. Here is an overview of the project structure:

```
fullstack-ecommerce/
├── backend/                       # Node.js server files
│   ├── config/                    # Configuration files
│   │   └── db.js                  # Database connection
│   ├── docs/
│   │   └── swagger.js             # Swagger API documentation setup
│   ├── models/                    # Mongoose models
│   │   ├── user.js                # User schema
│   │   └── product.js             # Product schema
│   ├── routes/                    # Route handlers
│   │   ├── products.js            # Product routes
│   │   ├── search.js              # Search routes
│   │   └── checkout.js            # Checkout routes
│   ├── middleware/                # Middleware functions
│   │   ├── auth.js                # Authentication middleware
│   ├── scripts/                   # Scripts for various tasks
│   │   ├── build-faiss-index.js   # Script to build FAISS index
│   │   ├── search-faiss-index.js  # Script to search FAISS index
│   │   ├── query-weaviate.js      # Script to query Weaviate
│   │   ├── weaviate-upsert.js     # Script to upsert products to Weaviate
│   │   ├── sync-weaviate.js       # Script to synchronize products with Weaviate
│   │   └── sync-pinecone.js       # Script to synchronize products with Pinecone
│   ├── seed/                      # Database seed data
│   │   └── productSeeds.js        # Product seed data
│   ├── services/                  # Shared services (e.g., Pinecone sync helpers)
│   ├── weaviateClient.js          # Weaviate client setup
│   ├── pineconeClient.js          # Pinecone client setup
│   ├── faiss.sh                   # FAISS index setup script
│   ├── .env                       # Environment variables
│   └── index.js                   # Server entry point
├── public/                        # Frontend public assets
│   ├── index.html                 # HTML template
│   ├── manifest.json              # Web app manifest
│   └── favicon.ico                # Favicon
├── src/                           # React.js frontend files
│   ├── components/                # Reusable components
│   │   ├── CheckoutForm.jsx       # Checkout form component
│   │   ├── ProductCard.jsx        # Product card component
│   │   ├── NavigationBar.jsx      # Navigation bar component
│   │   ├── OrderConfirmation.jsx  # Order confirmation component
│   │   ├── ProductListing.jsx     # Product listing component
│   │   ├── SearchResults.jsx      # Search results component
│   │   └── ShoppingCart.jsx       # Shopping cart component
│   ├── dev/                       # Development utilities
│   │   ├── index.js               # Development entry point
│   │   ├── palette.jsx            # Color palette
│   │   ├── preview.jsx            # Component preview
│   │   └── useInitials.js         # Initials hook
│   ├── pages/                     # Page components
│   │   ├── Cart.jsx               # Cart page component
│   │   ├── Checkout.jsx           # Checkout page component
│   │   ├── Home.jsx               # Home page component
│   │   ├── ProductDetails.jsx     # Product details page component
│   │   ├── OrderSuccess.jsx       # Order success page component
│   │   ├── ProductDetails.jsx     # Product details page component
│   │   └── Shop.jsx               # Shop page component
│   ├── App.jsx                    # Main application component
│   ├── App.css                    # Main application styles
│   └── index.js                   # React entry point
├── build/                         # Frontend production build files
├── tests/                         # Test files
├── .gitignore                     # Git ignore file
├── package.json                   # NPM package file
├── jsconfig.json                  # JS config file
└── setupProxy.js                  # Proxy configuration
(... and more files not listed here ...)
```

## Getting Started

### Prerequisites

Before running this project, ensure you have the following installed:

- Node.js (with npm)
- MongoDB (with either local or remote instance)
- Git
