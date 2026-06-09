# CWmsWebServiceProxy::s_SetSslCertificate(ushort *,ushort *,ushort *,ulong)

- ea: `0x140059214`
- end: `0x1400595e3`
- name: `?s_SetSslCertificate@CWmsWebServiceProxy@@SAJPEAG00K@Z`
- size: `975`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task`

## callers

- `0x140016500`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140059214`
- `0x140059ec0`
- `0x14005a4e8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140063a08`
- `0x140064148`
- `0x140064644`
- `0x140064dc0`
- `0x140076988`
- `0x140076b18`
- `0x140076c98`
- `0x140077448`
- `0x14007cbd0`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140059374`
- `KERNEL32!IsDebuggerPresent` at `0x14005950d`
- `KERNEL32!IsDebuggerPresent` at `0x140059374`
- `KERNEL32!IsDebuggerPresent` at `0x14005950d`
- `msvcrt!memcpy_s` at `0x1400593c7`
- `msvcrt!memcpy_s` at `0x1400593c7`
- `CRYPT32!CertFreeCertificateContext` at `0x1400595bb`
- `CRYPT32!CertFreeCertificateContext` at `0x1400595bb`
- `OLEAUT32!__imp_SysFreeString` at `0x140059584`
- `OLEAUT32!__imp_SysFreeString` at `0x140059584`
- `webservices!WsAlloc` at `0x140059334`
- `webservices!WsAlloc` at `0x140059334`
- `webservices!WsCall` at `0x1400594a8`
- `webservices!WsCall` at `0x1400594a8`

## string_xrefs

- `0x1400594d3`: `pWebServiceProxy`
- `0x140059515`: `pWebServiceProxy`
- `0x140059355`: `termsrv\wms\src\devices\wmssvc\wmswebserviceproxy.cpp`
- `0x1400594ea`: `termsrv\wms\src\devices\wmssvc\wmswebserviceproxy.cpp`
- `0x140059344`: `CWmsWebServiceProxy::s_SetSslCertificate`
- `0x1400594bd`: `CWmsWebServiceProxy::s_SetSslCertificate`
- `0x1400594df`: `CWmsWebServiceProxy::s_SetSslCertificate`

## pseudocode

```c

```
