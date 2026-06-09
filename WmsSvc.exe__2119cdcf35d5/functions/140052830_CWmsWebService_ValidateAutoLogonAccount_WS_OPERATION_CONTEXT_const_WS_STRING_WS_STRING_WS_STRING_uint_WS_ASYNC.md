# CWmsWebService::ValidateAutoLogonAccount(_WS_OPERATION_CONTEXT const *,_WS_STRING,_WS_STRING,_WS_STRING,uint *,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x140052830`
- end: `0x1400529a0`
- name: `?ValidateAutoLogonAccount@CWmsWebService@@SAJPEBU_WS_OPERATION_CONTEXT@@U_WS_STRING@@11PEAIPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(const struct _WS_OPERATION_CONTEXT *, struct _WS_STRING *, struct _WS_STRING *, struct _WS_STRING *, unsigned int *, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x14004c43c`
- `0x14004d3dc`
- `0x140052830`
- `0x140065070`
- `0x14006c264`

## import_xrefs

- `ADVAPI32!LogonUserW` at `0x1400528d6`
- `ADVAPI32!LogonUserW` at `0x1400528d6`
- `KERNEL32!CloseHandle` at `0x14005298b`
- `KERNEL32!CloseHandle` at `0x14005298b`
- `OLEAUT32!__imp_SysFreeString` at `0x140052963`
- `OLEAUT32!__imp_SysFreeString` at `0x14005296d`
- `OLEAUT32!__imp_SysFreeString` at `0x140052977`
- `OLEAUT32!__imp_SysFreeString` at `0x140052963`
- `OLEAUT32!__imp_SysFreeString` at `0x14005296d`
- `OLEAUT32!__imp_SysFreeString` at `0x140052977`
- `OLEAUT32!__imp_SysStringLen` at `0x140052944`
- `OLEAUT32!__imp_SysStringLen` at `0x140052944`

## pseudocode

```c

```
