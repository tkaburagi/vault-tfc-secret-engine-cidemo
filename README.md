## User API TOKEN

generate an user api token


setup config
```
vault write terraform/config \
    token=${APITOKEN}
```

retrieve user id
```
curl \
  --header "Authorization: Bearer $TOKEN" \
  --header "Content-Type: application/vnd.api+json" \
  --request GET \
  https://app.terraform.io/api/v2/account/details
```

setup role
```
 vault write terraform/roles/user-api user_id=user-xxxxxxxx
 ```

generate the tfc token
```
vault read terraform/creds/user-api
```

## Org API Token

setup role
```
vault write terraform/role/org-api organization=${ORGNAME}
```

generate the tfc token
```
vault read terraform/creds/org-api
```