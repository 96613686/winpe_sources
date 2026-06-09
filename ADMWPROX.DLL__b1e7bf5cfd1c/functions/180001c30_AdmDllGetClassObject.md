# AdmDllGetClassObject

- ea: `0x180001c30`
- end: `0x180001c6d`
- name: `AdmDllGetClassObject`
- size: `61`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001c30`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180001c62`
- `RPCRT4!NdrDllGetClassObject` at `0x180001c62`

## pseudocode

```c
HRESULT __stdcall AdmDllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
}

```

## disassembly

```asm
0x180001c30  sub     rsp, 38h
0x180001c34  mov     rax, cs:aProxyFileList
0x180001c3b  mov     r9, [rax+8]
0x180001c3f  mov     rax, [r9]
0x180001c42  test    rax, rax
0x180001c45  jz      short loc_180001C4A
0x180001c47  mov     rax, [rax]
0x180001c4a  lea     r9, gPFactory
0x180001c51  mov     [rsp+38h+pPSFactoryBuffer], r9; pPSFactoryBuffer
0x180001c56  lea     r9, aProxyFileList; pProxyFileList
0x180001c5d  mov     [rsp+38h+pclsid], rax; pclsid
0x180001c62  call    cs:__imp_NdrDllGetClassObject
0x180001c68  add     rsp, 38h
0x180001c6c  retn
```
