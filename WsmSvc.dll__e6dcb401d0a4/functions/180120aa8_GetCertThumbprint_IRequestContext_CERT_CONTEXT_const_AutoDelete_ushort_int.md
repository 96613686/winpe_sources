# GetCertThumbprint(IRequestContext *,_CERT_CONTEXT const *,AutoDelete<ushort> &,int)

- ea: `0x180120aa8`
- end: `0x180120d7b`
- name: `?GetCertThumbprint@@YAHPEAVIRequestContext@@PEBU_CERT_CONTEXT@@AEAV?$AutoDelete@G@@H@Z`
- size: `723`
- prototype: `__int64 __fastcall(struct IRequestContext *, PCCERT_CONTEXT pCertContext)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18011ff54`
- `0x18012051c`
- `0x180120d84`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180013760`
- `0x1800621e0`
- `0x180120aa8`
- `0x1801c2010`

## import_xrefs

- `msvcrt!iswspace` at `0x180120d3c`
- `msvcrt!iswspace` at `0x180120d3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120bcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120cc6`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180120b2f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180120bb8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180120b2f`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180120bb8`
- `CRYPT32!CryptBinaryToStringW` at `0x180120c1a`
- `CRYPT32!CryptBinaryToStringW` at `0x180120cb3`
- `CRYPT32!CryptBinaryToStringW` at `0x180120c1a`
- `CRYPT32!CryptBinaryToStringW` at `0x180120cb3`

## pseudocode

```c

```
