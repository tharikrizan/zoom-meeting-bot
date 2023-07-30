# Zoom Meeting Bot JavaScript sample

Use of this sample app is subject to our [Terms of Use](https://explore.zoom.us/en/legal/zoom-api-license-and-tou/).

This repo contains an HTML/CSS/JavaScript website that utilizes the [Zoom Meeting SDK](https://developers.zoom.us/docs/meeting-sdk/web/) with a Node.js Express backend and the Chrome Headless browser to join Zoom meetings and request recording permission as a participant. The frontend is built with Vanilla JS to demonstrate the capabilities of headless browsers for bot development.

Requirements:

- Nodejs

---

## Installation

To get started, clone the repo : https://github.com/zoom/meetingsdk-web-bot-sample.git

## Setup

1. Once cloned, navigate to the meetingsdk-sample-javascript directory:

```bash
$ cd meetingsdk-web-bot-sample-javascript
```

2. Then install the dependencies:

```bash
$ npm install
```

3. Copy .env.example to store your Meeting SDK credentials:
   login to zoom marketplace with your zoom account, on top right corner click build, create app. We need to create 2 apps.

Firstly, Create a meeting sdk app and copy the client key and secret, use them for ZOOM_MSDK_KEY and
ZOOM_MSDK_SECRET respectively
Secondly, create a server to server Oauth app and get the values for ACCOUNT_ID, CLIENT_ID, CLIENT_SECRET

```bash
$ cp .env.example .env
```

4. In the frontend directory, open the client-view.js file, and enter values for the variables:

   | Variable | Description                                                          |
   | -------- | -------------------------------------------------------------------- |
   | url      | invite url of zoom meeting                                           |
   | sdkKey   | Required, your Zoom Meeting SDK Key or Client ID for Meeting SDK app |

5. Launch a development local Server or open index.html in your browser ([or serve over localhost](https://www.npmjs.com/package/http-server)).

6. In backend/helpers/meetingBot.js, enter local development url or site url.

```js
await page.goto("{Enter local development url or site url}", {
  waitUntil: "load",
});
```

8. Start the server:

```bash
npm run start
```

9.  Meeting bot should enter the meeting as a participant and request recording permission.
