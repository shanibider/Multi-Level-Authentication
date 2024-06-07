# Node.js & Express - Multi-Level Authentication <img height="60px" align="center" src="https://github.com/shanibider/Authentication-and-Security-Node-Express-PostgreSQL/assets/72359805/d5814dcd-031a-4225-95da-e2a515dfa4de">


<div align="center">
<img align="right" height="270px" src="https://github.com/shanibider/Node.js-Express-Multi-Level-Authentication/assets/72359805/08ff40e7-09b9-4446-b503-6804eca27afb">
<img height="250px" src="https://github.com/shanibider/Authentication-and-Security-Node-Express-PostgreSQL/assets/72359805/c181937f-4d68-41be-b341-8667fcdeae1d"></div>
<br>

This guide will walk you through implementing multi-level authentication in your Node.js and Express application, using:
### JavaScript, Node.js, Express.js, EJS, and PostgreSQL. <img height=20px src="https://skillicons.dev/icons?i=postgresql"> <img height=20px src="https://skillicons.dev/icons?i=express"> <img height=20px src="https://skillicons.dev/icons?i=nodejs"> <img height=20px src="https://skillicons.dev/icons?i=js">.

The authentication levels covered include: 
### 🔑 1. Basic Authentication 
### 🔑 2. Hashing Authentication  
### 🔑 3. Google OAuth 2.0 Authentication using Passport.js and PostgreSQL 



## 🔓 1. Basic Authentication
Basic Authentication involves prompting users to enter their **credentials (username and password)** for authentication.

### Steps to Implement Basic Authentication 📄
1. Define **routes** for ***login and registration***.
2. Implement **route handlers** to handle login and registration requests.
3. Verify `user credentials` against a database.
4. Upon successful authentication, issue a `token` or set a `session` to maintain user authentication.

## 🔓 2. Hashing and Session Authentication
**Hashing and Session Authentication** involves securely storing user passwords using `bcrypt.js` and maintaining user sessions using Express session middleware.

### Steps to Implement Hashing and Session Authentication 📄
1. Install `bcryptjs.js` and Express session middleware.
2. Configure **session middleware** and **secret**.
3. **Hash** user passwords before storing them in the database.
4. Use **session middleware** to maintain user sessions across requests.
5. Protect routes by verifying `session` authentication.

## 🔓 3. OAuth2 Authentication using Google
Google `OAuth2` Authentication allows users to authenticate using their Google account, providing a seamless and secure login experience.

### Steps to Implement Google OAuth2 Authentication 📄
1. Set up Google Developer Console and obtain `OAuth client credentials`.
2. Install required dependencies: `passport`, `passport-google-oauth20`, `dotenv`.
3. Configure **environment variables** for **Google OAuth credentials**.
4. Implement `Passport.js` Google OAuth2 strategy.
5. Define **routes** for Google authentication.
6. Protect routes using `Passport's` authentication middleware.
<br>

<div align="center">
<img height=300px src="https://github.com/shanibider/Node.js-Express-Multi-Level-Authentication/assets/72359805/c86c9981-a0b4-4dc9-a2a9-12b5c88acdf2">
</div>

---


# About OAuth 2.0 🛡️ <img align="center" height=150px src="https://github.com/shanibider/Node.js-Express-Multi-Level-Authentication/assets/72359805/a0c4fac3-6a30-4ccc-8057-bf7fd0ba21cf">

OAuth 2.0 is an authorization framework that standardizes third-party access to HTTP services securely, allowing applications to act on behalf of users.

<img align="center" height=650px width=1200px src="https://github.com/shanibider/Node.js-Express-Multi-Level-Authentication/assets/72359805/191614c1-65aa-4da9-bf4e-0e7285e9e737">

## Key Roles

- [ ] **Client**: Requests access to resources.
- [ ] **Resource Owner**: User granting or denying access to their data.
- [ ] **Resource Server**: Stores protected user data.
- [ ] **Authorization Server**: Authenticates the resource owner and issues access tokens.

## Process Overview 🔄

- [x] 1. User wants to access resources.
- [x] 2. App requests **authorization**.
- [x] 3. User inputs **credentials**.
- [x] 4. App sends **credentials with `OAuth keys`** to Authorization Server.
- [x] 5. Authorization Server returns `Access token`.
- [x] 6. App sends `token` to Resource Server.
- [x] 7. Resource Server serves resource to the app.
- [x] 8. App ***confirms accessibility*** to the user.

## OAuth 2.0 Flow 🌊

OAuth offers various flows:

- [ ] **Authorization Code Flow**: For server-side apps, exchanges code for `token`.
- [ ] **Implicit Flow**: Deprecated, returns `token` directly but lacks security.
- [ ] **Resource Owner Password Credentials Flow**: Uses `user's credentials` directly.
- [ ] **Client Credentials Flow**: For server-to-server authentication.
- [ ] **Refresh Token Flow**: Obtains `new token` when the old one expires.
- [ ] **Device Code Flow**: Facilitates authorization on devices with limited input.
- [ ] **Extension Flow**: Customizable for specific needs.

## Use Cases 📱

- **Third-Party Access**: Users grant apps limited access without credentials.
- **Single Sign-On (SSO)**: Enables users to log in once for multiple services.
- **Mobile Applications**: Allows secure access to services on mobile devices.

<div align="center"> 
<img height="650" src="https://github.com/shanibider/Node.js-Express-Multi-Level-Authentication/assets/72359805/3902d138-9fc0-4680-bc98-f67c22e75fb7">
</div>

---

## Related Links 🔗
- [x] [AES256 encrypt & decrypt online](https://encode-decode.com/aes256-encrypt-online/)
- [x] [Try the Ciser Chiper](https://cryptii.com/pipes/caesar-cipher)
- [x] [Password Strength Checker](http://password-checker.online-domain-tools.com/)
- [x] [Have I Been Pwned?](https://haveibeenpwned.com/)

## Resources 🔗
- [Passport.js Documentation](http://www.passportjs.org/)
- [Google OAuth 2.0 Documentation](https://developers.google.com/identity/protocols/oauth2)
- [Express.js Documentation](https://expressjs.com/)

---

# More Info About Authentication and Security 🧠

<div align="center">
<img height="180px" src="https://github.com/shanibider/Authentication-and-Security-Node-Express-PostgreSQL/assets/72359805/3f36e0ec-b21d-4b97-a99a-1dec29bf00e4"></div>

## Encryption for Data Security 🧰

Encryption involves encoding data to make it unintelligible to unauthorized users. In the context of web development, encrypting sensitive information before storing it in the database adds an extra layer of security. Tools like OpenSSL or libraries such as `bcrypt.js` can be used for **encryption in JavaScript applications**.
 
## Hashing and Salting with bcrypt 🧰

**Hashing** transforms sensitive data into a fixed-size string of characters, making it challenging for attackers to reverse-engineer the original data. Salting involves adding **random data (salt)🧂** to the input before hashing, further enhancing security. The `bcrypt` library in `Node.js` simplifies the process of hashing and salting passwords securely.

## Session Management with Sessions and Cookies 🧰

**Sessions and cookies** are commonly used to persist user login sessions across multiple requests. `Sessions` store user-specific data on the server, while cookies store data on the client-side. Implementing session management ensures that users remain **authenticated** throughout their **browsing session**, enhancing user experience and security.

## Using Passport.js for Authentication 🧰

`Passport.js` is a popular **authentication middleware** for `Node.js` applications, offering a wide range of authentication strategies, including local authentication, OAuth, and more. Integrating `Passport.js` simplifies the authentication process and provides robust security features out of the box.

## Securing Secret Keys with Environment Variables 🧰

Sensitive information such as **API keys**, **database credentials**, and cryptographic keys should never be hard-coded in the application code. Instead, they should be stored as **environment variable**s and accessed programmatically. This practice minimizes the risk of exposing sensitive information and enhances application security.

## OAuth 2.0 Integration 🧰

`OAuth 2.0` is an industry-standard protocol for authorization, allowing users to grant **third-party applications** limited access to their resources without sharing **their credentials**. Integrating `OAuth 2.0` with popular identity providers such as `Google` and `Facebook` enables seamless and **secure user authentication** in JavaScript applications.

> For detailed implementation instructions and code examples, please refer to the sample code provided in this repository.

--- 

## Installation 🛠️
```bash
npm install express bcryptjs passport passport-local passport-google-oauth20 express-session dotenv
```

## Usage
1. Clone this repository.
2. Configure your environment variables in a `.env` file.
3. Run the application using `npm start`.
4. Access the application in your browser.

---
  
## Screenshots 🖼️

![secrets_home](https://github.com/shanibider/Authentication-and-Security-Node-Express-PostgreSQL/assets/72359805/4a761bed-8e4a-4ca5-bb45-176b609fa6f0)

### Level 1 - Basic authentication - Registration users with email and password (password stored unencrypted in db) -
![2](https://github.com/shanibider/Authentication-and-Security-Node-Express-PostgreSQL/assets/72359805/260fdc2d-f934-4034-8586-ad1df079a832)
![3](https://github.com/shanibider/Authentication-and-Security-Node-Express-PostgreSQL/assets/72359805/1cee2680-8027-4880-aaf1-0b97d750dd1e)

### Level 2 of authentication - Encrypting and Hashing passwords -
![4-hash](https://github.com/shanibider/Authentication-and-Security-Node-Express-PostgreSQL/assets/72359805/9d4094b4-61fd-4a0c-8fd6-4d5120b51801)

### Level 3 Authentication - using OAuth (Open Authorisation, third party) to authenticate users, without storing their credentials -
![5-outh](https://github.com/shanibider/Authentication-and-Security-Node-Express-PostgreSQL/assets/72359805/921098a6-8813-4ca5-8781-f1bf9e03da2c)
![6](https://github.com/shanibider/Authentication-and-Security-Node-Express-PostgreSQL/assets/72359805/a339aa47-d82b-4798-b5bb-8d1969549d10)


---
> Feel free to explore my repositories and see my projects. I'm always open to collaboration and welcome feedback to improve and grow as a developer. Let's code something amazing together! 🚀😊👩‍💻💻


## 📫 Connect with me 😊
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/shani-bider/)
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://shanibider.github.io/Portfolio/)
[![gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:shanibider@gmail.com)

<footer>
<p style="float:left; width: 20%;">
Copyright © Shani Bider, 2024
</p>
</footer>

## License📄

This project is licensed under the MIT License.
