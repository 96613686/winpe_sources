# CDlpTask::UpdateProgressAction(IDlpAction *,ulong,int)

- ea: `0x140050ad8`
- end: `0x1400516d7`
- name: `?UpdateProgressAction@CDlpTask@@AEAAJPEAVIDlpAction@@KH@Z`
- size: `3071`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, struct IDlpAction *, unsigned int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1400452c8`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x140034ab4`
- `0x140038f00`
- `0x140038fc4`
- `0x14004c2b0`
- `0x140050ad8`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x140050c3d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140050c3d`
- `KERNEL32!LeaveCriticalSection` at `0x140050ee0`
- `KERNEL32!LeaveCriticalSection` at `0x140050ee0`
- `KERNEL32!EnterCriticalSection` at `0x140050eb2`
- `KERNEL32!EnterCriticalSection` at `0x140050eb2`
- `OLEAUT32!__imp_SysFreeString` at `0x140051687`
- `OLEAUT32!__imp_SysFreeString` at `0x140051687`

## string_xrefs

- `0x140051646`: `CDlpTask::UpdateProgressAction`

## pseudocode

```c

```
