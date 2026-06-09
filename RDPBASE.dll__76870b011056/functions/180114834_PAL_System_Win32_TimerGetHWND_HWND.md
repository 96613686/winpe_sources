# PAL_System_Win32_TimerGetHWND(HWND__ * *)

- ea: `0x180114834`
- end: `0x1801149a4`
- name: `?PAL_System_Win32_TimerGetHWND@@YAJPEAPEAUHWND__@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(HWND *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180115fc0`
- `0x180116230`

## callees

- `0x1800018a4`
- `0x1801144e8`
- `0x180114834`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18011493b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18011493b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801148ca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801148ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114945`

## string_xrefs

- `0x180114874`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180114917`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x18011497e`: `onecore\termsrv\rdpplatform\common\pal\win32\system\tssystempalwin32int.cpp`
- `0x180114922`: `Failed to create timer window`

## pseudocode

```c

```
