# DllGetClassObject

- ea: `0x180006480`
- end: `0x18000657a`
- name: `DllGetClassObject`
- size: `250`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180005d34`
- `0x180006480`
- `0x18000b010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800064b1`
- `RPCRT4!NdrDllGetClassObject` at `0x1800064b1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800064d3`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800064d3`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  const struct _GUID **v7; // rbx
  unsigned __int64 v8; // rdx
  const struct _GUID *v9; // r9
  _QWORD *v10; // rax
  int v11; // [rsp+78h] [rbp+20h] BYREF

  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  if ( result )
  {
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_180015488 = 1;
    *ppv = 0;
    v7 = (const struct _GUID **)((*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                      + 32))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                               + 8);
    v8 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                              + 40))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    if ( (unsigned __int64)v7 >= v8 )
    {
      return -2147221231;
    }
    else
    {
      while ( 1 )
      {
        v9 = *v7;
        if ( *v7 )
        {
          v10 = *(_QWORD **)v9->Data4;
          if ( *v10 == *(_QWORD *)&rclsid->Data1 && v10[1] == *(_QWORD *)rclsid->Data4 )
            break;
        }
        if ( (unsigned __int64)++v7 >= v8 )
          return -2147221231;
      }
      v11 = 1;
      return Microsoft::WRL::Details::GetCacheEntry(
               (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
               (struct Microsoft::WRL::Details::ModuleBase *)&v11,
               &riid->Data1,
               v9,
               ppv);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006480  push    rbx
0x180006482  push    rbp
0x180006483  push    rsi
0x180006484  push    rdi
0x180006485  sub     rsp, 38h
0x180006489  mov     rsi, r8
0x18000648c  mov     rbp, rdx
0x18000648f  mov     rdi, rcx
0x180006492  lea     rax, gPFactory
0x180006499  mov     [rsp+58h+pPSFactoryBuffer], rax; struct IUnknown **
0x18000649e  lea     rax, CLSID_PSFactoryBuffer
0x1800064a5  mov     [rsp+58h+pclsid], rax; pclsid
0x1800064aa  lea     r9, aProxyFileList; pProxyFileList
0x1800064b1  call    cs:__imp_NdrDllGetClassObject
0x1800064b7  test    eax, eax
0x1800064b9  jz      loc_18000654D
0x1800064bf  xor     r9d, r9d; Context
0x1800064c2  xor     r8d, r8d; Parameter
0x1800064c5  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800064cc  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800064d3  call    cs:__imp_InitOnceExecuteOnce
0x1800064d9  mov     cs:byte_180015488, 1
0x1800064e0  mov     qword ptr [rsi], 0
0x1800064e7  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800064ee  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800064f5  mov     rax, [rax+20h]
0x1800064f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064fe  lea     rbx, [rax+8]
0x180006502  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006509  mov     rax, [rcx+28h]
0x18000650d  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006519  mov     rdx, rax
0x18000651c  cmp     rbx, rax
0x18000651f  jnb     short loc_180006548
0x180006521  mov     r9, [rbx]; struct _GUID *
0x180006524  test    r9, r9
0x180006527  jz      short loc_18000653F
0x180006529  mov     rax, [r9+8]
0x18000652d  mov     rcx, [rax]
0x180006530  cmp     rcx, [rdi]
0x180006533  jnz     short loc_18000653F
0x180006535  mov     rax, [rax+8]
0x180006539  cmp     rax, [rdi+8]
0x18000653d  jz      short loc_180006556
0x18000653f  add     rbx, 8
0x180006543  cmp     rbx, rdx
0x180006546  jb      short loc_180006521
0x180006548  mov     eax, 80040111h
0x18000654d  add     rsp, 38h
0x180006551  pop     rdi
0x180006552  pop     rsi
0x180006553  pop     rbp
0x180006554  pop     rbx
0x180006555  retn
0x180006556  mov     [rsp+58h+arg_18], 1
0x18000655e  mov     [rsp+58h+pclsid], rsi; Ptr
0x180006563  mov     r8, rbp; unsigned int *
0x180006566  lea     rdx, [rsp+58h+arg_18]; struct Microsoft::WRL::Details::ModuleBase *
0x18000656b  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180006572  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180006577  jmp     short loc_18000654D
```
