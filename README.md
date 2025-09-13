# 🤖 AI-Powered Personal Finance Optimizer

A full-stack web application that helps users analyze their spending patterns, detect subscriptions and anomalies, and generate optimized monthly spending plans with concrete savings recommendations.

## 🚀 Quick Start

### Prerequisites
- Python 3.10+
- Node.js 18+
- npm

### Running the Application

1. **Start the Demo API (Backend)**
```bash
   # From the project root
   python demo_api.py
```
   The API will be available at: http://localhost:8000

2. **Start the Frontend**
```bash
   # From the project root
   cd frontend
   npm run dev
   ```
   The frontend will be available at: http://localhost:3000

## 🔑 Demo Credentials

- **Email:** demo@fin.com
- **Password:** finpass
- **API Token:** demo_token_123

## 📊 Features

### 🔍 **Transaction Analysis**
- Upload CSV/Excel transaction files
- Automatic categorization using AI
- Spending pattern analysis
- Currency handling (INR)

### 📈 **Subscription Detection**
- Identifies recurring payments
- Analyzes periodicity patterns
- Confidence scoring for each subscription
- Examples: Netflix, Spotify, Gym memberships

### ⚠️ **Anomaly Detection**
- Robust z-score analysis
- Flags unusual spending patterns
- Provides explanations for anomalies
- Helps identify potential fraud or errors

### 💡 **Smart Budget Optimization**
- AI-powered spending plan generation
- Knapsack algorithm for optimal savings
- Pain score assessment for each action
- What-if analysis with interactive sliders

### 📱 **Modern UI/UX**
- Dark theme with glassmorphism design
- Responsive dashboard with charts
- Interactive data visualization
- Real-time plan updates

## 🏗️ Architecture

### Backend (FastAPI)
- **Framework:** FastAPI with Python 3.10
- **Database:** SQLite (development) / PostgreSQL (production)
- **Authentication:** JWT with Argon2 password hashing
- **Algorithms:** 
  - TF-IDF for category classification
  - Autocorrelation for subscription detection
  - Robust z-score for anomaly detection
  - Knapsack optimization for budget planning

### Frontend (React + TypeScript)
- **Framework:** React 18 with TypeScript
- **Build Tool:** Vite
- **Styling:** Tailwind CSS
- **Charts:** Recharts
- **State Management:** Jotai
- **HTTP Client:** Axios

## 📋 API Endpoints

### Authentication
- `POST /auth/login` - User login
- `POST /auth/register` - User registration

### Finance Analysis
- `GET /finance/insights` - Get spending insights and KPIs
- `GET /finance/subscriptions` - Get detected subscriptions
- `GET /finance/anomalies` - Get detected anomalies
- `POST /finance/plan` - Generate optimized spending plan
- `POST /finance/whatif` - What-if analysis
- `POST /finance/upload` - Upload transaction files
- `POST /finance/seed` - Seed demo data

## 🎯 How to Use

### 1. **Login/Register**
- Use demo credentials or create a new account
- JWT token is automatically stored and used for API calls

### 2. **Upload Transactions**
- Upload CSV files with columns: date, amount, currency, merchant, description
- System automatically categorizes and analyzes transactions

### 3. **View Dashboard**
- **KPIs:** Total spend, subscriptions count, anomalies, projected savings
- **Charts:** Spending trends, category breakdown, subscription analysis
- **Tables:** Detailed subscription and anomaly information

### 4. **Generate Savings Plan**
- Set your monthly savings goal
- System generates optimized plan with specific actions
- Each action includes:
  - Type (cancel, switch, cap)
  - Target merchant/category
  - Monthly savings amount
  - Pain score (0-1)
  - Detailed description

### 5. **What-If Analysis**
- Adjust savings goals with interactive sliders
- See real-time plan updates
- Compare different scenarios

## 🔬 Technical Highlights

### Data Science & Algorithms
- **Category Classification:** Rule-based + TF-IDF baseline
- **Subscription Detection:** Periodicity analysis via autocorrelation
- **Anomaly Detection:** Robust z-score with rolling median + MAD
- **Budget Optimization:** 0/1 knapsack-style heuristic with pain scoring

### Security Features
- Argon2 password hashing
- JWT token authentication
- CORS protection
- Input validation with Pydantic

### Performance Optimizations
- Mock data for development
- Efficient database queries
- Caching strategies
- Responsive UI with skeleton loaders

## 🧪 Testing

### API Testing
```bash
# Test health endpoint
curl http://localhost:8000/health

# Test login
curl -X POST http://localhost:8000/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"demo@fin.com","password":"finpass"}'

# Test insights (with token)
curl -X GET http://localhost:8000/finance/insights \
  -H "Authorization: Bearer demo_token_123"
```

### Frontend Testing
- Open http://localhost:3000 in your browser
- Login with demo credentials
- Navigate through all features
- Test responsive design on different screen sizes

## 📁 Project Structure

```
finance/
├── backend/
│   ├── app/
│   │   ├── auth/           # Authentication
│   │   ├── finance/        # Core finance logic
│   │   ├── db/            # Database setup
│   │   └── main.py        # FastAPI app
│   ├── requirements.txt
│   └── .env
├── frontend/
│   ├── src/
│   │   ├── components/    # React components
│   │   ├── pages/         # Page components
│   │   ├── lib/           # Utilities and API
│   │   └── App.tsx        # Main app
│   └── package.json
├── demo_api.py            # Demo API server
└── README.md
```

## 🚀 Deployment

### Production Setup
1. Use PostgreSQL instead of SQLite
2. Set up MongoDB for unstructured data
3. Configure environment variables
4. Use Docker Compose for containerization
5. Set up reverse proxy (nginx)
6. Configure SSL certificates

### Environment Variables
```bash
ENV=production
JWT_SECRET=your-secret-key
POSTGRES_HOST=your-db-host
MONGO_URI=your-mongo-uri
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License.

## 🆘 Support

For issues and questions:
1. Check the API documentation at http://localhost:8000/docs
2. Review the console logs for errors
3. Test individual endpoints with curl
4. Check browser developer tools for frontend issues

---

**🎉 Enjoy optimizing your finances with AI!**
