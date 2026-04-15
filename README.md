# User Directory App

User Directory App is a lightweight web app for viewing and organizing user records in a clean, server-rendered interface.

Built with Node.js, Express, MySQL, and Jade templates, it is a good starter project for teams that want a simple full-stack baseline.

## Features

- Server-rendered pages using Express + Jade templates
- MySQL-backed user data layer
- Dedicated user list page at `/users`
- Fast client-side sorting by name, email, and age
- Docker support for quick containerized runs

## Tech Stack

- Node.js
- Express
- MySQL (`mysql` npm package)
- Jade templating engine
- Plain JavaScript and CSS for frontend behavior/styling

## Project Structure

- `app.js` - App entry point and middleware wiring
- `routes/` - Route handlers for `/` and `/users`
- `model/` - User model and SQL bootstrap scripts
- `config/db.js` - MySQL connection setup via environment variables
- `views/` - Jade templates
- `public/` - Static assets (CSS/JS)

## Requirements

- Node.js 14+ (newer LTS versions also work)
- npm
- MySQL server

## Environment Variables

Create a `.env` file in the project root:

```env
DB_HOST=localhost
DB_USER=your_mysql_user
DB_PASS=your_mysql_password
DB_NAME=your_database_name
PORT=5000
```

## Database Setup

Initialize your database with the SQL scripts in `model/`:

1. `model/create-users.sql`
2. `model/insert-users.sql`

Run these with any MySQL client or the MySQL CLI.

## Run Locally

Install dependencies:

```bash
npm install
```

Start the app:

```bash
node app.js
```

Open in your browser:

- Home page: `http://localhost:5000/`
- Users page: `http://localhost:5000/users`

## Run with Docker

Build the image:

```bash
docker build -t user-directory .
```

Run the container:

```bash
docker run -p 8080:8080 --env-file .env user-directory
```

Note: the `Dockerfile` exposes `8080`, while `app.js` defaults to `5000` unless `PORT` is set. Use `PORT=8080` in `.env` for Docker.

## Notes

- The homepage form currently adds users to the UI only (client-side), not to the database.
- Some backend CRUD methods are partial and can be expanded for full create/update/delete behavior.

## License

MIT
