# DllRegisterServer

- ea: `0x18000c590`
- end: `0x18000c595`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002900`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CTempSignedLicenseExchangeTaskHandler,&_GUID const CLSID_TempSignedLicenseExchangeTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x18000c590  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCTempSignedLicenseExchangeTaskHandler@@$1?CLSID_TempSignedLicenseExchangeTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CTempSignedLicenseExchangeTaskHandler,&_GUID const CLSID_TempSignedLicenseExchangeTask>::DllRegisterServer(void)
```
