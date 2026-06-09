# CachedSTAObject_QueryInterface(ulong,int *,_GUID const &,void * *)

- ea: `0x18002d1e0`
- end: `0x18002d38c`
- name: `?CachedSTAObject_QueryInterface@@YAJKPEAHAEBU_GUID@@PEAPEAX@Z`
- size: `428`
- prototype: `__int64 __fastcall(DWORD dwTlsIndex, int *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002d3fc`
- `0x1800a9de4`

## callees

- `0x18002d1e0`
- `0x18002d3a0`
- `0x18002d3d0`
- `0x18002e0ec`
- `0x180071df0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002d33c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002d33c`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002d23e`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002d23e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002d348`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002d348`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d258`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d258`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18002d30f`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18002d30f`

## pseudocode

```c

```
