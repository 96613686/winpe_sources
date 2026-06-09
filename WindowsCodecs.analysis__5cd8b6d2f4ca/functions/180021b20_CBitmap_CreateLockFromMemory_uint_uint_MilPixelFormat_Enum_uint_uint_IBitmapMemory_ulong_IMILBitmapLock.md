# CBitmap::CreateLockFromMemory(uint,uint,MilPixelFormat::Enum,uint,uint,IBitmapMemory *,ulong,IMILBitmapLock * *)

- ea: `0x180021b20`
- end: `0x180021e1d`
- name: `?CreateLockFromMemory@CBitmap@@IEAAJIIW4Enum@MilPixelFormat@@IIPEAUIBitmapMemory@@KPEAPEAUIMILBitmapLock@@@Z`
- size: `765`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18003c170`

## callees

- `0x180021b20`
- `0x180022d68`
- `0x1800bd9d4`
- `0x1800e5a18`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021bac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021bac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021b7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021b7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180021ddf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180021ddf`

## string_xrefs

- `0x180021dd8`: `WindowsCodecs.dll`

## pseudocode

```c

```
