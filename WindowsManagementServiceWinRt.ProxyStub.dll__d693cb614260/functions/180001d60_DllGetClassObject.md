# DllGetClassObject

- ea: `0x180001d60`
- end: `0x180001d8e`
- name: `DllGetClassObject`
- size: `46`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180001d83`
- `RPCRT4!NdrDllGetClassObject` at `0x180001d83`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  return NdrDllGetClassObject(
           rclsid,
           riid,
           ppv,
           (const ProxyFileInfo **)&aProxyFileList,
           &CLSID_PSFactoryBuffer,
           &gPFactory);
}

```

## disassembly

```asm
0x180001d60  sub     rsp, 38h
0x180001d64  lea     rax, gPFactory
0x180001d6b  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180001d70  lea     r9, aProxyFileList; pProxyFileList
0x180001d77  lea     rax, CLSID_PSFactoryBuffer
0x180001d7e  mov     [rsp+38h+pclsid], rax; pclsid
0x180001d83  call    cs:__imp_NdrDllGetClassObject
0x180001d89  add     rsp, 38h
0x180001d8d  retn
```
