# CWmsWebService::GetPeerWmsServerList(_WS_OPERATION_CONTEXT const *,uint *,_WS_STRING * *,uint *,_WS_STRING * *,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x14004ef80`
- end: `0x14004f148`
- name: `?GetPeerWmsServerList@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@PEAIPEAPEAU_WS_STRING@@12PEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `456`
- prototype: `__int64 __fastcall(const struct _WS_OPERATION_CONTEXT *, unsigned int *, struct _WS_STRING **, unsigned int *, struct _WS_STRING **, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *error)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x14004c43c`
- `0x14004d3dc`
- `0x14004ef80`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140064b30`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14004f052`
- `KERNEL32!IsDebuggerPresent` at `0x14004f052`
- `OLEAUT32!__imp_VariantInit` at `0x14004efc9`
- `OLEAUT32!__imp_VariantInit` at `0x14004efd3`
- `OLEAUT32!__imp_VariantInit` at `0x14004efc9`
- `OLEAUT32!__imp_VariantInit` at `0x14004efd3`
- `OLEAUT32!__imp_VariantClear` at `0x14004f122`
- `OLEAUT32!__imp_VariantClear` at `0x14004f12c`
- `OLEAUT32!__imp_VariantClear` at `0x14004f122`
- `OLEAUT32!__imp_VariantClear` at `0x14004f12c`
- `webservices!WsGetOperationContextProperty` at `0x14004f008`
- `webservices!WsGetOperationContextProperty` at `0x14004f008`

## string_xrefs

- `0x14004f02f`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14004f023`: `CWmsWebService::GetPeerWmsServerList`

## pseudocode

```c

```
