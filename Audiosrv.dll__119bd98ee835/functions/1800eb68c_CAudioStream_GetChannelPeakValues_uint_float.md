# CAudioStream::GetChannelPeakValues(uint,float *)

- ea: `0x1800eb68c`
- end: `0x1800eb8cc`
- name: `?GetChannelPeakValues@CAudioStream@@QEAAJIPEAM@Z`
- size: `576`
- prototype: `int(CAudioStream *__hidden this, unsigned int, float *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800bf100`

## callees

- `0x18001280c`
- `0x180019468`
- `0x1800424ec`
- `0x1800cbfcc`
- `0x1800cd8d0`
- `0x1800ce774`
- `0x1800eb68c`
- `0x180160690`
- `0x18016c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800eb77f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800eb77f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eb70f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eb70f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb82d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb874`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb8c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb82d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb874`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb8c1`

## string_xrefs

- `0x1800eb6c5`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x1800eb7df`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x1800eb80a`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`
- `0x1800eb8a3`: `avcore\audiocore\server\audiosrv\dll\audiostream.cpp`

## pseudocode

```c

```
