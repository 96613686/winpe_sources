# TextServicesHost::EnsureTimerWindowClass(void)

- ea: `0x1806f76cc`
- end: `0x1806f7813`
- name: `?EnsureTimerWindowClass@TextServicesHost@@AEAAJXZ`
- size: `327`
- prototype: `HRESULT __fastcall(TextServicesHost *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180672208`

## callees

- `0x1806877a8`
- `0x180687890`
- `0x180687a78`
- `0x1806c4ccc`
- `0x1806f76cc`
- `0x18076f0a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1806f77b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1806f77b3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1806f76f1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1806f76f1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1806f776f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1806f776f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1806f77f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1806f77f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1806f7763`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1806f7763`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1806f7745`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1806f7745`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassW` at `0x1806f77cf`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassW` at `0x1806f77cf`

## string_xrefs

- `0x1806f77a7`: `windows.ui.xaml.dll`
- `0x1806f77c3`: `XAML_TextServicesTimerClass`

## pseudocode

```c

```
