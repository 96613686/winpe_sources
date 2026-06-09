# NdrDllUnregisterProxy_0

- ea: `0x180002778`
- end: `0x18000277e`
- name: `NdrDllUnregisterProxy_0`
- size: `6`
- prototype: `HRESULT __stdcall(HMODULE hDll, const ProxyFileInfo **pProxyFileList, const CLSID *pclsid)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllUnregisterProxy` at `0x180002778`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall NdrDllUnregisterProxy_0(HMODULE hDll, const ProxyFileInfo **pProxyFileList, const CLSID *pclsid)
{
  return NdrDllUnregisterProxy(hDll, pProxyFileList, pclsid);
}

```

## disassembly

```asm
0x180002778  jmp     cs:__imp_NdrDllUnregisterProxy
```
