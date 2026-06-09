# GetLogonBlobForCertValidation(ushort *,ulong *,uchar *)

- ea: `0x1800ee0b4`
- end: `0x1800ee568`
- name: `?GetLogonBlobForCertValidation@@YAJPEAGPEAKPEAE@Z`
- size: `1204`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800f2dd8`

## callees

- `0x180002550`
- `0x180004a94`
- `0x180079600`
- `0x180079618`
- `0x18007969c`
- `0x1800ec828`
- `0x1800ee0b4`
- `0x1801614c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee1e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee1e1`
- `CRYPT32!CertCloseStore` at `0x1800ee537`
- `CRYPT32!CertCloseStore` at `0x1800ee537`
- `CRYPT32!CertOpenStore` at `0x1800ee18f`
- `CRYPT32!CertOpenStore` at `0x1800ee18f`
- `CRYPT32!CertFindCertificateInStore` at `0x1800ee1cd`
- `CRYPT32!CertFindCertificateInStore` at `0x1800ee1cd`
- `CRYPT32!CertFreeCertificateContext` at `0x1800ee545`
- `CRYPT32!CertFreeCertificateContext` at `0x1800ee545`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800ee27b`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800ee314`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800ee27b`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800ee314`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x1800ee10b`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x1800ee10b`

## pseudocode

```c

```
