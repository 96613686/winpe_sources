# UniDrvUI::CreateDriverUniqueUri(UniDrvUI::_COMMONINFO *,ushort * *)

- ea: `0x18011d7f0`
- end: `0x18011da69`
- name: `?CreateDriverUniqueUri@UniDrvUI@@YAJPEAU_COMMONINFO@1@PEAPEAG@Z`
- size: `633`
- prototype: `__int64 __fastcall(UniDrvUI *this, BSTR *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800f7d64`

## callees

- `0x18000bf2c`
- `0x18011d7f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18011d85b`
- `KERNEL32!GetLastError` at `0x18011d85b`
- `KERNEL32!LocalFree` at `0x18011d98e`
- `KERNEL32!LocalFree` at `0x18011d98e`
- `KERNEL32!LocalAlloc` at `0x18011d94e`
- `KERNEL32!LocalAlloc` at `0x18011d94e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18011d8a4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18011d8a4`
- `OLEAUT32!__imp_SysFreeString` at `0x18011d977`
- `OLEAUT32!__imp_SysFreeString` at `0x18011d977`
- `VERSION!GetFileVersionInfoW` at `0x18011d9b5`
- `VERSION!GetFileVersionInfoW` at `0x18011d9b5`
- `VERSION!VerQueryValueW` at `0x18011d9e3`
- `VERSION!VerQueryValueW` at `0x18011d9e3`
- `VERSION!GetFileVersionInfoSizeW` at `0x18011d841`
- `VERSION!GetFileVersionInfoSizeW` at `0x18011d841`

## string_xrefs

- `0x18011d8dc`: `http://schemas.microsoft.com/windows/printing/oemdriverpt`

## pseudocode

```c

```
