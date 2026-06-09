# FwpsInjectForwardAsync0

- ea: `0x180001cd0`
- end: `0x180001f5d`
- name: `FwpsInjectForwardAsync0`
- size: `653`
- prototype: `NTSTATUS __stdcall(HANDLE injectionHandle, HANDLE injectionContext, UINT32 flags, ADDRESS_FAMILY addressFamily, COMPARTMENT_ID compartmentId, IF_INDEX interfaceIndex, NET_BUFFER_LIST *netBufferList, FWPS_INJECT_COMPLETE0 completionFn, HANDLE completionContext)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180003048`

## callees

- `0x180001cd0`
- `0x1800021f4`
- `0x180002dd8`
- `0x180003048`
- `0x1800032f0`
- `0x180004904`
- `0x18000ca00`
- `0x180020400`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x180001d1a`
- `ntoskrnl!KfRaiseIrql` at `0x180001d1a`
- `ntoskrnl!KeLowerIrql` at `0x180001d6b`
- `ntoskrnl!KeLowerIrql` at `0x180001d6b`
- `ntoskrnl!KeIsExecutingDpc` at `0x180001db3`
- `ntoskrnl!KeIsExecutingDpc` at `0x180001db3`

## pseudocode

```c

```
