# VsecCacheManager::SerializeAndPersistClaimMap(VdocumentStore &,_GUID const *,VsiteCollectionRecord *,VdbServer &)

- ea: `0x18017a920`
- end: `0x18017b2ae`
- name: `?SerializeAndPersistClaimMap@VsecCacheManager@@QEAA?AVVHRESULT@@AEAVVdocumentStore@@PEBU_GUID@@PEAVVsiteCollectionRecord@@AEAVVdbServer@@@Z`
- size: `2446`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18017da80`

## callees

- `0x18008ea50`
- `0x180137580`
- `0x18017a920`
- `0x18017bb30`
- `0x180180348`
- `0x1801ae140`
- `0x1801ae230`
- `0x1801ae2e0`
- `0x1801ae440`
- `0x1801afec0`
- `0x1801b0490`
- `0x1801b0a40`
- `0x1801c1770`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18017aa59`
- `KERNEL32!QueryPerformanceCounter` at `0x18017b16d`
- `KERNEL32!QueryPerformanceCounter` at `0x18017b1bb`
- `KERNEL32!QueryPerformanceCounter` at `0x18017aa59`
- `KERNEL32!QueryPerformanceCounter` at `0x18017b16d`
- `KERNEL32!QueryPerformanceCounter` at `0x18017b1bb`
- `KERNEL32!QueryPerformanceFrequency` at `0x18017aa35`
- `KERNEL32!QueryPerformanceFrequency` at `0x18017aa35`
- `KERNEL32!GetTickCount64` at `0x18017aa75`
- `KERNEL32!GetTickCount64` at `0x18017b184`
- `KERNEL32!GetTickCount64` at `0x18017b1d2`
- `KERNEL32!GetTickCount64` at `0x18017aa75`
- `KERNEL32!GetTickCount64` at `0x18017b184`
- `KERNEL32!GetTickCount64` at `0x18017b1d2`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017af9a`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017b0ed`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017af9a`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017b0ed`
- `onetutil!??AVint32Vvector@@QEAAAEAJI@Z` at `0x18017ac48`
- `onetutil!??AVint32Vvector@@QEAAAEAJI@Z` at `0x18017adcb`
- `onetutil!??AVint32Vvector@@QEAAAEAJI@Z` at `0x18017ac48`
- `onetutil!??AVint32Vvector@@QEAAAEAJI@Z` at `0x18017adcb`
- `onetutil!?CloseIterator@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEAVCIterator@1@@Z` at `0x18017acb0`
- `onetutil!?CloseIterator@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEAVCIterator@1@@Z` at `0x18017ae2f`
- `onetutil!?CloseIterator@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEAVCIterator@1@@Z` at `0x18017acb0`
- `onetutil!?CloseIterator@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEAVCIterator@1@@Z` at `0x18017ae2f`
- `onetutil!?IncrementIterator@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEAVCIterator@1@@Z` at `0x18017ac84`
- `onetutil!?IncrementIterator@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEAVCIterator@1@@Z` at `0x18017ae08`
- `onetutil!?IncrementIterator@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEAVCIterator@1@@Z` at `0x18017ac84`
- `onetutil!?IncrementIterator@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEAVCIterator@1@@Z` at `0x18017ae08`
- `onetutil!?InitializeIterator@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEAVCIterator@1@@Z` at `0x18017ab4e`
- `onetutil!?InitializeIterator@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEAVCIterator@1@@Z` at `0x18017acbe`
- `onetutil!?InitializeIterator@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEAVCIterator@1@@Z` at `0x18017ab4e`
- `onetutil!?InitializeIterator@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEAVCIterator@1@@Z` at `0x18017acbe`
- `onetutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18017aaa4`
- `onetutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18017aab7`
- `onetutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18017aaa4`
- `onetutil!?Size@CLKRHashTable@@QEBAKXZ` at `0x18017aab7`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017aac6`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017aaff`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017ae8f`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017aeaa`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017b265`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017aac6`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017aaff`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017ae8f`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017aeaa`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017b265`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x18017aad3`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x18017ab0c`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x18017aad3`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x18017ab0c`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017ae9c`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017aeb7`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017b272`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017ae9c`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017aeb7`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017b272`
- `onetutil!?Vstrlen@@YAIPEBD@Z` at `0x18017ab85`
- `onetutil!?Vstrlen@@YAIPEBD@Z` at `0x18017ad03`
- `onetutil!?Vstrlen@@YAIPEBD@Z` at `0x18017ab85`
- `onetutil!?Vstrlen@@YAIPEBD@Z` at `0x18017ad03`
- `onetutil!??0VHRESULT@@QEAA@J@Z` at `0x18017a9df`
- `onetutil!??0VHRESULT@@QEAA@J@Z` at `0x18017a9df`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017afab`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017afdc`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017b0fe`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017b148`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017afab`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017afdc`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017b0fe`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017b148`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18017aadb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18017ab14`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18017aadb`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18017ab14`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017aea4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017aebf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017b27a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017aea4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017aebf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017b27a`
- `onetnative!ULSPerfmonEvent` at `0x18017b192`
- `onetnative!ULSPerfmonEvent` at `0x18017b19d`
- `onetnative!ULSPerfmonEvent` at `0x18017b192`
- `onetnative!ULSPerfmonEvent` at `0x18017b19d`
- `onetnative!ULSPerfmonIncrement` at `0x18017b204`
- `onetnative!ULSPerfmonIncrement` at `0x18017b204`
- `onetnative!ULSSendTraceTag` at `0x18017b126`
- `onetnative!ULSSendTraceTag` at `0x18017b126`

## string_xrefs

- `0x18017a9fd`: `\sts\wel\security.cpp`
- `0x18017b212`: `\sts\wel\security.cpp`
- `0x18017b237`: `\sts\wel\security.cpp`
- `0x18017aec5`: `AuthZenKS_ClaimMapWriteBack`
- `0x18017aefb`: `proc_SecUpdateDomainGroupMapData`
- `0x18017affa`: `proc_SecUpdateDomainGroupMapData`
- `0x18017af77`: `VsecCacheManager::SerializeAndPersistClaimMap`
- `0x18017b0ca`: `VsecCacheManager::SerializeAndPersistClaimMap`
- `0x18017b10f`: `Call to proc_SecUpdateDomainGroupMapData failed. HR: '0x%08x'.`

## pseudocode

```c

```
