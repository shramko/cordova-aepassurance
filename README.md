# Adobe Experience Platform - Assurance plugin for Cordova apps
[![CI](https://github.com/adobe/cordova-aepassurance/workflows/CI/badge.svg)](https://github.com/adobe/cordova-aepassurance/actions)
[![npm](https://img.shields.io/npm/v/@adobe/cordova-aepassurance)](https://www.npmjs.com/package/@adobe/cordova-aepassurance)
[![GitHub](https://img.shields.io/github/license/adobe/cordova-aepassurance)](https://github.com/adobe/cordova-aepassurance/blob/main/LICENSE)

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Running Tests](#running-tests)
- [Sample App](#sample-app)
- [Additional Cordova Plugins](#additional-cordova-plugins)
- [Contributing](#contributing)
- [Licensing](#licensing)

## Prerequisites

Cordova is distributed via [Node Package Management](https://www.npmjs.com/) (aka - `npm`).  

In order to install and build Cordova applications you will need to have `Node.js` installed. [Install Node.js](https://nodejs.org/en/).  

Once Node.js is installed, you can install the Cordova framework from terminal:  

```  
sudo npm install -g cordova  
```  
## Installation

To start using the AEP SDK for Cordova, navigate to the directory of your Cordova app and install the plugin:
```
cordova plugin add cordova-aepassurance-fork
```
Check out the documentation for help with APIs

## Usage
### [Assurance](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-experience-platform-assurance)

##### Getting the SDK version:
```js
AEPAssurance.extensionVersion(function(version){  
  console.log(version);
}, function(error){  
  console.log(error);  
});
```
##### Registering the extension with ACPCore:

> Note: It is required to initialize the SDK via native code inside your AppDelegate and MainApplication for iOS and Android respectively. For more information see how to initialize [Griffon](https://aep-sdks.gitbook.io/docs/beta/project-griffon/set-up-project-griffon#add-project-griffon-extension-to-your-app).
#####  **iOS**
```objective-c
#import "AEPAssurance.h"  
[AEPAssurance registerExtension];
```
#####  **Android:**
```java
import com.adobe.marketing.mobile.Assurance;
Assurance.registerExtension();
```
##### Starting the Assurance session:
```js
AEPAssurance.startSession(url, function(response) {  
  console.log("Success in starting AEPAssurance session");  
}, function(error){  
  console.log(error);  
});
```

## Running Tests
Install cordova-paramedic `https://github.com/apache/cordova-paramedic`
```bash
npm install -g cordova-paramedic
```
Run the tests
```
cordova-paramedic --platform ios --plugin . --verbose
```
```
cordova-paramedic --platform android --plugin . --verbose
```

## Sample App

A Cordova app for testing the Adobe SDK plugins is located at [https://github.com/adobe/cordova-acpsample](https://github.com/adobe/cordova-acpsample). The app is configured for both iOS and Android platforms.  

## Additional Cordova Plugins

Below is a list of additional Cordova plugins from the AEP SDK suite:

| Extension | GitHub | npm |
|-----------|--------|-----|
| Core SDK | https://github.com/adobe/cordova-acpcore | [![npm](https://img.shields.io/npm/v/@adobe/cordova-acpcore)](https://www.npmjs.com/package/@adobe/cordova-acpcore)
| Adobe Analytics | https://github.com/adobe/cordova-acpanalytics | [![npm](https://img.shields.io/npm/v/@adobe/cordova-acpanalytics)](https://www.npmjs.com/package/@adobe/cordova-acpanalytics)
| Places | https://github.com/adobe/cordova-acpplaces | [![npm](https://img.shields.io/npm/v/@adobe/cordova-acpplaces)](https://www.npmjs.com/package/@adobe/cordova-acpplaces)

## Contributing

Looking to contribute to this project? Please review our [Contributing guidelines](.github/CONTRIBUTING.md) prior to opening a pull request.  

We look forward to working with you!

## Licensing
This project is licensed under the Apache V2 License. See [LICENSE](LICENSE) for more information.
