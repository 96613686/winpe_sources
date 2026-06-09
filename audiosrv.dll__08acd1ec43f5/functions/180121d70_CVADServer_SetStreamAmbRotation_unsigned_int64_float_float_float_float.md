# CVADServer::SetStreamAmbRotation(unsigned __int64,float,float,float,float)

- ea: `0x180121d70`
- end: `0x180121eaa`
- name: `?SetStreamAmbRotation@CVADServer@@UEAAJ_KMMMM@Z`
- size: `314`
- prototype: `__int64 __usercall@<rax>(CVADServer *__hidden this@<rcx>, unsigned __int64@<rdx>, float@<xmm2>, float@<xmm3>, float, float)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180124be0`

## callees

- `0x18001280c`
- `0x18005851c`
- `0x1800ec5ec`
- `0x180121d70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180121d9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180121d9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121de2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121e14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121e3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121e88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121de2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121e14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121e3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180121e88`

## string_xrefs

- `0x180121dc8`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180121e28`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c

```
