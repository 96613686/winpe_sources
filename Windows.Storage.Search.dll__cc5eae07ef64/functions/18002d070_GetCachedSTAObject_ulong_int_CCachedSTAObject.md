# _GetCachedSTAObject(ulong,int *,CCachedSTAObject * *)

- ea: `0x18002d070`
- end: `0x18002d1d4`
- name: `?_GetCachedSTAObject@@YAJKPEAHPEAPEAVCCachedSTAObject@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(DWORD dwTlsIndex, int *, struct CCachedSTAObject **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000713c`
- `0x18002cff0`

## callees

- `0x18002d070`
- `0x18002d3a0`
- `0x18002d3d0`
- `0x180071df0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002d16c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002d16c`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002d0aa`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002d0aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002d177`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002d177`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d0d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d0d3`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18002d141`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18002d141`

## pseudocode

```c

```
