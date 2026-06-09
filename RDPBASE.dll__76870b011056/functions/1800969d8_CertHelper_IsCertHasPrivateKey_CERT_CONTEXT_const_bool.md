# CertHelper::IsCertHasPrivateKey(_CERT_CONTEXT const *,bool &)

- ea: `0x1800969d8`
- end: `0x180096b01`
- name: `?IsCertHasPrivateKey@CertHelper@@YAJPEBU_CERT_CONTEXT@@AEA_N@Z`
- size: `297`
- prototype: `__int64 __fastcall(CertHelper *__hidden this, const struct _CERT_CONTEXT *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008b024`

## callees

- `0x180001aa0`
- `0x1800969d8`

## import_xrefs

- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180096ab2`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180096ab2`
- `ncrypt!NCryptFreeObject` at `0x180096ae8`
- `ncrypt!NCryptFreeObject` at `0x180096ae8`
- `ncrypt!NCryptIsKeyHandle` at `0x180096ad0`
- `ncrypt!NCryptIsKeyHandle` at `0x180096ad0`
- `CRYPTSP!CryptReleaseContext` at `0x180096ae0`
- `CRYPTSP!CryptReleaseContext` at `0x180096ae0`

## string_xrefs

- `0x180096a47`: `onecore\termsrv\rdp\win\security\certhelper.cpp`

## pseudocode

```c

```
