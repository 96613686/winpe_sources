# DllGetClassObject

- ea: `0x180002870`
- end: `0x180002971`
- name: `DllGetClassObject`
- size: `257`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002494`
- `0x180002870`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800028ca`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800028ca`
- `RPCRT4!NdrDllGetClassObject` at `0x1800028a1`
- `RPCRT4!NdrDllGetClassObject` at `0x1800028a1`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  const struct _GUID **v7; // rbx
  unsigned __int64 v8; // rdx
  const struct _GUID *v9; // r9
  _QWORD *v10; // rax
  struct IUnknown **pPSFactoryBuffer; // [rsp+28h] [rbp-30h]
  int v12; // [rsp+78h] [rbp+20h] BYREF

  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  if ( result )
  {
    *ppv = 0;
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_18001A518 = 1;
    *ppv = 0;
    v7 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                   + 32LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                               + 8);
    v8 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                           + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
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
      v12 = 1;
      return Microsoft::WRL::Details::GetCacheEntry(
               (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
               (struct Microsoft::WRL::Details::ModuleBase *)&v12,
               &riid->Data1,
               v9,
               ppv,
               pPSFactoryBuffer);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002870  push    rbx
0x180002872  push    rbp
0x180002873  push    rsi
0x180002874  push    rdi
0x180002875  sub     rsp, 38h
0x180002879  mov     rsi, r8
0x18000287c  mov     rbp, rdx
0x18000287f  mov     rdi, rcx
0x180002882  lea     rax, gPFactory
0x180002889  mov     [rsp+58h+pPSFactoryBuffer], rax; struct IUnknown **
0x18000288e  lea     rax, CLSID_PSFactoryBuffer
0x180002895  mov     [rsp+58h+pclsid], rax; pclsid
0x18000289a  lea     r9, aProxyFileList; pProxyFileList
0x1800028a1  call    cs:__imp_NdrDllGetClassObject
0x1800028a7  test    eax, eax
0x1800028a9  jz      loc_180002944
0x1800028af  mov     qword ptr [rsi], 0
0x1800028b6  xor     r9d, r9d; Context
0x1800028b9  xor     r8d, r8d; Parameter
0x1800028bc  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800028c3  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800028ca  call    cs:__imp_InitOnceExecuteOnce
0x1800028d0  mov     cs:byte_18001A518, 1
0x1800028d7  mov     qword ptr [rsi], 0
0x1800028de  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800028e5  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800028ec  mov     rax, [rax+20h]
0x1800028f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f5  lea     rbx, [rax+8]
0x1800028f9  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180002900  mov     rax, [rcx+28h]
0x180002904  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000290b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002910  mov     rdx, rax
0x180002913  cmp     rbx, rax
0x180002916  jnb     short loc_18000293F
0x180002918  mov     r9, [rbx]; struct _GUID *
0x18000291b  test    r9, r9
0x18000291e  jz      short loc_180002936
0x180002920  mov     rax, [r9+8]
0x180002924  mov     rcx, [rax]
0x180002927  cmp     rcx, [rdi]
0x18000292a  jnz     short loc_180002936
0x18000292c  mov     rax, [rax+8]
0x180002930  cmp     rax, [rdi+8]
0x180002934  jz      short loc_18000294D
0x180002936  add     rbx, 8
0x18000293a  cmp     rbx, rdx
0x18000293d  jb      short loc_180002918
0x18000293f  mov     eax, 80040111h
0x180002944  add     rsp, 38h
0x180002948  pop     rdi
0x180002949  pop     rsi
0x18000294a  pop     rbp
0x18000294b  pop     rbx
0x18000294c  retn
0x18000294d  mov     [rsp+58h+arg_18], 1
0x180002955  mov     [rsp+58h+pclsid], rsi; Ptr
0x18000295a  mov     r8, rbp; unsigned int *
0x18000295d  lea     rdx, [rsp+58h+arg_18]; struct Microsoft::WRL::Details::ModuleBase *
0x180002962  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180002969  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000296e  jmp     short loc_180002944
```
