# DllRegisterServer

- ea: `0x180009330`
- end: `0x180009335`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800044f8`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CPlutonTasksHandler,&_GUID const CLSID_PlutonTasks>::DllRegisterServer();
}

```

## disassembly

```asm
0x180009330  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCPlutonTasksHandler@@$1?CLSID_PlutonTasks@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CPlutonTasksHandler,&_GUID const CLSID_PlutonTasks>::DllRegisterServer(void)
```
