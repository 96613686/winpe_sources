# TileQueueManager::RequestToastNotificationWithPrivilege(_WPN_TOAST_NOTIFICATION * *,ulong *,ushort const * * *,ulong *)

- ea: `0x1800fecec`
- end: `0x1800ff604`
- name: `?RequestToastNotificationWithPrivilege@TileQueueManager@@AEAAJPEAPEAU_WPN_TOAST_NOTIFICATION@@PEAKPEAPEAPEBG1@Z`
- size: `2328`
- prototype: `__int64 __fastcall(TileQueueManager *__hidden this, struct _WPN_TOAST_NOTIFICATION **, unsigned int *, const unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1800fe440`

## callees

- `0x18002ee38`
- `0x180062bf0`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800fa6ec`
- `0x1800fad9c`
- `0x1800fecec`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800ff27c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800ff27c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ff266`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800ff266`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800fefd1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800fefd1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800feff7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800feff7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fee48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fef23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fee48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fef23`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800ff07a`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800ff0bb`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800ff1c0`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800ff202`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800ff07a`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800ff0bb`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800ff1c0`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800ff202`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800fee38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800fef13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ff067`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ff0a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ff1ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ff1ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ff594`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ff5ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800fee38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800fef13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ff067`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ff0a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ff1ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ff1ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ff594`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ff5ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ff5a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ff5bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ff5a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ff5bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800fef90`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800fef90`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ff0d8`
- `OLEAUT32!__imp_SysAllocString` at `0x1800ff0d8`

## pseudocode

```c

```
