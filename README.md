# React Custom `useFetch` Hook Demonstration

This project is a hands-on lab demonstrating the creation and implementation of a custom `useFetch` hook in React. It showcases how to build a reusable hook to fetch data from an API, manage state, and handle asynchronous operations efficiently within a React application. The app fetches and displays data from two different public APIs to illustrate the hook's versatility.

## 🚀 Skills Showcased

- **React:** Building a functional, component-based user interface.
- **React Hooks:**
  - `useState`: To manage component state.
  - `useEffect`: To handle side effects, specifically the data fetching operation.
- **Custom Hooks:** Abstracting complex logic into a reusable `useFetch` hook, promoting clean and DRY code.
- **Asynchronous JavaScript:** Using the native `fetch` API and Promises to retrieve data from remote endpoints.
- **Data Rendering:** Dynamically rendering lists of data retrieved from the APIs.
- **Modern JavaScript (ES6+):** Utilizing arrow functions, destructuring, and other modern syntax.
- **Basic CSS:** Applying simple styling for a clean presentation.

## ✨ How It Works

The core of this project is the `useFetch` custom hook.

### `src/Components/UseFetch.jsx`

```javascript
import React, { useEffect, useState } from "react";

const useFetch = (url) => {
  const [data, setData] = useState(null);
  useEffect(() => {
    fetch(url)
      .then((res) => res.json())
      .then((data) => setData(data));
  }, [url]);
  return [data];
};

export default useFetch;
```

This hook takes a `url` as an argument, fetches the data, and returns the data once it's available. The `useEffect` hook ensures that the fetch operation is only performed when the component mounts or the `url` changes.

### Component Implementation

The `useFetch` hook is then consumed by components like `FetchData.jsx` and `FetchYogaData.jsx` to fetch and display their respective data, like so:

```javascript
import React from "react";
import useFetch from "./UseFetch";

const FetchData = () => {
  const [data] = useFetch("https://api.npoint.io/9045c260b1565daa9e15");

  return <>{/* ... rendering logic ... */}</>;
};

export default FetchData;
```

This approach keeps our components clean and focused on rendering UI, while the data fetching logic is neatly encapsulated in the custom hook.

## 🛠️ Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

- Node.js and npm installed on your machine.

### Installation & Usage

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/rafael-a-g-n/custom_hook.git
    ```
2.  **Navigate to the project directory:**
    ```sh
    cd custom_hook
    ```
3.  **Install NPM packages:**
    ```sh
    npm install
    ```
4.  **Run the application:**
    ```sh
    npm run dev
    ```
    Open [http://localhost:5173](http://localhost:5173) (or the port specified in your terminal) to view it in the browser.

## 🙏 Credits

This project was completed as part of a lab exercise and is a fork of the original repository provided by the IBM Developer Skills Network.

**Original Author:** [IBM Developer Skills Network](https://github.com/ibm-developer-skills-network)
**Upstream Repository:** [ibm-developer-skills-network/custom_hook](https://github.com/ibm-developer-skills-network/custom_hook.git)
