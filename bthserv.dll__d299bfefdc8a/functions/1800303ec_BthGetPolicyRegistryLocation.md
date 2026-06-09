# BthGetPolicyRegistryLocation

- ea: `0x1800303ec`
- end: `0x1800304be`
- name: `BthGetPolicyRegistryLocation`
- size: `210`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c534`

## callees

- `0x180002470`
- `0x18000247c`
- `0x1800303ec`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003049c`
- `ntdll!RtlInitUnicodeString` at `0x18003049c`
- `ntdll!RtlGetPersistedStateLocation` at `0x180030432`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003048a`
- `ntdll!RtlGetPersistedStateLocation` at `0x180030432`
- `ntdll!RtlGetPersistedStateLocation` at `0x18003048a`

## pseudocode

```c

```
