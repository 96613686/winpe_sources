# PSUI::CreateDriverUniqueUri(PSUI::_COMMONINFO *,ushort * *)

- ea: `0x18013db50`
- end: `0x18013dd94`
- name: `?CreateDriverUniqueUri@PSUI@@YAJPEAU_COMMONINFO@1@PEAPEAG@Z`
- size: `580`
- prototype: `__int64 __fastcall(PSUI *__hidden this, struct PSUI::_COMMONINFO *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180128f0c`

## callees

- `0x18000bed0`
- `0x18013db50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18013dbb5`
- `KERNEL32!GetLastError` at `0x18013dbb5`
- `KERNEL32!LocalFree` at `0x18013dcd0`
- `KERNEL32!LocalFree` at `0x18013dcd0`
- `KERNEL32!LocalAlloc` at `0x18013dc9c`
- `KERNEL32!LocalAlloc` at `0x18013dc9c`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18013dbf8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18013dbf8`
- `OLEAUT32!__imp_SysFreeString` at `0x18013dcbf`
- `OLEAUT32!__imp_SysFreeString` at `0x18013dcbf`
- `VERSION!GetFileVersionInfoW` at `0x18013dcf1`
- `VERSION!GetFileVersionInfoW` at `0x18013dcf1`
- `VERSION!VerQueryValueW` at `0x18013dd19`
- `VERSION!VerQueryValueW` at `0x18013dd19`
- `VERSION!GetFileVersionInfoSizeW` at `0x18013dba1`
- `VERSION!GetFileVersionInfoSizeW` at `0x18013dba1`

## string_xrefs

- `0x18013dc2a`: `http://schemas.microsoft.com/windows/printing/oemdriverpt`

## pseudocode

```c

```
