# StandardCollectorService::SessionLifetimeMonitor::MonitorHandle(ATL::CHandle &)

- ea: `0x1800357fc`
- end: `0x1800358ca`
- name: `?MonitorHandle@SessionLifetimeMonitor@StandardCollectorService@@AEAAJAEAVCHandle@ATL@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(PVOID Context, struct ATL::CHandle *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180034eb0`
- `0x180035508`
- `0x180035f18`

## callees

- `0x1800357fc`

## import_xrefs

- `KERNEL32!UnregisterWaitEx` at `0x180035842`
- `KERNEL32!UnregisterWaitEx` at `0x180035842`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18003586f`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18003586f`
- `KERNEL32!TryEnterCriticalSection` at `0x180035822`
- `KERNEL32!TryEnterCriticalSection` at `0x180035822`
- `KERNEL32!LeaveCriticalSection` at `0x1800358a7`
- `KERNEL32!LeaveCriticalSection` at `0x1800358a7`
- `KERNEL32!GetLastError` at `0x180035879`
- `KERNEL32!GetLastError` at `0x180035879`

## pseudocode

```c

```
