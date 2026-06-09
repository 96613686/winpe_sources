# PAL_System_Win32_ThreadUnRegisterWindowClass(void)

- ea: `0x18001b0e8`
- end: `0x18001b331`
- name: `?PAL_System_Win32_ThreadUnRegisterWindowClass@@YAJXZ`
- size: `585`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001ba0c`

## callees

- `0x180001364`
- `0x1800013f4`
- `0x1800044bf`
- `0x18000b1d8`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001b0e8`
- `0x18001b6d4`
- `0x18009a520`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001b1eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001b1eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b25b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b25b`
- `USER32!UnregisterClassW` at `0x18001b24d`
- `USER32!UnregisterClassW` at `0x18001b24d`

## string_xrefs

- `0x18001b29a`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18001b136`: `Thread window class not registered. Skipping unregister.`
- `0x18001b283`: `PAL_System_Win32_ThreadUnRegisterWindowClass`

## pseudocode

```c

```
