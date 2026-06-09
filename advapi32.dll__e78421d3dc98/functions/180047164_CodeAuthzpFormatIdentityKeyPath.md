# CodeAuthzpFormatIdentityKeyPath

- ea: `0x180047164`
- end: `0x18004727d`
- name: `CodeAuthzpFormatIdentityKeyPath`
- size: `281`
- prototype: `__int64 __fastcall(ULONG Value, PCWSTR Source, GUID *Guid, PUNICODE_STRING Destination)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004535c`
- `0x180046530`
- `0x18004666c`
- `0x180046b50`
- `0x180046de8`

## callees

- `0x180047164`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x1800471b1`
- `ntdll!RtlAppendUnicodeToString` at `0x18004720d`
- `ntdll!RtlAppendUnicodeToString` at `0x18004721f`
- `ntdll!RtlAppendUnicodeToString` at `0x180047235`
- `ntdll!RtlAppendUnicodeToString` at `0x1800471b1`
- `ntdll!RtlAppendUnicodeToString` at `0x18004720d`
- `ntdll!RtlAppendUnicodeToString` at `0x18004721f`
- `ntdll!RtlAppendUnicodeToString` at `0x180047235`
- `ntdll!RtlIntegerToUnicodeString` at `0x1800471ef`
- `ntdll!RtlIntegerToUnicodeString` at `0x1800471ef`
- `ntdll!RtlStringFromGUID` at `0x180047249`
- `ntdll!RtlStringFromGUID` at `0x180047249`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004725d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004725d`
- `ntdll!RtlFreeUnicodeString` at `0x18004726a`
- `ntdll!RtlFreeUnicodeString` at `0x18004726a`

## pseudocode

```c

```
