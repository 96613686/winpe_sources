# SendIoctl(void *,int,void *,ulong,void *,ulong,ulong *)

- ea: `0x1801d63d0`
- end: `0x1801d662a`
- name: `?SendIoctl@@YAJPEAXH0K0KPEAK@Z`
- size: `602`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, int@<edx>, void *@<r8>, unsigned int@<r9d>, void *, unsigned int, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1801d525c`
- `0x1801d5730`
- `0x1801d5bb4`
- `0x1801d5e7c`
- `0x1801d6890`

## callees

- `0x180065bac`
- `0x180067a34`
- `0x180067a54`
- `0x1800873a4`
- `0x1801d63d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801d643d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801d643d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801d650d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801d650d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d64d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d64d2`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801d6526`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801d65a6`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801d6526`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801d65a6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801d64c8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801d64c8`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801d6568`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801d6568`

## pseudocode

```c

```
