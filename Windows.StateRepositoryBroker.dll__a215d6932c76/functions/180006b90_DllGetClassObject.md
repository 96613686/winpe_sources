# DllGetClassObject

- ea: `0x180006b90`
- end: `0x180006c1d`
- name: `DllGetClassObject`
- size: `141`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800030d0`
- `0x180004620`
- `0x180006224`
- `0x180006b90`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180006bd2`
- `RPCRT4!NdrDllGetClassObject` at `0x180006bd2`

## string_xrefs

- `0x180006bfa`: `onecore\base\appmodel\staterepository\winrt\broker\srv\servermain.cpp`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 *v6; // rbp
  int Class; // eax
  HRESULT v8; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  if ( NdrDllGetClassObject(
         rclsid,
         riid,
         ppv,
         (const ProxyFileInfo **)&aProxyFileList,
         &CLSID_PSFactoryBuffer,
         &gPFactory) >= 0 )
    return 0;
  Class = Microsoft::WRL::Details::GetClassObject<1>((Microsoft::WRL::Details *)v6, ppv);
  v8 = Class;
  if ( Class >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3E,
    (int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\srv\\servermain.cpp",
    (const char *)(unsigned int)Class);
  return v8;
}

```

## disassembly

```asm
0x180006b90  push    rbx
0x180006b92  push    rbp
0x180006b93  push    rsi
0x180006b94  push    rdi
0x180006b95  sub     rsp, 38h
0x180006b99  mov     rbx, r8
0x180006b9c  mov     rdi, rdx
0x180006b9f  mov     rsi, rcx
0x180006ba2  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180006ba7  mov     rbp, rax
0x180006baa  lea     r9, aProxyFileList; pProxyFileList
0x180006bb1  lea     rax, gPFactory
0x180006bb8  mov     r8, rbx; ppv
0x180006bbb  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180006bc0  mov     rdx, rdi; riid
0x180006bc3  lea     rax, CLSID_PSFactoryBuffer
0x180006bca  mov     rcx, rsi; rclsid
0x180006bcd  mov     [rsp+58h+pclsid], rax; pclsid
0x180006bd2  call    cs:__imp_NdrDllGetClassObject
0x180006bd8  test    eax, eax
0x180006bda  jns     short loc_180006C12
0x180006bdc  mov     r9, rdi
0x180006bdf  mov     [rsp+58h+pclsid], rbx; int
0x180006be4  mov     r8, rsi
0x180006be7  mov     rcx, rbp; this
0x180006bea  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x180006bef  mov     ebx, eax
0x180006bf1  test    eax, eax
0x180006bf3  jns     short loc_180006C12
0x180006bf5  mov     rcx, [rsp+58h]; this
0x180006bfa  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\staterepositor"...
0x180006c01  mov     r9d, eax; char *
0x180006c04  mov     edx, 3Eh ; '>'; void *
0x180006c09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006c0e  mov     eax, ebx
0x180006c10  jmp     short loc_180006C14
0x180006c12  xor     eax, eax
0x180006c14  add     rsp, 38h
0x180006c18  pop     rdi
0x180006c19  pop     rsi
0x180006c1a  pop     rbp
0x180006c1b  pop     rbx
0x180006c1c  retn
```
