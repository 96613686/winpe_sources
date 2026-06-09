# CHandlerCache::EndSession(uint)

- ea: `0x180013ae0`
- end: `0x180013bb1`
- name: `?EndSession@CHandlerCache@@QEAAXI@Z`
- size: `209`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180021a78`

## callees

- `0x180008abc`
- `0x1800096d0`
- `0x18000ad80`
- `0x180013ae0`
- `0x180015890`
- `0x180015af8`
- `0x18001618c`
- `0x180022f90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013b5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013b5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013b11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013b11`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013afb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013afb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180013b6f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180013b6f`

## pseudocode

```c

```
