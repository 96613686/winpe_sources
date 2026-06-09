# DllUnregisterServer

- ea: `0x180009340`
- end: `0x180009345`
- name: `DllUnregisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800046e4`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllUnregisterServer()
{
  return CWinTaskModuleT<CPlutonTasksHandler,&_GUID const CLSID_PlutonTasks>::DllUnregisterServer();
}

```

## disassembly

```asm
0x180009340  jmp     ?DllUnregisterServer@?$CWinTaskModuleT@VCPlutonTasksHandler@@$1?CLSID_PlutonTasks@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CPlutonTasksHandler,&_GUID const CLSID_PlutonTasks>::DllUnregisterServer(void)
```
