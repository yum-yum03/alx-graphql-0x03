```markdown
# ALX GraphQL - 0x03: Rick and Morty App

This project extends the **Rick and Morty GraphQL application** by adding an **Error Boundary** in TypeScript and integrating **Sentry error monitoring**.

---

## 📌 Objectives
- Implement a reusable **ErrorBoundary** component.
- Wrap the application with ErrorBoundary to handle runtime errors gracefully.
- Create a test component (`ErrorProneComponent`) to simulate errors.
- Integrate **Sentry** for monitoring and logging errors.

---

## 🛠️ Tech Stack
- [Next.js](https://nextjs.org/) (React Framework)
- [TypeScript](https://www.typescriptlang.org/)
- [GraphQL](https://graphql.org/)
- [Sentry](https://sentry.io/) (error monitoring)

---

## 📂 Project Structure
```

alx-rick-and-morty-app/
│── components/
│   ├── ErrorBoundary.tsx
│   ├── ErrorProneComponent.tsx
│
│── pages/
│   ├── \_app.tsx
│   ├── index.tsx
│
│── sentry.client.config.ts
│── sentry.server.config.ts
│── package.json
│── README.md
│── .env.local (not committed)

````

---

## 🚀 Getting Started

### 1️⃣ Clone the repo
```bash
git clone https://github.com/<your-username>/alx-graphql-0x03.git
cd alx-graphql-0x03/alx-rick-and-morty-app
````

### 2️⃣ Install dependencies

```bash
npm install
```

### 3️⃣ Setup environment variables

Create a `.env.local` file in the root:

```env
NEXT_PUBLIC_SENTRY_DSN=https://yourPublicDSNfromSentry
SENTRY_DSN=https://yourServerDSNfromSentry
```

### 4️⃣ Run the app

```bash
npm run dev
```

Then open 👉 [http://localhost:3000](http://localhost:3000)

---

## 🧪 Testing ErrorBoundary

We added a test component:

```tsx
const ErrorProneComponent: React.FC = () => {
  throw new Error("This is a test error!");
};
```

To test:

1. Visit `/` (home page).
2. You should see **"Oops, there is an error!"** message.
3. Check your **Sentry dashboard** for the logged error.

---

## 📊 Error Monitoring (Sentry)

Errors are captured in `ErrorBoundary.tsx` using:

```tsx
Sentry.captureException(error, { extra: errorInfo });
```

You can monitor them in your [Sentry project dashboard](https://sentry.io/).

---

## 📜 License

This project is for **educational purposes** under the **ALX Software Engineering curriculum**.

```
