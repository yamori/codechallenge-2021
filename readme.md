Code Challenge 2021 by Connor
===

This App built with [React Native](https://facebook.github.io/react-native/).

## Setup

This project was bootstrapped with Create React Native App with Typescript. Below you'll find information about performing common tasks.

After cloning the repoitory you should:
* Install NPM Packages `npm install`
* Then install CocoaPod dependencies `cd ios && pod install && cd ..`

## Running In a Simulator

To start the app in Development Mode:
* Start the Metro Bundler by running: `npx start`
* Leave the Metro Bundler running in one terminal, and in a new terminal run: `npx react-native run-ios`
  * NOTE, you can change what device you run it on, but currently the app is only supported on iPads. To see a full list of devices you can run `xcrun simctl list devices`

Sometimes you may need to reset or clear the React Native packager's cache. To do so, you can pass the `--reset-cache` flag to the start script:

```
npm start -- --reset-cache
# or
yarn start -- --reset-cache
```

## Linting

There are two Linter scripts available to run:
* `npm run lint` will give you a list of all linting warnings and errors
* `npm run lint:fix` will fix any linting errors that it's able to automatically fix. Warning that this WILL change files in your application

## Writing and Running Tests

This project is set up to use [jest](https://facebook.github.io/jest/) for tests. Create test files in directories called `__tests__` or with the `.test` extension to have the files loaded by jest. See the [the template project](https://github.com/react-community/create-react-native-app/blob/master/react-native-scripts/template/App.test.js) for an example test. The [jest documentation](https://facebook.github.io/jest/docs/en/getting-started.html) is also a wonderful resource, as is the [React Native testing tutorial](https://facebook.github.io/jest/docs/en/tutorial-react-native.html).

You can run all unit tests with `npm run test`.

## Testing on Non-Development Devices

Before you can share the application with other users for testing, you must sign your application. See the [React Native Code Signing Instructions](https://reactnative.dev/docs/running-on-device#2-configure-code-signing) for more information on how to sign an application.

Once your application is signed you can create a package that can be distributed for TestFlight deployment by following the steps below:
* In Xcode be sure that you've changed your target device to "Any iOS Device"
* Choose Product -> Archive
  * You should also be able to build the archive via Command Line with `npx react-native run-ios --configuration Release`, but you'll need to open Xcode for the next step regardless
* In the Organizer window (choose Window -> Organizer) you will see the archive that you created
* You can then choose Distribute App, follow the prompts (choose App Store Connect for distribution method), and it will upload to iTunes Connect
* In [iTunes Connect](https://appstoreconnect.apple.com/apps/) you then choose your application, go to the TestFlight tabm and once Apple has approved for testing you can choose the users or user-groups to send the application to

## Version Number and Last Updated Date

The app is setup to pull the Version Number from xcode (In xcode where you manage Version and Build numbers).

Apple doesn't have an out-of-the-box Build Date, so we added Build Phases Run Script in xcode that updates the versionInfo/buildDate.tsx file every time xcode does a build or archive. This could easily be replaced with another process if you want to manage the date manually, but this should work for all iOS builds (and the versionInfo.tsx file explains how to do this for Android if you expand there in the future)
