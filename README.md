# react-native-file-transfer
This little plugin lets you easily upload files from your photo library to a web server using a standard `multipart/form-data` POST request. It **does not** incorporate the tranfer of photo library images data from Objective-C to JavaScript (which is slow). The request are being made directly from Objective-C.
# installation
`npm install react-native-file-transfer`
then just add the `RCTFileTransfer.m` file to your xcode project
# how to use it
When you properly add the `RCTFileTransfer.m` file to your xcode project you may now use it in the js files. Example usage:
```javascript
var { NativeMethods } = require('react-native');
var obj = {
    path, // either an 'assets-library' url (for files from photo library) or an image dataURL
    uploadUrl,
    fileName,
    mimeType,
    data: {
        // whatever properties you wish to send in the request
        // along with the uploaded file
    }
};
NativeMethods.FileTransfer.upload(obj, res => {
    // handle response
    // it is an object with 'status' and 'data' properties
    // if the file path protocol is not supported the status will be 0
    // and the request won't be made at all
});
```
**pull-requests welcome**