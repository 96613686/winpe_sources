# CreateProcessExtensions::PreCreationExtension(void *,Common::COMMON_STRING *,_SECURITY_CAPABILITIES *,CreateProcessExtensions::ErrorContext *,_APPX_PROCESS_CONTEXT * *)

- ea: `0x1800496e0`
- end: `0x18004c238`
- name: `?PreCreationExtension@CreateProcessExtensions@@SAJPEAXPEAUCOMMON_STRING@Common@@PEAU_SECURITY_CAPABILITIES@@PEAVErrorContext@1@PEAPEAU_APPX_PROCESS_CONTEXT@@@Z`
- size: `11096`
- prototype: `__int64 __usercall@<rax>(HANDLE TokenHandle@<rcx>, struct Common::COMMON_STRING *@<rdx>, struct _SECURITY_CAPABILITIES *@<r8>, struct CreateProcessExtensions::ErrorContext *@<r9>, struct _APPX_PROCESS_CONTEXT **)`
- caller_count: `1`
- callee_count: `44`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a7f70`

## callees

- `0x1800134a0`
- `0x1800220f0`
- `0x18002ddc0`
- `0x18002f738`
- `0x18002f994`
- `0x180032f18`
- `0x180048f30`
- `0x1800493bc`
- `0x180049440`
- `0x180049460`
- `0x1800496e0`
- `0x18004c240`
- `0x18004c260`
- `0x18004c328`
- `0x18004c360`
- `0x18004c390`
- `0x18004c3b8`
- `0x18004c3e8`
- `0x18004c9c8`
- `0x18004cb70`
- `0x18004cb90`
- `0x18004f930`
- `0x180053148`
- `0x180057f40`
- `0x180058768`
- `0x180059e60`
- `0x18005b460`
- `0x18005b710`
- `0x1800689c8`
- `0x18009ba40`
- `0x18009de04`
- `0x18009df2c`
- `0x1800ab1d0`
- `0x1800ab840`
- `0x1800b5f1c`
- `0x1800dd594`
- `0x1800dd65c`
- `0x1800e48ac`
- `0x1800e93e0`
- `0x1801055dc`
- `0x1801080b4`
- `0x18010caa8`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180049d53`
- `ntdll!RtlInitUnicodeString` at `0x180049d53`
- `ntdll!RtlEqualSid` at `0x18004b097`
- `ntdll!RtlEqualSid` at `0x18004b097`
- `ntdll!RtlSetLastWin32Error` at `0x180049c8f`
- `ntdll!RtlSetLastWin32Error` at `0x180049c8f`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180049d24`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180049d24`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180049e17`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180049e17`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180049d78`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180049dfe`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180049d78`
- `ntdll!RtlExpandEnvironmentStrings_U` at `0x180049dfe`
- `ntdll!NtQueryInformationToken` at `0x180049925`
- `ntdll!NtQueryInformationToken` at `0x18004ab90`
- `ntdll!NtQueryInformationToken` at `0x180049925`
- `ntdll!NtQueryInformationToken` at `0x18004ab90`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18004a897`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18004a897`
- `ntdll!RtlFreeSid` at `0x180049f3f`
- `ntdll!RtlFreeSid` at `0x18004a06b`
- `ntdll!RtlFreeSid` at `0x18004a15d`
- `ntdll!RtlFreeSid` at `0x18004a628`
- `ntdll!RtlFreeSid` at `0x18004a78b`
- `ntdll!RtlFreeSid` at `0x18004a942`
- `ntdll!RtlFreeSid` at `0x18004aa0b`
- `ntdll!RtlFreeSid` at `0x18004ab25`
- `ntdll!RtlFreeSid` at `0x18004acab`
- `ntdll!RtlFreeSid` at `0x18004ad8f`
- `ntdll!RtlFreeSid` at `0x18004ae35`
- `ntdll!RtlFreeSid` at `0x18004af13`
- `ntdll!RtlFreeSid` at `0x18004b032`
- `ntdll!RtlFreeSid` at `0x18004b0ed`
- `ntdll!RtlFreeSid` at `0x18004b1a9`
- `ntdll!RtlFreeSid` at `0x18004b259`
- `ntdll!RtlFreeSid` at `0x18004b36b`
- `ntdll!RtlFreeSid` at `0x18004b47b`
- `ntdll!RtlFreeSid` at `0x18004b68c`
- `ntdll!RtlFreeSid` at `0x18004b7aa`
- `ntdll!RtlFreeSid` at `0x18004b879`
- `ntdll!RtlFreeSid` at `0x18004b980`
- `ntdll!RtlFreeSid` at `0x18004ba9e`
- `ntdll!RtlFreeSid` at `0x18004bb45`
- `ntdll!RtlFreeSid` at `0x18004bd3d`
- `ntdll!RtlFreeSid` at `0x18004bddd`
- `ntdll!RtlFreeSid` at `0x18004be7d`
- `ntdll!RtlFreeSid` at `0x18004bf1d`
- `ntdll!RtlFreeSid` at `0x18004bfb3`
- `ntdll!RtlFreeSid` at `0x18004c049`
- `ntdll!RtlFreeSid` at `0x18004c0df`
- `ntdll!RtlFreeSid` at `0x18004c17a`
- `ntdll!RtlFreeSid` at `0x180049f3f`
- `ntdll!RtlFreeSid` at `0x18004a06b`
- `ntdll!RtlFreeSid` at `0x18004a15d`
- `ntdll!RtlFreeSid` at `0x18004a628`
- `ntdll!RtlFreeSid` at `0x18004a78b`
- `ntdll!RtlFreeSid` at `0x18004a942`
- `ntdll!RtlFreeSid` at `0x18004aa0b`
- `ntdll!RtlFreeSid` at `0x18004ab25`
- `ntdll!RtlFreeSid` at `0x18004acab`
- `ntdll!RtlFreeSid` at `0x18004ad8f`
- `ntdll!RtlFreeSid` at `0x18004ae35`
- `ntdll!RtlFreeSid` at `0x18004af13`
- `ntdll!RtlFreeSid` at `0x18004b032`
- `ntdll!RtlFreeSid` at `0x18004b0ed`
- `ntdll!RtlFreeSid` at `0x18004b1a9`
- `ntdll!RtlFreeSid` at `0x18004b259`
- `ntdll!RtlFreeSid` at `0x18004b36b`
- `ntdll!RtlFreeSid` at `0x18004b47b`
- `ntdll!RtlFreeSid` at `0x18004b68c`
- `ntdll!RtlFreeSid` at `0x18004b7aa`
- `ntdll!RtlFreeSid` at `0x18004b879`
- `ntdll!RtlFreeSid` at `0x18004b980`
- `ntdll!RtlFreeSid` at `0x18004ba9e`
- `ntdll!RtlFreeSid` at `0x18004bb45`
- `ntdll!RtlFreeSid` at `0x18004bd3d`
- `ntdll!RtlFreeSid` at `0x18004bddd`
- `ntdll!RtlFreeSid` at `0x18004be7d`
- `ntdll!RtlFreeSid` at `0x18004bf1d`
- `ntdll!RtlFreeSid` at `0x18004bfb3`
- `ntdll!RtlFreeSid` at `0x18004c049`
- `ntdll!RtlFreeSid` at `0x18004c0df`
- `ntdll!RtlFreeSid` at `0x18004c17a`
- `ntdll!RtlLengthSid` at `0x18004995a`
- `ntdll!RtlLengthSid` at `0x180049c98`
- `ntdll!RtlLengthSid` at `0x18004abfd`
- `ntdll!RtlLengthSid` at `0x18004995a`
- `ntdll!RtlLengthSid` at `0x180049c98`
- `ntdll!RtlLengthSid` at `0x18004abfd`
- `ntdll!RtlGetAppContainerSidType` at `0x18004abac`
- `ntdll!RtlGetAppContainerSidType` at `0x18004abac`
- `ntdll!RtlCopySid` at `0x180049949`
- `ntdll!RtlCopySid` at `0x180049ce6`
- `ntdll!RtlCopySid` at `0x18004ac50`
- `ntdll!RtlCopySid` at `0x180049949`
- `ntdll!RtlCopySid` at `0x180049ce6`
- `ntdll!RtlCopySid` at `0x18004ac50`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x18004abd1`
- `ntdll!RtlIsParentOfChildAppContainer` at `0x18004abd1`
- `ntdll!RtlFreeHeap` at `0x18004a7ab`
- `ntdll!RtlFreeHeap` at `0x18004a7c2`
- `ntdll!RtlFreeHeap` at `0x18004a7ab`
- `ntdll!RtlFreeHeap` at `0x18004a7c2`
- `ntdll!NtOpenProcessToken` at `0x18004ad10`
- `ntdll!NtOpenProcessToken` at `0x18004ad10`
- `ntdll!RtlAllocateHeap` at `0x180049868`
- `ntdll!RtlAllocateHeap` at `0x1800498b6`
- `ntdll!RtlAllocateHeap` at `0x180049cc5`
- `ntdll!RtlAllocateHeap` at `0x180049db6`
- `ntdll!RtlAllocateHeap` at `0x18004a297`
- `ntdll!RtlAllocateHeap` at `0x180049868`
- `ntdll!RtlAllocateHeap` at `0x1800498b6`
- `ntdll!RtlAllocateHeap` at `0x180049cc5`
- `ntdll!RtlAllocateHeap` at `0x180049db6`
- `ntdll!RtlAllocateHeap` at `0x18004a297`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x18004a3a3`
- `ext-ms-win-security-capauthz-l1-1-1!QueryApplicationCapabilitiesEx` at `0x18004a3a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800499c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800499c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049b9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004a569`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004bc76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180049b9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004a569`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004bc76`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800499ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180049a3e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004a021`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004a113`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004a748`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004aec9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004b936`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004ba54`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800499ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180049a3e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004a021`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004a113`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004a748`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004aec9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004b936`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004ba54`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049e99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049eb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049fec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a005`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a322`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a33f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a6a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a6be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a6d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a6f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a709`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a722`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a735`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004aaa8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004aac5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004afb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004afd2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b2ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b30b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b400`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b41d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b611`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b62e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b72f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b74c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b901`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b91a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004ba17`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004ba34`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049e99`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049eb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180049fec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a005`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a322`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a33f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a6a5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a6be`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a6d7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a6f0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a709`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a722`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004a735`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004aaa8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004aac5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004afb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004afd2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b2ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b30b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b400`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b41d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b611`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b62e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b72f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b74c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b901`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004b91a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004ba17`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004ba34`

## string_xrefs

- `0x180049a19`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180049e37`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180049e72`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180049ee5`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180049fc5`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004a0e9`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004a1eb`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004a67c`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004a8e3`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004a9af`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004aa7b`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004ad33`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004ae9c`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004af8a`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004b14b`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004b207`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004b2c0`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004b3d7`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004b4e2`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004b5e3`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004b704`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004b7bf`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004b7df`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004b8d7`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004b9e9`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004baeb`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x18004bcbc`: `onecore\base\appmodel\processcreation\src\createprocessextensions.cpp`
- `0x180049fa5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18004a544`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18004bc88`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18004a0d3`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x18004a1d0`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x180049d37`: `%windir%\system32`
- `0x1800499fe`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-manager.hpp`

## pseudocode

```c
__int64 __fastcall CreateProcessExtensions::PreCreationExtension(
        HANDLE TokenHandle,
        struct Common::COMMON_STRING *a2,
        struct _SECURITY_CAPABILITIES *a3,
        struct CreateProcessExtensions::ErrorContext *a4,
        struct _APPX_PROCESS_CONTEXT **a5)
{
  int v5; // r12d
  HANDLE v7; // rsi
  wil::TraceLoggingProvider *v8; // rax
  __int64 v9; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v10; // rcx
  int EffectivePackageMoniker; // eax
  unsigned __int64 v12; // rdx
  unsigned int HResultFromLastError; // ebx
  PVOID ProcessHeap; // rcx
  struct _APPX_PROCESS_CONTEXT *Heap; // rax
  struct _APPX_PROCESS_CONTEXT *v16; // r13
  PVOID v17; // rcx
  _QWORD *v18; // rax
  _DWORD *v19; // rbx
  _WORD *v20; // r14
  __int64 v21; // rcx
  int v22; // eax
  PSID v23; // rdi
  void *v24; // r15
  unsigned int v25; // edi
  __int64 v26; // r8
  __int64 v27; // rcx
  bool v28; // di
  signed int PackagePath_Internal; // esi
  __int64 v30; // rsi
  int v31; // eax
  bool v32; // r15
  int v33; // eax
  __int64 v34; // rcx
  int v35; // eax
  WCHAR *v36; // rsi
  int v37; // eax
  HKEY v38; // rcx
  PSID v39; // r15
  ULONG v40; // eax
  PVOID v41; // rcx
  ULONG v42; // esi
  PVOID v43; // rdi
  NTSTATUS v44; // eax
  __int64 v45; // rcx
  bool v46; // zf
  unsigned int Status; // r15d
  NTSTATUS v48; // eax
  void *v49; // rax
  SIZE_T v50; // r8
  WCHAR *v51; // rsi
  NTSTATUS v52; // eax
  const unsigned __int16 *v53; // rdx
  int v54; // r9d
  __int64 v55; // rcx
  __int64 v56; // rcx
  unsigned __int64 v57; // rdx
  unsigned __int8 v58; // cl
  __int64 v59; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  unsigned __int64 v64; // rdx
  unsigned __int8 v65; // cl
  __int64 v66; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v67; // rcx
  __int64 v69; // rdx
  __int64 v70; // rcx
  void *v71; // rcx
  unsigned __int64 v72; // rdx
  unsigned __int8 v73; // cl
  __int64 v74; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v75; // rcx
  HANDLE v76; // rcx
  HKEY v77; // rcx
  WCHAR *v78; // rsi
  void *v79; // rax
  SIZE_T v80; // r8
  WCHAR *v81; // rax
  __int64 v82; // rcx
  WCHAR *v83; // rax
  unsigned int v84; // eax
  __int64 v85; // rcx
  __int64 v86; // rcx
  void *v87; // rsi
  int v88; // eax
  unsigned int *v89; // r8
  DWORD v90; // r13d
  int v91; // eax
  char v92; // dl
  int v93; // ecx
  DWORD v94; // eax
  unsigned int v95; // r8d
  int v96; // r9d
  void *v97; // r13
  unsigned int v98; // r8d
  int v99; // r9d
  unsigned int v100; // r8d
  int v101; // r9d
  struct CreateProcessExtensions::ErrorContext *v102; // r13
  ARI::CreateProcessExtensions *v103; // r13
  struct _APPX_PROCESS_CONTEXT *v104; // rcx
  int v105; // eax
  char v106; // al
  __int64 v107; // rcx
  struct CreateProcessExtensions::ErrorContext *v108; // rax
  PVOID v109; // r15
  const unsigned __int16 *v110; // r8
  PVOID v111; // rdx
  int ContextForChildProcess; // eax
  unsigned int v113; // r12d
  struct _APPX_PROCESS_CONTEXT *v114; // rcx
  _QWORD **v115; // rax
  _QWORD *v116; // rax
  unsigned __int64 v117; // rdx
  unsigned __int8 v118; // cl
  void *v119; // rdx
  __int64 v120; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v121; // rcx
  const char *v122; // r9
  signed int LastError; // eax
  __int64 v124; // rcx
  __int64 v125; // rcx
  __int64 v126; // rcx
  __int64 v127; // rcx
  __int64 v128; // rcx
  __int64 v129; // rcx
  __int64 v130; // rcx
  __int64 v131; // rcx
  unsigned __int64 v132; // rdx
  unsigned __int8 v133; // cl
  __int64 v134; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v135; // rcx
  unsigned int v136; // r12d
  unsigned int i; // r15d
  unsigned int v138; // r15d
  unsigned __int64 v139; // rdx
  unsigned __int8 v140; // cl
  __int64 v141; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v142; // rcx
  unsigned __int64 v143; // rdx
  unsigned __int8 v144; // cl
  void *v145; // rdx
  __int64 v146; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v147; // rcx
  signed int v148; // eax
  __int64 v149; // rcx
  __int64 v150; // rcx
  NTSTATUS v151; // eax
  int AppContainerSidType; // eax
  void *v153; // rcx
  ULONG v154; // eax
  ULONG v155; // esi
  HANDLE v156; // rcx
  void *v157; // r15
  NTSTATUS v158; // eax
  unsigned int v159; // esi
  unsigned __int64 v160; // rdx
  unsigned __int8 v161; // cl
  void *v162; // rdx
  __int64 v163; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v164; // rcx
  NTSTATUS v165; // eax
  void *v166; // rcx
  unsigned __int64 v167; // rdx
  unsigned __int8 v168; // cl
  __int64 v169; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v170; // rcx
  unsigned __int64 v171; // rdx
  unsigned __int8 v172; // cl
  __int64 v173; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v174; // rcx
  __int64 v175; // rcx
  unsigned __int64 v176; // rdx
  unsigned __int8 v177; // cl
  __int64 v178; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v179; // rcx
  HANDLE v180; // rcx
  bool v181; // sf
  __int64 v182; // rcx
  __int64 v183; // rcx
  unsigned __int64 v184; // rdx
  unsigned __int8 v185; // cl
  __int64 v186; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v187; // rcx
  unsigned __int64 v188; // rdx
  unsigned __int8 v189; // cl
  void *v190; // rdx
  __int64 v191; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v192; // rcx
  unsigned __int64 v193; // rdx
  unsigned __int8 v194; // cl
  void *v195; // rdx
  __int64 v196; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v197; // rcx
  unsigned __int64 v198; // rdx
  unsigned __int8 v199; // cl
  __int64 v200; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v201; // rcx
  HANDLE v202; // rcx
  __int64 v203; // rcx
  __int64 v204; // rcx
  unsigned __int64 v205; // rdx
  unsigned __int8 v206; // cl
  __int64 v207; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v208; // rcx
  __int64 v209; // rdx
  __int64 v210; // rcx
  __int64 v211; // rcx
  void *v212; // rcx
  PVOID v213; // rcx
  unsigned __int64 v214; // rdx
  __int64 v215; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v216; // rcx
  unsigned __int64 v217; // rdx
  unsigned __int8 v218; // cl
  __int64 v219; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v220; // rcx
  Common *v221; // rcx
  unsigned __int64 v222; // rdx
  unsigned __int8 v223; // cl
  __int64 v224; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v225; // rcx
  PVOID v226; // rcx
  unsigned __int8 v227; // cl
  __int64 v228; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v229; // rcx
  __int64 v230; // rcx
  __int64 v231; // rcx
  unsigned __int64 v232; // rdx
  unsigned __int8 v233; // cl
  __int64 v234; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v235; // rcx
  __int64 v236; // rcx
  __int64 v237; // rcx
  unsigned __int64 v238; // rdx
  unsigned __int8 v239; // cl
  void *v240; // rdx
  __int64 v241; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v242; // rcx
  __int64 v243; // rcx
  __int64 v244; // rcx
  __int64 v245; // rcx
  unsigned __int64 v246; // rdx
  unsigned __int8 v247; // cl
  __int64 v248; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v249; // rcx
  __int64 v250; // rcx
  __int64 v251; // rcx
  __int64 v252; // rcx
  LSTATUS v253; // eax
  __int64 v254; // rcx
  __int64 v255; // rcx
  unsigned __int64 v256; // rdx
  unsigned __int8 v257; // cl
  __int64 v258; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v259; // rcx
  unsigned __int64 v260; // rdx
  unsigned __int8 v261; // cl
  __int64 v262; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v263; // rcx
  unsigned __int64 v264; // rdx
  unsigned __int8 v265; // cl
  __int64 v266; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v267; // rcx
  unsigned __int64 v268; // rdx
  unsigned __int8 v269; // cl
  void *v270; // rdx
  __int64 v271; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v272; // rcx
  unsigned __int64 v273; // rdx
  unsigned __int8 v274; // cl
  void *v275; // rdx
  __int64 v276; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v277; // rcx
  unsigned __int64 v278; // rdx
  unsigned __int8 v279; // cl
  void *v280; // rdx
  __int64 v281; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v282; // rcx
  unsigned __int64 v283; // rdx
  unsigned __int8 v284; // cl
  void *v285; // rdx
  __int64 v286; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v287; // rcx
  unsigned int v288; // r15d
  PSID v289; // rcx
  unsigned __int64 v290; // rdx
  unsigned __int8 v291; // cl
  void *v292; // rdx
  __int64 v293; // rcx
  AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry *v294; // rcx
  bool *ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengthg; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  int ReturnLengthb; // [rsp+20h] [rbp-E0h]
  int ReturnLengthc; // [rsp+20h] [rbp-E0h]
  int ReturnLengthh; // [rsp+20h] [rbp-E0h]
  int ReturnLengthi; // [rsp+20h] [rbp-E0h]
  unsigned int ReturnLengthd; // [rsp+20h] [rbp-E0h]
  void **ReturnLengthe; // [rsp+20h] [rbp-E0h]
  int ReturnLengthf; // [rsp+20h] [rbp-E0h]
  void **v305; // [rsp+30h] [rbp-D0h]
  unsigned int v306; // [rsp+38h] [rbp-C8h]
  bool v307; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v309; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-88h]
  HLOCAL v311; // [rsp+80h] [rbp-80h] BYREF
  PSID v312; // [rsp+88h] [rbp-78h]
  __int64 v313; // [rsp+90h] [rbp-70h] BYREF
  __int64 v314; // [rsp+98h] [rbp-68h] BYREF
  struct _APPX_PROCESS_CONTEXT *v315; // [rsp+A0h] [rbp-60h]
  int v316; // [rsp+A8h] [rbp-58h] BYREF
  char v317; // [rsp+ACh] [rbp-54h] BYREF
  WCHAR *v318; // [rsp+B0h] [rbp-50h]
  PVOID P[2]; // [rsp+B8h] [rbp-48h] BYREF
  int v320; // [rsp+C8h] [rbp-38h]
  int v321; // [rsp+D0h] [rbp-30h]
  WCHAR *v322; // [rsp+D8h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v324; // [rsp+E8h] [rbp-18h] BYREF
  ULONG Length; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int v326; // [rsp+F4h] [rbp-Ch] BYREF
  unsigned int v327; // [rsp+F8h] [rbp-8h] BYREF
  void **v328; // [rsp+FCh] [rbp-4h] BYREF
  DWORD cbData; // [rsp+104h] [rbp+4h] BYREF
  HANDLE TokenHandlea; // [rsp+108h] [rbp+8h] BYREF
  PVOID v331[2]; // [rsp+110h] [rbp+10h] BYREF
  int v332; // [rsp+120h] [rbp+20h]
  BYTE Data[4]; // [rsp+128h] [rbp+28h] BYREF
  int v334; // [rsp+12Ch] [rbp+2Ch] BYREF
  int v335; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v336[2]; // [rsp+134h] [rbp+34h] BYREF
  int v337; // [rsp+138h] [rbp+38h] BYREF
  bool v338[4]; // [rsp+13Ch] [rbp+3Ch] BYREF
  LPWCH penv; // [rsp+140h] [rbp+40h] BYREF
  ULONG v340; // [rsp+148h] [rbp+48h] BYREF
  ULONG v341; // [rsp+14Ch] [rbp+4Ch] BYREF
  struct _UNICODE_STRING Destination; // [rsp+150h] [rbp+50h] BYREF
  __int128 v343; // [rsp+160h] [rbp+60h] BYREF
  __int64 v344; // [rsp+170h] [rbp+70h]
  __int64 v345; // [rsp+178h] [rbp+78h]
  __int64 v346; // [rsp+180h] [rbp+80h]
  __int64 v347; // [rsp+188h] [rbp+88h]
  __int64 v348; // [rsp+190h] [rbp+90h]
  __int64 v349; // [rsp+198h] [rbp+98h]
  __int128 v350; // [rsp+1A0h] [rbp+A0h]
  int v351; // [rsp+1B0h] [rbp+B0h]
  __int64 v352; // [rsp+1B8h] [rbp+B8h]
  __int64 v353; // [rsp+1C0h] [rbp+C0h]
  __int64 v354; // [rsp+1D0h] [rbp+D0h] BYREF
  struct CreateProcessExtensions::ErrorContext *v355; // [rsp+1D8h] [rbp+D8h]
  _QWORD v356[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 *v357; // [rsp+1F0h] [rbp+F0h]
  __int64 v358; // [rsp+1F8h] [rbp+F8h] BYREF
  char v359; // [rsp+200h] [rbp+100h]
  struct _APPX_PROCESS_CONTEXT **v360; // [rsp+208h] [rbp+108h]
  struct _UNICODE_STRING DestinationString; // [rsp+210h] [rbp+110h] BYREF
  __int128 v362; // [rsp+220h] [rbp+120h] BYREF
  char v363[72]; // [rsp+230h] [rbp+130h] BYREF
  PSID Sid; // [rsp+278h] [rbp+178h]
  __int64 v365; // [rsp+280h] [rbp+180h]
  _BYTE pSid2[80]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v367[80]; // [rsp+2E0h] [rbp+1E0h] BYREF
  PSID SourceSid[10]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE DestinationSid[80]; // [rsp+380h] [rbp+280h] BYREF
  PSID TokenInformation[12]; // [rsp+3D0h] [rbp+2D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+378h]

  v5 = 0;
  v360 = a5;
  hObject = 0;
  v355 = a4;
  TokenHandlea = TokenHandle;
  v7 = TokenHandle;
  v8 = (wil::TraceLoggingProvider *)wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
                                      TokenHandle,
                                      _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
  if ( wil::TraceLoggingProvider::IsEnabled_(v8, 0, 0) )
  {
    wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
      v9,
      _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
    AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Start_(v10);
  }
  *((_DWORD *)a4 + 1) = 200;
  if ( !v7 )
  {
    v165 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xBu, &hObject);
    if ( v165 < 0 )
    {
      BaseSetLastNTError((unsigned int)v165);
      HResultFromLastError = Common::GetHResultFromLastError(v221);
      if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v223, v222) )
      {
        wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
          v224,
          _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
        AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v225);
      }
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return HResultFromLastError;
    }
    v7 = hObject;
    TokenHandlea = hObject;
  }
  v332 = 0;
  v316 = 0;
  v317 = 0;
  LOBYTE(v313) = 0;
  *(_OWORD *)v331 = 0;
  v320 = 0;
  *(_OWORD *)P = 0;
  EffectivePackageMoniker = VerifyParametersAndGetEffectivePackageMoniker(
                              v7,
                              (__int64)P,
                              (__int64)&v316 + 3,
                              (__int64)&v316,
                              (__int64)&v317,
                              (__int64)&v316 + 2,
                              (__int64)&v313,
                              (__int64)&v316 + 1);
  HResultFromLastError = EffectivePackageMoniker;
  if ( EffectivePackageMoniker < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E9,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)(unsigned int)EffectivePackageMoniker,
      (int)ReturnLength);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    v218 = (unsigned __int8)v331[1];
    if ( v331[1] )
      Common::GlobalHeap::Free(v331[1]);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v218, v217) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v219,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v220);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      return HResultFromLastError;
    }
    return HResultFromLastError;
  }
  if ( !LODWORD(v331[0]) )
  {
    v226 = P[1];
    *a5 = 0;
    if ( v226 )
      Common::GlobalHeap::Free(v226);
    v227 = (unsigned __int8)v331[1];
    if ( v331[1] )
      Common::GlobalHeap::Free(v331[1]);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v227, v12) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v228,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v229);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 0;
  }
  ProcessHeap = ReservedForLocalUse::g_heap;
  v312 = 0;
  v318 = 0;
  v322 = 0;
  v337 = 0;
  *(_DWORD *)v336 = 0;
  v309 = 0;
  v327 = 0;
  v311 = 0;
  v328 = 0;
  hMem = 0;
  *(_DWORD *)v338 = 0;
  if ( !ReservedForLocalUse::g_heap )
  {
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    ReservedForLocalUse::g_heap = ProcessHeap;
  }
  Heap = (struct _APPX_PROCESS_CONTEXT *)RtlAllocateHeap(ProcessHeap, 0, 0x60u);
  v315 = Heap;
  v16 = Heap;
  if ( !Heap )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x306,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)0x8007000ELL,
      (int)ReturnLength);
    Common::GlobalHeap::Free(0);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(0);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    v199 = (unsigned __int8)v331[1];
    if ( v331[1] )
      Common::GlobalHeap::Free(v331[1]);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v199, v198) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v200,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v201);
    }
    v202 = hObject;
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return 2147942414LL;
LABEL_357:
    CloseHandle(v202);
    return 2147942414LL;
  }
  memset_0(Heap, 0, 0x60u);
  v17 = ReservedForLocalUse::g_heap;
  if ( !ReservedForLocalUse::g_heap )
  {
    v17 = NtCurrentPeb()->ProcessHeap;
    ReservedForLocalUse::g_heap = v17;
  }
  v18 = RtlAllocateHeap(v17, 0, 0x18u);
  v19 = v18;
  if ( !v18 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30B,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)0x8007000ELL,
      (int)ReturnLength);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(0);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    v213 = v331[1];
    if ( !v331[1] )
    {
LABEL_354:
      if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled((unsigned __int8)v213, v214) )
      {
        wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
          v215,
          _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
        AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v216);
      }
      v202 = hObject;
      if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
        return 2147942414LL;
      goto LABEL_357;
    }
LABEL_353:
    Common::GlobalHeap::Free(v213);
    goto LABEL_354;
  }
  *v18 = 0;
  v20 = v331[1];
  v18[2] = 0;
  v18[1] = 0;
  if ( (_BYTE)v313 )
  {
    v43 = 0;
    v321 = 0;
    Status = 87;
    goto LABEL_134;
  }
  if ( !v20 || !*v20 )
  {
    LODWORD(v24) = 87;
LABEL_75:
    v25 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x311,
            (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
            (const char *)(unsigned int)v24,
            (unsigned int)ReturnLength);
LABEL_76:
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(0);
    v58 = (unsigned __int8)P[1];
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    if ( v20 )
      Common::GlobalHeap::Free(v20);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v58, v57) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v59,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v60);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return v25;
  }
  v340 = 0;
  v21 = -6;
  if ( v7 )
    v21 = (__int64)v7;
  v22 = NtQueryInformationToken((HANDLE)v21, TokenUser, TokenInformation, 0x54u, &v340);
  if ( v22 < 0 || (v23 = TokenInformation[0], v22 = RtlCopySid(0x44u, DestinationSid, TokenInformation[0]), v22 < 0) )
  {
    v24 = (void *)RtlNtStatusToDosErrorNoTeb(v22);
    ARI::Internal::EtwGetPackageStatusForUserError((ARI::Internal *)v20, v53, v24, v54);
  }
  else
  {
    RtlLengthSid(v23);
    LODWORD(v24) = SRGetPackageStatusForUserSid(DestinationSid, v20, &v337);
    if ( ((unsigned int)v24 & 0x1FFF0000) == 0x70000 )
      LODWORD(v24) = (unsigned __int16)v24;
    Common::GlobalHeap::Free(0);
  }
  if ( (_DWORD)v24 )
    goto LABEL_75;
  v359 = 1;
  v314 = 0;
  v357 = &v314;
  v358 = 0;
  v25 = SRCacheManager_Open(0, &v358);
  if ( v359 )
  {
    v26 = *v357;
    *v357 = v358;
    if ( v26 )
      SRCacheManager_Close(v26);
  }
  if ( (v25 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-manager.hpp",
      (const char *)v25,
      (int)ReturnLength);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x314,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)v25,
      ReturnLengthg);
    v27 = v314;
    v314 = 0;
    if ( v27 )
      SRCacheManager_Close(v27);
    goto LABEL_76;
  }
  v344 = 0;
  v28 = 0;
  v343 = 0;
  v350 = 0;
  v307 = 0;
  v345 = 0;
  v346 = 0;
  v347 = 0;
  v348 = 0;
  v349 = 0;
  v351 = 0;
  v352 = 0;
  v353 = 0;
  v354 = 0;
  PackagePath_Internal = StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
                           (struct StateRepository::Cache::Manager_NoThrow *)&v314,
                           v20,
                           &v354);
  if ( PackagePath_Internal < 0 )
  {
    v69 = 1165;
LABEL_102:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v69,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)(unsigned int)PackagePath_Internal,
      (int)ReturnLength);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31B,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)(unsigned int)PackagePath_Internal,
      ReturnLengthh);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v343);
    v70 = v314;
    v314 = 0;
    if ( v70 )
      SRCacheManager_Close(v70);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    v71 = 0;
    goto LABEL_107;
  }
  if ( !v354 )
    goto LABEL_33;
  ReturnLength = &v307;
  PackagePath_Internal = StateRepository::Cache::Entity::Package_NoThrow::Get(&v314, v354, 2058, &v343);
  if ( PackagePath_Internal < 0 )
  {
    v69 = 1168;
    goto LABEL_102;
  }
  v28 = v307;
LABEL_33:
  if ( !v28 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31C,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)0x80070002LL,
      (int)ReturnLength);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v343);
    v175 = v314;
    v314 = 0;
    if ( v175 )
      SRCacheManager_Close(v175);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(0);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    Common::GlobalHeap::Free(v20);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v177, v176) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v178,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v179);
    }
    v180 = hObject;
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return 2147942402LL;
    goto LABEL_426;
  }
  v307 = 0;
  v362 = 0;
  memset_0(v363, 0, 0x44u);
  v30 = v344;
  Sid = 0;
  v365 = 0;
  if ( !v344 )
  {
    v25 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)0x80070057LL,
      (int)ReturnLength);
    goto LABEL_87;
  }
  v324 = 0;
  v31 = StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(
          (struct StateRepository::Cache::Manager_NoThrow *)&v314,
          v344,
          (struct StateRepository::Cache::Context_NoThrow *)&v324,
          &v307);
  v25 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v31,
      (int)ReturnLength);
    v107 = v324;
    v324 = 0;
    if ( v107 )
LABEL_161:
      SRCacheContext_Close();
LABEL_87:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x320,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)v25,
      ReturnLengthc);
    v61 = v365;
    v365 = 0;
    if ( v61 )
      SRCache_Free();
    v62 = *((_QWORD *)&v362 + 1);
    *((_QWORD *)&v362 + 1) = 0;
    if ( v62 )
      SRCache_Free();
    goto LABEL_91;
  }
  v32 = v307;
  if ( !v307 )
  {
    v254 = v324;
    v324 = 0;
    if ( v254 )
      SRCacheContext_Close();
    goto LABEL_412;
  }
  v33 = StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(&v324, &v362, 0, v30);
  v25 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v33,
      (int)ReturnLength);
    v255 = v324;
    v324 = 0;
    if ( !v255 )
      goto LABEL_87;
    goto LABEL_161;
  }
  v34 = v324;
  v324 = 0;
  if ( v34 )
    SRCacheContext_Close();
  if ( !v32 )
  {
LABEL_412:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x321,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)0x80070002LL,
      (int)ReturnLength);
    v243 = v365;
    v365 = 0;
    if ( v243 )
      SRCache_Free();
    v244 = *((_QWORD *)&v362 + 1);
    *((_QWORD *)&v362 + 1) = 0;
    if ( v244 )
      SRCache_Free();
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v343);
    v245 = v314;
    v314 = 0;
    if ( v245 )
      SRCacheManager_Close(v245);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(0);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    Common::GlobalHeap::Free(v20);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v247, v246) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v248,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v249);
    }
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return 2147942402LL;
    v180 = hObject;
LABEL_426:
    CloseHandle(v180);
    return 2147942402LL;
  }
  hKey = 0;
  penv = 0;
  v35 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &penv,
          L"%s\\%s",
          L"Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel\\Repository\\Packages",
          v20);
  v25 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x286,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)(unsigned int)v35,
      (int)ReturnLength);
    if ( penv )
      FreeEnvironmentStringsW(penv);
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    goto LABEL_69;
  }
  v36 = penv;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  hKey = 0;
  v37 = RegOpenKeyExInternalW(HKEY_LOCAL_MACHINE, v36, (PHANDLE)&hKey, 0);
  v25 = v37;
  if ( v37 > 0 )
    v25 = (unsigned __int16)v37 | 0x80070000;
  if ( (int)v25 <= -2147024895 || v25 + 2147024892 <= 0x7FF8FFFB )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
      (const char *)v25,
      ReturnLengtha);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x288,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)v25,
      ReturnLengthi);
    if ( v36 )
      FreeEnvironmentStringsW(v36);
    v77 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_69;
LABEL_466:
    RegCloseKey(v77);
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x323,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)v25,
      ReturnLengthb);
    v55 = v365;
    v365 = 0;
    if ( v55 )
      SRCache_Free();
    v56 = *((_QWORD *)&v362 + 1);
    *((_QWORD *)&v362 + 1) = 0;
    if ( v56 )
      SRCache_Free();
LABEL_91:
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v343);
    v63 = v314;
    v314 = 0;
    if ( v63 )
      SRCacheManager_Close(v63);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(0);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    Common::GlobalHeap::Free(v20);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v65, v64) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v66,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v67);
    }
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return v25;
    CloseHandle(hObject);
    return v25;
  }
  v38 = hKey;
  v321 = 0;
  if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( v36 )
    {
      FreeEnvironmentStringsW(v36);
      v38 = hKey;
    }
    if ( (unsigned __int64)v38 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_52;
LABEL_460:
    RegCloseKey(v38);
    goto LABEL_52;
  }
  *(_DWORD *)Data = 0;
  cbData = 4;
  v253 = RegQueryValueExW(hKey, L"FullTrust", 0, 0, Data, &cbData);
  v25 = v253;
  if ( v253 > 0 )
    v25 = (unsigned __int16)v253 | 0x80070000;
  if ( (int)v25 <= -2147024895 || v25 + 2147024892 <= 0x7FF8FFFB )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x290,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)v25,
      ReturnLengtha);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::RtlFreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&penv);
    v77 = hKey;
    if ( (unsigned __int64)hKey - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_69;
    goto LABEL_466;
  }
  if ( (v25 & 0x80000000) == 0 )
  {
    if ( *(_DWORD *)Data == 1 )
      v321 = 1;
    if ( v36 )
      FreeEnvironmentStringsW(v36);
    v38 = hKey;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_460;
  }
  else
  {
    if ( v36 )
      FreeEnvironmentStringsW(v36);
    v38 = hKey;
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_460;
  }
LABEL_52:
  v39 = Sid;
  v5 = BYTE4(v345) & 1;
  RtlSetLastWin32Error(0);
  v40 = RtlLengthSid(v39);
  v41 = ReservedForLocalUse::g_heap;
  v42 = v40;
  if ( !ReservedForLocalUse::g_heap )
  {
    v41 = NtCurrentPeb()->ProcessHeap;
    ReservedForLocalUse::g_heap = v41;
  }
  v43 = RtlAllocateHeap(v41, 0, v40);
  if ( !v43 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32A,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)0x8007000ELL,
      ReturnLengtha);
    v250 = v365;
    v365 = 0;
    if ( v250 )
      SRCache_Free();
    v251 = *((_QWORD *)&v362 + 1);
    *((_QWORD *)&v362 + 1) = 0;
    if ( v251 )
      SRCache_Free();
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v343);
    v252 = v314;
    v314 = 0;
    if ( v252 )
      SRCacheManager_Close(v252);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    v212 = 0;
    goto LABEL_350;
  }
  Common::GlobalHeap::Free(0);
  v44 = RtlCopySid(v42, v43, v39);
  if ( v44 < 0 )
  {
    BaseSetLastNTError((unsigned int)v44);
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x32B,
                  (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                  v122);
    v124 = v365;
    v365 = 0;
    PackagePath_Internal = LastError;
    if ( v124 )
      SRCache_Free();
    v125 = *((_QWORD *)&v362 + 1);
    *((_QWORD *)&v362 + 1) = 0;
    if ( v125 )
      SRCache_Free();
    v126 = v352;
    v352 = 0;
    if ( v126 )
      SRCache_Free();
    v127 = *((_QWORD *)&v350 + 1);
    *((_QWORD *)&v350 + 1) = 0;
    if ( v127 )
      SRCache_Free();
    v128 = v350;
    *(_QWORD *)&v350 = 0;
    if ( v128 )
      SRCache_Free();
    v129 = v349;
    v349 = 0;
    if ( v129 )
      SRCache_Free();
    v130 = *((_QWORD *)&v343 + 1);
    *((_QWORD *)&v343 + 1) = 0;
    if ( v130 )
      SRCache_Free();
    v131 = v314;
    v314 = 0;
    if ( v131 )
      SRCacheManager_Close(v131);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    if ( P[1] )
      RtlFreeHeap(ReservedForLocalUse::g_heap, 0, P[1]);
    RtlFreeHeap(ReservedForLocalUse::g_heap, 0, v20);
LABEL_196:
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v133, v132) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v134,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v135);
    }
    v76 = hObject;
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return (unsigned int)PackagePath_Internal;
    goto LABEL_113;
  }
  v46 = (_BYTE)v316 == 0;
  Status = 87;
  *(_QWORD *)v19 = v43;
  if ( v46 )
    goto LABEL_129;
  if ( v351 != 12 || (v334 = 0, RtlGetDeviceFamilyInfoEnum(0, &v334, 0), v334 != 5) )
  {
    LODWORD(v51) = (_DWORD)v318;
    goto LABEL_119;
  }
  DestinationString = 0;
  Destination = 0;
  RtlInitUnicodeString(&DestinationString, L"%windir%\\system32");
  Length = 0;
  Destination = 0;
  v48 = RtlExpandEnvironmentStrings_U(0, &DestinationString, &Destination, &Length);
  PackagePath_Internal = v48;
  if ( !v48 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33F,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)0x8000FFFFLL,
      ReturnLengtha);
    v230 = v365;
    v365 = 0;
    if ( v230 )
      SRCache_Free();
    v231 = *((_QWORD *)&v362 + 1);
    *((_QWORD *)&v362 + 1) = 0;
    if ( v231 )
      SRCache_Free();
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v343);
    wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v314, 0);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    Common::GlobalHeap::Free(v20);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v233, v232) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v234,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v235);
    }
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return 2147549183LL;
    goto LABEL_340;
  }
  if ( v48 != -1073741789 )
  {
    if ( v48 > 0 )
      PackagePath_Internal = (unsigned __int16)v48 | 0x80070000;
    if ( PackagePath_Internal < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x340,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
        (const char *)(unsigned int)PackagePath_Internal,
        ReturnLengtha);
    v236 = v365;
    v365 = 0;
    if ( v236 )
      SRCache_Free();
    v237 = *((_QWORD *)&v362 + 1);
    *((_QWORD *)&v362 + 1) = 0;
    if ( v237 )
      SRCache_Free();
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v343);
    wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v314, 0);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    v71 = v43;
LABEL_107:
    Common::GlobalHeap::Free(v71);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    Common::GlobalHeap::Free(v20);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v73, v72) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v74,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v75);
    }
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return (unsigned int)PackagePath_Internal;
    v76 = hObject;
LABEL_113:
    CloseHandle(v76);
    return (unsigned int)PackagePath_Internal;
  }
  is_mul_ok(Length, 2u);
  v49 = ReservedForLocalUse::GetHeap((ReservedForLocalUse *)Length);
  v318 = (WCHAR *)RtlAllocateHeap(v49, 0, v50);
  v51 = v318;
  if ( !v318 )
  {
    v209 = 835;
LABEL_343:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v209,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)0x8007000ELL,
      ReturnLengtha);
    v210 = v365;
    v365 = 0;
    if ( v210 )
      SRCache_Free();
    v211 = *((_QWORD *)&v362 + 1);
    *((_QWORD *)&v362 + 1) = 0;
    if ( v211 )
      SRCache_Free();
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v343);
    wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v314, 0);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    v212 = v43;
LABEL_350:
    Common::GlobalHeap::Free(v212);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    v213 = v20;
    goto LABEL_353;
  }
  Common::GlobalHeap::Free(0);
  v322 = v51;
  *(_QWORD *)&Destination.Length = 0;
  Destination.Buffer = v51;
  *(_DWORD *)&Destination.MaximumLength = (unsigned __int16)(2 * Length);
  v52 = RtlExpandEnvironmentStrings_U(0, &DestinationString, &Destination, &Length);
  if ( v52 < 0 )
  {
    v148 = wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x345,
             (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
             (const char *)(unsigned int)v52,
             ReturnLengtha);
LABEL_228:
    v149 = v365;
    PackagePath_Internal = v148;
    v365 = 0;
    if ( v149 )
      SRCache_Free();
    v150 = *((_QWORD *)&v362 + 1);
    *((_QWORD *)&v362 + 1) = 0;
    if ( v150 )
      SRCache_Free();
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v343);
    wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v314, 0);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(v318);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    Common::GlobalHeap::Free(v20);
    goto LABEL_196;
  }
  *((_QWORD *)v16 + 2) = v51;
LABEL_119:
  if ( !*((_QWORD *)v16 + 2) )
  {
    v326 = 0;
    ReturnLengtha = (int)v51;
    LOBYTE(v45) = 1;
    PackagePath_Internal = ARI::GetPackagePath_Internal(v45, v20, 2, &v326);
    if ( PackagePath_Internal )
    {
      if ( PackagePath_Internal != 122 )
      {
        v181 = PackagePath_Internal < 0;
        if ( PackagePath_Internal > 0 )
        {
          PackagePath_Internal = (unsigned __int16)PackagePath_Internal | 0x80070000;
          v181 = PackagePath_Internal < 0;
        }
        if ( v181 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x350,
            (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
            (const char *)(unsigned int)PackagePath_Internal,
            ReturnLengtha);
        v182 = v365;
        v365 = 0;
        if ( v182 )
          SRCache_Free();
        v183 = *((_QWORD *)&v362 + 1);
        *((_QWORD *)&v362 + 1) = 0;
        if ( v183 )
          SRCache_Free();
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v343);
        wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v314, 0);
        Common::GlobalHeap::Free(v19);
        Common::GlobalHeap::Free(v16);
        LocalFree(hMem);
        LocalFree(v311);
        LocalFree(v309);
        Common::GlobalHeap::Free(v318);
        Common::GlobalHeap::Free(0);
        if ( v312 )
          RtlFreeSid(v312);
        Common::GlobalHeap::Free(v43);
        if ( P[1] )
          Common::GlobalHeap::Free(P[1]);
        Common::GlobalHeap::Free(v20);
        if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v185, v184) )
        {
          wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
            v186,
            _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
          AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v187);
        }
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          CloseHandle(hObject);
          return (unsigned int)PackagePath_Internal;
        }
        return (unsigned int)PackagePath_Internal;
      }
      is_mul_ok(v326, 2u);
      v78 = 0;
      v79 = ReservedForLocalUse::GetHeap((ReservedForLocalUse *)v326);
      v81 = (WCHAR *)RtlAllocateHeap(v79, 0, v80);
      if ( v81 )
        v78 = v81;
      v83 = v318;
      if ( v318 != v78 )
      {
        Common::GlobalHeap::Free(v318);
        v83 = v78;
        v318 = v78;
        v322 = v78;
      }
      if ( v83 )
      {
        ReturnLengthd = (unsigned int)v83;
        LOBYTE(v82) = 1;
        v84 = ARI::GetPackagePath_Internal(v82, v20, 2, &v326);
        if ( !v84 )
        {
          *((_QWORD *)v16 + 2) = v318;
          goto LABEL_129;
        }
        v148 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x354,
                 (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
                 (const char *)v84,
                 ReturnLengthd);
        goto LABEL_228;
      }
      v209 = 851;
      goto LABEL_343;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34F,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)0x8000FFFFLL,
      ReturnLengtha);
    v203 = v365;
    v365 = 0;
    if ( v203 )
      SRCache_Free();
    v204 = *((_QWORD *)&v362 + 1);
    *((_QWORD *)&v362 + 1) = 0;
    if ( v204 )
      SRCache_Free();
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v343);
    wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v314, 0);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v16);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(v318);
    Common::GlobalHeap::Free(0);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    Common::GlobalHeap::Free(v20);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v206, v205) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v207,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v208);
    }
    if ( (char *)hObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      return 2147549183LL;
LABEL_340:
    CloseHandle(hObject);
    return 2147549183LL;
  }
LABEL_129:
  v85 = v365;
  v365 = 0;
  if ( v85 )
    SRCache_Free();
  v86 = *((_QWORD *)&v362 + 1);
  *((_QWORD *)&v362 + 1) = 0;
  if ( v86 )
    SRCache_Free();
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v343);
  wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v314, 0);
LABEL_134:
  v87 = 0;
  v306 = 0;
  v305 = (void **)((char *)&v328 + 4);
  ReturnLengthe = (void **)&v328;
  v88 = QueryApplicationCapabilitiesEx(v20, &v309, &v327, &v311);
  v90 = v88;
  if ( v88 == -2147024444 )
    goto LABEL_142;
  if ( v88 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36F,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
      (const char *)(unsigned int)v88,
      (int)&v328);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(v318);
    v166 = 0;
    goto LABEL_256;
  }
  v91 = v321;
  v92 = BYTE1(v316);
  if ( *(_DWORD *)v338 == 2 )
    v91 = 1;
  v321 = v91;
  v93 = (_DWORD)v328 + HIDWORD(v328) + (BYTE1(v316) != 0);
  v46 = v327 + v93 == 0;
  v19[4] = v327 + v93;
  if ( !v46 )
  {
    LOBYTE(v306) = v92;
    LODWORD(v305) = HIDWORD(v328);
    LODWORD(ReturnLengthe) = (_DWORD)v328;
    v94 = ReservedForLocalUse::ReallocateCapabilityArray(
            (ReservedForLocalUse *)(v19 + 2),
            (struct _SID_AND_ATTRIBUTES **)v309,
            (void **)v327,
            (unsigned int)v311,
            ReturnLengthe,
            (unsigned int)hMem,
            v305,
            v306,
            (bool)v338);
    v97 = (void *)*((_QWORD *)v19 + 1);
    cbData = v94;
    if ( v97 )
    {
      Common::GlobalHeap::Free(0);
      v87 = v97;
    }
    ReservedForLocalUse::FreeSidsInSidArray((ReservedForLocalUse *)v309, (void **)v327, v95, v96);
    ReservedForLocalUse::FreeSidsInSidArray((ReservedForLocalUse *)v311, (void **)(unsigned int)v328, v98, v99);
    ReservedForLocalUse::FreeSidsInSidArray((ReservedForLocalUse *)hMem, (void **)HIDWORD(v328), v100, v101);
    v90 = cbData;
    if ( (cbData & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x393,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
        (const char *)cbData,
        (int)ReturnLengthe);
      Common::GlobalHeap::Free(v19);
      Common::GlobalHeap::Free(v315);
      LocalFree(hMem);
      LocalFree(v311);
      LocalFree(v309);
      Common::GlobalHeap::Free(v318);
      v166 = v87;
LABEL_256:
      Common::GlobalHeap::Free(v166);
      if ( v312 )
        RtlFreeSid(v312);
      Common::GlobalHeap::Free(v43);
      v168 = (unsigned __int8)P[1];
      if ( P[1] )
        Common::GlobalHeap::Free(P[1]);
      if ( v20 )
        Common::GlobalHeap::Free(v20);
      if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v168, v167) )
      {
        wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
          v169,
          _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
        AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v170);
      }
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return v90;
    }
  }
LABEL_142:
  v102 = v355;
  *((_DWORD *)v355 + 1) = 300;
  if ( (v337 & 0x20) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(v318);
    Common::GlobalHeap::Free(v87);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    v172 = (unsigned __int8)P[1];
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    if ( v20 )
      Common::GlobalHeap::Free(v20);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v172, v171) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v173,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v174);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 2147958016LL;
  }
  if ( (v337 & 0x800) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v322);
    Common::GlobalHeap::Free(v87);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v331);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v257, v256) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v258,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v259);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 2147958031LL;
  }
  if ( (v337 & 0x4000307) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v322);
    Common::GlobalHeap::Free(v87);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v331);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v261, v260) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v262,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v263);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 2147958012LL;
  }
  if ( (v337 & 0x98) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v322);
    Common::GlobalHeap::Free(v87);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v331);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v265, v264) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v266,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v267);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 2147958106LL;
  }
  *((_DWORD *)v102 + 1) = 400;
  if ( !v20 || !*v20 || (Status = ARI::Internal::GetStatus((ARI::Internal *)v20, v336, v89)) != 0 )
  {
    v138 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3B1,
             (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
             (const char *)Status,
             (unsigned int)ReturnLengthe);
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(v318);
    Common::GlobalHeap::Free(v87);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    v140 = (unsigned __int8)P[1];
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    if ( v20 )
      Common::GlobalHeap::Free(v20);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v140, v139) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v141,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v142);
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return v138;
  }
  if ( (*(_DWORD *)v336 & 0x80000) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v322);
    Common::GlobalHeap::Free(v87);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v331);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v269, v268) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v271,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v272);
    }
    Common::CloseHandleHelper((Common *)hObject, v270);
    return 2147958016LL;
  }
  if ( (*(_DWORD *)v336 & 0x400000) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v322);
    Common::GlobalHeap::Free(v87);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v331);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v274, v273) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v276,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v277);
    }
    Common::CloseHandleHelper((Common *)hObject, v275);
    return 2147958031LL;
  }
  if ( (*(_DWORD *)v336 & 0x4000347) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v322);
    Common::GlobalHeap::Free(v87);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v331);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v279, v278) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v281,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v282);
    }
    Common::CloseHandleHelper((Common *)hObject, v280);
    return 2147958012LL;
  }
  if ( (v336[0] & 0x98) != 0 )
  {
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v322);
    Common::GlobalHeap::Free(v87);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v331);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v284, v283) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v286,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v287);
    }
    Common::CloseHandleHelper((Common *)hObject, v285);
    return 2147958106LL;
  }
  *((_DWORD *)v102 + 1) = 500;
  v103 = (ARI::CreateProcessExtensions *)TokenHandlea;
  if ( BYTE2(v316) == (_BYTE)Status )
    goto LABEL_154;
  v341 = 76;
  v335 = 0;
  v151 = NtQueryInformationToken(TokenHandlea, TokenAppContainerSid, SourceSid, 0x4Cu, &v341);
  if ( v151 < 0 )
  {
    v288 = v151 | 0x10000000;
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v322);
    Common::GlobalHeap::Free(v87);
    v289 = v312;
    if ( !v312 )
    {
LABEL_510:
      Common::GlobalHeap::Free(v43);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)P);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)v331);
      if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v291, v290) )
      {
        wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
          v293,
          _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
        AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v294);
      }
      Common::CloseHandleHelper((Common *)hObject, v292);
      return v288;
    }
LABEL_509:
    RtlFreeSid(v289);
    goto LABEL_510;
  }
  AppContainerSidType = RtlGetAppContainerSidType(SourceSid[0], &v335);
  if ( AppContainerSidType < 0 )
  {
    v288 = AppContainerSidType | 0x10000000;
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>::~AutoArray<unsigned short,&void Common::AutoArrayDeallocate<unsigned short>(unsigned short *)>(&v322);
    Common::GlobalHeap::Free(v87);
    v289 = v312;
    if ( !v312 )
      goto LABEL_510;
    goto LABEL_509;
  }
  v153 = *(void **)v19;
  if ( v335 == 1 )
  {
    if ( (unsigned __int8)RtlIsParentOfChildAppContainer(v153, SourceSid[0]) )
    {
      v19[4] = 0;
      *((_QWORD *)v19 + 1) = 0;
      Common::GlobalHeap::Free(v87);
      v154 = RtlLengthSid(SourceSid[0]);
      TokenHandlea = 0;
      v155 = v154;
      Common::GlobalHeap::Alloc(v154, &TokenHandlea);
      v156 = TokenHandlea;
      *(_QWORD *)v19 = TokenHandlea;
      if ( v156 )
      {
        Common::GlobalHeap::Free(v43);
        v157 = *(void **)v19;
        v43 = 0;
        if ( *(_QWORD *)v19 )
        {
          Common::GlobalHeap::Free(0);
          v43 = v157;
        }
        v158 = RtlCopySid(v155, *(PSID *)v19, SourceSid[0]);
        if ( v158 < 0 )
        {
          v159 = v158 | 0x10000000;
          Common::GlobalHeap::Free(v19);
          Common::GlobalHeap::Free(v315);
          LocalFree(hMem);
          LocalFree(v311);
          LocalFree(v309);
          Common::GlobalHeap::Free(v318);
          Common::GlobalHeap::Free(0);
          if ( v312 )
            RtlFreeSid(v312);
          Common::GlobalHeap::Free(v43);
          if ( P[1] )
            Common::GlobalHeap::Free(P[1]);
          Common::GlobalHeap::Free(v20);
          if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v161, v160) )
          {
            wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
              v163,
              _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
            AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v164);
          }
          Common::CloseHandleHelper((Common *)hObject, v162);
          return v159;
        }
        v87 = 0;
LABEL_154:
        v104 = v315;
        v105 = v321;
        *((_BYTE *)v315 + 80) &= ~1u;
        if ( *(_QWORD *)v19 )
        {
          if ( v105 )
            goto LABEL_162;
          if ( v87 )
          {
            if ( !(unsigned int)IgnoreProtectedAppProcess(v5) )
            {
              memset_0(v367, 0, 0x44u);
              memset_0(pSid2, 0, 0x44u);
              v356[0] = 1703960;
              v356[1] = L"protectedApp";
              if ( (int)RtlDeriveCapabilitySidsFromName(v356, v367, pSid2) >= 0 )
              {
                v136 = v19[4];
                for ( i = 0; i < v136; ++i )
                {
                  if ( EqualSid(*((PSID *)v87 + 2 * i), pSid2) )
                  {
                    v104 = v315;
                    *((_BYTE *)v315 + 80) |= 1u;
                    goto LABEL_156;
                  }
                }
              }
            }
            v104 = v315;
          }
        }
        else if ( v105 )
        {
          goto LABEL_162;
        }
LABEL_156:
        if ( HIBYTE(v316) )
          *(_QWORD *)v104 = v19;
        if ( !v317 )
        {
          v106 = 0;
          goto LABEL_163;
        }
LABEL_162:
        v106 = 4;
LABEL_163:
        *((_BYTE *)v104 + 80) &= ~4u;
        *((_BYTE *)v104 + 80) |= v106;
        v108 = v355;
        v109 = P[1];
        v110 = (const unsigned __int16 *)(unsigned __int8)v313;
        v111 = P[1];
        *((_QWORD *)v104 + 3) = v20;
        *((_DWORD *)v108 + 1) = 600;
        ContextForChildProcess = ARI::CreateProcessExtensions::LoadContextForChildProcess(
                                   v103,
                                   v111,
                                   v110,
                                   (int)v104,
                                   (struct _APPX_PROCESS_CONTEXT *)ReturnLengthe);
        v113 = ContextForChildProcess;
        if ( ContextForChildProcess < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x437,
            (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
            (const char *)(unsigned int)ContextForChildProcess,
            ReturnLengthf);
          Common::GlobalHeap::Free(v19);
          Common::GlobalHeap::Free(v315);
          LocalFree(hMem);
          LocalFree(v311);
          LocalFree(v309);
          Common::GlobalHeap::Free(v318);
          Common::GlobalHeap::Free(v87);
          if ( v312 )
            RtlFreeSid(v312);
          Common::GlobalHeap::Free(v43);
          if ( v109 )
            Common::GlobalHeap::Free(v109);
          Common::GlobalHeap::Free(v20);
          if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v144, v143) )
          {
            wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
              v146,
              _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
            AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v147);
          }
          Common::CloseHandleHelper((Common *)hObject, v145);
          return v113;
        }
        else
        {
          v114 = v315;
          *v360 = v315;
          CreateProcessExtensions::AcquireAppXContext(v114);
          v116 = *v115;
          if ( *v116 )
          {
            v43 = 0;
            v87 = 0;
            v19 = 0;
          }
          if ( v116[2] )
            v318 = 0;
          Common::GlobalHeap::Free(v19);
          Common::GlobalHeap::Free(0);
          LocalFree(hMem);
          LocalFree(v311);
          LocalFree(v309);
          Common::GlobalHeap::Free(v318);
          Common::GlobalHeap::Free(v87);
          if ( v312 )
            RtlFreeSid(v312);
          Common::GlobalHeap::Free(v43);
          if ( v109 )
            Common::GlobalHeap::Free(v109);
          if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v118, v117) )
          {
            wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
              v120,
              _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
            AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v121);
          }
          Common::CloseHandleHelper((Common *)hObject, v119);
          return 0;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F6,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\createprocessextensions.cpp",
        (const char *)0x8007000ELL,
        (int)ReturnLengthe);
      Common::GlobalHeap::Free(v19);
      Common::GlobalHeap::Free(v315);
      LocalFree(hMem);
      LocalFree(v311);
      LocalFree(v309);
      Common::GlobalHeap::Free(v318);
      Common::GlobalHeap::Free(0);
      if ( v312 )
        RtlFreeSid(v312);
      Common::GlobalHeap::Free(v43);
      if ( P[1] )
        Common::GlobalHeap::Free(P[1]);
      Common::GlobalHeap::Free(v20);
      if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v194, v193) )
      {
        wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
          v196,
          _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
        AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v197);
      }
      Common::CloseHandleHelper((Common *)hObject, v195);
      return 2147942414LL;
    }
    else
    {
      Common::GlobalHeap::Free(v19);
      Common::GlobalHeap::Free(v315);
      LocalFree(hMem);
      LocalFree(v311);
      LocalFree(v309);
      Common::GlobalHeap::Free(v318);
      Common::GlobalHeap::Free(v87);
      if ( v312 )
        RtlFreeSid(v312);
      Common::GlobalHeap::Free(v43);
      if ( P[1] )
        Common::GlobalHeap::Free(P[1]);
      Common::GlobalHeap::Free(v20);
      if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v239, v238) )
      {
        wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
          v241,
          _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
        AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v242);
      }
      Common::CloseHandleHelper((Common *)hObject, v240);
      return 2147549183LL;
    }
  }
  else
  {
    if ( RtlEqualSid(v153, SourceSid[0]) )
      goto LABEL_154;
    Common::GlobalHeap::Free(v19);
    Common::GlobalHeap::Free(v315);
    LocalFree(hMem);
    LocalFree(v311);
    LocalFree(v309);
    Common::GlobalHeap::Free(v318);
    Common::GlobalHeap::Free(v87);
    if ( v312 )
      RtlFreeSid(v312);
    Common::GlobalHeap::Free(v43);
    if ( P[1] )
      Common::GlobalHeap::Free(P[1]);
    Common::GlobalHeap::Free(v20);
    if ( AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::IsEnabled(v189, v188) )
    {
      wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(
        v191,
        _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_);
      AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Stop_(v192);
    }
    Common::CloseHandleHelper((Common *)hObject, v190);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800496e0  push    rbp
0x1800496e2  push    rbx
0x1800496e3  push    rsi
0x1800496e4  push    rdi
0x1800496e5  push    r12
0x1800496e7  push    r14
0x1800496e9  push    r15
0x1800496eb  lea     rbp, [rsp-340h]
0x1800496f3  sub     rsp, 440h
0x1800496fa  mov     rax, cs:__security_cookie
0x180049701  xor     rax, rsp
0x180049704  mov     [rbp+370h+var_40], rax
0x18004970b  mov     r15, [rbp+370h+arg_20]
0x180049712  mov     rdi, rdx
0x180049715  xor     r12d, r12d
0x180049718  mov     [rbp+370h+var_268], r15
0x18004971f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_234fc6f01c94939abb1aa6f0961130da_@@CA@XZ; _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_(void)
0x180049726  mov     [rsp+470h+hObject], r12
0x18004972b  mov     r14, r9
0x18004972e  mov     [rbp+370h+var_298], r9
0x180049735  mov     rbx, r8
0x180049738  mov     [rbp+370h+TokenHandle], rcx
0x18004973c  mov     rsi, rcx
0x18004973f  call    ?get@?$static_lazy@VAppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@@details@wil@@QEAAPEAVAppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@P6AXXZ@Z; wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(void (*)(void))
0x180049744  xor     r8d, r8d; unsigned __int64
0x180049747  xor     edx, edx; unsigned __int8
0x180049749  mov     rcx, rax; this
0x18004974c  call    ?IsEnabled_@TraceLoggingProvider@wil@@IEBA_NE_K@Z; wil::TraceLoggingProvider::IsEnabled_(uchar,unsigned __int64)
0x180049751  test    al, al
0x180049753  jz      short loc_180049766
0x180049755  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_234fc6f01c94939abb1aa6f0961130da_@@CA@XZ; _lambda_234fc6f01c94939abb1aa6f0961130da_::_lambda_invoker_cdecl_(void)
0x18004975c  call    ?get@?$static_lazy@VAppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@@details@wil@@QEAAPEAVAppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@P6AXXZ@Z; wil::details::static_lazy<AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry>::get(void (*)(void))
0x180049761  call    ?PreCreationExtension_Start_@AppxCreateProcessExtensionsTelemetry@AppxCreateProcessExtensions@@QEAAXXZ; AppxCreateProcessExtensions::AppxCreateProcessExtensionsTelemetry::PreCreationExtension_Start_(void)
0x180049766  mov     dword ptr [r14+4], 0C8h
0x18004976e  test    rsi, rsi
0x180049771  jz      loc_18004ACFF
0x180049777  xor     eax, eax
0x180049779  mov     [rbp+370h+var_350], r12d
0x18004977d  mov     byte ptr [rbp+370h+var_3C8+3], al
0x180049780  lea     r9, [rbp+370h+var_360]
0x180049784  mov     byte ptr [rbp+370h+var_3C8], al
0x180049787  xorps   xmm0, xmm0
0x18004978a  mov     byte ptr [rbp+370h+var_3C8+4], al
0x18004978d  mov     r8, rbx
0x180049790  mov     byte ptr [rbp+370h+var_3C8+2], al
0x180049793  mov     rdx, rdi
0x180049796  mov     byte ptr [rbp+370h+var_3E0], al
0x180049799  mov     rcx, rsi; TokenHandle
0x18004979c  mov     byte ptr [rbp+370h+var_3C8+1], al
0x18004979f  lea     rax, [rbp+370h+var_3C8+1]
0x1800497a3  mov     [rsp+470h+var_420], rax; __int64
0x1800497a8  lea     rax, [rbp+370h+var_3E0]
0x1800497ac  mov     [rsp+470h+var_428], rax; __int64
0x1800497b1  lea     rax, [rbp+370h+var_3C8+2]
0x1800497b5  mov     qword ptr [rsp+470h+var_430], rax; __int64
0x1800497ba  lea     rax, [rbp+370h+var_3C8+4]
0x1800497be  mov     qword ptr [rsp+470h+var_438], rax; __int64
0x1800497c3  lea     rax, [rbp+370h+var_3C8]
0x1800497c7  mov     [rsp+470h+var_440], rax; __int64
0x1800497cc  lea     rax, [rbp+370h+var_3C8+3]
0x1800497d0  mov     [rsp+470h+lpcbData], rax; __int64
0x1800497d5  lea     rax, [rbp+370h+P]
0x1800497d9  mov     [rsp+470h+ReturnLength], rax; int
0x1800497de  movups  xmmword ptr [rbp+370h+var_360], xmm0
0x1800497e2  mov     [rbp+370h+var_3A8], r12d
0x1800497e6  movups  xmmword ptr [rbp+370h+P], xmm0
0x1800497ea  call    VerifyParametersAndGetEffectivePackageMoniker
0x1800497ef  mov     ebx, eax
0x1800497f1  test    eax, eax
0x1800497f3  js      loc_18004B4DB
0x1800497f9  cmp     dword ptr [rbp+370h+var_360], r12d
0x1800497fd  jz      loc_18004B589
0x180049803  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; void * ReservedForLocalUse::g_heap
0x18004980a  mov     rax, r12
0x18004980d  mov     [rsp+470h+arg_10], r13
0x180049815  mov     [rbp+370h+var_3E8], r12
0x180049819  mov     [rbp+370h+var_3C0], rax
0x18004981d  mov     [rbp+370h+var_398], rax
0x180049821  mov     [rbp+370h+var_338], r12d
0x180049825  mov     dword ptr [rbp+370h+var_33C], r12d
0x180049829  mov     [rsp+470h+var_400], r12
0x18004982e  mov     dword ptr [rbp+370h+var_37C+4], r12d
0x180049832  mov     [rbp+370h+var_3F0], r12
0x180049836  mov     dword ptr [rbp+370h+var_374], r12d
0x18004983a  mov     [rsp+470h+hMem], r12
0x18004983f  mov     dword ptr [rbp+370h+var_374+4], r12d
0x180049843  mov     dword ptr [rbp+370h+var_334], r12d
0x180049847  test    rcx, rcx
0x18004984a  jnz     short loc_180049860
0x18004984c  mov     rcx, gs:60h
0x180049855  mov     rcx, [rcx+30h]; HeapHandle
0x180049859  mov     cs:?g_heap@ReservedForLocalUse@@3PEAXEA, rcx; void * ReservedForLocalUse::g_heap
0x180049860  xor     edx, edx; Flags
0x180049862  mov     r8d, 60h ; '`'; Size
0x180049868  call    cs:__imp_RtlAllocateHeap
0x18004986e  mov     [rbp+370h+var_3D0], rax
0x180049872  mov     r13, rax
0x180049875  test    rax, rax
0x180049878  jz      loc_18004B200
0x18004987e  xor     edx, edx; Val
0x180049880  mov     r8d, 60h ; '`'; Size
0x180049886  mov     rcx, rax; void *
0x180049889  call    memset_0
0x18004988e  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; void * ReservedForLocalUse::g_heap
0x180049895  test    rcx, rcx
0x180049898  jnz     short loc_1800498AE
0x18004989a  mov     rcx, gs:60h
0x1800498a3  mov     rcx, [rcx+30h]; HeapHandle
0x1800498a7  mov     cs:?g_heap@ReservedForLocalUse@@3PEAXEA, rcx; void * ReservedForLocalUse::g_heap
0x1800498ae  xor     edx, edx; Flags
0x1800498b0  mov     r8d, 18h; Size
0x1800498b6  call    cs:__imp_RtlAllocateHeap
0x1800498bc  mov     rbx, rax
0x1800498bf  test    rax, rax
0x1800498c2  jz      loc_18004BAE4
0x1800498c8  mov     [rax], r12
0x1800498cb  mov     r14, [rbp+370h+var_360+8]
0x1800498cf  mov     [rax+10h], r12
0x1800498d3  mov     [rax+8], r12
0x1800498d7  cmp     byte ptr [rbp+370h+var_3E0], r12b
0x1800498db  jnz     loc_18004AA5F
0x1800498e1  test    r14, r14
0x1800498e4  jz      loc_180049ED8
0x1800498ea  cmp     [r14], r12w
0x1800498ee  jz      loc_180049ED8
0x1800498f4  mov     [rbp+370h+var_328], r12d
0x1800498f8  lea     rax, [rbp+370h+var_328]
0x1800498fc  test    rsi, rsi
0x1800498ff  mov     [rsp+470h+ReturnLength], rax; int
0x180049904  mov     r12d, 1
0x18004990a  lea     r8, [rbp+370h+TokenInformation]; TokenInformation
0x180049911  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x180049918  mov     edx, r12d; TokenInformationClass
0x18004991b  cmovnz  rcx, rsi; TokenHandle
0x18004991f  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180049925  call    cs:__imp_NtQueryInformationToken
0x18004992b  test    eax, eax
0x18004992d  js      loc_180049E15
0x180049933  mov     rdi, [rbp+370h+TokenInformation]
0x18004993a  lea     rdx, [rbp+370h+DestinationSid]; DestinationSid
0x180049941  mov     r8, rdi; SourceSid
0x180049944  mov     ecx, 44h ; 'D'; DestinationSidLength
0x180049949  call    cs:__imp_RtlCopySid
0x18004994f  test    eax, eax
0x180049951  js      loc_180049E15
0x180049957  mov     rcx, rdi; Sid
0x18004995a  call    cs:__imp_RtlLengthSid
0x180049960  lea     r8, [rbp+370h+var_338]
0x180049964  mov     rdx, r14
0x180049967  lea     rcx, [rbp+370h+DestinationSid]
0x18004996e  call    cs:__imp_SRGetPackageStatusForUserSid
0x180049974  mov     r15d, eax
0x180049977  and     eax, 1FFF0000h
0x18004997c  cmp     eax, 70000h
0x180049981  jz      loc_18004C21C
0x180049987  xor     ecx, ecx; void *
0x180049989  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18004998e  test    r15d, r15d
0x180049991  jnz     loc_180049EDE
0x180049997  xor     r15d, r15d
0x18004999a  mov     [rbp+370h+var_270], r12b
0x1800499a1  lea     rax, [rbp+370h+var_3D8]
0x1800499a5  mov     [rbp+370h+var_3D8], r15
0x1800499a9  lea     rdx, [rbp+370h+var_278]
0x1800499b0  mov     [rbp+370h+var_280], rax
0x1800499b7  xor     ecx, ecx
0x1800499b9  mov     [rbp+370h+var_278], r15
0x1800499c0  call    cs:__imp_SRCacheManager_Open
0x1800499c6  mov     edi, eax
0x1800499c8  cmp     [rbp+370h+var_270], r15b
0x1800499cf  jz      short loc_1800499F3
0x1800499d1  mov     rdx, [rbp+370h+var_280]
0x1800499d8  mov     rcx, [rbp+370h+var_278]
0x1800499df  mov     r8, [rdx]
0x1800499e2  mov     [rdx], rcx
0x1800499e5  test    r8, r8
0x1800499e8  jz      short loc_1800499F3
0x1800499ea  mov     rcx, r8
0x1800499ed  call    cs:__imp_SRCacheManager_Close
0x1800499f3  test    edi, edi
0x1800499f5  jns     short loc_180049A49
0x1800499f7  mov     rcx, [rbp+378h]; this
0x1800499fe  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180049a05  mov     r9d, edi; char *
0x180049a08  mov     edx, 0A5h; void *
0x180049a0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049a12  mov     rcx, [rbp+378h]; this
0x180049a19  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\processcreatio"...
0x180049a20  mov     r9d, edi; char *
0x180049a23  mov     edx, 314h; void *
0x180049a28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049a2d  mov     rcx, [rbp+370h+var_3D8]
0x180049a31  mov     [rbp+370h+var_3D8], r15
0x180049a35  test    rcx, rcx
0x180049a38  jz      loc_180049EFB
0x180049a3e  call    cs:__imp_SRCacheManager_Close
0x180049a44  jmp     loc_180049EFB
0x180049a49  xorps   xmm0, xmm0
0x180049a4c  mov     [rbp+370h+var_300], r15
0x180049a50  xor     dil, dil
0x180049a53  movdqa  [rbp+370h+var_310], xmm0
0x180049a58  lea     r8, [rbp+370h+var_2A0]; __int64 *
0x180049a5f  movdqa  [rbp+370h+var_2D0], xmm0
0x180049a67  mov     rdx, r14; unsigned __int16 *
0x180049a6a  mov     [rsp+470h+var_410], dil
0x180049a6f  lea     rcx, [rbp+370h+var_3D8]; struct StateRepository::Cache::Manager_NoThrow *
0x180049a73  mov     [rbp+370h+var_2F8], r15
0x180049a77  mov     [rbp+370h+var_2F0], r15
0x180049a7e  mov     [rbp+370h+var_2E8], r15
0x180049a85  mov     [rbp+370h+var_2E0], r15
0x180049a8c  mov     [rbp+370h+var_2D8], r15
0x180049a93  mov     [rbp+370h+var_2C0], r15d
0x180049a9a  mov     [rbp+370h+var_2B8], r15
0x180049aa1  mov     [rbp+370h+var_2B0], r15
0x180049aa8  mov     [rbp+370h+var_2A0], r15
0x180049aaf  call    ?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180049ab4  mov     esi, eax
0x180049ab6  test    eax, eax
0x180049ab8  js      loc_18004A0C7
0x180049abe  mov     rdx, [rbp+370h+var_2A0]
0x180049ac5  test    rdx, rdx
0x180049ac8  jz      short loc_180049AF6
0x180049aca  lea     rax, [rsp+470h+var_410]
0x180049acf  mov     r8d, 80Ah
0x180049ad5  lea     r9, [rbp+370h+var_310]
0x180049ad9  mov     [rsp+470h+ReturnLength], rax; int
0x180049ade  lea     rcx, [rbp+370h+var_3D8]
0x180049ae2  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180049ae7  mov     esi, eax
0x180049ae9  test    eax, eax
0x180049aeb  js      loc_18004C225
0x180049af1  movzx   edi, [rsp+470h+var_410]
0x180049af6  test    dil, dil
0x180049af9  jz      loc_18004AE95
0x180049aff  xorps   xmm0, xmm0
0x180049b02  mov     [rsp+470h+var_410], r15b
0x180049b07  xor     edx, edx; Val
0x180049b09  movdqa  [rbp+370h+var_250], xmm0
0x180049b11  mov     r8d, 44h ; 'D'; Size
0x180049b17  lea     rcx, [rbp+370h+var_240]; void *
0x180049b1e  call    memset_0
0x180049b23  mov     rsi, [rbp+370h+var_300]
0x180049b27  mov     [rbp+370h+Sid], r15
0x180049b2e  mov     [rbp+370h+var_1F0], r15
0x180049b35  test    rsi, rsi
0x180049b38  jz      loc_180049F9E
0x180049b3e  lea     r9, [rsp+470h+var_410]; bool *
0x180049b43  mov     [rbp+370h+var_388], r15
0x180049b47  lea     r8, [rbp+370h+var_388]; struct StateRepository::Cache::Context_NoThrow *
0x180049b4b  mov     rdx, rsi; __int64
0x180049b4e  lea     rcx, [rbp+370h+var_3D8]; struct StateRepository::Cache::Manager_NoThrow *
0x180049b52  call    ?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180049b57  mov     edi, eax
0x180049b59  test    eax, eax
0x180049b5b  js      loc_18004A53D
0x180049b61  movzx   r15d, [rsp+470h+var_410]
0x180049b67  test    r15b, r15b
0x180049b6a  jz      loc_18004BC63
0x180049b70  mov     r9, rsi
0x180049b73  lea     rdx, [rbp+370h+var_250]
0x180049b7a  xor     r8d, r8d
0x180049b7d  lea     rcx, [rbp+370h+var_388]
0x180049b81  call    ?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)
0x180049b86  mov     edi, eax
0x180049b88  test    eax, eax
0x180049b8a  js      loc_18004BC81
0x180049b90  mov     rcx, [rbp+370h+var_388]
0x180049b94  xor     esi, esi
0x180049b96  mov     [rbp+370h+var_388], rsi
0x180049b9a  test    rcx, rcx
0x180049b9d  jz      short loc_180049BA5
0x180049b9f  call    cs:__imp_SRCacheContext_Close
0x180049ba5  test    r15b, r15b
0x180049ba8  jz      loc_18004B8D0
0x180049bae  mov     r9, r14
0x180049bb1  mov     [rbp+370h+hKey], rsi
0x180049bb5  lea     r8, aSoftwareClasse_3; "Software\\Classes\\Local Settings\\Soft"...
0x180049bbc  mov     [rbp+370h+penv], rsi
0x180049bc0  lea     rdx, aSS; "%s\\%s"
0x180049bc7  lea     rcx, [rbp+370h+penv]
0x180049bcb  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180049bd0  mov     edi, eax
0x180049bd2  test    eax, eax
0x180049bd4  js      loc_180049E30
0x180049bda  mov     rcx, [rbp+370h+hKey]; hKey
0x180049bde  mov     rsi, [rbp+370h+penv]
0x180049be2  lea     rax, [rcx-1]
0x180049be6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180049bea  jbe     loc_180049ECE
0x180049bf0  xor     r15d, r15d
0x180049bf3  lea     rax, [rbp+370h+hKey]
0x180049bf7  mov     [rsp+470h+lpcbData], r15; __int64
0x180049bfc  mov     r9d, 20019h
0x180049c02  xor     r8d, r8d
0x180049c05  mov     [rsp+470h+ReturnLength], rax; int
0x180049c0a  mov     rdx, rsi; SourceString
0x180049c0d  mov     [rbp+370h+hKey], r15
0x180049c11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180049c18  call    RegOpenKeyExInternalW
0x180049c1d  mov     edi, eax
  ... truncated ...
```
