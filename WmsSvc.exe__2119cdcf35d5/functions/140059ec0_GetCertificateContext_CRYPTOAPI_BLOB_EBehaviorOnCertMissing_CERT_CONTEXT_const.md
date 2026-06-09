# GetCertificateContext(_CRYPTOAPI_BLOB *,EBehaviorOnCertMissing,_CERT_CONTEXT const * *)

- ea: `0x140059ec0`
- end: `0x14005a106`
- name: `?GetCertificateContext@@YAJPEAU_CRYPTOAPI_BLOB@@W4EBehaviorOnCertMissing@@PEAPEBU_CERT_CONTEXT@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(const void *, int, PCCERT_CONTEXT *)`
- caller_count: `8`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000308c`
- `0x140023030`
- `0x140026298`
- `0x14004823c`
- `0x14004a590`
- `0x14004c738`
- `0x140050720`
- `0x140059214`

## callees

- `0x140059ec0`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140059f0a`
- `KERNEL32!GetLastError` at `0x140059ff3`
- `KERNEL32!GetLastError` at `0x14005a013`
- `KERNEL32!GetLastError` at `0x14005a033`
- `KERNEL32!GetLastError` at `0x140059f0a`
- `KERNEL32!GetLastError` at `0x140059ff3`
- `KERNEL32!GetLastError` at `0x14005a013`
- `KERNEL32!GetLastError` at `0x14005a033`
- `KERNEL32!IsDebuggerPresent` at `0x140059f65`
- `KERNEL32!IsDebuggerPresent` at `0x14005a08a`
- `KERNEL32!IsDebuggerPresent` at `0x140059f65`
- `KERNEL32!IsDebuggerPresent` at `0x14005a08a`
- `CRYPT32!CertFindCertificateInStore` at `0x140059fe4`
- `CRYPT32!CertFindCertificateInStore` at `0x140059fe4`
- `CRYPT32!CertCloseStore` at `0x14005a0ef`
- `CRYPT32!CertCloseStore` at `0x14005a0ef`
- `CRYPT32!CertOpenStore` at `0x140059ef8`
- `CRYPT32!CertOpenStore` at `0x140059ef8`

## string_xrefs

- `0x140059eda`: `MultiPoint Services Certificates`
- `0x140059f3a`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005a05f`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`

## pseudocode

```c

```
