# DllRegisterServer

- ea: `0x1800023d0`
- end: `0x1800023d5`
- name: `DllRegisterServer`
- size: `5`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001cac`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall DllRegisterServer()
{
  return CWinTaskModuleT<CReAgentTaskHandler,&_GUID const CLSID_ReAgentTaskHandler>::DllRegisterServer();
}

```

## disassembly

```asm
0x1800023d0  jmp     ?DllRegisterServer@?$CWinTaskModuleT@VCReAgentTaskHandler@@$1?CLSID_ReAgentTaskHandler@@3U_GUID@@B@@QEAAJXZ; CWinTaskModuleT<CReAgentTaskHandler,&_GUID const CLSID_ReAgentTaskHandler>::DllRegisterServer(void)
```
