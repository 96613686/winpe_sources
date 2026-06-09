# StructuredQuery1::CoAllocStringLowercased(wchar_t const *,ulong,wchar_t * *)

- ea: `0x18007a9bc`
- end: `0x18007aa69`
- name: `?CoAllocStringLowercased@StructuredQuery1@@YAJPEB_WKPEAPEA_W@Z`
- size: `173`
- prototype: `__int64 __fastcall(LPCWSTR lpSrcStr, LCID Locale, LPWSTR *, wchar_t **)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e688`
- `0x18006d610`
- `0x180071a30`

## callees

- `0x18001ee60`
- `0x180059920`
- `0x18007a9bc`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18007a9ee`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18007aa3b`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18007a9ee`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18007aa3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aa48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007aa48`

## pseudocode

```c

```
