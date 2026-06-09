# CSecurityManager::MapUrlToZoneEx2Internal(IUri *,ulong *,ulong,ushort * *,ulong *,ulong,ulong *)

- ea: `0x180010970`
- end: `0x18001152c`
- name: `?MapUrlToZoneEx2Internal@CSecurityManager@@IEAAJPEAUIUri@@PEAKKPEAPEAG1K1@Z`
- size: `3004`
- prototype: `int(CSecurityManager *__hidden this, struct IUri *, unsigned int *, unsigned int, unsigned __int16 **, unsigned int *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180010690`

## callees

- `0x18000d870`
- `0x18000e618`
- `0x18000eae0`
- `0x180010970`
- `0x180011540`
- `0x1800121e4`
- `0x180013be0`
- `0x1800215c0`
- `0x18007a044`
- `0x18011c010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001149e`
- `msvcrt!_wcsnicmp` at `0x18001149e`
- `iertutil!GetIUriPriv` at `0x180010b48`
- `iertutil!GetIUriPriv` at `0x180010b48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010a39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010e7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011343`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011470`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010a39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010e7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011343`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011470`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010ba5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010fa2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010ba5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010fa2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001142f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001142f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180010ace`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180010af5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180010ace`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180010af5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011521`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011521`
- `OLEAUT32!__imp_SysFreeString` at `0x180010a76`
- `OLEAUT32!__imp_SysFreeString` at `0x180010a76`

## pseudocode

```c

```
