# send-json-data-in-ajax-request-in-react-js

i have spent lot of time to send json data in ajax request in react js and gettting the data in php server. Finally i have solved this problem

# In React js Ajax

fetch(url, {
  method: 'POST', // or 'PUT'
  body: JSON.stringify(fieldsList), // data can be `string` or {object}!
  headers:{
    'Content-Type': 'application/json'
  }
})
.then(result => {
	console.log(result);
	return result.json();
})
.then(jsonResult => {
console.log(jsonResult);
});

# getting in php

header("Access-Control-Allow-Origin: *");
header("Access-Control-Allow-Headers: Origin, X-Requested-With, Content-Type, Accept");


$postData = file_get_contents("php://input");
$postData=json_decode($postData);
echo "<pre>";
print_r($postData);
