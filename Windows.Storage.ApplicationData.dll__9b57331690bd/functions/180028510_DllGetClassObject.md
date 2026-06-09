# DllGetClassObject

- ea: `0x180028510`
- end: `0x1800285c2`
- name: `DllGetClassObject`
- size: `178`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009778`
- `0x180010984`
- `0x180018fb8`
- `0x180026d3c`
- `0x180028510`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180028552`
- `RPCRT4!NdrDllGetClassObject` at `0x180028552`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  Microsoft::WRL::Details::ModuleBase *v6; // rbp
  int ClassObject; // eax
  const wchar_t *v8; // rdx
  HRESULT Class; // ebx
  void *retaddr; // [rsp+58h] [rbp+0h]

  v6 = (Microsoft::WRL::Details::ModuleBase *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  ClassObject = NdrDllGetClassObject(
                  rclsid,
                  riid,
                  ppv,
                  (const ProxyFileInfo **)aProxyFileList,
                  &CLSID_PSFactoryBuffer,
                  &gPFactory);
  if ( ClassObject >= 0 )
    return 0;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    0x91u,
    "onecoreuap\\base\\appmodel\\statemanager\\winrt\\srv\\abiservermodule.cpp",
    ClassObject);
  Class = Microsoft::WRL::Details::GetClassObject<1>(v6, v8, rclsid, riid, ppv);
  if ( Class >= 0 )
    return 0;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    0x93u,
    "onecoreuap\\base\\appmodel\\statemanager\\winrt\\srv\\abiservermodule.cpp",
    Class,
    "GetClassObject");
  return Class;
}

```

## disassembly

```asm
0x180028510  push    rbx
0x180028512  push    rbp
0x180028513  push    rsi
0x180028514  push    rdi
0x180028515  sub     rsp, 38h
0x180028519  mov     rbx, ppv
0x18002851c  mov     rdi, riid
0x18002851f  mov     rsi, rclsid
0x180028522  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180028527  mov     rbp, rax
0x18002852a  lea     r9, aProxyFileList; pProxyFileList
0x180028531  lea     rax, gPFactory
0x180028538  mov     ppv, rbx; ppv
0x18002853b  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180028540  mov     riid, rdi; riid
0x180028543  lea     rax, CLSID_PSFactoryBuffer
0x18002854a  mov     rclsid, rsi; rclsid
0x18002854d  mov     [rsp+58h+pclsid], rax; pclsid
0x180028552  call    cs:__imp_NdrDllGetClassObject
0x180028558  test    eax, eax
0x18002855a  jns     short loc_1800285B7
0x18002855c  mov     rclsid, [rsp+58h]; callerReturnAddress
0x180028561  lea     ppv, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\statemanage"...
0x180028568  mov     r9d, eax; hr
0x18002856b  mov     edx, 91h; lineNumber
0x180028570  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180028575  mov     r9, rdi; ppv
0x180028578  mov     [rsp+58h+pclsid], rbx; modulePtr
0x18002857d  mov     ppv, rsi; riid
0x180028580  mov     rclsid, rbp; modulePtr
0x180028583  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x180028588  mov     ebx, eax
0x18002858a  test    eax, eax
0x18002858c  jns     short loc_1800285B7
0x18002858e  mov     rclsid, [rsp+58h]; callerReturnAddress
0x180028593  lea     rax, aGetclassobject; "GetClassObject"
0x18002859a  mov     r9d, ebx; hr
0x18002859d  mov     [rsp+58h+pclsid], rax; formatString
0x1800285a2  lea     ppv, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800285a9  mov     edx, 93h; lineNumber
0x1800285ae  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800285b3  mov     eax, ebx
0x1800285b5  jmp     short loc_1800285B9
0x1800285b7  xor     eax, eax
0x1800285b9  add     rsp, 38h
0x1800285bd  pop     rdi
0x1800285be  pop     rsi
0x1800285bf  pop     rbp
0x1800285c0  pop     rbx
0x1800285c1  retn
```
