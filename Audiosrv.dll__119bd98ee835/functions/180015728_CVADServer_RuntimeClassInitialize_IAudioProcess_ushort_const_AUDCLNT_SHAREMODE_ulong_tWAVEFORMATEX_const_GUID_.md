# CVADServer::RuntimeClassInitialize(IAudioProcess *,ushort const *,_AUDCLNT_SHAREMODE,ulong,tWAVEFORMATEX const *,_GUID const *,VadServerSettings *,ushort * *,IProcessSubmixProxy *)

- ea: `0x180015728`
- end: `0x180015c95`
- name: `?RuntimeClassInitialize@CVADServer@@QEAAJPEAUIAudioProcess@@PEBGW4_AUDCLNT_SHAREMODE@@KPEBUtWAVEFORMATEX@@PEBU_GUID@@PEAUVadServerSettings@@PEAPEAGPEAUIProcessSubmixProxy@@@Z`
- size: `1389`
- prototype: `__int64 __usercall@<rax>(CVADServer *__hidden this@<rcx>, struct IAudioProcess *@<rdx>, const unsigned __int16 *@<r8>, enum _AUDCLNT_SHAREMODE@<r9d>, unsigned int, const struct tWAVEFORMATEX *Src, const struct _GUID *, struct VadServerSettings *, unsigned __int16 **, struct IProcessSubmixProxy *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting`

## callers

- `0x180015474`

## callees

- `0x18000ad20`
- `0x180011ec0`
- `0x18001280c`
- `0x180015728`
- `0x18001e92c`
- `0x18002318c`
- `0x18002e354`
- `0x180031a7c`
- `0x180032ffc`
- `0x18003d040`
- `0x18004d1d4`
- `0x180050730`
- `0x180053e64`
- `0x18005afa8`
- `0x1800cbfcc`
- `0x1800cdd70`
- `0x1800cddac`
- `0x1800ce75c`
- `0x180120880`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001576a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015bf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001576a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015bf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800157a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015838`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800157a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015838`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015c72`

## string_xrefs

- `0x180015789`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800157c0`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180015819`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180015865`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180015a38`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180015af5`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180015b43`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180015c4e`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c

```
