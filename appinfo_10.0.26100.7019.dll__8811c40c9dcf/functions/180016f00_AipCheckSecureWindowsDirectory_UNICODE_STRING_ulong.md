# AipCheckSecureWindowsDirectory(_UNICODE_STRING *,ulong *)

- ea: `0x180016f00`
- end: `0x1800170f9`
- name: `?AipCheckSecureWindowsDirectory@@YAXPEAU_UNICODE_STRING@@PEAK@Z`
- size: `505`
- prototype: `void __fastcall(struct _UNICODE_STRING *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f11c`

## callees

- `0x180016f00`
- `0x18001947c`
- `0x18002444c`

## import_xrefs

- `msvcrt!wcschr` at `0x180016fff`
- `msvcrt!wcschr` at `0x1800170c6`
- `msvcrt!wcschr` at `0x180016fff`
- `msvcrt!wcschr` at `0x1800170c6`
- `ntdll!RtlEqualUnicodeString` at `0x18001703f`
- `ntdll!RtlEqualUnicodeString` at `0x18001703f`
- `ntdll!RtlPrefixUnicodeString` at `0x180016f4f`
- `ntdll!RtlPrefixUnicodeString` at `0x180016f8f`
- `ntdll!RtlPrefixUnicodeString` at `0x180016fcf`
- `ntdll!RtlPrefixUnicodeString` at `0x18001708f`
- `ntdll!RtlPrefixUnicodeString` at `0x180016f4f`
- `ntdll!RtlPrefixUnicodeString` at `0x180016f8f`
- `ntdll!RtlPrefixUnicodeString` at `0x180016fcf`
- `ntdll!RtlPrefixUnicodeString` at `0x18001708f`

## pseudocode

```c

```
