# GetCertificateThumbprint(_CERT_CONTEXT const *,_CRYPTOAPI_BLOB *)

- ea: `0x14005a300`
- end: `0x14005a4e1`
- name: `?GetCertificateThumbprint@@YAJPEBU_CERT_CONTEXT@@PEAU_CRYPTOAPI_BLOB@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, DWORD *pcbData)`
- caller_count: `6`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140046d54`
- `0x140048d20`
- `0x14004a590`
- `0x140051b60`
- `0x14005aec4`
- `0x14005b0fc`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005a300`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005a32f`
- `KERNEL32!GetLastError` at `0x14005a342`
- `KERNEL32!GetLastError` at `0x14005a48f`
- `KERNEL32!GetLastError` at `0x14005a32f`
- `KERNEL32!GetLastError` at `0x14005a342`
- `KERNEL32!GetLastError` at `0x14005a48f`
- `KERNEL32!IsDebuggerPresent` at `0x14005a393`
- `KERNEL32!IsDebuggerPresent` at `0x14005a444`
- `KERNEL32!IsDebuggerPresent` at `0x14005a393`
- `KERNEL32!IsDebuggerPresent` at `0x14005a444`
- `CRYPT32!CertGetCertificateContextProperty` at `0x14005a321`
- `CRYPT32!CertGetCertificateContextProperty` at `0x14005a485`
- `CRYPT32!CertGetCertificateContextProperty` at `0x14005a321`
- `CRYPT32!CertGetCertificateContextProperty` at `0x14005a485`

## string_xrefs

- `0x14005a37b`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005a420`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`

## pseudocode

```c

```
