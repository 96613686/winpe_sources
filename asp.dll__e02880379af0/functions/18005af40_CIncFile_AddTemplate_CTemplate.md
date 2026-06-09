# CIncFile::AddTemplate(CTemplate *)

- ea: `0x18005af40`
- end: `0x18005b063`
- name: `?AddTemplate@CIncFile@@QEAAJPEAVCTemplate@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(CIncFile *__hidden this, struct CTemplate *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005e24c`

## callees

- `0x18003c9d4`
- `0x18005af40`
- `0x180060300`
- `0x180060334`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18005b048`
- `KERNEL32!LeaveCriticalSection` at `0x18005b048`
- `KERNEL32!EnterCriticalSection` at `0x18005af64`
- `KERNEL32!EnterCriticalSection` at `0x18005af64`
- `iisutil!PuDbgPrint` at `0x18005b026`
- `iisutil!PuDbgPrint` at `0x18005b026`

## string_xrefs

- `0x18005b01f`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18005b006`: `AddTemplate: Notifying debugger to refresh breakpoints\n`
- `0x18005b00d`: `CIncFile::AddTemplate`

## pseudocode

```c

```
