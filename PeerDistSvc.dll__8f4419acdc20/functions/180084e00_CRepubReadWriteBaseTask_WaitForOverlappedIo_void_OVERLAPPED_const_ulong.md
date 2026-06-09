# CRepubReadWriteBaseTask::WaitForOverlappedIo(void *,_OVERLAPPED * const,ulong)

- ea: `0x180084e00`
- end: `0x180084fde`
- name: `?WaitForOverlappedIo@CRepubReadWriteBaseTask@@IEAAKPEAXQEAU_OVERLAPPED@@K@Z`
- size: `478`
- prototype: `unsigned int __fastcall(CRepubReadWriteBaseTask *__hidden this, void *, struct _OVERLAPPED *const, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180082170`
- `0x180085870`

## callees

- `0x180008310`
- `0x18000cef8`
- `0x180084e00`
- `0x180086f80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180084e9b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180084e9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ea5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ea5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084f0a`
- `KERNEL32!CloseHandle` at `0x180084f56`
- `KERNEL32!CloseHandle` at `0x180084f56`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180084f00`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180084f00`

## pseudocode

```c

```
