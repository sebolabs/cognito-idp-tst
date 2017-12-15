# cognito-idp-tst

**Story**
------
[Cognito Federated Identities with Google IdP — the simplest try-yourself tutorial](https://medium.com/@sebolabs/cognito-idp-google-tutorial-379fa08464)

**Configuration**
------

index.html

```
<meta name="google-signin-client_id" content="XXXXXXXXXX-XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX.apps.googleusercontent.com">
```

scripts.js

```
function signInCallback(authResult) {
  if (authResult['access_token']) {
    
    // add google access token to Cognito credentials login map
    AWS.config.region = 'XX-XXXX-X';
    AWS.config.credentials = new AWS.CognitoIdentityCredentials({
      IdentityPoolId: 'XX-XXXX-X:XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX',
      Logins: {
        'accounts.google.com': authResult['id_token']
      }
    });
[...]
```
