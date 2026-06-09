# LsaICLookupSidsWithCreds

- ea: `0x180061a54`
- end: `0x180061c45`
- name: `LsaICLookupSidsWithCreds`
- size: `497`
- prototype: `__int64 __fastcall(int, int, int, int, RPC_AUTH_IDENTITY_HANDLE, unsigned int, int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18003e780`

## callees

- `0x18002c9b0`
- `0x180061a54`
- `0x180061f40`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180061bd9`
- `KERNEL32!LocalFree` at `0x180061bea`
- `KERNEL32!LocalFree` at `0x180061bd9`
- `KERNEL32!LocalFree` at `0x180061bea`
- `RPCRT4!I_RpcMapWin32Status` at `0x180061b89`
- `RPCRT4!I_RpcMapWin32Status` at `0x180061b89`
- `RPCRT4!I_RpcExceptionFilter` at `0x180065c09`
- `RPCRT4!I_RpcExceptionFilter` at `0x180065c09`
- `RPCRT4!NdrClientCall3` at `0x180061b6b`
- `RPCRT4!NdrClientCall3` at `0x180061b6b`
- `RPCRT4!RpcBindingFree` at `0x180061c25`
- `RPCRT4!RpcBindingFree` at `0x180061c25`

## pseudocode

```c

```
