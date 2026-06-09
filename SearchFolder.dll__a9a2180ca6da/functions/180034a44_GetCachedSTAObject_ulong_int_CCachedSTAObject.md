# _GetCachedSTAObject(ulong,int *,CCachedSTAObject * *)

- ea: `0x180034a44`
- end: `0x180034b88`
- name: `?_GetCachedSTAObject@@YAJKPEAHPEAPEAVCCachedSTAObject@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(DWORD dwTlsIndex, int *, struct CCachedSTAObject **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800292b8`
- `0x180034c88`

## callees

- `0x180006924`
- `0x1800275d8`
- `0x18002f540`
- `0x180034a44`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180034b18`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180034b18`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180034a88`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180034a88`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180034ab2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180034ab2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180034b24`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180034b24`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180034af0`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180034af0`

## pseudocode

```c

```
