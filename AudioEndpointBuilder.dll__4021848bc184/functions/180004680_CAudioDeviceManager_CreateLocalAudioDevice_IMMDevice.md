# CAudioDeviceManager::CreateLocalAudioDevice(IMMDevice *)

- ea: `0x180004680`
- end: `0x18000471a`
- name: `?CreateLocalAudioDevice@CAudioDeviceManager@@QEAAJPEAUIMMDevice@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(CAudioDeviceManager *__hidden this, struct IMMDevice *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180055054`

## callees

- `0x180004680`
- `0x180004720`
- `0x180010da8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800046d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004710`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800046d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004710`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000469c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000469c`

## string_xrefs

- `0x1800046f6`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c

```
