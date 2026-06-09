# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x18001cb78`
- end: `0x18001cc67`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d2e0`

## callees

- `0x18001a6c0`
- `0x18001cb78`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001cbd4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001cbd4`
- `ole32!CoGetObject` at `0x18001cc3d`
- `ole32!CoGetObject` at `0x18001cc3d`

## pseudocode

```c

```
