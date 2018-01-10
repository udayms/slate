---
title: Percipient Public API Endpoints v1
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2


---


<h1 id="Percipient-Public-API-Endpoints">Percipient Public API Endpoints v1</h1>


> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.


# Percipient Public API Documentation: #
- https://docs.methodics.com/display/PI2/Percipient+Public+API


# Base Path: #
http://&lt;piserver-hostname&gt;:&lt;port&gt;/**public**/
<header>


Base URLs:


* <a href="/public">/public</a>


<h1 id="Percipient-Public-API-Endpoints-Aliases">Aliases</h1>


## getAlias


<a id="opIdgetAlias"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/aliases/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/aliases/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/aliases/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/aliases/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/aliases/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/aliases/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/aliases/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/aliases/{id}`


*Get the alias with the specified ID*


<h3 id="getAlias-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Alias ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - ipls
 - ipvs
 - old_ipvs


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - old_ipvs


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|ipls|
|link|ipvs|
|link|old_ipvs|
|exclude|old_ipvs|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name",
      "alias": "GOLD"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353110888,
    "locked": true,
    "ipl": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      }
    },
    "ipv": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      }
    },
    "old_ipvs": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      }
    ]
  },
  "links": {
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  }
}
```


<h3 id="getAlias-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AliasResponseData](#schemaaliasresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## usageAlias


<a id="opIdusageAlias"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/aliases/{id}/usage \
  -H 'Accept: application/json'


```


```http
GET /public/v1/aliases/{id}/usage HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/aliases/{id}/usage',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/aliases/{id}/usage',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/aliases/{id}/usage',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/aliases/{id}/usage', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/aliases/{id}/usage");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/aliases/{id}/usage`


*Get a flattened list of the IPVs that use this aliased IPV*


<h3 id="usageAlias-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Alias ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - top_level_ips


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - top_level_ips


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|top_level_ips|
|exclude|top_level_ips|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "ipvs": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "parent_ids": "[xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx]"
      }
    ],
    "top_level_ips": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      }
    ]
  },
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    }
  }
}
```


<h3 id="usageAlias-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpvReferenceUsageResponseData](#schemaipvreferenceusageresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-Attributes">Attributes</h1>


## getAttribute


<a id="opIdgetAttribute"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/attributes/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/attributes/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/attributes/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/attributes/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/attributes/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/attributes/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/attributes/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/attributes/{id}`


*Get the attribute with the specified ID*


<h3 id="getAttribute-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Attribute ID|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "attribute_name",
    "value": "attribute_value",
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353110568
  },
  "links": {}
}
```


<h3 id="getAttribute-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AttributeResponseData](#schemaattributeresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-Groups">Groups</h1>


## findGroups


<a id="opIdfindGroups"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/groups \
  -H 'Accept: application/json'


```


```http
GET /public/v1/groups HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/groups',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/groups',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/groups',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/groups', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/groups");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/groups`


*Get a list of groups*


<h3 id="findGroups-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|false|Expression language query for filtering groups.|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - child_groups
 - parent_groups
 - users


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - child_groups
 - parent_groups
 - users


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|child_groups|
|link|parent_groups|
|link|users|
|exclude|child_groups|
|exclude|parent_groups|
|exclude|users|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "group_name",
      "description": "group_description",
      "builtin": true,
      "external": true,
      "parent_groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ],
      "child_groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ],
      "users": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        }
      ]
    }
  ],
  "links": {
    "groups": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      }
    },
    "users": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "user_name",
        "full_name": "user_full_name",
        "email": "user_email",
        "description": "user_description",
        "builtin": true,
        "admin": true,
        "external": true,
        "groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "user_name",
        "full_name": "user_full_name",
        "email": "user_email",
        "description": "user_description",
        "builtin": true,
        "admin": true,
        "external": true,
        "groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="findGroups-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GroupsResponseData](#schemagroupsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## getGroup


<a id="opIdgetGroup"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/groups/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/groups/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/groups/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/groups/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/groups/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/groups/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/groups/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/groups/{id}`


*Get the group with the specified ID*


<h3 id="getGroup-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Group ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - child_groups
 - parent_groups
 - users


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - child_groups
 - parent_groups
 - users


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|child_groups|
|link|parent_groups|
|link|users|
|exclude|child_groups|
|exclude|parent_groups|
|exclude|users|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "group_name",
    "description": "group_description",
    "builtin": true,
    "external": true,
    "parent_groups": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      }
    ],
    "child_groups": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      }
    ],
    "users": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      }
    ]
  },
  "links": {
    "groups": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      }
    },
    "users": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "user_name",
        "full_name": "user_full_name",
        "email": "user_email",
        "description": "user_description",
        "builtin": true,
        "admin": true,
        "external": true,
        "groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "user_name",
        "full_name": "user_full_name",
        "email": "user_email",
        "description": "user_description",
        "builtin": true,
        "admin": true,
        "external": true,
        "groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="getGroup-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GroupResponseData](#schemagroupresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-IPLs">IPLs</h1>


## findIpls


<a id="opIdfindIpls"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ipls \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ipls HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ipls',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ipls',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ipls',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ipls', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ipls");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ipls`


*Get a list of IPLs*


<h3 id="findIpls-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|false|Expression language query for filtering IPLs|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - ips
 - ipvs


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - ipvs
 - perms


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|ips|
|link|ipvs|
|exclude|attributes|
|exclude|ipvs|
|exclude|perms|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353223268,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    }
  ],
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  }
}
```


<h3 id="findIpls-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IplsResponseData](#schemaiplsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## getIpl


<a id="opIdgetIpl"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ipls/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ipls/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ipls/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ipls/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ipls/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ipls/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ipls/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ipls/{id}`


*Get the IPL with the specified ID*


<h3 id="getIpl-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IPL ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - ips
 - ipvs


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - ipvs
 - perms


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|ips|
|link|ipvs|
|exclude|attributes|
|exclude|ipvs|
|exclude|perms|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353223268,
    "ip": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      }
    },
    "attributes": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "attribute_name"
      }
    ],
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "ipvs": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      }
    ]
  },
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  }
}
```


<h3 id="getIpl-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IplResponseData](#schemaiplresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## findIpvsFromIpl


<a id="opIdfindIpvsFromIpl"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ipls/{id}/ipvs \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ipls/{id}/ipvs HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ipls/{id}/ipvs',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ipls/{id}/ipvs',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ipls/{id}/ipvs',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ipls/{id}/ipvs', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ipls/{id}/ipvs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ipls/{id}/ipvs`


*Get a list of IPVs for this IPL*


<h3 id="findIpvsFromIpl-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IPL ID|
|query|query|string|false|Expression language query for filtering IPVs.|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - contents
 - current_aliases
 - historic_aliases
 - ipls
 - property_values
 - resources


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - current_aliases
- historic_aliases
 - property_values
 - resources


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|contents|
|link|current_aliases|
|link|historic_aliases|
|link|ipls|
|link|property_values|
|link|resources|
|exclude|attributes|
|exclude|current_aliases|
|exclude|historic_aliases|
|exclude|property_values|
|exclude|resources|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    }
  ],
  "links": {
    "aliases": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    },
    "ipv_contents": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    }
  }
}
```


<h3 id="findIpvsFromIpl-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpvsResponseData](#schemaipvsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## usageIpl


<a id="opIdusageIpl"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ipls/{id}/usage \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ipls/{id}/usage HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ipls/{id}/usage',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ipls/{id}/usage',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ipls/{id}/usage',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ipls/{id}/usage', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ipls/{id}/usage");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ipls/{id}/usage`


*Get a flattened list of the IPVs that use this IPL*


<h3 id="usageIpl-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IPL ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - top_level_ips


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - top_level_ips


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|top_level_ips|
|exclude|top_level_ips|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "ipvs": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "parent_ids": "[xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx]"
      }
    ],
    "top_level_ips": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      }
    ]
  },
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    }
  }
}
```


<h3 id="usageIpl-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpvReferenceUsageResponseData](#schemaipvreferenceusageresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## getIplPerms


<a id="opIdgetIplPerms"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ipls/{id}/perms \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ipls/{id}/perms HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ipls/{id}/perms',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ipls/{id}/perms',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ipls/{id}/perms',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ipls/{id}/perms', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ipls/{id}/perms");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ipls/{id}/perms`


*Get a list of group and user permissions for this IPL*


<h3 id="getIplPerms-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IPL ID|
|filter|query|string|false|Filter list of permissions by following the CLI format |


#### Detailed descriptions


**filter**: Filter list of permissions by following the CLI format 
`[u/g]:[user_name/group_name]:[r/w/o]`, e.g. u:bob:r


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "ipl": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      }
    }
  },
  "links": {}
}
```


<h3 id="getIplPerms-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IplPermsResponseData](#schemaiplpermsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## updateIplPerms


<a id="opIdupdateIplPerms"></a>


> Code samples


```shell
# You can also use wget
curl -X POST /public/v1/ipls/{id}/perms \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


```http
POST /public/v1/ipls/{id}/perms HTTP/1.1
Host: null
Content-Type: application/json
Accept: application/json


```


```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ipls/{id}/perms',
  method: 'post',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "perms": [
    {
      "group_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "read": true,
      "write": true,
      "owner": true
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'


};


fetch('/public/v1/ipls/{id}/perms',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}


result = RestClient.post '/public/v1/ipls/{id}/perms',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}


r = requests.post('/public/v1/ipls/{id}/perms', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ipls/{id}/perms");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /v1/ipls/{id}/perms`


*Specify the permissions for this IPL*


> Body parameter


```json
{
  "perms": [
    {
      "group_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "read": true,
      "write": true,
      "owner": true
    }
  ]
}
```


<h3 id="updateIplPerms-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IPL ID|
|body|body|[ObjectPermsWrite](#schemaobjectpermswrite)|false|No description|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "ipl": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      }
    }
  },
  "links": {}
}
```


<h3 id="updateIplPerms-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IplPermsResponseData](#schemaiplpermsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-IPLVs">IPLVs</h1>


## findIplvs


<a id="opIdfindIplvs"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/iplvs \
  -H 'Accept: application/json'


```


```http
GET /public/v1/iplvs HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/iplvs',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/iplvs',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/iplvs',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/iplvs', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/iplvs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/iplvs`


*Get a list of IPLVs*


<h3 id="findIplvs-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|false|Expression language query for filtering IPLVs.|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - contents
 - current_aliases
 - historic_aliases
 - labels
 - libraries
 - property_values
 - property_sets
 - resources


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - labels
 - perms
- property_values
 - property_sets
 - resources


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|contents|
|link|current_aliases|
|link|historic_aliases|
|link|labels|
|link|libraries|
|link|property_values|
|link|property_sets|
|link|resources|
|exclude|attributes|
|exclude|labels|
|exclude|perms|
|exclude|property_values|
|exclude|property_sets|
|exclude|resources|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "ipv": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  ],
  "links": {
    "aliases": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    },
    "ipv_contents": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "libraries": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="findIplvs-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IplvsResponseData](#schemaiplvsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## getIplv


<a id="opIdgetIplv"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/iplvs/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/iplvs/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/iplvs/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/iplvs/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/iplvs/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/iplvs/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/iplvs/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/iplvs/{id}`


*Get the IPLV with the specified ID*


<h3 id="getIplv-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IPLV ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - contents
 - current_aliases
 - historic_aliases
 - labels
 - libraries
 - property_values
 - property_sets
 - resources


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - labels
 - perms
- property_values
 - property_sets
 - resources


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|contents|
|link|current_aliases|
|link|historic_aliases|
|link|labels|
|link|libraries|
|link|property_values|
|link|property_sets|
|link|resources|
|exclude|attributes|
|exclude|labels|
|exclude|perms|
|exclude|property_values|
|exclude|property_sets|
|exclude|resources|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "ip": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    },
    "ipl": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353223268,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    },
    "ipv": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    }
  },
  "links": {
    "aliases": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    },
    "ipv_contents": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "libraries": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="getIplv-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IplvResponseData](#schemaiplvresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-IPs">IPs</h1>


## findIps


<a id="opIdfindIps"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ips \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ips HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ips',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ips',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ips',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ips', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ips");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ips`


*Get a list of IPs*


<h3 id="findIps-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|false|Expression language query for filtering IPs.|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - ipls
 - labels
 - libraries
 - property_values
 - property_sets


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - ipls
 - labels
 - perms
 - property_values
 - property_sets


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|ipls|
|link|labels|
|link|libraries|
|link|property_values|
|link|property_sets|
|exclude|attributes|
|exclude|ipls|
|exclude|labels|
|exclude|perms|
|exclude|property_values|
|exclude|property_sets|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    }
  ],
  "links": {
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "libraries": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="findIps-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpsResponseData](#schemaipsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## getIp


<a id="opIdgetIp"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ips/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ips/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ips/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ips/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ips/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ips/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ips/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ips/{id}`


*Get the IP with the specified ID*


<h3 id="getIp-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IP ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - ipls
 - labels
 - libraries
 - property_values
 - property_sets


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - ipls
 - labels
 - perms
 - property_values
 - property_sets


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|ipls|
|link|labels|
|link|libraries|
|link|property_values|
|link|property_sets|
|exclude|attributes|
|exclude|ipls|
|exclude|labels|
|exclude|perms|
|exclude|property_values|
|exclude|property_sets|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353220568,
    "library": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name"
      }
    },
    "description": "ip_description",
    "dm_type": "P4",
    "host": "ip_hook",
    "hooks": {
      "hook_post_load": "post_load_hook",
      "hook_post_update": "post_update_hook",
      "hook_pre_release": "pre_release_hook",
      "hook_post_release": "post_release_hook"
    },
    "labels": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "label_name"
      }
    ],
    "ipls": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      }
    ],
    "attributes": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "attribute_name"
      }
    ],
    "property_values": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "default_value": "default_value",
        "name": "property_name",
        "suffix": "property_suffix",
        "value": "property_value"
      }
    ],
    "property_sets": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "property_set_name"
      }
    ],
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ]
  },
  "links": {
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "libraries": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="getIp-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpResponseData](#schemaipresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## findIplsFromIp


<a id="opIdfindIplsFromIp"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ips/{id}/ipls \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ips/{id}/ipls HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ips/{id}/ipls',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ips/{id}/ipls',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ips/{id}/ipls',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ips/{id}/ipls', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ips/{id}/ipls");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ips/{id}/ipls`


*Get a list of IPLs for this IP*


<h3 id="findIplsFromIp-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IP ID|
|query|query|string|false|Expression language query for filtering IPLs.|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - ips
 - ipvs


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - ipvs
 - perms


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|ips|
|link|ipvs|
|exclude|attributes|
|exclude|ipvs|
|exclude|perms|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353223268,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    }
  ],
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  }
}
```


<h3 id="findIplsFromIp-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IplsResponseData](#schemaiplsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## usageIp


<a id="opIdusageIp"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ips/{id}/usage \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ips/{id}/usage HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ips/{id}/usage',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ips/{id}/usage',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ips/{id}/usage',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ips/{id}/usage', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ips/{id}/usage");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ips/{id}/usage`


*Get a flattened list of the IPVs that use this IP*


<h3 id="usageIp-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IP ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - top_level_ips


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - top_level_ips


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|top_level_ips|
|exclude|top_level_ips|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "ipvs": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "parent_ids": "[xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx]"
      }
    ],
    "top_level_ips": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      }
    ]
  },
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    }
  }
}
```


<h3 id="usageIp-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpvReferenceUsageResponseData](#schemaipvreferenceusageresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## getIpPerms


<a id="opIdgetIpPerms"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ips/{id}/perms \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ips/{id}/perms HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ips/{id}/perms',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ips/{id}/perms',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ips/{id}/perms',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ips/{id}/perms', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ips/{id}/perms");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ips/{id}/perms`


*Get a list of group and user permissions for this IP*


<h3 id="getIpPerms-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IP ID|
|filter|query|string|false|Filter list of permissions by following the CLI format |


#### Detailed descriptions


**filter**: Filter list of permissions by following the CLI format 
`[u/g]:[user_name/group_name]:[r/w/o]`, e.g. u:bob:r


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "ip": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      }
    }
  },
  "links": {}
}
```


<h3 id="getIpPerms-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpPermsResponseData](#schemaippermsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## updateIpPerms


<a id="opIdupdateIpPerms"></a>


> Code samples


```shell
# You can also use wget
curl -X POST /public/v1/ips/{id}/perms \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


```http
POST /public/v1/ips/{id}/perms HTTP/1.1
Host: null
Content-Type: application/json
Accept: application/json


```


```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ips/{id}/perms',
  method: 'post',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "perms": [
    {
      "group_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "read": true,
      "write": true,
      "owner": true
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'


};


fetch('/public/v1/ips/{id}/perms',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}


result = RestClient.post '/public/v1/ips/{id}/perms',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}


r = requests.post('/public/v1/ips/{id}/perms', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ips/{id}/perms");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /v1/ips/{id}/perms`


*Specify the permissions for this IP*


> Body parameter


```json
{
  "perms": [
    {
      "group_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "read": true,
      "write": true,
      "owner": true
    }
  ]
}
```


<h3 id="updateIpPerms-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IP ID|
|body|body|[ObjectPermsWrite](#schemaobjectpermswrite)|false|No description|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "ip": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      }
    }
  },
  "links": {}
}
```


<h3 id="updateIpPerms-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpPermsResponseData](#schemaippermsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-IPVs">IPVs</h1>


## getIpv


<a id="opIdgetIpv"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ipvs/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ipvs/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ipvs/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ipvs/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ipvs/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ipvs/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ipvs/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ipvs/{id}`


*Get the IPV with the specified ID*


<h3 id="getIpv-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IPV ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - contents
 - current_aliases
 - historic_aliases
- ipls
 - property_values
 - resources


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - current_aliases
 - historic_aliases
 - property_values
 - resources


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|contents|
|link|current_aliases|
|link|historic_aliases|
|link|ipls|
|link|property_values|
|link|resources|
|exclude|attributes|
|exclude|current_aliases|
|exclude|historic_aliases|
|exclude|property_values|
|exclude|resources|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name",
      "version": 1,
      "alias": "GOLD"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353533268,
    "ipl": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      }
    },
    "version_message": "version_message",
    "repo_path": "//depot/xxx",
    "project_props": "--xxx xxxxx",
    "resources": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "private_resource": true
      }
    ],
    "contents": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "timestamp": 1456353223265
    },
    "source": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      }
    },
    "current_aliases": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "GOLD"
      }
    ],
    "historic_aliases": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "GOLD"
      }
    ],
    "attributes": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "attribute_name"
      }
    ],
    "property_values": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "default_value": "default_value",
        "name": "property_name",
        "suffix": "property_suffix",
        "value": "property_value"
      }
    ]
  },
  "links": {
    "aliases": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    },
    "ipv_contents": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    }
  }
}
```


<h3 id="getIpv-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpvResponseData](#schemaipvresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## findIpvs


<a id="opIdfindIpvs"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ipvs \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ipvs HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ipvs',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ipvs',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ipvs',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ipvs', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ipvs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ipvs`


*Get a list of IPVs*


<h3 id="findIpvs-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|false|Expression language query for filtering IPVs.|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - contents
 - current_aliases
 - historic_aliases
- ipls
 - property_values
 - resources


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - current_aliases
 - historic_aliases
- property_values
 - resources


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|contents|
|link|current_aliases|
|link|historic_aliases|
|link|ipls|
|link|property_values|
|link|resources|
|exclude|attributes|
|exclude|current_aliases|
|exclude|historic_aliases|
|exclude|property_values|
|exclude|resources|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    }
  ],
  "links": {
    "aliases": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    },
    "ipv_contents": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    }
  }
}
```


<h3 id="findIpvs-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpvsResponseData](#schemaipvsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## treeIpv


<a id="opIdtreeIpv"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ipvs/{id}/tree \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ipvs/{id}/tree HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ipvs/{id}/tree',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ipvs/{id}/tree',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ipvs/{id}/tree',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ipvs/{id}/tree', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ipvs/{id}/tree");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ipvs/{id}/tree`


*Get the flattened tree of this top IPV*


<h3 id="treeIpv-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IPV ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - contents
 - current_aliases
- historic_aliases
 - ipls
 - property_values


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - current_aliases
 - historic_aliases
 - property_values


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|contents|
|link|current_aliases|
|link|historic_aliases|
|link|ipls|
|link|property_values|
|exclude|attributes|
|exclude|current_aliases|
|exclude|historic_aliases|
|exclude|property_values|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name",
      "version": 1,
      "alias": "GOLD"
    },
    "resources": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    ]
  },
  "links": {
    "aliases": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    },
    "ipv_contents": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    }
  }
}
```


<h3 id="treeIpv-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpvTreeResponseData](#schemaipvtreeresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## usageIpv


<a id="opIdusageIpv"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/ipvs/{id}/usage \
  -H 'Accept: application/json'


```


```http
GET /public/v1/ipvs/{id}/usage HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/ipvs/{id}/usage',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/ipvs/{id}/usage',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/ipvs/{id}/usage',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/ipvs/{id}/usage', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/ipvs/{id}/usage");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/ipvs/{id}/usage`


*Get a flattened list of the IPVs that use this IPV*


<h3 id="usageIpv-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The IPV ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - top_level_ips


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - top_level_ips


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|top_level_ips|
|exclude|top_level_ips|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "ipvs": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "parent_ids": "[xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx]"
      }
    ],
    "top_level_ips": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      }
    ]
  },
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    }
  }
}
```


<h3 id="usageIpv-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpvReferenceUsageResponseData](#schemaipvreferenceusageresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-Labels">Labels</h1>


## getLabel


<a id="opIdgetLabel"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/labels/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/labels/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/labels/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/labels/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/labels/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/labels/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/labels/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/labels/{id}`


*Get the label with the specified ID*


<h3 id="getLabel-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Label ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - ips
 - libraries


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - ips
 - libraries


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|ips|
|link|libraries|
|exclude|ips|
|exclude|libraries|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "label_name",
    "type": "label_type",
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1646455223268,
    "color": "#xxxxxx",
    "libraries": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      }
    ],
    "ips": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      }
    ]
  },
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    },
    "libraries": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="getLabel-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[LabelResponseData](#schemalabelresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-Property-definitions">Property definitions</h1>


## getPropertyDefinition


<a id="opIdgetPropertyDefinition"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/property-definitions/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/property-definitions/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/property-definitions/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/property-definitions/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/property-definitions/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/property-definitions/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/property-definitions/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/property-definitions/{id}`


*Get the property definition with the specified ID*


<h3 id="getPropertyDefinition-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Property definition ID|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "property_def_name",
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1646655255268,
    "target_type": "target_type",
    "value_type": "value_type",
    "choice_values": "choice_values",
    "description": "property_def_description",
    "suffix": "property_def_suffix",
    "default_value": "default_value",
    "propagate_value": false
  },
  "links": {}
}
```


<h3 id="getPropertyDefinition-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PropertyDefinitionResponseData](#schemapropertydefinitionresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-Property-sets">Property sets</h1>


## getPropertySet


<a id="opIdgetPropertySet"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/property-sets/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/property-sets/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/property-sets/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/property-sets/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/property-sets/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/property-sets/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/property-sets/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/property-sets/{id}`


*Get the property set with the specified ID*


<h3 id="getPropertySet-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Property set ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - property_definitions


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - property_definitions


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|property_definitions|
|exclude|property_definitions|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "property_set_name",
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1667655255268,
    "description": "property_set_description",
    "property_definitions": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "property_def_name"
      }
    ]
  },
  "links": {
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    }
  }
}
```


<h3 id="getPropertySet-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PropertySetResponseData](#schemapropertysetresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-System">System</h1>


## getInfo


<a id="opIdgetInfo"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/system/info \
  -H 'Accept: application/json'


```


```http
GET /public/v1/system/info HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/system/info',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/system/info',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/system/info',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/system/info', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/system/info");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/system/info`


*Get the system information*


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "server": {
      "version": {
        "major": 2,
        "minor": 15,
        "patch": 0
      },
      "release": true
    },
    "extension": {
      "version": {
        "major": 2,
        "minor": 15,
        "patch": 0
      },
      "release": true
    },
    "neo4j_version": {
      "major": 2,
      "minor": 15,
      "patch": 0
    }
  },
  "links": {}
}
```


<h3 id="getInfo-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SystemResponseData](#schemasystemresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-Users">Users</h1>


## whoami


<a id="opIdwhoami"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/users/whoami \
  -H 'Accept: application/json'


```


```http
GET /public/v1/users/whoami HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/users/whoami',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/users/whoami',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/users/whoami',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/users/whoami', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/users/whoami");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/users/whoami`


*Get the current user*


<h3 id="whoami-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - groups


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - groups


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|groups|
|exclude|groups|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "user_name",
    "full_name": "user_full_name",
    "email": "user_email",
    "description": "user_description",
    "builtin": true,
    "admin": true,
    "external": true,
    "groups": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      }
    ]
  },
  "links": {
    "groups": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="whoami-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserResponseData](#schemauserresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## getUser


<a id="opIdgetUser"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/users/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/users/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/users/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/users/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/users/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/users/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/users/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/users/{id}`


*Get the user with the specified ID*


<h3 id="getUser-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The User ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - groups


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - groups


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|groups|
|exclude|groups|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "user_name",
    "full_name": "user_full_name",
    "email": "user_email",
    "description": "user_description",
    "builtin": true,
    "admin": true,
    "external": true,
    "groups": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      }
    ]
  },
  "links": {
    "groups": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="getUser-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserResponseData](#schemauserresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## findUsers


<a id="opIdfindUsers"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/users \
  -H 'Accept: application/json'


```


```http
GET /public/v1/users HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/users',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/users',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/users',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/users', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/users");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/users`


*Get a list of users*


<h3 id="findUsers-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|false|Expression language query for filtering users.|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - groups


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - groups


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|groups|
|exclude|groups|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "user_name",
      "full_name": "user_full_name",
      "email": "user_email",
      "description": "user_description",
      "builtin": true,
      "admin": true,
      "external": true,
      "groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ]
    }
  ],
  "links": {
    "groups": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="findUsers-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UsersResponseData](#schemausersresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-Workspaces">Workspaces</h1>


## getWorkspace


<a id="opIdgetWorkspace"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/workspaces/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/workspaces/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/workspaces/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/workspaces/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/workspaces/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/workspaces/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/workspaces/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/workspaces/{id}`


*Get the workspace with the specified ID*


<h3 id="getWorkspace-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Workspace ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - top_ipvs
 - resources


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - resources


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|top_ipvs|
|link|resources|
|exclude|resources|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1667652355268,
    "path": "//depot/xxx",
    "p4_client": "workspace_p4_client",
    "snapshot": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "snapshot_id": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD",
        "snapshot": 0
      }
    },
    "top_ipv": {
      "ipv": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "alias": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "GOLD"
      },
      "last_updater": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "last_update_timestamp": 1667659955268
    },
    "resources": [
      {
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "alias": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        },
        "last_updater": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "last_update_timestamp": 1667659955268
      }
    ]
  },
  "links": {
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  }
}
```


<h3 id="getWorkspace-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[WorkspaceResponseData](#schemaworkspaceresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## findWorkspaces


<a id="opIdfindWorkspaces"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/workspaces \
  -H 'Accept: application/json'


```


```http
GET /public/v1/workspaces HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/workspaces',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/workspaces',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/workspaces',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/workspaces', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/workspaces");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/workspaces`


*Get a list of workspaces*


<h3 id="findWorkspaces-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|false|Expression language query for filtering workspaces.|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - top_ipvs
 - resources


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - resources


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|top_ipvs|
|link|resources|
|exclude|resources|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1667652355268,
      "path": "//depot/xxx",
      "p4_client": "workspace_p4_client",
      "snapshot": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "snapshot_id": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD",
          "snapshot": 0
        }
      },
      "top_ipv": {
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "alias": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        },
        "last_updater": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "last_update_timestamp": 1667659955268
      },
      "resources": [
        {
          "ipv": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          },
          "alias": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          },
          "last_updater": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          },
          "last_update_timestamp": 1667659955268
        }
      ]
    }
  ],
  "links": {
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  }
}
```


<h3 id="findWorkspaces-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[WorkspacesResponseData](#schemaworkspacesresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


<h1 id="Percipient-Public-API-Endpoints-Libraries">Libraries</h1>


## findLibraries


<a id="opIdfindLibraries"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/libraries \
  -H 'Accept: application/json'


```


```http
GET /public/v1/libraries HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/libraries',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/libraries',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/libraries',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/libraries', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/libraries");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/libraries`


*Get a list of libraries*


<h3 id="findLibraries-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|false|Expression language query for filtering libraries.|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - ips
 - labels
 - property_sets


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - ips
 - labels
 - perms
 - property_sets


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|ips|
|link|labels|
|link|property_sets|
|exclude|attributes|
|exclude|ips|
|exclude|labels|
|exclude|perms|
|exclude|property_sets|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455255268,
      "vendor": "vendor",
      "description": "library_description",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ],
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ]
    }
  ],
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="findLibraries-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[LibrariesResponseData](#schemalibrariesresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## getLibrary


<a id="opIdgetLibrary"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/libraries/{id} \
  -H 'Accept: application/json'


```


```http
GET /public/v1/libraries/{id} HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/libraries/{id}',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/libraries/{id}',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/libraries/{id}',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/libraries/{id}', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/libraries/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/libraries/{id}`


*Get the library with the specified ID*


<h3 id="getLibrary-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Library ID|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - ips
 - labels
 - property_sets


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - ips
 - labels
 - perms
 - property_sets


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|ips|
|link|labels|
|link|property_sets|
|exclude|attributes|
|exclude|ips|
|exclude|labels|
|exclude|perms|
|exclude|property_sets|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1646455255268,
    "vendor": "vendor",
    "description": "library_description",
    "hooks": {
      "hook_post_load": "post_load_hook",
      "hook_post_update": "post_update_hook",
      "hook_pre_release": "pre_release_hook",
      "hook_post_release": "post_release_hook"
    },
    "attributes": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "attribute_name"
      }
    ],
    "ips": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      }
    ],
    "labels": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "label_name"
      }
    ],
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "property_sets": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "property_set_name"
      }
    ]
  },
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="getLibrary-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[LibraryResponseData](#schemalibraryresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## findIpsFromLibrary


<a id="opIdfindIpsFromLibrary"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/libraries/{id}/ips \
  -H 'Accept: application/json'


```


```http
GET /public/v1/libraries/{id}/ips HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/libraries/{id}/ips',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/libraries/{id}/ips',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/libraries/{id}/ips',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/libraries/{id}/ips', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/libraries/{id}/ips");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/libraries/{id}/ips`


*Get a list of IPs for this library*


<h3 id="findIpsFromLibrary-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Library ID|
|query|query|string|false|Expression language query for filtering IPs.|
|link|query|array[string]|false|Additional fields that can be optionally extended (linked) in the payload.|
|exclude|query|array[string]|false|Fields that can be optionally excluded from the payload.|


#### Detailed descriptions


**link**: Additional fields that can be optionally extended (linked) in the payload.
Available options:
 - ipls
 - labels
 - libraries
 - property_values
 - property_sets


**exclude**: Fields that can be optionally excluded from the payload.
Available options:
 - attributes
 - ipls
 - labels
 - perms
 - property_values
 - property_sets


#### Enumerated Values


|Parameter|Value|
|---|---|
|link|ipls|
|link|labels|
|link|libraries|
|link|property_values|
|link|property_sets|
|exclude|attributes|
|exclude|ipls|
|exclude|labels|
|exclude|perms|
|exclude|property_values|
|exclude|property_sets|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    }
  ],
  "links": {
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "libraries": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


<h3 id="findIpsFromLibrary-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[IpsResponseData](#schemaipsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## getLibraryPerms


<a id="opIdgetLibraryPerms"></a>


> Code samples


```shell
# You can also use wget
curl -X GET /public/v1/libraries/{id}/perms \
  -H 'Accept: application/json'


```


```http
GET /public/v1/libraries/{id}/perms HTTP/1.1
Host: null


Accept: application/json


```


```javascript
var headers = {
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/libraries/{id}/perms',
  method: 'get',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');


const headers = {
  'Accept':'application/json'


};


fetch('/public/v1/libraries/{id}/perms',
{
  method: 'GET',


  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Accept' => 'application/json'
}


result = RestClient.get '/public/v1/libraries/{id}/perms',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Accept': 'application/json'
}


r = requests.get('/public/v1/libraries/{id}/perms', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/libraries/{id}/perms");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`GET /v1/libraries/{id}/perms`


*Get a list of group and user permissions for this library*


<h3 id="getLibraryPerms-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Library ID|
|filter|query|string|false|Filter list of permissions by following the CLI format |


#### Detailed descriptions


**filter**: Filter list of permissions by following the CLI format 
`[u/g]:[user_name/group_name]:[r/w/o]`, e.g. u:bob:r


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "library": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name"
      }
    }
  },
  "links": {}
}
```


<h3 id="getLibraryPerms-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[LibraryPermsResponseData](#schemalibrarypermsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


## updateLibraryPerms


<a id="opIdupdateLibraryPerms"></a>


> Code samples


```shell
# You can also use wget
curl -X POST /public/v1/libraries/{id}/perms \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'


```


```http
POST /public/v1/libraries/{id}/perms HTTP/1.1
Host: null
Content-Type: application/json
Accept: application/json


```


```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'


};


$.ajax({
  url: '/public/v1/libraries/{id}/perms',
  method: 'post',


  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})


```


```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "perms": [
    {
      "group_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "read": true,
      "write": true,
      "owner": true
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'


};


fetch('/public/v1/libraries/{id}/perms',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});


```


```ruby
require 'rest-client'
require 'json'


headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}


result = RestClient.post '/public/v1/libraries/{id}/perms',
  params: {
  }, headers: headers


p JSON.parse(result)


```


```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}


r = requests.post('/public/v1/libraries/{id}/perms', params={


}, headers = headers)


print r.json()


```


```java
URL obj = new URL("/public/v1/libraries/{id}/perms");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());


```


`POST /v1/libraries/{id}/perms`


*Specify the permissions for this library*


> Body parameter


```json
{
  "perms": [
    {
      "group_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "read": true,
      "write": true,
      "owner": true
    }
  ]
}
```


<h3 id="updateLibraryPerms-parameters">Parameters</h3>


|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Library ID|
|body|body|[ObjectPermsWrite](#schemaobjectpermswrite)|false|No description|


> Example responses


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "library": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name"
      }
    }
  },
  "links": {}
}
```


<h3 id="updateLibraryPerms-responses">Responses</h3>


|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[LibraryPermsResponseData](#schemalibrarypermsresponsedata)|


<aside class="success">
This operation does not require authentication
</aside>


# Schemas


<h2 id="tocSaliasfqn">AliasFqn</h2>


<a id="schemaaliasfqn"></a>


```json
{
  "library": "library_name",
  "ip": "ip_name",
  "line": "line_name",
  "alias": "GOLD"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|library|string|false|No description|
|ip|string|false|No description|
|line|string|false|No description|
|alias|string|false|No description|


<h2 id="tocSaliasfullview">AliasFullView</h2>


<a id="schemaaliasfullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "fqn": {
    "library": "library_name",
    "ip": "ip_name",
    "line": "line_name",
    "alias": "GOLD"
  },
  "creator": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "user_name"
  },
  "creation_timestamp": 1456353110888,
  "locked": true,
  "ipl": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name"
    }
  },
  "ipv": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name",
      "version": 1,
      "alias": "GOLD"
    }
  },
  "old_ipvs": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      }
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|fqn|[AliasFqn](#schemaaliasfqn)|false|No description|
|creator|[UserShortView](#schemausershortview)|false|No description|
|creation_timestamp|integer(int64)|false|No description|
|locked|boolean|false|No description|
|ipl|[IplShortView](#schemaiplshortview)|false|No description|
|ipv|[IpvShortView](#schemaipvshortview)|false|No description|
|old_ipvs|[[IpvShortView](#schemaipvshortview)]|false|No description|


<h2 id="tocSaliaslinksdata">AliasLinksData</h2>


<a id="schemaaliaslinksdata"></a>


```json
{
  "ipls": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353223268,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353223268,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    }
  },
  "ipvs": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|ipls|object|false|No description|
|» **additionalProperties**|[IplFullView](#schemaiplfullview)|false|No description|
|ipvs|object|false|No description|
|» **additionalProperties**|[IpvFullView](#schemaipvfullview)|false|No description|


<h2 id="tocSaliasresponsedata">AliasResponseData</h2>


<a id="schemaaliasresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name",
      "alias": "GOLD"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353110888,
    "locked": true,
    "ipl": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      }
    },
    "ipv": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      }
    },
    "old_ipvs": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      }
    ]
  },
  "links": {
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[AliasFullView](#schemaaliasfullview)|false|No description|
|links|[AliasLinksData](#schemaaliaslinksdata)|false|No description|


<h2 id="tocSaliasshortview">AliasShortView</h2>


<a id="schemaaliasshortview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "name": "GOLD"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|name|string|false|No description|


<h2 id="tocSattributeshortview">AttributeShortView</h2>


<a id="schemaattributeshortview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "name": "attribute_name"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|name|string|false|No description|


<h2 id="tocSgroupshortview">GroupShortView</h2>


<a id="schemagroupshortview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "name": "group_name"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|name|string|false|No description|


<h2 id="tocSipfqn">IpFqn</h2>


<a id="schemaipfqn"></a>


```json
{
  "library": "library_name",
  "ip": "ip_name"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|library|string|false|No description|
|ip|string|false|No description|


<h2 id="tocSipshortview">IpShortView</h2>


<a id="schemaipshortview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "fqn": {
    "library": "library_name",
    "ip": "ip_name"
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|fqn|[IpFqn](#schemaipfqn)|false|No description|


<h2 id="tocSiplfqn">IplFqn</h2>


<a id="schemaiplfqn"></a>


```json
{
  "library": "library_name",
  "ip": "ip_name",
  "line": "line_name"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|library|string|false|No description|
|ip|string|false|No description|
|line|string|false|No description|


<h2 id="tocSiplfullview">IplFullView</h2>


<a id="schemaiplfullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "fqn": {
    "library": "library_name",
    "ip": "ip_name",
    "line": "line_name"
  },
  "creator": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "user_name"
  },
  "creation_timestamp": 1456353223268,
  "ip": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "fqn": {
      "library": "library_name",
      "ip": "ip_name"
    }
  },
  "attributes": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "attribute_name"
    }
  ],
  "perms": [
    {
      "group": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      },
      "read": true,
      "write": true,
      "owner": true
    }
  ],
  "ipvs": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      }
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|fqn|[IplFqn](#schemaiplfqn)|false|No description|
|creator|[UserShortView](#schemausershortview)|false|No description|
|creation_timestamp|integer(int64)|false|No description|
|ip|[IpShortView](#schemaipshortview)|false|No description|
|attributes|[[AttributeShortView](#schemaattributeshortview)]|false|No description|
|perms|[[PermsView](#schemapermsview)]|false|No description|
|ipvs|[[IpvShortView](#schemaipvshortview)]|false|No description|


<h2 id="tocSiplshortview">IplShortView</h2>


<a id="schemaiplshortview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "fqn": {
    "library": "library_name",
    "ip": "ip_name",
    "line": "line_name"
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|fqn|[IplFqn](#schemaiplfqn)|false|No description|


<h2 id="tocSipvcontentsshortview">IpvContentsShortView</h2>


<a id="schemaipvcontentsshortview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "timestamp": 1456353223265
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|timestamp|integer(int64)|false|No description|


<h2 id="tocSipvfqn">IpvFqn</h2>


<a id="schemaipvfqn"></a>


```json
{
  "library": "library_name",
  "ip": "ip_name",
  "line": "line_name",
  "version": 1,
  "alias": "GOLD"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|library|string|false|No description|
|ip|string|false|No description|
|line|string|false|No description|
|version|integer(int64)|false|No description|
|alias|string|false|No description|


<h2 id="tocSipvfullview">IpvFullView</h2>


<a id="schemaipvfullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "fqn": {
    "library": "library_name",
    "ip": "ip_name",
    "line": "line_name",
    "version": 1,
    "alias": "GOLD"
  },
  "creator": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "user_name"
  },
  "creation_timestamp": 1456353533268,
  "ipl": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name"
    }
  },
  "version_message": "version_message",
  "repo_path": "//depot/xxx",
  "project_props": "--xxx xxxxx",
  "resources": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "private_resource": true
    }
  ],
  "contents": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "timestamp": 1456353223265
  },
  "source": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name",
      "version": 1,
      "alias": "GOLD"
    }
  },
  "current_aliases": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "GOLD"
    }
  ],
  "historic_aliases": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "GOLD"
    }
  ],
  "attributes": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "attribute_name"
    }
  ],
  "property_values": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "default_value": "default_value",
      "name": "property_name",
      "suffix": "property_suffix",
      "value": "property_value"
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|fqn|[IpvFqn](#schemaipvfqn)|false|No description|
|creator|[UserShortView](#schemausershortview)|false|No description|
|creation_timestamp|integer(int64)|false|No description|
|ipl|[IplShortView](#schemaiplshortview)|false|No description|
|version_message|string|false|No description|
|repo_path|string|false|No description|
|project_props|string|false|No description|
|resources|[[IpvResourceView](#schemaipvresourceview)]|false|No description|
|contents|[IpvContentsShortView](#schemaipvcontentsshortview)|false|No description|
|source|[IpvShortView](#schemaipvshortview)|false|No description|
|current_aliases|[[AliasShortView](#schemaaliasshortview)]|false|No description|
|historic_aliases|[[AliasShortView](#schemaaliasshortview)]|false|No description|
|attributes|[[AttributeShortView](#schemaattributeshortview)]|false|No description|
|property_values|[[PropertyValue](#schemapropertyvalue)]|false|No description|


<h2 id="tocSipvresourceview">IpvResourceView</h2>


<a id="schemaipvresourceview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "fqn": {
    "library": "library_name",
    "ip": "ip_name",
    "line": "line_name",
    "version": 1,
    "alias": "GOLD"
  },
  "private_resource": true
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|fqn|[IpvFqn](#schemaipvfqn)|false|No description|
|private_resource|boolean|false|No description|


<h2 id="tocSipvshortview">IpvShortView</h2>


<a id="schemaipvshortview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "fqn": {
    "library": "library_name",
    "ip": "ip_name",
    "line": "line_name",
    "version": 1,
    "alias": "GOLD"
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|fqn|[IpvFqn](#schemaipvfqn)|false|No description|


<h2 id="tocSmetadata">MetaData</h2>


<a id="schemametadata"></a>


```json
{
  "status_code": 200,
  "timestamp": 1236353533268,
  "duration": 6
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|status_code|integer(int32)|false|No description|
|timestamp|integer(int64)|false|No description|
|duration|integer(int64)|false|No description|


<h2 id="tocSpermsview">PermsView</h2>


<a id="schemapermsview"></a>


```json
{
  "group": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "group_name"
  },
  "read": true,
  "write": true,
  "owner": true
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|group|[GroupShortView](#schemagroupshortview)|false|No description|
|read|boolean|false|No description|
|write|boolean|false|No description|
|owner|boolean|false|No description|


<h2 id="tocSpropertyvalue">PropertyValue</h2>


<a id="schemapropertyvalue"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "default_value": "default_value",
  "name": "property_name",
  "suffix": "property_suffix",
  "value": "property_value"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|default_value|object|false|Object type of default_value is determined by value_type|
|name|string|false|No description|
|suffix|string|false|No description|
|value|object|false|Object type of default_value is determined by value_type|


<h2 id="tocSusershortview">UserShortView</h2>


<a id="schemausershortview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "name": "user_name"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|name|string|false|No description|


<h2 id="tocSid">Id</h2>


<a id="schemaid"></a>


```json
{}
```


### Properties


*None*


<h2 id="tocSipfullview">IpFullView</h2>


<a id="schemaipfullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "fqn": {
    "library": "library_name",
    "ip": "ip_name"
  },
  "creator": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "user_name"
  },
  "creation_timestamp": 1456353220568,
  "library": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "fqn": {
      "library": "library_name"
    }
  },
  "description": "ip_description",
  "dm_type": "P4",
  "host": "ip_hook",
  "hooks": {
    "hook_post_load": "post_load_hook",
    "hook_post_update": "post_update_hook",
    "hook_pre_release": "pre_release_hook",
    "hook_post_release": "post_release_hook"
  },
  "labels": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "label_name"
    }
  ],
  "ipls": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      }
    }
  ],
  "attributes": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "attribute_name"
    }
  ],
  "property_values": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "default_value": "default_value",
      "name": "property_name",
      "suffix": "property_suffix",
      "value": "property_value"
    }
  ],
  "property_sets": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "property_set_name"
    }
  ],
  "perms": [
    {
      "group": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      },
      "read": true,
      "write": true,
      "owner": true
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|fqn|[IpFqn](#schemaipfqn)|false|No description|
|creator|[UserShortView](#schemausershortview)|false|No description|
|creation_timestamp|integer(int64)|false|No description|
|library|[LibraryShortView](#schemalibraryshortview)|false|No description|
|description|string|false|No description|
|dm_type|string|false|No description|
|host|string|false|No description|
|hooks|[IpHook](#schemaiphook)|false|No description|
|labels|[[LabelShortView](#schemalabelshortview)]|false|No description|
|ipls|[[IplShortView](#schemaiplshortview)]|false|No description|
|attributes|[[AttributeShortView](#schemaattributeshortview)]|false|No description|
|property_values|[[PropertyValue](#schemapropertyvalue)]|false|No description|
|property_sets|[[PropertySetShortView](#schemapropertysetshortview)]|false|No description|
|perms|[[PermsView](#schemapermsview)]|false|No description|


<h2 id="tocSiphook">IpHook</h2>


<a id="schemaiphook"></a>


```json
{
  "hook_post_load": "post_load_hook",
  "hook_post_update": "post_update_hook",
  "hook_pre_release": "pre_release_hook",
  "hook_post_release": "post_release_hook"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|hook_post_load|string|false|No description|
|hook_post_update|string|false|No description|
|hook_pre_release|string|false|No description|
|hook_post_release|string|false|No description|


<h2 id="tocSipvreferenceusagelinksdata">IpvReferenceUsageLinksData</h2>


<a id="schemaipvreferenceusagelinksdata"></a>


```json
{
  "ips": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|ips|object|false|No description|
|» **additionalProperties**|[IpFullView](#schemaipfullview)|false|No description|


<h2 id="tocSipvreferenceusageresponsedata">IpvReferenceUsageResponseData</h2>


<a id="schemaipvreferenceusageresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "ipvs": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "parent_ids": "[xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx]"
      }
    ],
    "top_level_ips": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      }
    ]
  },
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[UsageView](#schemausageview)|false|No description|
|links|[IpvReferenceUsageLinksData](#schemaipvreferenceusagelinksdata)|false|No description|


<h2 id="tocSipvusageview">IpvUsageView</h2>


<a id="schemaipvusageview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "name": {
    "library": "library_name",
    "ip": "ip_name",
    "line": "line_name",
    "version": 1,
    "alias": "GOLD"
  },
  "parent_ids": "[xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx]"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|name|[IpvFqn](#schemaipvfqn)|false|No description|
|parent_ids|[[Id](#schemaid)]|false|No description|


<h2 id="tocSlabelshortview">LabelShortView</h2>


<a id="schemalabelshortview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "name": "label_name"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|name|string|false|No description|


<h2 id="tocSlibraryfqn">LibraryFqn</h2>


<a id="schemalibraryfqn"></a>


```json
{
  "library": "library_name"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|library|string|false|No description|


<h2 id="tocSlibraryshortview">LibraryShortView</h2>


<a id="schemalibraryshortview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "fqn": {
    "library": "library_name"
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|fqn|[LibraryFqn](#schemalibraryfqn)|false|No description|


<h2 id="tocSpropertysetshortview">PropertySetShortView</h2>


<a id="schemapropertysetshortview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "name": "property_set_name"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|name|string|false|No description|


<h2 id="tocSusageview">UsageView</h2>


<a id="schemausageview"></a>


```json
{
  "ipvs": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "parent_ids": "[xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx]"
    }
  ],
  "top_level_ips": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      }
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|ipvs|[[IpvUsageView](#schemaipvusageview)]|false|No description|
|top_level_ips|[[IpShortView](#schemaipshortview)]|false|No description|


<h2 id="tocSattributefullview">AttributeFullView</h2>


<a id="schemaattributefullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "name": "attribute_name",
  "value": "attribute_value",
  "creator": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "user_name"
  },
  "creation_timestamp": 1456353110568
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|name|string|false|No description|
|value|string|false|No description|
|creator|[UserShortView](#schemausershortview)|false|No description|
|creation_timestamp|integer(int64)|false|No description|


<h2 id="tocSattributelinksdata">AttributeLinksData</h2>


<a id="schemaattributelinksdata"></a>


```json
{}
```


### Properties


*None*


<h2 id="tocSattributeresponsedata">AttributeResponseData</h2>


<a id="schemaattributeresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "attribute_name",
    "value": "attribute_value",
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353110568
  },
  "links": {}
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[AttributeFullView](#schemaattributefullview)|false|No description|
|links|[AttributeLinksData](#schemaattributelinksdata)|false|No description|


<h2 id="tocSgroupfullview">GroupFullView</h2>


<a id="schemagroupfullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "name": "group_name",
  "description": "group_description",
  "builtin": true,
  "external": true,
  "parent_groups": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "group_name"
    }
  ],
  "child_groups": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "group_name"
    }
  ],
  "users": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|name|string|false|No description|
|description|string|false|No description|
|builtin|boolean|false|No description|
|external|boolean|false|No description|
|parent_groups|[[GroupShortView](#schemagroupshortview)]|false|No description|
|child_groups|[[GroupShortView](#schemagroupshortview)]|false|No description|
|users|[[UserShortView](#schemausershortview)]|false|No description|


<h2 id="tocSgrouplinksdata">GroupLinksData</h2>


<a id="schemagrouplinksdata"></a>


```json
{
  "groups": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "group_name",
      "description": "group_description",
      "builtin": true,
      "external": true,
      "parent_groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ],
      "child_groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ],
      "users": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "group_name",
      "description": "group_description",
      "builtin": true,
      "external": true,
      "parent_groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ],
      "child_groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ],
      "users": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        }
      ]
    }
  },
  "users": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "user_name",
      "full_name": "user_full_name",
      "email": "user_email",
      "description": "user_description",
      "builtin": true,
      "admin": true,
      "external": true,
      "groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "user_name",
      "full_name": "user_full_name",
      "email": "user_email",
      "description": "user_description",
      "builtin": true,
      "admin": true,
      "external": true,
      "groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ]
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|groups|object|false|No description|
|» **additionalProperties**|[GroupFullView](#schemagroupfullview)|false|No description|
|users|object|false|No description|
|» **additionalProperties**|[UserFullView](#schemauserfullview)|false|No description|


<h2 id="tocSgroupsresponsedata">GroupsResponseData</h2>


<a id="schemagroupsresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "group_name",
      "description": "group_description",
      "builtin": true,
      "external": true,
      "parent_groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ],
      "child_groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ],
      "users": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        }
      ]
    }
  ],
  "links": {
    "groups": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      }
    },
    "users": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "user_name",
        "full_name": "user_full_name",
        "email": "user_email",
        "description": "user_description",
        "builtin": true,
        "admin": true,
        "external": true,
        "groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "user_name",
        "full_name": "user_full_name",
        "email": "user_email",
        "description": "user_description",
        "builtin": true,
        "admin": true,
        "external": true,
        "groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[[GroupFullView](#schemagroupfullview)]|false|No description|
|links|[GroupLinksData](#schemagrouplinksdata)|false|No description|


<h2 id="tocSuserfullview">UserFullView</h2>


<a id="schemauserfullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "name": "user_name",
  "full_name": "user_full_name",
  "email": "user_email",
  "description": "user_description",
  "builtin": true,
  "admin": true,
  "external": true,
  "groups": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "group_name"
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|name|string|false|No description|
|full_name|string|false|No description|
|email|string|false|No description|
|description|string|false|No description|
|builtin|boolean|false|No description|
|admin|boolean|false|No description|
|external|boolean|false|No description|
|groups|[[GroupShortView](#schemagroupshortview)]|false|No description|


<h2 id="tocSgroupresponsedata">GroupResponseData</h2>


<a id="schemagroupresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "group_name",
    "description": "group_description",
    "builtin": true,
    "external": true,
    "parent_groups": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      }
    ],
    "child_groups": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      }
    ],
    "users": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      }
    ]
  },
  "links": {
    "groups": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      }
    },
    "users": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "user_name",
        "full_name": "user_full_name",
        "email": "user_email",
        "description": "user_description",
        "builtin": true,
        "admin": true,
        "external": true,
        "groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "user_name",
        "full_name": "user_full_name",
        "email": "user_email",
        "description": "user_description",
        "builtin": true,
        "admin": true,
        "external": true,
        "groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[GroupFullView](#schemagroupfullview)|false|No description|
|links|[GroupLinksData](#schemagrouplinksdata)|false|No description|


<h2 id="tocSipllinksdata">IplLinksData</h2>


<a id="schemaipllinksdata"></a>


```json
{
  "ips": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    }
  },
  "ipvs": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|ips|object|false|No description|
|» **additionalProperties**|[IpFullView](#schemaipfullview)|false|No description|
|ipvs|object|false|No description|
|» **additionalProperties**|[IpvFullView](#schemaipvfullview)|false|No description|


<h2 id="tocSiplsresponsedata">IplsResponseData</h2>


<a id="schemaiplsresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353223268,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    }
  ],
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[[IplFullView](#schemaiplfullview)]|false|No description|
|links|[IplLinksData](#schemaipllinksdata)|false|No description|


<h2 id="tocSiplresponsedata">IplResponseData</h2>


<a id="schemaiplresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353223268,
    "ip": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      }
    },
    "attributes": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "attribute_name"
      }
    ],
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "ipvs": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      }
    ]
  },
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[IplFullView](#schemaiplfullview)|false|No description|
|links|[IplLinksData](#schemaipllinksdata)|false|No description|


<h2 id="tocSfilelist">FileList</h2>


<a id="schemafilelist"></a>


```json
{
  "paths_array": [
    "string"
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|paths_array|[string]|false|No description|


<h2 id="tocSipvcontentsfullview">IpvContentsFullView</h2>


<a id="schemaipvcontentsfullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "timestamp": 1456455223268,
  "file_list": {
    "paths_array": [
      "string"
    ]
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|timestamp|integer(int64)|false|No description|
|file_list|[FileList](#schemafilelist)|false|No description|


<h2 id="tocSipvlinksdata">IpvLinksData</h2>


<a id="schemaipvlinksdata"></a>


```json
{
  "aliases": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353110888,
      "locked": true,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "ipv": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "old_ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353110888,
      "locked": true,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "ipv": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "old_ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    }
  },
  "ipls": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353223268,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353223268,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    }
  },
  "ipvs": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    }
  },
  "ipv_contents": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "timestamp": 1456455223268,
      "file_list": {
        "paths_array": [
          "string"
        ]
      }
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "timestamp": 1456455223268,
      "file_list": {
        "paths_array": [
          "string"
        ]
      }
    }
  },
  "property_definitions": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_def_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646655255268,
      "target_type": "target_type",
      "value_type": "value_type",
      "choice_values": "choice_values",
      "description": "property_def_description",
      "suffix": "property_def_suffix",
      "default_value": "default_value",
      "propagate_value": false
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_def_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646655255268,
      "target_type": "target_type",
      "value_type": "value_type",
      "choice_values": "choice_values",
      "description": "property_def_description",
      "suffix": "property_def_suffix",
      "default_value": "default_value",
      "propagate_value": false
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|aliases|object|false|No description|
|» **additionalProperties**|[AliasFullView](#schemaaliasfullview)|false|No description|
|ipls|object|false|No description|
|» **additionalProperties**|[IplFullView](#schemaiplfullview)|false|No description|
|ipvs|object|false|No description|
|» **additionalProperties**|[IpvFullView](#schemaipvfullview)|false|No description|
|ipv_contents|object|false|No description|
|» **additionalProperties**|[IpvContentsFullView](#schemaipvcontentsfullview)|false|No description|
|property_definitions|object|false|No description|
|» **additionalProperties**|[PropertyDefinitionFullView](#schemapropertydefinitionfullview)|false|No description|


<h2 id="tocSipvsresponsedata">IpvsResponseData</h2>


<a id="schemaipvsresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    }
  ],
  "links": {
    "aliases": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    },
    "ipv_contents": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[[IpvFullView](#schemaipvfullview)]|false|No description|
|links|[IpvLinksData](#schemaipvlinksdata)|false|No description|


<h2 id="tocSpropertydefinitionfullview">PropertyDefinitionFullView</h2>


<a id="schemapropertydefinitionfullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "name": "property_def_name",
  "creator": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "user_name"
  },
  "creation_timestamp": 1646655255268,
  "target_type": "target_type",
  "value_type": "value_type",
  "choice_values": "choice_values",
  "description": "property_def_description",
  "suffix": "property_def_suffix",
  "default_value": "default_value",
  "propagate_value": false
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|name|string|false|No description|
|creator|[UserShortView](#schemausershortview)|false|No description|
|creation_timestamp|integer(int64)|false|No description|
|target_type|string|false|No description|
|value_type|string|false|No description|
|choice_values|[string]|false|this field only shows when value_type is choice|
|description|string|false|No description|
|suffix|string|false|No description|
|default_value|object|false|Object type of default_value is determined by value_type|
|propagate_value|boolean|false|this field only shows when target_type value is IPV.|


<h2 id="tocSiplpermslinksdata">IplPermsLinksData</h2>


<a id="schemaiplpermslinksdata"></a>


```json
{}
```


### Properties


*None*


<h2 id="tocSiplpermsresponsedata">IplPermsResponseData</h2>


<a id="schemaiplpermsresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "ipl": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      }
    }
  },
  "links": {}
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[IplPermsView](#schemaiplpermsview)|false|No description|
|links|[IplPermsLinksData](#schemaiplpermslinksdata)|false|No description|


<h2 id="tocSiplpermsview">IplPermsView</h2>


<a id="schemaiplpermsview"></a>


```json
{
  "perms": [
    {
      "group": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      },
      "read": true,
      "write": true,
      "owner": true
    }
  ],
  "ipl": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name"
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|perms|[[PermsView](#schemapermsview)]|false|No description|
|ipl|[IplShortView](#schemaiplshortview)|false|No description|


<h2 id="tocSobjectpermswrite">ObjectPermsWrite</h2>


<a id="schemaobjectpermswrite"></a>


```json
{
  "perms": [
    {
      "group_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "read": true,
      "write": true,
      "owner": true
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|perms|[[PermsWrite](#schemapermswrite)]|false|No description|


<h2 id="tocSpermswrite">PermsWrite</h2>


<a id="schemapermswrite"></a>


```json
{
  "group_id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "read": true,
  "write": true,
  "owner": true
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|group_id|string|false|No description|
|read|boolean|false|No description|
|write|boolean|false|No description|
|owner|boolean|false|No description|


<h2 id="tocSiplvlinksdata">IplvLinksData</h2>


<a id="schemaiplvlinksdata"></a>


```json
{
  "aliases": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353110888,
      "locked": true,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "ipv": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "old_ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353110888,
      "locked": true,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "ipv": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "old_ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    }
  },
  "ipvs": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    }
  },
  "ipv_contents": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "timestamp": 1456455223268,
      "file_list": {
        "paths_array": [
          "string"
        ]
      }
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "timestamp": 1456455223268,
      "file_list": {
        "paths_array": [
          "string"
        ]
      }
    }
  },
  "labels": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "label_name",
      "type": "label_type",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455223268,
      "color": "#xxxxxx",
      "libraries": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "label_name",
      "type": "label_type",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455223268,
      "color": "#xxxxxx",
      "libraries": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ]
    }
  },
  "libraries": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455255268,
      "vendor": "vendor",
      "description": "library_description",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ],
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455255268,
      "vendor": "vendor",
      "description": "library_description",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ],
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ]
    }
  },
  "property_definitions": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_def_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646655255268,
      "target_type": "target_type",
      "value_type": "value_type",
      "choice_values": "choice_values",
      "description": "property_def_description",
      "suffix": "property_def_suffix",
      "default_value": "default_value",
      "propagate_value": false
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_def_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646655255268,
      "target_type": "target_type",
      "value_type": "value_type",
      "choice_values": "choice_values",
      "description": "property_def_description",
      "suffix": "property_def_suffix",
      "default_value": "default_value",
      "propagate_value": false
    }
  },
  "property_sets": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_set_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1667655255268,
      "description": "property_set_description",
      "property_definitions": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_def_name"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_set_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1667655255268,
      "description": "property_set_description",
      "property_definitions": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_def_name"
        }
      ]
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|aliases|object|false|No description|
|» **additionalProperties**|[AliasFullView](#schemaaliasfullview)|false|No description|
|ipvs|object|false|No description|
|» **additionalProperties**|[IpvFullView](#schemaipvfullview)|false|No description|
|ipv_contents|object|false|No description|
|» **additionalProperties**|[IpvContentsFullView](#schemaipvcontentsfullview)|false|No description|
|labels|object|false|No description|
|» **additionalProperties**|[LabelFullView](#schemalabelfullview)|false|No description|
|libraries|object|false|No description|
|» **additionalProperties**|[LibraryFullView](#schemalibraryfullview)|false|No description|
|property_definitions|object|false|No description|
|» **additionalProperties**|[PropertyDefinitionFullView](#schemapropertydefinitionfullview)|false|No description|
|property_sets|object|false|No description|
|» **additionalProperties**|[PropertySetFullView](#schemapropertysetfullview)|false|No description|


<h2 id="tocSiplvreadview">IplvReadView</h2>


<a id="schemaiplvreadview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "ip": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353220568,
    "library": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name"
      }
    },
    "description": "ip_description",
    "dm_type": "P4",
    "host": "ip_hook",
    "hooks": {
      "hook_post_load": "post_load_hook",
      "hook_post_update": "post_update_hook",
      "hook_pre_release": "pre_release_hook",
      "hook_post_release": "post_release_hook"
    },
    "labels": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "label_name"
      }
    ],
    "ipls": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      }
    ],
    "attributes": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "attribute_name"
      }
    ],
    "property_values": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "default_value": "default_value",
        "name": "property_name",
        "suffix": "property_suffix",
        "value": "property_value"
      }
    ],
    "property_sets": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "property_set_name"
      }
    ],
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ]
  },
  "ipl": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353223268,
    "ip": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      }
    },
    "attributes": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "attribute_name"
      }
    ],
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "ipvs": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      }
    ]
  },
  "ipv": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name",
      "version": 1,
      "alias": "GOLD"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353533268,
    "ipl": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      }
    },
    "version_message": "version_message",
    "repo_path": "//depot/xxx",
    "project_props": "--xxx xxxxx",
    "resources": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "private_resource": true
      }
    ],
    "contents": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "timestamp": 1456353223265
    },
    "source": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      }
    },
    "current_aliases": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "GOLD"
      }
    ],
    "historic_aliases": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "GOLD"
      }
    ],
    "attributes": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "attribute_name"
      }
    ],
    "property_values": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "default_value": "default_value",
        "name": "property_name",
        "suffix": "property_suffix",
        "value": "property_value"
      }
    ]
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|ip|[IpFullView](#schemaipfullview)|false|No description|
|ipl|[IplFullView](#schemaiplfullview)|false|No description|
|ipv|[IpvFullView](#schemaipvfullview)|false|No description|


<h2 id="tocSiplvsresponsedata">IplvsResponseData</h2>


<a id="schemaiplvsresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "ipv": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  ],
  "links": {
    "aliases": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    },
    "ipv_contents": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "libraries": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[[IplvReadView](#schemaiplvreadview)]|false|No description|
|links|[IplvLinksData](#schemaiplvlinksdata)|false|No description|


<h2 id="tocSlabelfullview">LabelFullView</h2>


<a id="schemalabelfullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "name": "label_name",
  "type": "label_type",
  "creator": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "user_name"
  },
  "creation_timestamp": 1646455223268,
  "color": "#xxxxxx",
  "libraries": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name"
      }
    }
  ],
  "ips": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      }
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|name|string|false|No description|
|type|string|false|No description|
|creator|[UserShortView](#schemausershortview)|false|No description|
|creation_timestamp|integer(int64)|false|No description|
|color|string|false|No description|
|libraries|[[LibraryShortView](#schemalibraryshortview)]|false|No description|
|ips|[[IpShortView](#schemaipshortview)]|false|No description|


<h2 id="tocSlibraryfullview">LibraryFullView</h2>


<a id="schemalibraryfullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "fqn": {
    "library": "library_name"
  },
  "creator": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "user_name"
  },
  "creation_timestamp": 1646455255268,
  "vendor": "vendor",
  "description": "library_description",
  "hooks": {
    "hook_post_load": "post_load_hook",
    "hook_post_update": "post_update_hook",
    "hook_pre_release": "pre_release_hook",
    "hook_post_release": "post_release_hook"
  },
  "attributes": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "attribute_name"
    }
  ],
  "ips": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      }
    }
  ],
  "labels": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "label_name"
    }
  ],
  "perms": [
    {
      "group": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      },
      "read": true,
      "write": true,
      "owner": true
    }
  ],
  "property_sets": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "property_set_name"
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|fqn|[LibraryFqn](#schemalibraryfqn)|false|No description|
|creator|[UserShortView](#schemausershortview)|false|No description|
|creation_timestamp|integer(int64)|false|No description|
|vendor|string|false|No description|
|description|string|false|No description|
|hooks|[LibraryHook](#schemalibraryhook)|false|No description|
|attributes|[[AttributeShortView](#schemaattributeshortview)]|false|No description|
|ips|[[IpShortView](#schemaipshortview)]|false|No description|
|labels|[[LabelShortView](#schemalabelshortview)]|false|No description|
|perms|[[PermsView](#schemapermsview)]|false|No description|
|property_sets|[[PropertySetShortView](#schemapropertysetshortview)]|false|No description|


<h2 id="tocSlibraryhook">LibraryHook</h2>


<a id="schemalibraryhook"></a>


```json
{
  "hook_post_load": "post_load_hook",
  "hook_post_update": "post_update_hook",
  "hook_pre_release": "pre_release_hook",
  "hook_post_release": "post_release_hook"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|hook_post_load|string|false|No description|
|hook_post_update|string|false|No description|
|hook_pre_release|string|false|No description|
|hook_post_release|string|false|No description|


<h2 id="tocSpropertydefinitionshortview">PropertyDefinitionShortView</h2>


<a id="schemapropertydefinitionshortview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "name": "property_def_name"
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|name|string|false|No description|


<h2 id="tocSpropertysetfullview">PropertySetFullView</h2>


<a id="schemapropertysetfullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "name": "property_set_name",
  "creator": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "user_name"
  },
  "creation_timestamp": 1667655255268,
  "description": "property_set_description",
  "property_definitions": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "property_def_name"
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|name|string|false|No description|
|creator|[UserShortView](#schemausershortview)|false|No description|
|creation_timestamp|integer(int64)|false|No description|
|description|string|false|No description|
|property_definitions|[[PropertyDefinitionShortView](#schemapropertydefinitionshortview)]|false|No description|


<h2 id="tocSiplvresponsedata">IplvResponseData</h2>


<a id="schemaiplvresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "ip": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    },
    "ipl": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353223268,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    },
    "ipv": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    }
  },
  "links": {
    "aliases": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    },
    "ipv_contents": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "libraries": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[IplvReadView](#schemaiplvreadview)|false|No description|
|links|[IplvLinksData](#schemaiplvlinksdata)|false|No description|


<h2 id="tocSiplinksdata">IpLinksData</h2>


<a id="schemaiplinksdata"></a>


```json
{
  "ipls": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353223268,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353223268,
      "ip": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "ipvs": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        }
      ]
    }
  },
  "labels": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "label_name",
      "type": "label_type",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455223268,
      "color": "#xxxxxx",
      "libraries": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "label_name",
      "type": "label_type",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455223268,
      "color": "#xxxxxx",
      "libraries": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ]
    }
  },
  "libraries": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455255268,
      "vendor": "vendor",
      "description": "library_description",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ],
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455255268,
      "vendor": "vendor",
      "description": "library_description",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ],
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ]
    }
  },
  "property_definitions": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_def_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646655255268,
      "target_type": "target_type",
      "value_type": "value_type",
      "choice_values": "choice_values",
      "description": "property_def_description",
      "suffix": "property_def_suffix",
      "default_value": "default_value",
      "propagate_value": false
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_def_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646655255268,
      "target_type": "target_type",
      "value_type": "value_type",
      "choice_values": "choice_values",
      "description": "property_def_description",
      "suffix": "property_def_suffix",
      "default_value": "default_value",
      "propagate_value": false
    }
  },
  "property_sets": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_set_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1667655255268,
      "description": "property_set_description",
      "property_definitions": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_def_name"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_set_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1667655255268,
      "description": "property_set_description",
      "property_definitions": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_def_name"
        }
      ]
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|ipls|object|false|No description|
|» **additionalProperties**|[IplFullView](#schemaiplfullview)|false|No description|
|labels|object|false|No description|
|» **additionalProperties**|[LabelFullView](#schemalabelfullview)|false|No description|
|libraries|object|false|No description|
|» **additionalProperties**|[LibraryFullView](#schemalibraryfullview)|false|No description|
|property_definitions|object|false|No description|
|» **additionalProperties**|[PropertyDefinitionFullView](#schemapropertydefinitionfullview)|false|No description|
|property_sets|object|false|No description|
|» **additionalProperties**|[PropertySetFullView](#schemapropertysetfullview)|false|No description|


<h2 id="tocSipsresponsedata">IpsResponseData</h2>


<a id="schemaipsresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    }
  ],
  "links": {
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "libraries": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[[IpFullView](#schemaipfullview)]|false|No description|
|links|[IpLinksData](#schemaiplinksdata)|false|No description|


<h2 id="tocSipresponsedata">IpResponseData</h2>


<a id="schemaipresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353220568,
    "library": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name"
      }
    },
    "description": "ip_description",
    "dm_type": "P4",
    "host": "ip_hook",
    "hooks": {
      "hook_post_load": "post_load_hook",
      "hook_post_update": "post_update_hook",
      "hook_pre_release": "pre_release_hook",
      "hook_post_release": "post_release_hook"
    },
    "labels": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "label_name"
      }
    ],
    "ipls": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      }
    ],
    "attributes": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "attribute_name"
      }
    ],
    "property_values": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "default_value": "default_value",
        "name": "property_name",
        "suffix": "property_suffix",
        "value": "property_value"
      }
    ],
    "property_sets": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "property_set_name"
      }
    ],
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ]
  },
  "links": {
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "libraries": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[IpFullView](#schemaipfullview)|false|No description|
|links|[IpLinksData](#schemaiplinksdata)|false|No description|


<h2 id="tocSippermslinksdata">IpPermsLinksData</h2>


<a id="schemaippermslinksdata"></a>


```json
{}
```


### Properties


*None*


<h2 id="tocSippermsresponsedata">IpPermsResponseData</h2>


<a id="schemaippermsresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "ip": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      }
    }
  },
  "links": {}
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[IpPermsView](#schemaippermsview)|false|No description|
|links|[IpPermsLinksData](#schemaippermslinksdata)|false|No description|


<h2 id="tocSippermsview">IpPermsView</h2>


<a id="schemaippermsview"></a>


```json
{
  "perms": [
    {
      "group": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      },
      "read": true,
      "write": true,
      "owner": true
    }
  ],
  "ip": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "fqn": {
      "library": "library_name",
      "ip": "ip_name"
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|perms|[[PermsView](#schemapermsview)]|false|No description|
|ip|[IpShortView](#schemaipshortview)|false|No description|


<h2 id="tocSipvresponsedata">IpvResponseData</h2>


<a id="schemaipvresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name",
      "version": 1,
      "alias": "GOLD"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1456353533268,
    "ipl": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name"
      }
    },
    "version_message": "version_message",
    "repo_path": "//depot/xxx",
    "project_props": "--xxx xxxxx",
    "resources": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "private_resource": true
      }
    ],
    "contents": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "timestamp": 1456353223265
    },
    "source": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      }
    },
    "current_aliases": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "GOLD"
      }
    ],
    "historic_aliases": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "GOLD"
      }
    ],
    "attributes": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "attribute_name"
      }
    ],
    "property_values": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "default_value": "default_value",
        "name": "property_name",
        "suffix": "property_suffix",
        "value": "property_value"
      }
    ]
  },
  "links": {
    "aliases": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    },
    "ipv_contents": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[IpvFullView](#schemaipvfullview)|false|No description|
|links|[IpvLinksData](#schemaipvlinksdata)|false|No description|


<h2 id="tocSipvtreeresponsedata">IpvTreeResponseData</h2>


<a id="schemaipvtreeresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name",
      "version": 1,
      "alias": "GOLD"
    },
    "resources": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    ]
  },
  "links": {
    "aliases": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353110888,
        "locked": true,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "old_ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipls": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353223268,
        "ip": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "ipvs": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          }
        ]
      }
    },
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    },
    "ipv_contents": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "timestamp": 1456455223268,
        "file_list": {
          "paths_array": [
            "string"
          ]
        }
      }
    },
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[IpvTreeView](#schemaipvtreeview)|false|No description|
|links|[IpvLinksData](#schemaipvlinksdata)|false|No description|


<h2 id="tocSipvtreeview">IpvTreeView</h2>


<a id="schemaipvtreeview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "fqn": {
    "library": "library_name",
    "ip": "ip_name",
    "line": "line_name",
    "version": 1,
    "alias": "GOLD"
  },
  "resources": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|fqn|[IpvFqn](#schemaipvfqn)|false|No description|
|resources|[[IpvFullView](#schemaipvfullview)]|false|No description|


<h2 id="tocSlabellinksdata">LabelLinksData</h2>


<a id="schemalabellinksdata"></a>


```json
{
  "ips": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    }
  },
  "libraries": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455255268,
      "vendor": "vendor",
      "description": "library_description",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ],
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455255268,
      "vendor": "vendor",
      "description": "library_description",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ],
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ]
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|ips|object|false|No description|
|» **additionalProperties**|[IpFullView](#schemaipfullview)|false|No description|
|libraries|object|false|No description|
|» **additionalProperties**|[LibraryFullView](#schemalibraryfullview)|false|No description|


<h2 id="tocSlabelresponsedata">LabelResponseData</h2>


<a id="schemalabelresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "label_name",
    "type": "label_type",
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1646455223268,
    "color": "#xxxxxx",
    "libraries": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      }
    ],
    "ips": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      }
    ]
  },
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    },
    "libraries": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455255268,
        "vendor": "vendor",
        "description": "library_description",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ],
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[LabelFullView](#schemalabelfullview)|false|No description|
|links|[LabelLinksData](#schemalabellinksdata)|false|No description|


<h2 id="tocSpropertydefinitionlinksdata">PropertyDefinitionLinksData</h2>


<a id="schemapropertydefinitionlinksdata"></a>


```json
{}
```


### Properties


*None*


<h2 id="tocSpropertydefinitionresponsedata">PropertyDefinitionResponseData</h2>


<a id="schemapropertydefinitionresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "property_def_name",
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1646655255268,
    "target_type": "target_type",
    "value_type": "value_type",
    "choice_values": "choice_values",
    "description": "property_def_description",
    "suffix": "property_def_suffix",
    "default_value": "default_value",
    "propagate_value": false
  },
  "links": {}
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[PropertyDefinitionFullView](#schemapropertydefinitionfullview)|false|No description|
|links|[PropertyDefinitionLinksData](#schemapropertydefinitionlinksdata)|false|No description|


<h2 id="tocSpropertysetlinksdata">PropertySetLinksData</h2>


<a id="schemapropertysetlinksdata"></a>


```json
{
  "property_definitions": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_def_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646655255268,
      "target_type": "target_type",
      "value_type": "value_type",
      "choice_values": "choice_values",
      "description": "property_def_description",
      "suffix": "property_def_suffix",
      "default_value": "default_value",
      "propagate_value": false
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_def_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646655255268,
      "target_type": "target_type",
      "value_type": "value_type",
      "choice_values": "choice_values",
      "description": "property_def_description",
      "suffix": "property_def_suffix",
      "default_value": "default_value",
      "propagate_value": false
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|property_definitions|object|false|No description|
|» **additionalProperties**|[PropertyDefinitionFullView](#schemapropertydefinitionfullview)|false|No description|


<h2 id="tocSpropertysetresponsedata">PropertySetResponseData</h2>


<a id="schemapropertysetresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "property_set_name",
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1667655255268,
    "description": "property_set_description",
    "property_definitions": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "property_def_name"
      }
    ]
  },
  "links": {
    "property_definitions": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_def_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646655255268,
        "target_type": "target_type",
        "value_type": "value_type",
        "choice_values": "choice_values",
        "description": "property_def_description",
        "suffix": "property_def_suffix",
        "default_value": "default_value",
        "propagate_value": false
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[PropertySetFullView](#schemapropertysetfullview)|false|No description|
|links|[PropertySetLinksData](#schemapropertysetlinksdata)|false|No description|


<h2 id="tocScomponentinfodata">ComponentInfoData</h2>


<a id="schemacomponentinfodata"></a>


```json
{
  "version": {
    "major": 2,
    "minor": 15,
    "patch": 0
  },
  "release": true
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|version|[Version](#schemaversion)|false|No description|
|release|boolean|false|No description|


<h2 id="tocSsysteminfodata">SystemInfoData</h2>


<a id="schemasysteminfodata"></a>


```json
{
  "server": {
    "version": {
      "major": 2,
      "minor": 15,
      "patch": 0
    },
    "release": true
  },
  "extension": {
    "version": {
      "major": 2,
      "minor": 15,
      "patch": 0
    },
    "release": true
  },
  "neo4j_version": {
    "major": 2,
    "minor": 15,
    "patch": 0
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|server|[ComponentInfoData](#schemacomponentinfodata)|false|No description|
|extension|[ComponentInfoData](#schemacomponentinfodata)|false|No description|
|neo4j_version|[Version](#schemaversion)|false|No description|


<h2 id="tocSsystemlinksdata">SystemLinksData</h2>


<a id="schemasystemlinksdata"></a>


```json
{}
```


### Properties


*None*


<h2 id="tocSsystemresponsedata">SystemResponseData</h2>


<a id="schemasystemresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "server": {
      "version": {
        "major": 2,
        "minor": 15,
        "patch": 0
      },
      "release": true
    },
    "extension": {
      "version": {
        "major": 2,
        "minor": 15,
        "patch": 0
      },
      "release": true
    },
    "neo4j_version": {
      "major": 2,
      "minor": 15,
      "patch": 0
    }
  },
  "links": {}
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[SystemInfoData](#schemasysteminfodata)|false|No description|
|links|[SystemLinksData](#schemasystemlinksdata)|false|No description|


<h2 id="tocSversion">Version</h2>


<a id="schemaversion"></a>


```json
{
  "major": 2,
  "minor": 15,
  "patch": 0
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|major|integer(int32)|false|No description|
|minor|integer(int32)|false|No description|
|patch|integer(int32)|false|No description|


<h2 id="tocSuserlinksdata">UserLinksData</h2>


<a id="schemauserlinksdata"></a>


```json
{
  "groups": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "group_name",
      "description": "group_description",
      "builtin": true,
      "external": true,
      "parent_groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ],
      "child_groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ],
      "users": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "group_name",
      "description": "group_description",
      "builtin": true,
      "external": true,
      "parent_groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ],
      "child_groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ],
      "users": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        }
      ]
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|groups|object|false|No description|
|» **additionalProperties**|[GroupFullView](#schemagroupfullview)|false|No description|


<h2 id="tocSuserresponsedata">UserResponseData</h2>


<a id="schemauserresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "name": "user_name",
    "full_name": "user_full_name",
    "email": "user_email",
    "description": "user_description",
    "builtin": true,
    "admin": true,
    "external": true,
    "groups": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      }
    ]
  },
  "links": {
    "groups": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[UserFullView](#schemauserfullview)|false|No description|
|links|[UserLinksData](#schemauserlinksdata)|false|No description|


<h2 id="tocSusersresponsedata">UsersResponseData</h2>


<a id="schemausersresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "user_name",
      "full_name": "user_full_name",
      "email": "user_email",
      "description": "user_description",
      "builtin": true,
      "admin": true,
      "external": true,
      "groups": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        }
      ]
    }
  ],
  "links": {
    "groups": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "group_name",
        "description": "group_description",
        "builtin": true,
        "external": true,
        "parent_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "child_groups": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          }
        ],
        "users": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[[UserFullView](#schemauserfullview)]|false|No description|
|links|[UserLinksData](#schemauserlinksdata)|false|No description|


<h2 id="tocSsnapshotid">SnapshotId</h2>


<a id="schemasnapshotid"></a>


```json
{
  "library": "library_name",
  "ip": "ip_name",
  "line": "line_name",
  "version": 1,
  "alias": "GOLD",
  "snapshot": 0
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|library|string|false|No description|
|ip|string|false|No description|
|line|string|false|No description|
|version|integer(int64)|false|No description|
|alias|string|false|No description|
|snapshot|integer(int64)|false|No description|


<h2 id="tocSsnapshotshortviewdata">SnapshotShortViewData</h2>


<a id="schemasnapshotshortviewdata"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "snapshot_id": {
    "library": "library_name",
    "ip": "ip_name",
    "line": "line_name",
    "version": 1,
    "alias": "GOLD",
    "snapshot": 0
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|href|string|false|No description|
|snapshot_id|[SnapshotId](#schemasnapshotid)|false|No description|


<h2 id="tocSworkspacefullview">WorkspaceFullView</h2>


<a id="schemaworkspacefullview"></a>


```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "update_count": 1,
  "creator": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "user_name"
  },
  "creation_timestamp": 1667652355268,
  "path": "//depot/xxx",
  "p4_client": "workspace_p4_client",
  "snapshot": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "snapshot_id": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name",
      "version": 1,
      "alias": "GOLD",
      "snapshot": 0
    }
  },
  "top_ipv": {
    "ipv": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      }
    },
    "alias": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "GOLD"
    },
    "last_updater": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "last_update_timestamp": 1667659955268
  },
  "resources": [
    {
      "ipv": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "alias": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "GOLD"
      },
      "last_updater": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "last_update_timestamp": 1667659955268
    }
  ]
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|id|string|false|No description|
|update_count|integer(int64)|false|No description|
|creator|[UserShortView](#schemausershortview)|false|No description|
|creation_timestamp|integer(int64)|false|No description|
|path|string|false|No description|
|p4_client|string|false|Field only present for IPs of DM_TYPE = P4|
|snapshot|[SnapshotShortViewData](#schemasnapshotshortviewdata)|false|No description|
|top_ipv|[WorkspaceResourceShortView](#schemaworkspaceresourceshortview)|false|No description|
|resources|[[WorkspaceResourceShortView](#schemaworkspaceresourceshortview)]|false|No description|


<h2 id="tocSworkspacelinksdata">WorkspaceLinksData</h2>


<a id="schemaworkspacelinksdata"></a>


```json
{
  "ipvs": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353533268,
      "ipl": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name"
        }
      },
      "version_message": "version_message",
      "repo_path": "//depot/xxx",
      "project_props": "--xxx xxxxx",
      "resources": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          },
          "private_resource": true
        }
      ],
      "contents": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp": 1456353223265
      },
      "source": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "current_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "historic_aliases": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ]
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|ipvs|object|false|No description|
|» **additionalProperties**|[IpvFullView](#schemaipvfullview)|false|No description|


<h2 id="tocSworkspaceresourceshortview">WorkspaceResourceShortView</h2>


<a id="schemaworkspaceresourceshortview"></a>


```json
{
  "ipv": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "fqn": {
      "library": "library_name",
      "ip": "ip_name",
      "line": "line_name",
      "version": 1,
      "alias": "GOLD"
    }
  },
  "alias": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "GOLD"
  },
  "last_updater": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "name": "user_name"
  },
  "last_update_timestamp": 1667659955268
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|ipv|[IpvShortView](#schemaipvshortview)|false|No description|
|alias|[AliasShortView](#schemaaliasshortview)|false|No description|
|last_updater|[UserShortView](#schemausershortview)|false|No description|
|last_update_timestamp|integer(int64)|false|No description|


<h2 id="tocSworkspaceresponsedata">WorkspaceResponseData</h2>


<a id="schemaworkspaceresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1667652355268,
    "path": "//depot/xxx",
    "p4_client": "workspace_p4_client",
    "snapshot": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "snapshot_id": {
        "library": "library_name",
        "ip": "ip_name",
        "line": "line_name",
        "version": 1,
        "alias": "GOLD",
        "snapshot": 0
      }
    },
    "top_ipv": {
      "ipv": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        }
      },
      "alias": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "GOLD"
      },
      "last_updater": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "last_update_timestamp": 1667659955268
    },
    "resources": [
      {
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "alias": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        },
        "last_updater": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "last_update_timestamp": 1667659955268
      }
    ]
  },
  "links": {
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[WorkspaceFullView](#schemaworkspacefullview)|false|No description|
|links|[WorkspaceLinksData](#schemaworkspacelinksdata)|false|No description|


<h2 id="tocSworkspacesresponsedata">WorkspacesResponseData</h2>


<a id="schemaworkspacesresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1667652355268,
      "path": "//depot/xxx",
      "p4_client": "workspace_p4_client",
      "snapshot": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "snapshot_id": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD",
          "snapshot": 0
        }
      },
      "top_ipv": {
        "ipv": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "alias": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "GOLD"
        },
        "last_updater": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "last_update_timestamp": 1667659955268
      },
      "resources": [
        {
          "ipv": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            }
          },
          "alias": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          },
          "last_updater": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "user_name"
          },
          "last_update_timestamp": 1667659955268
        }
      ]
    }
  ],
  "links": {
    "ipvs": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name",
          "line": "line_name",
          "version": 1,
          "alias": "GOLD"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353533268,
        "ipl": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        },
        "version_message": "version_message",
        "repo_path": "//depot/xxx",
        "project_props": "--xxx xxxxx",
        "resources": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name",
              "version": 1,
              "alias": "GOLD"
            },
            "private_resource": true
          }
        ],
        "contents": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "timestamp": 1456353223265
        },
        "source": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name",
            "version": 1,
            "alias": "GOLD"
          }
        },
        "current_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "historic_aliases": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "GOLD"
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[[WorkspaceFullView](#schemaworkspacefullview)]|false|No description|
|links|[WorkspaceLinksData](#schemaworkspacelinksdata)|false|No description|


<h2 id="tocSlibrariesresponsedata">LibrariesResponseData</h2>


<a id="schemalibrariesresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": [
    {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455255268,
      "vendor": "vendor",
      "description": "library_description",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ],
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ]
    }
  ],
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[[LibraryFullView](#schemalibraryfullview)]|false|No description|
|links|[LibraryLinksData](#schemalibrarylinksdata)|false|No description|


<h2 id="tocSlibrarylinksdata">LibraryLinksData</h2>


<a id="schemalibrarylinksdata"></a>


```json
{
  "ips": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "fqn": {
        "library": "library_name",
        "ip": "ip_name"
      },
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1456353220568,
      "library": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name"
        }
      },
      "description": "ip_description",
      "dm_type": "P4",
      "host": "ip_hook",
      "hooks": {
        "hook_post_load": "post_load_hook",
        "hook_post_update": "post_update_hook",
        "hook_pre_release": "pre_release_hook",
        "hook_post_release": "post_release_hook"
      },
      "labels": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "label_name"
        }
      ],
      "ipls": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name",
            "line": "line_name"
          }
        }
      ],
      "attributes": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "attribute_name"
        }
      ],
      "property_values": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "default_value": "default_value",
          "name": "property_name",
          "suffix": "property_suffix",
          "value": "property_value"
        }
      ],
      "property_sets": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_set_name"
        }
      ],
      "perms": [
        {
          "group": {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "group_name"
          },
          "read": true,
          "write": true,
          "owner": true
        }
      ]
    }
  },
  "labels": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "label_name",
      "type": "label_type",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455223268,
      "color": "#xxxxxx",
      "libraries": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "label_name",
      "type": "label_type",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1646455223268,
      "color": "#xxxxxx",
      "libraries": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        }
      ],
      "ips": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name",
            "ip": "ip_name"
          }
        }
      ]
    }
  },
  "property_sets": {
    "property1": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_set_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1667655255268,
      "description": "property_set_description",
      "property_definitions": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_def_name"
        }
      ]
    },
    "property2": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "update_count": 1,
      "name": "property_set_name",
      "creator": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "user_name"
      },
      "creation_timestamp": 1667655255268,
      "description": "property_set_description",
      "property_definitions": [
        {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "property_def_name"
        }
      ]
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|ips|object|false|No description|
|» **additionalProperties**|[IpFullView](#schemaipfullview)|false|No description|
|labels|object|false|No description|
|» **additionalProperties**|[LabelFullView](#schemalabelfullview)|false|No description|
|property_sets|object|false|No description|
|» **additionalProperties**|[PropertySetFullView](#schemapropertysetfullview)|false|No description|


<h2 id="tocSlibraryresponsedata">LibraryResponseData</h2>


<a id="schemalibraryresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "update_count": 1,
    "fqn": {
      "library": "library_name"
    },
    "creator": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "name": "user_name"
    },
    "creation_timestamp": 1646455255268,
    "vendor": "vendor",
    "description": "library_description",
    "hooks": {
      "hook_post_load": "post_load_hook",
      "hook_post_update": "post_update_hook",
      "hook_pre_release": "pre_release_hook",
      "hook_post_release": "post_release_hook"
    },
    "attributes": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "attribute_name"
      }
    ],
    "ips": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        }
      }
    ],
    "labels": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "label_name"
      }
    ],
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "property_sets": [
      {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "property_set_name"
      }
    ]
  },
  "links": {
    "ips": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "fqn": {
          "library": "library_name",
          "ip": "ip_name"
        },
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1456353220568,
        "library": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "fqn": {
            "library": "library_name"
          }
        },
        "description": "ip_description",
        "dm_type": "P4",
        "host": "ip_hook",
        "hooks": {
          "hook_post_load": "post_load_hook",
          "hook_post_update": "post_update_hook",
          "hook_pre_release": "pre_release_hook",
          "hook_post_release": "post_release_hook"
        },
        "labels": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "label_name"
          }
        ],
        "ipls": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name",
              "line": "line_name"
            }
          }
        ],
        "attributes": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "attribute_name"
          }
        ],
        "property_values": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "default_value": "default_value",
            "name": "property_name",
            "suffix": "property_suffix",
            "value": "property_value"
          }
        ],
        "property_sets": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_set_name"
          }
        ],
        "perms": [
          {
            "group": {
              "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
              "name": "group_name"
            },
            "read": true,
            "write": true,
            "owner": true
          }
        ]
      }
    },
    "labels": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "label_name",
        "type": "label_type",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1646455223268,
        "color": "#xxxxxx",
        "libraries": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name"
            }
          }
        ],
        "ips": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "fqn": {
              "library": "library_name",
              "ip": "ip_name"
            }
          }
        ]
      }
    },
    "property_sets": {
      "property1": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      },
      "property2": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "update_count": 1,
        "name": "property_set_name",
        "creator": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "user_name"
        },
        "creation_timestamp": 1667655255268,
        "description": "property_set_description",
        "property_definitions": [
          {
            "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
            "name": "property_def_name"
          }
        ]
      }
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[LibraryFullView](#schemalibraryfullview)|false|No description|
|links|[LibraryLinksData](#schemalibrarylinksdata)|false|No description|


<h2 id="tocSlibrarypermslinksdata">LibraryPermsLinksData</h2>


<a id="schemalibrarypermslinksdata"></a>


```json
{}
```


### Properties


*None*


<h2 id="tocSlibrarypermsresponsedata">LibraryPermsResponseData</h2>


<a id="schemalibrarypermsresponsedata"></a>


```json
{
  "metadata": {
    "status_code": 200,
    "timestamp": 1236353533268,
    "duration": 6
  },
  "data": {
    "perms": [
      {
        "group": {
          "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "name": "group_name"
        },
        "read": true,
        "write": true,
        "owner": true
      }
    ],
    "library": {
      "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      "fqn": {
        "library": "library_name"
      }
    }
  },
  "links": {}
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|metadata|[MetaData](#schemametadata)|false|No description|
|data|[LibraryPermsView](#schemalibrarypermsview)|false|No description|
|links|[LibraryPermsLinksData](#schemalibrarypermslinksdata)|false|No description|


<h2 id="tocSlibrarypermsview">LibraryPermsView</h2>


<a id="schemalibrarypermsview"></a>


```json
{
  "perms": [
    {
      "group": {
        "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "name": "group_name"
      },
      "read": true,
      "write": true,
      "owner": true
    }
  ],
  "library": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "href": "public/v1/{object_type}/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "fqn": {
      "library": "library_name"
    }
  }
}
```


### Properties


|Name|Type|Required|Description|
|---|---|---|---|
|perms|[[PermsView](#schemapermsview)]|false|No description|
|library|[LibraryShortView](#schemalibraryshortview)|false|No description|


