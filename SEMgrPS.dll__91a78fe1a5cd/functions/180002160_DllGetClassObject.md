# DllGetClassObject

- ea: `0x180002160`
- end: `0x18000218e`
- name: `DllGetClassObject`
- size: `46`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180002183`
- `RPCRT4!NdrDllGetClassObject` at `0x180002183`

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
0x180002160  sub     rsp, 38h
0x180002164  lea     rax, gPFactory
0x18000216b  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180002170  lea     r9, aProxyFileList; pProxyFileList
0x180002177  lea     rax, CLSID_PSFactoryBuffer
0x18000217e  mov     [rsp+38h+pclsid], rax; pclsid
0x180002183  call    cs:__imp_NdrDllGetClassObject
0x180002189  add     rsp, 38h
0x18000218d  retn
```
