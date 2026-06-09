# CTnoDriver::CancelRequests(ulong)

- ea: `0x18001046c`
- end: `0x180010624`
- name: `?CancelRequests@CTnoDriver@@QEAAJK@Z`
- size: `440`
- prototype: `__int64 __fastcall(CTnoDriver *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000ed50`

## callees

- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x18001046c`
- `0x18001911c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010585`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18001057b`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18001057b`
- `KERNEL32!CancelIoEx` at `0x1800104f0`
- `KERNEL32!CancelIoEx` at `0x1800104f0`

## pseudocode

```c

```
