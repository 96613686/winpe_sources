# KerbCompareDomains(_UNICODE_STRING *,_UNICODE_STRING *,ulong *)

- ea: `0x180067e10`
- end: `0x180067f0f`
- name: `?KerbCompareDomains@@YA?AW4_KERB_DOMAIN_COMPARISON@@PEAU_UNICODE_STRING@@0PEAK@Z`
- size: `255`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800676b0`
- `0x180067c28`

## callees

- `0x180067e10`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180067e62`
- `ntdll!RtlEqualUnicodeString` at `0x180067eb8`
- `ntdll!RtlEqualUnicodeString` at `0x180067ee3`
- `ntdll!RtlEqualUnicodeString` at `0x180067e62`
- `ntdll!RtlEqualUnicodeString` at `0x180067eb8`
- `ntdll!RtlEqualUnicodeString` at `0x180067ee3`

## pseudocode

```c

```
