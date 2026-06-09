# FwpsInjectNetworkSendAsync0

- ea: `0x180002280`
- end: `0x1800025a7`
- name: `FwpsInjectNetworkSendAsync0`
- size: `807`
- prototype: `NTSTATUS __stdcall(HANDLE injectionHandle, HANDLE injectionContext, UINT32 flags, COMPARTMENT_ID compartmentId, NET_BUFFER_LIST *netBufferList, FWPS_INJECT_COMPLETE0 completionFn, HANDLE completionContext)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180003048`

## callees

- `0x1800021f4`
- `0x180002280`
- `0x180002dd8`
- `0x180003048`
- `0x1800032f0`
- `0x180004904`
- `0x18000ca00`
- `0x180020400`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1800022cc`
- `ntoskrnl!KfRaiseIrql` at `0x1800022cc`
- `ntoskrnl!KeLowerIrql` at `0x180002455`
- `ntoskrnl!KeLowerIrql` at `0x180002455`
- `ntoskrnl!KeIsExecutingDpc` at `0x180002487`
- `ntoskrnl!KeIsExecutingDpc` at `0x180002487`
- `NDIS!NdisGetDataBuffer` at `0x180002395`
- `NDIS!NdisGetDataBuffer` at `0x1800023d1`
- `NDIS!NdisGetDataBuffer` at `0x180002395`
- `NDIS!NdisGetDataBuffer` at `0x1800023d1`
- `NETIO!NetioDereferenceNetBufferList` at `0x1800024da`
- `NETIO!NetioDereferenceNetBufferList` at `0x1800024da`

## pseudocode

```c

```
