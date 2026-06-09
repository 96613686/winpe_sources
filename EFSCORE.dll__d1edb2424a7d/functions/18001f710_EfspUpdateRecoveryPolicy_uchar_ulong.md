# EfspUpdateRecoveryPolicy(uchar *,ulong)

- ea: `0x18001f710`
- end: `0x18001f906`
- name: `?EfspUpdateRecoveryPolicy@@YAKPEAEK@Z`
- size: `502`
- prototype: `unsigned int __fastcall(unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18001f920`

## callees

- `0x180005045`
- `0x18000505d`
- `0x18001f4ac`
- `0x18001f710`
- `0x180063698`
- `0x1800dca3c`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001f8bc`
- `ntdll!RtlReleaseResource` at `0x18001f8bc`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001f851`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001f851`
- `EFSUTIL!EfsUtilParseDataRecoveryPolicy_1_1` at `0x18001f79b`
- `EFSUTIL!EfsUtilParseDataRecoveryPolicy_1_1` at `0x18001f7b3`
- `EFSUTIL!EfsUtilParseDataRecoveryPolicy_1_1` at `0x18001f79b`
- `EFSUTIL!EfsUtilParseDataRecoveryPolicy_1_1` at `0x18001f7b3`
- `EFSUTIL!EfsUtilFreeParsedRecoveryPolicy` at `0x18001f85e`
- `EFSUTIL!EfsUtilFreeParsedRecoveryPolicy` at `0x18001f85e`

## pseudocode

```c

```
