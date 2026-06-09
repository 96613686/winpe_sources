# AipCheckSecureWindowsDirectory(_UNICODE_STRING *,ulong *)

- ea: `0x1800171b0`
- end: `0x1800173a9`
- name: `?AipCheckSecureWindowsDirectory@@YAXPEAU_UNICODE_STRING@@PEAK@Z`
- size: `505`
- prototype: `void __fastcall(struct _UNICODE_STRING *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f24c`

## callees

- `0x1800171b0`
- `0x18001984c`
- `0x180022bb0`

## import_xrefs

- `msvcrt!wcschr` at `0x1800172af`
- `msvcrt!wcschr` at `0x180017376`
- `msvcrt!wcschr` at `0x1800172af`
- `msvcrt!wcschr` at `0x180017376`
- `ntdll!RtlEqualUnicodeString` at `0x1800172ef`
- `ntdll!RtlEqualUnicodeString` at `0x1800172ef`
- `ntdll!RtlPrefixUnicodeString` at `0x1800171ff`
- `ntdll!RtlPrefixUnicodeString` at `0x18001723f`
- `ntdll!RtlPrefixUnicodeString` at `0x18001727f`
- `ntdll!RtlPrefixUnicodeString` at `0x18001733f`
- `ntdll!RtlPrefixUnicodeString` at `0x1800171ff`
- `ntdll!RtlPrefixUnicodeString` at `0x18001723f`
- `ntdll!RtlPrefixUnicodeString` at `0x18001727f`
- `ntdll!RtlPrefixUnicodeString` at `0x18001733f`

## pseudocode

```c

```
