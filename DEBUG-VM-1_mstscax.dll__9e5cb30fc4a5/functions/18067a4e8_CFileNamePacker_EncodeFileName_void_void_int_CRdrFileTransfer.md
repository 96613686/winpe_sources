# CFileNamePacker::EncodeFileName(void * *,void *,int,CRdrFileTransfer *)

- ea: `0x18067a4e8`
- end: `0x18067a8d7`
- name: `?EncodeFileName@CFileNamePacker@@QEAAJPEAPEAXPEAXHPEAVCRdrFileTransfer@@@Z`
- size: `1007`
- prototype: `int(CFileNamePacker *__hidden this, void **, void *, int, struct CRdrFileTransfer *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1806785f4`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1800ebae0`
- `0x18061f858`
- `0x180621640`
- `0x18067a4e8`
- `0x18067a8e0`
- `0x180688f26`
- `0x180688f3e`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18067a819`
- `KERNEL32!GetLastError` at `0x18067a878`
- `KERNEL32!GetLastError` at `0x18067a882`
- `KERNEL32!GetLastError` at `0x18067a819`
- `KERNEL32!GetLastError` at `0x18067a878`
- `KERNEL32!GetLastError` at `0x18067a882`
- `KERNEL32!LocalAlloc` at `0x18067a663`
- `KERNEL32!LocalAlloc` at `0x18067a7a5`
- `KERNEL32!LocalAlloc` at `0x18067a663`
- `KERNEL32!LocalAlloc` at `0x18067a7a5`
- `KERNEL32!LocalFree` at `0x18067a89f`
- `KERNEL32!LocalFree` at `0x18067a89f`
- `KERNEL32!MultiByteToWideChar` at `0x18067a80b`
- `KERNEL32!MultiByteToWideChar` at `0x18067a80b`
- `KERNEL32!GlobalUnlock` at `0x18067a86e`
- `KERNEL32!GlobalUnlock` at `0x18067a86e`
- `KERNEL32!GlobalFree` at `0x18067a8b2`
- `KERNEL32!GlobalFree` at `0x18067a8b2`

## string_xrefs

- `0x18067a766`: `CopyFileNameToTempPath failed!`

## pseudocode

```c

```
