# CPolicyConfig::GetAudioSessionPropertyStore(IAudioSessionInfo *,IPropertyStore * *)

- ea: `0x180033d44`
- end: `0x180034183`
- name: `?GetAudioSessionPropertyStore@CPolicyConfig@@QEAAJPEAUIAudioSessionInfo@@PEAPEAUIPropertyStore@@@Z`
- size: `1087`
- prototype: `__int64 __fastcall(CPolicyConfig *__hidden this, struct IAudioSessionInfo *, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180069ff0`

## callees

- `0x1800126bc`
- `0x18001d788`
- `0x180033d44`
- `0x180057554`
- `0x1800593c8`
- `0x18005b438`
- `0x1800671d0`
- `0x18006a7c0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033d6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033d6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033f5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003402d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003410a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034152`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033f5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003402d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003410a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034152`

## string_xrefs

- `0x1800340e2`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18003411f`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`

## pseudocode

```c

```
