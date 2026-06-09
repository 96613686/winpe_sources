# AipCheckSecurePFDirectory(_UNICODE_STRING *,ulong *)

- ea: `0x180017108`
- end: `0x1800171a8`
- name: `?AipCheckSecurePFDirectory@@YAXPEAU_UNICODE_STRING@@PEAK@Z`
- size: `160`
- prototype: `void __fastcall(PCUNICODE_STRING String2, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f24c`

## callees

- `0x180017108`
- `0x180022bb0`

## import_xrefs

- `ntdll!RtlPrefixUnicodeString` at `0x180017145`
- `ntdll!RtlPrefixUnicodeString` at `0x18001717a`
- `ntdll!RtlPrefixUnicodeString` at `0x180017145`
- `ntdll!RtlPrefixUnicodeString` at `0x18001717a`

## pseudocode

```c

```
