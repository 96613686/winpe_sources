# AipCheckSecureWindowsDirectory(_UNICODE_STRING *,ulong *)

- ea: `0x180017840`
- end: `0x1800179df`
- name: `?AipCheckSecureWindowsDirectory@@YAXPEAU_UNICODE_STRING@@PEAK@Z`
- size: `415`
- prototype: `void __fastcall(struct _UNICODE_STRING *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000f210`
- `0x18003f7ac`

## callees

- `0x180017840`
- `0x18001bab0`
- `0x180026630`

## import_xrefs

- `msvcrt!wcschr` at `0x180017919`
- `msvcrt!wcschr` at `0x1800179bb`
- `msvcrt!wcschr` at `0x180017919`
- `msvcrt!wcschr` at `0x1800179bb`
- `ntdll!RtlEqualUnicodeString` at `0x18001794f`
- `ntdll!RtlEqualUnicodeString` at `0x18001794f`
- `ntdll!RtlPrefixUnicodeString` at `0x18001787f`
- `ntdll!RtlPrefixUnicodeString` at `0x1800178af`
- `ntdll!RtlPrefixUnicodeString` at `0x1800178ef`
- `ntdll!RtlPrefixUnicodeString` at `0x18001798f`
- `ntdll!RtlPrefixUnicodeString` at `0x18001787f`
- `ntdll!RtlPrefixUnicodeString` at `0x1800178af`
- `ntdll!RtlPrefixUnicodeString` at `0x1800178ef`
- `ntdll!RtlPrefixUnicodeString` at `0x18001798f`

## pseudocode

```c

```
