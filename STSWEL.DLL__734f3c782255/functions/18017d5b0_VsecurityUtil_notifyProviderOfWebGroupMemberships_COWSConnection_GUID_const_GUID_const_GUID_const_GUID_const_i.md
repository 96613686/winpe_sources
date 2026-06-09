# VsecurityUtil::notifyProviderOfWebGroupMemberships(COWSConnection *,_GUID const &,_GUID const *,_GUID const *,_GUID const *,__int64)

- ea: `0x18017d5b0`
- end: `0x18017da7b`
- name: `?notifyProviderOfWebGroupMemberships@VsecurityUtil@@SA?AVVHRESULT@@PEAVCOWSConnection@@AEBU_GUID@@PEBU4@22_J@Z`
- size: `1227`
- prototype: `static struct VHRESULT __high(struct COWSConnection *, const struct _GUID *, const struct _GUID *, const struct _GUID *, const struct _GUID *, __int64)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1801618a0`
- `0x1801730e0`

## callees

- `0x180046410`
- `0x1800465d0`
- `0x180144664`
- `0x18014478c`
- `0x180144a10`
- `0x18017639c`
- `0x18017d5b0`
- `0x180198330`
- `0x1801ae140`
- `0x1801ae230`
- `0x1801ae380`
- `0x1801ae440`
- `0x1801b0490`
- `0x1801b0a40`
- `0x1801b0b80`
- `0x1801b0d10`
- `0x1801c1770`
- `0x1801c2da0`

## import_xrefs

- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x18017d65b`
- `onetutil!??4VHRESULT@@QEAAAEAV0@J@Z` at `0x18017d65b`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017d7b6`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017d7e9`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017d83b`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017d8b7`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017d984`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017d7b6`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017d7e9`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017d83b`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017d8b7`
- `onetutil!??4VHRESULT@@QEAAAEAV0@AEBV0@@Z` at `0x18017d984`
- `onetutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18017d67c`
- `onetutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18017d67c`
- `onetutil!?ReadLock@CReaderWriterLock3@VonetLocks@@QEAAXXZ` at `0x18017d693`
- `onetutil!?ReadLock@CReaderWriterLock3@VonetLocks@@QEAAXXZ` at `0x18017d693`
- `onetutil!?ReadUnlock@CReaderWriterLock3@VonetLocks@@QEAAXXZ` at `0x18017d6ac`
- `onetutil!?ReadUnlock@CReaderWriterLock3@VonetLocks@@QEAAXXZ` at `0x18017d6ac`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017d71c`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017d8e4`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017d90f`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017d934`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017d9a9`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017d9ec`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017da11`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017d71c`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017d8e4`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017d90f`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017d934`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017d9a9`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017d9ec`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18017da11`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x18017d729`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x18017d729`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017d8f1`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017d91c`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017d9b6`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017d9f9`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017da1e`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017d8f1`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017d91c`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017d9b6`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017d9f9`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x18017da1e`
- `onetutil!??0VHRESULT@@QEAA@J@Z` at `0x18017d60d`
- `onetutil!??0VHRESULT@@QEAA@J@Z` at `0x18017d60d`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017d7c6`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017d7f9`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017d84b`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017d8c7`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017d994`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017d7c6`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017d7f9`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017d84b`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017d8c7`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x18017d994`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18017d731`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18017d731`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017d924`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017d942`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017d9be`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017da01`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017da26`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017d924`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017d942`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017d9be`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017da01`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18017da26`

## string_xrefs

- `0x18017d73f`: `proc_SecGetCompleteWebRoleMemberList`
- `0x18017d79b`: `VsecurityUtil::notifyProviderOfWebGroupMemberships`

## pseudocode

```c

```
