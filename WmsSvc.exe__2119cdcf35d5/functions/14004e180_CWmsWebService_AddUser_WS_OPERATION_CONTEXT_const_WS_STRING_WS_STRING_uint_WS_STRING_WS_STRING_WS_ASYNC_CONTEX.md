# CWmsWebService::AddUser(_WS_OPERATION_CONTEXT const *,_WS_STRING,_WS_STRING,uint,_WS_STRING,_WS_STRING,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x14004e180`
- end: `0x14004e510`
- name: `?AddUser@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@U_WS_STRING@@1I11PEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `912`
- prototype: `__int64 __fastcall(const struct _WS_OPERATION_CONTEXT *, struct _WS_STRING *, struct _WS_STRING *, int, struct _WS_STRING *, struct _WS_STRING *, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update`

## callees

- `0x1400016b8`
- `0x14004c43c`
- `0x14004d3dc`
- `0x14004e180`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140065070`
- `0x14006ada4`
- `0x14006b2d0`
- `0x1400760c8`
- `0x140076348`
- `0x14007cb9e`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14004e3be`
- `KERNEL32!IsDebuggerPresent` at `0x14004e3be`
- `NETAPI32!NetUserAdd` at `0x14004e2ac`
- `NETAPI32!NetUserAdd` at `0x14004e2ac`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e4d2`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e4db`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e4e4`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e4ed`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e4d2`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e4db`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e4e4`
- `OLEAUT32!__imp_SysFreeString` at `0x14004e4ed`
- `OLEAUT32!__imp_SysStringLen` at `0x14004e4b3`
- `OLEAUT32!__imp_SysStringLen` at `0x14004e4b3`

## string_xrefs

- `0x14004e3b2`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14004e3da`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14004e414`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14004e3ab`: `CWmsWebService::AddUser`
- `0x14004e3c6`: `CWmsWebService::AddUser`
- `0x14004e386`: `fIsWmsRole || fToolsInstalled || (eType != EUserType::MogUser)`
- `0x14004e3cd`: `fIsWmsRole || fToolsInstalled || (eType != EUserType::MogUser)`

## pseudocode

```c

```
