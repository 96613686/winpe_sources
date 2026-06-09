# CAudioSessionManager::GetAudioSessions(IAudioProcess *,ulong *,void * * *,ushort * * *)

- ea: `0x1800111e0`
- end: `0x180011c6d`
- name: `?GetAudioSessions@CAudioSessionManager@@UEAAJPEAUIAudioProcess@@PEAKPEAPEAPEAXPEAPEAPEAG@Z`
- size: `2701`
- prototype: `__int64 __usercall@<rax>(CAudioSessionManager *__hidden this@<rcx>, struct IAudioProcess *@<rdx>, unsigned int *@<r8>, void ***@<r9>, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting`

## callees

- `0x18000accc`
- `0x18000fe60`
- `0x180010770`
- `0x1800111e0`
- `0x1800126bc`
- `0x1800128bc`
- `0x180012930`
- `0x180013660`
- `0x180053400`
- `0x180072dc4`
- `0x1800cf8c0`
- `0x1800cfd9c`
- `0x1800d0740`
- `0x1800d0764`
- `0x1800e8300`
- `0x1800e8440`
- `0x1800ea53c`
- `0x1800ea5a0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001174b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18001174b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800115c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800115c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011888`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ac5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011888`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a21`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011a9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ac5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011b06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011b06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011b14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011b14`

## string_xrefs

- `0x18001135c`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x1800118cf`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x1800119d6`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x180011a56`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x180011ae9`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x180011b3f`: `avcore\audiocore\server\audiosrv\dll\audiosessionmanager.cpp`
- `0x180011c08`: `CAudioSessionManager::CreateAudioSessionControl`

## pseudocode

```c

```
