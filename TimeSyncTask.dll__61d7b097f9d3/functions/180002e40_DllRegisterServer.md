# DllRegisterServer

- ea: `0x180002e40`
- end: `0x180002e45`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002520`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CTimeSyncTaskHandler,&_GUID const CLSID_TimeSyncTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x180002e40  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCTimeSyncTaskHandler@@$1?CLSID_TimeSyncTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CTimeSyncTaskHandler,&_GUID const CLSID_TimeSyncTask>::DllRegisterServer(void)
```
