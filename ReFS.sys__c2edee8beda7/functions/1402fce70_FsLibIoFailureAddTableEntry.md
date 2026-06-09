# FsLibIoFailureAddTableEntry

- ea: `0x1402fce70`
- end: `0x1402fd170`
- name: `FsLibIoFailureAddTableEntry`
- size: `768`
- prototype: `__int64 __fastcall(int, int, int, int, PCANSI_STRING SourceString, PCUNICODE_STRING StringIn)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1402d9e00`

## callees

- `0x1401f3d1c`
- `0x1402fce70`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1402fced4`
- `ntoskrnl!ExAcquireFastMutex` at `0x1402fced4`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402fd14b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1402fd14b`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1402fd00d`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1402fd0ef`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1402fd00d`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1402fd0ef`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1402fcfe7`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1402fd0b8`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1402fcfe7`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1402fd0b8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402fd099`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402fd0d4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402fd099`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402fd0d4`

## pseudocode

```c

```
