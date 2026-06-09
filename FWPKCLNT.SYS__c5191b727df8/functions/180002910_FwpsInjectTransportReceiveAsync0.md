# FwpsInjectTransportReceiveAsync0

- ea: `0x180002910`
- end: `0x180002dcf`
- name: `FwpsInjectTransportReceiveAsync0`
- size: `1215`
- prototype: `NTSTATUS __stdcall(HANDLE injectionHandle, HANDLE injectionContext, PVOID reserved, UINT32 flags, ADDRESS_FAMILY addressFamily, COMPARTMENT_ID compartmentId, IF_INDEX interfaceIndex, IF_INDEX subInterfaceIndex, NET_BUFFER_LIST *netBufferList, FWPS_INJECT_COMPLETE0 completionFn, HANDLE completionContext)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180003048`

## callees

- `0x1800021f4`
- `0x180002910`
- `0x180002dd8`
- `0x180003048`
- `0x180003980`
- `0x180004904`
- `0x180009344`
- `0x18000ca00`
- `0x180020400`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x180002b5c`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x180002b5c`
- `ntoskrnl!KfRaiseIrql` at `0x180002944`
- `ntoskrnl!KfRaiseIrql` at `0x180002944`
- `ntoskrnl!KeLowerIrql` at `0x180002b9e`
- `ntoskrnl!KeLowerIrql` at `0x180002b9e`
- `ntoskrnl!MmBadPointer` at `0x1800029a8`
- `ntoskrnl!MmBadPointer` at `0x180002a7a`
- `ntoskrnl!MmBadPointer` at `0x180002bd5`
- `ntoskrnl!KeIsExecutingDpc` at `0x180002d43`
- `ntoskrnl!KeIsExecutingDpc` at `0x180002d43`
- `NETIO!WfpNblInfoGet` at `0x180002990`
- `NETIO!WfpNblInfoGet` at `0x180002a99`
- `NETIO!WfpNblInfoGet` at `0x180002990`
- `NETIO!WfpNblInfoGet` at `0x180002a99`

## pseudocode

```c

```
