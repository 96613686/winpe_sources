# CVolumeControlBase::SetChannelVolumeLevelScalar(uint,float,_GUID const *,int *)

- ea: `0x1801270f0`
- end: `0x1801272fe`
- name: `?SetChannelVolumeLevelScalar@CVolumeControlBase@@UEAAJIMPEBU_GUID@@PEAH@Z`
- size: `526`
- prototype: `__int64 __usercall@<rax>(CVolumeControlBase *__hidden this@<rcx>, unsigned int@<edx>, float@<xmm2>, const struct _GUID *@<r9>, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18001280c`
- `0x18002dff0`
- `0x180047a50`
- `0x180058aa8`
- `0x1801270f0`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012713e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012713e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180127176`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801271e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801272ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180127176`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801271e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801272ac`

## string_xrefs

- `0x180127159`: `avcore\audiocore\server\audiosrv\dll\volumecontrol.cpp`
- `0x1801271c8`: `avcore\audiocore\server\audiosrv\dll\volumecontrol.cpp`
- `0x18012721d`: `avcore\audiocore\server\audiosrv\dll\volumecontrol.cpp`
- `0x1801272c6`: `avcore\audiocore\server\audiosrv\dll\volumecontrol.cpp`

## pseudocode

```c

```
