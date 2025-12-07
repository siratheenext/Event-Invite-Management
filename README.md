# Admin Event Check-in
![React](https://img.shields.io/badge/Frontend-React-%2361DAFB?logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Build-Vite-%23646CFF?logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Style-TailwindCSS-%2338B2AC?logo=tailwindcss&logoColor=white)
![Node.js](https://img.shields.io/badge/Backend-Node.js-339933?logo=nodedotjs&logoColor=white)
![SQL](https://img.shields.io/badge/Database-SQL-4479A1?logo=mysql&logoColor=white)

Lightweight event check-in web app (frontend + simple Node server) built with Vite, React, and Tailwind CSS. Designed to manage events, scan/record attendee check-ins, and handle a small SQLite/MySQL/Postgres database (see [database/setup.sql](admin-event-checkin/database/setup.sql)).

- Live demo UI entry: [index.html](admin-event-checkin/index.html)  
- Frontend entry: [`src/main.jsx`](admin-event-checkin/src/main.jsx) and [`src/App.jsx`](admin-event-checkin/src/App.jsx)  
- Server entry: [`server/index.js`](admin-event-checkin/server/index.js)  
- Database schema: [database/setup.sql](admin-event-checkin/database/setup.sql)

Features
- Create and edit events (see [`EventForm.jsx`](admin-event-checkin/src/components/EventForm.jsx), [`EditEventForm.jsx`](admin-event-checkin/src/components/EditEventForm.jsx))
- Add attendees and list them (see [`AddAttendeeForm.jsx`](admin-event-checkin/src/components/AddAttendeeForm.jsx), [`AttendeeList.jsx`](admin-event-checkin/src/components/AttendeeList.jsx))
- QR scanner-based check-in (see [`QRScanner.jsx`](admin-event-checkin/src/components/QRScanner.jsx))
- Manual check-in form (see [`CheckInForm.jsx`](admin-event-checkin/src/components/CheckInForm.jsx))
- Event listing components: [`EventList.jsx`](admin-event-checkin/src/components/EventList.jsx) and [`EventList_new.jsx`](admin-event-checkin/src/components/EventList_new.jsx)

Tech stack
- Frontend: React + Vite ([vite.config.js](admin-event-checkin/vite.config.js))  
- Styling: Tailwind CSS ([tailwind.config.js](admin-event-checkin/tailwind.config.js), [postcss.config.js](admin-event-checkin/postcss.config.js))  
- Backend: Node.js Express minimal server ([server/index.js](admin-event-checkin/server/index.js), [server/routes/](admin-event-checkin/server/routes/), [server/config/](admin-event-checkin/server/config/))  
- DB: SQL schema in [database/setup.sql](admin-event-checkin/database/setup.sql)

Prerequisites
- Node.js (v16+ recommended)
- npm or yarn
- A SQL database supported by the server (see [database/setup.sql](admin-event-checkin/database/setup.sql))

Quick start

1. Clone the repo and change into the project folder

```bash
git clone <repo-url>
cd <repo-root>/admin-event-checkin
```

2. Install dependencies

```bash
npm install
# or
yarn
```

3. Configure environment

- Copy or edit the environment template: [.env](admin-event-checkin/.env)  
- Set your database connection and any other server vars in [.env](admin-event-checkin/.env)

4. Initialize database

- Run the SQL schema in [database/setup.sql](admin-event-checkin/database/setup.sql) against your DB.

5. Run the backend server

```bash
node server/index.js
# or if a script is defined in [package.json](admin-event-checkin/package.json):
npm run start
```

6. Run the frontend (Vite dev server)

```bash
npm run dev
# serves the frontend; see [vite.config.js](admin-event-checkin/vite.config.js)
```

Project structure (important files)
- [admin-event-checkin/package.json](admin-event-checkin/package.json) — project scripts & deps  
- [admin-event-checkin/index.html](admin-event-checkin/index.html) — frontend HTML shell  
- [admin-event-checkin/src/main.jsx](admin-event-checkin/src/main.jsx) — app bootstrap  
- [admin-event-checkin/src/App.jsx](admin-event-checkin/src/App.jsx) — top-level React component  
- Components:
  - [`AddAttendeeForm`](admin-event-checkin/src/components/AddAttendeeForm.jsx)
  - [`AttendeeList`](admin-event-checkin/src/components/AttendeeList.jsx)
  - [`CheckInForm`](admin-event-checkin/src/components/CheckInForm.jsx)
  - [`EditEventForm`](admin-event-checkin/src/components/EditEventForm.jsx)
  - [`EventForm`](admin-event-checkin/src/components/EventForm.jsx)
  - [`EventList_new`](admin-event-checkin/src/components/EventList_new.jsx)
  - [`EventList`](admin-event-checkin/src/components/EventList.jsx)
  - [`QRScanner`](admin-event-checkin/src/components/QRScanner.jsx)
- Server:
  - [admin-event-checkin/server/index.js](admin-event-checkin/server/index.js)
  - [admin-event-checkin/server/routes/](admin-event-checkin/server/routes/)
  - [admin-event-checkin/server/config/](admin-event-checkin/server/config/)
- DB schema: [admin-event-checkin/database/setup.sql](admin-event-checkin/database/setup.sql)
- Config: [admin-event-checkin/.env](admin-event-checkin/.env), [admin-event-checkin/vite.config.js](admin-event-checkin/vite.config.js), [admin-event-checkin/tailwind.config.js](admin-event-checkin/tailwind.config.js)

API
- Server routes live in [admin-event-checkin/server/routes/](admin-event-checkin/server/routes/). Inspect those files to see endpoint paths and payload expectations.

Testing
- No dedicated test suite detected in the project root. Add tests and scripts to [admin-event-checkin/package.json](admin-event-checkin/package.json) as needed.

Deployment
- Build frontend with:

```bash
npm run build
# serves static files from dist; see [admin-event-checkin/vite.config.js](admin-event-checkin/vite.config.js)
```

- Host static files on any static host and run the Node server with production environment variables set (see [.env](admin-event-checkin/.env)).

Contributing
- Fork, create a branch, add features or fixes, update docs, open a PR.
- Keep UI components in [admin-event-checkin/src/components/](admin-event-checkin/src/components/).

References
- Project root: [admin-event-checkin/](admin-event-checkin/)  
- Frontend entry: [`src/main.jsx`](admin-event-checkin/src/main.jsx)  
- Backend entry: [`server/index.js`](admin-event-checkin/server/index.js)  
- DB schema: [database/setup.sql](admin-event-checkin/database/setup.sql)

License
- Add your preferred license file to the repo (e.g., LICENSE).

If you want, I can generate a shorter version, add badges, or create a CONTRIBUTING.md and ISSUE_TEMPLATE for this repo.
