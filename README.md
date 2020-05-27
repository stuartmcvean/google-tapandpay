cordova-android-googlepay-issuer
============================================

Cordova/Phonegap plugin for Android for Google Pay - Issuers


# Requirements

This plugin requires `cordova@7.1+` (CLI) and `cordova-android@8+` (Android platform).

# Installation

    cordova plugin add https://github.com/andregrillo/google-tapandpay.git

# How to use

```javascript
    declare var GooglePayIssuer: any;

    var googlePay = new GooglePayIssuer();

    GooglePayIssuer.prototype.getActiveWalletID((walletID)=>{
        console.log(walletID);
    },(error)=>{
        console.log(error);
    });
    
```

# Functions

### GetTokenStatus
Return the token status for a token in the active wallet.

```javascript
    let tsp = "VISA";
    let tokenReferenceId = "dP4Pwaq7WQY:APA9";

    GooglePayIssuer.prototype.getTokenStatus(tsp,tokenReferenceId,onSuccess,onError);
```

### GetEnvironment
Return the current environment Google Pay is configured to use.

```javascript
    GooglePayIssuer.prototype.getEnvironment(onSuccess,onError);
```

### GetActiveWalletID
Returns the Wallet ID of the active wallet. If there is no active wallet, a error is throw.

```javascript
    GooglePayIssuer.prototype.getActiveWalletID(onSuccess,onError);
```

### GetStableHardwareId
Returns the stable hardware ID of the device. Each physical Android device has a stable hardware ID which is consistent between wallets for a given device. This ID will change as a result of a factory reset.

```javascript
    GooglePayIssuer.prototype.getStableHardwareId(onSuccess,onError);
```

### PushProvision
Starts the push tokenization flow in which the issuer provides most or all card details needed for Google Pay to get a valid token. Tokens added using this method are added to the active wallet.

```javascript
    let opc = "eyJhb...0zfF20w";
    let tsp = "VISA";
    let clientName = "John Doe";
    let lastDigits = "1234";
    let address = {
        name:"John Doe",
        address: "St. Some Street",
        locality: "London",
        administrativeArea: "Sutton",
        countryCode:"UK",
        postalCode: "99999",
        phoneNumber: "9999999999"
    };
    GooglePayIssuer.prototype.pushProvision(opc,tsp,clientName,lastDigits,address,onSuccess,onError);
```   

# Credits
Thanks to [**Raphael Godoi**](https://github.com/raphagodoi) and [**Guilherme Rodrigues**](https://github.com/Guiles92)