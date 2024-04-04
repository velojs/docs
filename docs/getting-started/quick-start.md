---
description: This guide will help you go from nothing to something with Velo in a few minutes.
---

# Quick Start

Velo is designed to be simple and easy to use, yet powerful and extensible. Velo can be set up with
just a 1 command, and you can start building your web application in seconds.

Before you begin, ensure you have the latest version of [Bun](https://bun.sh) installed on your
machine.

```bash
curl https://bun.sh/install | bash
```

## Automatic Setup

To create a new Velo project, run the following command:

```bash
bun create velo my-app
```

This will create a new Velo project in the `my-app` directory, and will set up everything for you.

Once this is done, navigate to the project directory:

```bash
cd my-app
```

And start the development server:

```bash
bun dev
```

This will start the development server on `http://localhost:3000`. Open this URL in your browser to
see your new Velo project.

## Manual Setup

If you prefer to set up your project manually, you can do so by following these steps:

1. Create a new project:

```bash
mkdir my-app && cd my-app
bun init
```

2. Add Velo to your project:

```bash
bun add velo
```

3. Open your `project.json` file and add these scripts:

    ```json
    {
        "scripts": {
            "dev": "bun --watch src/index.ts",
            "start": "NODE_ENV=production bun src/index.ts"
        }
    }
    ```

4. Setup your `src/index.ts` file:

    ```typescript
    import { Velo } from "velo";

    const app = new Velo();

    app.get("/", () => "Welcome to Velo!");

    app.listen(3000);
    ```

5. Start the development server:

    ```bash
    bun dev
    ```

This will start the development server on `http://localhost:3000`. Open this URL in your browser to
see your new Velo project.

## Project Structure

You can set up your project structure however you like, but we recommend the following:

```
app/
├── src/
│   └── index.ts <- The entry point of your app
│   └── lib/
│   └── routes/
│   └── types/
├── tests/
...
```
