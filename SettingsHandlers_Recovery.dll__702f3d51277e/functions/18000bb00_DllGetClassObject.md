# DllGetClassObject

- ea: `0x18000bb00`
- end: `0x18000bc01`
- name: `DllGetClassObject`
- size: `257`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b158`
- `0x18000bb00`
- `0x18002b010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000bb38`
- `RPCRT4!NdrDllGetClassObject` at `0x18000bb38`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000bb5a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000bb5a`

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
  int v12; // [rsp+70h] [rbp+18h] BYREF

  *ppv = 0;
  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  if ( result < 0 )
  {
    InitOnceExecuteOnce(
      &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
      _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_18005A058 = 1;
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
0x18000bb00  push    rbx
0x18000bb02  push    rbp
0x18000bb03  push    rsi
0x18000bb04  push    rdi
0x18000bb05  sub     rsp, 38h
0x18000bb09  mov     rdi, r8
0x18000bb0c  mov     rbp, rdx
0x18000bb0f  mov     rsi, rcx
0x18000bb12  mov     qword ptr [r8], 0
0x18000bb19  lea     rax, gPFactory
0x18000bb20  mov     [rsp+58h+pPSFactoryBuffer], rax; struct IUnknown **
0x18000bb25  lea     rax, CLSID_PSFactoryBuffer
0x18000bb2c  mov     [rsp+58h+pclsid], rax; pclsid
0x18000bb31  lea     r9, aProxyFileList; pProxyFileList
0x18000bb38  call    cs:__imp_NdrDllGetClassObject
0x18000bb3e  test    eax, eax
0x18000bb40  jns     loc_18000BBD4
0x18000bb46  xor     r9d, r9d; Context
0x18000bb49  xor     r8d, r8d; Parameter
0x18000bb4c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000bb53  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000bb5a  call    cs:__imp_InitOnceExecuteOnce
0x18000bb60  mov     cs:byte_18005A058, 1
0x18000bb67  mov     qword ptr [rdi], 0
0x18000bb6e  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000bb75  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000bb7c  mov     rax, [rax+20h]
0x18000bb80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb85  lea     rbx, [rax+8]
0x18000bb89  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000bb90  mov     rax, [rcx+28h]
0x18000bb94  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000bb9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bba0  mov     rdx, rax
0x18000bba3  cmp     rbx, rax
0x18000bba6  jnb     short loc_18000BBCF
0x18000bba8  mov     r9, [rbx]; struct _GUID *
0x18000bbab  test    r9, r9
0x18000bbae  jz      short loc_18000BBC6
0x18000bbb0  mov     rax, [r9+8]
0x18000bbb4  mov     rcx, [rax]
0x18000bbb7  cmp     rcx, [rsi]
0x18000bbba  jnz     short loc_18000BBC6
0x18000bbbc  mov     rax, [rax+8]
0x18000bbc0  cmp     rax, [rsi+8]
0x18000bbc4  jz      short loc_18000BBDD
0x18000bbc6  add     rbx, 8
0x18000bbca  cmp     rbx, rdx
0x18000bbcd  jb      short loc_18000BBA8
0x18000bbcf  mov     eax, 80040111h
0x18000bbd4  add     rsp, 38h
0x18000bbd8  pop     rdi
0x18000bbd9  pop     rsi
0x18000bbda  pop     rbp
0x18000bbdb  pop     rbx
0x18000bbdc  retn
0x18000bbdd  mov     [rsp+58h+arg_10], 1
0x18000bbe5  mov     [rsp+58h+pclsid], rdi; Ptr
0x18000bbea  mov     r8, rbp; unsigned int *
0x18000bbed  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x18000bbf2  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000bbf9  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000bbfe  jmp     short loc_18000BBD4
```
