# BipPackageResetAndQueryAccessStateForUserSidAsync

- ea: `0x180005280`
- end: `0x180005357`
- name: `BipPackageResetAndQueryAccessStateForUserSidAsync`
- size: `215`
- prototype: `__int64 __fastcall(PSID Sid1)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004f30`

## callees

- `0x1800048ec`
- `0x180005280`
- `0x180005360`
- `0x18000d7c0`
- `0x18000da50`
- `0x1800121b0`

## import_xrefs

- `ntdll!RtlEnumerateEntryHashTable` at `0x18000530b`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18000530b`
- `ntdll!RtlInitEnumerationHashTable` at `0x1800052cf`
- `ntdll!RtlInitEnumerationHashTable` at `0x1800052cf`
- `ntdll!RtlEqualSid` at `0x1800052f6`
- `ntdll!RtlEqualSid` at `0x1800052f6`
- `ntdll!RtlEndEnumerationHashTable` at `0x180005324`
- `ntdll!RtlEndEnumerationHashTable` at `0x180005324`

## pseudocode

```c

```
