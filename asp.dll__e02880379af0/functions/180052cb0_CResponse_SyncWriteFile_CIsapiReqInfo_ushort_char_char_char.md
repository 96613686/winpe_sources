# CResponse::SyncWriteFile(CIsapiReqInfo *,ushort *,char *,char *,char *)

- ea: `0x180052cb0`
- end: `0x180052e81`
- name: `?SyncWriteFile@CResponse@@SAJPEAVCIsapiReqInfo@@PEAGPEAD22@Z`
- size: `465`
- prototype: `__int64 __fastcall(struct CIsapiReqInfo *this, unsigned __int16 *, char *, char *, char *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18003f600`
- `0x180042d30`

## callees

- `0x180013f04`
- `0x180017fc0`
- `0x180051970`
- `0x180051e5c`
- `0x180052cb0`

## import_xrefs

- `msvcrt!_stricmp` at `0x180052cdf`
- `msvcrt!_stricmp` at `0x180052cdf`
- `KERNEL32!HeapFree` at `0x180052e61`
- `KERNEL32!HeapFree` at `0x180052e61`
- `KERNEL32!HeapAlloc` at `0x180052d15`
- `KERNEL32!HeapAlloc` at `0x180052d15`
- `KERNEL32!GetFileSize` at `0x180052da2`
- `KERNEL32!GetFileSize` at `0x180052da2`
- `KERNEL32!CloseHandle` at `0x180052e40`
- `KERNEL32!CloseHandle` at `0x180052e4f`
- `KERNEL32!CloseHandle` at `0x180052e40`
- `KERNEL32!CloseHandle` at `0x180052e4f`
- `KERNEL32!GetLastError` at `0x180052d57`
- `KERNEL32!GetLastError` at `0x180052e1b`
- `KERNEL32!GetLastError` at `0x180052d57`
- `KERNEL32!GetLastError` at `0x180052e1b`
- `iisutil!PuDbgPrint` at `0x180052d8d`
- `iisutil!PuDbgPrint` at `0x180052d8d`

## string_xrefs

- `0x180052d76`: `Could not open "%S".  Win32 Error = %u\n`
- `0x180052d64`: `CResponse::SyncWriteFile`

## pseudocode

```c

```
