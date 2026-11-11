🧾 Bill Book — Interactive Desktop POS Studio

100% Offline Point-of-Sale (POS) & Retail Intelligence Engine

Quick Start •
Features •
Architecture •
UPI QR Specification •
Verification Checklist

📌 Executive Summary

Objective:

Small neighbourhood stores and kirana grocers frequently suffer from intermittent connectivity, forcing shopkeepers into slow manual calculations, mental-math errors, and zero record of daily turnover. Bill Book solves this by delivering a high-speed, 100% offline-first billing studio that runs locally in any desktop or mobile browser. It handles fractional quantities, discounts, and GST taxes, generates dynamic UPI QR codes without external APIs, and maintains an automatic ledger of daily sales.

Methodology:

Designed as a modern, reactive single-page desktop workspace with zero runtime frameworks or remote CDNs:

Column 1 (Billing Engine): Interactive catalog chips, quantity steppers, manual line inputs, discount deductions, and GST calculation.

Column 2 (Current Bill & QR): Dynamic receipt layout (Sharma Stores #104 style), payment method toggling, pure JavaScript QR matrix synthesis, and instant WhatsApp / PNG image exports.

Column 3 (Sales Intelligence): Real-time daily gross turnover tracker (Today: ₹4,860), hourly transaction velocity sparklines, keyword search, and one-click cart duplication.

Expected Outcome:

A dependable POS utility that matches manual arithmetic to the exact paise across 5+ test bills, creates scannable UPI QR codes that open directly in Google Pay, PhonePe, and Paytm, and preserves customer transaction histories in local storage without network access.

📸 Interface Preview
<img width="911" height="435" alt="image" src="https://github.com/user-attachments/assets/0cab000d-06d5-416e-833a-6b4d1ff480bd" />


✨ Key Features

1. ⚡ High-Velocity 3-Column POS Dashboard

Simultaneous Visibility: Never lose context switching between tabs. Build bills, review receipts, and monitor sales metrics side-by-side.

Quick-Add Catalog: Pre-loaded with daily essentials (Rice 2 kg, Oil 1 L, Atta 5 kg, Sugar 1 kg) with customizable items and prices.

Interactive Quantity Steppers: Increment or decrement item quantities (+ / -) on the fly with live total recalculation.

2. 📲 Dynamic Offline UPI QR Code Engine

Zero Remote APIs: Encodes standardized NPCI / UPI deep-link URLs into clean matrix bitmaps using pure client-side mathematics:

Auto-Filled Amount: When scanned by Google Pay, PhonePe, BHIM, or Paytm, the exact bill total is pre-filled automatically—eliminating manual input errors.

3. 📊 Real-Time Retail Intelligence & Sparklines

Top Metric Strip: Live calculations of daily revenue, completed invoices count, average ticket size, and cumulative GST collected.

Hourly Velocity Sparkline: Built-in dynamic visual sparkline showing business traffic peaks throughout the business day.

Search & Ledger Filters: Instant search by Item Name or Invoice ID, plus quick filters (Above ₹500, Last 3).

4. 📤 Instant WhatsApp & Image Sharing

Formatted WhatsApp Text: Generates a clean, emoji-accented itemized bill and dispatches it directly to WhatsApp with a single tap.

Direct PNG Exporter: Uses an offline <canvas> renderer to construct clean image receipts that can be saved, printed, or texted.

Thermal Printer Ready: Clean standard printer stylesheet (@media print) supports receipt printing to 80mm thermal rolls or A4 paper.

5. 🔊 Sensory Audio Feedback

Built with the offline Web Audio API to generate subtle, satisfying cash-register chimes and barcode-beep audio feedback during high-volume checkout (toggleable with one click).

📐 Dynamic Offline UPI QR Engine

Unlike other billing web apps that query third-party image endpoints (api.qrserver.com or Google Charts API), Bill Book embeds a compiled Reed-Solomon QR encoder inside the application:

[ Line Items + Discounts + Taxes ]
               │
               ▼
   Calculated Total (e.g. ₹285.00)
               │
               ▼
   UPI Deep-Link String Builder
   "upi://pay?pa=sharma.stores@upi&pn=Sharma%20Stores&am=285.00&cu=INR&tn=Bill%20104"
               │
               ▼
   Client-Side Matrix Generator (Pure JS)
               │
               ▼
   HTML5 Canvas Renderer (100% Offline / No network calls)


📋 Acceptance Verification Checklist

Requirement

Test Scenario

Expected Result

Status

Calculation Accuracy

Compute 5 distinct bills with fractional quantities, 5% GST, and ₹20 flat discounts.

Item sub-totals, discounts, and tax match manual pencil calculations to the paise.

PASSED

Flight Mode Operation

Disconnect Wi-Fi/Ethernet, enable Flight Mode, and reload the application.

Full application boots instantly; adding items, generating bills, and updating sales works with 0 network calls.

PASSED

Real UPI Scanning

Scan generated QR code using Google Pay or PhonePe on an Android/iOS device.

Payment app launches instantly with merchant name pre-filled and the exact bill amount locked in.

PASSED

Persistent Ledger

Close browser tab, quit browser completely, and reopen index.html.

All historical invoices, daily turnover numbers, and custom catalog items remain fully intact via localStorage.

PASSED

🚀 Quick Start

Run Instantly in Any Browser (Zero Setup)

Clone this repository:

git clone https://github.com/suprithateju/ResumeForgeStudio.git
cd ResumeForgeStudio


Double-click bill_book.html (or index.html).

That's it! It runs immediately in Google Chrome, Microsoft Edge, Firefox, or Safari without installing Node.js, Python, or local servers.

📂 Repository Structure

BillBook-Studio/
├── index.html                   # Complete, self-contained interactive POS application
├── README.md                    # Project documentation & architectural manual
├── project_7_submission_guide.md# Formal academic submission & verification package
└── screenshots/                 # Showcase and rubric verification captures
    ├── 01-three-column-pos.png
    ├── 02-scannable-upi-qr.png
    └── 03-sales-ledger-analytics.png


🛠️ Customization & Settings

Click "Profile & UPI" in the top navigation bar to configure:

Shop Name: Updates all invoice headers and QR payment recipient tags.

UPI ID (VPA): Connect your Google Pay, PhonePe, or bank UPI ID (merchant@okhdfcbank, etc.).

WhatsApp Phone Number: Set default customer care / receipt forwarding number.

Quick Catalog: Add custom items, units, and rates directly from the UI.

📄 License

This project is open-source under the MIT License. Built for small retail shops, kirana merchants, and local businesses everywhere.
