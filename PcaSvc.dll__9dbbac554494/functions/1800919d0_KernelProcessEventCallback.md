# KernelProcessEventCallback

- ea: `0x1800919d0`
- end: `0x18009217f`
- name: `KernelProcessEventCallback`
- size: `1967`
- prototype: `int *__fastcall(PEVENT_RECORD pEvent)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800016b8`
- `0x18000c018`
- `0x18000da30`
- `0x180012920`
- `0x1800182b4`
- `0x1800182e0`
- `0x1800184ac`
- `0x180018768`
- `0x1800189e4`
- `0x180018b40`
- `0x1800195c8`
- `0x1800234fc`
- `0x180023e00`
- `0x18004290c`
- `0x180091314`
- `0x180091734`
- `0x1800919d0`
- `0x180092188`
- `0x18009389c`
- `0x1800938f4`
- `0x1800945a0`
- `0x180094634`
- `0x180094d48`
- `0x180094e6c`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180091a8b`
- `ntdll!RtlFreeHeap` at `0x180091a8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091c3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091e4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091c3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091e4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091adb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091d37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091adb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091d37`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180091d27`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180091d27`
- `AEPIC!PicRetrieveFileInfo` at `0x180091e75`
- `AEPIC!PicRetrieveFileInfo` at `0x180091e75`
- `AEPIC!PicFreeFileInfo` at `0x180091eeb`
- `AEPIC!PicFreeFileInfo` at `0x180091eeb`
- `tdh!TdhGetProperty` at `0x180091ace`
- `tdh!TdhGetProperty` at `0x180091cf6`
- `tdh!TdhGetProperty` at `0x180091ace`
- `tdh!TdhGetProperty` at `0x180091cf6`

## string_xrefs

- `0x180091a9a`: `ParentProcessID`

## pseudocode

```c

```
