# LsaICLookupSidsWithCreds

- ea: `0x18006e5c8`
- end: `0x18006e7d8`
- name: `LsaICLookupSidsWithCreds`
- size: `528`
- prototype: `__int64 __fastcall(int, int, int, int, RPC_AUTH_IDENTITY_HANDLE, unsigned int, int, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180043390`

## callees

- `0x18002f474`
- `0x18006e5c8`
- `0x18006eaf0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18006e759`
- `KERNEL32!LocalFree` at `0x18006e770`
- `KERNEL32!LocalFree` at `0x18006e759`
- `KERNEL32!LocalFree` at `0x18006e770`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006e703`
- `RPCRT4!I_RpcMapWin32Status` at `0x18006e703`
- `RPCRT4!I_RpcExceptionFilter` at `0x180072da0`
- `RPCRT4!I_RpcExceptionFilter` at `0x180072da0`
- `RPCRT4!NdrClientCall3` at `0x18006e6df`
- `RPCRT4!NdrClientCall3` at `0x18006e6df`
- `RPCRT4!RpcBindingFree` at `0x18006e7b1`
- `RPCRT4!RpcBindingFree` at `0x18006e7b1`

## pseudocode

```c

```
