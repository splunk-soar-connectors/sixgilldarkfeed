[comment]: # "Auto-generated SOAR connector documentation"
# Sixgill Darkfeed

Publisher: Sixgill  
Connector Version: 1\.0\.2  
Product Vendor: Sixgill  
Product Name: Darkfeed  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.9\.39220  

Sixgill's premium underground intelligence collection capabilities, real\-time collection, and advanced warning about IOCs help you keep your edge against unknown threats

[comment]: # " File: readme.md"
[comment]: # "  Copyright (c) 2021 Cybersixgill Ltd."
[comment]: # ""
[comment]: # "  Licensed under Apache 2.0 (https://www.apache.org/licenses/LICENSE-2.0.txt)"
[comment]: # ""
## SDK and SDK Licensing details for the app

#### sixgill-clients

This app uses the sixgill-clients module, which is licensed under the MIT License, Copyright (c)
Sixgill.


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Darkfeed asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**sixgill\_client\_id** |  required  | string | Sixgill Client ID
**sixgill\_client\_secret\_key** |  required  | password | Sixgill Client Secret Key
**phantom\_auth\_token** |  required  | password | Phantom authorization token
**verify\_ssl** |  optional  | boolean | Verify SSL Certificate

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[on poll](#action-on-poll) - Scheduled/Automated ingestion of all the new Darkfeed IOCs detected since the last ingestion  
[enrich ip](#action-enrich-ip) - Query the Sixgill Darkfeed for the specified IP and receive all the IOCs matching that IP  
[enrich url](#action-enrich-url) - Query the Sixgill Darkfeed for the specified URL and receive all the IOCs matching that URL  
[enrich domain](#action-enrich-domain) - Query the Sixgill Darkfeed for the specified domain and receive all the IOCs matching that domain  
[enrich hash](#action-enrich-hash) - Query the Sixgill Darkfeed for the specified hash and receive all the IOCs matching that hash  
[enrich post id](#action-enrich-post-id) - Query the Sixgill Darkfeed for the specified Sixgill Post ID \(i\.e\. unique identifier of a specific post shared in the underground\) and receive all the IOCs shared in that post  
[enrich threat actor](#action-enrich-threat-actor) - Query the Sixgill Darkfeed for the specified threat actor and receive all the IOCs shared by that threat actor  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'on poll'
Scheduled/Automated ingestion of all the new Darkfeed IOCs detected since the last ingestion

Type: **ingest**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**container\_id** |  optional  | Container IDs to limit the ingestion to | numeric | 
**start\_time** |  optional  | Start of time range, in epoch time \(milliseconds\) | string | 
**end\_time** |  optional  | End of time range, in epoch time \(milliseconds\) | string | 
**container\_count** |  optional  | Maximum number of container records to query for | numeric | 
**artifact\_count** |  optional  | Maximum number of artifact records to query for | numeric | 

#### Action Output
No Output  

## action: 'enrich ip'
Query the Sixgill Darkfeed for the specified IP and receive all the IOCs matching that IP

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | Enrich IP Address indicator with Sixgill Darkfeed | string |  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.ip | string |  `ip` 
action\_result\.data\.\*\.indicator\_value | string |  `ip` 
action\_result\.data\.\*\.valid\_from | string | 
action\_result\.data\.\*\.sixgill\_severity | string | 
action\_result\.data\.\*\.sixgill\_confidence | string | 
action\_result\.data\.\*\.sixgill\_feedname | string | 
action\_result\.data\.\*\.description | string | 
action\_result\.data\.\*\.sixgill\_posttitle | string | 
action\_result\.data\.\*\.sixgill\_source | string | 
action\_result\.data\.\*\.sixgill\_actor | string | 
action\_result\.data\.\*\.Mitre\_Pattern | string | 
action\_result\.data\.\*\.Virus\_Total | string | 
action\_result\.data\.\*\.labels | string | 
action\_result\.data\.\*\.sixgill\_postid | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'enrich url'
Query the Sixgill Darkfeed for the specified URL and receive all the IOCs matching that URL

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | Enrich URL indicator with Sixgill Darkfeed | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.url | string |  `url` 
action\_result\.data\.\*\.indicator\_value | string |  `url` 
action\_result\.data\.\*\.valid\_from | string | 
action\_result\.data\.\*\.sixgill\_severity | string | 
action\_result\.data\.\*\.sixgill\_confidence | string | 
action\_result\.data\.\*\.sixgill\_feedname | string | 
action\_result\.data\.\*\.description | string | 
action\_result\.data\.\*\.sixgill\_posttitle | string | 
action\_result\.data\.\*\.sixgill\_source | string | 
action\_result\.data\.\*\.sixgill\_actor | string | 
action\_result\.data\.\*\.Mitre\_Pattern | string | 
action\_result\.data\.\*\.Virus\_Total | string | 
action\_result\.data\.\*\.labels | string | 
action\_result\.data\.\*\.sixgill\_postid | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'enrich domain'
Query the Sixgill Darkfeed for the specified domain and receive all the IOCs matching that domain

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**domain** |  required  | Enrich Domain indicator with Sixgill Darkfeed | string |  `domain` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.domain | string |  `domain` 
action\_result\.data\.\*\.indicator\_value | string |  `domain` 
action\_result\.data\.\*\.valid\_from | string | 
action\_result\.data\.\*\.sixgill\_severity | string | 
action\_result\.data\.\*\.sixgill\_confidence | string | 
action\_result\.data\.\*\.sixgill\_feedname | string | 
action\_result\.data\.\*\.description | string | 
action\_result\.data\.\*\.sixgill\_posttitle | string | 
action\_result\.data\.\*\.sixgill\_source | string | 
action\_result\.data\.\*\.sixgill\_actor | string | 
action\_result\.data\.\*\.Mitre\_Pattern | string | 
action\_result\.data\.\*\.Virus\_Total | string | 
action\_result\.data\.\*\.labels | string | 
action\_result\.data\.\*\.sixgill\_postid | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'enrich hash'
Query the Sixgill Darkfeed for the specified hash and receive all the IOCs matching that hash

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**hash** |  required  | Enrich Hash indicator with Sixgill Darkfeed | string |  `hash` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.hash | string |  `hash` 
action\_result\.data\.\*\.indicator\_value | string |  `hash` 
action\_result\.data\.\*\.valid\_from | string | 
action\_result\.data\.\*\.sixgill\_severity | string | 
action\_result\.data\.\*\.sixgill\_confidence | string | 
action\_result\.data\.\*\.sixgill\_feedname | string | 
action\_result\.data\.\*\.description | string | 
action\_result\.data\.\*\.sixgill\_posttitle | string | 
action\_result\.data\.\*\.sixgill\_source | string | 
action\_result\.data\.\*\.sixgill\_actor | string | 
action\_result\.data\.\*\.Mitre\_Pattern | string | 
action\_result\.data\.\*\.Virus\_Total | string | 
action\_result\.data\.\*\.labels | string | 
action\_result\.data\.\*\.sixgill\_postid | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'enrich post id'
Query the Sixgill Darkfeed for the specified Sixgill Post ID \(i\.e\. unique identifier of a specific post shared in the underground\) and receive all the IOCs shared in that post

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**postid** |  required  | Enrich Post ID with Sixgill Darkfeed | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.postid | string | 
action\_result\.data\.\*\.indicator\_type | string | 
action\_result\.data\.\*\.indicator\_value | string | 
action\_result\.data\.\*\.valid\_from | string | 
action\_result\.data\.\*\.sixgill\_severity | string | 
action\_result\.data\.\*\.sixgill\_confidence | string | 
action\_result\.data\.\*\.sixgill\_feedname | string | 
action\_result\.data\.\*\.description | string | 
action\_result\.data\.\*\.sixgill\_posttitle | string | 
action\_result\.data\.\*\.sixgill\_source | string | 
action\_result\.data\.\*\.sixgill\_actor | string | 
action\_result\.data\.\*\.Mitre\_Pattern | string | 
action\_result\.data\.\*\.Virus\_Total | string | 
action\_result\.data\.\*\.labels | string | 
action\_result\.data\.\*\.sixgill\_postid | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'enrich threat actor'
Query the Sixgill Darkfeed for the specified threat actor and receive all the IOCs shared by that threat actor

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**actor** |  required  | Enrich Actor indicator with Sixgill Darkfeed | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.actor | string | 
action\_result\.data\.\*\.indicator\_type | string | 
action\_result\.data\.\*\.indicator\_value | string | 
action\_result\.data\.\*\.valid\_from | string | 
action\_result\.data\.\*\.sixgill\_severity | string | 
action\_result\.data\.\*\.sixgill\_confidence | string | 
action\_result\.data\.\*\.sixgill\_feedname | string | 
action\_result\.data\.\*\.description | string | 
action\_result\.data\.\*\.sixgill\_posttitle | string | 
action\_result\.data\.\*\.sixgill\_source | string | 
action\_result\.data\.\*\.sixgill\_actor | string | 
action\_result\.data\.\*\.Mitre\_Pattern | string | 
action\_result\.data\.\*\.Virus\_Total | string | 
action\_result\.data\.\*\.labels | string | 
action\_result\.data\.\*\.sixgill\_postid | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 