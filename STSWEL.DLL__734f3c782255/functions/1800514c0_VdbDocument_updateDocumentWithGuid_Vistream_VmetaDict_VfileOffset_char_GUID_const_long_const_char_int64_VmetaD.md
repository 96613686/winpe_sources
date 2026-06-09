# VdbDocument::updateDocumentWithGuid(Vistream &,VmetaDict &,VfileOffset,char,_GUID const *,long const *,char *,__int64,VmetaDict *,VvirusCheck *,Virm *,VcheckoutRequest const *,Vstring *,long,long,long,char,ulong *,long,VtriState)

- ea: `0x1800514c0`
- end: `0x180051c57`
- name: `?updateDocumentWithGuid@VdbDocument@@QEAAPEAVVstatus@@AEAVVistream@@AEAVVmetaDict@@VVfileOffset@@DPEBU_GUID@@PEBJPEAD_JPEAV4@PEAVVvirusCheck@@PEAVVirm@@PEBVVcheckoutRequest@@PEAVVstring@@JJJDPEAKJW4VtriState@@@Z`
- size: `1943`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801122f0`

## callees

- `0x18003e1dc`
- `0x18004f210`
- `0x1800514c0`
- `0x180051d40`
- `0x1800521e0`
- `0x180052850`
- `0x180052940`
- `0x180052b80`
- `0x18005a224`
- `0x1800f7eb0`
- `0x1800f8070`
- `0x1800f84c0`
- `0x1800ff610`
- `0x1801c1770`
- `0x1801c2da0`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180051817`
- `KERNEL32!GetTickCount64` at `0x180051922`
- `KERNEL32!GetTickCount64` at `0x180051a50`
- `KERNEL32!GetTickCount64` at `0x180051a77`
- `KERNEL32!GetTickCount64` at `0x180051817`
- `KERNEL32!GetTickCount64` at `0x180051922`
- `KERNEL32!GetTickCount64` at `0x180051a50`
- `KERNEL32!GetTickCount64` at `0x180051a77`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800515ef`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x18005178c`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800518f3`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800515ef`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x18005178c`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800518f3`
- `onetutil!??0Vwstring@@QEAA@PEBD@Z` at `0x1800515fc`
- `onetutil!??0Vwstring@@QEAA@PEBD@Z` at `0x1800515fc`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800516ae`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800517f7`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x180051a03`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x180051a47`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800516ae`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800517f7`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x180051a03`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x180051a47`
- `onetutil!?asVsize_tBounded@VfileOffset@@QEBAII@Z` at `0x18005183f`
- `onetutil!?asVsize_tBounded@VfileOffset@@QEBAII@Z` at `0x18005194c`
- `onetutil!?asVsize_tBounded@VfileOffset@@QEBAII@Z` at `0x18005183f`
- `onetutil!?asVsize_tBounded@VfileOffset@@QEBAII@Z` at `0x18005194c`
- `onetutil!??0VprettyUrl@@QEAA@PEBDI@Z` at `0x18005179f`
- `onetutil!??0VprettyUrl@@QEAA@PEBDI@Z` at `0x18005179f`
- `onetutil!??1VprettyUrl@@QEAA@XZ` at `0x180051809`
- `onetutil!??1VprettyUrl@@QEAA@XZ` at `0x180051809`
- `onetutil!?data@VprettyUrl@@QEBAPEBDXZ` at `0x1800517d2`
- `onetutil!?data@VprettyUrl@@QEBAPEBDXZ` at `0x1800517d2`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180051607`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x180051607`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x18005166b`
- `onetutil!??1Vwstring@@QEAA@XZ` at `0x18005166b`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180051590`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18005167d`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800517a6`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800519d2`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180051a16`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180051a83`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180051590`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x18005167d`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800517a6`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800519d2`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180051a16`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x180051a83`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800515a1`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x18005168c`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800517b4`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800519e1`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180051a25`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800515a1`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x18005168c`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800517b4`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800519e1`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x180051a25`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x180051a93`
- `onetutil!?Free@COWSAllocator@@SAXPEAX@Z` at `0x180051a93`
- `onetutil!??4Vdict@@QEAAAEAV0@AEBV0@@Z` at `0x180051b79`
- `onetutil!??4Vdict@@QEAAAEAV0@AEBV0@@Z` at `0x180051b79`
- `onetutil!?read@Vistream@@QEAAPEAVVstatus@@PEADIIPEAI@Z` at `0x180051859`
- `onetutil!?read@Vistream@@QEAAPEAVVstatus@@PEADIIPEAI@Z` at `0x180051969`
- `onetutil!?read@Vistream@@QEAAPEAVVstatus@@PEADIIPEAI@Z` at `0x180051859`
- `onetutil!?read@Vistream@@QEAAPEAVVstatus@@PEADIIPEAI@Z` at `0x180051969`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180051652`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x180051652`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800515a9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180051694`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800517bc`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800519e9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180051a2d`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800515a9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180051694`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800517bc`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800519e9`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180051a2d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180051a9b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180051a9b`
- `OLEAUT32!SysAllocString` at `0x180051611`
- `OLEAUT32!SysAllocString` at `0x180051611`
- `onetnative!ULSSendTraceTag` at `0x180051ac2`
- `onetnative!ULSSendTraceTag` at `0x180051ac2`

## string_xrefs

- `0x180051aab`: `Spent %u ms to read %I64u byte file stream`

## pseudocode

```c

```
