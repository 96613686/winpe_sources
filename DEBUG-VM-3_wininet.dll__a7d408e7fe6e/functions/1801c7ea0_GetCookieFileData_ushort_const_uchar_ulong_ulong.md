# GetCookieFileData(ushort const *,uchar * *,ulong *,ulong *)

- ea: `0x1801c7ea0`
- end: `0x1801c8122`
- name: `?GetCookieFileData@@YAJPEBGPEAPEAEPEAK2@Z`
- size: `642`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int8 **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180130918`

## callees

- `0x180020468`
- `0x1800701d0`
- `0x180091d90`
- `0x18014a7a0`
- `0x1801c7ea0`
- `0x1801e1790`
- `0x1801e1b00`
- `0x1801e3c24`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801c7f55`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801c7f55`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801c8090`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801c8090`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801c7fa1`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801c7fa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c80ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c80ff`
- `RPCRT4!RpcRevertToSelf` at `0x1801c7f92`
- `RPCRT4!RpcRevertToSelf` at `0x1801c80ce`
- `RPCRT4!RpcRevertToSelf` at `0x1801c7f92`
- `RPCRT4!RpcRevertToSelf` at `0x1801c80ce`

## pseudocode

```c

```
