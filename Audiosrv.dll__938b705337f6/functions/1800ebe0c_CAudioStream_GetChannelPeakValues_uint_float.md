# CAudioStream::GetChannelPeakValues(uint,float *)

- ea: `0x1800ebe0c`
- end: `0x1800ec04c`
- name: `?GetChannelPeakValues@CAudioStream@@QEAAJIPEAM@Z`
- size: `576`
- prototype: `int(CAudioStream *__hidden this, unsigned int, float *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800c0c50`

## callees

- `0x1800126bc`
- `0x180019318`
- `0x1800423cc`
- `0x1800cdfbc`
- `0x1800cf8c0`
- `0x1800d0764`
- `0x1800ebe0c`
- `0x18015f980`
- `0x18016b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ebeff`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ebeff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ebe8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ebe8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebfad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebff4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ec041`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebfad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebff4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ec041`

## string_xrefs

- `0x1800ebe45`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x1800ebf5f`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x1800ebf8a`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x1800ec023`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`

## pseudocode

```c

```
