# TpmPolicySession::GetPolicyInfo(unsigned __int64,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x1800a89ac`
- end: `0x1800a8af9`
- name: `?GetPolicyInfo@TpmPolicySession@@YAJ_KPEBEKPEAPEAEPEAK@Z`
- size: `333`
- prototype: `__int64 __usercall@<rax>(NCRYPT_HANDLE hObject@<rcx>, PBYTE pbInput@<rdx>, DWORD cbInput@<r8d>, unsigned int@<r9d>, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047258`
- `0x18004f3f8`

## callees

- `0x18000782c`
- `0x18004d980`
- `0x1800a89ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8ac4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a8ac4`
- `ncrypt!NCryptSetProperty` at `0x1800a89d6`
- `ncrypt!NCryptSetProperty` at `0x1800a89d6`
- `ncrypt!NCryptGetProperty` at `0x1800a8a2c`
- `ncrypt!NCryptGetProperty` at `0x1800a8a8c`
- `ncrypt!NCryptGetProperty` at `0x1800a8a2c`
- `ncrypt!NCryptGetProperty` at `0x1800a8a8c`

## string_xrefs

- `0x1800a89ea`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a8a40`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a8aa0`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c

```
