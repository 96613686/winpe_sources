# SdpDB_ServiceAttributeRequestResponse(_SDP_DATABASE *,ulong,_SDP_ATTRIB_SEARCH *,uchar * *,ulong *,void * *,ushort *,uchar)

- ea: `0x1401ee148`
- end: `0x1401ee52a`
- name: `?SdpDB_ServiceAttributeRequestResponse@@YAJPEAU_SDP_DATABASE@@KPEAU_SDP_ATTRIB_SEARCH@@PEAPEAEPEAKPEAPEAXPEAGE@Z`
- size: `994`
- prototype: `__int64 __fastcall(struct _SDP_DATABASE *, unsigned int, struct _SDP_ATTRIB_SEARCH *, unsigned __int8 **, unsigned int *, void **, unsigned __int16 *, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1401ee530`
- `0x1401ef3ec`

## callees

- `0x140005608`
- `0x140005690`
- `0x1401ee148`
- `0x14020aa5c`
- `0x14020b0b0`
- `0x14020c434`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1401ee17f`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401ee17f`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401ee317`
- `ntoskrnl!ExReleaseFastMutex` at `0x1401ee317`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee387`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ee387`
- `ntoskrnl!ExAllocatePool2` at `0x1401ee475`
- `ntoskrnl!ExAllocatePool2` at `0x1401ee475`

## pseudocode

```c

```
