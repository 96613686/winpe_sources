# FwpsStreamInjectAsync0

- ea: `0x180001f70`
- end: `0x1800021ee`
- name: `FwpsStreamInjectAsync0`
- size: `638`
- prototype: `NTSTATUS __stdcall(HANDLE injectionHandle, HANDLE injectionContext, UINT32 flags, UINT64 flowId, UINT32 calloutId, UINT16 layerId, UINT32 streamFlags, NET_BUFFER_LIST *netBufferList, SIZE_T dataLength, FWPS_INJECT_COMPLETE0 completionFn, HANDLE completionContext)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001f70`
- `0x180003b60`
- `0x180004904`
- `0x180004a60`
- `0x18000a224`
- `0x18001e740`
- `0x18001e9c0`
- `0x18001f0b4`
- `0x180020400`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x180002131`

## pseudocode

```c

```
