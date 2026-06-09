# CVolumeControlBase::SetAllChannelVolumeLevelScalar(uint,float const *,_GUID const *,int *)

- ea: `0x180126b40`
- end: `0x180126cc3`
- name: `?SetAllChannelVolumeLevelScalar@CVolumeControlBase@@UEAAJIPEBMPEBU_GUID@@PEAH@Z`
- size: `387`
- prototype: `__int64 __usercall@<rax>(CVolumeControlBase *__hidden this@<rcx>, unsigned int@<edx>, const float *@<r8>, const struct _GUID *@<r9>, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800126bc`
- `0x18002ddcc`
- `0x18002de90`
- `0x180047ee0`
- `0x180058f38`
- `0x180126b40`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180126b65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180126b65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126b97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126c14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126c65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126caa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126b97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126c14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126c65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180126caa`

## string_xrefs

- `0x180126b76`: `avcore\audiocore\server\audiosrv\dll\volumecontrol.cpp`
- `0x180126bf8`: `avcore\audiocore\server\audiosrv\dll\volumecontrol.cpp`
- `0x180126c49`: `avcore\audiocore\server\audiosrv\dll\volumecontrol.cpp`

## pseudocode

```c

```
