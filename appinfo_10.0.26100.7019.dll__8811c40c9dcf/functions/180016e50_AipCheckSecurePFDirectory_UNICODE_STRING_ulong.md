# AipCheckSecurePFDirectory(_UNICODE_STRING *,ulong *)

- ea: `0x180016e50`
- end: `0x180016ef0`
- name: `?AipCheckSecurePFDirectory@@YAXPEAU_UNICODE_STRING@@PEAK@Z`
- size: `160`
- prototype: `void __fastcall(PCUNICODE_STRING String2, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f11c`

## callees

- `0x180016e50`
- `0x18002444c`

## import_xrefs

- `ntdll!RtlPrefixUnicodeString` at `0x180016e8d`
- `ntdll!RtlPrefixUnicodeString` at `0x180016ec2`
- `ntdll!RtlPrefixUnicodeString` at `0x180016e8d`
- `ntdll!RtlPrefixUnicodeString` at `0x180016ec2`

## pseudocode

```c

```
