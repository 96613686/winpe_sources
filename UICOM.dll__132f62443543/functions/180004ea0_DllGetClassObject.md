# DllGetClassObject

- ea: `0x180004ea0`
- end: `0x180004f11`
- name: `DllGetClassObject`
- size: `113`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800036fc`
- `0x180004ea0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180004ee9`
- `RPCRT4!NdrDllGetClassObject` at `0x180004ee9`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax
  __int64 v8; // rcx

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result )
    return ATL::CAtlDllModuleT<CUICOMModule>::DllGetClassObject(v8, rclsid, riid, ppv);
  return result;
}

```

## disassembly

```asm
0x180004ea0  mov     [rsp+arg_0], rbx
0x180004ea5  mov     [rsp+arg_8], rsi
0x180004eaa  push    rdi
0x180004eab  sub     rsp, 30h
0x180004eaf  mov     rax, cs:aProxyFileList
0x180004eb6  mov     rbx, r8
0x180004eb9  mov     rdi, rdx
0x180004ebc  mov     rsi, rcx
0x180004ebf  mov     r9, [rax+8]
0x180004ec3  mov     rax, [r9]
0x180004ec6  test    rax, rax
0x180004ec9  jz      short loc_180004ECE
0x180004ecb  mov     rax, [rax]
0x180004ece  lea     rcx, gPFactory
0x180004ed5  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x180004eda  lea     r9, aProxyFileList; pProxyFileList
0x180004ee1  mov     rcx, rsi; rclsid
0x180004ee4  mov     [rsp+38h+pclsid], rax; pclsid
0x180004ee9  call    cs:__imp_NdrDllGetClassObject
0x180004eef  test    eax, eax
0x180004ef1  jz      short loc_180004F01
0x180004ef3  mov     r9, rbx
0x180004ef6  mov     r8, rdi
0x180004ef9  mov     rdx, rsi
0x180004efc  call    ?DllGetClassObject@?$CAtlDllModuleT@VCUICOMModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CAtlDllModuleT<CUICOMModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x180004f01  mov     rbx, [rsp+38h+arg_0]
0x180004f06  mov     rsi, [rsp+38h+arg_8]
0x180004f0b  add     rsp, 30h
0x180004f0f  pop     rdi
0x180004f10  retn
```
