# _GetCachedSTAObject(ulong,int *,CCachedSTAObject * *)

- ea: `0x180068498`
- end: `0x1800685dc`
- name: `?_GetCachedSTAObject@@YAJKPEAHPEAPEAVCCachedSTAObject@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(DWORD dwTlsIndex, int *, struct CCachedSTAObject **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006342c`
- `0x180068848`

## callees

- `0x180046b0c`
- `0x1800627ac`
- `0x180066cb0`
- `0x180068498`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006856c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006856c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180068578`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180068578`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180068506`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180068506`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800684dc`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1800684dc`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180068544`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x180068544`

## pseudocode

```c

```
