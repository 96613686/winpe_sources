# CAudioHealthMonitor::LooksLikeWeAreHung_Old(ulong,ushort const *)

- ea: `0x1800dfdf0`
- end: `0x1800dff7c`
- name: `?LooksLikeWeAreHung_Old@CAudioHealthMonitor@@AEAAXKPEBG@Z`
- size: `396`
- prototype: `void __fastcall(CAudioHealthMonitor *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800dfb10`

## callees

- `0x18001b3d0`
- `0x180060eec`
- `0x1800618c0`
- `0x180073310`
- `0x1800dfdf0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dfe15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dfe15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dff61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dff61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800dfec6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800dfec6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800dff47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800dff47`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800dff52`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800dff52`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800dff41`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800dff41`
- `faultrep!ReportCoreHang` at `0x1800dfef6`
- `faultrep!ReportCoreHang` at `0x1800dfef6`

## pseudocode

```c

```
