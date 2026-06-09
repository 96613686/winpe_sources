# PersistCertChainHelper(SECURITY_CACHE_LIST_ENTRY *,_CERT_CONTEXT const *)

- ea: `0x180002af4`
- end: `0x180003001`
- name: `?PersistCertChainHelper@@YAXPEAVSECURITY_CACHE_LIST_ENTRY@@PEBU_CERT_CONTEXT@@@Z`
- size: `1293`
- prototype: `void __fastcall(struct SECURITY_CACHE_LIST_ENTRY *this, PCCERT_CONTEXT pCertContext)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180002aac`
- `0x180059394`

## callees

- `0x180002af4`
- `0x180003074`
- `0x180006568`
- `0x180019f44`
- `0x180025910`
- `0x180025980`
- `0x180027ec0`
- `0x1800295b0`
- `0x1800701d0`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e2f30`
- `0x1801e3c78`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002b66`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002b66`
- `CRYPT32!CertFreeCertificateChain` at `0x180002db9`
- `CRYPT32!CertFreeCertificateChain` at `0x180002db9`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180002cdf`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180002cdf`
- `CRYPT32!CertCloseStore` at `0x180002dc4`
- `CRYPT32!CertCloseStore` at `0x180002dc4`
- `CRYPT32!CertOpenStore` at `0x180002b9e`
- `CRYPT32!CertOpenStore` at `0x180002b9e`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180002c20`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180002c20`
- `CRYPT32!CertSaveStore` at `0x180002c4e`
- `CRYPT32!CertSaveStore` at `0x180002cb9`
- `CRYPT32!CertSaveStore` at `0x180002c4e`
- `CRYPT32!CertSaveStore` at `0x180002cb9`

## pseudocode

```c

```
