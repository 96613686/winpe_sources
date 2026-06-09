# CodeAuthzpFormatIdentityKeyPath

- ea: `0x18004ca48`
- end: `0x18004cb96`
- name: `CodeAuthzpFormatIdentityKeyPath`
- size: `334`
- prototype: `__int64 __fastcall(ULONG Value, PCWSTR Source, GUID *Guid, PUNICODE_STRING Destination)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004aa98`
- `0x18004bd04`
- `0x18004be4c`
- `0x18004c398`
- `0x18004c674`

## callees

- `0x18004ca48`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x18004ca95`
- `ntdll!RtlAppendUnicodeToString` at `0x18004cb01`
- `ntdll!RtlAppendUnicodeToString` at `0x18004cb19`
- `ntdll!RtlAppendUnicodeToString` at `0x18004cb35`
- `ntdll!RtlAppendUnicodeToString` at `0x18004ca95`
- `ntdll!RtlAppendUnicodeToString` at `0x18004cb01`
- `ntdll!RtlAppendUnicodeToString` at `0x18004cb19`
- `ntdll!RtlAppendUnicodeToString` at `0x18004cb35`
- `ntdll!RtlIntegerToUnicodeString` at `0x18004cad9`
- `ntdll!RtlIntegerToUnicodeString` at `0x18004cad9`
- `ntdll!RtlStringFromGUID` at `0x18004cb4f`
- `ntdll!RtlStringFromGUID` at `0x18004cb4f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004cb69`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18004cb69`
- `ntdll!RtlFreeUnicodeString` at `0x18004cb7c`
- `ntdll!RtlFreeUnicodeString` at `0x18004cb7c`

## pseudocode

```c

```
