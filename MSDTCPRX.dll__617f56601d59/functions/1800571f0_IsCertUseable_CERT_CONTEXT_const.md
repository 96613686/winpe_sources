# IsCertUseable(_CERT_CONTEXT const *)

- ea: `0x1800571f0`
- end: `0x1800572f2`
- name: `?IsCertUseable@@YAKPEBU_CERT_CONTEXT@@@Z`
- size: `258`
- prototype: `unsigned int __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800572f8`
- `0x18006e22c`

## callees

- `0x180003cf0`
- `0x1800570b8`
- `0x1800571f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800572bc`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800572b2`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800572b2`
- `CRYPT32!CertVerifyTimeValidity` at `0x180057203`
- `CRYPT32!CertVerifyTimeValidity` at `0x180057203`

## string_xrefs

- `0x18005723f`: `com\complus\dtc\dtc\cm\src\certvalidationhelper.cpp`

## pseudocode

```c

```
