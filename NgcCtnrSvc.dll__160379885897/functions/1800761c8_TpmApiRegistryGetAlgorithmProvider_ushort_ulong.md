# TpmApiRegistryGetAlgorithmProvider(ushort * *,ulong *)

- ea: `0x1800761c8`
- end: `0x180076310`
- name: `?TpmApiRegistryGetAlgorithmProvider@@YAJPEAPEAGPEAK@Z`
- size: `328`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180076124`

## callees

- `0x180074a1c`
- `0x180074a48`
- `0x1800761c8`
- `0x180076318`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180076218`
- `ntdll!RtlInitUnicodeString` at `0x18007622f`
- `ntdll!RtlInitUnicodeString` at `0x180076218`
- `ntdll!RtlInitUnicodeString` at `0x18007622f`

## string_xrefs

- `0x180076205`: `\Registry\Machine\System\CurrentControlSet\Control\BitLocker`

## pseudocode

```c

```
