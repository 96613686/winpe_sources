# VmMigrationTcpTransport::GetLmEncryptionCertFromStore(_CERT_CONTEXT const * *)

- ea: `0x1400faeb0`
- end: `0x1400fb044`
- name: `?GetLmEncryptionCertFromStore@VmMigrationTcpTransport@@UEAAJPEAPEBU_CERT_CONTEXT@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, const struct _CERT_CONTEXT **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140042240`
- `0x1400549dc`
- `0x14006af38`
- `0x1400faeb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fafae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400faffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fafae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400faffb`
- `CRYPT32!CertFindCertificateInStore` at `0x1400faf56`
- `CRYPT32!CertFindCertificateInStore` at `0x1400faf56`
- `CRYPT32!CertCloseStore` at `0x1400fafce`
- `CRYPT32!CertCloseStore` at `0x1400fafce`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1400faf9a`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1400faf9a`
- `CRYPT32!CertOpenStore` at `0x1400faf12`
- `CRYPT32!CertOpenStore` at `0x1400faf12`

## string_xrefs

- `0x1400fafe3`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c

```
