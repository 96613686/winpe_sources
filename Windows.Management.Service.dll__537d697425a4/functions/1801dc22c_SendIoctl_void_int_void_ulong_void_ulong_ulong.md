# SendIoctl(void *,int,void *,ulong,void *,ulong,ulong *)

- ea: `0x1801dc22c`
- end: `0x1801dc4b4`
- name: `?SendIoctl@@YAJPEAXH0K0KPEAK@Z`
- size: `648`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, int@<edx>, void *@<r8>, unsigned int@<r9d>, void *, unsigned int, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1801db080`
- `0x1801db558`
- `0x1801db9dc`
- `0x1801dbca4`
- `0x1801dc748`

## callees

- `0x180065d98`
- `0x180067e34`
- `0x180067e54`
- `0x180088144`
- `0x1801dc22c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801dc299`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801dc299`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801dc37b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1801dc37b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dc33a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dc33a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801dc39a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801dc429`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801dc39a`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1801dc429`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801dc32a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801dc32a`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801dc3e2`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x1801dc3e2`

## pseudocode

```c

```
