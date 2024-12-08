# GraphQL Products API

A **Node.js GraphQL API** for managing products. This project allows users to perform CRUD operations on a MongoDB database using GraphQL.

## Table of Contents

- [Features](#features)
- [Getting Started](#getting-started)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Project Structure](#project-structure)
- [Dependencies](#dependencies)
- [Contributing](#contributing)
- [License](#license)

## Features

- CRUD functionality for products (Create, Read, Update, Delete).
- GraphQL queries and mutations for managing product data.
- MongoDB integration with Mongoose.
- Built with Apollo Server and GraphQL.

## Getting Started

### Prerequisites

Ensure you have the following installed:

- [Node.js](https://nodejs.org/)
- [MongoDB](https://www.mongodb.com/)

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/solarluiso/graphql-products-api.git
   cd graphql-products-api
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory and add the following environment variables:
   ```bash
   MONGO_URI=your_mongodb_connection_string
   PORT=4000
   ```

## Usage

### Running the Server

Start the server in development mode with hot-reloading:

```bash
npm run dev
```

Or, start the server in production mode:

```bash
npm start
```

The server will run at `http://localhost:4000`.

## API Endpoints

This API uses GraphQL. Use `/graphql` to query and mutate data. Below are some examples:

### Queries

- **Get all products**:

  ```graphql
  query {
    products {
      id
      title
      category
      price
      inStock
    }
  }
  ```

- **Get a single product by ID**:
  ```graphql
  query {
    product(id: "1") {
      title
      category
      price
    }
  }
  ```

### Mutations

- **Create a product**:

  ```graphql
  mutation {
    createProduct(
      title: "Laptop"
      category: "Electronics"
      price: 999.99
      inStock: true
    ) {
      id
      title
    }
  }
  ```

- **Update a product**:

  ```graphql
  mutation {
    updateProduct(id: "1", price: 799.99) {
      id
      title
      price
    }
  }
  ```

- **Delete a product**:
  ```graphql
  mutation {
    deleteProduct(id: "1")
  }
  ```

## Project Structure

- `src/models`: Contains the Mongoose schemas.
- `src/resolvers`: Includes GraphQL resolvers for handling queries and mutations.
- `src/schema`: Defines the GraphQL schema.
- `src/server.js`: Entry point for the application.

## Dependencies

- **[@apollo/server](https://www.npmjs.com/package/@apollo/server)**
- **[dotenv](https://www.npmjs.com/package/dotenv)**
- **[graphql](https://www.npmjs.com/package/graphql)**
- **[graphql-tag](https://www.npmjs.com/package/graphql-tag)**
- **[mongoose](https://www.npmjs.com/package/mongoose)**

## Contributing

Contributions are welcome! Feel free to submit a pull request or open an issue.

## License

This project is licensed under the ISC License.
