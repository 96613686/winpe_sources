# MsSetEvent(MS_EVENT_USERMODE *)

- ea: `0x1400ab43c`
- end: `0x1400ab4af`
- name: `?MsSetEvent@@YAXPEAUMS_EVENT_USERMODE@@@Z`
- size: `115`
- prototype: `void __fastcall(struct MS_EVENT_USERMODE *)`
- caller_count: `68`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140085be8`
- `0x140086ab4`
- `0x14008b0a4`
- `0x14008d5ac`
- `0x14008d634`
- `0x14008d750`
- `0x14008e3c8`
- `0x14008ff90`
- `0x14009a248`
- `0x14009a9f0`
- `0x14009bb10`
- `0x1400a1da0`
- `0x1400a21b0`
- `0x1400a31c8`
- `0x1400a3cd8`
- `0x1400a41c0`
- `0x1400a42d8`
- `0x1400a48d4`
- `0x1400a4ed0`
- `0x1400a5370`
- `0x1400a5cf0`
- `0x1400a836c`
- `0x1400af1f0`
- `0x1400b1584`
- `0x1400bbaa4`
- `0x1400c0ba4`
- `0x1400c3a98`
- `0x1400c6ce0`
- `0x1400c8b40`
- `0x1400d259c`
- `0x1400d28b0`
- `0x1400d365c`
- `0x1400d39e4`
- `0x1400d4134`
- `0x1400d4d74`
- `0x1400d5984`
- `0x1400d5e18`
- `0x1400dc4e8`
- `0x1400dc5ac`
- `0x1400dc67c`
- `0x1400dc73c`
- `0x1400dc7fc`
- `0x1400de68c`
- `0x1400df150`
- `0x1400e1be0`
- `0x1400e1d30`
- `0x1400f3bb0`
- `0x1400f69e8`
- `0x1400f86c0`
- `0x1400f9a7c`

## callees

- `0x1400ab43c`

## import_xrefs

- `ntdll!RtlWakeAllConditionVariable` at `0x1400ab489`
- `ntdll!RtlWakeAllConditionVariable` at `0x1400ab489`
- `ntdll!RtlWakeConditionVariable` at `0x1400ab47b`
- `ntdll!RtlWakeConditionVariable` at `0x1400ab47b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400ab44d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400ab44d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400ab4a3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400ab465`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400ab465`

## pseudocode

```c

```
