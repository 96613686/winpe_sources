# CPerSessionTempDir::GetUserEnvVar(ushort const *,ushort * *,unsigned __int64 *)

- ea: `0x180027cdc`
- end: `0x180027e63`
- name: `?GetUserEnvVar@CPerSessionTempDir@@AEAAJPEBGPEAPEAGPEA_K@Z`
- size: `391`
- prototype: `__int64 __fastcall(CPerSessionTempDir *this, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002832c`

## callees

- `0x180003f30`
- `0x18001a2a4`
- `0x18001a8d0`
- `0x180027780`
- `0x180027cdc`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180027d3e`
- `ntdll!RtlInitUnicodeStringEx` at `0x180027d3e`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x180027dac`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x180027e1f`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x180027dac`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x180027e1f`

## string_xrefs

- `0x180027d59`: `CPerSessionTempDir::GetUserEnvVar`
- `0x180027d2e`: `CreateEnvironmentBlock failed: 0x%x in %s`

## pseudocode

```c

```
