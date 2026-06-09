# NdrDllGetClassObject_0

- ea: `0x180002766`
- end: `0x18000276c`
- name: `NdrDllGetClassObject_0`
- size: `6`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, void **ppv, const ProxyFileInfo **pProxyFileList, const CLSID *pclsid, CStdPSFactoryBuffer *pPSFactoryBuffer)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180002766`

## pseudocode

```c
// attributes: thunk
HRESULT __stdcall NdrDllGetClassObject_0(
        const IID *const rclsid,
        const IID *const riid,
        void **ppv,
        const ProxyFileInfo **pProxyFileList,
        const CLSID *pclsid,
        CStdPSFactoryBuffer *pPSFactoryBuffer)
{
  return NdrDllGetClassObject(rclsid, riid, ppv, pProxyFileList, pclsid, pPSFactoryBuffer);
}

```

## disassembly

```asm
0x180002766  jmp     cs:__imp_NdrDllGetClassObject
```
