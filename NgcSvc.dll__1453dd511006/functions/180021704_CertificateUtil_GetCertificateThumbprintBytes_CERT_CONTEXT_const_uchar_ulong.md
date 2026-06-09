# CertificateUtil::GetCertificateThumbprintBytes(_CERT_CONTEXT const *,uchar * *,ulong *)

- ea: `0x180021704`
- end: `0x180021940`
- name: `?GetCertificateThumbprintBytes@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAEPEAK@Z`
- size: `572`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002055c`

## callees

- `0x18001eb00`
- `0x180021704`
- `0x18004a8ec`
- `0x18004aa08`
- `0x18004d79c`
- `0x18005cee0`
- `0x18005db30`
- `0x1800606dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218db`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002188a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800218d1`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18002188a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800218d1`

## string_xrefs

- `0x1800217be`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x1800217b7`: `EventWriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c

```
