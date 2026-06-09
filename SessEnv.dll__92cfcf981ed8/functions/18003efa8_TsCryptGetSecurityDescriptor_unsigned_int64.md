# TsCryptGetSecurityDescriptor(unsigned __int64)

- ea: `0x18003efa8`
- end: `0x18003f0aa`
- name: `?TsCryptGetSecurityDescriptor@@YAPEAU_SECURITY_DESCRIPTOR@@_K@Z`
- size: `258`
- prototype: `struct _SECURITY_DESCRIPTOR *__fastcall(NCRYPT_HANDLE hObject)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b830`
- `0x18003eae0`
- `0x18003f2e0`

## callees

- `0x18003efa8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003eff0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f055`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003eff0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f055`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f094`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f094`
- `ncrypt!NCryptIsKeyHandle` at `0x18003efbb`
- `ncrypt!NCryptIsKeyHandle` at `0x18003efbb`
- `ncrypt!NCryptGetProperty` at `0x18003f042`
- `ncrypt!NCryptGetProperty` at `0x18003f087`
- `ncrypt!NCryptGetProperty` at `0x18003f042`
- `ncrypt!NCryptGetProperty` at `0x18003f087`
- `CRYPTSP!CryptGetProvParam` at `0x18003efdb`
- `CRYPTSP!CryptGetProvParam` at `0x18003f01a`
- `CRYPTSP!CryptGetProvParam` at `0x18003efdb`
- `CRYPTSP!CryptGetProvParam` at `0x18003f01a`

## string_xrefs

- `0x18003f03b`: `Security Descr`
- `0x18003f075`: `Security Descr`

## pseudocode

```c

```
