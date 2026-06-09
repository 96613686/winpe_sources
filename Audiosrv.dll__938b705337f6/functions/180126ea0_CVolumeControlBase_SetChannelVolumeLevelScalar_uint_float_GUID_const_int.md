# CVolumeControlBase::SetChannelVolumeLevelScalar(uint,float,_GUID const *,int *)

- ea: `0x180126ea0`
- end: `0x1801270ae`
- name: `?SetChannelVolumeLevelScalar@CVolumeControlBase@@UEAAJIMPEBU_GUID@@PEAH@Z`
- size: `526`
- prototype: `__int64 __usercall@<rax>(CVolumeControlBase *__hidden this@<rcx>, unsigned int@<edx>, float@<xmm2>, const struct _GUID *@<r9>, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800126bc`
- `0x18002de90`
- `0x180047ee0`
- `0x180058f38`
- `0x180126ea0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180126eee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180126eee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126f26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126f91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012705c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126f26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126f91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012705c`

## string_xrefs

- `0x180126f09`: `avcore\audiocore\server\audiosrv\dll\volumecontrol.cpp`
- `0x180126f78`: `avcore\audiocore\server\audiosrv\dll\volumecontrol.cpp`
- `0x180126fcd`: `avcore\audiocore\server\audiosrv\dll\volumecontrol.cpp`
- `0x180127076`: `avcore\audiocore\server\audiosrv\dll\volumecontrol.cpp`

## pseudocode

```c

```
