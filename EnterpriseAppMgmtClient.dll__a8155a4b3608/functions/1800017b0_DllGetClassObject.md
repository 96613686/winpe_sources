# DllGetClassObject

- ea: `0x1800017b0`
- end: `0x1800017de`
- name: `DllGetClassObject`
- size: `46`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800017d3`
- `RPCRT4!NdrDllGetClassObject` at `0x1800017d3`

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
0x1800017b0  sub     rsp, 38h
0x1800017b4  lea     rax, gPFactory
0x1800017bb  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800017c0  lea     r9, aProxyFileList; pProxyFileList
0x1800017c7  lea     rax, CLSID_PSFactoryBuffer
0x1800017ce  mov     [rsp+38h+pclsid], rax; pclsid
0x1800017d3  call    cs:__imp_NdrDllGetClassObject
0x1800017d9  add     rsp, 38h
0x1800017dd  retn
```
