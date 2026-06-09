# Common::Security::NtFreeUserSidString(ushort *)

- ea: `0x180021328`
- end: `0x180021357`
- name: `?NtFreeUserSidString@Security@Common@@YAXPEAG@Z`
- size: `47`
- prototype: `void __fastcall(PCWSTR SourceString, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001f890`
- `0x180020db0`

## callees

- `0x180021328`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180021341`
- `ntdll!RtlInitUnicodeString` at `0x180021341`
- `ntdll!RtlFreeUnicodeString` at `0x18002134c`
- `ntdll!RtlFreeUnicodeString` at `0x18002134c`

## pseudocode

```c

```
