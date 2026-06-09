# CVADServer::RuntimeClassInitialize(IAudioProcess *,ushort const *,_AUDCLNT_SHAREMODE,ulong,tWAVEFORMATEX const *,_GUID const *,VadServerSettings *,ushort * *,IProcessSubmixProxy *)

- ea: `0x1800155d8`
- end: `0x180015b45`
- name: `?RuntimeClassInitialize@CVADServer@@QEAAJPEAUIAudioProcess@@PEBGW4_AUDCLNT_SHAREMODE@@KPEBUtWAVEFORMATEX@@PEBU_GUID@@PEAUVadServerSettings@@PEAPEAGPEAUIProcessSubmixProxy@@@Z`
- size: `1389`
- prototype: `__int64 __usercall@<rax>(CVADServer *__hidden this@<rcx>, struct IAudioProcess *@<rdx>, const unsigned __int16 *@<r8>, enum _AUDCLNT_SHAREMODE@<r9d>, unsigned int, const struct tWAVEFORMATEX *Src, const struct _GUID *, struct VadServerSettings *, unsigned __int16 **, struct IProcessSubmixProxy *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting`

## callers

- `0x180015324`

## callees

- `0x18000abd0`
- `0x180011d70`
- `0x1800126bc`
- `0x1800155d8`
- `0x18001e7dc`
- `0x18002303c`
- `0x18002e1f4`
- `0x18003191c`
- `0x180032e9c`
- `0x18003cee0`
- `0x18004d664`
- `0x180050bc0`
- `0x1800542f4`
- `0x18005b438`
- `0x1800cdfbc`
- `0x1800cfd60`
- `0x1800cfd9c`
- `0x1800d074c`
- `0x180120630`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001561a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015aa4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001561a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015aa4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015653`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800156e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001590c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015abf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015653`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800156e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001590c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015abf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b22`

## string_xrefs

- `0x180015639`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180015670`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800156c9`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180015715`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800158e8`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800159a5`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800159f3`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180015afe`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c

```
