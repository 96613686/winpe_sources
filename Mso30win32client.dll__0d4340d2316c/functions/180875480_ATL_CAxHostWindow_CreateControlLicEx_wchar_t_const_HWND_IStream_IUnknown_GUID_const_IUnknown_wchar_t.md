# ATL::CAxHostWindow::CreateControlLicEx(wchar_t const *,HWND__ *,IStream *,IUnknown * *,_GUID const &,IUnknown *,wchar_t *)

- ea: `0x180875480`
- end: `0x1808759d3`
- name: `?CreateControlLicEx@CAxHostWindow@ATL@@UEAAJPEB_WPEAUHWND__@@PEAUIStream@@PEAPEAUIUnknown@@AEBU_GUID@@PEAU5@PEA_W@Z`
- size: `1363`
- prototype: `int(ATL::CAxHostWindow *__hidden this, const wchar_t *, HWND, struct IStream *, struct IUnknown **, const struct _GUID *, struct IUnknown *, wchar_t *)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x18009c710`
- `0x180192520`
- `0x180192560`
- `0x1805109ac`
- `0x18051bb90`
- `0x180623f80`
- `0x18062ce34`
- `0x18064ae38`
- `0x18077cec4`
- `0x180871550`
- `0x180875480`
- `0x18087705c`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x1808757e2`
- `KERNEL32!GlobalAlloc` at `0x1808757e2`
- `KERNEL32!GlobalLock` at `0x1808757fb`
- `KERNEL32!GlobalLock` at `0x1808757fb`
- `KERNEL32!GlobalUnlock` at `0x18087581d`
- `KERNEL32!GlobalUnlock` at `0x18087581d`
- `KERNEL32!lstrcmpW` at `0x180875590`
- `KERNEL32!lstrcmpW` at `0x180875590`
- `ole32!CreateStreamOnHGlobal` at `0x18087582f`
- `ole32!CreateStreamOnHGlobal` at `0x18087582f`
- `OLEAUT32!__imp_VariantClear` at `0x180875933`
- `OLEAUT32!__imp_VariantClear` at `0x18087593d`
- `OLEAUT32!__imp_VariantClear` at `0x180875933`
- `OLEAUT32!__imp_VariantClear` at `0x18087593d`
- `USER32!IsWindow` at `0x18087551c`
- `USER32!IsWindow` at `0x18087551c`
- `USER32!GetParent` at `0x180875564`
- `USER32!GetParent` at `0x180875564`
- `USER32!RedrawWindow` at `0x18087550b`
- `USER32!RedrawWindow` at `0x180875999`
- `USER32!RedrawWindow` at `0x18087550b`
- `USER32!RedrawWindow` at `0x180875999`
- `USER32!SetWindowPos` at `0x180875729`
- `USER32!SetWindowPos` at `0x180875729`
- `USER32!GetWindowLongW` at `0x1808756d3`
- `USER32!GetWindowLongW` at `0x1808756f0`
- `USER32!GetWindowLongW` at `0x1808756d3`
- `USER32!GetWindowLongW` at `0x1808756f0`
- `USER32!SetWindowLongW` at `0x180875705`
- `USER32!SetWindowLongW` at `0x180875705`
- `USER32!GetClassNameW` at `0x180875577`
- `USER32!GetClassNameW` at `0x180875577`
- `USER32!GetSysColor` at `0x1808755ab`
- `USER32!GetSysColor` at `0x1808755ab`

## pseudocode

```c

```
