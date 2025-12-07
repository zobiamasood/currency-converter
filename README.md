✔️

📌 Currency Converter — README

A simple and responsive Currency Converter built using HTML, CSS, JavaScript, and the Fetch API. It retrieves real-time exchange rates from a public currency API.

🔗 Live Demo

You can use the app here:
👉 https://currency-converter-19f357.netlify.app/

🚀 Features

. Convert any currency to another in real time

. Clean and modern UI

. Live exchange rates from a public API

. Automatic country flag update when selecting currencies

. Handles decimals and invalid input smoothly

🛠️ Tech Stack

. HTML — Structure

. CSS — Styling

. JavaScript (Fetch API) — Logic & API integration

. Public API: fawazahmed0/currency-api (via jsDelivr CDN)

📂 Project Structure
currency-converter/
│── index.html
│── style.css
│── apps.js
└── README.md

📘 How to Use the App

1. Enter the amount you want to convert (e.g., 1, 10, 100).

2. Choose the From Currency (USD, PKR, INR, etc.).

3. Choose the To Currency you want to convert into.

4. Click the Convert button.

5. The converted amount will appear instantly on the screen.

🌍 Automatic Flag Change

. When you select a different currency, its country flag updates automatically.

. Example:

. USD → USA flag

. PKR → Pakistan flag

. EUR → European Union flag

. This makes the UI more interactive and visually clear.

🔗 API Usage Example
const BASE_URL = "https://cdn.jsdelivr.net/gh/fawazahmed0/currency-api@1/latest/currencies";

async function convert(from, to, amount) {
  const response = await fetch(`${BASE_URL}/${from}/${to}.json`);

  if (!response.ok) throw new Error("API request failed");

  const data = await response.json();
  const rate = data[to];
  const result = (amount * rate).toFixed(2);

  return { rate, result };
}

🧾 Example HTML Structure
<form id="convertForm">
  <input type="number" id="amount" value="1" min="0" step="any" />
  
  <select id="from"></select>
  <select id="to"></select>

  <button type="submit">Convert</button>
</form>

<div id="output"></div>

📬 Contact

If you have any questions or want improvements, feel free to ask!
