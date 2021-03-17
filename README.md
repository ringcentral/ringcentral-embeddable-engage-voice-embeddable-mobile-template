# RingCentral Engage voice embeddable mobile template

<!-- sep -->

**Experimental** Android/IOS apps template based on [ringcentral-engage-voice-embeddable](https://github.com/ringcentral/engage-voice-embeddable) and cordova

## Demo video

- Android: https://youtu.be/rPoOqpVa5as

## Download demo apps

[https://github.com/ringcentral/ringcentral-engage-voice-embeddable-mobile/releases](https://github.com/ringcentral/ringcentral-engage-voice-embeddable-mobile/releases)

## Dev

### Prerequisites

- Install Nodejs and npm(recommend using [nvm](https://github.com/nvm-sh/nvm)).
- Install cordova: `npm i -g cordova`
- Android: Follow the cordova guide to prepare for Android development: https://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html
- IOS: Follow the cordova guide to prepare for ISO development: https://cordova.apache.org/docs/en/latest/guide/platforms/ios/index.html, also requires paid apple developer account.
- ImageMagick installed (Mac: `brew install imagemagick`, Debian/Ubuntu: `sudo apt-get install imagemagick`, Windows: [See here, install "Legacy tools"](http://www.imagemagick.org/script/binary-releases.php#windows))
- cordova-splash: `npm install cordova-splash -g`
- cordova-icon: `npm install cordova-icon -g`
- If you using emulator, you may need open the emulator first
- A developer account in developer.ringcentral.com(free to register)
- Create an app in developer.ringcentral.com, Create a RingCentral app with platform type - "Browser Based", and add permissions `Edit Message`, `Edit Presence`, `Internal Messages`, `Read Accounts`, `Read Call Log`, `Read Contacts`, `Read Messages`, `Read Presence`, `RingOut`, `SMS`, `Call Control` and `VoIP Calling` to your app, must graduate to deploy in production.

```bash
# install dependencies
npm run pre && npm i

# start proxy server
npm run proxy

# will get https://xxxx.ngrok.io -> localhost:6066
# Remember https://xxxx.ngrok.io as serverUrl

# create env file, then fill .env with serverUrl as RINGCENTRAL_APP_SERVER and RINGCENTRAL_CLIENT_ID and RINGCENTRAL_CLIENT_SECRET with your own app in developer.ringcentral.com, must be production app and web based with account permission.
# Set https://xxxx.ngrok.io/rc-auth as callback url in app setting
cp sample.env .env

# start server
npm start

# start client in another terminal
npm run c

# prepare cordova in another terminal
npm run prepare

# run Android app, make sure you have simulator or real android device ready
npm run a

# run IOS app, make sure you have real IOS device and paid developer ID ready,
# and open platforms/ios with xcode and config build an debug env
npm run i
```

## Build apps

```sh
# build Android app
npm run build-android

# build IOS app
npmrun build-ios
```

## Deploy

```sh
## build all files to deploy folder
npm run build-dist
```

Just deploy the `deploy` folder to your server/serverless or any platform.

## Customize

- **Edit icon/splash**: Just replace [src/app/icon.png](src/app/icon.png) or [src/app/splash.png](src/app/splash.png)
- **Edit config/plugin**: Edit [src/app/config.xml](src/app/config.xml)
- **Add more server side function**: Edit [src/server/app/app.js](src/server/app/app.js)
- **Add more front end functions**: Edit [src/client/extra/index.js](src/client/extra/index.js)

## License

MIT
