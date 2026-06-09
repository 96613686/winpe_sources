# LookupAccountNameA

- ea: `0x1800250f0`
- end: `0x18002530b`
- name: `LookupAccountNameA`
- size: `539`
- prototype: `BOOL __stdcall(LPCSTR lpSystemName, LPCSTR lpAccountName, PSID Sid, LPDWORD cbSid, LPSTR ReferencedDomainName, LPDWORD cchReferencedDomainName, PSID_NAME_USE peUse)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002062c`
- `0x1800250f0`
- `0x1800256d8`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180025253`
- `ntdll!RtlFreeUnicodeString` at `0x180025296`
- `ntdll!RtlFreeUnicodeString` at `0x180025300`
- `ntdll!RtlFreeUnicodeString` at `0x180025253`
- `ntdll!RtlFreeUnicodeString` at `0x180025296`
- `ntdll!RtlFreeUnicodeString` at `0x180025300`
- `ntdll!RtlInitAnsiString` at `0x1800251a2`
- `ntdll!RtlInitAnsiString` at `0x18002521c`
- `ntdll!RtlInitAnsiString` at `0x1800251a2`
- `ntdll!RtlInitAnsiString` at `0x18002521c`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800252da`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800252da`
- `ntdll!RtlInitUnicodeString` at `0x1800252a8`
- `ntdll!RtlInitUnicodeString` at `0x1800252a8`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800251b3`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002522d`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800251b3`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002522d`
- `KERNELBASE!LocalAlloc` at `0x180025200`
- `KERNELBASE!LocalAlloc` at `0x180025200`
- `KERNEL32!LocalFree` at `0x1800252f1`
- `KERNEL32!LocalFree` at `0x1800252f1`
- `KERNEL32!BaseSetLastNTError` at `0x1800251f0`
- `KERNEL32!BaseSetLastNTError` at `0x180025239`
- `KERNEL32!BaseSetLastNTError` at `0x1800251f0`
- `KERNEL32!BaseSetLastNTError` at `0x180025239`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalA` at `0x18002516d`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalA` at `0x18002516d`

## pseudocode

```c

```
