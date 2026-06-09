# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180024a68`
- end: `0x180024b57`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011170`

## callees

- `0x180006900`
- `0x18000eec0`
- `0x180024a68`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180024ac4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180024ac4`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x180024b2d`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x180024b2d`

## pseudocode

```c

```
