# CRpcIOManagerServer::BuildContextPrimary(CSessionObject *,_BindVersionSet,ushort const *,int,int,ushort *,CContextInfo *,_BoundVersionSet *)

- ea: `0x180057928`
- end: `0x180057bd2`
- name: `?BuildContextPrimary@CRpcIOManagerServer@@AEAAJPEAVCSessionObject@@U_BindVersionSet@@PEBGHHPEAGPEAVCContextInfo@@PEAU_BoundVersionSet@@@Z`
- size: `682`
- prototype: `__int64 __fastcall(__int64, __int64, __int128 *, const wchar_t *, int, int, wchar_t *Dest, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18005743c`

## callees

- `0x180003cf0`
- `0x180012130`
- `0x180019908`
- `0x180027920`
- `0x180057928`
- `0x1800677e4`
- `0x1800678d0`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180057a45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180057a45`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180057a13`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180057a13`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800579f1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800579f1`
- `msvcrt!wcstombs` at `0x180057982`
- `msvcrt!wcstombs` at `0x180057982`
- `msvcrt!mbstowcs` at `0x180057ab6`
- `msvcrt!mbstowcs` at `0x180057ab6`

## string_xrefs

- `0x180057a5b`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180057b92`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x180057b2c`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`

## pseudocode

```c

```
