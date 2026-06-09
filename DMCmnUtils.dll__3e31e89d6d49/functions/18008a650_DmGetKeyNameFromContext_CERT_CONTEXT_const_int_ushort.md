# DmGetKeyNameFromContext(_CERT_CONTEXT const *,int,ushort * *)

- ea: `0x18008a650`
- end: `0x18008a936`
- name: `?DmGetKeyNameFromContext@@YAJPEBU_CERT_CONTEXT@@HPEAPEAG@Z`
- size: `742`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCert, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008a440`

## callees

- `0x18005b914`
- `0x18005bd30`
- `0x18005cb4c`
- `0x1800605a8`
- `0x1800609dc`
- `0x180069ef0`
- `0x18008a650`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a89d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008a89d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008a839`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008a839`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a822`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a889`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a822`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008a889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a74e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a7bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a8b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a74e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a7bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a8b2`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18008a705`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18008a705`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18008a80e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18008a8fd`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18008a80e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18008a8fd`
- `ncrypt!NCryptFreeObject` at `0x18008a7fb`
- `ncrypt!NCryptFreeObject` at `0x18008a8ed`
- `ncrypt!NCryptFreeObject` at `0x18008a7fb`
- `ncrypt!NCryptFreeObject` at `0x18008a8ed`
- `ncrypt!NCryptGetProperty` at `0x18008a793`
- `ncrypt!NCryptGetProperty` at `0x18008a86b`
- `ncrypt!NCryptGetProperty` at `0x18008a793`
- `ncrypt!NCryptGetProperty` at `0x18008a86b`

## string_xrefs

- `0x18008a6bf`: `DmGetKeyNameFromContext: DmGetActiveUserSid`

## pseudocode

```c

```
