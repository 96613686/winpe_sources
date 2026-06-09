# DllRegisterServer

- ea: `0x180030ac0`
- end: `0x180030ac5`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180029794`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CDeferredChargingTaskHandler,&_GUID const CLSID_DeferredChargingTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x180030ac0  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCDeferredChargingTaskHandler@@$1?CLSID_DeferredChargingTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CDeferredChargingTaskHandler,&_GUID const CLSID_DeferredChargingTask>::DllRegisterServer(void)
```
