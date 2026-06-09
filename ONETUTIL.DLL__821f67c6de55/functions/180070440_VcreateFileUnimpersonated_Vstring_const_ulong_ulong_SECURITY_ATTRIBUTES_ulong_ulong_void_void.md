# VcreateFileUnimpersonated(Vstring const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,void * *)

- ea: `0x180070440`
- end: `0x180070719`
- name: `?VcreateFileUnimpersonated@@YAPEAVVstatus@@PEBVVstring@@KKPEAU_SECURITY_ATTRIBUTES@@KKPEAXPEAPEAX@Z`
- size: `729`
- prototype: `struct Vstatus *__usercall@<rax>(const struct Vstring *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, struct _SECURITY_ATTRIBUTES *@<r9>, DWORD, unsigned int, void *, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006fb10`

## callees

- `0x18004acd0`
- `0x18006b8a4`
- `0x18006ff20`
- `0x180070440`
- `0x1800838f0`
- `0x180090560`
- `0x180095100`
- `0x1800b7a58`
- `0x1800b7b38`
- `0x1800d9fd0`
- `0x1800da020`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180070509`
- `KERNEL32!TlsGetValue` at `0x18007062a`
- `KERNEL32!TlsGetValue` at `0x180070509`
- `KERNEL32!TlsGetValue` at `0x18007062a`
- `KERNEL32!GetLastError` at `0x1800705a8`
- `KERNEL32!GetLastError` at `0x1800705a8`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800706ed`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800706ed`
- `onetnative!ULSSendTraceTag` at `0x1800705ed`
- `onetnative!ULSSendTraceTag` at `0x1800705ed`

## string_xrefs

- `0x1800705d8`: `VcreateFile(%S, %d, %d, lpSA, %d, %d, hTemplate) returned INVALID_HANDLE_VALUE; GetLastError() returned 0x%04X`

## pseudocode

```c

```
