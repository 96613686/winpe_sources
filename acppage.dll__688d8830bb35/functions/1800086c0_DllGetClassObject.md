# DllGetClassObject

- ea: `0x1800086c0`
- end: `0x180008731`
- name: `DllGetClassObject`
- size: `113`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004324`
- `0x1800086c0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180008709`
- `RPCRT4!NdrDllGetClassObject` at `0x180008709`

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
    return ATL::CAtlDllModuleT<CSlayeruiModule>::DllGetClassObject(v8, rclsid, riid, ppv);
  return result;
}

```

## disassembly

```asm
0x1800086c0  mov     [rsp+arg_0], rbx
0x1800086c5  mov     [rsp+arg_8], rsi
0x1800086ca  push    rdi
0x1800086cb  sub     rsp, 30h
0x1800086cf  mov     rax, cs:aProxyFileList
0x1800086d6  mov     rbx, r8
0x1800086d9  mov     rdi, rdx
0x1800086dc  mov     rsi, rcx
0x1800086df  mov     r9, [rax+8]
0x1800086e3  mov     rax, [r9]
0x1800086e6  test    rax, rax
0x1800086e9  jz      short loc_1800086EE
0x1800086eb  mov     rax, [rax]
0x1800086ee  lea     rcx, gPFactory
0x1800086f5  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x1800086fa  lea     r9, aProxyFileList; pProxyFileList
0x180008701  mov     rcx, rsi; rclsid
0x180008704  mov     [rsp+38h+pclsid], rax; pclsid
0x180008709  call    cs:__imp_NdrDllGetClassObject
0x18000870f  test    eax, eax
0x180008711  jz      short loc_180008721
0x180008713  mov     r9, rbx
0x180008716  mov     r8, rdi
0x180008719  mov     rdx, rsi
0x18000871c  call    ?DllGetClassObject@?$CAtlDllModuleT@VCSlayeruiModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CAtlDllModuleT<CSlayeruiModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x180008721  mov     rbx, [rsp+38h+arg_0]
0x180008726  mov     rsi, [rsp+38h+arg_8]
0x18000872b  add     rsp, 30h
0x18000872f  pop     rdi
0x180008730  retn
```
