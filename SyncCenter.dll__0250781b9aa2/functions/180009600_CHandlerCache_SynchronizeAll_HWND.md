# CHandlerCache::SynchronizeAll(HWND__ *)

- ea: `0x180009600`
- end: `0x1800096c8`
- name: `?SynchronizeAll@CHandlerCache@@QEAAJPEAUHWND__@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, HWND pData)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180012710`
- `0x18001ff20`
- `0x180023314`

## callees

- `0x180008abc`
- `0x18000926c`
- `0x180009600`
- `0x18000977c`
- `0x1800097e4`
- `0x180010310`
- `0x180013ab0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000968b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000968b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009644`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009644`

## pseudocode

```c

```
