# SafeArrayOfBstrToArrayOfWs(_WS_HEAP *,tagVARIANT *,_WS_STRING * *,uint *,_WS_ERROR *)

- ea: `0x140064b30`
- end: `0x140064db8`
- name: `?SafeArrayOfBstrToArrayOfWs@@YAJPEAU_WS_HEAP@@PEAUtagVARIANT@@PEAPEAU_WS_STRING@@PEAIPEAU_WS_ERROR@@@Z`
- size: `648`
- prototype: `__int64 __usercall@<rax>(struct _WS_HEAP *heap@<rcx>, struct tagVARIANT *@<rdx>, struct _WS_STRING **@<r8>, unsigned int *@<r9>, struct _WS_ERROR *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004edb0`
- `0x14004ef80`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140063a08`
- `0x140064b30`
- `0x14007cb9e`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140064bba`
- `KERNEL32!IsDebuggerPresent` at `0x140064ca5`
- `KERNEL32!IsDebuggerPresent` at `0x140064bba`
- `KERNEL32!IsDebuggerPresent` at `0x140064ca5`
- `OLEAUT32!__imp_SysFreeString` at `0x140064d6f`
- `OLEAUT32!__imp_SysFreeString` at `0x140064d98`
- `OLEAUT32!__imp_SysFreeString` at `0x140064d6f`
- `OLEAUT32!__imp_SysFreeString` at `0x140064d98`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x140064c30`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x140064c30`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x140064cd5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x140064cd5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x140064c5d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x140064c5d`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x140064d41`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x140064d41`
- `webservices!WsAlloc` at `0x140064d06`
- `webservices!WsAlloc` at `0x140064d06`

## string_xrefs

- `0x140064b9a`: `termsrv\wms\src\common\srcutils\wsutils.cpp`
- `0x140064c84`: `termsrv\wms\src\common\srcutils\wsutils.cpp`

## pseudocode

```c

```
