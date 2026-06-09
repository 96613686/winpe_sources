# CAppln::UpdateConfig(CIsapiReqInfo *,int *,int *)

- ea: `0x180001400`
- end: `0x1800014b8`
- name: `?UpdateConfig@CAppln@@QEAAJPEAVCIsapiReqInfo@@PEAH1@Z`
- size: `184`
- prototype: `__int64 __fastcall(CAppln *__hidden this, struct CIsapiReqInfo *, int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180009180`

## callees

- `0x180001400`
- `0x180002864`
- `0x1800033e8`
- `0x180003424`
- `0x180006244`
- `0x18000f690`
- `0x180045820`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18002483d`
- `KERNEL32!HeapAlloc` at `0x18002483d`
- `KERNEL32!LeaveCriticalSection` at `0x18002486f`
- `KERNEL32!LeaveCriticalSection` at `0x1800248b2`
- `KERNEL32!LeaveCriticalSection` at `0x1800248c1`
- `KERNEL32!LeaveCriticalSection` at `0x18002486f`
- `KERNEL32!LeaveCriticalSection` at `0x1800248b2`
- `KERNEL32!LeaveCriticalSection` at `0x1800248c1`
- `KERNEL32!EnterCriticalSection` at `0x18002480e`
- `KERNEL32!EnterCriticalSection` at `0x18002480e`
- `iisutil!ScheduleAdjustTime` at `0x1800248d3`
- `iisutil!ScheduleAdjustTime` at `0x1800248d3`

## pseudocode

```c

```
