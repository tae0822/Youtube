# YouTube Clone 
**YouTube Clone** is a video streaming interface built with React, focusing on **Efficient API Integration** and **Data Caching Strategies** using the YouTube Data API v3.

[![Tech Stack](https://img.shields.io/badge/React-Ready-blue)](https://reactjs.org/)
[![YouTube API](https://img.shields.io/badge/API-YouTube_Data_v3-red)](https://developers.google.com/youtube/v3)
[![React Query](https://img.shields.io/badge/State-React_Query-red)](https://tanstack.com/query/latest)

---

## 💡 Why I Built This
Handling massive amounts of external data requires more than just fetching; it requires **optimization**. I built this **YouTube Clone** to explore:
- **API Efficiency**: Managing the strict daily quotas of the YouTube Data API.
- **Search UX**: Implementing seamless search and filtering logic.
- **Data Persistence**: Reducing redundant network requests through smart caching.

## 🛠 Strategic Engineering Choices

### 1. Optimized Data Fetching (React Query)
To prevent hitting API limits and to provide a snappy user experience, I centralized all data fetching.
- **Result**: Implemented **React Query** to cache video lists and search results. 
- **Impact**: Users can navigate back and forth between the home feed and video details without triggering new API calls, saving significant Quota and improving load speeds.

### 2. Scalable API Client Architecture (Axios)
Instead of scattered `fetch` calls, I built a modular API client.
- **Pattern**: Created a dedicated `Youtube` class/service using **Axios instances**.
- **Impact**: This decoupled the UI components from the API logic, making it easy to switch between "Mock Data" (for development) and "Real API Data" without changing the component code.

### 3. Responsive Media Layout
- **Fluid UI**: Used **Tailwind CSS** to build a responsive grid system that mimics the original YouTube layout across mobile, tablet, and desktop.
- **Dynamic Routing**: Utilized **React Router** for deep-linking to specific videos and search queries.

## 🔥 Critical Problem Solving

### Case Study: Minimizing API Quota Usage
**Context**: The YouTube Data API has a very limited daily free tier. Every search and list request consumes "points," which can quickly run out during development.

**Analysis**: Constant re-rendering and page navigation were causing duplicate API requests for the same data.

**Resolution**: 
- Implemented a **Global Cache** strategy using React Query.
- Set a custom `staleTime` and `cacheTime` for video data that doesn't change frequently (like Popular Videos).
- **Outcome**: Reduced API consumption by approximately 60%, allowing for extended development and testing periods without service interruption.

## 🎬 Project Showcase

#### ✅ Video Discovery & Feed
*High-performance video grid featuring popular trends and category filtering.*
<img src="https://github.com/user-attachments/assets/df5d72a7-2464-4589-b448-4f3ec057c44c" width="100%" />

---

#### ✅ Search & Detailed View
*Optimized search functionality with dynamic video playback and related content suggestions.*
<img src="https://github.com/user-attachments/assets/64467e85-c416-4895-84e4-525ea8e3afba" width="100%" />

---

## 📊 Technical Specs & Growth
- **Data Source**: YouTube Data API v3.
- **Styling**: Tailwind CSS (Utility-first).
- **Future Scale**: 
  - Implement **Infinite Scroll** to load more videos seamlessly.
  - Add **Shimmer UI (Skeleton Screens)** for a better perceived loading experience.

---
[Live Demo](https://youtube-lyart-pi.vercel.app) | [GitHub Repo](https://github.com/tae0822/Youtube)
