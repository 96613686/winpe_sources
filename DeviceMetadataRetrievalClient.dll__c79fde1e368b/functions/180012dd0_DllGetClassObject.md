# DllGetClassObject

- ea: `0x180012dd0`
- end: `0x180012e45`
- name: `DllGetClassObject`
- size: `117`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180012bb4`
- `0x180012dd0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180012e19`
- `RPCRT4!NdrDllGetClassObject` at `0x180012e19`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  __int64 v7; // rcx

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  if ( NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory) < 0 )
    return ATL::CAtlDllModuleT<DmrcComServer>::DllGetClassObject(v7, rclsid, (__int64)riid, ppv);
  else
    return 0;
}

```

## disassembly

```asm
0x180012dd0  mov     [rsp+arg_0], rbx
0x180012dd5  mov     [rsp+arg_8], rsi
0x180012dda  push    rdi
0x180012ddb  sub     rsp, 30h
0x180012ddf  mov     rax, cs:aProxyFileList
0x180012de6  mov     rbx, r8
0x180012de9  mov     rdi, rdx
0x180012dec  mov     rsi, rcx
0x180012def  mov     r9, [rax+8]
0x180012df3  mov     rax, [r9]
0x180012df6  test    rax, rax
0x180012df9  jz      short loc_180012DFE
0x180012dfb  mov     rax, [rax]
0x180012dfe  lea     rcx, gPFactory
0x180012e05  mov     [rsp+38h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x180012e0a  lea     r9, aProxyFileList; pProxyFileList
0x180012e11  mov     rcx, rsi; rclsid
0x180012e14  mov     [rsp+38h+pclsid], rax; pclsid
0x180012e19  call    cs:__imp_NdrDllGetClassObject
0x180012e1f  test    eax, eax
0x180012e21  js      short loc_180012E27
0x180012e23  xor     eax, eax
0x180012e25  jmp     short loc_180012E35
0x180012e27  mov     r9, rbx
0x180012e2a  mov     r8, rdi
0x180012e2d  mov     rdx, rsi
0x180012e30  call    ?DllGetClassObject@?$CAtlDllModuleT@VDmrcComServer@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CAtlDllModuleT<DmrcComServer>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x180012e35  mov     rbx, [rsp+38h+arg_0]
0x180012e3a  mov     rsi, [rsp+38h+arg_8]
0x180012e3f  add     rsp, 30h
0x180012e43  pop     rdi
0x180012e44  retn
```
