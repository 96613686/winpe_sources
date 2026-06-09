# CAudioStream::GetPeakValue(float *)

- ea: `0x180019218`
- end: `0x180019461`
- name: `?GetPeakValue@CAudioStream@@QEAAJPEAM@Z`
- size: `585`
- prototype: `__int64 __fastcall(CAudioStream *__hidden this, float *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800190e0`

## callees

- `0x18001280c`
- `0x180019218`
- `0x180019468`
- `0x1800424ec`
- `0x1800cbfcc`
- `0x1800cd8d0`
- `0x1800ce774`
- `0x180160690`
- `0x18016c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019455`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019455`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001942b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001942b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019253`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019253`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019379`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800193a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001941a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019379`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800193a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001941a`

## string_xrefs

- `0x1800192e5`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x1800193bd`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x1800193d6`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x1800193f7`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`

## pseudocode

```c

```
