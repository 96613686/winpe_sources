# _GetCachedSTAObject(ulong,int *,CCachedSTAObject * *)

- ea: `0x180013b54`
- end: `0x180013c98`
- name: `?_GetCachedSTAObject@@YAJKPEAHPEAPEAVCCachedSTAObject@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(DWORD dwTlsIndex, int *, struct CCachedSTAObject **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180013060`
- `0x1800130f8`

## callees

- `0x180003d70`
- `0x180012be8`
- `0x180013680`
- `0x180013b54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180013c28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180013c28`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180013c34`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180013c34`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013bc2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013bc2`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180013b98`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180013b98`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180013c00`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180013c00`

## pseudocode

```c

```
