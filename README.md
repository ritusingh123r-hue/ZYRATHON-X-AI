y for ZYRATHON-X
Copilot Chat
Create a GitHub repository for ZYRATHON-X
You said: ``` 📁 Folder Structure zyrathron-x-ai/ ├── frontend/
📁 Folder Structure
zyrathron-x-ai/
├── frontend/                  # Next.js 14 App
│   ├── public/
│   │   ├── images/
│   │   └── icons/
│   ├── src/
│   │   ├── app/
│   │   │   ├── (auth)/
│   │   │   │   ├── login/page.tsx
│   │   │   │   ├── signup/page.tsx
│   │   │   │   └── forgot-password/page.tsx
│   │   │   ├── (dashboard)/
│   │   │   │   ├── layout.tsx
│   │   │   │   ├── page.tsx              # Dashboard main
│   │   │   │   ├── workout/page.tsx
│   │   │   │   ├── nutrition/page.tsx
│   │   │   │   ├── ai-chat/page.tsx
│   │   │   │   ├── subscription/page.tsx
│   │   │   │   └── settings/page.tsx
│   │   │   ├── admin/
│   │   │   │   ├── layout.tsx
│   │   │   │   └── page.tsx
│   │   │   ├── layout.tsx                # Root layout with providers
│   │   │   ├── page.tsx                  # Landing page
│   │   │   ├── globals.css
│   │   │   └── providers.tsx
│   │   ├── components/
│   │   │   ├── ui/                       # Shadcn components (button, card, etc.)
│   │   │   ├── layout/
│   │   │   │   ├── Navbar.tsx
│   │   │   │   ├── Sidebar.tsx
│   │   │   │   ├── Footer.tsx
│   │   │   │   └── DashboardShell.tsx
│   │   │   ├── landing/
│   │   │   │   ├── HeroSection.tsx
│   │   │   │   ├── FeaturesSection.tsx
│   │   │   │   ├── PricingSection.tsx
│   │   │   │   ├── Testimonials.tsx
│   │   │   │   └── CTASection.tsx
│   │   │   ├── dashboard/
│   │   │   │   ├── StatsCard.tsx
│   │   │   │   ├── ProgressRing.tsx
│   │   │   │   ├── WorkoutCard.tsx
│   │   │   │   ├── NutritionCard.tsx
│   │   │   │   └── ActivityChart.tsx
│   │   │   ├── auth/
│   │   │   │   ├── LoginForm.tsx
│   │   │   │   ├── SignupForm.tsx
│   │   │   │   └── ForgotPasswordForm.tsx
│   │   │   ├── ai/
│   │   │   │   ├── ChatWindow.tsx
│   │   │   │   └── MessageBubble.tsx
│   │   │   └── subscription/
│   │   │       ├── PlanCard.tsx
│   │   │       └── CheckoutButton.tsx
│   │   ├── hooks/
│   │   │   ├── useAuth.ts
│   │   │   ├── useSubscription.ts
│   │   │   └── useOpenAI.ts
│   │   ├── lib/
│   │   │   ├── api.ts                    # Axios instance
│   │   │   ├── stripe.ts                 # Stripe client helpers
│   │   │   └── utils.ts
│   │   ├── store/                        # Zustand or context (optional)
│   │   │   └── authStore.ts
│   │   └── types/
│   │       └── index.ts
│   ├── .env.local
│   ├── next.config.js
│   ├── tailwind.config.ts
│   ├── components.json                   # Shadcn config
│   └── package.json
│
├── backend/
│   ├── src/
│   │   ├── config/
│   │   │   ├── db.ts                     # MongoDB connection
│   │   │   ├── stripe.ts
│   │   │   └── razorpay.ts
│   │   ├── models/
│   │   │   ├── User.js
│   │   │   ├── Workout.js
│   │   │   ├── DietPlan.js
│   │   │   ├── Subscription.js
│   │   │   ├── Payment.js
│   │   │   ├── Progress.js
│   │   │   └── ChatHistory.js
│   │   ├── routes/
│   │   │   ├── auth.js
│   │   │   ├── users.js
│   │   │   ├── workouts.js
│   │   │   ├── nutrition.js
│   │   │   ├── subscriptions.js
│   │   │   ├── payments.js
│   │   │   ├── ai.js
│   │   │   └── admin.js
│   │   ├── controllers/
│   │   │   ├── authController.js
│   │   │   ├── userController.js
│   │   │   ├── workoutController.js
│   │   │   ├── nutritionController.js
│   │   │   ├── subscriptionController.js
│   │   │   ├── paymentController.js
│   │   │   ├── aiController.js
│   │   │   └── adminController.js
│   │   ├── middleware/
│   │   │   ├── auth.js                   # JWT verify
│   │   │   ├── admin.js                  # Admin check
│   │   │   └── error.js
│   │   ├── utils/
│   │   │   ├── generateToken.js
│   │   │   └── openai.js                 # OpenAI client
│   │   └── server.js                     # Express entry
│   ├── .env
│   ├── package.json
│   └── vercel.json                       # Optional for deployment
│
├── .gitignore
├── README.md
└── docker-compose.yml                    # Optional
🚀 Setup Instructions
1️⃣ Prerequisites
Node.js 18+, MongoDB Atlas (or local), Stripe & Razorpay accounts, Google OAuth credentials, OpenAI API key.
2️⃣ Backend Setup
cd backend
npm init -y
npm install express mongoose cors dotenv jsonwebtoken bcryptjs stripe razorpay openai google-auth-library
npm install -D nodemon
Create .env file:

PORT=5000
MONGO_URI=your_mongodb_uri
JWT_SECRET=your_jwt_secret
GOOGLE_CLIENT_ID=your_google_client_id
STRIPE_SECRET_KEY=sk_test_...
RAZORPAY_KEY_ID=rzp_test_...
RAZORPAY_KEY_SECRET=...
OPENAI_API_KEY=sk-...
CLIENT_URL=http://localhost:3000
3️⃣ Frontend Setup
cd frontend
npx create-next-app@latest . --typescript --tailwind --app
npm install framer-motion @radix-ui/react-dialog @radix-ui/react-dropdown-menu @radix-ui/react-slot
npm install lucide-react class-variance-authority clsx tailwind-merge
npm install axios react-hook-form zustand @stripe/react-stripe-js @stripe/stripe-js
npx shadcn-ui@latest init
Add to .env.local:

NEXT_PUBLIC_API_URL=http://localhost:5000/api
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=pk_test_...
NEXT_PUBLIC_RAZORPAY_KEY_ID=rzp_test_...
🔐 Core Files (Real Code)
1️⃣ Backend: src/server.js
const express = require('express');
const cors = require('cors');
const dotenv = require('dotenv');
const connectDB = require('./config/db');

dotenv.config();
connectDB();

const app = express();
app.use(cors({ origin: process.env.CLIENT_URL, credentials: true }));
app.use(express.json());

// Routes
app.use('/api/auth', require('./routes/auth'));
app.use('/api/users', require('./routes/users'));
app.use('/api/workouts', require('./routes/workouts'));
app.use('/api/nutrition', require('./routes/nutrition'));
app.use('/api/subscriptions', require('./routes/subscriptions'));
app.use('/api/payments', require('./routes/payments'));
app.use('/api/ai', require('./routes/ai'));
app.use('/api/admin', require('./routes/admin'));

// Error middleware
app.use(require('./middleware/error'));

const PORT = process.env.PORT || 5000;
app.listen(PORT, () => console.log(`🚀 ZYRATHON-X AI backend running on port ${PORT}`));
2️⃣ Backend: src/models/User.js
const mongoose = require('mongoose');
const bcrypt = require('bcryptjs');

const userSchema = new mongoose.Schema({
  name: { type: String, required: true },
  email: { type: String, required: true, unique: true },
  password: { type: String, required: function() { return !this.googleId; } },
  googleId: { type: String },
  avatar: { type: String },
  role: { type: String, enum: ['user', 'admin'], default: 'user' },
  subscription: { type: mongoose.Schema.Types.ObjectId, ref: 'Subscription' },
  fitnessGoal: { type: String, enum: ['lose_weight', 'build_muscle', 'maintain', 'endurance'] },
  createdAt: { type: Date, default: Date.now }
});

userSchema.pre('save', async function(next) {
  if (!this.isModified('password') || !this.password) return next();
  this.password = await bcrypt.hash(this.password, 12);
  next();
});

userSchema.methods.matchPassword = async function(enteredPassword) {
  return await bcrypt.compare(enteredPassword, this.password);
};

module.exports = mongoose.model('User', userSchema);
3️⃣ Backend: src/middleware/auth.js
const jwt = require('jsonwebtoken');
const User = require('../models/User');

const protect = async (req, res, next) => {
  let token;
  if (req.headers.authorization?.startsWith('Bearer')) {
    token = req.headers.authorization.split(' ')[1];
  }
  if (!token) return res.status(401).json({ message: 'Not authorized' });

  try {
    const decoded = jwt.verify(token, process.env.JWT_SECRET);
    req.user = await User.findById(decoded.id).select('-password');
    next();
  } catch (error) {
    res.status(401).json({ message: 'Token invalid' });
  }
};

const admin = (req, res, next) => {
  if (req.user && req.user.role === 'admin') next();
  else res.status(403).json({ message: 'Admin only' });
};

module.exports = { protect, admin };
4️⃣ Backend: src/routes/auth.js
const router = require('express').Router();
const { login, signup, googleAuth, forgotPassword } = require('../controllers/authController');

router.post('/signup', signup);
router.post('/login', login);
router.post('/google', googleAuth);
router.post('/forgot-password', forgotPassword);

module.exports = router;
5️⃣ Backend: src/controllers/authController.js (excerpt)
const User = require('../models/User');
const jwt = require('jsonwebtoken');
const { OAuth2Client } = require('google-auth-library');
const client = new OAuth2Client(process.env.GOOGLE_CLIENT_ID);

const generateToken = (id) => jwt.sign({ id }, process.env.JWT_SECRET, { expiresIn: '30d' });

exports.signup = async (req, res) => {
  const { name, email, password } = req.body;
  const userExists = await User.findOne({ email });
  if (userExists) return res.status(400).json({ message: 'User already exists' });

  const user = await User.create({ name, email, password });
  res.status(201).json({
    _id: user._id,
    name: user.name,
    email: user.email,
    token: generateToken(user._id)
  });
};

exports.login = async (req, res) => {
  const { email, password } = req.body;
  const user = await User.findOne({ email });
  if (user && (await user.matchPassword(password))) {
    res.json({
      _id: user._id,
      name: user.name,
      email: user.email,
      avatar: user.avatar,
      token: generateToken(user._id)
    });
  } else {
    res.status(401).json({ message: 'Invalid email or password' });
  }
};

exports.googleAuth = async (req, res) => {
  const { tokenId } = req.body;
  const ticket = await client.verifyIdToken({ idToken: tokenId, audience: process.env.GOOGLE_CLIENT_ID });
  const { name, email, picture } = ticket.getPayload();
  let user = await User.findOne({ email });
  if (!user) {
    user = await User.create({ name, email, googleId: email, avatar: picture });
  }
  res.json({ _id: user._id, name: user.name, email: user.email, avatar: user.avatar, token: generateToken(user._id) });
};
6️⃣ Backend: src/controllers/aiController.js (OpenAI integration)
const { Configuration, OpenAIApi } = require('openai');
const configuration = new Configuration({ apiKey: process.env.OPENAI_API_KEY });
const openai = new OpenAIApi(configuration);
const ChatHistory = require('../models/ChatHistory');

exports.chat = async (req, res) => {
  try {
    const { message } = req.body;
    const userId = req.user._id;

    // Fetch previous context
    const history = await ChatHistory.find({ user: userId }).sort({ createdAt: -1 }).limit(10);
    const context = history.reverse().map(h => ({ role: 'user', content: h.message }));

    const completion = await openai.createChatCompletion({
      model: 'gpt-4',
      messages: [
        { role: 'system', content: 'You are Zyrath, an elite AI fitness coach. Provide concise, motivating, science-based advice. Include exercises, meal tips, and progress tracking.' },
        ...context,
        { role: 'user', content: message }
      ],
      max_tokens: 500
    });

    const reply = completion.data.choices[0].message.content;

    // Save to history
    await ChatHistory.create({ user: userId, message, reply });

    res.json({ reply });
  } catch (error) {
    console.error(error);
    res.status(500).json({ message: 'AI service error' });
  }
};
7️⃣ Frontend: src/app/globals.css (cyberpunk theme)
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  :root {
    --background: 0 0% 0%;
    --foreground: 0 0% 100%;
    --card: 0 0% 3%;
    --card-foreground: 0 0% 100%;
    --primary: 217 91% 60%;      /* Neon blue */
    --primary-foreground: 0 0% 100%;
    --secondary: 271 81% 56%;    /* Neon purple */
    --secondary-foreground: 0 0% 100%;
    --muted: 0 0% 15%;
    --muted-foreground: 0 0% 65%;
    --accent: 217 91% 60%;
    --accent-foreground: 0 0% 100%;
    --destructive: 0 84% 60%;
    --border: 0 0% 20%;
    --input: 0 0% 20%;
    --ring: 217 91% 60%;
    --radius: 0.75rem;
  }
}

.glass {
  background: rgba(0, 0, 0, 0.6);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.neon-glow {
  box-shadow: 0 0 15px theme('colors.primary.DEFAULT'), 0 0 30px theme('colors.secondary.DEFAULT');
}
8️⃣ Frontend: tailwind.config.ts
import type { Config } from 'tailwindcss'

const config: Config = {
  darkMode: 'class', // always dark
  content: ['./src/**/*.{ts,tsx}'],
  theme: {
    extend: {
      colors: {
        primary: {
          DEFAULT: '#4A90FF',
          dark: '#1E5AFF',
        },
        secondary: {
          DEFAULT: '#9B59B6',
          dark: '#7D3C98',
        },
        background: '#000000',
        card: '#0A0A0A',
        border: '#1F1F1F',
      },
      fontFamily: {
        sans: ['Inter', 'sans-serif'],
        mono: ['JetBrains Mono', 'monospace'],
      },
      animation: {
        'pulse-glow': 'pulse-glow 2s ease-in-out infinite',
      },
      keyframes: {
        'pulse-glow': {
          '0%, 100%': { boxShadow: '0 0 5px #4A90FF, 0 0 10px #9B59B6' },
          '50%': { boxShadow: '0 0 20px #4A90FF, 0 0 40px #9B59B6' },
        },
      },
    },
  },
  plugins: [require('tailwindcss-animate')],
}

export default config
9️⃣ Frontend: src/app/page.tsx (Landing Page – hero snippet)
'use client'
import { motion } from 'framer-motion'
import { ArrowRight, Sparkles, Zap } from 'lucide-react'
import { Button } from '@/components/ui/button'

export default function LandingPage() {
  return (
    <div className="min-h-screen bg-black text-white overflow-hidden">
      {/* Animated background grid */}
      <div className="absolute inset-0 bg-[linear-gradient(rgba(74,144,255,0.05)_1px,transparent_1px),linear-gradient(90deg,rgba(74,144,255,0.05)_1px,transparent_1px)] bg-[size:50px_50px]" />
      
      <section className="relative z-10 flex flex-col items-center justify-center min-h-screen px-4 text-center">
        <motion.div
          initial={{ opacity: 0, y: 30 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.8 }}
        >
          <div className="inline-flex items-center gap-2 px-4 py-2 mb-8 glass rounded-full text-sm">
            <Sparkles className="w-4 h-4 text-primary" />
            <span>AI-Powered Fitness Evolution</span>
          </div>
          <h1 className="text-5xl md:text-7xl font-bold mb-6 bg-gradient-to-r from-primary via-secondary to-primary bg-clip-text text-transparent">
            ZYRATHON-X AI
          </h1>
          <p className="text-xl md:text-2xl text-muted-foreground max-w-2xl mb-8">
            Your personal AI fitness coach, nutritionist, and transformation engine — all in one cybernetic platform.
          </p>
          <div className="flex gap-4 justify-center">
            <Button size="lg" className="neon-glow text-lg px-8 py-6">
              Start Free Trial <ArrowRight className="ml-2 h-5 w-5" />
            </Button>
            <Button variant="outline" size="lg" className="border-primary text-primary hover:bg-primary/10 text-lg px-8 py-6">
              Watch Trailer <Zap className="ml-2 h-5 w-5" />
            </Button>
          </div>
        </motion.div>
      </section>
    </div>
  )
}
🔟 Frontend: src/app/(dashboard)/layout.tsx (Dashboard shell with sidebar)
'use client'
import { Sidebar } from '@/components/layout/Sidebar'
import { DashboardShell } from '@/components/layout/DashboardShell'

export default function DashboardLayout({ children }: { children: React.ReactNode }) {
  return (
    <div className="flex h-screen bg-black">
      <Sidebar />
      <DashboardShell>
        {children}
      </DashboardShell>
    </div>
  )
}
1️⃣1️⃣ Frontend: src/components/layout/Sidebar.tsx
'use client'
import { Dumbbell, Apple, Bot, BarChart3, Settings, CreditCard, LogOut } from 'lucide-react'
import Link from 'next/link'
import { usePathname } from 'next/navigation'
import { cn } from '@/lib/utils'

const navItems = [
  { href: '/dashboard', icon: BarChart3, label: 'Overview' },
  { href: '/dashboard/workout', icon: Dumbbell, label: 'Workouts' },
  { href: '/dashboard/nutrition', icon: Apple, label: 'Nutrition' },
  { href: '/dashboard/ai-chat', icon: Bot, label: 'AI Coach' },
  { href: '/dashboard/subscription', icon: CreditCard, label: 'Subscription' },
  { href: '/dashboard/settings', icon: Settings, label: 'Settings' },
]

export function Sidebar() {
  const pathname = usePathname()
  return (
    <aside className="w-64 border-r border-border bg-card glass flex flex-col">
      <div className="p-6 border-b border-border">
        <h2 className="text-2xl font-bold bg-gradient-to-r from-primary to-secondary bg-clip-text text-transparent">
          ZYRATHON-X
        </h2>
      </div>
      <nav className="flex-1 p-4 space-y-2">
        {navItems.map((item) => (
          <Link
            key={item.href}
            href={item.href}
            className={cn(
              'flex items-center gap-3 px-4 py-3 rounded-lg text-sm font-medium transition-all duration-200',
              pathname === item.href
                ? 'bg-primary/20 text-primary neon-glow'
                : 'text-muted-foreground hover:bg-primary/10 hover:text-white'
            )}
          >
            <item.icon className="w-5 h-5" />
            {item.label}
          </Link>
        ))}
      </nav>
      <div className="p-4 border-t border-border">
        <button className="flex items-center gap-3 px-4 py-3 text-muted-foreground hover:text-red-500 transition-colors w-full">
          <LogOut className="w-5 h-5" />
          Logout
        </button>
      </div>
    </aside>
  )
}
1️⃣2️⃣ Frontend: src/components/dashboard/ProgressRing.tsx
'use client'
import { motion } from 'framer-motion'

interface ProgressRingProps {
  progress: number // 0-100
  size?: number
  strokeWidth?: number
  color?: string
  label?: string
}

export function ProgressRing({ progress, size = 120, strokeWidth = 8, color = '#4A90FF', label }: ProgressRingProps) {
  const radius = (size - strokeWidth) / 2
  const circumference = 2 * Math.PI * radius
  const offset = circumference - (progress / 100) * circumference

  return (
    <div className="relative flex items-center justify-center">
      <svg width={size} height={size} className="rotate-[-90deg]">
        <circle
          cx={size / 2}
          cy={size / 2}
          r={radius}
          stroke="rgba(255,255,255,0.1)"
          strokeWidth={strokeWidth}
          fill="none"
        />
        <motion.circle
          cx={size / 2}
          cy={size / 2}
          r={radius}
          stroke={color}
          strokeWidth={strokeWidth}
          fill="none"
          strokeLinecap="round"
          strokeDasharray={circumference}
          initial={{ strokeDashoffset: circumference }}
          animate={{ strokeDashoffset: offset }}
          transition={{ duration: 1.5, ease: 'easeOut' }}
        />
      </svg>
      <div className="absolute flex flex-col items-center">
        <span className="text-2xl font-bold text-white">{Math.round(progress)}%</span>
        {label && <span className="text-xs text-muted-foreground">{label}</span>}
      </div>
    </div>
  )
}
1️⃣3️⃣ Frontend: src/app/(dashboard)/workout/page.tsx (excerpt)
'use client'
import { useEffect, useState } from 'react'
import { ProgressRing } from '@/components/dashboard/ProgressRing'
import { Button } from '@/components/ui/button'
import { Dumbbell, Flame, Zap, Trophy } from 'lucide-react'

export default function WorkoutPage() {
  const [stats, setStats] = useState({ caloriesBurned: 0, streak: 0, workoutsThisWeek: 0 })

  useEffect(() => {
    // Fetch from API
    fetch('/api/workouts/stats', { headers: { Authorization: `Bearer ${localStorage.getItem('token')}` } })
      .then(res => res.json())
      .then(data => setStats(data))
  }, [])

  return (
    <div className="p-6 space-y-8">
      <h1 className="text-3xl font-bold">Workouts</h1>
      
      <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div className="glass p-6 rounded-xl flex items-center gap-4">
          <Flame className="w-8 h-8 text-orange-500" />
          <div>
            <p className="text-sm text-muted-foreground">Calories Burned</p>
            <p className="text-2xl font-bold">{stats.caloriesBurned}</p>
          </div>
        </div>
        <div className="glass p-6 rounded-xl flex items-center gap-4">
          <Zap className="w-8 h-8 text-yellow-500" />
          <div>
            <p className="text-sm text-muted-foreground">Streak</p>
            <p className="text-2xl font-bold">{stats.streak} days</p>
          </div>
        </div>
        <div className="glass p-6 rounded-xl flex items-center gap-4">
          <Trophy className="w-8 h-8 text-purple-500" />
          <div>
            <p className="text-sm text-muted-foreground">Workouts This Week</p>
            <p className="text-2xl font-bold">{stats.workoutsThisWeek}</p>
          </div>
        </div>
      </div>

      <div className="glass p-6 rounded-xl">
        <h2 className="text-xl font-semibold mb-4">Today's AI-Generated Workout</h2>
        <p className="text-muted-foreground mb-4">Your personal Zyrath AI has prepared a 45-min full body session.</p>
        <Button className="neon-glow">Start Workout</Button>
      </div>
    </div>
  )
}
1️⃣4️⃣ Frontend: src/app/(dashboard)/ai-chat/page.tsx
'use client'
import { useState } from 'react'
import { ChatWindow } from '@/components/ai/ChatWindow'
import { Button } from '@/components/ui/button'
import { Input } from '@/components/ui/input'

export default function AIChatPage() {
  const [messages, setMessages] = useState<{ role: 'user' | 'ai'; content: string }[]>([])
  const [input, setInput] = useState('')
  const [loading, setLoading] = useState(false)

  const sendMessage = async () => {
    if (!input.trim()) return
    const userMsg = { role: 'user' as const, content: input }
    setMessages(prev => [...prev, userMsg])
    setInput('')
    setLoading(true)

    try {
      const res = await fetch('/api/ai/chat', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
          Authorization: `Bearer ${localStorage.getItem('token')}`
        },
        body: JSON.stringify({ message: input })
      })
      const data = await res.json()
      setMessages(prev => [...prev, { role: 'ai', content: data.reply }])
    } catch (error) {
      setMessages(prev => [...prev, { role: 'ai', content: 'Sorry, I encountered an error. Please try again.' }])
    } finally {
      setLoading(false)
    }
  }

  return (
    <div className="flex flex-col h-full p-6">
      <h1 className="text-3xl font-bold mb-6">AI Coach Zyrath</h1>
      <div className="flex-1 overflow-y-auto space-y-4 mb-4">
        <ChatWindow messages={messages} loading={loading} />
      </div>
      <div className="flex gap-2">
        <Input
          value={input}
          onChange={(e) => setInput(e.target.value)}
          onKeyDown={(e) => e.key === 'Enter' && sendMessage()}
          placeholder="Ask Zyrath anything about fitness, nutrition, or motivation..."
          className="flex-1 bg-card border-border"
        />
        <Button onClick={sendMessage} disabled={loading} className="neon-glow">
          Send
        </Button>
      </div>
    </div>
  )
}
1️⃣5️⃣ Backend: src/routes/payments.js (Stripe + Razorpay)
const router = require('express').Router();
const stripe = require('stripe')(process.env.STRIPE_SECRET_KEY);
const Razorpay = require('razorpay');
const { protect } = require('../middleware/auth');

const razorpay = new Razorpay({
  key_id: process.env.RAZORPAY_KEY_ID,
  key_secret: process.env.RAZORPAY_KEY_SECRET
});

// Stripe Checkout Session
router.post('/create-checkout-session', protect, async (req, res) => {
  const { plan, paymentMethod } = req.body; // 'stripe' or 'razorpay'
  const priceMap = {
    'nexus': 1400,    // $14 in cents
    'titan-x': 3900,
    'omega-infinity': 9900
  };
  const amount = priceMap[plan];
  if (!amount) return res.status(400).json({ message: 'Invalid plan' });

  if (paymentMethod === 'stripe') {
    const session = await stripe.checkout.sessions.create({
      payment_method_types: ['card'],
      line_items: [{
        price_data: {
          currency: 'usd',
          product_data: { name: `ZYRATHON-X ${plan.toUpperCase()} Plan` },
          unit_amount: amount
        },
        quantity: 1
      }],
      mode: 'subscription',
      success_url: `${process.env.CLIENT_URL}/dashboard/subscription?success=true`,
      cancel_url: `${process.env.CLIENT_URL}/dashboard/subscription?canceled=true`,
      metadata: { userId: req.user._id.toString(), plan }
    });
    res.json({ url: session.url });
  } else if (paymentMethod === 'razorpay') {
    const order = await razorpay.orders.create({
      amount: amount * 100, // Razorpay expects paise
      currency: 'INR',
      receipt: `receipt_${req.user._id}`
    });
    res.json({ orderId: order.id, amount: order.amount, currency: order.currency });
  }
});

// Webhook endpoints (Stripe & Razorpay) – omitted for brevity but must be implemented
🧠 Key UI Components (Shadcn & Custom)
ui/button.tsx – Shadcn button with neon-glow variant
ui/card.tsx – Glassmorphism card with className="glass rounded-xl p-6"
ui/input.tsx – Dark input with bg-card border-border
ui/badge.tsx – For subscription tiers
ui/avatar.tsx – User avatar
All Shadcn components are installed via npx shadcn-ui@latest add button card input badge avatar.

🚀 Deployment Steps
Backend (Vercel / Railway / Render)
Set environment variables in your hosting dashboard.
Build command: npm install
Start command: node src/server.js
Ensure MongoDB Atlas whitelist includes your server IP.
Frontend (Vercel)
Connect GitHub repo.
Set environment variables (NEXT_PUBLIC_*).
Build command: npm run build
Output directory: out (if static) or default.
Docker (Optional)
# docker-compose.yml
version: '3'
services:
  backend:
    build: ./backend
    ports:
      - "5000:5000"
    env_file: ./backend/.env
  frontend:
    build: ./frontend
    ports:
      - "3000:3000"
    env_file: ./frontend/.env.locaL
