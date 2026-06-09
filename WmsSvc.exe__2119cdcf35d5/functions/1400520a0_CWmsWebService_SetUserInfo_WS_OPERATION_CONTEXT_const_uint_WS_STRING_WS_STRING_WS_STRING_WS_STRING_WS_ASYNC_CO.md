# CWmsWebService::SetUserInfo(_WS_OPERATION_CONTEXT const *,uint *,_WS_STRING,_WS_STRING,_WS_STRING,_WS_STRING,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x1400520a0`
- end: `0x1400524ef`
- name: `?SetUserInfo@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@PEAIU_WS_STRING@@222PEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `1103`
- prototype: `__int64 __fastcall(const struct _WS_OPERATION_CONTEXT *, unsigned int *, struct _WS_STRING *, struct _WS_STRING *, struct _WS_STRING *, struct _WS_STRING *, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update`

## callees

- `0x1400016b8`
- `0x14004c43c`
- `0x14004d3dc`
- `0x1400520a0`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140065070`
- `0x14006ada4`
- `0x14006b2d0`
- `0x14006b790`
- `0x1400760c8`
- `0x140076348`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140052194`
- `KERNEL32!IsDebuggerPresent` at `0x140052194`
- `NETAPI32!NetUserSetInfo` at `0x14005237d`
- `NETAPI32!NetUserSetInfo` at `0x14005237d`
- `NETAPI32!NetApiBufferFree` at `0x1400521f2`
- `NETAPI32!NetApiBufferFree` at `0x1400521f2`
- `NETAPI32!NetUserGetInfo` at `0x1400522bb`
- `NETAPI32!NetUserGetInfo` at `0x1400522bb`
- `NETAPI32!NetLocalGroupDelMembers` at `0x140052415`
- `NETAPI32!NetLocalGroupDelMembers` at `0x14005245b`
- `NETAPI32!NetLocalGroupDelMembers` at `0x140052494`
- `NETAPI32!NetLocalGroupDelMembers` at `0x140052415`
- `NETAPI32!NetLocalGroupDelMembers` at `0x14005245b`
- `NETAPI32!NetLocalGroupDelMembers` at `0x140052494`
- `OLEAUT32!__imp_SysFreeString` at `0x140052230`
- `OLEAUT32!__imp_SysFreeString` at `0x140052239`
- `OLEAUT32!__imp_SysFreeString` at `0x140052243`
- `OLEAUT32!__imp_SysFreeString` at `0x14005224d`
- `OLEAUT32!__imp_SysFreeString` at `0x140052230`
- `OLEAUT32!__imp_SysFreeString` at `0x140052239`
- `OLEAUT32!__imp_SysFreeString` at `0x140052243`
- `OLEAUT32!__imp_SysFreeString` at `0x14005224d`
- `OLEAUT32!__imp_SysStringLen` at `0x140052211`
- `OLEAUT32!__imp_SysStringLen` at `0x140052211`

## string_xrefs

- `0x14005216d`: `termsrv\wms\src\devices\wmssvc\wmswebservice.imultipointserver.cpp`
- `0x14005215d`: `CWmsWebService::SetUserInfo`
- `0x140052177`: `fIsWmsRole || fToolsInstalled || (peType == 0) || (*peType != MogUser)`

## pseudocode

```c

```
