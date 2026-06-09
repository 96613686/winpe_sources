# CIncFile::RemoveTemplate(CTemplate *)

- ea: `0x18005f938`
- end: `0x18005fa19`
- name: `?RemoveTemplate@CIncFile@@QEAAXPEAVCTemplate@@@Z`
- size: `225`
- prototype: `void __fastcall(CIncFile *__hidden this, struct CTemplate *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019fe4`

## callees

- `0x18003c9d4`
- `0x18005f938`
- `0x180060300`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18005fa12`
- `KERNEL32!EnterCriticalSection` at `0x18005f951`
- `KERNEL32!EnterCriticalSection` at `0x18005f951`
- `iisutil!PuDbgPrint` at `0x18005f9e8`
- `iisutil!PuDbgPrint` at `0x18005f9e8`

## string_xrefs

- `0x18005f9e1`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18005f9c8`: `RemoveTemplate: Notifying debugger to refresh breakpoints\n`
- `0x18005f9cf`: `CIncFile::RemoveTemplate`

## pseudocode

```c

```
