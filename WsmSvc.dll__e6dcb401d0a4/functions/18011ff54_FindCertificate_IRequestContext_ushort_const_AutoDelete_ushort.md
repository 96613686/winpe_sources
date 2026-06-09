# FindCertificate(IRequestContext *,ushort const *,AutoDelete<ushort> &)

- ea: `0x18011ff54`
- end: `0x180120513`
- name: `?FindCertificate@@YAHPEAVIRequestContext@@PEBGAEAV?$AutoDelete@G@@@Z`
- size: `1471`
- prototype: `__int64 __fastcall(struct IRequestContext *, __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180043c10`
- `0x180106594`
- `0x180198cb0`
- `0x180199718`
- `0x1801adb7c`

## callees

- `0x180005d10`
- `0x180112380`
- `0x180112460`
- `0x1801133b0`
- `0x18011a6d4`
- `0x18011ff54`
- `0x180120aa8`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801200ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801201f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801203c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801200ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801201f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180120259`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801203c8`
- `CRYPT32!CertFreeCertificateContext` at `0x18012048f`
- `CRYPT32!CertFreeCertificateContext` at `0x18012048f`
- `CRYPT32!CertFreeCertificateChain` at `0x18012010b`
- `CRYPT32!CertFreeCertificateChain` at `0x1801204e1`
- `CRYPT32!CertFreeCertificateChain` at `0x18012010b`
- `CRYPT32!CertFreeCertificateChain` at `0x1801204e1`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180120351`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180120351`
- `CRYPT32!CertGetCertificateChain` at `0x180120231`
- `CRYPT32!CertGetCertificateChain` at `0x180120231`
- `CRYPT32!CertCloseStore` at `0x1801204f0`
- `CRYPT32!CertCloseStore` at `0x1801204f0`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1801201a2`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1801201a2`
- `CRYPT32!CertFindCertificateInStore` at `0x180120137`
- `CRYPT32!CertFindCertificateInStore` at `0x180120137`
- `CRYPT32!CertOpenStore` at `0x180120072`
- `CRYPT32!CertOpenStore` at `0x180120072`

## string_xrefs

- `0x1801200d4`: `CertOpenStore`

## pseudocode

```c

```
