# CWmsWebService::GetReplacementSslCertificate(_WS_OPERATION_CONTEXT const *,uint *,uchar * *,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x14004f150`
- end: `0x14004f33c`
- name: `?GetReplacementSslCertificate@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@PEAIPEAPEAEPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(const struct _WS_OPERATION_CONTEXT *context, unsigned int *, unsigned __int8 **, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x14004c43c`
- `0x14004c738`
- `0x14004d3dc`
- `0x14004f150`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14004f221`
- `KERNEL32!IsDebuggerPresent` at `0x14004f2fe`
- `KERNEL32!IsDebuggerPresent` at `0x14004f221`
- `KERNEL32!IsDebuggerPresent` at `0x14004f2fe`
- `msvcrt!memcpy_s` at `0x14004f331`
- `msvcrt!memcpy_s` at `0x14004f331`
- `webservices!WsAlloc` at `0x14004f2ba`
- `webservices!WsAlloc` at `0x14004f2ba`
- `webservices!WsGetOperationContextProperty` at `0x14004f1d9`
- `webservices!WsGetOperationContextProperty` at `0x14004f1d9`

## string_xrefs

- `0x14004f1fe`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14004f2db`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14004f1f4`: `CWmsWebService::GetReplacementSslCertificate`
- `0x14004f2d1`: `CWmsWebService::GetReplacementSslCertificate`

## pseudocode

```c

```
