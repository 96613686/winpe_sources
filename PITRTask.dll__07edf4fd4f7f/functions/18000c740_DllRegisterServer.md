# DllRegisterServer

- ea: `0x18000c740`
- end: `0x18000c745`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004bd4`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CPITRTaskHandler,&_GUID const CLSID_PITRTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x18000c740  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCPITRTaskHandler@@$1?CLSID_PITRTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CPITRTaskHandler,&_GUID const CLSID_PITRTask>::DllRegisterServer(void)
```
