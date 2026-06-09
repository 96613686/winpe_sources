# DllGetClassObject

- ea: `0x18000a4c0`
- end: `0x18000a528`
- name: `DllGetClassObject`
- size: `104`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800071c0`
- `0x180008754`
- `0x18000a4c0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000a502`
- `RPCRT4!NdrDllGetClassObject` at `0x18000a502`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  Microsoft::WRL::Details *v6; // rbp
  HRESULT result; // eax

  v6 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  if ( result < 0 )
    return Microsoft::WRL::Details::GetClassObject<1>(v6, ppv);
  return result;
}

```

## disassembly

```asm
0x18000a4c0  push    rbx
0x18000a4c2  push    rbp
0x18000a4c3  push    rsi
0x18000a4c4  push    rdi
0x18000a4c5  sub     rsp, 38h
0x18000a4c9  mov     rbx, r8
0x18000a4cc  mov     rdi, rdx
0x18000a4cf  mov     rsi, rcx
0x18000a4d2  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18000a4d7  mov     rbp, rax
0x18000a4da  lea     r9, aProxyFileList; pProxyFileList
0x18000a4e1  lea     rax, gPFactory
0x18000a4e8  mov     r8, rbx; ppv
0x18000a4eb  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000a4f0  mov     rdx, rdi; riid
0x18000a4f3  lea     rax, CLSID_PSFactoryBuffer
0x18000a4fa  mov     rcx, rsi; rclsid
0x18000a4fd  mov     [rsp+58h+pclsid], rax; pclsid
0x18000a502  call    cs:__imp_NdrDllGetClassObject
0x18000a508  test    eax, eax
0x18000a50a  jns     short loc_18000A51F
0x18000a50c  mov     r9, rdi
0x18000a50f  mov     [rsp+58h+pclsid], rbx; PVOID
0x18000a514  mov     r8, rsi
0x18000a517  mov     rcx, rbp; this
0x18000a51a  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x18000a51f  add     rsp, 38h
0x18000a523  pop     rdi
0x18000a524  pop     rsi
0x18000a525  pop     rbp
0x18000a526  pop     rbx
0x18000a527  retn
```
