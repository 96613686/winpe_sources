# DllRegisterServer

- ea: `0x18000b770`
- end: `0x18000b775`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180004654`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<SetupRecoveryTaskHandler,&_GUID const CLSID_SetupRecoveryDataTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x18000b770  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VSetupRecoveryTaskHandler@@$1?CLSID_SetupRecoveryDataTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<SetupRecoveryTaskHandler,&_GUID const CLSID_SetupRecoveryDataTask>::DllRegisterServer(void)
```
