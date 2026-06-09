# PAL_System_ThreadFree(void *)

- ea: `0x1800c6244`
- end: `0x1800c636f`
- name: `?PAL_System_ThreadFree@@YAJPEAX@Z`
- size: `299`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004f8fc`
- `0x180059298`

## callees

- `0x1800018a4`
- `0x180004970`
- `0x1800c6244`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c62ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c62ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c62ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c62ce`

## string_xrefs

- `0x1800c6279`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x1800c630e`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x1800c6260`: `PAL_System_ThreadFree`
- `0x1800c6303`: `PAL_System_ThreadFree`
- `0x1800c6319`: `Failed to CloseHandle on thread. GetLastError: 0x%x`

## pseudocode

```c

```
