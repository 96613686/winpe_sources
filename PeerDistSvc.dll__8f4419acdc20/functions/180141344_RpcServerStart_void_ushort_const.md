# RpcServerStart(void *,ushort const *)

- ea: `0x180141344`
- end: `0x1801415fa`
- name: `?RpcServerStart@@YAJPEAXPEBG@Z`
- size: `694`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180122590`

## callees

- `0x180004374`
- `0x180008290`
- `0x180141344`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801413c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801413c5`
- `RPCRT4!RpcServerRegisterIf3` at `0x1801414c1`
- `RPCRT4!RpcServerRegisterIf3` at `0x1801414c1`
- `RPCRT4!RpcEpRegisterW` at `0x18014153c`
- `RPCRT4!RpcEpRegisterW` at `0x18014153c`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180141450`
- `RPCRT4!RpcServerRegisterAuthInfoW` at `0x180141450`
- `RPCRT4!RpcBindingVectorFree` at `0x1801415c6`
- `RPCRT4!RpcBindingVectorFree` at `0x1801415c6`
- `RPCRT4!RpcServerInqBindings` at `0x1801414fc`
- `RPCRT4!RpcServerInqBindings` at `0x1801414fc`
- `RPCRT4!RpcServerUseProtseqW` at `0x18014140b`
- `RPCRT4!RpcServerUseProtseqW` at `0x18014140b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801413bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801413bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801415d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801415d6`

## pseudocode

```c

```
