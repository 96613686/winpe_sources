# NdrDllRegisterProxy_0

- ea: `0x180002492`
- end: `0x180002498`
- name: `NdrDllRegisterProxy_0`
- size: `6`
- prototype: `HRESULT __stdcall(HMODULE hDll, const ProxyFileInfo **pProxyFileList, const CLSID *pclsid)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllRegisterProxy` at `0x180002492`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall NdrDllRegisterProxy_0(HMODULE hDll, const ProxyFileInfo **pProxyFileList, const CLSID *pclsid)
{
  return NdrDllRegisterProxy(hDll, pProxyFileList, pclsid);
}

```

## disassembly

```asm
0x180002492  jmp     cs:__imp_NdrDllRegisterProxy
```
