# AudioServerInitialize_Internal(void *,ushort const *,_AUDCLNT_SHAREMODE,ulong,tWAVEFORMATEX const *,_GUID const *,VadServerSettings *,ushort * *,IProcessSubmixProxy *,void * *)

- ea: `0x1800601fc`
- end: `0x18006068d`
- name: `?AudioServerInitialize_Internal@@YAJPEAXPEBGW4_AUDCLNT_SHAREMODE@@KPEBUtWAVEFORMATEX@@PEBU_GUID@@PEAUVadServerSettings@@PEAPEAGPEAUIProcessSubmixProxy@@PEAPEAX@Z`
- size: `1169`
- prototype: `int(void *, const unsigned __int16 *, enum _AUDCLNT_SHAREMODE, unsigned int, const struct tWAVEFORMATEX *, const struct _GUID *, struct VadServerSettings *, unsigned __int16 **, struct IProcessSubmixProxy *, void **)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting`

## callers

- `0x1800601a0`
- `0x1800daa40`

## callees

- `0x18000ae1c`
- `0x18001280c`
- `0x180015474`
- `0x18001b520`
- `0x18001c8fc`
- `0x18004d314`
- `0x18004e780`
- `0x18004fa90`
- `0x18004fb10`
- `0x1800534a8`
- `0x1800601fc`
- `0x1800b4d5c`
- `0x1800cd8d0`
- `0x1800cddac`
- `0x1800d6468`
- `0x1800d6540`
- `0x1800d67f4`
- `0x1800d6810`
- `0x1800da3f4`
- `0x1800da614`
- `0x1800da638`
- `0x18016c010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180060283`
- `ntdll!EtwEventActivityIdControl` at `0x180060665`
- `ntdll!EtwEventActivityIdControl` at `0x180060283`
- `ntdll!EtwEventActivityIdControl` at `0x180060665`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006035d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800603bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060447`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800604bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060545`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060600`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006035d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800603bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060447`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800604bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060545`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060600`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060384`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800603d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006045e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800604d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006055c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060617`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060384`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800603d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006045e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800604d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006055c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060617`

## string_xrefs

- `0x1800603a0`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180060421`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180060496`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x18006051f`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800605d0`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`

## pseudocode

```c

```
