# VsecCacheManager::SetClaimsForUser(VsiteCollectionRecord *,VdbServer *,VurlTemplate<VurlSettings> const &,Vstring const &,_TOKEN_GROUPS *,OWSVARIANT &,OWSVARIANT &,OWSVARIANT &,OWSVARIANT &,PVclaimVvector &,ulong *,long * *,ulong *,long * *,ulong *,long * *,char *,char *,char *,VAuthenticationType,Vint32Vvector &)

- ea: `0x180177110`
- end: `0x180178454`
- name: `?SetClaimsForUser@VsecCacheManager@@QEAA?AVVHRESULT@@PEAVVsiteCollectionRecord@@PEAVVdbServer@@AEBV?$VurlTemplate@VVurlSettings@@@@AEBVVstring@@PEAU_TOKEN_GROUPS@@AEAUOWSVARIANT@@555AEAVPVclaimVvector@@PEAKPEAPEAJ7878PEAD99W4VAuthenticationType@@AEAVVint32Vvector@@@Z`
- size: `4932`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18016e030`

## callees

- `0x180005750`
- `0x180017be0`
- `0x18004a6c0`
- `0x18008ea10`
- `0x18008ea50`
- `0x18013f5c0`
- `0x180142d70`
- `0x180177110`
- `0x180178460`
- `0x18017b640`
- `0x18017b770`
- `0x18017bb30`
- `0x1801c1770`
- `0x1801c2d7d`
- `0x1801c2da0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180177d0e`
- `KERNEL32!QueryPerformanceCounter` at `0x180177dca`
- `KERNEL32!QueryPerformanceCounter` at `0x180177e36`
- `KERNEL32!QueryPerformanceCounter` at `0x180177eb5`
- `KERNEL32!QueryPerformanceCounter` at `0x180177d0e`
- `KERNEL32!QueryPerformanceCounter` at `0x180177dca`
- `KERNEL32!QueryPerformanceCounter` at `0x180177e36`
- `KERNEL32!QueryPerformanceCounter` at `0x180177eb5`
- `KERNEL32!QueryPerformanceFrequency` at `0x180177cdd`
- `KERNEL32!QueryPerformanceFrequency` at `0x180177cdd`
- `KERNEL32!GetTickCount64` at `0x180177d29`
- `KERNEL32!GetTickCount64` at `0x180177de4`
- `KERNEL32!GetTickCount64` at `0x180177e50`
- `KERNEL32!GetTickCount64` at `0x180177ecc`
- `KERNEL32!GetTickCount64` at `0x180177d29`
- `KERNEL32!GetTickCount64` at `0x180177de4`
- `KERNEL32!GetTickCount64` at `0x180177e50`
- `KERNEL32!GetTickCount64` at `0x180177ecc`
- `ADVAPI32!GetLengthSid` at `0x18017737a`
- `ADVAPI32!GetLengthSid` at `0x18017737a`
- `onetutil!??1Vint32Vvector@@QEAA@XZ` at `0x18017785a`
- `onetutil!??1Vint32Vvector@@QEAA@XZ` at `0x1801783e3`
- `onetutil!??1Vint32Vvector@@QEAA@XZ` at `0x1801783f1`
- `onetutil!??1Vint32Vvector@@QEAA@XZ` at `0x18017785a`
- `onetutil!??1Vint32Vvector@@QEAA@XZ` at `0x1801783e3`
- `onetutil!??1Vint32Vvector@@QEAA@XZ` at `0x1801783f1`
- `onetutil!??0Vint32Vvector@@QEAA@AEBV0@@Z` at `0x1801775d0`
- `onetutil!??0Vint32Vvector@@QEAA@AEBV0@@Z` at `0x1801777e7`
- `onetutil!??0Vint32Vvector@@QEAA@AEBV0@@Z` at `0x180178219`
- `onetutil!??0Vint32Vvector@@QEAA@AEBV0@@Z` at `0x1801775d0`
- `onetutil!??0Vint32Vvector@@QEAA@AEBV0@@Z` at `0x1801777e7`
- `onetutil!??0Vint32Vvector@@QEAA@AEBV0@@Z` at `0x180178219`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x18017749e`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1801776fb`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x180177bcc`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x180178097`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x18017749e`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1801776fb`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x180177bcc`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x180178097`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x180177b3f`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x180177fa1`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x180177fbb`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1801783ac`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1801783c5`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x180177b3f`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x180177fa1`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x180177fbb`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1801783ac`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x1801783c5`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x180177605`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x180177817`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x180177da3`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x180178248`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1801782ed`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x180177605`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x180177817`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x180177da3`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x180178248`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x1801782ed`
- `onetutil!??0Vint32Vvector@@QEAA@XZ` at `0x18017727a`
- `onetutil!??0Vint32Vvector@@QEAA@XZ` at `0x180177288`
- `onetutil!??0Vint32Vvector@@QEAA@XZ` at `0x180177651`
- `onetutil!??0Vint32Vvector@@QEAA@XZ` at `0x18017727a`
- `onetutil!??0Vint32Vvector@@QEAA@XZ` at `0x180177288`
- `onetutil!??0Vint32Vvector@@QEAA@XZ` at `0x180177651`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18017750f`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18017751e`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x180177561`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18017773a`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x180177747`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18017777b`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x1801780ea`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x1801780f9`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18017812f`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18017750f`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18017751e`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x180177561`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18017773a`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x180177747`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18017777b`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x1801780ea`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x1801780f9`
- `onetutil!?insert@Vint32Vvector@@QEAAXAEBJ@Z` at `0x18017812f`
- `onetutil!??0Vtime@@QEAA@_K@Z` at `0x180177bae`
- `onetutil!??0Vtime@@QEAA@_K@Z` at `0x180177bae`
- `onetutil!?sort@Vint32Vvector@@QEAAXP6AHPEBJ0@Z@Z` at `0x1801783d5`
- `onetutil!?sort@Vint32Vvector@@QEAAXP6AHPEBJ0@Z@Z` at `0x1801783d5`
- `onetutil!??AVint32Vvector@@QEAAAEAJI@Z` at `0x180177551`
- `onetutil!??AVint32Vvector@@QEAAAEAJI@Z` at `0x18017776e`
- `onetutil!??AVint32Vvector@@QEAAAEAJI@Z` at `0x18017811f`
- `onetutil!??AVint32Vvector@@QEAAAEAJI@Z` at `0x180177551`
- `onetutil!??AVint32Vvector@@QEAAAEAJI@Z` at `0x18017776e`
- `onetutil!??AVint32Vvector@@QEAAAEAJI@Z` at `0x18017811f`
- `onetutil!?reallocate@VstackBuffer512@@AEAAXI@Z` at `0x180177458`
- `onetutil!?reallocate@VstackBuffer512@@AEAAXI@Z` at `0x180177458`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1801772e4`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1801772f5`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1801772e4`
- `onetutil!??0Vwstring@@QEAA@AEBVVstring@@@Z` at `0x1801772f5`
- `onetutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1801773c7`
- `onetutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1801776a8`
- `onetutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180178067`
- `onetutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1801773c7`
- `onetutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1801776a8`
- `onetutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180178067`
- `onetutil!?clear@Vint32Vvector@@QEAAXXZ` at `0x1801772a1`
- `onetutil!?clear@Vint32Vvector@@QEAAXXZ` at `0x1801772a1`
- `onetutil!?appendBSTR@VstackBuffer512@@QEAAIQEA_W@Z` at `0x18017803e`
- `onetutil!?appendBSTR@VstackBuffer512@@QEAAIQEA_W@Z` at `0x18017803e`
- `onetutil!?appendBinary@VstackBuffer512@@QEAAAEAV1@PEBEK@Z` at `0x18017739d`
- `onetutil!?appendBinary@VstackBuffer512@@QEAAAEAV1@PEBEK@Z` at `0x18017739d`
- `onetutil!?asUTCtimestamp3@Vtime@@QEBA?AVVstring@@XZ` at `0x180177bc2`
- `onetutil!?asUTCtimestamp3@Vtime@@QEBA?AVVstring@@XZ` at `0x180177bc2`
- `onetutil!?appendSid@VstackBuffer512@@QEAAAEAV1@QEAX@Z` at `0x18017742c`
- `onetutil!?appendSid@VstackBuffer512@@QEAAAEAV1@QEAX@Z` at `0x18017742c`
- `onetutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x1801779b4`
- `onetutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x1801779b4`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180177bf9`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180177bf9`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x180177330`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x18017733e`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x180177330`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x18017733e`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1801774df`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1801781be`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017840b`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1801774df`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1801781be`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017840b`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1801774ec`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1801781cb`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x180178418`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1801774ec`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x1801781cb`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x180178418`
- `onetutil!??0VHRESULT@@QEAA@J@Z` at `0x180177246`
- `onetutil!??0VHRESULT@@QEAA@J@Z` at `0x180177246`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180177613`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180177825`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180177c07`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180177c89`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180177db1`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180178256`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1801782fb`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180177613`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180177825`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180177c07`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180177c89`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180177db1`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180178256`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1801782fb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801774f4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801781d3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180178420`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801774f4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801781d3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180178420`
- `OLEAUT32!SafeArrayAccessData` at `0x180177fb0`
- `OLEAUT32!SafeArrayAccessData` at `0x180177fb0`
- `OLEAUT32!SafeArrayUnaccessData` at `0x1801781fa`
- `OLEAUT32!SafeArrayUnaccessData` at `0x1801781fa`
- `onetnative!ULSPerfmonEvent` at `0x1801778d2`
- `onetnative!ULSPerfmonEvent` at `0x180177ab0`
- `onetnative!ULSPerfmonEvent` at `0x180177c2f`
- `onetnative!ULSPerfmonEvent` at `0x180177c3a`
- `onetnative!ULSPerfmonEvent` at `0x180177e09`
- `onetnative!ULSPerfmonEvent` at `0x180177e14`
- `onetnative!ULSPerfmonEvent` at `0x180177e8b`
- `onetnative!ULSPerfmonEvent` at `0x180177e96`
- `onetnative!ULSPerfmonEvent` at `0x18017830c`
- `onetnative!ULSPerfmonEvent` at `0x18017832c`
- `onetnative!ULSPerfmonEvent` at `0x1801778d2`
- `onetnative!ULSPerfmonEvent` at `0x180177ab0`
- `onetnative!ULSPerfmonEvent` at `0x180177c2f`
- `onetnative!ULSPerfmonEvent` at `0x180177c3a`
- `onetnative!ULSPerfmonEvent` at `0x180177e09`
- `onetnative!ULSPerfmonEvent` at `0x180177e14`
- `onetnative!ULSPerfmonEvent` at `0x180177e8b`
- `onetnative!ULSPerfmonEvent` at `0x180177e96`
- `onetnative!ULSPerfmonEvent` at `0x18017830c`
- `onetnative!ULSPerfmonEvent` at `0x18017832c`
- `onetnative!ULSPerfmonIncrement` at `0x180177f00`
- `onetnative!ULSPerfmonIncrement` at `0x180177f00`
- `onetnative!ULSShouldTrace` at `0x1801773ee`
- `onetnative!ULSShouldTrace` at `0x1801776cd`
- `onetnative!ULSShouldTrace` at `0x180177b99`
- `onetnative!ULSShouldTrace` at `0x180178089`
- `onetnative!ULSShouldTrace` at `0x1801773ee`
- `onetnative!ULSShouldTrace` at `0x1801776cd`
- `onetnative!ULSShouldTrace` at `0x180177b99`
- `onetnative!ULSShouldTrace` at `0x180178089`
- `onetnative!ULSSendTraceTag` at `0x180177325`
- `onetnative!ULSSendTraceTag` at `0x1801774c5`
- `onetnative!ULSSendTraceTag` at `0x18017763d`
- `onetnative!ULSSendTraceTag` at `0x180177722`
- `onetnative!ULSSendTraceTag` at `0x18017784f`
- `onetnative!ULSSendTraceTag` at `0x1801778c7`
- `onetnative!ULSSendTraceTag` at `0x180177938`
- `onetnative!ULSSendTraceTag` at `0x18017796c`

## string_xrefs

- `0x1801772bd`: `\sts\wel\security.cpp`
- `0x18017730e`: `VsecCacheManager::SetClaimsForUser entry. User: '%s', Url: '%s'.`
- `0x1801774ae`: `VsecCacheManager::SetClaimsForUser: User has stable claim. User: '%S' Claim: '%S'.`
- `0x180177628`: `VsecCacheManager::SetClaimsForUser: SortAndRemoveDuplicates failed. HR: '0x%08x'.`
- `0x18017770b`: `VsecCacheManager::SetClaimsForUser: User has link claim. User: '%S' Claim: '%S'.`
- `0x18017783a`: `VsecCacheManager::SetClaimsForUser: SortAndRemoveDuplicates(vivLinkClaims) failed. HR: '0x%08x'.`
- `0x180178365`: `VsecCacheManager::SetClaimsForUser: Content database schema and sproc versions do not support dynamic claims. Skipping processing.`
- `0x1801778ae`: `VsecCacheManager::SetClaimsForUser: Dynamic augmentation is supported by the content DB so running the code.`
- `0x180177927`: `VsecCacheManager::SetClaimsForUser: Dynamic claim variant inputs have inconsistent types. Setting all to NULL and recalculating this user's dynamic claims. varDynamicClaims type: %d varDynamicClaimsLastUpdated type: %d varClaimMapVersionAtLastUpdate type: %d`
- `0x18017795b`: `VsecCacheManager::SetClaimsForUser: The 'allow dynamic claims refresh' variant has an inconsistent type. Expected OWSDBTYPE_BOOL. Setting to OWSDBTYPE_BOOL with a value of VTRUE. Received type: %d`
- `0x1801779f9`: `VsecCacheManager::SetClaimsForUser: Received cache: %d SPSite uses dynamic claims: %d Refresh allowed: %d Last refresh version: %d Current version: %d`
- `0x180177b20`: `VsecCacheManager::SetClaimsForUser: Unable to convert time from Vdbtime to Vtime. Returning E_FAIL.`
- `0x180177b71`: `VsecCacheManager::SetClaimsForUser: IsDynamicClaimCacheExpired says the cache has expired. Setting refresh cache to VTRUE. HR: '0x%08x'.`
- `0x180177bd7`: `VsecCacheManager::SetClaimsForUser: Dynamic claims cache is not expired. Using cached claims. Time last updated: '%S'.`
- `0x180177a3c`: `VsecCacheManager::SetClaimsForUser: Do refresh: '%d'.`
- `0x180177ad3`: `VsecCacheManager::SetClaimsForUser: Call to InitDynamicClaimsFromCache failed. Will attempt to refresh claims. HR: '0x%08x'.`
- `0x180177c12`: `VsecCacheManager::SetClaimsForUser: Call to InitDynamicClaimsFromCache failed. Caller disallowed claim refresh. HR: '0x%08x'.`
- `0x180177c40`: `VsecCacheManager::SetClaimsForUser: InitDynamicClaimsFromCache succeeded.`
- `0x180177ca4`: `VsecCacheManager::SetClaimsForUser: SPSite does not use dynamic claims and we will update the cached claims to reflect that. We will not try to refresh the user's dynamic claims again until something in the SPSite is ACLed to a dynamic claim.`
- `0x180177d32`: `VsecCacheManager::SetClaimsForUser: Calling dynamic claim providers to find out if the user has membership in the dynamic claims.`
- `0x180177f11`: `VsecCacheManager::SetClaimsForUser: Call to VmanagedCodeInterop::CheckDynamicClaimsForUser failed. HR: '0x%08x'.`
- `0x180177f82`: `VsecCacheManager::SetClaimsForUser: Dynamic claim bitmask is an unexpected length. Expected: '%d', Actual: '%d'.`
- `0x180177fc9`: `VsecCacheManager::SetClaimsForUser: SafeArrayAccessData failed for dynamic claims. HR: '0x%08x'.`
- `0x1801780b2`: `VsecCacheManager::SetClaimsForUser user has dynamic claim. User: '%S' Claim (hex): '%s'.`
- `0x180178264`: `VsecCacheManager::SetClaimsForUser: SortAndRemoveDuplicates from dynamic claims vector failed. HR: '0x%08x'.`
- `0x18017829e`: `Tried to refresh dynamic claims but the claim providers returned a null bitmask. Trying to use the cached claim vector.`
- `0x180178316`: `Dynamic claims refresh failed, and so did initialization from the cached value. HR: '0x%08x'.`
- `0x180178387`: `VsecCacheManager::SetClaimsForUser claim map record was null.`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
VHRESULT *__fastcall VsecCacheManager::SetClaimsForUser(
        VsecCacheManager *a1,
        VHRESULT *a2,
        __int64 a3,
        VdbServer *a4,
        const struct Vstring *a5,
        Vstring *a6,
        unsigned int *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        char *a11,
        pvAuditEntryVvector *a12,
        __int64 a13,
        _BYTE *a14,
        unsigned int *a15,
        const int **a16,
        __int64 a17,
        __int64 a18,
        _BYTE *a19,
        _BYTE *a20,
        _BYTE *a21,
        int a22,
        Vint32Vvector *a23)
{
  const struct VsiteCollectionRecord *v23; // rdi
  VHRESULT *v24; // r13
  Vint32Vvector *v25; // rsi
  Vwstring *v26; // rbx
  Vwstring *v27; // rcx
  unsigned int v28; // r14d
  char *v29; // rsi
  _BYTE *v30; // r13
  PSID *v31; // rbx
  DWORD LengthSid; // edi
  __int64 v33; // rsi
  DWORD v34; // eax
  PSID v35; // rbx
  __int64 v36; // rcx
  void *v37; // rbx
  const char *v38; // rax
  __int64 v39; // rcx
  void *v40; // rbx
  __int64 v41; // rcx
  unsigned int i; // ebx
  const int *v43; // rax
  Vint32Vvector *v44; // rax
  VsecCacheManager *v45; // r12
  __int64 v46; // rax
  unsigned int v47; // esi
  pvAuditEntryVvector *v48; // r15
  char *v49; // r14
  Vstring *v50; // r12
  __int64 (__fastcall ***v51)(_QWORD); // rcx
  __int64 v52; // rax
  __int64 v53; // rdi
  __int64 (__fastcall ***v54)(_QWORD); // rcx
  __int64 v55; // rbx
  const char *v56; // rax
  __int64 v57; // rcx
  unsigned int v58; // ebx
  const int *v59; // rax
  Vint32Vvector *v60; // rax
  __int64 v61; // rax
  VdbServer *v62; // rbx
  __int64 v63; // r14
  int v64; // ecx
  __int64 v65; // rbx
  __int64 v66; // r15
  char *v67; // r14
  bool v68; // r12
  bool v69; // r14
  char v70; // bl
  VsecCacheManager *v71; // r15
  Vstring *v72; // rax
  const char *v73; // rax
  char v74; // r15
  ULONGLONG TickCount64; // rbx
  ULONGLONG QuadPart; // r14
  __int64 v77; // rax
  unsigned __int64 v78; // rdx
  unsigned __int64 v79; // rbx
  __int64 v80; // rcx
  unsigned __int64 v81; // rbx
  int v82; // eax
  unsigned int v83; // r15d
  const wchar_t *v84; // r9
  __int64 v85; // rcx
  __int64 v86; // r14
  __int64 v87; // r8
  unsigned __int64 v88; // r12
  unsigned __int64 v89; // rcx
  unsigned int v90; // eax
  unsigned __int64 v91; // rbx
  pvAuditEntryVvector *v92; // r13
  _BYTE *v93; // r14
  void (__fastcall ***v94)(_QWORD, __int64); // rcx
  const char *v95; // rax
  __int64 v96; // rax
  __int64 v97; // rcx
  const int *v98; // rax
  void *v99; // r14
  Vint32Vvector *v100; // rax
  __int64 v101; // rax
  unsigned int *v102; // rbx
  const int **v103; // r14
  __int64 inited; // rax
  __int64 v105; // rcx
  void *v106; // rbx
  struct Vint32Vvector *v108; // [rsp+28h] [rbp-E0h]
  struct Vint32Vvector *v109; // [rsp+28h] [rbp-E0h]
  struct Vint32Vvector *v110; // [rsp+28h] [rbp-E0h]
  struct Vint32Vvector *v111; // [rsp+28h] [rbp-E0h]
  struct Vint32Vvector *v112; // [rsp+28h] [rbp-E0h]
  struct Vint32Vvector *v113; // [rsp+28h] [rbp-E0h]
  __int64 v114; // [rsp+30h] [rbp-D8h]
  __int64 v115; // [rsp+30h] [rbp-D8h]
  __int64 v116; // [rsp+38h] [rbp-D0h]
  char v117; // [rsp+58h] [rbp-B0h]
  __int64 v120; // [rsp+80h] [rbp-88h] BYREF
  int v121; // [rsp+88h] [rbp-80h] BYREF
  int v122; // [rsp+8Ch] [rbp-7Ch] BYREF
  int v123; // [rsp+90h] [rbp-78h] BYREF
  int v124; // [rsp+94h] [rbp-74h] BYREF
  Vstring *v125; // [rsp+98h] [rbp-70h]
  char *v126; // [rsp+A0h] [rbp-68h]
  pvAuditEntryVvector *v127; // [rsp+A8h] [rbp-60h]
  char *v128; // [rsp+B0h] [rbp-58h]
  unsigned int *v129; // [rsp+B8h] [rbp-50h]
  const int **v130; // [rsp+C0h] [rbp-48h]
  __int64 v131; // [rsp+C8h] [rbp-40h]
  _BYTE *v132; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD v133[2]; // [rsp+D8h] [rbp-30h] BYREF
  int v134; // [rsp+E8h] [rbp-20h]
  __int64 v135; // [rsp+F0h] [rbp-18h]
  __int64 v136; // [rsp+F8h] [rbp-10h]
  void *ppvData; // [rsp+100h] [rbp-8h] BYREF
  VHRESULT *v138; // [rsp+108h] [rbp+0h]
  _BYTE *v139; // [rsp+110h] [rbp+8h]
  _BYTE v140[32]; // [rsp+118h] [rbp+10h] BYREF
  __int64 v141; // [rsp+138h] [rbp+30h] BYREF
  __int64 v142; // [rsp+140h] [rbp+38h] BYREF
  unsigned __int64 v143; // [rsp+148h] [rbp+40h] BYREF
  _BYTE *v144; // [rsp+150h] [rbp+48h]
  LARGE_INTEGER v145; // [rsp+158h] [rbp+50h] BYREF
  _BYTE *v146; // [rsp+160h] [rbp+58h]
  _DWORD v147[4]; // [rsp+168h] [rbp+60h] BYREF
  char v148[8]; // [rsp+178h] [rbp+70h] BYREF
  __int64 v149; // [rsp+180h] [rbp+78h]
  VdbServer *v150; // [rsp+188h] [rbp+80h]
  char v151[8]; // [rsp+190h] [rbp+88h] BYREF
  LARGE_INTEGER Frequency; // [rsp+198h] [rbp+90h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+1A0h] [rbp+98h] BYREF
  const struct Vstring *v154; // [rsp+1A8h] [rbp+A0h]
  LARGE_INTEGER v155; // [rsp+1B0h] [rbp+A8h] BYREF
  LARGE_INTEGER v156; // [rsp+1B8h] [rbp+B0h] BYREF
  __int64 v157; // [rsp+1C0h] [rbp+B8h]
  __int64 v158; // [rsp+1C8h] [rbp+C0h]
  char v159[8]; // [rsp+1D0h] [rbp+C8h] BYREF
  _DWORD v160[4]; // [rsp+1D8h] [rbp+D0h] BYREF
  _BYTE v161[32]; // [rsp+1E8h] [rbp+E0h] BYREF
  _BYTE v162[32]; // [rsp+208h] [rbp+100h] BYREF
  __int64 v163; // [rsp+228h] [rbp+120h]
  VHRESULT *v164; // [rsp+230h] [rbp+128h]
  _BYTE v165[16]; // [rsp+238h] [rbp+130h] BYREF
  _BYTE v166[16]; // [rsp+248h] [rbp+140h] BYREF
  _BYTE v167[16]; // [rsp+258h] [rbp+150h] BYREF
  _BYTE v168[16]; // [rsp+268h] [rbp+160h] BYREF
  _BYTE v169[16]; // [rsp+278h] [rbp+170h] BYREF
  _BYTE v170[16]; // [rsp+288h] [rbp+180h] BYREF
  _BYTE v171[32]; // [rsp+298h] [rbp+190h] BYREF
  _BYTE v172[32]; // [rsp+2B8h] [rbp+1B0h] BYREF
  _BYTE v173[32]; // [rsp+2D8h] [rbp+1D0h] BYREF
  void *Block; // [rsp+2F8h] [rbp+1F0h] BYREF
  _BYTE v175[516]; // [rsp+300h] [rbp+1F8h] BYREF
  unsigned int v176; // [rsp+504h] [rbp+3FCh]
  unsigned int v177; // [rsp+508h] [rbp+400h]
  void *v178; // [rsp+518h] [rbp+410h] BYREF
  _BYTE v179[516]; // [rsp+520h] [rbp+418h] BYREF
  unsigned int v180; // [rsp+724h] [rbp+61Ch]
  int v181; // [rsp+728h] [rbp+620h]
  void *v182; // [rsp+738h] [rbp+630h] BYREF
  _BYTE v183[516]; // [rsp+740h] [rbp+638h] BYREF
  unsigned int v184; // [rsp+944h] [rbp+83Ch]
  int v185; // [rsp+948h] [rbp+840h]

  v163 = -2;
  v150 = a4;
  v23 = (const struct VsiteCollectionRecord *)a3;
  v24 = a2;
  v138 = a2;
  v164 = a2;
  v154 = a5;
  v125 = a6;
  v131 = a8;
  v136 = a9;
  v135 = a10;
  v128 = a11;
  v127 = a12;
  v158 = a13;
  v146 = a14;
  v129 = a15;
  v130 = a16;
  v157 = a17;
  v149 = a18;
  v132 = a19;
  v139 = a20;
  v144 = a21;
  v25 = a23;
  VHRESULT::VHRESULT(a2, 0);
  v134 = 1;
  v178 = v179;
  v180 = 0;
  v181 = 512;
  Vint32Vvector::Vint32Vvector((Vint32Vvector *)v162);
  Vint32Vvector::Vint32Vvector((Vint32Vvector *)v161);
  Vint32Vvector::clear(a23);
  *a21 = 0;
  if ( a7 )
  {
    LogDGCacheEvents("SetClaimsForUser", v23, qword_18020E990, "\\sts\\wel\\security.cpp", 7547);
    v26 = Vwstring::Vwstring((Vwstring *)v159, a5);
    v27 = Vwstring::Vwstring((Vwstring *)v148, v125);
    ULSSendTraceTag(
      5812553,
      117141572,
      100,
      L"VsecCacheManager::SetClaimsForUser entry. User: '%s', Url: '%s'.",
      *(_QWORD *)v27,
      *(_QWORD *)v26);
    Vwstring::~Vwstring(v148);
    Vwstring::~Vwstring(v159);
    if ( v23 )
    {
      v28 = 0;
      if ( *a7 )
      {
        v29 = (char *)v23 + 48;
        v126 = (char *)v23 + 48;
        v30 = v132;
        do
        {
          v31 = (PSID *)&a7[4 * v28];
          if ( a22 == 1 )
            LengthSid = GetLengthSid(v31[1]);
          else
            LengthSid = *((_DWORD *)v31 + 4);
          v180 = 0;
          VstackBuffer512::appendBinary((VstackBuffer512 *)&v178, (const unsigned __int8 *)v31[1], LengthSid);
          *((_BYTE *)v178 + v180) = 0;
          v141 = 0;
          if ( !(unsigned int)CLKRHashTable::FindKey(v29, v178, &v141) )
          {
            v33 = v141;
            if ( v141 )
            {
              if ( (unsigned __int8)ULSShouldTrace(117141572, 200) )
              {
                Block = v175;
                v176 = 0;
                v177 = 512;
                if ( a22 == 1 )
                {
                  VstackBuffer512::appendSid((VstackBuffer512 *)&Block, v31[1]);
                  v34 = v176;
                }
                else
                {
                  v35 = v31[1];
                  v36 = v176;
                  if ( v176 + LengthSid > v177 )
                  {
                    VstackBuffer512::reallocate((VstackBuffer512 *)&Block, LengthSid);
                    v36 = v176;
                  }
                  memcpy((char *)Block + v36, v35, LengthSid);
                  v34 = LengthSid + v176;
                  v176 += LengthSid;
                }
                *((_BYTE *)Block + v34) = 0;
                v37 = Block;
                v38 = Vstring::data(v125);
                ULSSendTraceTag(
                  7365505,
                  117141572,
                  200,
                  L"VsecCacheManager::SetClaimsForUser: User has stable claim. User: '%S' Claim: '%S'.",
                  v38,
                  v37);
                v40 = Block;
                if ( Block != v175 )
                {
                  if ( (unsigned int)COWSAllocator::QueryNewMode(v39) )
                    COWSAllocator::Free(v40);
                  else
                    free(v40);
                }
              }
              v121 = *(_DWORD *)(*(_QWORD *)(v33 + 48) + 16LL);
              Vint32Vvector::insert((Vint32Vvector *)v162, &v121);
              Vint32Vvector::insert(a23, &v121);
              if ( *(_BYTE *)(*(_QWORD *)(v33 + 48) + 36LL) )
                *v30 = 1;
              v41 = *(_QWORD *)(v33 + 48);
              if ( *(_QWORD *)(v41 + 24) )
              {
                for ( i = 0; i < *(_DWORD *)(*(_QWORD *)(v41 + 24) + 16LL); v41 = *(_QWORD *)(v33 + 48) )
                {
                  v43 = (const int *)Vint32Vvector::operator[](*(_QWORD *)(v41 + 24), i);
                  Vint32Vvector::insert((Vint32Vvector *)v162, v43);
                  ++i;
                }
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v33 + 24), 0xFFFFFFFF) == 1 && v33 != -16 )
                (**(void (__fastcall ***)(__int64, __int64))(v33 + 16))(v33 + 16, 1);
            }
            v29 = v126;
          }
          ++v28;
        }
        while ( v28 < *a7 );
        v24 = v138;
        v23 = (const struct VsiteCollectionRecord *)a3;
      }
      v126 = v171;
      v44 = Vint32Vvector::Vint32Vvector((Vint32Vvector *)v171, (const struct Vint32Vvector *)v162);
      v45 = a1;
      v46 = VsecCacheManager::SortAndRemoveDuplicates(a1, v170, v44, v146, v158);
      VHRESULT::operator=(v24, v46);
      VHRESULT::~VHRESULT((VHRESULT *)v170);
      if ( *(int *)v24 < 0 )
      {
        LODWORD(v108) = *(_DWORD *)v24;
        ULSSendTraceTag(
          5769168,
          117141511,
          10,
          L"VsecCacheManager::SetClaimsForUser: SortAndRemoveDuplicates failed. HR: '0x%08x'.",
          v108);
LABEL_33:
        v25 = a23;
        goto LABEL_182;
      }
      Vint32Vvector::Vint32Vvector((Vint32Vvector *)v140);
      v47 = 0;
      v48 = v127;
      if ( *((_DWORD *)v127 + 4) )
      {
        v49 = (char *)v23 + 48;
        v50 = v125;
        do
        {
          pvAuditEntryVvector::boundsCheck(v48, v47);
          v51 = *(__int64 (__fastcall ****)(_QWORD))(*((_QWORD *)v48 + 1) + 8LL * v47);
          v52 = (**v51)(v51);
          v142 = 0;
          if ( !(unsigned int)CLKRHashTable::FindKey(v49, v52, &v142) )
          {
            v53 = v142;
            if ( v142 )
            {
              if ( (unsigned __int8)ULSShouldTrace(117141572, 200) )
              {
                pvAuditEntryVvector::boundsCheck(v48, v47);
                v54 = *(__int64 (__fastcall ****)(_QWORD))(*((_QWORD *)v48 + 1) + 8LL * v47);
                v55 = (**v54)(v54);
                v56 = Vstring::data(v50);
                ULSSendTraceTag(
                  23081352,
                  117141572,
                  200,
                  L"VsecCacheManager::SetClaimsForUser: User has link claim. User: '%S' Claim: '%S'.",
                  v56,
                  v55);
              }
              v122 = *(_DWORD *)(*(_QWORD *)(v53 + 48) + 16LL);
              Vint32Vvector::insert((Vint32Vvector *)v140, &v122);
              Vint32Vvector::insert(a23, &v122);
              v57 = *(_QWORD *)(v53 + 48);
              if ( *(_QWORD *)(v57 + 24) )
              {
                v58 = 0;
                if ( *(_DWORD *)(*(_QWORD *)(v57 + 24) + 16LL) )
                {
                  do
                  {
                    v59 = (const int *)Vint32Vvector::operator[](*(_QWORD *)(v57 + 24), v58);
                    Vint32Vvector::insert((Vint32Vvector *)v140, v59);
                    ++v58;
                    v57 = *(_QWORD *)(v53 + 48);
                  }
                  while ( v58 < *(_DWORD *)(*(_QWORD *)(v57 + 24) + 16LL) );
                  v48 = v127;
                }
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v53 + 24), 0xFFFFFFFF) == 1 && v53 != -16 )
                (**(void (__fastcall ***)(__int64, __int64))(v53 + 16))(v53 + 16, 1);
            }
          }
          ++v47;
        }
        while ( v47 < *((_DWORD *)v48 + 4) );
        v24 = v138;
        v45 = a1;
      }
      v146 = v172;
      v60 = Vint32Vvector::Vint32Vvector((Vint32Vvector *)v172, (const struct Vint32Vvector *)v140);
      v61 = VsecCacheManager::SortAndRemoveDuplicates(v45, v165, v60, v149, v157);
      VHRESULT::operator=(v24, v61);
      VHRESULT::~VHRESULT((VHRESULT *)v165);
      if ( *(int *)v24 < 0 )
      {
        LODWORD(v109) = *(_DWORD *)v24;
        ULSSendTraceTag(
          23081353,
          117141511,
          10,
          L"VsecCacheManager::SetClaimsForUser: SortAndRemoveDuplicates(vivLinkClaims) failed. HR: '0x%08x'.",
          v109);
        goto LABEL_51;
      }
      v62 = v150;
      if ( !VdbServer::databaseSchemaVersionGreaterThanOrEqualTo(v150, 16, 0, 45, 0)
        || !VdbServer::sprocsSchemaVersionGreaterThanOrEqualTo(v62, 16, 0, 30, 0) )
      {
        ULSSendTraceTag(
          5022109,
          117141624,
          100,
          L"VsecCacheManager::SetClaimsForUser: Content database schema and sproc versions do not support dynamic claims. "
           "Skipping processing.");
        goto LABEL_51;
      }
      ULSSendTraceTag(
        5812554,
        117141624,
        100,
        L"VsecCacheManager::SetClaimsForUser: Dynamic augmentation is supported by the content DB so running the code.");
      ULSPerfmonEvent(1438745533);
      v63 = v131;
      v64 = *(_DWORD *)(v131 + 8);
      v65 = v136;
      v66 = v135;
      if ( (v64 != 1 || *(_DWORD *)(v136 + 8) != 1 || *(_DWORD *)(v135 + 8) != 1)
        && (v64 != 4 || *(_DWORD *)(v136 + 8) != 5 || *(_DWORD *)(v135 + 8) != 14) )
      {
        LODWORD(v114) = *(_DWORD *)(v136 + 8);
        LODWORD(v110) = *(_DWORD *)(v131 + 8);
        ULSSendTraceTag(
          5022111,
          117141624,
          10,
          L"VsecCacheManager::SetClaimsForUser: Dynamic claim variant inputs have inconsistent types. Setting all to NULL "
           "and recalculating this user's dynamic claims. varDynamicClaims type: %d varDynamicClaimsLastUpdated type: %d "
           "varClaimMapVersionAtLastUpdate type: %d",
          v110,
          v114,
          *(_DWORD *)(v135 + 8));
        *(_DWORD *)(v63 + 8) = 1;
        *(_DWORD *)(v65 + 8) = 1;
        *(_DWORD *)(v66 + 8) = 1;
      }
      v67 = v128;
      if ( *((_DWORD *)v128 + 2) != 6 )
      {
        LODWORD(v110) = *((_DWORD *)v128 + 2);
        ULSSendTraceTag(
          5022113,
          117141624,
          10,
          L"VsecCacheManager::SetClaimsForUser: The 'allow dynamic claims refresh' variant has an inconsistent type. Expec"
           "ted OWSDBTYPE_BOOL. Setting to OWSDBTYPE_BOOL with a value of VTRUE. Received type: %d",
          v110);
        *((_DWORD *)v67 + 2) = 6;
        *v67 = 1;
      }
      v68 = 0;
      if ( *(_DWORD *)(v131 + 8) == 4 && *(_DWORD *)(v65 + 8) == 5 )
        v68 = *(_DWORD *)(v66 + 8) == 14;
      v127 = (pvAuditEntryVvector *)(a3 + 88);
      v69 = (int)CLKRHashTable::Size((CLKRHashTable *)(a3 + 88)) > 0;
      LODWORD(v116) = *v128;
      LODWORD(v114) = v69;
      LODWORD(v110) = v68;
      ULSSendTraceTag(
        5812555,
        117141572,
        100,
        L"VsecCacheManager::SetClaimsForUser: Received cache: %d SPSite uses dynamic claims: %d Refresh allowed: %d Last r"
         "efresh version: %d Current version: %d",
        v110,
        v114,
        v116,
        *(_QWORD *)v66,
        *(_QWORD *)(a3 + 136));
      v70 = 0;
      if ( *v128 == 1 )
      {
        if ( v68 && *(_QWORD *)v66 == *(_QWORD *)(a3 + 136) )
        {
          if ( v69 )
          {
            if ( !OWSTimeTFromOleDate(*(double *)v136, &v143) )
            {
              ULSSendTraceTag(
                5812556,
                117141624,
                10,
                L"VsecCacheManager::SetClaimsForUser: Unable to convert time from Vdbtime to Vtime. Returning E_FAIL.");
              VHRESULT::operator=(v24, 2147500037LL);
              goto LABEL_51;
            }
            v71 = a1;
            VsecCacheManager::IsDynamicClaimCacheExpired(a1, v160, v143);
            if ( v160[0] >= 0 )
            {
              if ( (unsigned __int8)ULSShouldTrace(117141624, 200) )
              {
                Vtime::Vtime((Vtime *)v166, v143);
                v72 = (Vstring *)Vtime::asUTCtimestamp3(v166, v151);
                v73 = Vstring::data(v72);
                ULSSendTraceTag(
                  7365506,
                  117141624,
                  200,
                  L"VsecCacheManager::SetClaimsForUser: Dynamic claims cache is not expired. Using cached claims. Time las"
                   "t updated: '%S'.",
                  v73);
                Vstring::~Vstring((Vstring *)v151);
              }
            }
            else
            {
              LODWORD(v111) = v160[0];
              ULSSendTraceTag(
                5812557,
                117141624,
                100,
                L"VsecCacheManager::SetClaimsForUser: IsDynamicClaimCacheExpired says the cache has expired. Setting refre"
                 "sh cache to VTRUE. HR: '0x%08x'.",
                v111);
              v70 = 1;
            }
            VHRESULT::~VHRESULT((VHRESULT *)v160);
LABEL_70:
            LODWORD(v111) = v70;
            ULSSendTraceTag(5812558, 117141572, 100, L"VsecCacheManager::SetClaimsForUser: Do refresh: '%d'.", v111);
            v117 = 0;
            if ( !v70 )
            {
              if ( !v68 )
                goto LABEL_51;
              v117 = 1;
              VsecCacheManager::InitDynamicClaimsFromCache(v71, v147, v131, v130, v129, v139);
              if ( v147[0] >= 0 )
              {
                ULSPerfmonEvent(180949477);
                ULSPerfmonEvent(1303316727);
                ULSSendTraceTag(
                  5812559,
                  117141624,
                  100,
                  L"VsecCacheManager::SetClaimsForUser: InitDynamicClaimsFromCache succeeded.");
                if ( *v129 )
                  VsecCacheManager::AddClaimIdsFromCache(v71, (struct VsiteCollectionRecord *)a3, *v129, *v130, a23);
              }
              else
              {
                ULSPerfmonEvent(508259280);
                v70 = 1;
                LODWORD(v112) = v147[0];
                if ( *v128 == 1 )
                {
                  ULSSendTraceTag(
                    5022115,
                    117141624,
                    10,
                    L"VsecCacheManager::SetClaimsForUser: Call to InitDynamicClaimsFromCache failed. Will attempt to refre"
                     "sh claims. HR: '0x%08x'.",
                    v112);
                }
                else
                {
                  ULSSendTraceTag(
                    5022144,
                    117141624,
                    10,
                    L"VsecCacheManager::SetClaimsForUser: Call to InitDynamicClaimsFromCache failed. Caller disallowed cla"
                     "im refresh. HR: '0x%08x'.",
                    v112);
                  v70 = 0;
                }
              }
              VHRESULT::~VHRESULT((VHRESULT *)v147);
            }
            v74 = 0;
            if ( v70 != 1 )
            {
LABEL_51:
              Vint32Vvector::~Vint32Vvector((Vint32Vvector *)v140);
              goto LABEL_33;
            }
            if ( !v69 )
            {
              ULSSendTraceTag(
                7365507,
                117141624,
                200,
                L"VsecCacheManager::SetClaimsForUser: SPSite does not use dynamic claims and we will update the cached cla"
                 "ims to reflect that. We will not try to refresh the user's dynamic claims again until something in the "
                 "SPSite is ACLed to a dynamic claim.");
              *v144 = 1;
              goto LABEL_51;
            }
            v120 = 0;
            v123 = 0;
            if ( QueryPerformanceFrequency(&Frequency) && Frequency.QuadPart >= 1 )
            {
              v74 = 1;
              TickCount64 = 0;
              QueryPerformanceCounter(&PerformanceCount);
              QuadPart = 0;
              if ( PerformanceCount.QuadPart >= 0 )
                QuadPart = PerformanceCount.QuadPart;
            }
            else
            {
              TickCount64 = 0;
              QuadPart = GetTickCount64();
            }
            ULSSendTraceTag(
              18982722,
              117141624,
              100,
              L"VsecCacheManager::SetClaimsForUser: Calling dynamic claim providers to find out if the user has membership"
               " in the dynamic claims.");
            v133[0] = &VmanagedCodeInterop::`vftable';
            v133[1] = 0;
            v77 = VmanagedCodeInterop::CheckDynamicClaimsForUser(
                    v133,
                    v167,
                    v154,
                    v125,
                    *(_QWORD *)(a3 + 128),
                    &v120,
                    &v123);
            VHRESULT::operator=(v24, v77);
            VHRESULT::~VHRESULT((VHRESULT *)v167);
            if ( QuadPart )
            {
              if ( v74 )
              {
                QueryPerformanceCounter(&v155);
                TickCount64 = 0;
                if ( v155.QuadPart >= 0 )
                  TickCount64 = v155.QuadPart;
              }
              else
              {
                TickCount64 = GetTickCount64();
              }
            }
            if ( *(int *)v24 >= 0 && v120 )
            {
              ULSPerfmonEvent(2140861980);
              ULSPerfmonEvent(380040645);
              if ( QuadPart )
              {
                if ( !TickCount64 )
                {
                  if ( v74 )
                  {
                    QueryPerformanceCounter(&v156);
                    TickCount64 = 0;
                    if ( v156.QuadPart >= 0 )
                      TickCount64 = v156.QuadPart;
                  }
                  else
                  {
                    TickCount64 = GetTickCount64();
                  }
                }
                if ( TickCount64 >= QuadPart )
                  v79 = TickCount64 - QuadPart;
                else
                  v79 = TickCount64 - QuadPart - 1;
                v78 = 0;
                if ( v79 <= 0x7FFFFFFFFFFFFFFFLL )
                  v78 = v79;
              }
              else
              {
                v78 = 0;
              }
              v80 = 399998856;
            }
            else
            {
              ULSPerfmonEvent(1302336102);
              ULSPerfmonEvent(558549861);
              if ( QuadPart )
              {
                if ( !TickCount64 )
                {
                  if ( v74 )
                  {
                    QueryPerformanceCounter(&v145);
                    TickCount64 = 0;
                    if ( v145.QuadPart >= 0 )
                      TickCount64 = v145.QuadPart;
                  }
                  else
                  {
                    TickCount64 = GetTickCount64();
                  }
                }
                if ( TickCount64 >= QuadPart )
                  v81 = TickCount64 - QuadPart;
                else
                  v81 = TickCount64 - QuadPart - 1;
                v78 = 0;
                if ( v81 <= 0x7FFFFFFFFFFFFFFFLL )
                  v78 = v81;
              }
              else
              {
                v78 = 0;
              }
              v80 = 1652710711;
            }
            ULSPerfmonIncrement(v80, v78);
            v82 = *(_DWORD *)v24;
            v83 = 0;
            if ( *(int *)v24 >= 0 )
            {
              v86 = v120;
              if ( v120 )
              {
                v87 = *(_QWORD *)(a3 + 128);
                v88 = *(unsigned int *)(v87 + 24);
                v89 = (v88 - (*(_DWORD *)(v87 + 24) & 7)) >> 3;
                if ( (*(_DWORD *)(v87 + 24) & 7) != 0 )
                  ++v89;
                if ( v123 != v89 )
                {
                  LODWORD(v115) = v123;
                  ULSSendTraceTag(
                    5812560,
                    117141624,
                    10,
                    L"VsecCacheManager::SetClaimsForUser: Dynamic claim bitmask is an unexpected length. Expected: '%d', Actual: '%d'.",
                    v89,
                    v115);
                  VHRESULT::operator=(v24, 2147500037LL);
                  goto LABEL_136;
                }
                v90 = SafeArrayAccessData(*(SAFEARRAY **)(a3 + 128), &ppvData);
                VHRESULT::operator=(v24, v90);
                v82 = *(_DWORD *)v24;
                if ( *(int *)v24 >= 0 )
                {
                  v91 = 0;
                  if ( v88 )
                  {
                    v92 = v127;
                    do
                    {
                      if ( ((*(unsigned __int8 *)(((v91 - (v91 & 7)) >> 3) + v86) >> (v91 & 7)) & 1) != 0 )
                      {
                        v182 = v183;
                        v184 = 0;
                        v185 = 512;
                        VstackBuffer512::appendBSTR((VstackBuffer512 *)&v182, *((wchar_t *const *)ppvData + v91));
                        *((_BYTE *)v182 + v184) = 0;
                        v132 = 0;
                        if ( (unsigned int)CLKRHashTable::FindKey(v92, v182, &v132) || (v93 = v132) == 0 )
                        {
                          ULSSendTraceTag(
                            5022150,
                            117141624,
                            10,
                            L"SetClaimsForUser: Dynamic claim not found in map! Skipping. Claim (hex): '%s'.",
                            *((_QWORD *)ppvData + v91));
                        }
                        else
                        {
                          if ( (unsigned __int8)ULSShouldTrace(117141624, 200) )
                          {
                            v95 = Vstring::data(v125);
                            ULSSendTraceTag(
                              7365508,
                              117141624,
                              200,
                              L"VsecCacheManager::SetClaimsForUser user has dynamic claim. User: '%S' Claim (hex): '%s'.",
                              v95,
                              *((_QWORD *)ppvData + v91));
                          }
                          v96 = *((_QWORD *)v93 + 6);
                          if ( v96 )
                          {
                            v124 = *(_DWORD *)(v96 + 16);
                            Vint32Vvector::insert((Vint32Vvector *)v161, &v124);
                            Vint32Vvector::insert(a23, &v124);
                            v97 = *((_QWORD *)v93 + 6);
                            if ( *(_QWORD *)(v97 + 24) )
                            {
                              if ( *(_DWORD *)(*(_QWORD *)(v97 + 24) + 16LL) )
                              {
                                do
                                {
                                  v98 = (const int *)Vint32Vvector::operator[](*(_QWORD *)(v97 + 24), v83);
                                  Vint32Vvector::insert((Vint32Vvector *)v161, v98);
                                  ++v83;
                                  v97 = *((_QWORD *)v93 + 6);
                                }
                                while ( v83 < *(_DWORD *)(*(_QWORD *)(v97 + 24) + 16LL) );
                                v92 = v127;
                              }
                              v83 = 0;
                            }
                            if ( *(_BYTE *)(*((_QWORD *)v93 + 6) + 36LL) )
                              *v139 = 1;
                            v94 = (void (__fastcall ***)(_QWORD, __int64))(v93 + 16);
                            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v93 + 6, 0xFFFFFFFF) == 1
                              && v93 != (_BYTE *)-16LL )
                            {
                              (**v94)(v94, 1);
                            }
                          }
                        }
                        v99 = v182;
                        if ( v182 != v183 )
                        {
                          if ( (unsigned int)COWSAllocator::QueryNewMode(v94) )
                            COWSAllocator::Free(v99);
                          else
                            free(v99);
                        }
                        v86 = v120;
                      }
                      ++v91;
                    }
                    while ( v91 < v88 );
                    v24 = v138;
                  }
                  SafeArrayUnaccessData(*(SAFEARRAY **)(a3 + 128));
                  v145.QuadPart = (LONGLONG)v173;
                  v100 = Vint32Vvector::Vint32Vvector((Vint32Vvector *)v173, (const struct Vint32Vvector *)v161);
                  v101 = VsecCacheManager::SortAndRemoveDuplicates(a1, v168, v100, v130, v129);
                  VHRESULT::operator=(v24, v101);
                  VHRESULT::~VHRESULT((VHRESULT *)v168);
                  v82 = *(_DWORD *)v24;
                  if ( *(int *)v24 >= 0 )
                  {
                    *v144 = 1;
                    goto LABEL_136;
                  }
                  v84 = L"VsecCacheManager::SetClaimsForUser: SortAndRemoveDuplicates from dynamic claims vector failed. HR: '0x%08x'.";
                  v85 = 5812562;
                }
                else
                {
                  v84 = L"VsecCacheManager::SetClaimsForUser: SafeArrayAccessData failed for dynamic claims. HR: '0x%08x'.";
                  v85 = 5812561;
                }
              }
              else
              {
                if ( !v68 || v117 )
                  goto LABEL_136;
                ULSSendTraceTag(
                  5022151,
                  117141624,
                  10,
                  L"Tried to refresh dynamic claims but the claim providers returned a null bitmask. Trying to use the cac"
                   "hed claim vector.");
                v102 = v129;
                v103 = v130;
                inited = VsecCacheManager::InitDynamicClaimsFromCache(a1, v169, v131, v130, v129, v139);
                VHRESULT::operator=(v24, inited);
                VHRESULT::~VHRESULT((VHRESULT *)v169);
                if ( *(int *)v24 >= 0 )
                {
                  ULSPerfmonEvent(214531827);
                  if ( *v102 )
                    VsecCacheManager::AddClaimIdsFromCache(a1, (struct VsiteCollectionRecord *)a3, *v102, *v103, a23);
                  goto LABEL_136;
                }
                ULSPerfmonEvent(1748316671);
                v82 = *(_DWORD *)v24;
                v84 = L"Dynamic claims refresh failed, and so did initialization from the cached value. HR: '0x%08x'.";
                v85 = 5022152;
              }
            }
            else
            {
              v84 = L"VsecCacheManager::SetClaimsForUser: Call to VmanagedCodeInterop::CheckDynamicClaimsForUser failed. HR: '0x%08x'.";
              v85 = 5022146;
            }
            LODWORD(v113) = v82;
            ULSSendTraceTag(v85, 117141624, 10, v84, v113);
LABEL_136:
            VmanagedCodeInterop::~VmanagedCodeInterop((VmanagedCodeInterop *)v133);
            goto LABEL_51;
          }
        }
        else
        {
          v70 = 1;
        }
      }
      v71 = a1;
      goto LABEL_70;
    }
    ULSSendTraceTag(5769169, 117141624, 10, L"VsecCacheManager::SetClaimsForUser claim map record was null.");
    VHRESULT::operator=(v24, 2147500037LL);
    v25 = a23;
  }
LABEL_182:
  if ( *(int *)v24 >= 0 )
  {
    VHRESULT::operator=(v24, 0);
    Vint32Vvector::sort(v25, (int (*)(const int *, const int *))sub_180128980);
  }
  Vint32Vvector::~Vint32Vvector((Vint32Vvector *)v161);
  Vint32Vvector::~Vint32Vvector((Vint32Vvector *)v162);
  v106 = v178;
  if ( v178 != v179 )
  {
    if ( (unsigned int)COWSAllocator::QueryNewMode(v105) )
      COWSAllocator::Free(v106);
    else
      free(v106);
  }
  return v24;
}

```

## disassembly

```asm
0x180177110  mov     rax, rsp
0x180177113  push    rbp
0x180177114  push    rsi
0x180177115  push    rdi
0x180177116  push    r12
0x180177118  push    r13
0x18017711a  push    r14
0x18017711c  push    r15
0x18017711e  lea     rbp, [rax-898h]
0x180177125  sub     rsp, 960h
0x18017712c  mov     [rbp+890h+var_770], 0FFFFFFFFFFFFFFFEh
0x180177137  mov     [rax+20h], rbx
0x18017713b  mov     rax, cs:__security_cookie
0x180177142  xor     rax, rsp
0x180177145  mov     [rbp+890h+var_40], rax
0x18017714c  mov     [rbp+890h+var_810], r9
0x180177153  mov     rdi, r8
0x180177156  mov     [rsp+68h], r8
0x18017715b  mov     r13, rdx
0x18017715e  mov     [rbp+890h+var_890], rdx
0x180177162  mov     [rsp+990h+var_930], rcx
0x180177167  mov     [rbp+890h+var_768], rdx
0x18017716e  mov     rbx, [rbp+890h+arg_20]
0x180177175  mov     [rbp+890h+var_7F0], rbx
0x18017717c  mov     rax, [rbp+890h+arg_28]
0x180177183  mov     [rbp+890h+var_900], rax
0x180177187  mov     r15, [rbp+890h+arg_30]
0x18017718e  mov     rax, [rbp+890h+arg_38]
0x180177195  mov     [rbp+890h+var_8D0], rax
0x180177199  mov     rax, [rbp+890h+arg_40]
0x1801771a0  mov     [rbp+890h+var_8A0], rax
0x1801771a4  mov     rax, [rbp+890h+arg_48]
0x1801771ab  mov     [rbp+890h+var_8A8], rax
0x1801771af  mov     rax, [rbp+890h+arg_50]
0x1801771b6  mov     [rbp+890h+var_8E8], rax
0x1801771ba  mov     rax, [rbp+890h+arg_58]
0x1801771c1  mov     [rbp+890h+var_8F0], rax
0x1801771c5  mov     rax, [rbp+890h+arg_60]
0x1801771cc  mov     [rbp+890h+var_7D0], rax
0x1801771d3  mov     rax, [rbp+890h+arg_68]
0x1801771da  mov     [rbp+890h+var_838], rax
0x1801771de  mov     rax, [rbp+890h+arg_70]
0x1801771e5  mov     [rbp+890h+var_8E0], rax
0x1801771e9  mov     rax, [rbp+890h+arg_78]
0x1801771f0  mov     [rbp+890h+var_8D8], rax
0x1801771f4  mov     rax, [rbp+890h+arg_80]
0x1801771fb  mov     [rbp+890h+var_7D8], rax
0x180177202  mov     rax, [rbp+890h+arg_88]
0x180177209  mov     [rbp+890h+var_818], rax
0x18017720d  mov     rax, [rbp+890h+arg_90]
0x180177214  mov     [rbp+890h+var_8C8], rax
0x180177218  mov     rax, [rbp+890h+arg_98]
0x18017721f  mov     [rbp+890h+var_888], rax
0x180177223  mov     r14, [rbp+890h+arg_A0]
0x18017722a  mov     [rbp+890h+var_848], r14
0x18017722e  mov     rsi, [rbp+890h+arg_B0]
0x180177235  mov     [rsp+990h+var_938], rsi
0x18017723a  xor     r12d, r12d
0x18017723d  mov     [rbp+890h+var_8B0], r12d
0x180177241  xor     edx, edx
0x180177243  mov     rcx, r13
0x180177246  call    cs:??0VHRESULT@@QEAA@J@Z; VHRESULT::VHRESULT(long)
0x18017724c  lea     eax, [r12+1]
0x180177251  mov     [rbp+890h+var_8B0], eax
0x180177254  lea     rax, [rbp+890h+var_478]
0x18017725b  mov     [rbp+890h+var_480], rax
0x180177262  mov     [rbp+890h+var_274], r12d
0x180177269  mov     [rbp+890h+var_270], 200h
0x180177273  lea     rcx, [rbp+890h+var_790]
0x18017727a  call    cs:??0Vint32Vvector@@QEAA@XZ; Vint32Vvector::Vint32Vvector(void)
0x180177280  nop
0x180177281  lea     rcx, [rbp+890h+var_7B0]
0x180177288  call    cs:??0Vint32Vvector@@QEAA@XZ; Vint32Vvector::Vint32Vvector(void)
0x18017728e  nop
0x18017728f  lea     eax, [r12+1]
0x180177294  cmp     [rbp+890h+arg_A8], eax
0x18017729a  setz    r12b
0x18017729e  mov     rcx, rsi
0x1801772a1  call    cs:?clear@Vint32Vvector@@QEAAXXZ; Vint32Vvector::clear(void)
0x1801772a7  xor     eax, eax
0x1801772a9  mov     [r14], al
0x1801772ac  test    r15, r15
0x1801772af  jz      loc_1801783B7
0x1801772b5  mov     dword ptr [rsp+990h+var_970], 1D7Bh; int
0x1801772bd  lea     r9, aStsWelSecurity; "\\sts\\wel\\security.cpp"
0x1801772c4  lea     r8, qword_18020E990; char *
0x1801772cb  mov     rdx, rdi; struct VsiteCollectionRecord *
0x1801772ce  lea     rcx, aSetclaimsforus_0; "SetClaimsForUser"
0x1801772d5  call    ?LogDGCacheEvents@@YAXPEBDPEBVVsiteCollectionRecord@@00H@Z; LogDGCacheEvents(char const *,VsiteCollectionRecord const *,char const *,char const *,int)
0x1801772da  mov     rdx, rbx
0x1801772dd  lea     rcx, [rbp+890h+var_7C8]
0x1801772e4  call    cs:??0Vwstring@@QEAA@AEBVVstring@@@Z; Vwstring::Vwstring(Vstring const &)
0x1801772ea  mov     rbx, rax
0x1801772ed  mov     rdx, [rbp+890h+var_900]
0x1801772f1  lea     rcx, [rbp+890h+var_820]
0x1801772f5  call    cs:??0Vwstring@@QEAA@AEBVVstring@@@Z; Vwstring::Vwstring(Vstring const &)
0x1801772fb  mov     rcx, rax
0x1801772fe  mov     rax, [rbx]
0x180177301  mov     rcx, [rcx]
0x180177304  mov     [rsp+990h+var_968], rax
0x180177309  mov     [rsp+990h+var_970], rcx
0x18017730e  lea     r9, aVseccachemanag; "VsecCacheManager::SetClaimsForUser entr"...
0x180177315  mov     edx, 6FB7044h
0x18017731a  mov     ecx, 58B149h
0x18017731f  mov     r8d, 64h ; 'd'
0x180177325  call    cs:ULSSendTraceTag
0x18017732b  nop
0x18017732c  lea     rcx, [rbp+890h+var_820]
0x180177330  call    cs:??1Vwstring@@QEAA@XZ; Vwstring::~Vwstring(void)
0x180177336  nop
0x180177337  lea     rcx, [rbp+890h+var_7C8]
0x18017733e  call    cs:??1Vwstring@@QEAA@XZ; Vwstring::~Vwstring(void)
0x180177344  xor     edx, edx
0x180177346  test    rdi, rdi
0x180177349  jz      loc_180178387
0x18017734f  mov     r14d, edx
0x180177352  cmp     [r15], edx
0x180177355  jbe     loc_1801775B7
0x18017735b  lea     rsi, [rdi+30h]
0x18017735f  mov     [rbp+890h+var_8F8], rsi
0x180177363  mov     r13, [rbp+890h+var_8C8]
0x180177367  mov     ebx, r14d
0x18017736a  shl     rbx, 4
0x18017736e  add     rbx, r15
0x180177371  test    r12b, r12b
0x180177374  jz      short loc_180177386
0x180177376  mov     rcx, [rbx+8]; pSid
0x18017737a  call    cs:GetLengthSid
0x180177380  mov     edi, eax
0x180177382  xor     edx, edx
0x180177384  jmp     short loc_180177389
0x180177386  mov     edi, [rbx+10h]
0x180177389  mov     [rbp+890h+var_274], edx
0x18017738f  mov     r8d, edi
0x180177392  mov     rdx, [rbx+8]
0x180177396  lea     rcx, [rbp+890h+var_480]
0x18017739d  call    cs:?appendBinary@VstackBuffer512@@QEAAAEAV1@PEBEK@Z; VstackBuffer512::appendBinary(uchar const *,ulong)
0x1801773a3  mov     ecx, [rbp+890h+var_274]
0x1801773a9  mov     rax, [rbp+890h+var_480]
0x1801773b0  xor     edx, edx
0x1801773b2  mov     [rcx+rax], dl
0x1801773b5  mov     [rbp+890h+var_860], rdx
0x1801773b9  lea     r8, [rbp+890h+var_860]
0x1801773bd  mov     rdx, [rbp+890h+var_480]
0x1801773c4  mov     rcx, rsi
0x1801773c7  call    cs:?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1801773cd  xor     edx, edx
0x1801773cf  test    eax, eax
0x1801773d1  jnz     loc_1801775A2
0x1801773d7  mov     rsi, [rbp+890h+var_860]
0x1801773db  test    rsi, rsi
0x1801773de  jz      loc_18017759E
0x1801773e4  mov     edx, 0C8h
0x1801773e9  mov     ecx, 6FB7044h
0x1801773ee  call    cs:ULSShouldTrace
0x1801773f4  xor     ecx, ecx
0x1801773f6  test    al, al
0x1801773f8  jz      loc_1801774FA
0x1801773fe  lea     rax, [rbp+890h+var_698]
0x180177405  mov     [rbp+890h+Block], rax
0x18017740c  mov     [rbp+890h+var_494], ecx
0x180177412  mov     [rbp+890h+var_490], 200h
0x18017741c  test    r12b, r12b
0x18017741f  jz      short loc_18017743A
0x180177421  mov     rdx, [rbx+8]
0x180177425  lea     rcx, [rbp+890h+Block]
0x18017742c  call    cs:?appendSid@VstackBuffer512@@QEAAAEAV1@QEAX@Z; VstackBuffer512::appendSid(void * const)
0x180177432  mov     eax, [rbp+890h+var_494]
0x180177438  jmp     short loc_180177484
0x18017743a  mov     rbx, [rbx+8]
0x18017743e  mov     ecx, [rbp+890h+var_494]
0x180177444  lea     eax, [rcx+rdi]
0x180177447  cmp     eax, [rbp+890h+var_490]
0x18017744d  jbe     short loc_180177464
0x18017744f  mov     edx, edi
0x180177451  lea     rcx, [rbp+890h+Block]
0x180177458  call    cs:?reallocate@VstackBuffer512@@AEAAXI@Z; VstackBuffer512::reallocate(uint)
0x18017745e  mov     ecx, [rbp+890h+var_494]
0x180177464  mov     r8d, edi; Size
0x180177467  add     rcx, [rbp+890h+Block]; void *
0x18017746e  mov     rdx, rbx; Src
0x180177471  call    memcpy
0x180177476  mov     eax, [rbp+890h+var_494]
0x18017747c  add     eax, edi
0x18017747e  mov     [rbp+890h+var_494], eax
0x180177484  mov     ecx, eax
0x180177486  mov     rax, [rbp+890h+Block]
0x18017748d  xor     edi, edi
0x18017748f  mov     [rcx+rax], dil
0x180177493  mov     rbx, [rbp+890h+Block]
0x18017749a  mov     rcx, [rbp+890h+var_900]
0x18017749e  call    cs:?data@Vstring@@QEBAPEBDXZ; Vstring::data(void)
0x1801774a4  mov     [rsp+990h+var_968], rbx
0x1801774a9  mov     [rsp+990h+var_970], rax
0x1801774ae  lea     r9, aVseccachemanag_0; "VsecCacheManager::SetClaimsForUser: Use"...
0x1801774b5  mov     edx, 6FB7044h
0x1801774ba  mov     ecx, 706381h
0x1801774bf  mov     r8d, 0C8h
0x1801774c5  call    cs:ULSSendTraceTag
0x1801774cb  nop
0x1801774cc  lea     rax, [rbp+890h+var_698]
0x1801774d3  mov     rbx, [rbp+890h+Block]
0x1801774da  cmp     rbx, rax
0x1801774dd  jz      short loc_1801774FA
0x1801774df  call    cs:?QueryNewMode@COWSAllocator@@SAHXZ; COWSAllocator::QueryNewMode(void)
0x1801774e5  mov     rcx, rbx; Block
0x1801774e8  test    eax, eax
0x1801774ea  jz      short loc_1801774F4
0x1801774ec  call    cs:?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x1801774f2  jmp     short loc_1801774FA
0x1801774f4  call    cs:free
0x1801774fa  mov     rax, [rsi+30h]
0x1801774fe  mov     ecx, [rax+10h]
0x180177501  mov     [rbp+890h+var_910], ecx
0x180177504  lea     rdx, [rbp+890h+var_910]
0x180177508  lea     rcx, [rbp+890h+var_790]
0x18017750f  call    cs:?insert@Vint32Vvector@@QEAAXAEBJ@Z; Vint32Vvector::insert(long const &)
0x180177515  lea     rdx, [rbp+890h+var_910]
0x180177519  mov     rcx, [rsp+990h+var_938]
0x18017751e  call    cs:?insert@Vint32Vvector@@QEAAXAEBJ@Z; Vint32Vvector::insert(long const &)
0x180177524  mov     rax, [rsi+30h]
0x180177528  xor     edx, edx
0x18017752a  lea     edi, [rdx+1]
0x18017752d  cmp     [rax+24h], dl
0x180177530  jz      short loc_180177536
0x180177532  mov     [r13+0], dil
0x180177536  mov     rcx, [rsi+30h]
0x18017753a  cmp     [rcx+18h], rdx
0x18017753e  jz      short loc_180177578
0x180177540  mov     ebx, edx
0x180177542  mov     rax, [rcx+18h]
0x180177546  cmp     [rax+10h], edx
0x180177549  jbe     short loc_180177578
0x18017754b  mov     edx, ebx
0x18017754d  mov     rcx, [rcx+18h]
0x180177551  call    cs:??AVint32Vvector@@QEAAAEAJI@Z; Vint32Vvector::operator[](uint)
0x180177557  mov     rdx, rax
0x18017755a  lea     rcx, [rbp+890h+var_790]
0x180177561  call    cs:?insert@Vint32Vvector@@QEAAXAEBJ@Z; Vint32Vvector::insert(long const &)
0x180177567  add     ebx, edi
0x180177569  mov     rcx, [rsi+30h]
0x18017756d  mov     rax, [rcx+18h]
0x180177571  cmp     ebx, [rax+10h]
0x180177574  jb      short loc_18017754B
0x180177576  xor     edx, edx
0x180177578  lea     rcx, [rsi+10h]
0x18017757c  or      eax, 0FFFFFFFFh
0x18017757f  lock xadd [rcx+8], eax
0x180177584  cmp     eax, 1
0x180177587  jnz     short loc_18017759E
0x180177589  test    rcx, rcx
0x18017758c  jz      short loc_18017759E
0x18017758e  mov     rax, [rcx]
0x180177591  mov     edx, edi
0x180177593  mov     rax, [rax]
0x180177596  call    cs:__guard_dispatch_icall_fptr
0x18017759c  xor     edx, edx
0x18017759e  mov     rsi, [rbp+890h+var_8F8]
0x1801775a2  inc     r14d
0x1801775a5  cmp     r14d, [r15]
0x1801775a8  jb      loc_180177367
0x1801775ae  mov     r13, [rbp+890h+var_890]
0x1801775b2  mov     rdi, [rsp+68h]
0x1801775b7  lea     rax, [rbp+890h+var_700]
0x1801775be  mov     [rbp+890h+var_8F8], rax
0x1801775c2  lea     rdx, [rbp+890h+var_790]
0x1801775c9  lea     rcx, [rbp+890h+var_700]
0x1801775d0  call    cs:??0Vint32Vvector@@QEAA@AEBV0@@Z; Vint32Vvector::Vint32Vvector(Vint32Vvector const &)
0x1801775d6  nop
0x1801775d7  mov     rcx, [rbp+890h+var_7D0]
0x1801775de  mov     [rsp+990h+var_970], rcx
0x1801775e3  mov     r9, [rbp+890h+var_838]
0x1801775e7  mov     r8, rax
0x1801775ea  lea     rdx, [rbp+890h+var_710]
0x1801775f1  mov     r12, [rsp+990h+var_930]
0x1801775f6  mov     rcx, r12
0x1801775f9  call    ?SortAndRemoveDuplicates@VsecCacheManager@@AEAA?AVVHRESULT@@VVint32Vvector@@PEAPEAJPEAK@Z; VsecCacheManager::SortAndRemoveDuplicates(Vint32Vvector,long * *,ulong *)
0x1801775fe  nop
0x1801775ff  mov     rdx, rax
0x180177602  mov     rcx, r13
0x180177605  call    cs:??4VHRESULT@@QEAAAEAV0@AEBV0@@Z; VHRESULT::operator=(VHRESULT const &)
0x18017760b  nop
0x18017760c  lea     rcx, [rbp+890h+var_710]
0x180177613  call    cs:??1VHRESULT@@QEAA@XZ; VHRESULT::~VHRESULT(void)
0x180177619  mov     eax, [r13+0]
0x18017761d  xor     r15d, r15d
0x180177620  test    eax, eax
0x180177622  jns     short loc_18017764D
0x180177624  mov     dword ptr [rsp+990h+var_970], eax
0x180177628  lea     r9, aVseccachemanag_1; "VsecCacheManager::SetClaimsForUser: Sor"...
0x18017762f  mov     edx, 6FB7007h
0x180177634  mov     ecx, 5807D0h
0x180177639  lea     r8d, [r15+0Ah]
0x18017763d  call    cs:ULSSendTraceTag
0x180177643  mov     rsi, [rsp+990h+var_938]
0x180177648  jmp     loc_1801783BA
0x18017764d  lea     rcx, [rbp+890h+var_880]
0x180177651  call    cs:??0Vint32Vvector@@QEAA@XZ; Vint32Vvector::Vint32Vvector(void)
0x180177657  nop
0x180177658  mov     esi, r15d
  ... truncated ...
```
