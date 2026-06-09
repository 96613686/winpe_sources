# CPolicyConfig::GetAudioSessionPropertyStore(IAudioSessionInfo *,IPropertyStore * *)

- ea: `0x180033ea4`
- end: `0x1800342e3`
- name: `?GetAudioSessionPropertyStore@CPolicyConfig@@QEAAJPEAUIAudioSessionInfo@@PEAPEAUIPropertyStore@@@Z`
- size: `1087`
- prototype: `__int64 __fastcall(CPolicyConfig *__hidden this, struct IAudioSessionInfo *, struct IPropertyStore **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180069b60`

## callees

- `0x18001280c`
- `0x18001d8d8`
- `0x180033ea4`
- `0x1800570c4`
- `0x180058f38`
- `0x18005afa8`
- `0x180066d40`
- `0x18006a330`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033eca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033eca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800340ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003418d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003426a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800342b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800340ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003418d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003426a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800342b2`

## string_xrefs

- `0x180034242`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`
- `0x18003427f`: `avcore\audiocore\server\audiosrv\dll\policyconfig.cpp`

## pseudocode

```c

```
