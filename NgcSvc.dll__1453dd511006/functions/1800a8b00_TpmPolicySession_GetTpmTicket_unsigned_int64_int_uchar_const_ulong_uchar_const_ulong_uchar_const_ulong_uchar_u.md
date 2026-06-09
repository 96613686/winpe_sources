# TpmPolicySession::GetTpmTicket(unsigned __int64,int,uchar const *,ulong,uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x1800a8b00`
- end: `0x1800a8d45`
- name: `?GetTpmTicket@TpmPolicySession@@YAJ_KHPEBEK1K1KPEAPEAEPEAK@Z`
- size: `581`
- prototype: `__int64 __usercall@<rax>(NCRYPT_HANDLE hObject@<rcx>, unsigned __int64@<rdx>, int@<r8d>, const unsigned __int8 *@<r9>, void *Source, rsize_t SourceSize, void *, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004f3f8`
- `0x18004faf0`

## callees

- `0x18000782c`
- `0x18002ab60`
- `0x180050b30`
- `0x18005cee0`
- `0x18005dd44`
- `0x1800a8430`
- `0x1800a8b00`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x1800a8bed`
- `ncrypt!NCryptSetProperty` at `0x1800a8bed`
- `ncrypt!NCryptGetProperty` at `0x1800a8c40`
- `ncrypt!NCryptGetProperty` at `0x1800a8ca0`
- `ncrypt!NCryptGetProperty` at `0x1800a8c40`
- `ncrypt!NCryptGetProperty` at `0x1800a8ca0`

## string_xrefs

- `0x1800a8c04`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a8c57`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a8cb7`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`
- `0x1800a8d09`: `onecore\ds\security\biometrics\service\trustlet\lib\tpmpolicysession.cpp`

## pseudocode

```c

```
