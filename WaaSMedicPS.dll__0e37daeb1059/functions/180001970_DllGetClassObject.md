# DllGetClassObject

- ea: `0x180001970`
- end: `0x18000199e`
- name: `DllGetClassObject`
- size: `46`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180001993`
- `RPCRT4!NdrDllGetClassObject` at `0x180001993`

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
0x180001970  sub     rsp, 38h
0x180001974  lea     rax, gPFactory
0x18000197b  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180001980  lea     r9, aProxyFileList; pProxyFileList
0x180001987  lea     rax, CLSID_PSFactoryBuffer
0x18000198e  mov     [rsp+38h+pclsid], rax; pclsid
0x180001993  call    cs:__imp_NdrDllGetClassObject
0x180001999  add     rsp, 38h
0x18000199d  retn
```
