# DllGetClassObject

- ea: `0x180001c80`
- end: `0x180001cae`
- name: `DllGetClassObject`
- size: `46`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180001ca3`
- `RPCRT4!NdrDllGetClassObject` at `0x180001ca3`

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
0x180001c80  sub     rsp, 38h
0x180001c84  lea     rax, gPFactory
0x180001c8b  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180001c90  lea     r9, aProxyFileList; pProxyFileList
0x180001c97  lea     rax, CLSID_PSFactoryBuffer
0x180001c9e  mov     [rsp+38h+pclsid], rax; pclsid
0x180001ca3  call    cs:__imp_NdrDllGetClassObject
0x180001ca9  add     rsp, 38h
0x180001cad  retn
```
