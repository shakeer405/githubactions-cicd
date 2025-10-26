# Use an official Node.js image as base
FROM node:23-alpine AS builder

# Set working directory
WORKDIR /app

# Copy package files first for dependency caching
COPY ui/package*.json ./

# Install app dependencies
RUN npm ci

# Copy the rest of the application code
COPY . .

# Build the frontend (if applicable)
# Uncomment this if package.json has a build command
# RUN npm run build

# Expose a port (default: 3000 if running a dev server)
EXPOSE 3000

# Define the command to start your app
CMD ["npm", "start"]
