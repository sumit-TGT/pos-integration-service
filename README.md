# 📦 POS Integration Service

**Purpose:**  
Connects and receives data from various POS systems (e.g., Shopify, Oracle, Zoho POS) and forwards it to the ingestion service.

---

## 🛠 Tech Stack

- **Backend:** Node.js, Express.js  
- **Integrations:** Shopify, Zoho POS (extensible)  
- **Communication:** REST APIs, Webhooks  

---

## ✨ Key Features

- ✅ **POS-specific Adapters**  
  Modular support for Shopify, Zoho, Oracle, etc.

- 🔄 **Plugin Install Callbacks**  
  Securely handles authorization and plugin install flows.

- 📤 **Data Forwarding**  
  Automatically sends data (orders, products, etc.) to the ingestion service.

---

## 📁 Project Structure

pos-integration-service/
├── adapters/ # POS-specific logic
│ ├── shopifyAdapter.js
│ └── zohoAdapter.js
├── routes/ # Express routes
│ ├── shopifyRoutes.js
│ └── zohoRoutes.js
├── services/ # Business logic
│ └── dataForwarder.js
├── .env # Environment variables
├── package.json # NPM config
├── server.js # Entry point
└── README.md


---

## 🚀 Setup Instructions

### 1. Clone or Download the Project

```bash
git clone https://github.com/sumit-TGT/pos-integration-service.git
cd pos-integration-service

🪜 Step-by-Step Guide
1️⃣ Clone या Create Project Folder

```bash
mkdir pos-integration-service
cd pos-integration-service

2. Install Dependencies

npm install


3. Configure Environment
Create a .env file:
PORT=3000
INGESTION_SERVICE_URL=http://localhost:4000/ingest

4. Start the Server

npm start

📡 Webhook Example (Shopify)
```http

POST /webhook/shopify/order
Content-Type: application/json

{
  "id": "4321",
  "email": "customer@example.com",
  "line_items": [...]
}

🔌 Plugin Install Flow
1. Handles app installation (e.g., Shopify OAuth)

2. Stores access tokens (optional future feature)

🧩 Adding New POS Adapters
1. Add a new adapter in adapters/.

2. Add a new route in routes/.

3. Forward data to the ingestion service using dataForwarder.js.

🧪 Testing Webhooks with Postman
Shopify: POST http://localhost:3000/webhook/shopify/order

Zoho: POST http://localhost:3000/webhook/zoho/order

    *Use raw JSON body matching the adapter’s structure.

👤 Author
**Sumit Kumar**
 TeraGridTech



