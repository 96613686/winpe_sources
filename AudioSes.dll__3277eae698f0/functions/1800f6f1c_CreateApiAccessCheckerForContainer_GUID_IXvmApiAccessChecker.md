# CreateApiAccessCheckerForContainer(_GUID,IXvmApiAccessChecker * *)

- ea: `0x1800f6f1c`
- end: `0x1800f70a2`
- name: `?CreateApiAccessCheckerForContainer@@YAJU_GUID@@PEAPEAUIXvmApiAccessChecker@@@Z`
- size: `390`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, struct IXvmApiAccessChecker **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180098b08`

## callees

- `0x180007f00`
- `0x180010a90`
- `0x180087e80`
- `0x180096510`
- `0x1800f6b34`
- `0x1800f6c7c`
- `0x1800f6f1c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f6f4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f6f4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6fe0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7070`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f6fe0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f7070`

## string_xrefs

- `0x1800f6fc0`: `avcore\audiocore\lib\crossvmapiaccesschecker\crossvmapiaccesschecker.cpp`

## pseudocode

```c

```
