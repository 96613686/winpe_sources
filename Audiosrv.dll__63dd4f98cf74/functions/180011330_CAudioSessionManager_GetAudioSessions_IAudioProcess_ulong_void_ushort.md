# CAudioSessionManager::GetAudioSessions(IAudioProcess *,ulong *,void * * *,ushort * * *)

- ea: `0x180011330`
- end: `0x180011dbd`
- name: `?GetAudioSessions@CAudioSessionManager@@UEAAJPEAUIAudioProcess@@PEAKPEAPEAPEAXPEAPEAPEAG@Z`
- size: `2701`
- prototype: `__int64 __fastcall(CAudioSessionManager *this, struct IAudioProcess *, unsigned int *, void ***, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting`

## callees

- `0x18000ae1c`
- `0x18000ffb0`
- `0x1800108c0`
- `0x180011330`
- `0x18001280c`
- `0x180012a0c`
- `0x180012a80`
- `0x1800137b0`
- `0x180052f70`
- `0x1800728c4`
- `0x1800cd8d0`
- `0x1800cddac`
- `0x1800ce750`
- `0x1800ce774`
- `0x1800e7b80`
- `0x1800e7cc0`
- `0x1800e9dbc`
- `0x1800e9e20`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001189b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001189b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011715`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011715`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011bec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011b71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011bec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011c15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011c56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011c56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011c64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011c64`

## string_xrefs

- `0x1800114ac`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x180011a1f`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x180011b26`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x180011ba6`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x180011c39`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x180011c8f`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x180011d58`: `CAudioSessionManager::CreateAudioSessionControl`

## pseudocode

```c

```
