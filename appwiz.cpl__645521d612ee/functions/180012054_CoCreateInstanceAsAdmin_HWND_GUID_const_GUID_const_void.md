# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180012054`
- end: `0x180012132`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `222`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012910`
- `0x180017e58`
- `0x18002e61c`

## callees

- `0x180007960`
- `0x180012054`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800120ac`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800120ac`
- `ole32!CoGetObject` at `0x180012111`
- `ole32!CoGetObject` at `0x180012111`

## pseudocode

```c

```
