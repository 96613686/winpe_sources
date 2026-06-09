# CAudioDeviceManager::CreateRemoteAudioDevice(IMMDevice *,ulong)

- ea: `0x180036de4`
- end: `0x180036e6c`
- name: `?CreateRemoteAudioDevice@CAudioDeviceManager@@QEAAJPEAUIMMDevice@@K@Z`
- size: `136`
- prototype: `__int64 __fastcall(CAudioDeviceManager *__hidden this, struct IMMDevice *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003630`
- `0x180028c64`

## callees

- `0x180004720`
- `0x180010da8`
- `0x180021060`
- `0x180036de4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036e19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036e19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036dfd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036dfd`

## string_xrefs

- `0x180036e42`: `avcore\audiocore\server\audioendpointbuilder\dll\audiodevice.cpp`

## pseudocode

```c

```
