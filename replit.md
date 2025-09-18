# Overview

This is a Progressive Web App (PWA) for retail shop management called "HZ Shop Management". The application is built using Next.js 14 with React Server Components and provides comprehensive features for managing products, categories, receipts, returns, shopkeepers, and reports. The system is designed with offline-first capabilities, allowing shops to continue operations even without internet connectivity.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
The application uses Next.js 14 with the App Router and React Server Components for optimal performance. The UI is built with shadcn/ui components based on Radix UI primitives and styled with Tailwind CSS. The system implements a responsive design with mobile-first approach, including a bottom navigation for mobile devices and a collapsible sidebar for desktop.

## State Management
The application uses React hooks for local state management with custom hooks for common functionality like mobile detection and toast notifications. Real-time synchronization is handled through event-driven architecture using CustomEvents for cross-component communication.

## Offline-First Architecture
The system implements a comprehensive offline-first approach using IndexedDB for local data storage and a custom sync manager for handling data synchronization between local storage and the server. The offline storage wrapper provides a unified interface for CRUD operations that work both online and offline.

## PWA Implementation
The application is configured as a Progressive Web App with service worker support, manifest file, and installation prompts. It includes offline fallbacks and background sync capabilities to ensure seamless user experience regardless of connectivity.

## Authentication & Data Layer
The system integrates with Supabase for backend services, providing authentication, real-time database capabilities, and server-side rendering support. The middleware handles CORS configuration and request routing, with special considerations for Replit development environment.

## Component Architecture
The UI follows a modular component architecture with reusable components organized by function:
- Layout components for structural elements (header, sidebar, navigation)
- Page components for main application views
- Modal components for forms and detailed views
- UI components following the shadcn/ui design system

## Data Synchronization
The sync manager handles bidirectional data synchronization between local IndexedDB storage and Supabase. It maintains a sync queue for offline operations and automatically synchronizes data when connectivity is restored. The system supports conflict resolution and maintains data consistency across online/offline states.

## PDF Generation
The application includes custom PDF generation capabilities for receipts and reports using jsPDF library, with support for generating both PDF documents and receipt images for sharing.

# External Dependencies

## Backend Services
- **Supabase**: Primary backend-as-a-service providing PostgreSQL database, authentication, and real-time subscriptions
- **@supabase/supabase-js**: JavaScript client for Supabase integration
- **@supabase/ssr**: Server-side rendering support for Supabase

## UI Framework & Styling
- **Next.js 14**: React framework with App Router and Server Components
- **React**: Frontend framework with hooks and context
- **Tailwind CSS**: Utility-first CSS framework for styling
- **shadcn/ui**: Component library built on Radix UI primitives
- **@radix-ui/***: Headless UI components for accessibility and behavior

## State Management & Forms
- **react-hook-form**: Form state management and validation
- **@hookform/resolvers**: Form validation resolvers

## Utilities & Tools
- **clsx & class-variance-authority**: Utility functions for conditional CSS classes
- **date-fns**: Date manipulation and formatting library
- **jsPDF**: PDF generation for receipts and reports
- **cmdk**: Command palette component
- **next-themes**: Theme switching functionality

## Development & Deployment
- **TypeScript**: Type safety and development experience
- **@vercel/analytics**: Analytics and performance monitoring
- **Geist fonts**: Typography (Sans and Mono variants)

## PWA & Offline Support
- **IndexedDB**: Browser storage for offline data persistence
- **Service Worker**: Background sync and offline capabilities
- **Web App Manifest**: PWA installation and theming configuration