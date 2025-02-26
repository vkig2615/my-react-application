# Step 1: Build React App
FROM node:14 AS build

WORKDIR /app
COPY . /app

RUN npm install
RUN npm run build

# Step 2: Serve the React App
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
