# DeepLinkingExample

Example of usage of deep linking for blog post in React Navigation.

### Run it locally

1. Clone the repository
2. `cd` into the main project directory.
3. Run `yarn` (or `npm install`)
4. `yarn start`
5. To pass deep links to the app, follow https://reactnavigation.org/docs/en/deep-linking.html#test-deep-linking-on-android and https://reactnavigation.org/docs/en/deep-linking.html#test-deep-linking-on-ios

### Settings

1. app.json
   "expo": {
   "scheme": "mychat",
   "ios": {
   "bundleIdentifier": "com.yourcompany.yourappname",
   "buildNumber": "1.0.0",
   "supportsTablet": true
   },
   "android": {
   "package": "com.yourcompany.yourappname",
   "versionCode": 1
   }
   }

2. 빌드 및 설치
   expo build:ios -t simulator
   expo build:android -t apk

   expo build:status
   download and tar -xvzf your-app.tar.gz

   xcrun simctl install booted <app path>
   adb install app-filename.apk

3. Test
   xcrun simctl openurl booted mychat://user/1/2
   adb shell am start -W -a android.intent.action.VIEW -d "mychat://user/1/2" com.yourcompany.yourappname
