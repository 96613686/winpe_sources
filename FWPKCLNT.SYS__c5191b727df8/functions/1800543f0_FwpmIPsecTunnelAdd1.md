# FwpmIPsecTunnelAdd1

- ea: `0x1800543f0`
- end: `0x180054538`
- name: `FwpmIPsecTunnelAdd1`
- size: `328`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, UINT32 flags, const FWPM_PROVIDER_CONTEXT1 *mainModePolicy, const FWPM_PROVIDER_CONTEXT1 *tunnelPolicy, UINT32 numFilterConditions, const FWPM_FILTER_CONDITION0 *filterConditions, const GUID *keyModKey, PSECURITY_DESCRIPTOR sd)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008f10`
- `0x180012978`
- `0x180015864`
- `0x18001a5a8`
- `0x1800543f0`
- `0x180054670`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180054419`
- `ntoskrnl!KeGetCurrentIrql` at `0x180054419`

## pseudocode

```c

```
