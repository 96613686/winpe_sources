# FwpmIPsecTunnelAdd0

- ea: `0x1800542a0`
- end: `0x1800543e8`
- name: `FwpmIPsecTunnelAdd0`
- size: `328`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, UINT32 flags, const FWPM_PROVIDER_CONTEXT0 *mainModePolicy, const FWPM_PROVIDER_CONTEXT0 *tunnelPolicy, UINT32 numFilterConditions, const FWPM_FILTER_CONDITION0 *filterConditions, PSECURITY_DESCRIPTOR sd)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008f10`
- `0x180015864`
- `0x18001a5a8`
- `0x1800542a0`
- `0x180054670`
- `0x18005a86c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800542c9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800542c9`

## pseudocode

```c

```
