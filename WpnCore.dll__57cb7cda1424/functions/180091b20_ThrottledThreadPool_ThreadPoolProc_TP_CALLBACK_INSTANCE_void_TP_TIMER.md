# ThrottledThreadPool::ThreadPoolProc(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180091b20`
- end: `0x180091cd9`
- name: `?ThreadPoolProc@ThrottledThreadPool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `441`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180002ab8`
- `0x18000e5f4`
- `0x18002ee38`
- `0x180034288`
- `0x180034548`
- `0x180034624`
- `0x180049644`
- `0x1800713b0`
- `0x1800720c4`
- `0x18008a97c`
- `0x180091b20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180091b55`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180091b55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091bf0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091bf0`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180091caf`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180091caf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180091bcc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180091c99`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180091bcc`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180091c99`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180091b5f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180091bd6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180091b5f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180091bd6`

## string_xrefs

- `0x180091c71`: `onecoreuap\base\diagnosis\platform\notifications\platform\threadpool\throttledthreadpool.cpp`
- `0x180091cc6`: `onecoreuap\base\diagnosis\platform\notifications\platform\threadpool\throttledthreadpool.cpp`

## pseudocode

```c

```
