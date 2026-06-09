# CQueueMgr::GetOpenQueuesFormatName(wchar_t * * *,ulong *)

- ea: `0x180015a04`
- end: `0x180015cc9`
- name: `?GetOpenQueuesFormatName@CQueueMgr@@QEAAXPEAPEAPEA_WPEAK@Z`
- size: `709`
- prototype: `void __fastcall(CQueueMgr *__hidden this, wchar_t ***, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18002fa28`

## callees

- `0x180004d91`
- `0x180009924`
- `0x18000f35c`
- `0x180015a04`
- `0x18002c61c`
- `0x18009bd1c`
- `0x18009bdf8`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x180015c6d`
- `msvcrt!free` at `0x180015c8b`
- `msvcrt!free` at `0x180015c6d`
- `msvcrt!free` at `0x180015c8b`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180015c30`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180015c30`
- `KERNEL32!LeaveCriticalSection` at `0x180015c95`
- `KERNEL32!LeaveCriticalSection` at `0x180015c95`
- `ntdll!NtDeviceIoControlFile` at `0x180015b1c`
- `ntdll!NtDeviceIoControlFile` at `0x180015baf`
- `ntdll!NtDeviceIoControlFile` at `0x180015b1c`
- `ntdll!NtDeviceIoControlFile` at `0x180015baf`

## pseudocode

```c

```
