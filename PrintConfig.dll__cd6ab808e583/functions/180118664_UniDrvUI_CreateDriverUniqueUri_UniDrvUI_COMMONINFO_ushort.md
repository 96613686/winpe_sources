# UniDrvUI::CreateDriverUniqueUri(UniDrvUI::_COMMONINFO *,ushort * *)

- ea: `0x180118664`
- end: `0x1801188a8`
- name: `?CreateDriverUniqueUri@UniDrvUI@@YAJPEAU_COMMONINFO@1@PEAPEAG@Z`
- size: `580`
- prototype: `__int64 __fastcall(UniDrvUI *__hidden this, struct UniDrvUI::_COMMONINFO *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800f32a4`

## callees

- `0x18000bed0`
- `0x180118664`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801186c9`
- `KERNEL32!GetLastError` at `0x1801186c9`
- `KERNEL32!LocalFree` at `0x1801187e4`
- `KERNEL32!LocalFree` at `0x1801187e4`
- `KERNEL32!LocalAlloc` at `0x1801187b0`
- `KERNEL32!LocalAlloc` at `0x1801187b0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18011870c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18011870c`
- `OLEAUT32!__imp_SysFreeString` at `0x1801187d3`
- `OLEAUT32!__imp_SysFreeString` at `0x1801187d3`
- `VERSION!GetFileVersionInfoW` at `0x180118805`
- `VERSION!GetFileVersionInfoW` at `0x180118805`
- `VERSION!VerQueryValueW` at `0x18011882d`
- `VERSION!VerQueryValueW` at `0x18011882d`
- `VERSION!GetFileVersionInfoSizeW` at `0x1801186b5`
- `VERSION!GetFileVersionInfoSizeW` at `0x1801186b5`

## string_xrefs

- `0x18011873e`: `http://schemas.microsoft.com/windows/printing/oemdriverpt`

## pseudocode

```c

```
