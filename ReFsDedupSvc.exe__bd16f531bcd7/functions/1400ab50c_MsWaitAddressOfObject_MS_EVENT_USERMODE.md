# MsWaitAddressOfObject(MS_EVENT_USERMODE &)

- ea: `0x1400ab50c`
- end: `0x1400ab58e`
- name: `?MsWaitAddressOfObject@@YAPEAXAEAUMS_EVENT_USERMODE@@@Z`
- size: `130`
- prototype: `void *__fastcall(struct MS_EVENT_USERMODE *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400a4ed0`
- `0x1400d4d74`
- `0x1400fce80`
- `0x1401279a0`

## callees

- `0x1400ab50c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400ab525`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400ab525`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400ab573`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400ab573`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400ab546`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400ab546`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400ab55d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400ab55d`

## pseudocode

```c

```
