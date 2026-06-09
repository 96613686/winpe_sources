# GetCertificateSubjectName(_CERT_CONTEXT const *,ushort * *)

- ea: `0x14005a10c`
- end: `0x14005a2f7`
- name: `?GetCertificateSubjectName@@YAJPEBU_CERT_CONTEXT@@PEAPEAG@Z`
- size: `491`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14004823c`
- `0x14005b418`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005a10c`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14005a1c5`
- `KERNEL32!IsDebuggerPresent` at `0x14005a299`
- `KERNEL32!IsDebuggerPresent` at `0x14005a1c5`
- `KERNEL32!IsDebuggerPresent` at `0x14005a299`
- `CRYPT32!CertGetNameStringW` at `0x14005a14b`
- `CRYPT32!CertGetNameStringW` at `0x14005a232`
- `CRYPT32!CertGetNameStringW` at `0x14005a14b`
- `CRYPT32!CertGetNameStringW` at `0x14005a232`
- `OLEAUT32!__imp_SysAllocString` at `0x14005a24b`
- `OLEAUT32!__imp_SysAllocString` at `0x14005a24b`

## string_xrefs

- `0x14005a1af`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005a1e0`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005a283`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`
- `0x14005a2bf`: `termsrv\wms\src\devices\wmssvc\wmswebserviceutils.cpp`

## pseudocode

```c

```
