# sms-api
SMS API is build for Samaya Technology SMS - Bulk SMS Application For Marketing

Samaya Technology SMS API
Samaya Technology SMS API is build for Samaya Technology SMS - Bulk SMS Application For Marketing

Prerequisites
To run Samaya Technology SMS API you have to install Samaya Technology SMS Application on your server. For more details please visit: Samaya Technology SMS

php >=5.6
Samaya Technology SMS - Bulk SMS Application For Markting
Installing
Via Composer

composer require shamim/samayatech-sms-api 
And Via Bash

git clone https://github.com/samayatech/sms-api/.git
Usage
Step 1:
If install Samaya Technology SMS API using Git Clone then load your Samaya Technology SMS API Class file and Use namespace.

require_once 'src/Class_Samaya Technology_SMS_API.php';
use Samaya TechnologySMS\Samaya TechnologySMSAPI;
If install Samaya Technology SMS API using Composer then Require/Include autoload.php file in the index.php of your project or whatever file you need to use Samaya Technology SMS API classes:.

require 'vendor/autoload.php';
use Samaya TechnologySMS\Samaya TechnologySMSAPI;
Step 2:
set your API_KEY from https://mywebhost.com/sms-api/info (your application install url)

$api_key = 'YWRtaW46YWRtaW4ucGFzc3dvcmQ=';
Step 3:
Change the from number below. It can be a valid phone number or a String

$from = '9866875279';
Step 4:
the number we are sending to - Any phone number

$destination = '9866875279';
You have to must include Country code at beginning of the phone number.

Step 5:
Replace your Install URL like https://mywebhost.com/sms/api with https://yourhost.com/demo/ sms/api is mandatory on your install url

$url = 'https://yourhost/sms/api';
// SMS Body

$sms = 'test message from Samaya Technology SMS';
// Unicode SMS

$unicode = '0'; //For plain message
$unicode = '1'; //For Unicode message
// Create SMS Body for request

$sms_body = array(
    'api_key' => $api_key,
    'to' => $destination,
    'from' => $from,
    'sms' => $sms,
    'unicode' => $unicode,
);
Step 6:
Instantiate a new Samaya Technology SMS API request

$client = new Samaya TechnologySMSAPI();
Send SMS
Finally send your sms through Samaya Technology SMS API

$response = $client->send_sms($sms_body, $url);
Get Inbox
Get your all message

$get_inbox=$client->get_inbox($api_key,$url);
Get Balance
Get your account balance

$get_balance=$client->check_balance($api_key,$url);
Response
Samaya Technology SMS API return response with json format, like:

{"code":"ok","message":"Successfully Send"}
Status Code
Status	Message
ok	Successfully Send
100	Bad gateway requested
101	Wrong action
102	Authentication failed
103	Invalid phone number
104	Phone coverage not active
105	Insufficient balance
106	Invalid Sender ID
