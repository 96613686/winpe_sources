# ThreadPool::ThreadPoolProc(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800919f0`
- end: `0x180091b14`
- name: `?ThreadPoolProc@ThreadPool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `292`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800036a4`
- `0x18000e5f4`
- `0x180050ef0`
- `0x18008a97c`
- `0x1800919f0`
- `0x1800a0b2c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180091a2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180091a2e`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180091ad8`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180091ad8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180091a93`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180091ac2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180091a93`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180091ac2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180091a46`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180091a9d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180091a46`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180091a9d`

## string_xrefs

- `0x180091aec`: `onecoreuap\base\diagnosis\platform\notifications\platform\threadpool\threadpool.cpp`
- `0x180091b01`: `onecoreuap\base\diagnosis\platform\notifications\platform\threadpool\threadpool.cpp`

## pseudocode

```c

```
