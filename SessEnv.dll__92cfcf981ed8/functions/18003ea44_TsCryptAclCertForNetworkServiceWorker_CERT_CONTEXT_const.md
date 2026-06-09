# TsCryptAclCertForNetworkServiceWorker(_CERT_CONTEXT const *)

- ea: `0x18003ea44`
- end: `0x18003ead7`
- name: `?TsCryptAclCertForNetworkServiceWorker@@YAHPEBU_CERT_CONTEXT@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x18003f194`

## callees

- `0x18003ea44`
- `0x18003eae0`

## import_xrefs

- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18003ea87`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18003ea87`
- `ncrypt!NCryptFreeObject` at `0x18003eac9`
- `ncrypt!NCryptFreeObject` at `0x18003eac9`
- `ncrypt!NCryptIsKeyHandle` at `0x18003eab0`
- `ncrypt!NCryptIsKeyHandle` at `0x18003eab0`
- `CRYPTSP!CryptReleaseContext` at `0x18003eac1`
- `CRYPTSP!CryptReleaseContext` at `0x18003eac1`

## pseudocode

```c

```
