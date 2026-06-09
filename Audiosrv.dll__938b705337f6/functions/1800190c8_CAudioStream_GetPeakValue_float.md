# CAudioStream::GetPeakValue(float *)

- ea: `0x1800190c8`
- end: `0x180019311`
- name: `?GetPeakValue@CAudioStream@@QEAAJPEAM@Z`
- size: `585`
- prototype: `__int64 __fastcall(CAudioStream *__hidden this, float *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180018f90`

## callees

- `0x1800126bc`
- `0x1800190c8`
- `0x180019318`
- `0x1800423cc`
- `0x1800cdfbc`
- `0x1800cf8c0`
- `0x1800d0764`
- `0x18015f980`
- `0x18016b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019305`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180019305`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800192db`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800192db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019103`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019103`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019229`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019256`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800192ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019229`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019256`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800192ca`

## string_xrefs

- `0x180019195`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x18001926d`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x180019286`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x1800192a7`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`

## pseudocode

```c

```
