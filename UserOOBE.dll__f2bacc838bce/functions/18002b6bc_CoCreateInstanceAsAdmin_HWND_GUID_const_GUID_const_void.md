# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x18002b6bc`
- end: `0x18002b7a3`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `231`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002b7b0`

## callees

- `0x1800032b0`
- `0x180007710`
- `0x18002b6bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b710`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002b710`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x18002b77d`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x18002b77d`

## pseudocode

```c

```
