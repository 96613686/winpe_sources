# PAL_System_Win32_ThreadUnRegisterWindowClass(void)

- ea: `0x1800676ac`
- end: `0x180067966`
- name: `?PAL_System_Win32_ThreadUnRegisterWindowClass@@YAJXZ`
- size: `698`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180050b00`

## callees

- `0x180002550`
- `0x180004970`
- `0x180046a84`
- `0x1800676ac`
- `0x18006e6a8`
- `0x1800711c8`
- `0x1800721d4`
- `0x180078c20`
- `0x18007969c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006782f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006782f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067898`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!UnregisterClassW` at `0x18006788a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!UnregisterClassW` at `0x18006788a`

## string_xrefs

- `0x1800678d7`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18006774b`: `PAL_SYS_WIN32_THREAD_WNDCLASS`
- `0x1800678c0`: `PAL_System_Win32_ThreadUnRegisterWindowClass`
- `0x1800676f5`: `Thread window class not registered. Skipping unregister.`

## pseudocode

```c

```
