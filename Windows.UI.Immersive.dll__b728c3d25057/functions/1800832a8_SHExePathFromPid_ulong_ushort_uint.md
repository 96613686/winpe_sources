# SHExePathFromPid(ulong,ushort *,uint)

- ea: `0x1800832a8`
- end: `0x180083366`
- name: `?SHExePathFromPid@@YAJKPEAGI@Z`
- size: `190`
- prototype: `__int64 __fastcall(DWORD dwProcessId, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18003b500`

## callees

- `0x180015580`
- `0x180050ba0`
- `0x1800832a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008332e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008332e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800832fe`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800832fe`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800832d9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800832d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083326`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180083326`

## pseudocode

```c

```
