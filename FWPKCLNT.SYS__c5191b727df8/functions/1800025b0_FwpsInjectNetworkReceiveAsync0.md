# FwpsInjectNetworkReceiveAsync0

- ea: `0x1800025b0`
- end: `0x180002902`
- name: `FwpsInjectNetworkReceiveAsync0`
- size: `850`
- prototype: `NTSTATUS __stdcall(HANDLE injectionHandle, HANDLE injectionContext, UINT32 flags, COMPARTMENT_ID compartmentId, IF_INDEX interfaceIndex, IF_INDEX subInterfaceIndex, NET_BUFFER_LIST *netBufferList, FWPS_INJECT_COMPLETE0 completionFn, HANDLE completionContext)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180003048`

## callees

- `0x1800021f4`
- `0x1800025b0`
- `0x180002dd8`
- `0x180003048`
- `0x18000ca00`
- `0x18000de60`
- `0x180020400`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x180002726`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x180002726`
- `ntoskrnl!KfRaiseIrql` at `0x1800025f4`
- `ntoskrnl!KfRaiseIrql` at `0x1800025f4`
- `ntoskrnl!KeLowerIrql` at `0x180002764`
- `ntoskrnl!KeLowerIrql` at `0x180002764`
- `ntoskrnl!KeIsExecutingDpc` at `0x1800027cd`
- `ntoskrnl!KeIsExecutingDpc` at `0x1800027cd`

## pseudocode

```c

```
