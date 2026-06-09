# CWebService::AddServiceEndpoint(int,ushort *,ulong,ushort *,_WS_SERVICE_CONTRACT const *,long (*)(void *,_WS_STRING const *,_WS_STRING const *,_WS_ASYNC_CONTEXT const *,_WS_ERROR *),long (*)(_WS_OPERATION_CONTEXT const *,int *,_WS_ERROR *))

- ea: `0x140007350`
- end: `0x14000776c`
- name: `?AddServiceEndpoint@CWebService@@QEAAJHPEAGK0PEBU_WS_SERVICE_CONTRACT@@P6AJPEAXPEBU_WS_STRING@@3PEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@ZP6AJPEBU_WS_OPERATION_CONTEXT@@PEAH5@Z@Z`
- size: `1052`
- prototype: `__int64 __fastcall(CWebService *__hidden this, int, unsigned __int16 *, unsigned int, unsigned __int16 *, const struct _WS_SERVICE_CONTRACT *, int (*)(void *, const struct _WS_STRING *, const struct _WS_STRING *, const struct _WS_ASYNC_CONTEXT *, struct _WS_ERROR *), int (*)(const struct _WS_OPERATION_CONTEXT *, int *, struct _WS_ERROR *))`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x14004ac94`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140007350`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140063cd0`
- `0x14007cb9e`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400074b0`
- `KERNEL32!IsDebuggerPresent` at `0x14000759e`
- `KERNEL32!IsDebuggerPresent` at `0x1400076da`
- `KERNEL32!IsDebuggerPresent` at `0x1400074b0`
- `KERNEL32!IsDebuggerPresent` at `0x14000759e`
- `KERNEL32!IsDebuggerPresent` at `0x1400076da`
- `msvcrt!wcsnlen` at `0x14000760e`
- `msvcrt!wcsnlen` at `0x14000760e`
- `msvcrt!realloc` at `0x14000743f`
- `msvcrt!realloc` at `0x140007531`
- `msvcrt!realloc` at `0x14000743f`
- `msvcrt!realloc` at `0x140007531`
- `OLEAUT32!__imp_SysFreeString` at `0x140007738`
- `OLEAUT32!__imp_SysFreeString` at `0x14000774a`
- `OLEAUT32!__imp_SysFreeString` at `0x140007738`
- `OLEAUT32!__imp_SysFreeString` at `0x14000774a`

## string_xrefs

- `0x14000747e`: `termsrv\wms\src\devices\wmssvc\cwebservice.cpp`
- `0x14000756c`: `termsrv\wms\src\devices\wmssvc\cwebservice.cpp`
- `0x1400076b4`: `termsrv\wms\src\devices\wmssvc\cwebservice.cpp`
- `0x1400076bb`: `pWmsServiceEndpoint`
- `0x140007470`: `CWebService::AddServiceEndpoint`
- `0x14000755e`: `CWebService::AddServiceEndpoint`
- `0x1400076a4`: `CWebService::AddServiceEndpoint`

## pseudocode

```c

```
