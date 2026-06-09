# CWmsWebService::AdministratorPasswordValidator(void *,_WS_STRING const *,_WS_STRING const *,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x1400465f0`
- end: `0x14004680d`
- name: `?AdministratorPasswordValidator@CWmsWebService@@SAJPEAXPEBU_WS_STRING@@1PEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `541`
- prototype: `__int64 __fastcall(void *, const struct _WS_STRING *, const struct _WS_STRING *, const struct _WS_ASYNC_CONTEXT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1400465f0`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140065070`
- `0x14006c264`

## import_xrefs

- `ADVAPI32!LogonUserW` at `0x1400466ae`
- `ADVAPI32!LogonUserW` at `0x1400466ae`
- `KERNEL32!CloseHandle` at `0x1400467b8`
- `KERNEL32!CloseHandle` at `0x1400467b8`
- `KERNEL32!GetLastError` at `0x1400466bc`
- `KERNEL32!GetLastError` at `0x1400466bc`
- `KERNEL32!IsDebuggerPresent` at `0x140046714`
- `KERNEL32!IsDebuggerPresent` at `0x140046714`
- `msvcrt!wcschr` at `0x14004663a`
- `msvcrt!wcschr` at `0x140046653`
- `msvcrt!wcschr` at `0x14004663a`
- `msvcrt!wcschr` at `0x140046653`
- `OLEAUT32!__imp_SysFreeString` at `0x1400467ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1400467f7`
- `OLEAUT32!__imp_SysFreeString` at `0x1400467ca`
- `OLEAUT32!__imp_SysFreeString` at `0x1400467f7`
- `OLEAUT32!__imp_SysStringLen` at `0x1400467d8`
- `OLEAUT32!__imp_SysStringLen` at `0x1400467d8`

## string_xrefs

- `0x1400466df`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x1400466d6`: `CWmsWebService::AdministratorPasswordValidator`

## pseudocode

```c

```
