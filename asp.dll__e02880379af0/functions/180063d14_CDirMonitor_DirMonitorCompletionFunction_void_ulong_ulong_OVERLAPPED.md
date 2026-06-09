# CDirMonitor::DirMonitorCompletionFunction(void *,ulong,ulong,_OVERLAPPED *)

- ea: `0x180063d14`
- end: `0x180063e3d`
- name: `?DirMonitorCompletionFunction@CDirMonitor@@SAXPEAXKKPEAU_OVERLAPPED@@@Z`
- size: `297`
- prototype: `void __fastcall(CDirMonitorEntry *this, unsigned int, unsigned int, struct _OVERLAPPED *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180063ce0`

## callees

- `0x180018d1c`
- `0x180063d14`
- `0x180063e44`
- `0x180064010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180063dcd`
- `KERNEL32!LeaveCriticalSection` at `0x180063dcd`
- `KERNEL32!EnterCriticalSection` at `0x180063d9f`
- `KERNEL32!EnterCriticalSection` at `0x180063d9f`
- `iisutil!PuDbgPrint` at `0x180063d6f`
- `iisutil!PuDbgPrint` at `0x180063e27`
- `iisutil!PuDbgPrint` at `0x180063d6f`
- `iisutil!PuDbgPrint` at `0x180063e27`

## string_xrefs

- `0x180063d68`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x180063e20`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`
- `0x180063d56`: `CDirMonitor::DirMonitorCompletionFunction`
- `0x180063e0e`: `CDirMonitor::DirMonitorCompletionFunction`

## pseudocode

```c

```
