# StateRepository::ServiceRpc::Initialize(void)

- ea: `0x18009d38c`
- end: `0x18009d588`
- name: `?Initialize@ServiceRpc@StateRepository@@SAJXZ`
- size: `508`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180176e70`
- `0x1801a3984`

## callees

- `0x18000e8dc`
- `0x18001a9e0`
- `0x180050364`
- `0x18006ab30`
- `0x18009d38c`
- `0x1800afc64`
- `0x1800b4dbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d557`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009d557`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d3a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009d3a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d541`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d541`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009d445`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009d445`
- `RPCRT4!RpcServerUseProtseqW` at `0x18009d3f5`
- `RPCRT4!RpcServerUseProtseqW` at `0x18009d3f5`
- `RPCRT4!RpcServerRegisterIf3` at `0x18009d4a3`
- `RPCRT4!RpcServerRegisterIf3` at `0x18009d4a3`
- `RPCRT4!RpcServerInqBindings` at `0x18009d4cb`
- `RPCRT4!RpcServerInqBindings` at `0x18009d4cb`
- `RPCRT4!RpcEpRegisterW` at `0x18009d514`
- `RPCRT4!RpcEpRegisterW` at `0x18009d514`

## string_xrefs

- `0x18009d3b9`: `onecore\base\appmodel\staterepository\winrt\client\lib\servicerpc.cpp`
- `0x18009d403`: `onecore\base\appmodel\staterepository\winrt\client\lib\servicerpc.cpp`
- `0x18009d453`: `onecore\base\appmodel\staterepository\winrt\client\lib\servicerpc.cpp`
- `0x18009d4b1`: `onecore\base\appmodel\staterepository\winrt\client\lib\servicerpc.cpp`
- `0x18009d4d9`: `onecore\base\appmodel\staterepository\winrt\client\lib\servicerpc.cpp`
- `0x18009d522`: `onecore\base\appmodel\staterepository\winrt\client\lib\servicerpc.cpp`

## pseudocode

```c

```
