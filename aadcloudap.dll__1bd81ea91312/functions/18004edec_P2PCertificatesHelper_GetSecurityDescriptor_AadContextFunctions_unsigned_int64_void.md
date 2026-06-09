# P2PCertificatesHelper::GetSecurityDescriptor(AadContextFunctions *,unsigned __int64,void * *)

- ea: `0x18004edec`
- end: `0x18004f12b`
- name: `?GetSecurityDescriptor@P2PCertificatesHelper@@CAJPEAVAadContextFunctions@@_KPEAPEAX@Z`
- size: `831`
- prototype: `static int(struct AadContextFunctions *, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004e2b8`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x18004edec`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ef68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ee93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ef68`
- `ncrypt!NCryptGetProperty` at `0x18004efa5`
- `ncrypt!NCryptGetProperty` at `0x18004f040`
- `ncrypt!NCryptGetProperty` at `0x18004efa5`
- `ncrypt!NCryptGetProperty` at `0x18004f040`
- `ncrypt!NCryptIsKeyHandle` at `0x18004ee63`
- `ncrypt!NCryptIsKeyHandle` at `0x18004ee63`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x18004ee89`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x18004ef5a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x18004ee89`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetProvParam` at `0x18004ef5a`

## string_xrefs

- `0x18004ef9e`: `Security Descr`
- `0x18004f036`: `Security Descr`
- `0x18004ee23`: `P2PCertificatesHelper::GetSecurityDescriptor`

## pseudocode

```c

```
