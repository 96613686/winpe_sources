# LogonUserCommonA

- ea: `0x18005db18`
- end: `0x18005dcb4`
- name: `LogonUserCommonA`
- size: `412`
- prototype: `__int64 __usercall@<rax>(PCSZ SourceString@<rcx>, PCSZ@<rdx>, PCSZ@<r8>, int, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005dad0`
- `0x18005dcc0`

## callees

- `0x1800380f8`
- `0x18005db18`
- `0x18007205a`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18005dc5d`
- `ntdll!RtlFreeUnicodeString` at `0x18005dc74`
- `ntdll!RtlFreeUnicodeString` at `0x18005dc99`
- `ntdll!RtlFreeUnicodeString` at `0x18005dc5d`
- `ntdll!RtlFreeUnicodeString` at `0x18005dc74`
- `ntdll!RtlFreeUnicodeString` at `0x18005dc99`
- `ntdll!RtlInitAnsiString` at `0x18005db70`
- `ntdll!RtlInitAnsiString` at `0x18005dbb3`
- `ntdll!RtlInitAnsiString` at `0x18005dbe1`
- `ntdll!RtlInitAnsiString` at `0x18005db70`
- `ntdll!RtlInitAnsiString` at `0x18005dbb3`
- `ntdll!RtlInitAnsiString` at `0x18005dbe1`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18005db87`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18005dbca`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18005dbf8`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18005db87`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18005dbca`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18005dbf8`
- `KERNEL32!BaseSetLastNTError` at `0x18005db99`
- `KERNEL32!BaseSetLastNTError` at `0x18005db99`

## pseudocode

```c

```
