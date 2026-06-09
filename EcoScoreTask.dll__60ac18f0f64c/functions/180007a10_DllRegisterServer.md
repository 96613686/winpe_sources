# DllRegisterServer

- ea: `0x180007a10`
- end: `0x180007a15`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003ee0`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CEcoScoreTaskHandler,&_GUID const CLSID_EcoScoreTask>::DllRegisterServer();
}

```

## disassembly

```asm
0x180007a10  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCEcoScoreTaskHandler@@$1?CLSID_EcoScoreTask@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CEcoScoreTaskHandler,&_GUID const CLSID_EcoScoreTask>::DllRegisterServer(void)
```
