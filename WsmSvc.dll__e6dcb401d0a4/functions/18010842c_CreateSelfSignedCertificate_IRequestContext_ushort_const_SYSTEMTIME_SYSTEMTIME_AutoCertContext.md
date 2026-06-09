# CreateSelfSignedCertificate(IRequestContext &,ushort const *,_SYSTEMTIME *,_SYSTEMTIME *,AutoCertContext &)

- ea: `0x18010842c`
- end: `0x180108703`
- name: `?CreateSelfSignedCertificate@@YA_NAEAVIRequestContext@@PEBGPEAU_SYSTEMTIME@@2AEAVAutoCertContext@@@Z`
- size: `727`
- prototype: `bool __fastcall(struct IRequestContext *, LPCWSTR pszX500, PSYSTEMTIME pStartTime, PSYSTEMTIME pEndTime, struct AutoCertContext *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18016b814`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180013760`
- `0x1800621e0`
- `0x18010842c`
- `0x180109050`
- `0x180112380`
- `0x1801123a8`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010868b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180108644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010868b`
- `CRYPT32!CertAddEnhancedKeyUsageIdentifier` at `0x180108681`
- `CRYPT32!CertAddEnhancedKeyUsageIdentifier` at `0x180108681`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x180108627`
- `CRYPT32!CertCreateSelfSignCertificate` at `0x180108627`
- `CRYPT32!CertStrToNameW` at `0x18010853d`
- `CRYPT32!CertStrToNameW` at `0x18010853d`

## pseudocode

```c

```
