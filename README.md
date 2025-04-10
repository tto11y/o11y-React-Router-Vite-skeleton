# O11y's Handbook

this repo contains a skeleton React router project that leverages Vite

below you find details on ...
- how to set up your local environment (on macOS) to run this application
- how to build and run the application
- how the application is structured

---

## Setup

on macOS
### Install nvm
```shell
  brew install nvm
```
- see https://formulae.brew.sh/formula/nvm#default
- check successful installation with `nvm current`

```console
foo@bar:~$ nvm current
v22.14.0
```   


### Install and setup NodeJS
```shell
  nvm install 22
```
- installs NodeJS v22.14.0 (LTS)
- the output should look like the following:

```console
foo@bar:~$ nvm install 22
Downloading and installing node v22.14.0...
Downloading https://nodejs.org/dist/v22.14.0/node-v22.14.0-darwin-arm64.tar.xz...
############################################################################# 100.0%
Computing checksum with sha256sum
Checksums matched!
Now using node v22.14.0 (npm v10.9.2)
```

#### Set default NodeJS version

```shell
  nvm alias default 22
```

```console
foo@bar:~$ nvm alias default 22
default -> 22 (-> v22.14.0)
```

### Install the project dependencies

```shell
  npm install
```

---

## Project structure

### Components

Components are located in [/components](apps/o11y-self-service-frontend/src/components)

To keep a clean file structure, we follow the following guidelines for components:
1. for each component create a dedicated folder
2. put each of the following in a separate file
    - the component, (*.tsx)
    - its corresponding styles, (*.styles.tsx)
    - and tests (*.test.tsx)
3. child components should reside under the folder of their parent component

NOTE: Some components might not need custom styles or tests. In this case you can omit the respective file.

```text
e.g.

/components
  ├── Card/
  │    ├── Card.tsx
  │    ├── Card.styles.tsx
  │    ├── Card.test.tsx
  │    ├── CardHeader/
  │    │    ├── CardHeader.tsx
  │    │    ├── CardHeader.styles.tsx
  │    │    ├── CardHeader.test.tsx
  ├── Footer/
  │    ├── Footer.tsx
  │    ├── Footer.styles.tsx
  │    ├── Footer.test.tsx
  │    ├── Links/
  │    │    ├── Links.tsx
  │    │    ├── Links.styles.tsx
  │    │    ├── Links.test.tsx
```

### Custom hooks

Custom hooks are located in [/hooks](apps/o11y-self-service-frontend/src/hooks)

To keep a clean file structure, we follow the following guidelines for custom hooks:
1. put each custom hook in a separate file
2. group custom hooks in folders, if they are related by domain

```text
e,g,
/hooks
  ├── user/
  │    ├── useUserData.ts
  │    ├── useUserPermissions.ts
  ├── useFetchData.ts
  ├── useThemeToggle.ts
```


---

# Welcome to React Router!

A modern, production-ready template for building full-stack React applications using React Router.

[![Open in StackBlitz](https://developer.stackblitz.com/img/open_in_stackblitz.svg)](https://stackblitz.com/github/remix-run/react-router-templates/tree/main/default)

## Features

- 🚀 Server-side rendering
- ⚡️ Hot Module Replacement (HMR)
- 📦 Asset bundling and optimization
- 🔄 Data loading and mutations
- 🔒 TypeScript by default
- 🎉 TailwindCSS for styling
- 📖 [React Router docs](https://reactrouter.com/)

## Getting Started

### Installation

Install the dependencies:

```bash
npm install
```

### Development

Start the development server with HMR:

```bash
npm run dev
```

Your application will be available at `http://localhost:5173`.

## Building for Production

Create a production build:

```bash
npm run build
```

## Deployment

### Docker Deployment

To build and run using Docker:

```bash
docker build -t my-app .

# Run the container
docker run -p 3000:3000 my-app
```

The containerized application can be deployed to any platform that supports Docker, including:

- AWS ECS
- Google Cloud Run
- Azure Container Apps
- Digital Ocean App Platform
- Fly.io
- Railway

### DIY Deployment

If you're familiar with deploying Node applications, the built-in app server is production-ready.

Make sure to deploy the output of `npm run build`

```
├── package.json
├── package-lock.json (or pnpm-lock.yaml, or bun.lockb)
├── build/
│   ├── client/    # Static assets
│   └── server/    # Server-side code
```

## Styling

This template comes with [Tailwind CSS](https://tailwindcss.com/) already configured for a simple default starting experience. You can use whatever CSS framework you prefer.

---

Built with ❤️ using React Router.
