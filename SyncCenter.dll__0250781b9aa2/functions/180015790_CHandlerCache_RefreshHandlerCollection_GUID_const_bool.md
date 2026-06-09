# CHandlerCache::_RefreshHandlerCollection(_GUID const &,bool)

- ea: `0x180015790`
- end: `0x18001588a`
- name: `?_RefreshHandlerCollection@CHandlerCache@@AEAAJAEBU_GUID@@_N@Z`
- size: `250`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, const struct _GUID *, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180002130`
- `0x180008398`
- `0x180012b00`

## callees

- `0x180008978`
- `0x18000a5e4`
- `0x180010310`
- `0x1800132bc`
- `0x180015488`
- `0x180015790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015856`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015856`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800157b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800157b4`

## pseudocode

```c

```
