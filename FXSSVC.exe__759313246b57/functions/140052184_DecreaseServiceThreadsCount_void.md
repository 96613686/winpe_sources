# DecreaseServiceThreadsCount(void)

- ea: `0x140052184`
- end: `0x14005229b`
- name: `?DecreaseServiceThreadsCount@@YAHXZ`
- size: `279`
- prototype: `__int64(void)`
- caller_count: `10`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140006fc0`
- `0x140007430`
- `0x140030cf0`
- `0x1400311d0`
- `0x140031d80`
- `0x14003b300`
- `0x1400411a0`
- `0x1400596c0`
- `0x140059870`
- `0x14005cec0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140052184`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140052251`
- `KERNEL32!GetLastError` at `0x140052251`
- `KERNEL32!EnterCriticalSection` at `0x1400521cc`
- `KERNEL32!EnterCriticalSection` at `0x1400521cc`
- `KERNEL32!LeaveCriticalSection` at `0x140052281`
- `KERNEL32!LeaveCriticalSection` at `0x140052281`
- `KERNEL32!SetEvent` at `0x140052227`
- `KERNEL32!SetEvent` at `0x140052227`

## pseudocode

```c

```
