# IncreaseServiceThreadsCount(void)

- ea: `0x140052fb0`
- end: `0x1400530c7`
- name: `?IncreaseServiceThreadsCount@@YAHXZ`
- size: `279`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140051f44`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140052fb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005307d`
- `KERNEL32!GetLastError` at `0x14005307d`
- `KERNEL32!EnterCriticalSection` at `0x140052ff8`
- `KERNEL32!EnterCriticalSection` at `0x140052ff8`
- `KERNEL32!LeaveCriticalSection` at `0x1400530ad`
- `KERNEL32!LeaveCriticalSection` at `0x1400530ad`
- `KERNEL32!ResetEvent` at `0x140053053`
- `KERNEL32!ResetEvent` at `0x140053053`

## pseudocode

```c

```
