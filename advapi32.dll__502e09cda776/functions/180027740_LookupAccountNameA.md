# LookupAccountNameA

- ea: `0x180027740`
- end: `0x1800279b3`
- name: `LookupAccountNameA`
- size: `627`
- prototype: `BOOL __stdcall(LPCSTR lpSystemName, LPCSTR lpAccountName, PSID Sid, LPDWORD cbSid, LPSTR ReferencedDomainName, LPDWORD cchReferencedDomainName, PSID_NAME_USE peUse)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001f6bc`
- `0x180027740`
- `0x180027df0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800278d7`
- `ntdll!RtlFreeUnicodeString` at `0x180027920`
- `ntdll!RtlFreeUnicodeString` at `0x1800279a2`
- `ntdll!RtlFreeUnicodeString` at `0x1800278d7`
- `ntdll!RtlFreeUnicodeString` at `0x180027920`
- `ntdll!RtlFreeUnicodeString` at `0x1800279a2`
- `ntdll!RtlInitAnsiString` at `0x1800277f9`
- `ntdll!RtlInitAnsiString` at `0x18002788e`
- `ntdll!RtlInitAnsiString` at `0x1800277f9`
- `ntdll!RtlInitAnsiString` at `0x18002788e`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180027970`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180027970`
- `ntdll!RtlInitUnicodeString` at `0x180027938`
- `ntdll!RtlInitUnicodeString` at `0x180027938`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180027810`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800278a5`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180027810`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800278a5`
- `KERNELBASE!LocalAlloc` at `0x18002786c`
- `KERNELBASE!LocalAlloc` at `0x18002786c`
- `KERNEL32!LocalFree` at `0x18002798d`
- `KERNEL32!LocalFree` at `0x18002798d`
- `KERNEL32!BaseSetLastNTError` at `0x180027853`
- `KERNEL32!BaseSetLastNTError` at `0x1800278b7`
- `KERNEL32!BaseSetLastNTError` at `0x180027853`
- `KERNEL32!BaseSetLastNTError` at `0x1800278b7`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalA` at `0x1800277bd`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalA` at `0x1800277bd`

## pseudocode

```c

```
