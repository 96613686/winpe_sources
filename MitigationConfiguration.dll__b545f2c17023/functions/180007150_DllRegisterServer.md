# DllRegisterServer

- ea: `0x180007150`
- end: `0x180007155`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004490`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<ExploitGuardNotificationTaskHandler,&_GUID const CLSID_ExploitGuardNotificationTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x180007150  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VExploitGuardNotificationTaskHandler@@$1?CLSID_ExploitGuardNotificationTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<ExploitGuardNotificationTaskHandler,&_GUID const CLSID_ExploitGuardNotificationTask>::DllRegisterServer(void)
```
