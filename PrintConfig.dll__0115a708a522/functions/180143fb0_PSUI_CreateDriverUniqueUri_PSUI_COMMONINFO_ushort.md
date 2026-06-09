# PSUI::CreateDriverUniqueUri(PSUI::_COMMONINFO *,ushort * *)

- ea: `0x180143fb0`
- end: `0x180144229`
- name: `?CreateDriverUniqueUri@PSUI@@YAJPEAU_COMMONINFO@1@PEAPEAG@Z`
- size: `633`
- prototype: `__int64 __fastcall(PSUI *this, BSTR *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18012ec04`

## callees

- `0x18000bf2c`
- `0x180143fb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18014401b`
- `KERNEL32!GetLastError` at `0x18014401b`
- `KERNEL32!LocalFree` at `0x18014414e`
- `KERNEL32!LocalFree` at `0x18014414e`
- `KERNEL32!LocalAlloc` at `0x18014410e`
- `KERNEL32!LocalAlloc` at `0x18014410e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180144064`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180144064`
- `OLEAUT32!__imp_SysFreeString` at `0x180144137`
- `OLEAUT32!__imp_SysFreeString` at `0x180144137`
- `VERSION!GetFileVersionInfoW` at `0x180144175`
- `VERSION!GetFileVersionInfoW` at `0x180144175`
- `VERSION!VerQueryValueW` at `0x1801441a3`
- `VERSION!VerQueryValueW` at `0x1801441a3`
- `VERSION!GetFileVersionInfoSizeW` at `0x180144001`
- `VERSION!GetFileVersionInfoSizeW` at `0x180144001`

## string_xrefs

- `0x18014409c`: `http://schemas.microsoft.com/windows/printing/oemdriverpt`

## pseudocode

```c

```
