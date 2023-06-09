**Tailwind CSS Workshop**

# 01. Getting Started

## 01. Installation

- **Install Tailwind CSS with Vite**

  - 1. Create your project

    - Start by creating a new Vite project if you don’t have one set up already. The most common approach is to use [Create Vite](https://vitejs.dev/guide/#scaffolding-your-first-vite-project).

      - See create-vite for more details on each supported template: `vanilla`, `vanilla-ts`, `vue`, `vue-ts`, `react`, `react-ts`, `react-swc`, `react-swc-ts`, `preact`, `preact-ts`, `lit`, `lit-ts`, `svelte`, `svelte-ts`.

    - pnpm

      ```
      pnpm create vite {project-name} --template {template-name}
      ```

      ```
      cd {project-name}
      pnpm install
      pnpm run dev
      ```

  - 2. Install Tailwind CSS

    - Install `tailwindcss` and its peer dependencies, then generate your `tailwind.config.js` and `postcss.config.js` files.

      ```
      pnpm add -D tailwindcss postcss autoprefixer
      pnpm dlx tailwindcss init -p
      ```

  - 3. Configure your template paths

    - Add the paths to all of your template files in your `tailwind.config.js` file.

      - tailwind.config.js

        ```js
        /** @type {import('tailwindcss').Config} */
        export default {
          content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
          theme: {
            extend: {},
          },
          plugins: [],
        };
        ```

  - 4. Add the Tailwind directives to your CSS

    - Add the `@tailwind` directives for each of Tailwind’s layers to your `./src/index.css` file.

    ```css
    @tailwind base;
    @tailwind components;
    @tailwind utilities;
    ```

  - 5. Start your build process

    - Run your build process with `pnpm dev`.

  - 6. Start using Tailwind in your project

    - Start using Tailwind’s utility classes to style your content.

## 02. Editor Setup

- IntelliSense for VS Code

- Automatic class sorting with Prettier

  - We maintain an official [Prettier plugin](https://github.com/tailwindlabs/prettier-plugin-tailwindcss) for Tailwind CSS that automatically sorts your classes following our recommended class order.

    - Installation

      ```
      npm install -D prettier prettier-plugin-tailwindcss
      ```

      - .prettierrc.json

        ```json
        {
          "pluginSearchDirs": ["./node_modules"],
          "plugins": ["prettier-plugin-tailwindcss"]
        }
        ```

# 02. Core Concepts

## 01. Responsive Design

| Breakpoint prefix | Minimum width | CSS                                  |
| ----------------- | ------------- | ------------------------------------ |
| `sm`              | 640px         | `@media (min-width: 640px) { ... }`  |
| `md`              | 768px         | `@media (min-width: 768px) { ... }`  |
| `lg`              | 1024px        | `@media (min-width: 1024px) { ... }` |
| `xl`              | 1280px        | `@media (min-width: 1280px) { ... }` |
| `2xl`             | 1536px        | `@media (min-width: 1536px) { ... }` |
