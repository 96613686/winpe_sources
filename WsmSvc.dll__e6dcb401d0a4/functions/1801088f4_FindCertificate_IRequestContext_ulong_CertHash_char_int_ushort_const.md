# FindCertificate(IRequestContext *,ulong,CertHash *,char *,int,ushort const *)

- ea: `0x1801088f4`
- end: `0x180109041`
- name: `?FindCertificate@@YAPEBU_CERT_CONTEXT@@PEAVIRequestContext@@KPEAVCertHash@@PEADHPEBG@Z`
- size: `1869`
- prototype: `PCCERT_CONTEXT __fastcall(struct IRequestContext *, int, struct CertHash *, char *, int, wchar_t *String2)`
- caller_count: `6`
- callee_count: `15`
- tags: ``

## callers

- `0x18006bb9c`
- `0x180108710`
- `0x18012051c`
- `0x18016b814`
- `0x18019a648`
- `0x1801a0710`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180035ee0`
- `0x1800f3b70`
- `0x1801088f4`
- `0x180109050`
- `0x180112380`
- `0x1801123a8`
- `0x1801133b0`
- `0x18011d8c0`
- `0x18011ed04`
- `0x18011ef20`
- `0x180120d84`
- `0x1801ba15e`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801089fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108e7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108f9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801089fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108e7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108f64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108f9f`
- `CRYPT32!CertCloseStore` at `0x180109013`
- `CRYPT32!CertCloseStore` at `0x180109013`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180108f1d`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180108f1d`
- `CRYPT32!CertGetNameStringW` at `0x180108ba6`
- `CRYPT32!CertGetNameStringW` at `0x180108c43`
- `CRYPT32!CertGetNameStringW` at `0x180108e0a`
- `CRYPT32!CertGetNameStringW` at `0x180108ba6`
- `CRYPT32!CertGetNameStringW` at `0x180108c43`
- `CRYPT32!CertGetNameStringW` at `0x180108e0a`
- `CRYPT32!CertFindCertificateInStore` at `0x180108aab`
- `CRYPT32!CertFindCertificateInStore` at `0x180108dbf`
- `CRYPT32!CertFindCertificateInStore` at `0x180108aab`
- `CRYPT32!CertFindCertificateInStore` at `0x180108dbf`
- `CRYPT32!CertOpenStore` at `0x1801089eb`
- `CRYPT32!CertOpenStore` at `0x1801089eb`

## string_xrefs

- `0x180108a4e`: `CertOpenStore`

## pseudocode

```c

```
