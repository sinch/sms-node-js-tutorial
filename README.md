One of the teams at the TheNextWeb hackathon this past weekend was kind enough to open source a node module to send SMS with Sinch. (shoutout to Mihir and Mikhail!) Here's an example of how to use it:

````
var sinchAuth = require('sinch-auth');

var sinchSms = require('sinch-messaging');

var auth = sinchAuth("your-app-key", "your-app-secret");

sinchSms.sendMessage("+16507141052", "Hello world!");
````

The above script will print an ID for the SMS. It will look like this:

	{"MessageId":123456789}

You can use this ID to check the status of the SMS at any point like so...

	console.log(sinchSms.getStatus("123456789");

...which will give you a response like so:

	{"Status":"Successful"}

If you're interested in digging into the node modules for auth and sending SMS, you can find the source code on Github:

1. [sinch-auth](https://github.com/ChewTeaYeah/sinch-auth)

2. [sinch-messaging](https://github.com/ChewTeaYeah/sinch-messaging)


To get your own app key and secret, [sign up](https://www.sinch.com/dashboard/#/signup) for a Sinch account, and create a new app. To start, you will have $2 on your account to send some test messages. See SMS pricing by country here [www.sinch.com/pricing/sms-prices/](https://www.sinch.com/pricing/sms-prices/).