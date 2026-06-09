# _GetCachedSTAObject(ulong,int *,CCachedSTAObject * *)

- ea: `0x18003eed4`
- end: `0x18003efa8`
- name: `?_GetCachedSTAObject@@YAJKPEAHPEAPEAVCCachedSTAObject@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(DWORD dwTlsIndex, int *, struct CCachedSTAObject **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003ee6c`

## callees

- `0x18003eed4`
- `0x18003efb0`
- `0x18003efe0`
- `0x18005db64`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003ef7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003ef7b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003eee9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003eee9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003ef86`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18003ef86`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18003ef45`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18003ef45`

## pseudocode

```c

```
