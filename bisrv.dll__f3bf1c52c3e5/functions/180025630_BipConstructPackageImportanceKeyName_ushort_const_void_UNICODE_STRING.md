# BipConstructPackageImportanceKeyName(ushort const *,void *,_UNICODE_STRING *)

- ea: `0x180025630`
- end: `0x1800257f4`
- name: `?BipConstructPackageImportanceKeyName@@YAJPEBGPEAXPEAU_UNICODE_STRING@@@Z`
- size: `452`
- prototype: `__int64 __fastcall(PCWSTR Source, PSID Sid, PUNICODE_STRING Destination)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180023a78`
- `0x180024240`
- `0x1800251f8`

## callees

- `0x180025630`
- `0x180049844`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x180025682`
- `ntdll!RtlAppendUnicodeToString` at `0x1800256a6`
- `ntdll!RtlAppendUnicodeToString` at `0x1800256d0`
- `ntdll!RtlAppendUnicodeToString` at `0x1800256e6`
- `ntdll!RtlAppendUnicodeToString` at `0x1800256fc`
- `ntdll!RtlAppendUnicodeToString` at `0x180025682`
- `ntdll!RtlAppendUnicodeToString` at `0x1800256a6`
- `ntdll!RtlAppendUnicodeToString` at `0x1800256d0`
- `ntdll!RtlAppendUnicodeToString` at `0x1800256e6`
- `ntdll!RtlAppendUnicodeToString` at `0x1800256fc`
- `ntdll!RtlFreeHeap` at `0x1800257e1`
- `ntdll!RtlFreeHeap` at `0x1800257e1`
- `ntdll!RtlAllocateHeap` at `0x180025665`
- `ntdll!RtlAllocateHeap` at `0x180025665`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800256be`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800256be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025718`

## pseudocode

```c

```
