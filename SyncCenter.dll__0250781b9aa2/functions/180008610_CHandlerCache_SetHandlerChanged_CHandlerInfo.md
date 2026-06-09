# CHandlerCache::SetHandlerChanged(CHandlerInfo *)

- ea: `0x180008610`
- end: `0x180008682`
- name: `?SetHandlerChanged@CHandlerCache@@QEAAJPEAVCHandlerInfo@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct CHandlerInfo *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000700c`
- `0x180017370`

## callees

- `0x180008610`
- `0x180008a90`
- `0x180010310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000866a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000866a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000865d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000865d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008625`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008625`

## pseudocode

```c

```
