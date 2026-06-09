# AipCheckSecurePFDirectory(_UNICODE_STRING *,ulong *)

- ea: `0x1800177a4`
- end: `0x180017837`
- name: `?AipCheckSecurePFDirectory@@YAXPEAU_UNICODE_STRING@@PEAK@Z`
- size: `147`
- prototype: `void __fastcall(PCUNICODE_STRING String2, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f210`
- `0x18003f7ac`

## callees

- `0x1800177a4`
- `0x180026630`

## import_xrefs

- `ntdll!RtlPrefixUnicodeString` at `0x1800177e1`
- `ntdll!RtlPrefixUnicodeString` at `0x180017810`
- `ntdll!RtlPrefixUnicodeString` at `0x1800177e1`
- `ntdll!RtlPrefixUnicodeString` at `0x180017810`

## pseudocode

```c

```
