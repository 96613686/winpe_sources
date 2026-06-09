# CViperReqManager::WatchThread(void *)

- ea: `0x18001cb50`
- end: `0x18001cbdc`
- name: `?WatchThread@CViperReqManager@@CAKPEAX@Z`
- size: `140`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18001a600`
- `0x18001cb50`
- `0x180047370`
- `0x1800625b8`
- `0x180062b00`
- `0x180064010`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x18001cb8f`
- `KERNEL32!ResetEvent` at `0x18001cb8f`
- `KERNEL32!LeaveCriticalSection` at `0x18002fce6`
- `KERNEL32!LeaveCriticalSection` at `0x18002fce6`
- `KERNEL32!WaitForSingleObject` at `0x18001cbac`
- `KERNEL32!WaitForSingleObject` at `0x18001cbac`
- `KERNEL32!EnterCriticalSection` at `0x18002fc95`
- `KERNEL32!EnterCriticalSection` at `0x18002fc95`
- `KERNEL32!GetTickCount` at `0x18001cbb2`
- `KERNEL32!GetTickCount` at `0x18002fd82`
- `KERNEL32!GetTickCount` at `0x18001cbb2`
- `KERNEL32!GetTickCount` at `0x18002fd82`

## pseudocode

```c

```
