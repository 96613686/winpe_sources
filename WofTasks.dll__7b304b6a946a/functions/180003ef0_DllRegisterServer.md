# DllRegisterServer

- ea: `0x180003ef0`
- end: `0x180003ef5`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002fd0`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CWofTasksHandler,&_GUID const CLSID_WofTasks>::DllRegisterServer();
}

```

## disassembly

```asm
0x180003ef0  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCWofTasksHandler@@$1?CLSID_WofTasks@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CWofTasksHandler,&_GUID const CLSID_WofTasks>::DllRegisterServer(void)
```
