# CWmsWebServiceProxy::s_SetReplacementSslCertificate(ushort *,ulong,ushort *,ushort *,ushort *,_CERT_CONTEXT const *)

- ea: `0x140058f24`
- end: `0x14005920e`
- name: `?s_SetReplacementSslCertificate@CWmsWebServiceProxy@@SAJPEAGK000PEBU_CERT_CONTEXT@@@Z`
- size: `746`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x14002b2ac`

## callees

- `0x1400016c4`
- `0x140058f24`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140063a08`
- `0x140076988`
- `0x140076b18`
- `0x140076c98`
- `0x140077448`
- `0x14007cbd0`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140059023`
- `KERNEL32!IsDebuggerPresent` at `0x140059193`
- `KERNEL32!IsDebuggerPresent` at `0x140059023`
- `KERNEL32!IsDebuggerPresent` at `0x140059193`
- `msvcrt!memcpy_s` at `0x140059098`
- `msvcrt!memcpy_s` at `0x140059098`
- `webservices!WsAlloc` at `0x140058fda`
- `webservices!WsAlloc` at `0x140058fda`
- `webservices!WsCall` at `0x140059115`
- `webservices!WsCall` at `0x140059115`

## string_xrefs

- `0x140059177`: `pWebServiceProxy`
- `0x140058ffb`: `termsrv\wms\src\devices\wmssvc\wmswebserviceproxy.cpp`
- `0x140059170`: `termsrv\wms\src\devices\wmssvc\wmswebserviceproxy.cpp`
- `0x140058fee`: `CWmsWebServiceProxy::s_SetReplacementSslCertificate`
- `0x14005912a`: `CWmsWebServiceProxy::s_SetReplacementSslCertificate`
- `0x140059160`: `CWmsWebServiceProxy::s_SetReplacementSslCertificate`

## pseudocode

```c

```
