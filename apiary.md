FORMAT: 1A


# CSR Health care

<p>Corporate social responsibility <code>(CSR)</code> is a health care EMR <code>(Electronic Medical Records)</code> Software, Implementing Clinical concept with Android Tablet.</p>
<br/><p>An EMR contains the standard medical and clinical data gathered in one provider�s office. Electronic health records (EHR) go beyond the data collected in the provider�s office and include a more comprehensive patient history.</p>

## Server information

<p>Server</p>
<p> PHP <code>5.3 </code> and mysql <code>5.6</code>.</p>
<p>For example we use <code>android retrofit</code> to connect to this <code>REST API</code>.</p>

<em><small>**Note: This content is currently DRAFT and under development**</small></em>

# Overview

<ul>
<li><p>All Api access is at <code>https://www.sitename.com/xxxxxx/interface/api/v1/</code></p></li>
<li><p>All Api access is based on  API Mode such as <code>�development�</code>, <code>�test�</code>, and <code>�production�</code></p><br/><br/>
<p>- e.g: <code>API development Mode</code> <br/><br/> <code>https://www.sitename.com/xxxxxxx_dev/interface/api/v1/</code><br/><br/>
<code>API test Mode</code><br/><br/>  <code>https://www.sitename.com/xxxxxxx/interface/api/v1/</code></p></li>
<li><p>All data response as <code>JSON OBJECT</code>.</p></li>
<li><p>Client can send any kind of data with supportable format of header content-type</p></li>
</ul>

##Requests

<p>All API methods are described by a HTTP method (e.g. GET, POST, PUT, DELETE) and a URL endpoint.</p>
<p>For example: <code>REQUEST_METHOD:</code>  <code>POST</code>, <code>URL pattern</code>   <code>/User/login</code> Requests data is required </p>
<p>- e.g.: <code>User login </code> - it must be supplied in the request body as a <code>JSON object</code> and the <code>Content-Type: application/json</code> header needs to be set.</p>
<p>Hence:<br/><pre><code>if request supplied in the request body as a  JSON object  and the  Content-Type: application/json  header needs to be set.</code></pre></p>
 
<em>**Note: The request content and content-type on header should be same.**</em>

##Responses

<p>Responses are returned in <code>JSON format;</code> every response will have the <code>Content-Type: application/json</code> header set.</p>

<h3>Response Status</h3>

<p>All responses from the API use a standard HTTP status code. Common status codes you will see while using the API are:</p>
<ul>
<li><p><code>2xx </code>  <code>Successful</code>- the request was successful and a resource was created</p></li>
<li><p><code>200 </code>  <code>OK </code>- the request completed successfully (POST calls return 201 instead)</p><br/><p><strong>Status Code: 200 - OK</strong><br/> Standard response for successful HTTP requests. The actual response will depend on the request method used. In a GET request, the response will contain an entity corresponding to the requested resource. In a POST request the response will contain an entity describing or containing the result of the action.</p></li>
<li><p><code>201 </code>  <code>Created </code>- the request was successful and a resource was created</p></li>
<li><p><code>3xx </code>  <code>Redirection </code>- Server redirect if it's need. </p></li>
<li><p><code>301 </code>  <code>Moved Permanently</code>- Server redirect if it's need. </p></li>
<li><p><code>4xx </code>  <code>Client Error </code>- the request could not be understood by server or client was missing required parameters. </p></li>
<li><p><code>400 </code>  <code>Bad Request </code>- the request could not be understood or was missing required parameters. </p></li>
<li><p><code>401 </code>  <code>Unauthorized </code>- authentication failed or user doesn't have permissions for requested operation. </p></li>
<li><p><code>412 </code>  <code> Precondition Failed</code>-The server does not meet one of the preconditions that the requester put on the request.</p></li>
<li><p><code>403 </code>  <code>Forbidden </code>-  access denied, currently authorized user doesn't have access to the resource. </p></li>
<li><p><code>404 </code>  <code>Not Found </code>-  resource was not found. </p></li>
<li><p><code>405 </code>  <code>Method Not Allowed </code>-  requested method is not supported for resource. </p></li>
<li><p><code>5xx </code>  <code>Server Error </code>- something went wrong serverside. Likely a transient issue, but if you get repeated 5XX errors, please contact support. </p></li>
</ul>

## Operations

<p>We use RESTful verbs for all operations and methods.</p>
<table>
<thead><tr><th>Verb</th><th>Description</th></tr></thead>
<tbody>
<tr><td><code>GET</code></td><td>Used to select one or more items. Success returns 200 status code with json result item(s) in body.</td></tr>
<tr><td><code>POST</code></td><td>Used to create a new item. Success returns 201 status code with newly created json item in body.</td></tr>
<tr><td><code>PUT</code></td><td>Used to update an item. Success returns 200 status code with updated json item in body.</td></tr>
<tr><td><code>DELETE</code></td><td>Used to delete an item. Success returns 204 status code with no body.</td></tr>
</tbody>
</table>

## Query Parameters

<p>You can add query parameters to your requests, most commonly for <code>GET</code> requests.</p>
<p><em>Example: http://www.sitename/com/api/v1/plist?page=2&amp;pageSize=10 will return page 2, of 10 results per page.</em></p>

# Authentication

<p>All User need to Login their application before getting started.<p>
<p>Login credential such as : <code>Username</code> & <code>Password</code><p>
<p>After Successful Login in to server, server send an unique UUID for the User, After login Every request needs a valid UUID key for request Services</p>

<table style="width: 100%; margin: 12px 0 0 0;">
<tbody>
<tr><td colspan="2"><strong>After Successful Login Request Required Header Parameters</strong></td></tr>
<tr><td ><code>auth</code></td><td><code>xxxxx</code></td></tr>
<tr><td ><code>auth_key</code></td><td><code>xxxxx</code></td></tr>
</tbody>
</table>

# Group API

<p><em>Notes related resources of the **API**</em></p>
<p>Every Request need a <code>REQUEST METHOD</code> , <code>specified URL</code> and required <code>request data</code></p>

# Group User 

<p>User login attributes:</p>

<ul >
<li ><p><strong>Request attributes</strong></p></li>
<li ><p class="tocColumnItemText"><code><strong>authUser</strong></code> <code>string</code> - unique name of the User in the system</p></li>
<li ><p class="tocColumnItemText"><code><strong>authPass</strong></code> <code>string</code> - base64_encode of password used in this filed for crypt.</p></li>
<li ><p><strong>Response attributes</strong></p></li>
<li ><p class="tocColumnItemText"><code><strong>StatusCode</strong></code> <code>mixed</code> - Server return header message based on credential.</p></li>
<li ><p class="tocColumnItemText"><code><strong>Message</strong></code> <code>string</code> - Server return message based on credential.</p></li>
<li ><p class="tocColumnItemText"><code><strong>authUser</strong></code> <code>string</code> - Authenticated unique name of the User in the system.</p></li>
<li ><p class="tocColumnItemText"><code><strong>Username</strong></code> <code>string</code> - Authenticated Name of the User in the system.</p></li>
<li ><p class="tocColumnItemText"><code><strong>Facility</strong></code> <code>string</code> - Facility of the current User.</p></li>
<li ><p class="tocColumnItemText"><code><strong>authUserID</strong></code> <code>string</code> - Unique UUID for the current User.</p></li>
<li ><p class="tocColumnItemText"><code><strong>setControllerlevels</strong></code> <code>array of object</code> - Current User having Generic Access Control Lists.</p></li>
</ul>


##User Login on GET [/user/login?authUser=admin&authPass=YWRtaW5sc2FwcEAyMDE0]

<pre class="json">
<code><span>Request method : GET</span>
<span>Resource URI : /user/:login</span>
<span>Request Content type :application/json</span>
<span>Request Query:authUser=admin&authPass=YWRtaW5sc2FwcEAyMDE0</span>
<span>For example<br/>Request URL: https://yourdomain.com/User/:login?authUser=admin&authPass=YWRtaW5sc2FwcEAyMDE0</span></code>
</pre>

### User Login on GET method [GET]

+ Response 200 (application/json)

    + Body
    
                {"StatusCode":200,"Message":"Login Successful!","authUser":"raj","Username":"Rajesh Testing","Facility":"Malar Hospital","authUserID":"E1BF1EF6-208B-9AAF-4A21-4AAA4E3D7B76","setControllerlevels":[{"ControllerName":"Clinicians"},{"ControllerName":"Front Office"},{"ControllerName":"Paramedical"},{"ControllerName":"Pharmacy"}]}
        
+ Parameters
    + login (required , `login?` , `string`) ... this is used as a key.
    + authUser (required , `admin` , `string`) ... name of the User in the system.
    + authPass (required , `YWRtaW5sc2FwcEAyMDE0` , `string`) ... unique name of the User key  encripted base64_encode value to be used.
    

##User Login on POST [/user/login]

<pre class="json">
<code><span> Request method : POST</span>
<span>Resource URI : /user/login</span>
<span>Request Content type :application/json</span>
<span>Request variables : {"authUser":"xxxxx","authPass":"xxxxx"}</span></code>
</pre>



### User Login on POST method  [POST]

+ Request (application/json)

    + Body
    
            {"authUser":"admin","authPass":"YWRtaW5sc2FwcEAyMDE0"}

+ Response 200 (application/json)

    + Body

            {"StatusCode":200,"Message":"Login Successful!","authUser":"raj","Username":"Rajesh Testing","Facility":"Malar Hospital","authUserID":"E1BF1EF6-208B-9AAF-4A21-4AAA4E3D7B76","setControllerlevels":[{"ControllerName":"Clinicians"},{"ControllerName":"Front Office"},{"ControllerName":"Paramedical"},{"ControllerName":"Pharmacy"}]}


+ Request (application/x-www-form-urlencoded)

        authUser=admin&authPass=YWRtaW5sc2FwcEAyMDE0

+ Response 201 (application/json)
    
    + Body

            {"StatusCode":200,"Message":"Login Successful!","authUser":"raj","Username":"Rajesh Testing","Facility":"Malar Hospital","authUserID":"E1BF1EF6-208B-9AAF-4A21-4AAA4E3D7B76","setControllerlevels":[{"ControllerName":"Clinicians"},{"ControllerName":"Front Office"},{"ControllerName":"Paramedical"},{"ControllerName":"Pharmacy"}]}

## User Logout on POST [/user/logout]

<pre class="json">
<code><span> Request method : POST</span>
<span>Resource URI : /user/logout</span>
<span>Request Content type :application/json</span></code>
</pre>

<p>User Logout attributes:</p>

<ul>
<li><p class="tocColumnItemText"></code><strong>auth_key</strong></code> <code>string</code> - unique UUID of the User in the system , it is to be passed on Headers</p></li>
<li><p class="tocColumnItemText"></code><strong>auth</strong></code> <code>string</code> - authenticate user stay on login to request and retrieve data from server  or logout, it is to be passed on Headers</p></li>
</ul>

<table style="width: 100%; margin: 12px 0 0 0;">
<tbody>
<tr><td colspan="2"><strong>Required Header Parameters</strong></td></tr>
<tr><td ></code>auth</code></td><td><code>logout</code></td></tr>
<tr><td ></code>auth_key</code></td><td><code>91B0B365-7BF7-4724-FEC3-4848E07312B5</code></td></tr>
</tbody>
</table>

### User Logout on POST [POST]

+ Request (application/json)

    + Headers
    
            auth: logout
            auth_key: 91B0B365-7BF7-4724-FEC3-4848E07312B5
       
+ Response 200 (application/json)
    
    + Body

            {"StatusCode":200,"Message":"Logout Successful."}

# Group Patient Data collection

<p>Common attributes:</p>
<ul>
<li><p class="tocColumnItemText"><code><strong>auth_key</strong></code> <code>string</code> - unique UUID of the User in the system , it is to be passed on Headers</p></li>
<li><p class="tocColumnItemText"><code><strong>auth</strong></code> <code>string</code> - authenticate user stay on login to request and retrieve data from server  or logout, it is to be passed on Headers</p></li>
<li><p class="tocColumnItemText"><code><strong>StatusCode</strong></code> <code>200</code> - Client request with REQUEST_METHOD , URL pattern and Parameters to the server, Server response as an success object .</p></li>
<li><p class="tocColumnItemText"><code><strong>StatusCode</strong></code> <code>4xx, 5xx - x can be any number between 0-9</code> -  Client request with invalid REQUEST_METHOD or invalid URL pattern or invalid Parameters to the server, Server response as an failure object .</p></li>
</ul>

<table style="width: 100%; margin: 12px 0 0 0;">
<tbody>
<tr><td colspan="2"><strong>Required Header Parameters</strong></td></tr>
<tr><td ><code>auth</code></td><td><code>login</code></td></tr>
<tr><td ><code>auth_key</code></td><td><code>UUID</code></td></tr>
</tbody>
</table>

## Patient Register Form [/demographics/form]



<pre class="json">
<code><span> Request method : POST<span>
<span>Resource URI : /demographics/form<span>
<span>Request Content type :application/json<span></code>
</pre>

### Patient Register Form  [POST]

+ Request (application/json)

    + Headers
    
            auth: login
            auth_key: 91B0B365-7BF7-4724-FEC3-4848E07312B5
       
+ Response 200 (application/json)
    
    + Body

                {"StatusCode":200,"form_pubpid":{"label":"Biometric","required":1},"form_fname":{"label":"First Name","required":1},"form_lname":{"label":"Last name","required":1},"form_DOB":{"label":"Date of birth","required":1},"form_age":{"label":"Age","required":1},"form_sex":{"label":"sex","options":{"Unassigned":"Unassigned","Female":"Female","Male":"Male"},"required":1},"form_status":{"label":"Status","options":{"Unassigned":"Unassigned","married":"Married","single":"Single","divorced":"Divorced","widowed":"Widowed","separated":"Separated","domestic partner":"Domestic Partner"},"required":1},"form_photo":{"label":"Photograph","required":1},"form_genericname1":{"label":"Blood Group","options":{"Unassigned":"Unassigned","O+":"O+","A+":"A+","B+":"B+","AB+":"AB+","O-":"O-","A-":"A-","B-":"B-","AB-":"AB-"},"required":0},"form_street":{"label":"Door no, Street name","required":0},"form_genericval2":{"label":"Village","required":0},"form_genericval1":{"label":"Taluk","required":0},"form_city":{"label":"City","required":0},"form_genericname2":{"label":"District","required":1},"form_state":{"label":"State","options":{"Unassigned":"Unassigned","AN":"Andaman and Nicobar Islands","AP":"Andhra Pradesh","AR":"Arunachal Pradesh","AS":"Assam","BI":"Bihar","CH":"Chandigarh","DA":"Dadra and Nagar Haveli","DM":"Daman and Diu","DE":"Delhi","GO":"Goa","GU":"Gujarat","HA":"Haryana","HP":"Himachal Pradesh","JA":"Jammu and Kashmir","KA":"Karnataka","KE":"Kerala","LI":"Lakshadweep Islands","MP":"Madhya Pradesh","MA":"Maharashtra","MN":"Manipur","ME":"Meghalaya","MI":"Mizoram","NA":"Nagaland","OR":"Orissa","PO":"Pondicherry","PU":"Punjab","RA":"Rajasthan","SI":"Sikkim","TN":"Tamil Nadu","TR":"Tripura","UP":"Uttar Pradesh","WB":"West Bengal"},"required":1},"form_postal_code":{"label":"Pin code","required":1},"form_phone_cell":{"label":"Mobile Number","required":0},"form_phone_home":{"label":"Land line","required":0},"form_email":{"label":"Contact Email","required":0},"form_guardiansname":{"label":"Emergency Contact Name","required":0},"form_contact_relationship":{"label":"Emergency Contact RelationShip","required":0},"form_phone_contact":{"label":"Emergency Contact Phone","required":0},"form_occupation":{"label":"Occupation","required":1},"form_em_name":{"label":"Employer Name","required":1},"form_em_street":{"label":"Employer Address","required":1},"form_usertext11":{"label":"Risk Factors","checkbox":{"form_usertext11[vv]":"Varicose Veins","form_usertext11[ht]":"Hypertension","form_usertext11[db]":"Diabetes","form_usertext11[sc]":"Sickle Cell","form_usertext11[fib]":"Fibroids","form_usertext11[pid]":"PID (Pelvic Inflammatory Disease)","form_usertext11[mig]":"Severe Migraine","form_usertext11[hd]":"Heart Disease","form_usertext11[str]":"Thrombosis\/Stroke","form_usertext11[hep]":"Hepatitis","form_usertext11[gb]":"Gall Bladder Condition","form_usertext11[br]":"Breast Disease","form_usertext11[dpr]":"Depression","form_usertext11[all]":"Allergies","form_usertext11[inf]":"Infertility","form_usertext11[ast]":"Asthma","form_usertext11[ep]":"Epilepsy","form_usertext11[cl]":"Contact Lenses","form_usertext11[coc]":"Contraceptive Complication (specify)","form_usertext11[oth]":"Other (specify)"},"required":0},"form_userarea11":{"label":"Risk Factors Others","required":0},"form_exams":{"labels":{"form_exams[brs]":{"label":"Breast Exam","radio":{"radio_exams[brs][1]":"N\/A","radio_exams[brs][2]":"Normal","radio_exams[brs][3]":"Abnormal"}},"form_exams[cec]":{"label":"Cardiac Echo","radio":{"radio_exams[cec][1]":"N\/A","radio_exams[cec][2]":"Normal","radio_exams[cec][3]":"Abnormal"}},"form_exams[ecg]":{"label":"ECG","radio":{"radio_exams[ecg][1]":"N\/A","radio_exams[ecg][2]":"Normal","radio_exams[ecg][3]":"Abnormal"}},"form_exams[gyn]":{"label":"Gynecological Exam","radio":{"radio_exams[gyn][1]":"N\/A","radio_exams[gyn][2]":"Normal","radio_exams[gyn][3]":"Abnormal"}},"form_exams[mam]":{"label":"Mammogram","radio":{"radio_exams[mam][1]":"N\/A","radio_exams[mam][2]":"Normal","radio_exams[mam][3]":"Abnormal"}},"form_exams[phy]":{"label":"Physical Exam","radio":{"radio_exams[phy][1]":"N\/A","radio_exams[phy][2]":"Normal","radio_exams[phy][3]":"Abnormal"}},"form_exams[pro]":{"label":"Prostate Exam","radio":{"radio_exams[pro][1]":"N\/A","radio_exams[pro][2]":"Normal","radio_exams[pro][3]":"Abnormal"}},"form_exams[rec]":{"label":"Rectal Exam","radio":{"radio_exams[rec][1]":"N\/A","radio_exams[rec][2]":"Normal","radio_exams[rec][3]":"Abnormal"}},"form_exams[sic]":{"label":"Sigmoid\/Colonoscopy","radio":{"radio_exams[sic][1]":"N\/A","radio_exams[sic][2]":"Normal","radio_exams[sic][3]":"Abnormal"}},"form_exams[ret]":{"label":"Retinal Exam","radio":{"radio_exams[ret][1]":"N\/A","radio_exams[ret][2]":"Normal","radio_exams[ret][3]":"Abnormal"}},"form_exams[flu]":{"label":"Flu Vaccination","radio":{"radio_exams[flu][1]":"N\/A","radio_exams[flu][2]":"Normal","radio_exams[flu][3]":"Abnormal"}},"form_exams[pne]":{"label":"Pneumonia Vaccination","radio":{"radio_exams[pne][1]":"N\/A","radio_exams[pne][2]":"Normal","radio_exams[pne][3]":"Abnormal"}},"form_exams[ldl]":{"label":"LDL","radio":{"radio_exams[ldl][1]":"N\/A","radio_exams[ldl][2]":"Normal","radio_exams[ldl][3]":"Abnormal"}},"form_exams[hem]":{"label":"Hemoglobin","radio":{"radio_exams[hem][1]":"N\/A","radio_exams[hem][2]":"Normal","radio_exams[hem][3]":"Abnormal"}},"form_exams[psa]":{"label":"PSA","radio":{"radio_exams[psa][1]":"N\/A","radio_exams[psa][2]":"Normal","radio_exams[psa][3]":"Abnormal"}}},"label":"Exams\/Tests","required":0},"form_text_tobacco":{"label":"Tobacco Type","required":0},"form_tobacco":{"label":"Tobacco","options":{"Unassigned":"Unassigned","1":"Current every day smoker","2":"Current some day smoker","3":"Former smoker","4":"Never smoker","5":"Smoker, current status unknown","9":"Unknown if ever smoked","15":"Heavy tobacco smoker","16":"Light tobacco smoker"},"radio":{"radio_tobacco[current]":"Current","radio_tobacco[quit]":"Quit","radio_tobacco[never]":"Never","radio_tobacco[not_applicable]":"N\/A"},"date_tobacco":"choose a date","required":0},"form_coffee":{"label":"Coffee","radio":{"radio_coffee[current]":"Current","radio_coffee[quit]":"Quit","radio_coffee[never]":"Never","radio_coffee[not_applicable]":"N\/A"},"date_coffee":"choose a date","required":0},"form_alcohol":{"label":"Alcohol","radio":{"radio_alcohol[current]":"Current","radio_alcohol[quit]":"Quit","radio_alcohol[never]":"Never","radio_alcohol[not_applicable]":"N\/A"},"date_alcohol":"choose a date","required":0},"form_recreational_drugs":{"label":"Recreational Drugs","radio":{"radio_recreational_drugs[current]":"Current","radio_recreational_drugs[quit]":"Quit","radio_recreational_drugs[never]":"Never","radio_recreational_drugs[not_applicable]":"N\/A"},"date_recreational_drugs":"choose a date","required":0},"form_counseling":{"label":"Counselling","radio":{"radio_counseling[current]":"Current","radio_counseling[quit]":"Quit","radio_counseling[never]":"Never","radio_counseling[not_applicable]":"N\/A"},"date_counseling":"choose a date","required":0},"form_exercise_patterns":{"label":"Exercise Patterns","radio":{"radio_exercise_patterns[current]":"Current","radio_exercise_patterns[quit]":"Quit","radio_exercise_patterns[never]":"Never","radio_exercise_patterns[not_applicable]":"N\/A"},"date_exercise_patterns":"choose a date","required":0},"form_hazardous_activities":{"label":"Hazardous Activities","radio":{"radio_hazardous_activities[current]":"Current","radio_hazardous_activities[quit]":"Quit","radio_hazardous_activities[never]":"Never","radio_hazardous_activities[not_applicable]":"N\/A"},"date_hazardous_activities":"choose a date","required":0},"form_userarea12":{"label":"Life style Others","required":0},"form_relatives_cancer":{"label":"Cancer","required":0},"form_relatives_tuberculosis":{"label":"Tuberculosis","required":0},"form_relatives_diabetes":{"label":"Diabetes","required":0},"form_relatives_high_blood_pressure":{"label":"High Blood Pressure","required":0},"form_relatives_heart_problems":{"label":"Heart Problems","required":0},"form_relatives_stroke":{"label":"Stroke","required":0},"form_relatives_epilepsy":{"label":"Epilepsy","required":0},"form_relatives_mental_illness":{"label":"Mental Illness","required":0},"form_relatives_suicide":{"label":"Suicide","required":0},"form_history_father":{"label":"Father `s Name","required":0},"form_history_mother":{"label":"Mothers `s Name","required":0},"form_history_siblings":{"label":"Siblings","required":0},"form_history_spouse":{"label":"Spouse","required":0},"form_history_offspring":{"label":"Child","required":0}}
    
##  New Patient Register [/demographics/new]

<pre class="json">
<code><span> Request method : POST<span>
<span>Resource URI : /demographics/new<span>
<span>Request Content type :application/json<span></code>
</pre>

<table style="width: 100%; margin: 12px 0 0 0;">
<tbody>
<tr><td colspan="2"><strong>Required Header Parameters</strong></td></tr>
<tr><td ><code>auth</code></td><td><code>login</code></td></tr>
<tr><td ><code>auth_key</code></td><td><code>91B0B365-7BF7-4724-FEC3-4848E07312B5</code></td></tr>
</tbody>
</table>

<p>Data Collection Attributes:</p>
<table style="width: 100%; margin: 12px 0 0 0;">
<thead><tr><th> Attributes </th><th colspan=2> Description </th><th>data type </th></tr></thead>
<tbody>
<tr><td ><code>form_pubpid</code> <span style="color:red">*</span> </td><td colspan=2>Biometric ( Finger print) Unique value or system will generate unique value.</td><td> <code>alphanumeric</code></td></tr>
<tr><td ><code>form_fname</code> <span style="color:red">*</span> </td><td colspan=2>Patient first name </td><td><code>alpha</code></td></tr>
<tr><td ><code>form_lname</code> <span style="color:red">*</span> </td><td colspan=2>Patient last name  </td><td><code>alpha</code></td></tr>
<tr><td ><code>form_DOB/form_age</code>  <span style="color:red">*</span> </td><td colspan=2>Patient date of birth or age   </td><td><code> Supported input date formats are:
mm/dd/yyyy ,   mm/dd/yy   (assumes 20yy for yy < 10, else 19yy)
yyyy/mm/dd ,  also mm-dd-yyyy, and mm.dd.yyyy, Age is an 3 digit Numeric Value.</code></td></tr>
<tr><td ><code>form_sex</code> <span style="color:red">*</span> </td><td colspan=2>Patient sex info   </td><td><code>option</code></td></tr>
<tr><td ><code>form_status</code> <span style="color:red">*</span> </td><td colspan=2>Patient marital status   </td><td><code>option</code></td></tr>
<tr><td ><code>form_photo</code>  <span style="color:red">*</span> </td><td colspan=2>Patient Photograph   </td><td><code>base64_encode file format</code></td></tr>
<tr><td ><code>form_genericname1</code></td><td colspan=2>Patient Blood Group  </td><td><code>option</code></td></tr>
<tr><td colspan="3">&nbsp;<h4>Address</h4></td></tr>
<tr><td ><code>form_street</code></td><td colspan=2>Patient Address Door no, Street name  </td><td><code>string</code></td></tr>
<tr><td ><code>form_genericval2</code></td><td colspan=2>Patient Address Village  </td><td><code>string</code></td></tr>
<tr><td ><code>form_genericval1</code></td><td colspan=2>Patient Address Taluk   </td><td><code>string</code></td></tr>
<tr><td ><code>form_city</code></td><td colspan=2>Patient Address  City </td><td><code>string</code></td></tr>
<tr><td ><code>form_genericname2</code> <span style="color:red">*</span> </td><td colspan=2>Patient Address  District </td><td><code>string</code></td></tr>
<tr><td ><code>form_state</code> <span style="color:red">*</span> </td><td colspan=2>Patient Address  State </td><td><code>option</code></td></tr>
<tr><td ><code>form_postal_code</code> <span style="color:red">*</span> </td><td colspan=2>Patient Address Pin code  </td><td><code>numeric</code></td></tr>
<tr><td colspan="3">&nbsp;<h4>Contact</h4></td></tr>
<tr><td ><code>form_phone_cell</code></td><td colspan=2>Patient Mobile Number  </td><td></td><td><code>numeric</code></td></tr>
<tr><td ><code>form_phone_home</code></td><td colspan=2>Patient Land line   </td><td><code>numeric</code></td></tr>
<tr><td ><code>form_email</code></td><td colspan=2>Patient Contact Email   </td><td><code>email address format</code></td></tr>
<tr><td colspan="3">&nbsp;<h4>Emergency</h4></td></tr>
<tr><td ><code>form_guardiansname</code></td><td colspan=2>Patient Emergency Contact Name  </td><td><code>numeric</code></td></tr>
<tr><td ><code>form_contact_relationship</code></td><td colspan=2>Patient Emergency Contact RelationShip   </td><td><code>string</code></td></tr>
<tr><td ><code>form_phone_contact</code></td><td colspan=2>Patient Emergency Contact Phone   </td><td><code>numeric</code></td></tr>
<tr><td colspan="3">&nbsp;<h4>Employer with </h4></td></tr>
<tr><td ><code>form_occupation</code> <span style="color:red">*</span> </td><td colspan=2>Patient Occupation   </td><td> <code>alphanumeric</code></td></tr>
<tr><td ><code>form_em_name</code> <span style="color:red">*</span> </td><td colspan=2>Patient Employer Name  </td><td><code>string</code></td></tr>
<tr><td ><code>form_em_street</code> <span style="color:red">*</span> </td><td colspan=2>Patient Employer Address   </td><td> <code>string</code></td></tr>
<tr><td colspan="3">&nbsp;<h4>Risk</h4> </td></tr>
<tr><td ><code>form_usertext11</code></td><td colspan=2>Risk Factors  </td><td><code>array of risk factors</code></td></tr>
<tr><td ><code>form_userarea11</code></td><td colspan=2>Risk Factors Others  </td><td><code>array</code></td></tr>
<tr><td ><code>form_exams</code></td><td colspan=2>Exams/Tests  </td><td> <code>array contain  Exams/Tests  name  and result </code></td></tr>
<tr><td ><code>radio_exams</code></td><td colspan=2>Exams/Tests options  </td><td><code>array contain  Exams/Tests options  </code></td></tr>
<tr><td colspan="3">&nbsp;<h4>Life style</h4></td></tr>
<tr><td ><code>form_text_tobacco</code></td><td colspan=2>Tobacco Type   </td><td> <code>string</code></td></tr>
<tr><td ><code>form_tobacco</code></td><td colspan=2>Tobacco   </td><td> <code>array contain  frequency of usage and status if quit on date.</code></td></tr>
<tr><td ><code>form_coffee</code></td><td colspan=2>Coffee   </td><td> <code>array contain status if quit on date.</code></td></tr>
<tr><td ><code>form_alcohol</code></td><td colspan=2>Alcohol   </td><td><code>array contain status if quit on date.</code></td></tr>
<tr><td ><code>form_recreational_drugs</code></td><td colspan=2>Recreational Drugs   </td><td><code>array contain status if quit on date.</code></td></tr>
<tr><td ><code>form_counseling</code></td><td colspan=2>Counselling   </td><td> <code>array contain status if quit on date.</code></td></tr>
<tr><td ><code>form_exercise_patterns</code></td><td colspan=2>Exercise Patterns  </td><td> <code>array contain status if quit on date.</code></td></tr>
<tr><td ><code>form_hazardous_activities</code></td><td colspan=2>Hazardous Activities  </td><td> <code>array contain status if quit on date.</code></td></tr>
<tr><td ><code>form_userarea12</code></td><td colspan=2>Life style Others  </td><td><code>string</code></td></tr>
<tr><td colspan="3">&nbsp; <h4>Relatives </h4></td></tr>
<tr><td ><code>form_relatives_cancer</code></td><td colspan=2>Cancer   </td><td><code>string</code></td></tr>
<tr><td ><code>form_relatives_tuberculosis</code></td><td colspan=2>Tuberculosis  </td><td> <code>string</code></td></tr>
<tr><td ><code>form_relatives_diabetes</code></td><td colspan=2>Diabetes   </td><td> <code>string</code></td></tr>
<tr><td ><code>form_relatives_heart_problems</code></td><td colspan=2>High Blood Pressure  </td><td><code>string</code></td></tr>
<tr><td ><code>form_relatives_stroke</code></td><td colspan=2>Stroke   </td><td> <code>string</code></td></tr>
<tr><td ><code>form_relatives_epilepsy</code></td><td colspan=2>Epilepsy  </td><td><code>string</code></td></tr>
<tr><td ><code>form_relatives_mental_illness</code></td><td colspan=2>Mental Illness  </td><td> <code>string</code></td></tr>
<tr><td ><code>form_relatives_suicide</code></td><td colspan=2>Suicide   </td><td> <code>string</code></td></tr>
<tr><td colspan="3">&nbsp; <h4>Biological History</h4> </td></tr>
<tr><td ><code>form_history_father</code></td><td colspan=2>Father's Name   </td><td> <code>string</code></td></tr>
<tr><td ><code>form_history_mother</code></td><td colspan=2>Mother's Name  </td><td> <code>string</code></td></tr>
<tr><td ><code>form_history_siblings</code></td><td colspan=2>Siblings   </td><td> <code>string</code></td></tr>
<tr><td ><code>form_history_spouse</code></td><td colspan=2>Spouse   </td><td> <code>string</code></td></tr>
<tr><td ><code>form_history_offspring</code></td><td colspan=2>Child   </td><td> <code>string</code></td></tr>
</tbody></table>

### New Patient Register ON POST [POST]

+ Request (application/json)

    + Headers

            auth: login
            auth_key: 91B0B365-7BF7-4724-FEC3-4848E07312B5
    + Body
    
            {"form_pubpid":"Biometricq","form_fname":"First Name","form_lname":"Last name","form_DOB":"2014-12-15","form_age":"","form_sex":"Male","form_status":"single","form_photo":"data:image\/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKAAAAB4CAYAAAB1ovlvAAAABHNCSVQICAgIfAhkiAAABGNJREFUeJzt3E9oHFUAx\/HfzG72T7I1m9am2BKTqPinNLRY\/FNEIlK1KEVFEPTswUsRTx4KevSgJ8GTF6+i9CDVg4cqBVFBsbQoVISmNjVbU9o0f3c3M288bJJ2SaHJpb8Rv5\/LhtkMzCNfHvPeg0T1ej0TYBK7HwD\/bwQIKwKEFQHCigBhRYCwIkBYESCsCBBWBAgrAoQVAcKKAGFFgLAiQFgRIKwIEFYECCsChBUBwooAYUWAsCJAWBEgrAgQVgQIKwKEFQHCigBhRYCwIkBYFd0PgG5ZJEXZ9c8ok0LcfU2SCpmUxNJ29ehQeUijUU1tBZ1fvKrjYUrzhbB2T54xA+ZMMXQ+V+MJcfc1qXM9iaXne0f05bYX9MDALv1dTDRbjvX4vXt0bOBZ7Um3eAawSRH\/ITVfVme5fXG\/nqjs1La0pIlkTl+1\/tKVQqLlgtSTSgcqg\/qg\/4COzP2oXxcvrc10USa9NLxXR67t0uvT36hRSrwDugVmwBx6q29MH905rp4tvWpUE+0eGtbn25\/RHtVUDJ1I39y6V5\/O\/q5fmt3xSdIXF0\/rTP+yXqmO2MawUbwD5swj1UG9XBvVG9Mn9UeYURZJ8dXf9NrIfr3fflSH50+oVOvV\/erXO0sXFN3wjrcaYhwynZq5qEPxoD5O\/\/QMZIOYAXNmvD6i4wvndDbMSurMakksHbt4WrWBfo236uotlhSyTNNRa939aSTFQbqslvrintv9+JtGgDlTK1U02ZrVjYvXWNJi0lZDTdULFS20lhRHkR5qVtfdH6szE+6KetW4SaB5Q4A5cy1parfuWHufS1cWJZViSUNpRVNRU+1mS9+Vr+rF8vC6++MgxcWCDlaH9G3auM1Pv3kEmDNfL53X0\/VRPRz6JIXOHyiO9F55TJPtWf1UnFEaSZ\/MnNHBnQ\/q1dagpLC2ZxgXpA+r+xUnQZ+lF7yD2QC2YXImyqTnRsZ0tHmfzl6Z0tnygp4s7FBaKent6ZOaCPMqZJ2Z8bGBu3V0yz4t\/XNF38czGohKGi\/t0ERlWe9e+kGTYcE9nFsiwJzJVhYRW+t1HdJdqhWLOtee04mlSSVJ0llkrPxuHKSeao+e6hvWPaopC0Gn2pf182JDaRas49goAsyh1VOQzqZ0rDQKKqed1fDq99L1Izqp++guWTk9yfsxnMQ+YC51byyHtXPfm3\/f\/XMWdc6J\/wvxSSxCYEaAsCJAWBEgrAgQVgQIKwKEFQHCigBhRYCwIkBYESCsCBBWBAgrAoQVAcKKAGFFgLAiQFgRIKwIEFYECCsChBUBwooAYUWAsCJAWBEgrAgQVgQIKwKEFQHCigBhRYCwIkBYESCsCBBWBAgrAoQVAcKKAGFFgLAiQFgRIKwIEFYECCsChBUBwooAYUWAsCJAWBEgrAgQVgQIKwKEFQHCigBhRYCwIkBYESCsCBBWBAgrAoQVAcKKAGFFgLAiQFgRIKwIEFYECCsChBUBwooAYUWAsCJAWP0Lie0T6S1FkqMAAAAASUVORK5CYII=","form_genericname1":"A+","form_street":"Door no, Street name","form_genericval2":"Village","form_genericval1":"Taluk","form_city":"City","form_genericname2":"District","form_state":"AP","form_postal_code":"628151","form_phone_cell":"0987654321","form_phone_home":"1234567890","form_email":"rajasekar.jeya@gmail.com","form_guardiansname":"Emergency Contact Name","form_contact_relationship":"Contact RelationShip","form_phone_contact":"1029384756","form_occupation":"Occupation","form_em_name":"Employer Name","form_em_street":"Employer Address","form_usertext11":{"vv":"Varicose Veins","ht":"Hypertension","db":"Diabetes","sc":"Sickle Cell","fib":"Fibroids","pid":"PID (Pelvic Inflammatory Disease)","mig":"Severe Migraine","hd":"Heart Disease","str":"Thrombosis\/Stroke","hep":"Hepatitis","gb":"Gall Bladder Condition","br":"Breast Disease","dpr":"Depression","all":"Allergies","inf":"Infertility","ast":"Asthma","ep":"Epilepsy","cl":"Contact Lenses","coc":"Contraceptive Complication (specify)","oth":"Other (specify)"},"form_userarea11":["Varicose Veins","Hypertension","Diabetes"],"form_exams":{"brs":"Breast Exam","cec":"Cardiac Echo","ecg":"ECG","gyn":"Gynecological","mam":"Mammogram","phy":"Physical","pro":"","rec":"","sic":"","ret":"","flu":"","pne":"","ldl":"","hem":"Hemoglobin","psa":"PSA"},"radio_exams":{"brs":"2","cec":"3","ecg":"2","gyn":"3","mam":"2","phy":"2","hem":"2","psa":"2"},"form_text_tobacco":"Tobacco Type","form_tobacco":"15","form_coffee":"Coffee","form_alcohol":"Alcohol","form_recreational_drugs":"Recreational Drugs","form_counseling":"Counselling","form_exercise_patterns":"Exercise Patterns","form_hazardous_activities":"Hazardous Activities","form_userarea12":"Life style Others","form_relatives_cancer":"Cancer","form_relatives_tuberculosis":"Tuberculosis","form_relatives_diabetes":"Diabetes","form_relatives_high_blood_pressure":"High Blood Pressure","form_relatives_heart_problems":"Tuberculosis","form_relatives_stroke":"Stroke","form_relatives_epilepsy":"Epilepsy","form_relatives_mental_illness":"Mental Illness","form_relatives_suicide":"Suicide","form_history_father":"Father","form_history_mother":"Mothers","form_history_siblings":"Siblings","form_history_spouse":"Spouse","form_history_offspring":"Child"}

+ Response 200 (application/json)
    
    + Body
    
            {"StatusCode":200,"Patient Details":{"Patient_Name":"First Name ","Birth_date":"15-Dec-2014","Birth_date_YMD":"2014-12-15","External_id":"Biometric-89","pid":"89","Age_flag":"0","Patient_Address":"Door no, Street name Village Taluk District City Andhra Pradesh 628151","Address_Street":"Door no, Street name","Village":"Village","Taluk":"Taluk","District":"District","City":"City","State":"Andhra Pradesh","Pin_code":"628151","sex":"Male","status":"single","Blood_group":"A+","Mobile":"0987654321","Landline":"1234567890","email":"rajasekar.jeya@gmail.com","Emergency":"Emergency Contact Name - Contact RelationShip","Emergency_contact":"1029384756","occupation":"Occupation","Regdate":"19-Dec-2014","Lastupdate":"19-Dec-2014 11:28 AM","Register_Facility":"Dr. Metha Hospital","fathers_name":"Father","mothers_name":"Mothers","Age":"0y 0m 4d","images":"csr_data\/89-00E4FDD37D5D46CDFDE6385D596F58C4.png","Register_By":"Administrator Administrator","Since":"11 hours"}}

## Update Patient  [/demographics/update/:update]

<pre class="json">
<code><span> Request method : PUT<span>
<span>Resource URI : /demographics/update/:update<span>
<span>Request Content type :application/json<span></code>
</pre>

<table><tbody>
<tr><td colspan="2"><strong>Required Header Parameters</strong></td></tr>
<tr><td >auth</td><td><code>login</code></td></tr>
<tr><td >auth_key</td><td><code>91B0B365-7BF7-4724-FEC3-4848E07312B5</code></td></tr>
</tbody></table>

<table><tbody>
<tr><td colspan="2"><strong>Required URI Parameters</strong></td></tr>
<tr><td >:update</td><td><code>patient internal id </code>passed here.<code>( integer)</code></td></tr>
</tbody></table>


### Update Patient  ON PUT  [PUT]

+ Request (application/json)

    + Headers
    
            auth: login
            auth_key: 91B0B365-7BF7-4724-FEC3-4848E07312B5
   
    + Body
    
            {"form_pubpid":"Biometricqcsr","form_fname":"First Name","form_lname":"Last name","form_DOB":"2014-12-15","form_age":"","form_sex":"Male","form_status":"single","form_photo":"data:image\/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKAAAAB4CAYAAAB1ovlvAAAABHNCSVQICAgIfAhkiAAABGNJREFUeJzt3E9oHFUAx\/HfzG72T7I1m9am2BKTqPinNLRY\/FNEIlK1KEVFEPTswUsRTx4KevSgJ8GTF6+i9CDVg4cqBVFBsbQoVISmNjVbU9o0f3c3M288bJJ2SaHJpb8Rv5\/LhtkMzCNfHvPeg0T1ej0TYBK7HwD\/bwQIKwKEFQHCigBhRYCwIkBYESCsCBBWBAgrAoQVAcKKAGFFgLAiQFgRIKwIEFYECCsChBUBwooAYUWAsCJAWBEgrAgQVgQIKwKEFQHCigBhRYCwIkBYFd0PgG5ZJEXZ9c8ok0LcfU2SCpmUxNJ29ehQeUijUU1tBZ1fvKrjYUrzhbB2T54xA+ZMMXQ+V+MJcfc1qXM9iaXne0f05bYX9MDALv1dTDRbjvX4vXt0bOBZ7Um3eAawSRH\/ITVfVme5fXG\/nqjs1La0pIlkTl+1\/tKVQqLlgtSTSgcqg\/qg\/4COzP2oXxcvrc10USa9NLxXR67t0uvT36hRSrwDugVmwBx6q29MH905rp4tvWpUE+0eGtbn25\/RHtVUDJ1I39y6V5\/O\/q5fmt3xSdIXF0\/rTP+yXqmO2MawUbwD5swj1UG9XBvVG9Mn9UeYURZJ8dXf9NrIfr3fflSH50+oVOvV\/erXO0sXFN3wjrcaYhwynZq5qEPxoD5O\/\/QMZIOYAXNmvD6i4wvndDbMSurMakksHbt4WrWBfo236uotlhSyTNNRa939aSTFQbqslvrintv9+JtGgDlTK1U02ZrVjYvXWNJi0lZDTdULFS20lhRHkR5qVtfdH6szE+6KetW4SaB5Q4A5cy1parfuWHufS1cWJZViSUNpRVNRU+1mS9+Vr+rF8vC6++MgxcWCDlaH9G3auM1Pv3kEmDNfL53X0\/VRPRz6JIXOHyiO9F55TJPtWf1UnFEaSZ\/MnNHBnQ\/q1dagpLC2ZxgXpA+r+xUnQZ+lF7yD2QC2YXImyqTnRsZ0tHmfzl6Z0tnygp4s7FBaKent6ZOaCPMqZJ2Z8bGBu3V0yz4t\/XNF38czGohKGi\/t0ERlWe9e+kGTYcE9nFsiwJzJVhYRW+t1HdJdqhWLOtee04mlSSVJ0llkrPxuHKSeao+e6hvWPaopC0Gn2pf182JDaRas49goAsyh1VOQzqZ0rDQKKqed1fDq99L1Izqp++guWTk9yfsxnMQ+YC51byyHtXPfm3\/f\/XMWdc6J\/wvxSSxCYEaAsCJAWBEgrAgQVgQIKwKEFQHCigBhRYCwIkBYESCsCBBWBAgrAoQVAcKKAGFFgLAiQFgRIKwIEFYECCsChBUBwooAYUWAsCJAWBEgrAgQVgQIKwKEFQHCigBhRYCwIkBYESCsCBBWBAgrAoQVAcKKAGFFgLAiQFgRIKwIEFYECCsChBUBwooAYUWAsCJAWBEgrAgQVgQIKwKEFQHCigBhRYCwIkBYESCsCBBWBAgrAoQVAcKKAGFFgLAiQFgRIKwIEFYECCsChBUBwooAYUWAsCJAWP0Lie0T6S1FkqMAAAAASUVORK5CYII=","form_genericname1":"A+","form_street":"Door no, Street name","form_genericval2":"Village","form_genericval1":"Taluk","form_city":"City","form_genericname2":"District","form_state":"AP","form_postal_code":"628151","form_phone_cell":"0987654321","form_phone_home":"1234567890","form_email":"rajasekar.jeya@gmail.com","form_guardiansname":"Emergency Contact Name","form_contact_relationship":"Contact RelationShip","form_phone_contact":"1029384756","form_occupation":"Occupation","form_em_name":"Employer Name","form_em_street":"Employer Address","form_usertext11":{"vv":"Varicose Veins","ht":"Hypertension","db":"Diabetes","sc":"Sickle Cell","fib":"Fibroids","pid":"PID (Pelvic Inflammatory Disease)","mig":"Severe Migraine","hd":"Heart Disease","str":"Thrombosis\/Stroke","hep":"Hepatitis","gb":"Gall Bladder Condition","br":"Breast Disease","dpr":"Depression","all":"Allergies","inf":"Infertility","ast":"Asthma","ep":"Epilepsy","cl":"Contact Lenses","coc":"Contraceptive Complication (specify)","oth":"Other (specify)"},"form_userarea11":["Varicose Veins","Hypertension","Diabetes"],"form_exams":{"brs":"Breast Exam","cec":"Cardiac Echo","ecg":"ECG","gyn":"Gynecological","mam":"Mammogram","phy":"Physical","pro":"","rec":"","sic":"","ret":"","flu":"","pne":"","ldl":"","hem":"Hemoglobin","psa":"PSA"},"radio_exams":{"brs":"2","cec":"3","ecg":"2","gyn":"3","mam":"2","phy":"2","hem":"2","psa":"2"},"form_text_tobacco":"Tobacco Type","form_tobacco":"15","form_coffee":"Coffee","form_alcohol":"Alcohol","form_recreational_drugs":"Recreational Drugs","form_counseling":"Counselling","form_exercise_patterns":"Exercise Patterns","form_hazardous_activities":"Hazardous Activities","form_userarea12":"Life style Others","form_relatives_cancer":"Cancer","form_relatives_tuberculosis":"Tuberculosis","form_relatives_diabetes":"Diabetes","form_relatives_high_blood_pressure":"High Blood Pressure","form_relatives_heart_problems":"Tuberculosis","form_relatives_stroke":"Stroke","form_relatives_epilepsy":"Epilepsy","form_relatives_mental_illness":"Mental Illness","form_relatives_suicide":"Suicide","form_history_father":"Father","form_history_mother":"Mothers","form_history_siblings":"Siblings","form_history_spouse":"Spouse","form_history_offspring":"Child"}

+ Parameters

    + update (required , `patient_id` , `integer`) ... this is used as a key segment.
    

+ Response 200 (application/json)
    
    + Body
    
            {"StatusCode":200,"Patient Details":{"Patient_Name":"First Name ","Birth_date":"15-Dec-2014","Birth_date_YMD":"2014-12-15","External_id":"Biometric-89","pid":"89","Age_flag":"0","Patient_Address":"Door no, Street name Village Taluk District City Andhra Pradesh 628151","Address_Street":"Door no, Street name","Village":"Village","Taluk":"Taluk","District":"District","City":"City","State":"Andhra Pradesh","Pin_code":"628151","sex":"Male","status":"single","Blood_group":"A+","Mobile":"0987654321","Landline":"1234567890","email":"rajasekar.jeya@gmail.com","Emergency":"Emergency Contact Name - Contact RelationShip","Emergency_contact":"1029384756","occupation":"Occupation","Regdate":"19-Dec-2014","Lastupdate":"19-Dec-2014 11:28 AM","Register_Facility":"Dr. Metha Hospital","fathers_name":"Father","mothers_name":"Mothers","Age":"0y 0m 4d","images":"csr_data\/89-00E4FDD37D5D46CDFDE6385D596F58C4.png","Register_By":"Administrator Administrator","Since":"11 hours"}}


## View an Existing Patient  [/demographics/view/:view]

<pre class="json">
<code><span> Request method : GET<span>
<span>Resource URI : /demographics/view/:view<span>
<span>Request Content type :application/json<span></code>
</pre>

<table><tbody>
<tr><td colspan="2"><strong>Required Header Parameters</strong></td></tr>
<tr><td >auth</td><td><code>login</code></td></tr>
<tr><td >auth_key</td><td><code>91B0B365-7BF7-4724-FEC3-4848E07312B5</code></td></tr>
</tbody></table>


<table><tbody>
<tr><td colspan="2"><strong>Required URI Parameters</strong></td></tr>
<tr><td >:view</td><td><code>patient internal id </code>passed here.<code>( integer)</code></td></tr>
</tbody></table>


### View an Existing Patient  ON GET  [GET]

+ Request (application/json)

    + Headers

            auth: login
            auth_key: 91B0B365-7BF7-4724-FEC3-4848E07312B5

+ Parameters

    + view (required , `patient_id` , `integer`) ... this is used as a key segment.

+ Response 200 (application/json)
    
    + Body
    
                {"success":{"Patient Details":{"pid":"internal_id","fname":"FIRST NAME","lname":"LAST NAME","DOB":"11-DEC-2014","DOB_YMD":"2014-12-11","street":"Door no, Street namE","genericval1":"Taluk","genericname2":"District","genericval2":"Village","city":"City","state":"Kerala","country_code":"IND","postal_code":"600001","occupation":"Occupation","phone_cell":"9876543210","status":"single","sex":"Female","pubpid":"UNIQUEID","genericname1":"O+","history_mother":"Mothers 's Name","guardiansname":"Emergency","Age_flag":"0","Regdate":2014-12-11 12:12:12,"Since":"0 day","history_father":"Father 's name","Age":"16 years","images":"csr_data\/72-DB05A752FF6DA04229BEF6A60765CA01.png"}}}


# Group Find Patient

## Patient Search [/client/search]

<pre class="json">
<code><span> Request method : POST<span>
<span>Resource URI : /client/search<span>
<span>Request Content type :application/json<span></code>
</pre>

<table><tbody>
<tr><td colspan="2"><strong>Required Header Parameters</strong></td></tr>
<tr><td >auth</td><td><code>login</code></td></tr>
<tr><td >auth_key</td><td><code>91B0B365-7BF7-4724-FEC3-4848E07312B5</code></td></tr>
</tbody></table>


### Patient Search  ON POST  [POST]

+ Request (application/json)

    + Headers
    
            auth: login
            auth_key: 91B0B365-7BF7-4724-FEC3-4848E07312B5
   
    + Body

                {"form_pubpid":"Biometricqcsr","form_fname":"First Name","form_lname":"Last name","form_DOB":"2014-12-15","form_age":""}

+ Response 200 (application/json)
    
    + Body
    
            {"success":[{"id":"83","fname":"Rajasekar","lname":"Jeyakumar","mname":"","DOB":"03-Nov-2014","street":"Door no, Street name","postal_code":"628151","city":"City","state":"Tamil Nadu","country_code":"IND","occupation":"","phone_cell":"098-765-4321","status":"married","DATE":"16-Dec-2014 04:33 PM","sex":"Female","pubpid":"Biometric83","pid":"83","genericname1":"B+","genericval1":"Taluk","genericname2":"District","genericval2":"Village","mothersname":"Mothers","guardiansname":"Emr c.N","Name":"Rajasekar Jeyakumar","DOB_YMD":"2014-11-03","Age_flag":"0","mothers_id":"UND::1418711572212219750","mothers_name":"Mothers","fathers_id":"UND::14187115721387416907","fathers_name":"Father","images":"csr_data\/83-A8C074080B30ED63F13AB74D1BF39AE1.png","Age":"1 month 1 week"}],"Total-data":"1"}


