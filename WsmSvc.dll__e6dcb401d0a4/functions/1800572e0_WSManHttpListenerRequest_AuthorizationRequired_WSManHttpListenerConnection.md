# WSManHttpListenerRequest::AuthorizationRequired(WSManHttpListenerConnection *)

- ea: `0x1800572e0`
- end: `0x1800576e4`
- name: `?AuthorizationRequired@WSManHttpListenerRequest@@AEAAHPEAVWSManHttpListenerConnection@@@Z`
- size: `1028`
- prototype: `__int64 __fastcall(WSManHttpListenerRequest *__hidden this, struct WSManHttpListenerConnection *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180054c30`

## callees

- `0x180005d10`
- `0x1800572e0`
- `0x1800576f0`
- `0x18005c09c`
- `0x180071400`
- `0x1800723d4`
- `0x1800dc630`
- `0x180112380`
- `0x1801123a8`
- `0x18011a6d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800575b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800575d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800575b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800575d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800573be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800573f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800573be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800573f4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800575a8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800575a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005756f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180057583`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005756f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180057583`
- `SspiCli!QuerySecurityContextToken` at `0x180057359`
- `SspiCli!QuerySecurityContextToken` at `0x180057359`

## string_xrefs

- `0x1800574b4`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`
- `0x1800576d3`: `onecore\admin\wmi\wmx\service\wsmanhttplistener.cpp`

## pseudocode

```c

```
