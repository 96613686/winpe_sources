# CAudioHealthMonitor::LooksLikeWeAreHung_Old(ulong,ushort const *)

- ea: `0x1800dde00`
- end: `0x1800ddf8c`
- name: `?LooksLikeWeAreHung_Old@CAudioHealthMonitor@@AEAAXKPEBG@Z`
- size: `396`
- prototype: `void __fastcall(CAudioHealthMonitor *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800ddb20`

## callees

- `0x18001b520`
- `0x180060a5c`
- `0x180061430`
- `0x180072e10`
- `0x1800dde00`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dde25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dde25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ddf71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ddf71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800dded6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800dded6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ddf57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ddf57`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800ddf62`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800ddf62`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ddf51`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ddf51`
- `faultrep!ReportCoreHang` at `0x1800ddf06`
- `faultrep!ReportCoreHang` at `0x1800ddf06`

## pseudocode

```c

```
