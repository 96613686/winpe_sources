# SafeTerminateDll(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18011be00`
- end: `0x18011bef0`
- name: `?SafeTerminateDll@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `240`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE pci, HANDLE hObject, struct _TP_WAIT *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18011bdc0`

## callees

- `0x1800b9abc`
- `0x18011be00`
- `0x18014a7a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011bea0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011bec8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011bea0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011bec8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011be69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011bedc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011be69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18011bedc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18011bed3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18011bed3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18011be3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18011be3a`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x18011be48`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x18011be48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011be59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011be59`

## pseudocode

```c

```
