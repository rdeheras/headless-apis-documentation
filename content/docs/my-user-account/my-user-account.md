---
mainPage: false
title: My User Account
description: My User Account Endpoint documentation
weight: 1
---

## The My User Account Model

The following fields are currently supported:

* **birthDate**: the date of birth of the user.
* **alternateName**: the alias of the user.
* **dashboardURL**: the user's dashboard URL.
* **email**: the user's email address.
* **familyName**: the user's last name.
* **gender**: the user's gender.
* **givenName**: the user's name.
* **name**: the user's full name.
* **profileURL**: the user's profile URL.

Also this model offers the following links:

* **roles**: the user's roles collection.
* **myOrganizations**: the list of organizations that the user is member.
* **myWebSites**: the list of web sites that the user is member.
* **tasksAssignedToMe**: the list of the tasks assigned to the user.
* **tasksAssignedToMyRoles**: the list of the tasks assigned to the user's roles.

The model also have the contact information:

* **address**: the list of postal addresses of the user.
* **email**: the list of email addresses of the user.
* **telephone**: the list of telephones of the user.
* **webUrl**: the list of user's webs.

## My User Account Collection

This is an example of the request: 

```bash
curl --request GET \
  --url http://localhost:8080/o/api/p/my-user-account \
  --header 'Accept: application/hal+json'
```

The response in `json HAL` format will contain inside the `_embedded` section, the user logged under the key `Liferay:UserAccount`.

```json
{
    "total": 1,
    "count": 1,
    "_links": {
        "self": {
            "href": "http://localhost:8080/o/api/p/my-user-account?page=1&per_page=30"
        },
        "first": {
            "href": "http://localhost:8080/o/api/p/my-user-account?page=1&per_page=30"
        },
        "last": {
            "href": "http://localhost:8080/o/api/p/my-user-account?page=1&per_page=30"
        },
        "collection": {
            "href": "http://localhost:8080/o/api/p/my-user-account"
        }
    },
    "_embedded": {
        "Liferay:UserAccount": [
            {
                "birthDate": "1970-01-01T00:00Z",
                "alternateName": "test",
                "dashboardURL": "http://localhost:8080/user/test",
                "email": "test@liferay.com",
                "familyName": "Test",
                "gender": "male",
                "givenName": "Test",
                "name": "Test Test",
                "profileURL": "http://localhost:8080/web/test",
                "_links": {
                    "self": {
                        "href": "http://localhost:8080/o/api/p/my-user-account/20139"
                    },
                    "roles": {
                        "href": "http://localhost:8080/o/api/p/my-user-account/20139/roles"
                    },
                    "myOrganizations": {
                        "href": "http://localhost:8080/o/api/p/my-user-account/20139/organization"
                    },
                    "myWebSites": {
                        "href": "http://localhost:8080/o/api/p/my-user-account/20139/web-site"
                    },
                    "tasksAssignedToMe": {
                        "href": "http://localhost:8080/o/api/p/r/workflow-tasks/assigned-to-me"
                    },
                    "tasksAssignedToMyRoles": {
                        "href": "http://localhost:8080/o/api/p/r/workflow-tasks/assigned-to-my-roles"
                    }
                },
                "_embedded": {
                    "contactInformation": {
                        "_links": {
                            "address": {
                                "href": "http://localhost:8080/o/api/p/r/addresses/20006:20139"
                            },
                            "email": {
                                "href": "http://localhost:8080/o/api/p/r/emails/20006:20139"
                            },
                            "telephone": {
                                "href": "http://localhost:8080/o/api/p/r/phones/20006:20139"
                            },
                            "webUrl": {
                                "href": "http://localhost:8080/o/api/p/r/web-urls/20006:20139"
                            }
                        }
                    }
                }
            }
        ]
    }
}
```

When navigating through the list of entities, the link to each entity can be found with the rel `self`.

You can found more examples in the following [link](/docs/my-user-account/examples.html).
