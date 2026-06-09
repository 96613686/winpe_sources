# DllGetClassObject

- ea: `0x180008860`
- end: `0x1800088ed`
- name: `DllGetClassObject`
- size: `141`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800043c0`
- `0x1800059f8`
- `0x1800075e4`
- `0x180008860`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800088a2`
- `RPCRT4!NdrDllGetClassObject` at `0x1800088a2`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  Microsoft::WRL::Details *v6; // rbp
  int Class; // eax
  HRESULT v8; // ebx
  int pclsid; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  if ( NdrDllGetClassObject(
         rclsid,
         riid,
         ppv,
         (const ProxyFileInfo **)&aProxyFileList,
         &CLSID_PSFactoryBuffer,
         &gPFactory) >= 0 )
    return 0;
  Class = Microsoft::WRL::Details::GetClassObject<1>(v6, ppv);
  v8 = Class;
  if ( Class >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x37,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\srv\\module.cpp",
    (const char *)(unsigned int)Class,
    pclsid);
  return v8;
}

```

## disassembly

```asm
0x180008860  push    rbx
0x180008862  push    rbp
0x180008863  push    rsi
0x180008864  push    rdi
0x180008865  sub     rsp, 38h
0x180008869  mov     rbx, r8
0x18000886c  mov     rdi, rdx
0x18000886f  mov     rsi, rcx
0x180008872  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180008877  mov     rbp, rax
0x18000887a  lea     r9, aProxyFileList; pProxyFileList
0x180008881  lea     rax, gPFactory
0x180008888  mov     r8, rbx; ppv
0x18000888b  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180008890  mov     rdx, rdi; riid
0x180008893  lea     rax, CLSID_PSFactoryBuffer
0x18000889a  mov     rcx, rsi; rclsid
0x18000889d  mov     [rsp+58h+pclsid], rax; pclsid
0x1800088a2  call    cs:__imp_NdrDllGetClassObject
0x1800088a8  test    eax, eax
0x1800088aa  jns     short loc_1800088E2
0x1800088ac  mov     r9, rdi
0x1800088af  mov     [rsp+58h+pclsid], rbx; int
0x1800088b4  mov     r8, rsi
0x1800088b7  mov     rcx, rbp; this
0x1800088ba  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x1800088bf  mov     ebx, eax
0x1800088c1  test    eax, eax
0x1800088c3  jns     short loc_1800088E2
0x1800088c5  mov     rcx, [rsp+58h]; this
0x1800088ca  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\staterepositor"...
0x1800088d1  mov     r9d, eax; char *
0x1800088d4  mov     edx, 37h ; '7'; void *
0x1800088d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088de  mov     eax, ebx
0x1800088e0  jmp     short loc_1800088E4
0x1800088e2  xor     eax, eax
0x1800088e4  add     rsp, 38h
0x1800088e8  pop     rdi
0x1800088e9  pop     rsi
0x1800088ea  pop     rbp
0x1800088eb  pop     rbx
0x1800088ec  retn
```
