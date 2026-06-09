# KerbFirstFsoCacheEntry(void)

- ea: `0x18007b868`
- end: `0x18007b8b6`
- name: `?KerbFirstFsoCacheEntry@@YAPEAU_KERB_FSO_CACHE_ENTRY@@XZ`
- size: `78`
- prototype: `struct _KERB_FSO_CACHE_ENTRY *(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180079ee4`
- `0x18007a5cc`
- `0x18007a92c`

## callees

- `0x18007b868`
- `0x18007bad0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18007b8a7`
- `ntdll!RtlLeaveCriticalSection` at `0x18007b8a7`
- `ntdll!RtlEnterCriticalSection` at `0x18007b875`
- `ntdll!RtlEnterCriticalSection` at `0x18007b875`

## pseudocode

```c

```
