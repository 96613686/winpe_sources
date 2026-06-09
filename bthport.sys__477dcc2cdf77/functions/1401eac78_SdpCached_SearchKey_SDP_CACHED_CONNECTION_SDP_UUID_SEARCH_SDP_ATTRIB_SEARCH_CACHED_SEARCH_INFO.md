# SdpCached_SearchKey(_SDP_CACHED_CONNECTION *,_SDP_UUID_SEARCH *,_SDP_ATTRIB_SEARCH *,_CACHED_SEARCH_INFO *)

- ea: `0x1401eac78`
- end: `0x1401eb04d`
- name: `?SdpCached_SearchKey@@YAJPEAU_SDP_CACHED_CONNECTION@@PEAU_SDP_UUID_SEARCH@@PEAU_SDP_ATTRIB_SEARCH@@PEAU_CACHED_SEARCH_INFO@@@Z`
- size: `981`
- prototype: `__int64 __fastcall(struct _SDP_CACHED_CONNECTION *, struct _SDP_UUID_SEARCH *, struct _SDP_ATTRIB_SEARCH *, struct _CACHED_SEARCH_INFO *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1401eb054`
- `0x1401eb224`

## callees

- `0x140165540`
- `0x1401eac78`
- `0x1401ef1f8`
- `0x14020abd4`
- `0x14020b0b0`
- `0x14020b1b0`
- `0x14020cf44`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401eb01e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401eb01e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401eacd9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401eacd9`
- `ntoskrnl!ZwQueryKey` at `0x1401ead18`
- `ntoskrnl!ZwQueryKey` at `0x1401ead7d`
- `ntoskrnl!ZwQueryKey` at `0x1401ead18`
- `ntoskrnl!ZwQueryKey` at `0x1401ead7d`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1401eae73`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1401eae73`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401eaceb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401eaceb`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401eb012`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401eb012`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401eaf6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401eafe8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401eaffe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401eaf6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401eafe8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401eaffe`
- `ntoskrnl!ExAllocatePool2` at `0x1401ead46`
- `ntoskrnl!ExAllocatePool2` at `0x1401eadbf`
- `ntoskrnl!ExAllocatePool2` at `0x1401ead46`
- `ntoskrnl!ExAllocatePool2` at `0x1401eadbf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401eae5a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401eae5a`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1401eae14`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1401eae14`

## pseudocode

```c

```
