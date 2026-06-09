# AudioServerInitialize_Internal(void *,ushort const *,_AUDCLNT_SHAREMODE,ulong,tWAVEFORMATEX const *,_GUID const *,VadServerSettings *,ushort * *,IProcessSubmixProxy *,void * *)

- ea: `0x18006068c`
- end: `0x180060b1d`
- name: `?AudioServerInitialize_Internal@@YAJPEAXPEBGW4_AUDCLNT_SHAREMODE@@KPEBUtWAVEFORMATEX@@PEBU_GUID@@PEAUVadServerSettings@@PEAPEAGPEAUIProcessSubmixProxy@@PEAPEAX@Z`
- size: `1169`
- prototype: `int(void *, const unsigned __int16 *, enum _AUDCLNT_SHAREMODE, unsigned int, const struct tWAVEFORMATEX *, const struct _GUID *, struct VadServerSettings *, unsigned __int16 **, struct IProcessSubmixProxy *, void **)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting`

## callers

- `0x180060630`
- `0x1800dca30`

## callees

- `0x18000accc`
- `0x1800126bc`
- `0x180015324`
- `0x18001b3d0`
- `0x18001c7ac`
- `0x18004d7a4`
- `0x18004ec10`
- `0x18004ff20`
- `0x18004ffa0`
- `0x180053938`
- `0x18006068c`
- `0x1800b6a4c`
- `0x1800cf8c0`
- `0x1800cfd9c`
- `0x1800d8458`
- `0x1800d8530`
- `0x1800d87e4`
- `0x1800d8800`
- `0x1800dc3e4`
- `0x1800dc604`
- `0x1800dc628`
- `0x18016b010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180060713`
- `ntdll!EtwEventActivityIdControl` at `0x180060af5`
- `ntdll!EtwEventActivityIdControl` at `0x180060713`
- `ntdll!EtwEventActivityIdControl` at `0x180060af5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800607ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006084c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800608d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006094c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800609d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060a90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800607ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006084c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800608d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006094c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800609d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060a90`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060814`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060863`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800608ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060963`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800609ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060aa7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060814`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060863`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800608ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060963`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800609ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060aa7`

## string_xrefs

- `0x180060830`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800608b1`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180060926`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800609af`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180060a60`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c

```
