# DllRegisterServer

- ea: `0x18000fa40`
- end: `0x18000fa45`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800075b4`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CAppListBackupLauncher,&_GUID const CLSID_AppListBackupLauncher>::DllRegisterServer();
}

```

## disassembly

```asm
0x18000fa40  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCAppListBackupLauncher@@$1?CLSID_AppListBackupLauncher@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CAppListBackupLauncher,&_GUID const CLSID_AppListBackupLauncher>::DllRegisterServer(void)
```
