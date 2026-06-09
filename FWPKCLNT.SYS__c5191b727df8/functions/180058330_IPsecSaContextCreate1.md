# IPsecSaContextCreate1

- ea: `0x180058330`
- end: `0x1800583c6`
- name: `IPsecSaContextCreate1`
- size: `150`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, const IPSEC_TRAFFIC1 *outboundTraffic, const IPSEC_VIRTUAL_IF_TUNNEL_INFO0 *virtualIfTunnelInfo, UINT64 *inboundFilterId, UINT64 *id)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180058220`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008f10`
- `0x180010a0c`
- `0x180058330`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180058345`
- `ntoskrnl!KeGetCurrentIrql` at `0x180058345`

## string_xrefs

- `0x18005835b`: `IPsecSaContextCreate1`
- `0x18005839c`: `FwppProxyBfeIPsecSaContextCreate`

## pseudocode

```c

```
