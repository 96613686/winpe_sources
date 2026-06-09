# CAudioResourceManager::CreateStream(IAudioProcess *,IAudioStreamInfo *,ulong,int,int,int,int,int,int,__int64,EndpointCharacteristicsDescriptor *,ulong,_AUDCLNT_SHAREMODE,IAudioGraphCallback *,tWAVEFORMATEX *,__int64,__int64,_GUID const *,_GUID const *,_GUID const *,ulong,ushort const *,ulong,SPATIAL_STREAM_PROPERTIES const *,_BridgeStreamProperties,__int64,ulong,IProcessSubmixProxy *,SystemAudioStream *)

- ea: `0x180073490`
- end: `0x180078508`
- name: `?CreateStream@CAudioResourceManager@@UEAAJPEAUIAudioProcess@@PEAUIAudioStreamInfo@@KHHHHHH_JPEAUEndpointCharacteristicsDescriptor@@KW4_AUDCLNT_SHAREMODE@@PEAUIAudioGraphCallback@@PEAUtWAVEFORMATEX@@22PEBU_GUID@@77KPEBGKPEBUSPATIAL_STREAM_PROPERTIES@@W4_BridgeStreamProperties@@2KPEAUIProcessSubmixProxy@@PEAUSystemAudioStream@@@Z`
- size: `20600`
- prototype: `__int64 __fastcall(__int64, __int64, struct IAudioStreamInfo *, unsigned int, unsigned int, unsigned int, int, int, int, int, __int64, struct EndpointCharacteristicsDescriptor *, unsigned int, enum _AUDCLNT_SHAREMODE, __int64, struct _RTL_CRITICAL_SECTION *, __int64, LPVOID, __int64, __int64, __int64, int, struct _RTL_CRITICAL_SECTION *, int, void *, int, __int64, int, struct IProcessSubmixProxy *, __int64)`
- caller_count: `0`
- callee_count: `58`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180008a2c`
- `0x180008f40`
- `0x180008fa8`
- `0x180009864`
- `0x18000ae1c`
- `0x18000cba0`
- `0x18000cc30`
- `0x18000e2a4`
- `0x18001280c`
- `0x1800182e8`
- `0x180019998`
- `0x18001b520`
- `0x18001d7ec`
- `0x18001d8d8`
- `0x18001e0b0`
- `0x18001ec9c`
- `0x180023100`
- `0x180025eb4`
- `0x18002659c`
- `0x18002c4c0`
- `0x1800318d8`
- `0x180031c80`
- `0x18003865c`
- `0x180039510`
- `0x18003a1e0`
- `0x1800424ec`
- `0x180045330`
- `0x1800467ac`
- `0x180049efc`
- `0x18004f2fc`
- `0x180050920`
- `0x18005abac`
- `0x18005eeb0`
- `0x180061430`
- `0x180061d20`
- `0x180061e64`
- `0x180062a0c`
- `0x180062e30`
- `0x180071c1c`
- `0x180072e10`
- `0x180073490`
- `0x180078510`
- `0x180078e2c`
- `0x1800a45f0`
- `0x1800a4af8`
- `0x1800a4da0`
- `0x1800a6b34`
- `0x1800a91f0`
- `0x1800af6ac`
- `0x1800b571c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074ec2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074fde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800750bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800750ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800750f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800752a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800752af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800752d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075416`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075425`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075447`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800755a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800755b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800755d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075807`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075816`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075838`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075a40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075a4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075a71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075c68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075c8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075fd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075feb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007600d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007622c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007623b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007625d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800764be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800764cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800764ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074ec2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180074fde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800750bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800750ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800750f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800752a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800752af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800752d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075416`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075425`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075447`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800755a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800755b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800755d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075807`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075816`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075838`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075a40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075a4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075a71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075c59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075c68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075c8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075fd7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180075feb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007600d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007622c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007623b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007625d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800764be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800764cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800764ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800763dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800763dd`
- `RPCRT4!RpcImpersonateClient` at `0x18007788f`
- `RPCRT4!RpcImpersonateClient` at `0x18007788f`
- `RPCRT4!RpcRevertToSelf` at `0x180077a72`
- `RPCRT4!RpcRevertToSelf` at `0x180077c04`
- `RPCRT4!RpcRevertToSelf` at `0x180077d9c`
- `RPCRT4!RpcRevertToSelf` at `0x180077ed7`
- `RPCRT4!RpcRevertToSelf` at `0x180077a72`
- `RPCRT4!RpcRevertToSelf` at `0x180077c04`
- `RPCRT4!RpcRevertToSelf` at `0x180077d9c`
- `RPCRT4!RpcRevertToSelf` at `0x180077ed7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073acc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073b04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073b20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073b7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073b97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073bcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800747e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074804`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074820`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007483c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074b04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074b20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074b3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074c52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074c6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074c8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074ca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074dab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074de3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074dff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074f18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074f34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074f50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074f6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075146`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075162`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007517e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007519a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075327`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007535f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007537b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007549d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800754b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800754d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800754f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007562b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075663`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007567f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007588e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800758aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800758c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800758e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075ac7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075ae3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075aff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075b1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075d18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075d34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076063`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007607f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007609b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800760b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800762b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800762cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800762eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076307`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076561`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007657d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076599`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073acc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073b04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073b20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073b7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073b97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073bcf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800747e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074804`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074820`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007483c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074ae8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074b04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074b20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074b3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074c52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074c6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074c8a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074ca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074dab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074dc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074de3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074dff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074f18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074f34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074f50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074f6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075146`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075162`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007517e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007519a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075327`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007535f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007537b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007549d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800754b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800754d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800754f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007562b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075647`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075663`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007567f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007588e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800758aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800758c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800758e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075ac7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075ae3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075aff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075b1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075d18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075d34`

## string_xrefs

- `0x180073646`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800738a1`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180073b54`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800747c1`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180074a95`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180074bff`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180074d4a`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180074e95`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800750a0`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180075281`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800753e9`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180075569`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x18007579c`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800759c7`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180075bee`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800761bb`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x18007642c`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800765e9`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800767ef`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180076b72`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180076efb`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180077261`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800775c5`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180077747`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800778a8`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180077a60`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180077bf2`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180077d8a`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180077f22`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800780a0`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x18007824f`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

## pseudocode

```c
__int64 __fastcall CAudioResourceManager::CreateStream(
        __int64 a1,
        __int64 a2,
        struct IAudioStreamInfo *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        __int64 a11,
        struct EndpointCharacteristicsDescriptor *a12,
        unsigned int a13,
        enum _AUDCLNT_SHAREMODE a14,
        __int64 a15,
        struct _RTL_CRITICAL_SECTION *a16,
        __int64 a17,
        LPVOID a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        int a22,
        struct _RTL_CRITICAL_SECTION *a23,
        int a24,
        void *a25,
        int a26,
        __int64 a27,
        int a28,
        struct IProcessSubmixProxy *a29,
        __int64 a30)
{
  int v31; // esi
  bool v32; // zf
  __int64 v33; // rdx
  char v34; // r15
  int v35; // eax
  unsigned int v36; // ebx
  __int64 AudioPumpDspResourceTokenFromTokenList; // rax
  struct _RTL_CRITICAL_SECTION *v39; // rdi
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 ConnectorTypeForStream; // edx
  __int64 v41; // rcx
  __int64 v42; // r13
  LPCRITICAL_SECTION v43; // rsi
  unsigned int v44; // r13d
  int v45; // eax
  unsigned int v46; // ebx
  GUID v47; // xmm7
  struct _GUID v48; // xmm8
  struct _GUID v49; // xmm6
  int v50; // ebx
  void *v51; // rcx
  void *v52; // rcx
  struct tWAVEFORMATEX *v53; // rcx
  void *v54; // rcx
  void *v55; // rcx
  void *v56; // rcx
  struct tWAVEFORMATEX *v57; // rcx
  void *v58; // rcx
  _DWORD *v59; // r8
  int v60; // r8d
  int v61; // r9d
  char *v62; // rdi
  _DWORD *v63; // r8
  int v64; // r8d
  int v65; // r9d
  _DWORD *v66; // r8
  int v67; // r8d
  int v68; // r9d
  _DWORD *v69; // r8
  int v70; // r8d
  int v71; // r9d
  int v72; // ecx
  _DWORD *v73; // r8
  int v74; // r8d
  int v75; // r9d
  _DWORD *v76; // r8
  int v77; // r8d
  int v78; // r9d
  char *v79; // rdi
  _DWORD *v80; // r8
  int v81; // r8d
  int v82; // r9d
  int v83; // ecx
  _DWORD *v84; // r8
  int v85; // r8d
  int v86; // r9d
  _DWORD *v87; // r8
  int v88; // r8d
  int v89; // r9d
  struct tWAVEFORMATEX *v90; // rdi
  _DWORD *v91; // r8
  int v92; // r8d
  int v93; // r9d
  int wFormatTag; // ecx
  _DWORD *v95; // r8
  int v96; // r8d
  int v97; // r9d
  _DWORD *v98; // r8
  int v99; // r8d
  int v100; // r9d
  char *v101; // rdi
  _DWORD *v102; // r8
  int v103; // r8d
  int v104; // r9d
  int v105; // ecx
  _DWORD *v106; // r8
  int v107; // r8d
  int v108; // r9d
  _DWORD *v109; // r8
  int v110; // r8d
  int v111; // r9d
  LPCRITICAL_SECTION v112; // r13
  int v113; // eax
  int v114; // ebx
  void *v115; // rcx
  void *v116; // rcx
  struct tWAVEFORMATEX *v117; // rcx
  void *v118; // rcx
  __int64 v119; // rbx
  __int64 v120; // rax
  int v121; // esi
  unsigned int v122; // r13d
  void *v123; // rcx
  void *v124; // rcx
  struct tWAVEFORMATEX *v125; // rcx
  void *v126; // rcx
  _QWORD *v127; // rax
  __int64 v128; // rcx
  int v129; // r8d
  __int64 v130; // rcx
  int v131; // edx
  __int64 v132; // rbx
  struct _GUID v133; // xmm6
  int DefaultAecReferenceEndpointId; // eax
  void *v135; // rcx
  void *v136; // rcx
  struct tWAVEFORMATEX *v137; // rcx
  void *v138; // rcx
  __int64 v139; // rcx
  __int64 v140; // rax
  int EndpointStore; // eax
  void *v142; // rcx
  void *v143; // rcx
  struct tWAVEFORMATEX *v144; // rcx
  void *v145; // rcx
  CEndpointCharacteristics *v146; // rcx
  int CustomResourceManagerService; // eax
  void *v148; // rcx
  void *v149; // rcx
  struct tWAVEFORMATEX *v150; // rcx
  void *v151; // rcx
  struct _RTL_CRITICAL_SECTION *v152; // rbx
  __int64 v153; // rax
  int v154; // eax
  int v155; // edi
  void *v156; // rcx
  void *v157; // rcx
  struct tWAVEFORMATEX *v158; // rcx
  void *v159; // rcx
  int v160; // eax
  __int64 v161; // rdx
  void *v162; // rcx
  void *v163; // rcx
  struct tWAVEFORMATEX *v164; // rcx
  void *v165; // rcx
  __int64 (__fastcall *v166)(struct IAudioStreamInfo *, __int128 *); // rdi
  int v167; // eax
  __int64 v168; // rdx
  void *v169; // rcx
  void *v170; // rcx
  struct tWAVEFORMATEX *v171; // rcx
  void *v172; // rcx
  __int64 v173; // rsi
  __int64 (__fastcall *v174)(__int64, GUID *); // rdi
  int v175; // eax
  void *v176; // rcx
  void *v177; // rcx
  struct tWAVEFORMATEX *v178; // rcx
  void *v179; // rcx
  char v180; // al
  __int64 v181; // rdx
  bool v182; // r13
  __int64 v183; // rax
  __int64 v184; // rdx
  void *v185; // rcx
  void *v186; // rcx
  struct tWAVEFORMATEX *v187; // rcx
  void *v188; // rcx
  bool v189; // si
  bool v190; // di
  __int64 v191; // rax
  int v192; // eax
  void *v193; // rcx
  void *v194; // rcx
  struct tWAVEFORMATEX *v195; // rcx
  void *v196; // rcx
  const struct tWAVEFORMATEX *v197; // rax
  int v198; // eax
  __int64 v199; // rdx
  void *v200; // rcx
  void *v201; // rcx
  struct tWAVEFORMATEX *v202; // rcx
  void *v203; // rcx
  bool v204; // si
  char v205; // al
  unsigned int v206; // r13d
  struct IProcessSubmixProxy **v207; // rsi
  LPCRITICAL_SECTION v208; // rax
  struct IProcessSubmixProxy *v209; // rdi
  const struct tWAVEFORMATEX *v210; // rax
  __int64 v211; // r13
  _DWORD *v212; // r8
  int v213; // r8d
  int v214; // r9d
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v215; // esi
  void *v216; // rcx
  void *v217; // rcx
  struct tWAVEFORMATEX *v218; // rcx
  void *v219; // rcx
  __int64 v220; // rdx
  bool DoesExclusiveModeOverrideShared; // si
  void *v222; // rcx
  void *v223; // rcx
  struct tWAVEFORMATEX *v224; // rcx
  void *v225; // rcx
  int SaDeviceForExclusiveStream; // eax
  __int64 v227; // rcx
  int v228; // r8d
  unsigned int v229; // ebx
  int SaDeviceForOffloadedStream; // eax
  unsigned int v231; // r13d
  int SaDeviceForSharedStream; // eax
  __int64 v233; // rbx
  char v234; // al
  int v235; // eax
  int v236; // ecx
  int v237; // r8d
  __int64 v238; // rax
  int v239; // ebx
  _DWORD *v240; // rbx
  int v241; // r8d
  int v242; // r9d
  bool v243; // cf
  __int64 v244; // r13
  __int64 v245; // rdi
  __int64 (__fastcall *v246)(__int64, unsigned int *); // rbx
  int v247; // eax
  __int64 v248; // rax
  int v249; // eax
  unsigned int v250; // eax
  int v251; // eax
  __int64 v252; // rcx
  int v253; // eax
  __int64 v254; // rcx
  int v255; // eax
  int v256; // eax
  int v257; // eax
  int v258; // eax
  __int64 v259; // rdx
  int v260; // [rsp+20h] [rbp-598h]
  int v261; // [rsp+20h] [rbp-598h]
  int v262; // [rsp+20h] [rbp-598h]
  int v263; // [rsp+20h] [rbp-598h]
  __int64 v264; // [rsp+20h] [rbp-598h]
  int v265; // [rsp+20h] [rbp-598h]
  int v266; // [rsp+20h] [rbp-598h]
  int v267; // [rsp+20h] [rbp-598h]
  unsigned int v268; // [rsp+20h] [rbp-598h]
  struct tWAVEFORMATEX **v269; // [rsp+48h] [rbp-570h]
  int v270; // [rsp+F0h] [rbp-4C8h] BYREF
  bool v271[4]; // [rsp+F4h] [rbp-4C4h] BYREF
  LPVOID pv; // [rsp+F8h] [rbp-4C0h] BYREF
  LPVOID v273; // [rsp+100h] [rbp-4B8h] BYREF
  struct tWAVEFORMATEX *Src; // [rsp+108h] [rbp-4B0h] BYREF
  LPVOID v275; // [rsp+110h] [rbp-4A8h] BYREF
  struct CEndpointStore *v276; // [rsp+118h] [rbp-4A0h] BYREF
  struct EndpointCharacteristicsDescriptor *v277; // [rsp+120h] [rbp-498h] BYREF
  struct IUnknown *v278; // [rsp+128h] [rbp-490h] BYREF
  __int64 v279; // [rsp+130h] [rbp-488h] BYREF
  void *v280; // [rsp+138h] [rbp-480h] BYREF
  __int64 v281[2]; // [rsp+140h] [rbp-478h] BYREF
  GUID v282; // [rsp+150h] [rbp-468h] BYREF
  struct _GUID v283; // [rsp+160h] [rbp-458h] BYREF
  LPCRITICAL_SECTION v284[2]; // [rsp+170h] [rbp-448h] BYREF
  unsigned int v285; // [rsp+180h] [rbp-438h]
  LPCRITICAL_SECTION v286; // [rsp+188h] [rbp-430h] BYREF
  unsigned int v287[4]; // [rsp+190h] [rbp-428h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+1A0h] [rbp-418h] BYREF
  __int128 v289; // [rsp+1B0h] [rbp-408h] BYREF
  __int64 v290; // [rsp+1C0h] [rbp-3F8h]
  int v291; // [rsp+1C8h] [rbp-3F0h]
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v292; // [rsp+1CCh] [rbp-3ECh]
  __int64 v293; // [rsp+1D0h] [rbp-3E8h] BYREF
  struct IProcessSubmixProxy *v294; // [rsp+1D8h] [rbp-3E0h] BYREF
  LPCRITICAL_SECTION v295; // [rsp+1E0h] [rbp-3D8h] BYREF
  __int64 *p_pv; // [rsp+1E8h] [rbp-3D0h] BYREF
  struct tWAVEFORMATEX *v297; // [rsp+1F0h] [rbp-3C8h] BYREF
  char v298; // [rsp+1F8h] [rbp-3C0h]
  __int64 v299; // [rsp+200h] [rbp-3B8h] BYREF
  int v300[2]; // [rsp+208h] [rbp-3B0h]
  __int64 v301; // [rsp+210h] [rbp-3A8h] BYREF
  __int64 v302; // [rsp+218h] [rbp-3A0h] BYREF
  __int64 v303; // [rsp+220h] [rbp-398h] BYREF
  struct tWAVEFORMATEX **p_Src; // [rsp+228h] [rbp-390h] BYREF
  struct tWAVEFORMATEX *v305; // [rsp+230h] [rbp-388h] BYREF
  char v306; // [rsp+238h] [rbp-380h]
  __int64 v307; // [rsp+240h] [rbp-378h] BYREF
  __int64 v308; // [rsp+248h] [rbp-370h] BYREF
  __int64 v309; // [rsp+250h] [rbp-368h]
  __int64 v310; // [rsp+258h] [rbp-360h]
  struct _GUID v311; // [rsp+260h] [rbp-358h] BYREF
  _BYTE v312[304]; // [rsp+270h] [rbp-348h] BYREF
  _BYTE v313[304]; // [rsp+3A0h] [rbp-218h] BYREF
  struct _GUID v314; // [rsp+4D0h] [rbp-E8h] BYREF
  __int128 v315; // [rsp+4E0h] [rbp-D8h] BYREF
  char v316; // [rsp+4F0h] [rbp-C8h]
  struct _GUID v317; // [rsp+500h] [rbp-B8h] BYREF
  __int64 v318; // [rsp+510h] [rbp-A8h]
  LPVOID *v319; // [rsp+520h] [rbp-98h] BYREF
  struct tWAVEFORMATEX *v320; // [rsp+528h] [rbp-90h] BYREF
  enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 v321; // [rsp+530h] [rbp-88h]
  GUID v322; // [rsp+534h] [rbp-84h]
  int v323; // [rsp+544h] [rbp-74h]
  wil::details::in1diag3 *retaddr; // [rsp+5B8h] [rbp+0h]

  v287[0] = a4;
  v299 = a2;
  v302 = a1;
  lpCriticalSection[0] = a16;
  v277 = a12;
  v310 = a15;
  v301 = a19;
  v309 = a20;
  v303 = a21;
  v295 = a23;
  v280 = a25;
  v294 = a29;
  *(_QWORD *)v300 = a30;
  v31 = (*(unsigned __int8 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a3 + 208LL))(a3);
  v32 = (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v277 + 56LL))(*(_QWORD *)v277) == 0;
  v285 = a13;
  v34 = 1;
  if ( v32 )
  {
    if ( (a13 & 0x20000) != 0 )
      v291 = (v31 != 0) + 2;
    else
      v291 = 0;
  }
  else
  {
    v291 = 1;
  }
  v289 = 0;
  v290 = 0;
  v278 = 0;
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v278, v33);
  v35 = CAudioPumpDspResourceTracker::AcquireAudioPumpDspTokenForEndpoint(s_DspResourceTracker, v277, &v278);
  v36 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F5,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v35,
      v260);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v278);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v289);
    return v36;
  }
  if ( *((_QWORD *)&v289 + 1) == v290 )
  {
    std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<IUnknown,wil::err_returncode_policy> const &>(
      &v289,
      *((_QWORD *)&v289 + 1),
      &v278);
  }
  else
  {
    wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(
      *((_QWORD *)&v289 + 1),
      v278);
    *((_QWORD *)&v289 + 1) += 8LL;
  }
  v283 = GUID_00000000_0000_0000_0000_000000000000;
  v314 = GUID_00000000_0000_0000_0000_000000000000;
  v282 = GUID_00000000_0000_0000_0000_000000000000;
  v311 = GUID_00000000_0000_0000_0000_000000000000;
  v317 = GUID_00000000_0000_0000_0000_000000000000;
  AudioPumpDspResourceTokenFromTokenList = TryGetAudioPumpDspResourceTokenFromTokenList(&v315, &v289);
  v39 = *(struct _RTL_CRITICAL_SECTION **)(AudioPumpDspResourceTokenFromTokenList + 8);
  *(_QWORD *)(AudioPumpDspResourceTokenFromTokenList + 8) = 0;
  v284[0] = v39;
  AudioPumpDspResourceTokenPair::~AudioPumpDspResourceTokenPair((AudioPumpDspResourceTokenPair *)&v315);
  ConnectorTypeForStream = GetConnectorTypeForStream(
                             v277,
                             a13,
                             a14,
                             v31,
                             (const struct tWAVEFORMATEX *)a16,
                             v294,
                             (struct IUnknown *)v39);
  v292 = ConnectorTypeForStream;
  v41 = (__int64)a3 + 624;
  if ( !a3 )
    v41 = 632;
  *(_DWORD *)v41 = ConnectorTypeForStream;
  v286 = 0;
  if ( !v39 )
  {
    v42 = a17;
LABEL_15:
    v293 = v42;
    goto LABEL_20;
  }
  if ( ConnectorTypeForStream == eHostProcessConnector && (a13 & 1) != 0 )
  {
    v285 = a13 & 0x77FFFFFC | 0x88000002;
    v286 = (LPCRITICAL_SECTION)a18;
    a18 = 0;
    v42 = 2 * a17;
    goto LABEL_15;
  }
  v293 = a17;
LABEL_20:
  v43 = lpCriticalSection[0];
  v261 = v291;
  v44 = v287[0];
  v45 = DeriveAudioProcessingModeConfiguration(v287[0], a5, a6, v277);
  v46 = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x616,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v45,
      v261);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v284);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v278);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v289);
    return v46;
  }
  if ( v39 )
    v47 = GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf;
  else
    v47 = v283;
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v284);
  v275 = 0;
  Src = 0;
  v273 = 0;
  pv = 0;
  p_pv = (__int64 *)&pv;
  v297 = 0;
  v298 = 1;
  p_Src = &Src;
  v305 = 0;
  v306 = 1;
  v319 = &v273;
  v320 = 0;
  LOBYTE(v321) = 1;
  *(_QWORD *)&v315 = &v275;
  *((_QWORD *)&v315 + 1) = 0;
  v316 = 1;
  v48 = v314;
  v49 = v282;
  v271[0] = a8 != 0;
  *(GUID *)v284 = v47;
  v283 = v314;
  v314 = v282;
  v50 = DeriveDeviceGraphFormatsForStream(
          (CEndpointCharacteristics **)v277,
          a8 != 0,
          v292,
          a14,
          v44,
          (IAudioMediaType *)&v314,
          &v283,
          (struct _GUID *)v284,
          (struct tWAVEFORMATEX *)v43,
          (struct tWAVEFORMATEX **)&v315 + 1,
          &v320,
          &v305,
          &v297);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v315);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v319);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_Src);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v50 < 0 )
  {
    if ( v50 == -2005139333 )
    {
      v51 = pv;
      pv = 0;
      if ( v51 )
        CoTaskMemFree(v51);
      v52 = v273;
      v273 = 0;
      if ( v52 )
        CoTaskMemFree(v52);
      v53 = Src;
      Src = 0;
      if ( v53 )
        CoTaskMemFree(v53);
      v54 = v275;
      v275 = 0;
      if ( v54 )
        CoTaskMemFree(v54);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v278);
      std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v289);
      return 2289827963LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x621,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v50,
        v262);
      v55 = pv;
      pv = 0;
      if ( v55 )
        CoTaskMemFree(v55);
      v56 = v273;
      v273 = 0;
      if ( v56 )
        CoTaskMemFree(v56);
      v57 = Src;
      Src = 0;
      if ( v57 )
        CoTaskMemFree(v57);
      v58 = v275;
      v275 = 0;
      if ( v58 )
        CoTaskMemFree(v58);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v278);
      std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v289);
      return (unsigned int)v50;
    }
  }
  if ( v43 )
  {
    if ( LOWORD(v43->DebugInfo) == 0xFFFE )
    {
      v69 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v69 > 4u && (unsigned __int8)tlgKeywordOn(v69, 512) )
      {
        v282.Data1 = HIDWORD(v43->OwningThread);
        v284[0] = (LPCRITICAL_SECTION)&v43->LockSemaphore;
        LODWORD(v315) = v43->LockCount;
        v314.Data1 = HIDWORD(v43->DebugInfo);
        LOWORD(v270) = WORD1(v43->DebugInfo);
        *(_QWORD *)&v283.Data1 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v70,
          (unsigned int)byte_1801A347D,
          v70,
          v71,
          (__int64)&v283,
          (__int64)&v270,
          (__int64)&v314,
          (__int64)&v315,
          (__int64)v284,
          (__int64)&v282);
      }
    }
    else
    {
      *(_QWORD *)&v314.Data2 = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      *(_DWORD *)&v314.Data4[4] = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      v314.Data1 = LOWORD(v43->DebugInfo);
      v66 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v66 > 4u && (unsigned __int8)tlgKeywordOn(v66, 512) )
      {
        v284[0] = (LPCRITICAL_SECTION)&v314;
        LODWORD(v315) = v43->LockCount;
        v282.Data1 = HIDWORD(v43->DebugInfo);
        LOWORD(v270) = WORD1(v43->DebugInfo);
        *(_QWORD *)&v283.Data1 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v67,
          (unsigned int)&byte_1801A350F,
          v67,
          v68,
          (__int64)&v283,
          (__int64)&v270,
          (__int64)&v282,
          (__int64)&v315,
          (__int64)v284);
      }
    }
  }
  else
  {
    v59 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v59 > 4u && (unsigned __int8)tlgKeywordOn(v59, 512) )
    {
      v270 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v60,
        (unsigned int)&dword_1801A3594,
        v60,
        v61,
        (__int64)&v270);
    }
  }
  v62 = (char *)v275;
  if ( v275 )
  {
    v72 = *(unsigned __int16 *)v275;
    if ( (_WORD)v72 == 0xFFFE )
    {
      v76 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v76 > 4u && (unsigned __int8)tlgKeywordOn(v76, 512) )
      {
        v314.Data1 = *((_DWORD *)v62 + 5);
        v284[0] = (LPCRITICAL_SECTION)(v62 + 24);
        v282.Data1 = *((_DWORD *)v275 + 2);
        LODWORD(v315) = *((_DWORD *)v275 + 1);
        LOWORD(v270) = *((_WORD *)v275 + 1);
        *(_QWORD *)&v283.Data1 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v77,
          (unsigned int)&dword_1801A3314,
          v77,
          v78,
          (__int64)&v283,
          (__int64)&v270,
          (__int64)&v315,
          (__int64)&v282,
          (__int64)v284,
          (__int64)&v314);
      }
    }
    else
    {
      *(_QWORD *)((char *)&v315 + 4) = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      HIDWORD(v315) = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      LODWORD(v315) = v72;
      v73 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v73 > 4u && (unsigned __int8)tlgKeywordOn(v73, 512) )
      {
        v284[0] = (LPCRITICAL_SECTION)&v315;
        v314.Data1 = *((_DWORD *)v275 + 2);
        v282.Data1 = *((_DWORD *)v275 + 1);
        LOWORD(v270) = *((_WORD *)v275 + 1);
        *(_QWORD *)&v283.Data1 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v74,
          (unsigned int)&unk_1801A33A8,
          v74,
          v75,
          (__int64)&v283,
          (__int64)&v270,
          (__int64)&v282,
          (__int64)&v314,
          (__int64)v284);
      }
    }
  }
  else
  {
    v63 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v63 > 4u && (unsigned __int8)tlgKeywordOn(v63, 512) )
    {
      v314.Data1 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v64,
        (unsigned int)&byte_1801A342F,
        v64,
        v65,
        (__int64)&v314);
    }
  }
  v79 = (char *)v273;
  if ( v273 )
  {
    v83 = *(unsigned __int16 *)v273;
    if ( (_WORD)v83 == 0xFFFE )
    {
      v87 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v87 > 4u && (unsigned __int8)tlgKeywordOn(v87, 512) )
      {
        v314.Data1 = *((_DWORD *)v79 + 5);
        v284[0] = (LPCRITICAL_SECTION)(v79 + 24);
        v282.Data1 = *((_DWORD *)v273 + 2);
        LODWORD(v315) = *((_DWORD *)v273 + 1);
        LOWORD(v270) = *((_WORD *)v273 + 1);
        *(_QWORD *)&v283.Data1 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v88,
          (unsigned int)word_1801A31A2,
          v88,
          v89,
          (__int64)&v283,
          (__int64)&v270,
          (__int64)&v315,
          (__int64)&v282,
          (__int64)v284,
          (__int64)&v314);
      }
    }
    else
    {
      *(_QWORD *)((char *)&v315 + 4) = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      HIDWORD(v315) = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      LODWORD(v315) = v83;
      v84 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v84 > 4u && (unsigned __int8)tlgKeywordOn(v84, 512) )
      {
        v284[0] = (LPCRITICAL_SECTION)&v315;
        v314.Data1 = *((_DWORD *)v273 + 2);
        v282.Data1 = *((_DWORD *)v273 + 1);
        LOWORD(v270) = *((_WORD *)v273 + 1);
        *(_QWORD *)&v283.Data1 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v85,
          (unsigned int)byte_1801A3239,
          v85,
          v86,
          (__int64)&v283,
          (__int64)&v270,
          (__int64)&v282,
          (__int64)&v314,
          (__int64)v284);
      }
    }
  }
  else
  {
    v80 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v80 > 4u && (unsigned __int8)tlgKeywordOn(v80, 512) )
    {
      v314.Data1 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v81,
        (unsigned int)byte_1801A32C3,
        v81,
        v82,
        (__int64)&v314);
    }
  }
  v90 = Src;
  if ( Src )
  {
    wFormatTag = Src->wFormatTag;
    if ( (_WORD)wFormatTag == 0xFFFE )
    {
      v98 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v98 > 4u && (unsigned __int8)tlgKeywordOn(v98, 512) )
      {
        v314.Data1 = *(_DWORD *)&v90[1].nChannels;
        v284[0] = (LPCRITICAL_SECTION)((char *)&v90[1].nSamplesPerSec + 2);
        v282.Data1 = Src->nAvgBytesPerSec;
        LODWORD(v315) = Src->nSamplesPerSec;
        LOWORD(v270) = Src->nChannels;
        *(_QWORD *)&v283.Data1 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v99,
          (unsigned int)byte_1801A3033,
          v99,
          v100,
          (__int64)&v283,
          (__int64)&v270,
          (__int64)&v315,
          (__int64)&v282,
          (__int64)v284,
          (__int64)&v314);
      }
    }
    else
    {
      *(_QWORD *)((char *)&v315 + 4) = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      HIDWORD(v315) = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      LODWORD(v315) = wFormatTag;
      v95 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v95 > 4u && (unsigned __int8)tlgKeywordOn(v95, 512) )
      {
        v284[0] = (LPCRITICAL_SECTION)&v315;
        v314.Data1 = Src->nAvgBytesPerSec;
        v282.Data1 = Src->nSamplesPerSec;
        LOWORD(v270) = Src->nChannels;
        *(_QWORD *)&v283.Data1 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v96,
          (unsigned int)byte_1801A30C9,
          v96,
          v97,
          (__int64)&v283,
          (__int64)&v270,
          (__int64)&v282,
          (__int64)&v314,
          (__int64)v284);
      }
    }
  }
  else
  {
    v91 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v91 > 4u && (unsigned __int8)tlgKeywordOn(v91, 512) )
    {
      v314.Data1 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v92,
        (unsigned int)word_1801A3152,
        v92,
        v93,
        (__int64)&v314);
    }
  }
  v101 = (char *)pv;
  if ( pv )
  {
    v105 = *(unsigned __int16 *)pv;
    if ( (_WORD)v105 == 0xFFFE )
    {
      v109 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v109 > 4u && (unsigned __int8)tlgKeywordOn(v109, 512) )
      {
        v314.Data1 = *((_DWORD *)v101 + 5);
        v284[0] = (LPCRITICAL_SECTION)(v101 + 24);
        v282.Data1 = *((_DWORD *)pv + 2);
        LODWORD(v315) = *((_DWORD *)pv + 1);
        LOWORD(v270) = *((_WORD *)pv + 1);
        *(_QWORD *)&v283.Data1 = L"WAVEFORMATEXTENSIBLE";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v110,
          (unsigned int)&byte_1801A2EC7,
          v110,
          v111,
          (__int64)&v283,
          (__int64)&v270,
          (__int64)&v315,
          (__int64)&v282,
          (__int64)v284,
          (__int64)&v314);
      }
    }
    else
    {
      *(_QWORD *)((char *)&v315 + 4) = *(_QWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data2;
      HIDWORD(v315) = *(_DWORD *)&GUID_00000000_0000_0010_8000_00aa00389b71.Data4[4];
      LODWORD(v315) = v105;
      v106 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v106 > 4u && (unsigned __int8)tlgKeywordOn(v106, 512) )
      {
        v284[0] = (LPCRITICAL_SECTION)&v315;
        v314.Data1 = *((_DWORD *)pv + 2);
        v282.Data1 = *((_DWORD *)pv + 1);
        LOWORD(v270) = *((_WORD *)pv + 1);
        *(_QWORD *)&v283.Data1 = L"WAVEFORMATEX";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v107,
          (unsigned int)&dword_1801A2F5C,
          v107,
          v108,
          (__int64)&v283,
          (__int64)&v270,
          (__int64)&v282,
          (__int64)&v314,
          (__int64)v284);
      }
    }
  }
  else
  {
    v102 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
    if ( *v102 > 4u && (unsigned __int8)tlgKeywordOn(v102, 512) )
    {
      v314.Data1 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v103,
        (unsigned int)&dword_1801A2FE4,
        v103,
        v104,
        (__int64)&v314);
    }
  }
  v308 = 0;
  v307 = 0;
  *(struct _GUID *)v284 = v48;
  v283 = v49;
  v314 = v47;
  v112 = lpCriticalSection[0];
  v113 = DerivePeriodicityForStream(
           v277,
           (struct tWAVEFORMATEX *)lpCriticalSection[0],
           a3,
           v285,
           a14,
           v292,
           (struct tWAVEFORMATEX *)pv,
           &v314,
           &v283,
           (struct _GUID *)v284,
           a7 != 0,
           v271[0],
           v293,
           a18,
           v294,
           (__int64 *)&a18,
           &v307,
           &v308);
  v114 = v113;
  if ( v113 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x62F,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v113,
      v263);
    v115 = pv;
    pv = 0;
    if ( v115 )
      CoTaskMemFree(v115);
    v116 = v273;
    v273 = 0;
    if ( v116 )
      CoTaskMemFree(v116);
    v117 = Src;
    Src = 0;
    if ( v117 )
      CoTaskMemFree(v117);
    v118 = v275;
    v275 = 0;
    if ( v118 )
      CoTaskMemFree(v118);
LABEL_170:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v278);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v289);
    return (unsigned int)v114;
  }
  v271[0] = (__int64)a18 < v307;
  *(_QWORD *)&v283.Data1 = 0;
  v279 = 0;
  v281[0] = 0;
  p_pv = v281;
  v297 = 0;
  v298 = 1;
  v119 = v308;
  v120 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a3 + 80LL))(a3);
  *(struct _GUID *)v284 = v48;
  *(GUID *)lpCriticalSection = v47;
  v269 = (struct tWAVEFORMATEX **)v112;
  v121 = v291;
  v122 = v285;
  v114 = InitializeStreamAndModeDescriptors(
           (EffectPack **)v277,
           a14,
           v285,
           v291,
           v292,
           lpCriticalSection,
           (IID *)v284,
           &v317,
           a22,
           (__int64)v269,
           (__int64)v275,
           v293,
           (__int64)a18,
           (__int64)v286,
           (__int64)v295,
           (IID *)v301,
           (_QWORD *)v309,
           (GUID *)v303,
           (__int64)v280,
           v120,
           a9 != 0,
           a10 != 0,
           v119,
           a11,
           a26,
           a27,
           a28,
           &v297,
           (__int64)&v279);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v114 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63C,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v114,
      v264);
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(v281, 0);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
    v123 = pv;
    pv = 0;
    if ( v123 )
      CoTaskMemFree(v123);
    v124 = v273;
    v273 = 0;
    if ( v124 )
      CoTaskMemFree(v124);
    v125 = Src;
    Src = 0;
    if ( v125 )
      CoTaskMemFree(v125);
    v126 = v275;
    v275 = 0;
    if ( v126 )
      CoTaskMemFree(v126);
    goto LABEL_170;
  }
  v127 = (_QWORD *)v279;
  if ( v279 && (v128 = *(_QWORD *)(v279 + 8)) != 0 )
    v129 = *(_DWORD *)(v128 + 52);
  else
    v129 = 0;
  if ( v279 && (v130 = *(_QWORD *)(v279 + 8)) != 0 )
    v131 = *(_DWORD *)(v130 + 56);
  else
    v131 = 0;
  if ( v129 && v131 )
  {
    v132 = (__int64)a3 + 592;
    if ( !a3 )
      v132 = 600;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v132,
      0);
    v133 = v311;
    v317 = v311;
    DefaultAecReferenceEndpointId = GetDefaultAecReferenceEndpointId(&v317, (unsigned __int16 **)v132);
    v114 = DefaultAecReferenceEndpointId;
    if ( DefaultAecReferenceEndpointId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x643,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)DefaultAecReferenceEndpointId,
        v264);
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        v281,
        0);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
      v135 = pv;
      pv = 0;
      if ( v135 )
        CoTaskMemFree(v135);
      v136 = v273;
      v273 = 0;
      if ( v136 )
        CoTaskMemFree(v136);
      v137 = Src;
      Src = 0;
      if ( v137 )
        CoTaskMemFree(v137);
      v138 = v275;
      v275 = 0;
      if ( v138 )
        CoTaskMemFree(v138);
      goto LABEL_170;
    }
    v127 = (_QWORD *)v279;
  }
  else
  {
    v133 = v311;
  }
  v139 = 1;
  if ( v127 && *v127 )
    v139 = 3;
  v140 = (__int64)a3 + 360;
  if ( !a3 )
    v140 = 368;
  *(_DWORD *)v140 = v139;
  v276 = 0;
  EndpointStore = CEndpointStoreCache::GetEndpointStore(
                    (CEndpointStoreCache *)v139,
                    *(const unsigned __int16 **)(*(_QWORD *)v277 + 48LL),
                    &v276);
  v114 = EndpointStore;
  if ( EndpointStore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x656,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)EndpointStore,
      v264);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(v281, 0);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
    v142 = pv;
    pv = 0;
    if ( v142 )
      CoTaskMemFree(v142);
    v143 = v273;
    v273 = 0;
    if ( v143 )
      CoTaskMemFree(v143);
    v144 = Src;
    Src = 0;
    if ( v144 )
      CoTaskMemFree(v144);
    v145 = v275;
    v275 = 0;
    if ( v145 )
      CoTaskMemFree(v145);
    goto LABEL_170;
  }
  (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *, struct CEndpointStore *))(**(_QWORD **)(v302 + 48) + 80LL))(
    *(_QWORD *)(v302 + 48),
    lpCriticalSection,
    v276);
  v280 = 0;
  v146 = *(CEndpointCharacteristics **)v277;
  v280 = 0;
  CustomResourceManagerService = CEndpointCharacteristics::TryGetCustomResourceManagerService(
                                   v146,
                                   &GUID_475d74a7_6824_4b91_89be_33d893b255ed,
                                   &v280);
  v114 = CustomResourceManagerService;
  if ( CustomResourceManagerService < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x660,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)CustomResourceManagerService,
      v264);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(v281, 0);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
    v148 = pv;
    pv = 0;
    if ( v148 )
      CoTaskMemFree(v148);
    v149 = v273;
    v273 = 0;
    if ( v149 )
      CoTaskMemFree(v149);
    v150 = Src;
    Src = 0;
    if ( v150 )
      CoTaskMemFree(v150);
    v151 = v275;
    v275 = 0;
    if ( v151 )
      CoTaskMemFree(v151);
    goto LABEL_170;
  }
  v152 = 0;
  v286 = 0;
  if ( v280 )
  {
    v153 = (*(__int64 (__fastcall **)(void *, LPCRITICAL_SECTION *))(*(_QWORD *)v280 + 104LL))(v280, &v295);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(
      &v286,
      v153);
    if ( v295 )
      LeaveCriticalSection(v295);
    v152 = v286;
  }
  (*(void (__fastcall **)(_QWORD, LPCRITICAL_SECTION *))(**((_QWORD **)v276 + 13) + 128LL))(
    *((_QWORD *)v276 + 13),
    v284);
  v291 = v122 & 1;
  v317 = v133;
  v154 = DeriveStreamGroupParametersForStream(
           (CEndpointCharacteristics **)v277,
           v292,
           v121,
           *(_QWORD *)(v281[0] + 32),
           v264,
           &v317,
           a14 == AUDCLNT_SHAREMODE_EXCLUSIVE,
           v122 & 1,
           (struct tWAVEFORMATEX *)v273,
           v279,
           a3,
           (StreamGroupParams **)&v283);
  v155 = v154;
  if ( v154 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66F,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v154,
      v265);
    if ( v284[0] )
      LeaveCriticalSection(v284[0]);
    if ( v152 )
      LeaveCriticalSection(v152);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(v281, 0);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
    v156 = pv;
    pv = 0;
    if ( v156 )
      CoTaskMemFree(v156);
    v157 = v273;
    v273 = 0;
    if ( v157 )
      CoTaskMemFree(v157);
    v158 = Src;
    Src = 0;
    if ( v158 )
      CoTaskMemFree(v158);
    v159 = v275;
    v275 = 0;
    if ( v159 )
      CoTaskMemFree(v159);
LABEL_348:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v278);
    std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v289);
    return (unsigned int)v155;
  }
  v160 = BuildDeviceGraphForStream(
           (__int64)v277,
           (__int64)a3,
           v299,
           *((_QWORD *)v276 + 13),
           v287[0],
           v122,
           a14,
           v281[0],
           v279,
           *(_QWORD **)&v283.Data1,
           v121,
           v310,
           a24,
           (__int64)v294,
           (__int64)&v289,
           *(__int64 *)v300);
  v155 = v160;
  if ( v160 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x673,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v160,
      v266);
    if ( v284[0] )
      LeaveCriticalSection(v284[0]);
    if ( v152 )
      LeaveCriticalSection(v152);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(v281, 0);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
    v162 = pv;
    pv = 0;
    if ( v162 )
      CoTaskMemFree(v162);
    v163 = v273;
    v273 = 0;
    if ( v163 )
      CoTaskMemFree(v163);
    v164 = Src;
    Src = 0;
    if ( v164 )
      CoTaskMemFree(v164);
    v165 = v275;
    v275 = 0;
    if ( v165 )
      CoTaskMemFree(v165);
    goto LABEL_348;
  }
  *(_QWORD *)&v315 = 0;
  v166 = *(__int64 (__fastcall **)(struct IAudioStreamInfo *, __int128 *))(*(_QWORD *)a3 + 120LL);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v315, v161);
  v167 = v166(a3, &v315);
  v155 = v167;
  if ( v167 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x677,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v167,
      v266);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v315);
    if ( v284[0] )
      LeaveCriticalSection(v284[0]);
    if ( v152 )
      LeaveCriticalSection(v152);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(v281, 0);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
    v169 = pv;
    pv = 0;
    if ( v169 )
      CoTaskMemFree(v169);
    v170 = v273;
    v273 = 0;
    if ( v170 )
      CoTaskMemFree(v170);
    v171 = Src;
    Src = 0;
    if ( v171 )
      CoTaskMemFree(v171);
    v172 = v275;
    v275 = 0;
    if ( v172 )
      CoTaskMemFree(v172);
    goto LABEL_348;
  }
  *(_QWORD *)&v282.Data1 = 0;
  v173 = v315;
  v174 = *(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v315 + 224LL);
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v282, v168);
  v175 = v174(v173, &v282);
  v155 = v175;
  if ( v175 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x67B,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v175,
      v266);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v282);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v315);
    if ( v284[0] )
      LeaveCriticalSection(v284[0]);
    if ( v152 )
      LeaveCriticalSection(v152);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
    wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(v281, 0);
    std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
    v176 = pv;
    pv = 0;
    if ( v176 )
      CoTaskMemFree(v176);
    v177 = v273;
    v273 = 0;
    if ( v177 )
      CoTaskMemFree(v177);
    v178 = Src;
    Src = 0;
    if ( v178 )
      CoTaskMemFree(v178);
    v179 = v275;
    v275 = 0;
    if ( v179 )
      CoTaskMemFree(v179);
    goto LABEL_348;
  }
  LOBYTE(v270) = 0;
  p_Src = (struct tWAVEFORMATEX **)&v270;
  v305 = (struct tWAVEFORMATEX *)&v277;
  v306 = 1;
  v180 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a3 + 144LL))(a3);
  v182 = v271[0];
  if ( v180 || v271[0] && g_DisableSpatialOnLowLatency )
  {
    LOBYTE(v181) = 1;
    AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), v181);
    LOBYTE(v270) = 1;
    if ( *(_QWORD *)&v282.Data1 )
    {
      *(_QWORD *)&v314.Data1 = 0;
      v183 = **(_QWORD **)&v282.Data1;
      p_pv = (__int64 *)&v314;
      v297 = 0;
      v298 = 1;
      v155 = (*(__int64 (__fastcall **)(_QWORD, struct tWAVEFORMATEX **))(v183 + 120))(*(_QWORD *)&v282.Data1, &v297);
      wil::details::out_param_t<std::unique_ptr<SaDeviceParams>>::~out_param_t<std::unique_ptr<SaDeviceParams>>(&p_pv);
      if ( v155 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x697,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)(unsigned int)v155,
          v266);
        std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
        if ( (_BYTE)v270 )
          AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v282);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v315);
        if ( v284[0] )
          LeaveCriticalSection(v284[0]);
        if ( v152 )
          LeaveCriticalSection(v152);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
        if ( lpCriticalSection[0] )
          LeaveCriticalSection(lpCriticalSection[0]);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          v281,
          0);
        std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
        std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
        v185 = pv;
        pv = 0;
        if ( v185 )
          CoTaskMemFree(v185);
        v186 = v273;
        v273 = 0;
        if ( v186 )
          CoTaskMemFree(v186);
        v187 = Src;
        Src = 0;
        if ( v187 )
          CoTaskMemFree(v187);
        v188 = v275;
        v275 = 0;
        if ( v188 )
          CoTaskMemFree(v188);
        goto LABEL_348;
      }
      v189 = 0;
      if ( g_PerformStrictConnectorMatchOnMatchFormat
        && (*(unsigned __int8 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a3 + 144LL))(a3) )
      {
        v189 = (unsigned int)CompareWaveFormat(
                               *(const struct tWAVEFORMATEX **)(*(_QWORD *)&v314.Data1 + 16LL),
                               (const struct tWAVEFORMATEX *)pv) == 0;
      }
      v190 = 0;
      if ( v182 && g_DisableSpatialOnLowLatency && !v189 )
      {
        v287[0] = 0;
        v293 = 0;
        wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v293, v184);
        v191 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)&v282.Data1 + 24LL))(*(_QWORD *)&v282.Data1);
        v192 = Create_SpatialAudioDevicePropertyReader(v191, 0, &v293);
        v155 = v192;
        if ( v192 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6A9,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)(unsigned int)v192,
            v266);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v293);
          std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
          if ( (_BYTE)v270 )
            AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v282);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v315);
          if ( v284[0] )
            LeaveCriticalSection(v284[0]);
          if ( v152 )
            LeaveCriticalSection(v152);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
          if ( lpCriticalSection[0] )
            LeaveCriticalSection(lpCriticalSection[0]);
          wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
          wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            v281,
            0);
          std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
          std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
          v193 = pv;
          pv = 0;
          if ( v193 )
            CoTaskMemFree(v193);
          v194 = v273;
          v273 = 0;
          if ( v194 )
            CoTaskMemFree(v194);
          v195 = Src;
          Src = 0;
          if ( v195 )
            CoTaskMemFree(v195);
          v196 = v275;
          v275 = 0;
          if ( v196 )
            CoTaskMemFree(v196);
          goto LABEL_348;
        }
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v293 + 112LL))(v293, v287);
        v190 = v287[0] != 0;
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v293);
      }
      v197 = (const struct tWAVEFORMATEX *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v315 + 144LL))(v315);
      if ( !(unsigned int)CompareWaveFormat(*(const struct tWAVEFORMATEX **)(*(_QWORD *)&v314.Data1 + 24LL), v197)
        || v189
        || v190 )
      {
        v198 = (*(__int64 (__fastcall **)(struct IDeviceGraphManager *, _QWORD, _QWORD))(*(_QWORD *)g_DeviceGraphManager
                                                                                       + 40LL))(
                 g_DeviceGraphManager,
                 v315,
                 *(_QWORD *)&v282.Data1);
        v155 = v198;
        if ( v198 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6B9,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)(unsigned int)v198,
            v266);
          std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
          if ( (_BYTE)v270 )
            AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v282);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v315);
          if ( v284[0] )
            LeaveCriticalSection(v284[0]);
          if ( v152 )
            LeaveCriticalSection(v152);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
          if ( lpCriticalSection[0] )
            LeaveCriticalSection(lpCriticalSection[0]);
          wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
          wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            v281,
            0);
          std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
          std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
          v200 = pv;
          pv = 0;
          if ( v200 )
            CoTaskMemFree(v200);
          v201 = v273;
          v273 = 0;
          if ( v201 )
            CoTaskMemFree(v201);
          v202 = Src;
          Src = 0;
          if ( v202 )
            CoTaskMemFree(v202);
          v203 = v275;
          v275 = 0;
          if ( v203 )
            CoTaskMemFree(v203);
          goto LABEL_348;
        }
        wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v282, v199);
      }
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
    }
  }
  v204 = 0;
  v271[0] = 0;
  if ( *(_QWORD *)&v282.Data1 )
  {
    (*(void (__fastcall **)(__int64))(*((_QWORD *)a3 - 1) + 56LL))((__int64)a3 - 8);
    v231 = v285;
LABEL_431:
    if ( *(_QWORD *)&v282.Data1 )
    {
      v299 = 0;
      v238 = **(_QWORD **)&v282.Data1;
      p_pv = &v299;
      v297 = 0;
      v298 = 1;
      v239 = (*(__int64 (__fastcall **)(_QWORD, struct tWAVEFORMATEX **))(v238 + 120))(*(_QWORD *)&v282.Data1, &v297);
      wil::details::out_param_t<std::unique_ptr<SaDeviceParams>>::~out_param_t<std::unique_ptr<SaDeviceParams>>(&p_pv);
      if ( v239 >= 0 )
      {
        v240 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
        if ( *v240 > 4u )
        {
          if ( (unsigned __int8)tlgKeywordOn(v240, 0x400000000000LL) )
          {
            v295 = (LPCRITICAL_SECTION)(*(__int64 (__fastcall **)(struct IAudioStreamInfo *, struct _GUID *))(*(_QWORD *)a3 + 88LL))(
                                         a3,
                                         &v317);
            v302 = (*(__int64 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a3 + 80LL))(a3);
            v314.Data1 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v277 + 56LL))(*(_QWORD *)v277);
            v301 = v299 + 80;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
              (_DWORD)v240,
              (unsigned int)byte_1801A2E35,
              v241,
              v242,
              (__int64)&v303,
              (__int64)&v301,
              (__int64)&v314,
              (__int64)&v302,
              (__int64)&v295);
          }
        }
      }
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v299);
    }
    goto LABEL_438;
  }
  if ( !v294 )
  {
    if ( !g_DisableSpatialOnLowLatency
      || (v32 = !IsCompressedSpatialFormat((const struct tWAVEFORMATEX *)pv), v205 = 1, v32) )
    {
      v205 = 0;
    }
    v206 = v285;
    if ( (v285 & 0x20000) != 0 && g_UseSoftwareLoopbackOnMatchFormat || v205 )
    {
      v317 = 0;
      v318 = 0;
      if ( (*(int (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)v276 + 13) + 96LL))(
             *((_QWORD *)v276 + 13),
             &v317) >= 0 )
      {
        v207 = *(struct IProcessSubmixProxy ***)&v317.Data1;
        v208 = *(LPCRITICAL_SECTION *)v317.Data4;
        v295 = *(LPCRITICAL_SECTION *)v317.Data4;
        while ( v207 != (struct IProcessSubmixProxy **)v208 )
        {
          v294 = *v207;
          v209 = v294;
          Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v294);
          if ( (*(unsigned __int8 (__fastcall **)(struct IProcessSubmixProxy *))(*(_QWORD *)v209 + 168LL))(v209) )
          {
            v210 = (const struct tWAVEFORMATEX *)(*(__int64 (__fastcall **)(struct IProcessSubmixProxy *))(*(_QWORD *)v209 + 48LL))(v209);
            if ( !(unsigned int)ValidateUncompressedWaveFormatEx(v210) )
            {
              v211 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v315 + 128LL))(v315);
              if ( (*(__int64 (__fastcall **)(struct IProcessSubmixProxy *))(*(_QWORD *)v209 + 32LL))(v209) <= v211 )
              {
                wil::com_ptr_t<ResourceGroupInstance,wil::err_exception_policy>::operator=(&v282, &v294);
                v212 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
                if ( *v212 > 4u && (unsigned __int8)tlgKeywordOn(v212, 512) )
                {
                  v295 = *(LPCRITICAL_SECTION *)(*(_QWORD *)v277 + 48LL);
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                    v213,
                    (unsigned int)word_1801A2E8A,
                    v213,
                    v214,
                    (__int64)&v295);
                }
                Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v294);
                break;
              }
            }
          }
          Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v294);
          ++v207;
          v208 = v295;
        }
        v206 = v285;
        v204 = v271[0];
      }
      if ( *(_QWORD *)&v317.Data1 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IStreamGroupProxy>>>(
          *(_QWORD *)&v317.Data1,
          *(_QWORD *)v317.Data4);
        std::_Deallocate<16>(*(_QWORD *)&v317.Data1, (v318 - *(_QWORD *)&v317.Data1) & 0xFFFFFFFFFFFFFFF8uLL);
      }
    }
    if ( *(_QWORD *)&v282.Data1 )
    {
      v231 = v285;
LABEL_424:
      v233 = *(_QWORD *)g_DeviceGraphManager;
      v234 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v315 + 240LL))(v315);
      v266 = v300[0];
      v235 = (*(__int64 (__fastcall **)(struct IDeviceGraphManager *, _QWORD, _QWORD, bool))(v233 + 32))(
               g_DeviceGraphManager,
               v315,
               *(_QWORD *)&v282.Data1,
               v234 == 0);
      v229 = v235;
      if ( v235 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x741,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)(unsigned int)v235,
          v266);
        if ( (_BYTE)v270 )
          AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        goto LABEL_487;
      }
      if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
        McGenEventWrite_EtwEventWriteTransfer(
          v236,
          (unsigned int)AudioResourceManager_SaDevice_Connected,
          v237,
          1,
          (__int64)&v317);
      goto LABEL_431;
    }
    *(_QWORD *)&v314.Data1 = 0;
    p_pv = (__int64 *)&v314;
    v297 = 0;
    v298 = 1;
    v317 = v48;
    v311 = v47;
    v215 = v292;
    v155 = DeriveSaDeviceParametersForStream(
             v277,
             a14,
             v292,
             &v311,
             &v317,
             (struct tWAVEFORMATEX *)pv,
             Src,
             *(_QWORD *)(v281[0] + 32),
             (struct SaDeviceParams **)&v297);
    wil::details::out_param_t<std::unique_ptr<SaDeviceParams>>::~out_param_t<std::unique_ptr<SaDeviceParams>>(&p_pv);
    if ( v155 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F6,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v155,
        v267);
      std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
      if ( (_BYTE)v270 )
        AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v282);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v315);
      if ( v284[0] )
        LeaveCriticalSection(v284[0]);
      if ( v152 )
        LeaveCriticalSection(v152);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
      if ( lpCriticalSection[0] )
        LeaveCriticalSection(lpCriticalSection[0]);
      wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        v281,
        0);
      std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
      std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
      v216 = pv;
      pv = 0;
      if ( v216 )
        CoTaskMemFree(v216);
      v217 = v273;
      v273 = 0;
      if ( v217 )
        CoTaskMemFree(v217);
      v218 = Src;
      Src = 0;
      if ( v218 )
        CoTaskMemFree(v218);
      v219 = v275;
      v275 = 0;
      if ( v219 )
        CoTaskMemFree(v219);
      goto LABEL_348;
    }
    *(_WORD *)((char *)&v320 + 5) = 0;
    HIBYTE(v320) = 0;
    v323 = 0;
    BYTE4(v320) = 1;
    LODWORD(v320) = a24;
    v319 = 0;
    v322 = v47;
    v321 = v215;
    DoesExclusiveModeOverrideShared = CEndpointCharacteristics::DoesExclusiveModeOverrideShared(*(CEndpointCharacteristics **)v277);
    v271[0] = 0;
    p_pv = (__int64 *)v271;
    v297 = (struct tWAVEFORMATEX *)&v276;
    v298 = 1;
    if ( DoesExclusiveModeOverrideShared )
    {
      if ( a14 == AUDCLNT_SHAREMODE_EXCLUSIVE )
      {
        if ( _InterlockedCompareExchange(
               (volatile signed __int32 *)(*((_QWORD *)v276 + 12) + 276LL),
               GetCurrentThreadId(),
               0) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x714,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)0x887C005CLL,
            v267);
          if ( v271[0] )
            _InterlockedExchange((volatile __int32 *)(*((_QWORD *)v276 + 12) + 276LL), 0);
          std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
          if ( (_BYTE)v270 )
            AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v282);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v315);
          if ( v284[0] )
            LeaveCriticalSection(v284[0]);
          if ( v152 )
            LeaveCriticalSection(v152);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
          if ( lpCriticalSection[0] )
            LeaveCriticalSection(lpCriticalSection[0]);
          wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
          wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            v281,
            0);
          std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
          std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
          v222 = pv;
          pv = 0;
          if ( v222 )
            CoTaskMemFree(v222);
          v223 = v273;
          v273 = 0;
          if ( v223 )
            CoTaskMemFree(v223);
          v224 = Src;
          Src = 0;
          if ( v224 )
            CoTaskMemFree(v224);
          v225 = v275;
          v275 = 0;
          if ( v225 )
            CoTaskMemFree(v225);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v278);
          std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v289);
          return 2289827932LL;
        }
        v271[0] = 1;
        goto LABEL_379;
      }
      if ( _InterlockedCompareExchange((volatile signed __int32 *)(*((_QWORD *)v276 + 12) + 276LL), 0, 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x71A,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)0x887C005CLL,
          v267);
        if ( v271[0] )
          _InterlockedExchange((volatile __int32 *)(*((_QWORD *)v276 + 12) + 276LL), 0);
        std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
        if ( (_BYTE)v270 )
          AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v282);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v315);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v284);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v286);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(lpCriticalSection);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          v281,
          0);
        std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
        std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &pv,
          0);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v273,
          0);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &Src,
          0);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v275,
          0);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v278);
        std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v289);
        return 2289827932LL;
      }
    }
    else if ( a14 == AUDCLNT_SHAREMODE_EXCLUSIVE )
    {
LABEL_379:
      wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v282, v220);
      SaDeviceForExclusiveStream = CAudioResourceManager::GetSaDeviceForExclusiveStream(
                                     *((_QWORD *)v276 + 12),
                                     v277,
                                     v280,
                                     *(_QWORD *)&v314.Data1);
      v229 = SaDeviceForExclusiveStream;
      if ( SaDeviceForExclusiveStream < 0 )
      {
        if ( (unsigned int)(SaDeviceForExclusiveStream + 2005139335) <= 1 )
        {
          if ( v271[0] )
            _InterlockedExchange((volatile __int32 *)(*((_QWORD *)v276 + 12) + 276LL), 0);
          std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
          if ( (_BYTE)v270 )
            AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x723,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)(unsigned int)SaDeviceForExclusiveStream,
            v206);
          if ( v271[0] )
            _InterlockedExchange((volatile __int32 *)(*((_QWORD *)v276 + 12) + 276LL), 0);
          std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
          if ( (_BYTE)v270 )
            AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        }
LABEL_487:
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v282);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v315);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v284);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v286);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(lpCriticalSection);
        wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          v281,
          0);
        std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
        std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &pv,
          0);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v273,
          0);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &Src,
          0);
        wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
          &v275,
          0);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v278);
        std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v289);
        return v229;
      }
      goto LABEL_417;
    }
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v282, v220);
    if ( !v291 )
    {
      (*(void (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a3 + 144LL))(a3);
      (*(void (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a3 + 136LL))(a3);
      (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v299 + 96LL))(v299);
      v231 = v285;
      v268 = v285;
      SaDeviceForSharedStream = CAudioResourceManager::GetSaDeviceForSharedStream(
                                  v302 - 8,
                                  v277,
                                  v280,
                                  *(_QWORD *)&v314.Data1);
      v229 = SaDeviceForSharedStream;
      if ( SaDeviceForSharedStream < 0 )
      {
        if ( (unsigned int)(SaDeviceForSharedStream + 2005139335) <= 1 )
        {
          if ( v271[0] )
            _InterlockedExchange((volatile __int32 *)(*((_QWORD *)v276 + 12) + 276LL), 0);
          std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
          if ( (_BYTE)v270 )
            AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x732,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)(unsigned int)SaDeviceForSharedStream,
            v268);
          if ( v271[0] )
            _InterlockedExchange((volatile __int32 *)(*((_QWORD *)v276 + 12) + 276LL), 0);
          std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
          if ( (_BYTE)v270 )
            AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        }
        goto LABEL_487;
      }
      goto LABEL_418;
    }
    SaDeviceForOffloadedStream = CAudioResourceManager::GetSaDeviceForOffloadedStream(
                                   *((_QWORD *)v276 + 12),
                                   v277,
                                   v280,
                                   *(_QWORD *)&v314.Data1);
    v229 = SaDeviceForOffloadedStream;
    if ( SaDeviceForOffloadedStream < 0 )
    {
      if ( SaDeviceForOffloadedStream == -2005139370 || SaDeviceForOffloadedStream == -2005139334 )
      {
        if ( v271[0] )
          _InterlockedExchange((volatile __int32 *)(*((_QWORD *)v276 + 12) + 276LL), 0);
        std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
        if ( (_BYTE)v270 )
          AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x72A,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)(unsigned int)SaDeviceForOffloadedStream,
          v206);
        if ( v271[0] )
          _InterlockedExchange((volatile __int32 *)(*((_QWORD *)v276 + 12) + 276LL), 0);
        std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
        if ( (_BYTE)v270 )
          AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
      }
      goto LABEL_487;
    }
LABEL_417:
    v231 = v285;
LABEL_418:
    v204 = 1;
    if ( v271[0] )
    {
      v227 = *((_QWORD *)v276 + 12);
      _InterlockedExchange((volatile __int32 *)(v227 + 276), 0);
    }
    if ( (Microsoft_Windows_AudioEnableBits & 0x20) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v227,
        (unsigned int)AudioResourceManager_SaDevice_Created,
        v228,
        1,
        (__int64)&v317);
    std::unique_ptr<SaDeviceParams>::~unique_ptr<SaDeviceParams>(&v314);
    goto LABEL_424;
  }
  v231 = v285;
LABEL_438:
  v243 = (v231 & 0x400000) != 0;
  v244 = *(_QWORD *)v300;
  if ( v243 || *(_QWORD *)v300 && !*(_DWORD *)(*(_QWORD *)v300 + 960LL) && v291 )
  {
    *(_QWORD *)v287 = 0;
    v245 = v315;
    v246 = *(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v315 + 224LL);
    wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(v287, v181);
    v247 = v246(v245, v287);
    v229 = v247;
    if ( v247 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x767,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
        (const char *)(unsigned int)v247,
        v266);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v287);
      if ( (_BYTE)v270 )
        AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
      goto LABEL_487;
    }
    if ( *(_QWORD *)v287 )
    {
      *(_QWORD *)&v314.Data1 = 0;
      v248 = **(_QWORD **)v287;
      *(_QWORD *)&v314.Data1 = 0;
      v249 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(v248 + 56))(*(_QWORD *)v287, &v314);
      v229 = v249;
      if ( v249 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x76B,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)(unsigned int)v249,
          v266);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v314);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v287);
        if ( (_BYTE)v270 )
          AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        goto LABEL_487;
      }
      v250 = RpcImpersonateClient(0);
      if ( v250 )
      {
        v229 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x770,
                 (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
                 (const char *)v250,
                 v266);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v314);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v287);
        if ( (_BYTE)v270 )
          AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        goto LABEL_487;
      }
      v271[1] = 1;
      memset_0(v312, 0, 0x128u);
      memset_0(v313, 0, 0x128u);
      v251 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *, _BYTE *))(**(_QWORD **)&v314.Data1 + 32LL))(
               *(_QWORD *)&v314.Data1,
               (unsigned int)a22,
               v312,
               v313);
      v229 = v251;
      if ( v251 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x774,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)(unsigned int)v251,
          v266);
        RpcRevertToSelf();
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v314);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v287);
        if ( (_BYTE)v270 )
          AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        goto LABEL_487;
      }
      v252 = *(_QWORD *)(v244 + 48);
      *(_QWORD *)(v244 + 48) = 0;
      if ( v252 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v252 + 16LL))(v252);
      v253 = SystemAudioStream::move_from_blob(
               (struct CP_EVENT_METADATA_BLOB *)v312,
               (struct ICrossProcessEvent **)(v244 + 48),
               (struct CP_EVENT_METADATA_BLOB *)(v244 + 56));
      v229 = v253;
      if ( v253 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x776,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)(unsigned int)v253,
          v266);
        RpcRevertToSelf();
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v314);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v287);
        if ( (_BYTE)v270 )
          AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        goto LABEL_487;
      }
      v254 = *(_QWORD *)(v244 + 352);
      *(_QWORD *)(v244 + 352) = 0;
      if ( v254 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v254 + 16LL))(v254);
      v255 = SystemAudioStream::move_from_blob(
               (struct CP_EVENT_METADATA_BLOB *)v313,
               (struct ICrossProcessEvent **)(v244 + 352),
               (struct CP_EVENT_METADATA_BLOB *)(v244 + 360));
      v229 = v255;
      if ( v255 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x777,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)(unsigned int)v255,
          v266);
        RpcRevertToSelf();
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v314);
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v287);
        if ( (_BYTE)v270 )
          AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        goto LABEL_487;
      }
      RpcRevertToSelf();
      if ( v292 == eOffloadConnector )
      {
        v256 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)&v314.Data1 + 40LL))(
                 *(_QWORD *)&v314.Data1,
                 v244 + 1276,
                 v244 + 1280);
        v229 = v256;
        if ( v256 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x77F,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)(unsigned int)v256,
            v266);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v314);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v287);
          if ( (_BYTE)v270 )
            AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
          goto LABEL_487;
        }
        *(_DWORD *)(v244 + 1272) = 1;
        v257 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v310 + 32LL))(v310, *(_QWORD *)&v314.Data1);
        v229 = v257;
        if ( v257 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x781,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)(unsigned int)v257,
            v266);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v314);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v287);
          if ( (_BYTE)v270 )
            AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
          goto LABEL_487;
        }
      }
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v314);
    }
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v287);
  }
  if ( g_UseSoftwareLoopbackOnMatchFormat )
  {
    if ( (*(unsigned __int8 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a3 + 144LL))(a3) )
    {
      v258 = CAudioSessionManager::DisconnectAllStreamsOfType(*((_QWORD *)v276 + 12));
      v229 = v258;
      if ( v258 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x789,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
          (const char *)(unsigned int)v258,
          v266);
        if ( (_BYTE)v270 )
          AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
        goto LABEL_487;
      }
    }
  }
  if ( v204 && (*(unsigned __int8 (__fastcall **)(struct IAudioStreamInfo *))(*(_QWORD *)a3 + 144LL))(a3) )
  {
    LOBYTE(v259) = 1;
    AudioPolicyManagerExtension_OnPostMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), v259);
    v34 = 0;
  }
  if ( v34 && (_BYTE)v270 )
    AudioPolicyManagerExtension_OnPreMatchFormatStateChange(*(_QWORD *)(*(_QWORD *)v277 + 48LL), 0);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v282);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v315);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v284);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v286);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v280);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(lpCriticalSection);
  wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v276);
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(v281, 0);
  std::unique_ptr<MODE_PARAMS>::~unique_ptr<MODE_PARAMS>(&v279);
  std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v283);
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&pv, 0);
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v273, 0);
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&Src, 0);
  wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v275, 0);
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v278);
  std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(&v289);
  return 0;
}

```

## disassembly

```asm
0x180073490  mov     rax, rsp
0x180073493  push    rbx
0x180073494  push    rsi
0x180073495  push    rdi
0x180073496  push    r12
0x180073498  push    r13
0x18007349a  push    r14
0x18007349c  push    r15
0x18007349e  sub     rsp, 580h
0x1800734a5  movaps  xmmword ptr [rax-48h], xmm6
0x1800734a9  movaps  xmmword ptr [rax-58h], xmm7
0x1800734ad  movaps  xmmword ptr [rax-68h], xmm8
0x1800734b2  mov     rax, cs:__security_cookie
0x1800734b9  xor     rax, rsp
0x1800734bc  mov     [rsp+5B8h+var_70], rax
0x1800734c4  mov     [rsp+5B8h+var_428], r9d
0x1800734cc  mov     r12, r8
0x1800734cf  mov     [rsp+5B8h+var_3B8], rdx
0x1800734d7  mov     [rsp+5B8h+var_3A0], rcx
0x1800734df  mov     r13, [rsp+5B8h+arg_78]
0x1800734e7  mov     [rsp+5B8h+lpCriticalSection], r13
0x1800734ef  mov     rax, [rsp+5B8h+arg_58]
0x1800734f7  mov     [rsp+5B8h+var_498], rax
0x1800734ff  mov     rax, [rsp+5B8h+arg_70]
0x180073507  mov     [rsp+5B8h+var_360], rax
0x18007350f  mov     rax, [rsp+5B8h+arg_90]
0x180073517  mov     [rsp+5B8h+var_3A8], rax
0x18007351f  mov     rax, [rsp+5B8h+arg_98]
0x180073527  mov     [rsp+5B8h+var_368], rax
0x18007352f  mov     rax, [rsp+5B8h+arg_A0]
0x180073537  mov     [rsp+5B8h+var_398], rax
0x18007353f  mov     rax, [rsp+5B8h+arg_B0]
0x180073547  mov     [rsp+5B8h+var_3D8], rax
0x18007354f  mov     rax, [rsp+5B8h+arg_C0]
0x180073557  mov     [rsp+5B8h+var_480], rax
0x18007355f  mov     rax, [rsp+5B8h+arg_E0]
0x180073567  mov     [rsp+5B8h+var_3E0], rax
0x18007356f  mov     rax, [rsp+5B8h+arg_E8]
0x180073577  mov     qword ptr [rsp+5B8h+var_3B0], rax
0x18007357f  mov     rax, [r8]
0x180073582  mov     rcx, r8
0x180073585  mov     rax, [rax+0D0h]
0x18007358c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073591  movzx   esi, al
0x180073594  mov     rax, [rsp+5B8h+var_498]
0x18007359c  mov     rcx, [rax]
0x18007359f  mov     rax, [rcx]
0x1800735a2  mov     rax, [rax+38h]
0x1800735a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800735ab  xor     r14d, r14d
0x1800735ae  test    eax, eax
0x1800735b0  mov     eax, [rsp+5B8h+arg_60]
0x1800735b7  mov     [rsp+5B8h+var_438], eax
0x1800735be  lea     r15d, [r14+1]
0x1800735c2  jnz     short loc_1800735E8
0x1800735c4  bt      eax, 11h
0x1800735c8  jnb     short loc_1800735DE
0x1800735ca  mov     eax, esi
0x1800735cc  neg     eax
0x1800735ce  sbb     edi, edi
0x1800735d0  neg     edi
0x1800735d2  add     edi, 2
0x1800735d5  mov     [rsp+5B8h+var_3F0], edi
0x1800735dc  jmp     short loc_1800735F0
0x1800735de  mov     [rsp+5B8h+var_3F0], r14d
0x1800735e6  jmp     short loc_1800735F0
0x1800735e8  mov     [rsp+5B8h+var_3F0], r15d
0x1800735f0  xorps   xmm0, xmm0
0x1800735f3  movdqu  [rsp+5B8h+var_408], xmm0
0x1800735fc  mov     [rsp+5B8h+var_3F8], r14
0x180073604  mov     [rsp+5B8h+var_490], r14
0x18007360c  lea     rcx, [rsp+5B8h+var_490]
0x180073614  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x180073619  lea     r8, [rsp+5B8h+var_490]; struct IUnknown **
0x180073621  mov     rdx, [rsp+5B8h+var_498]; struct EndpointCharacteristicsDescriptor *
0x180073629  mov     rcx, cs:?s_DspResourceTracker@@3V?$com_ptr_t@VCAudioPumpDspResourceTracker@@Uerr_returncode_policy@wil@@@wil@@A; this
0x180073630  call    ?AcquireAudioPumpDspTokenForEndpoint@CAudioPumpDspResourceTracker@@QEAAJPEAUEndpointCharacteristicsDescriptor@@PEAPEAUIUnknown@@@Z; CAudioPumpDspResourceTracker::AcquireAudioPumpDspTokenForEndpoint(EndpointCharacteristicsDescriptor *,IUnknown * *)
0x180073635  mov     ebx, eax
0x180073637  test    eax, eax
0x180073639  jns     short loc_18007367A
0x18007363b  mov     rcx, [rsp+5B8h]; this
0x180073643  mov     r9d, eax; char *
0x180073646  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18007364d  mov     edx, 5F5h; void *
0x180073652  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073657  nop
0x180073658  lea     rcx, [rsp+5B8h+var_490]
0x180073660  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180073665  nop
0x180073666  lea     rcx, [rsp+5B8h+var_408]
0x18007366e  call    ??1?$vector@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(void)
0x180073673  mov     eax, ebx
0x180073675  jmp     loc_1800784D1
0x18007367a  mov     rax, qword ptr [rsp+5B8h+var_408+8]
0x180073682  cmp     rax, [rsp+5B8h+var_3F8]
0x18007368a  jz      short loc_1800736A7
0x18007368c  mov     rdx, [rsp+5B8h+var_490]
0x180073694  mov     rcx, rax
0x180073697  call    ??0?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAA@PEAVCEndpointCharacteristics@@@Z; wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>(CEndpointCharacteristics *)
0x18007369c  add     qword ptr [rsp+5B8h+var_408+8], 8
0x1800736a5  jmp     short loc_1800736BF
0x1800736a7  lea     r8, [rsp+5B8h+var_490]
0x1800736af  mov     rdx, rax
0x1800736b2  lea     rcx, [rsp+5B8h+var_408]
0x1800736ba  call    ??$_Emplace_reallocate@AEBV?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAV23@AEBV23@@Z; std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<IUnknown,wil::err_returncode_policy> const &>(wil::com_ptr_t<IUnknown,wil::err_returncode_policy> * const,wil::com_ptr_t<IUnknown,wil::err_returncode_policy> const &)
0x1800736bf  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800736c6  movdqu  xmmword ptr [rsp+5B8h+var_458.Data1], xmm0
0x1800736cf  movdqu  xmmword ptr [rsp+5B8h+var_E8.Data1], xmm0
0x1800736d8  movdqu  [rsp+5B8h+var_468], xmm0
0x1800736e1  movdqu  xmmword ptr [rsp+5B8h+var_358.Data1], xmm0
0x1800736ea  movdqu  xmmword ptr [rsp+5B8h+var_B8.Data1], xmm0
0x1800736f3  lea     rdx, [rsp+5B8h+var_408]
0x1800736fb  lea     rcx, [rsp+5B8h+var_D8]
0x180073703  call    ?TryGetAudioPumpDspResourceTokenFromTokenList@@YA?AUAudioPumpDspResourceTokenPair@@AEBV?$vector@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@@Z; TryGetAudioPumpDspResourceTokenFromTokenList(std::vector<wil::com_ptr_t<IUnknown,wil::err_returncode_policy>> const &)
0x180073708  mov     rdi, [rax+8]
0x18007370c  mov     [rax+8], r14
0x180073710  mov     [rsp+5B8h+var_448], rdi
0x180073718  lea     rcx, [rsp+5B8h+var_D8]; this
0x180073720  call    ??1AudioPumpDspResourceTokenPair@@QEAA@XZ; AudioPumpDspResourceTokenPair::~AudioPumpDspResourceTokenPair(void)
0x180073725  mov     [rsp+5B8h+Src], rdi; struct IUnknown *
0x18007372a  mov     r8, [rsp+5B8h+var_3E0]
0x180073732  mov     qword ptr [rsp+5B8h+var_590], r8; struct IProcessSubmixProxy *
0x180073737  mov     qword ptr [rsp+5B8h+var_598], r13; struct tWAVEFORMATEX *
0x18007373c  mov     r9d, esi; int
0x18007373f  mov     r8d, [rsp+5B8h+arg_68]; enum _AUDCLNT_SHAREMODE
0x180073747  mov     ebx, [rsp+5B8h+arg_60]
0x18007374e  mov     edx, ebx; unsigned int
0x180073750  mov     rcx, [rsp+5B8h+var_498]; struct EndpointCharacteristicsDescriptor *
0x180073758  call    ?GetConnectorTypeForStream@@YA?AW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUEndpointCharacteristicsDescriptor@@KW4_AUDCLNT_SHAREMODE@@HPEBUtWAVEFORMATEX@@PEAUIProcessSubmixProxy@@PEAUIUnknown@@@Z; GetConnectorTypeForStream(EndpointCharacteristicsDescriptor *,ulong,_AUDCLNT_SHAREMODE,int,tWAVEFORMATEX const *,IProcessSubmixProxy *,IUnknown *)
0x18007375d  mov     edx, eax
0x18007375f  mov     [rsp+5B8h+var_3EC], eax
0x180073766  lea     rcx, [r12+270h]
0x18007376e  mov     eax, 278h
0x180073773  test    r12, r12
0x180073776  cmovz   rcx, rax
0x18007377a  mov     [rcx], edx
0x18007377c  mov     [rsp+5B8h+var_430], r14
0x180073784  test    rdi, rdi
0x180073787  jnz     short loc_18007379B
0x180073789  mov     r13, [rsp+5B8h+arg_80]
0x180073791  mov     [rsp+5B8h+var_3E8], r13
0x180073799  jmp     short loc_1800737EA
0x18007379b  test    edx, edx
0x18007379d  jnz     short loc_1800737DA
0x18007379f  test    r15b, bl
0x1800737a2  jz      short loc_1800737DA
0x1800737a4  and     ebx, 0FFFFFFFEh
0x1800737a7  or      ebx, 88000002h
0x1800737ad  mov     [rsp+5B8h+var_438], ebx
0x1800737b4  mov     rax, [rsp+5B8h+arg_88]
0x1800737bc  mov     [rsp+5B8h+var_430], rax
0x1800737c4  mov     [rsp+5B8h+arg_88], r14
0x1800737cc  mov     rax, [rsp+5B8h+arg_80]
0x1800737d4  lea     r13, [rax+rax]
0x1800737d8  jmp     short loc_180073791
0x1800737da  mov     rax, [rsp+5B8h+arg_80]
0x1800737e2  mov     [rsp+5B8h+var_3E8], rax
0x1800737ea  lea     rax, [rsp+5B8h+var_B8]
0x1800737f2  mov     [rsp+5B8h+var_540], rax
0x1800737f7  lea     rax, [rsp+5B8h+var_358]
0x1800737ff  mov     [rsp+5B8h+var_548], rax
0x180073804  lea     rax, [rsp+5B8h+var_468]
0x18007380c  mov     [rsp+5B8h+var_550], rax
0x180073811  lea     rax, [rsp+5B8h+var_E8]
0x180073819  mov     [rsp+5B8h+var_558], rax
0x18007381e  lea     rax, [rsp+5B8h+var_458]
0x180073826  mov     [rsp+5B8h+var_560], rax
0x18007382b  mov     rsi, [rsp+5B8h+lpCriticalSection]
0x180073833  mov     [rsp+5B8h+var_568], rsi
0x180073838  mov     dword ptr [rsp+5B8h+var_570], r15d
0x18007383d  mov     dword ptr [rsp+5B8h+var_578], r14d
0x180073842  mov     rax, [rsp+5B8h+var_3E0]
0x18007384a  mov     [rsp+5B8h+var_580], rax
0x18007384f  mov     dword ptr [rsp+5B8h+Src], edx
0x180073853  mov     eax, [rsp+5B8h+arg_68]
0x18007385a  mov     [rsp+5B8h+var_590], eax
0x18007385e  mov     eax, [rsp+5B8h+var_3F0]
0x180073865  mov     [rsp+5B8h+var_598], eax; int
0x180073869  mov     r9, [rsp+5B8h+var_498]
0x180073871  mov     r8d, [rsp+5B8h+arg_28]
0x180073879  mov     edx, [rsp+5B8h+arg_20]
0x180073880  mov     r13d, [rsp+5B8h+var_428]
0x180073888  mov     ecx, r13d
0x18007388b  call    ?DeriveAudioProcessingModeConfiguration@@YAJKHHPEAUEndpointCharacteristicsDescriptor@@W4SYSTEM_AUDIO_STREAM_TYPE@@W4_AUDCLNT_SHAREMODE@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAUIProcessSubmixProxy@@HHPEBUtWAVEFORMATEX@@PEAU_GUID@@6666@Z; DeriveAudioProcessingModeConfiguration(ulong,int,int,EndpointCharacteristicsDescriptor *,SYSTEM_AUDIO_STREAM_TYPE,_AUDCLNT_SHAREMODE,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,IProcessSubmixProxy *,int,int,tWAVEFORMATEX const *,_GUID *,_GUID *,_GUID *,_GUID *,_GUID *)
0x180073890  mov     ebx, eax
0x180073892  test    eax, eax
0x180073894  jns     short loc_1800738E3
0x180073896  mov     rcx, [rsp+5B8h]; this
0x18007389e  mov     r9d, eax; char *
0x1800738a1  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800738a8  mov     edx, 616h; void *
0x1800738ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800738b2  nop
0x1800738b3  lea     rcx, [rsp+5B8h+var_448]
0x1800738bb  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800738c0  nop
0x1800738c1  lea     rcx, [rsp+5B8h+var_490]
0x1800738c9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800738ce  nop
0x1800738cf  lea     rcx, [rsp+5B8h+var_408]
0x1800738d7  call    ??1?$vector@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioStream@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>::~vector<wil::com_ptr_t<CAudioStream,wil::err_returncode_policy>>(void)
0x1800738dc  mov     eax, ebx
0x1800738de  jmp     loc_1800784D1
0x1800738e3  test    rdi, rdi
0x1800738e6  jz      short loc_1800738F1
0x1800738e8  movaps  xmm7, xmmword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x1800738ef  jmp     short loc_1800738F9
0x1800738f1  movaps  xmm7, xmmword ptr [rsp+5B8h+var_458.Data1]
0x1800738f9  lea     rcx, [rsp+5B8h+var_448]
0x180073901  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180073906  mov     [rsp+5B8h+var_4A8], r14
0x18007390e  mov     [rsp+5B8h+var_4B0], r14
0x180073916  mov     [rsp+5B8h+var_4B8], r14
0x18007391e  mov     [rsp+5B8h+pv], r14
0x180073926  lea     rax, [rsp+5B8h+pv]
0x18007392e  mov     [rsp+5B8h+var_3D0], rax
0x180073936  mov     [rsp+5B8h+var_3C8], r14
0x18007393e  mov     [rsp+5B8h+var_3C0], r15b
0x180073946  lea     rax, [rsp+5B8h+var_4B0]
0x18007394e  mov     [rsp+5B8h+var_390], rax
0x180073956  mov     [rsp+5B8h+var_388], r14
0x18007395e  mov     [rsp+5B8h+var_380], r15b
0x180073966  lea     rax, [rsp+5B8h+var_4B8]
0x18007396e  mov     [rsp+5B8h+var_98], rax
0x180073976  mov     [rsp+5B8h+var_90], r14
0x18007397e  mov     byte ptr [rsp+5B8h+var_88], r15b
0x180073986  lea     rax, [rsp+5B8h+var_4A8]
0x18007398e  mov     [rsp+5B8h+var_D8], rax
0x180073996  mov     [rsp+5B8h+var_D0], r14
0x18007399e  mov     [rsp+5B8h+var_C8], r15b
0x1800739a6  movaps  xmm8, xmmword ptr [rsp+5B8h+var_E8.Data1]
0x1800739af  movaps  xmm6, [rsp+5B8h+var_468]
0x1800739b7  cmp     [rsp+5B8h+arg_38], r14d
0x1800739bf  setnz   al
0x1800739c2  mov     [rsp+5B8h+var_4C4], al
0x1800739c9  movdqu  xmmword ptr [rsp+5B8h+var_448], xmm7
0x1800739d2  movdqu  xmmword ptr [rsp+5B8h+var_458.Data1], xmm8
0x1800739dc  movdqu  xmmword ptr [rsp+5B8h+var_E8.Data1], xmm6
0x1800739e5  lea     rcx, [rsp+5B8h+var_3C8]
0x1800739ed  mov     [rsp+5B8h+var_558], rcx; struct tWAVEFORMATEX **
0x1800739f2  lea     rcx, [rsp+5B8h+var_388]
0x1800739fa  mov     [rsp+5B8h+var_560], rcx; struct tWAVEFORMATEX **
0x1800739ff  lea     rcx, [rsp+5B8h+var_90]
0x180073a07  mov     [rsp+5B8h+var_568], rcx; struct tWAVEFORMATEX **
0x180073a0c  lea     rcx, [rsp+5B8h+var_D0]
0x180073a14  mov     [rsp+5B8h+var_570], rcx; struct tWAVEFORMATEX **
0x180073a19  mov     [rsp+5B8h+var_578], rsi; struct tWAVEFORMATEX *
0x180073a1e  lea     rcx, [rsp+5B8h+var_448]
0x180073a26  mov     [rsp+5B8h+var_580], rcx; struct _GUID *
0x180073a2b  lea     rcx, [rsp+5B8h+var_458]
0x180073a33  mov     [rsp+5B8h+Src], rcx; struct _GUID *
0x180073a38  lea     rcx, [rsp+5B8h+var_E8]
0x180073a40  mov     qword ptr [rsp+5B8h+var_590], rcx; struct _GUID *
0x180073a45  mov     [rsp+5B8h+var_598], r13d; int
0x180073a4a  mov     r9d, [rsp+5B8h+arg_68]; enum _AUDCLNT_SHAREMODE
0x180073a52  mov     r8d, [rsp+5B8h+var_3EC]; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180073a5a  mov     dl, al; bool
0x180073a5c  mov     rcx, [rsp+5B8h+var_498]; struct EndpointCharacteristicsDescriptor *
0x180073a64  call    ?DeriveDeviceGraphFormatsForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@_NW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4_AUDCLNT_SHAREMODE@@KU_GUID@@44PEAUtWAVEFORMATEX@@PEAPEAU5@666@Z; DeriveDeviceGraphFormatsForStream(EndpointCharacteristicsDescriptor *,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_AUDCLNT_SHAREMODE,ulong,_GUID,_GUID,_GUID,tWAVEFORMATEX *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *,tWAVEFORMATEX * *)
0x180073a69  mov     ebx, eax
0x180073a6b  lea     rcx, [rsp+5B8h+var_D8]
0x180073a73  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180073a78  nop
0x180073a79  lea     rcx, [rsp+5B8h+var_98]
0x180073a81  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180073a86  nop
0x180073a87  lea     rcx, [rsp+5B8h+var_390]
0x180073a8f  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180073a94  nop
0x180073a95  lea     rcx, [rsp+5B8h+var_3D0]
0x180073a9d  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180073aa2  test    ebx, ebx
0x180073aa4  jns     loc_180073BF8
0x180073aaa  mov     edi, 887C007Bh
0x180073aaf  cmp     ebx, edi
0x180073ab1  jnz     loc_180073B49
0x180073ab7  mov     rcx, [rsp+5B8h+pv]; pv
0x180073abf  mov     [rsp+5B8h+pv], r14
0x180073ac7  test    rcx, rcx
0x180073aca  jz      short loc_180073AD3
0x180073acc  call    cs:__imp_CoTaskMemFree
0x180073ad2  nop
0x180073ad3  mov     rcx, [rsp+5B8h+var_4B8]; pv
0x180073adb  mov     [rsp+5B8h+var_4B8], r14
0x180073ae3  test    rcx, rcx
0x180073ae6  jz      short loc_180073AEF
0x180073ae8  call    cs:__imp_CoTaskMemFree
0x180073aee  nop
0x180073aef  mov     rcx, [rsp+5B8h+var_4B0]; pv
0x180073af7  mov     [rsp+5B8h+var_4B0], r14
0x180073aff  test    rcx, rcx
0x180073b02  jz      short loc_180073B0B
0x180073b04  call    cs:__imp_CoTaskMemFree
0x180073b0a  nop
0x180073b0b  mov     rcx, [rsp+5B8h+var_4A8]; pv
0x180073b13  mov     [rsp+5B8h+var_4A8], r14
0x180073b1b  test    rcx, rcx
0x180073b1e  jz      short loc_180073B27
0x180073b20  call    cs:__imp_CoTaskMemFree
0x180073b26  nop
  ... truncated ...
```
