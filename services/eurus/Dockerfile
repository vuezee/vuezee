FROM node:12-alpine AS builder
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

FROM node:12-alpine
RUN yarn global add serve
WORKDIR /app
COPY --from=builder /app/build .
EXPOSE 8100
CMD ["serve", "-p", "8100", "-s", "."]
