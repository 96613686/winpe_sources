# SdpDB_ServiceSearchAttributeResponse(_SDP_DATABASE *,_SDP_UUID_SEARCH *,_SDP_ATTRIB_SEARCH *,uchar * *,ulong *,ushort *,uchar)

- ea: `0x1401ee618`
- end: `0x1401ee8a4`
- name: `?SdpDB_ServiceSearchAttributeResponse@@YAJPEAU_SDP_DATABASE@@PEAU_SDP_UUID_SEARCH@@PEAU_SDP_ATTRIB_SEARCH@@PEAPEAEPEAKPEAGE@Z`
- size: `652`
- prototype: `__int64 __fastcall(struct _SDP_DATABASE *, struct _SDP_UUID_SEARCH *, struct _SDP_ATTRIB_SEARCH *, unsigned __int8 **, unsigned int *, unsigned __int16 *, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x1401ee8ac`
- `0x1401ee9a0`

## callees

- `0x14014ab94`
- `0x140165640`
- `0x1401ee618`
- `0x1401ef1f8`
- `0x14020aa5c`
- `0x14020b0b0`
- `0x14020b2fc`
- `0x14020c434`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1401ee65e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401ee65e`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401ee76e`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401ee76e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee87b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee87b`
- `ntoskrnl!ExAllocatePool2` at `0x1401ee7a2`
- `ntoskrnl!ExAllocatePool2` at `0x1401ee7a2`

## pseudocode

```c

```
