# VdocHandle::beginUpdateVersion(ulong,long,uchar,char *,char)

- ea: `0x1800f9aa0`
- end: `0x1800fa182`
- name: `?beginUpdateVersion@VdocHandle@@QEAAPEAVVstatus@@KJEPEADD@Z`
- size: `1762`
- prototype: `struct Vstatus *__usercall@<rax>(VdocHandle *__hidden this@<rcx>, unsigned int@<edx>, int@<r8d>, unsigned __int8@<r9b>, char *, char)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800591d0`
- `0x1800f9890`
- `0x1800f99d0`

## callees

- `0x18005a36c`
- `0x18005a3fc`
- `0x18005a51c`
- `0x18009c4f0`
- `0x1800b54d0`
- `0x1800ee560`
- `0x1800f8f30`
- `0x1800f9460`
- `0x1800f9aa0`
- `0x1801025f0`
- `0x180102750`
- `0x1801035d0`
- `0x180137580`
- `0x18017dd90`
- `0x1801c2da0`

## import_xrefs

- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800f9b58`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800f9c0e`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800f9c28`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800f9c5a`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800fa0bc`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800f9b58`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800f9c0e`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800f9c28`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800f9c5a`
- `onetutil!?data@Vstring@@QEBAPEBDXZ` at `0x1800fa0bc`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800f9bf4`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800f9cc0`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800f9e60`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800fa048`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800fa117`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800f9bf4`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800f9cc0`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800f9e60`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800fa048`
- `onetutil!??0VgenericStatus@@QEAA@KJZZ` at `0x1800fa117`
- `onetutil!??0VprettyUrl@@QEAA@PEBDI@Z` at `0x1800fa0cf`
- `onetutil!??0VprettyUrl@@QEAA@PEBDI@Z` at `0x1800fa0cf`
- `onetutil!??1VprettyUrl@@QEAA@XZ` at `0x1800fa129`
- `onetutil!??1VprettyUrl@@QEAA@XZ` at `0x1800fa129`
- `onetutil!?data@VprettyUrl@@QEBAPEBDXZ` at `0x1800fa103`
- `onetutil!?data@VprettyUrl@@QEBAPEBDXZ` at `0x1800fa103`
- `onetutil!?urlIsXsnDoc@?$VurlTemplate@VVstoreUrlSettings@@@@SADAEBV1@@Z` at `0x1800f9cee`
- `onetutil!?urlIsXsnDoc@?$VurlTemplate@VVstoreUrlSettings@@@@SADAEBV1@@Z` at `0x1800f9cee`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800fa13c`
- `onetutil!??1Vstring@@QEAA@XZ` at `0x1800fa13c`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800f9bbc`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800f9c8f`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800f9e30`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800fa017`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800fa0d6`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800f9bbc`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800f9c8f`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800f9e30`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800fa017`
- `onetutil!?QueryNewMode@COWSAllocator@@SAHXZ` at `0x1800fa0d6`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800f9bcb`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800f9c9e`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800f9e3e`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800fa026`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800fa0e5`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800f9bcb`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800f9c9e`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800f9e3e`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800fa026`
- `onetutil!?AllocCurrentHeap@COWSAllocator@@SAPEAX_K@Z` at `0x1800fa0e5`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800f9b0b`
- `onetutil!??1VHRESULT@@QEAA@XZ` at `0x1800f9b0b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800f9bd3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800f9ca6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800f9e46`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fa02e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fa0ed`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800f9bd3`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800f9ca6`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800f9e46`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fa02e`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800fa0ed`
- `onetnative!ULSSendTraceTag` at `0x1800f9f26`
- `onetnative!ULSSendTraceTag` at `0x1800f9f91`
- `onetnative!ULSSendTraceTag` at `0x1800f9f26`
- `onetnative!ULSSendTraceTag` at `0x1800f9f91`

## string_xrefs

- `0x1800f9f0f`: `beginUpdateVersion(): Setting NoExecute to true on web file.`
- `0x1800f9f7a`: `beginUpdateVersion(): Setting NoExecute to true on non-web file.`

## pseudocode

```c

```
