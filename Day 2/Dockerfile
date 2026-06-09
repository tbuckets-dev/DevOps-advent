FROM node:26-alpine3.23

# Install everything first (breaks cache on any file change)
WORKDIR /app
COPY . .

# Install dependencies (runs every time anything changes)
RUN npm install

# Build the application
RUN npm run build

# Install production dependencies
RUN npm prune --production

EXPOSE 3000

CMD ["node", "dist/index.js"]
