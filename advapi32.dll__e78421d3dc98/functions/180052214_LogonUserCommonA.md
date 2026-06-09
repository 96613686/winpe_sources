# LogonUserCommonA

- ea: `0x180052214`
- end: `0x180052373`
- name: `LogonUserCommonA`
- size: `351`
- prototype: `__int64 __usercall@<rax>(PCSZ SourceString@<rcx>, PCSZ@<rdx>, PCSZ@<r8>, int, int, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800521d0`
- `0x180052380`

## callees

- `0x1800344c4`
- `0x180052214`
- `0x18006505a`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18005232f`
- `ntdll!RtlFreeUnicodeString` at `0x180052340`
- `ntdll!RtlFreeUnicodeString` at `0x18005235f`
- `ntdll!RtlFreeUnicodeString` at `0x18005232f`
- `ntdll!RtlFreeUnicodeString` at `0x180052340`
- `ntdll!RtlFreeUnicodeString` at `0x18005235f`
- `ntdll!RtlInitAnsiString` at `0x18005226c`
- `ntdll!RtlInitAnsiString` at `0x18005229d`
- `ntdll!RtlInitAnsiString` at `0x1800522bf`
- `ntdll!RtlInitAnsiString` at `0x18005226c`
- `ntdll!RtlInitAnsiString` at `0x18005229d`
- `ntdll!RtlInitAnsiString` at `0x1800522bf`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18005227d`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800522ae`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800522d0`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18005227d`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800522ae`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800522d0`
- `KERNEL32!BaseSetLastNTError` at `0x180052289`
- `KERNEL32!BaseSetLastNTError` at `0x180052289`

## pseudocode

```c

```
