# DllGetClassObject

- ea: `0x180012bd0`
- end: `0x180012ccf`
- name: `DllGetClassObject`
- size: `255`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b310`
- `0x180012bd0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180012bf6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180012bf6`
- `RPCRT4!NdrDllGetClassObject` at `0x180012c9c`
- `RPCRT4!NdrDllGetClassObject` at `0x180012c9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rdx
  const struct _GUID *v8; // r9
  _QWORD *v9; // rax
  HRESULT result; // eax
  struct IUnknown **pPSFactoryBuffer; // [rsp+28h] [rbp-30h]
  int v12; // [rsp+70h] [rbp+18h] BYREF

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180082A48 = 1;
  *ppv = 0;
  v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                 + 32LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                             + 8);
  v7 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                         + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  if ( (unsigned __int64)v6 >= v7 )
  {
LABEL_6:
    result = -2147221231;
  }
  else
  {
    while ( 1 )
    {
      v8 = *v6;
      if ( *v6 )
      {
        v9 = *(_QWORD **)v8->Data4;
        if ( *v9 == *(_QWORD *)&rclsid->Data1 && v9[1] == *(_QWORD *)rclsid->Data4 )
          break;
      }
      if ( (unsigned __int64)++v6 >= v7 )
        goto LABEL_6;
    }
    v12 = 1;
    result = Microsoft::WRL::Details::GetCacheEntry(
               (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
               (struct Microsoft::WRL::Details::ModuleBase *)&v12,
               &riid->Data1,
               v8,
               ppv,
               pPSFactoryBuffer);
  }
  if ( result < 0 )
    return NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  return result;
}

```

## disassembly

```asm
0x180012bd0  push    rbx
0x180012bd2  push    rbp
0x180012bd3  push    rsi
0x180012bd4  push    rdi
0x180012bd5  sub     rsp, 38h
0x180012bd9  mov     rsi, r8
0x180012bdc  mov     rbp, rdx
0x180012bdf  mov     rdi, rcx
0x180012be2  xor     r9d, r9d; Context
0x180012be5  xor     r8d, r8d; Parameter
0x180012be8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180012bef  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180012bf6  call    cs:__imp_InitOnceExecuteOnce
0x180012bfc  mov     cs:byte_180082A48, 1
0x180012c03  mov     qword ptr [rsi], 0
0x180012c0a  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180012c11  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180012c18  mov     rax, [rax+20h]
0x180012c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c21  lea     rbx, [rax+8]
0x180012c25  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180012c2c  mov     rax, [rcx+28h]
0x180012c30  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180012c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c3c  mov     rdx, rax
0x180012c3f  cmp     rbx, rax
0x180012c42  jnb     short loc_180012C6B
0x180012c44  mov     r9, [rbx]; struct _GUID *
0x180012c47  test    r9, r9
0x180012c4a  jz      short loc_180012C62
0x180012c4c  mov     rax, [r9+8]
0x180012c50  mov     rcx, [rax]
0x180012c53  cmp     rcx, [rdi]
0x180012c56  jnz     short loc_180012C62
0x180012c58  mov     rax, [rax+8]
0x180012c5c  cmp     rax, [rdi+8]
0x180012c60  jz      short loc_180012CAB
0x180012c62  add     rbx, 8
0x180012c66  cmp     rbx, rdx
0x180012c69  jb      short loc_180012C44
0x180012c6b  mov     eax, 80040111h
0x180012c70  test    eax, eax
0x180012c72  jns     short loc_180012CA2
0x180012c74  lea     rax, gPFactory
0x180012c7b  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180012c80  lea     rax, CLSID_PSFactoryBuffer
0x180012c87  mov     [rsp+58h+pclsid], rax; pclsid
0x180012c8c  lea     r9, aProxyFileList; pProxyFileList
0x180012c93  mov     r8, rsi; ppv
0x180012c96  mov     rdx, rbp; riid
0x180012c99  mov     rcx, rdi; rclsid
0x180012c9c  call    cs:__imp_NdrDllGetClassObject
0x180012ca2  add     rsp, 38h
0x180012ca6  pop     rdi
0x180012ca7  pop     rsi
0x180012ca8  pop     rbp
0x180012ca9  pop     rbx
0x180012caa  retn
0x180012cab  mov     [rsp+58h+arg_10], 1
0x180012cb3  mov     [rsp+58h+pclsid], rsi; Ptr
0x180012cb8  mov     r8, rbp; unsigned int *
0x180012cbb  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x180012cc0  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180012cc7  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180012ccc  jmp     short loc_180012C70
```
