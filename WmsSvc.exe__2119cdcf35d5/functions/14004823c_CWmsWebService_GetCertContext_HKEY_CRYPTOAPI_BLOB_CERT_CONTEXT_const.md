# CWmsWebService::GetCertContext(HKEY__ *,_CRYPTOAPI_BLOB *,_CERT_CONTEXT const * *)

- ea: `0x14004823c`
- end: `0x1400483d7`
- name: `?GetCertContext@CWmsWebService@@AEAAJPEAUHKEY__@@PEAU_CRYPTOAPI_BLOB@@PEAPEBU_CERT_CONTEXT@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(CWmsWebService *this, HKEY, struct _CRYPTOAPI_BLOB *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x140048d20`

## callees

- `0x140046c2c`
- `0x14004823c`
- `0x14004c52c`
- `0x140059ec0`
- `0x14005a10c`
- `0x14005bc30`
- `0x14006440c`
- `0x140064644`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140048315`
- `KERNEL32!CompareStringW` at `0x140048315`
- `CRYPT32!CertFreeCertificateContext` at `0x140048339`
- `CRYPT32!CertFreeCertificateContext` at `0x1400483b7`
- `CRYPT32!CertFreeCertificateContext` at `0x140048339`
- `CRYPT32!CertFreeCertificateContext` at `0x1400483b7`
- `OLEAUT32!__imp_SysFreeString` at `0x14004839f`
- `OLEAUT32!__imp_SysFreeString` at `0x1400483a8`
- `OLEAUT32!__imp_SysFreeString` at `0x14004839f`
- `OLEAUT32!__imp_SysFreeString` at `0x1400483a8`
- `OLEAUT32!__imp_SysStringLen` at `0x1400482e0`
- `OLEAUT32!__imp_SysStringLen` at `0x1400482ec`
- `OLEAUT32!__imp_SysStringLen` at `0x1400482e0`
- `OLEAUT32!__imp_SysStringLen` at `0x1400482ec`

## string_xrefs

- `0x140048293`: `CWmsWebService::GetCertContext - cert thumbprint not found in certificate store, creating new cert.\n`
- `0x140048327`: `CWmsWebService::GetCertContext - cert thumbprint has subject name %s, hostname is %s, creating new cert.\n`

## pseudocode

```c

```
