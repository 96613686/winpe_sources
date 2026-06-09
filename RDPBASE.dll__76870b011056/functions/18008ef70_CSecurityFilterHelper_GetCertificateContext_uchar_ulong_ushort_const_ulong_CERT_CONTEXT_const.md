# CSecurityFilterHelper::GetCertificateContext(uchar *,ulong,ushort const *,ulong,_CERT_CONTEXT const * *)

- ea: `0x18008ef70`
- end: `0x18008f059`
- name: `?GetCertificateContext@CSecurityFilterHelper@@EEAAJPEAEKPEBGKPEAPEBU_CERT_CONTEXT@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(CSecurityFilterHelper *__hidden this, unsigned __int8 *, unsigned int, const unsigned __int16 *, unsigned int, const struct _CERT_CONTEXT **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18008ef70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008efd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f01e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008efd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008f01e`
- `CRYPT32!CertCloseStore` at `0x18008f03f`
- `CRYPT32!CertCloseStore` at `0x18008f03f`
- `CRYPT32!CertOpenStore` at `0x18008efcb`
- `CRYPT32!CertOpenStore` at `0x18008efcb`
- `CRYPT32!CertFindCertificateInStore` at `0x18008f013`
- `CRYPT32!CertFindCertificateInStore` at `0x18008f013`

## pseudocode

```c

```
