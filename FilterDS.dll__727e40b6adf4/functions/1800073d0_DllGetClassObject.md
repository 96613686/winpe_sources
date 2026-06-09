# DllGetClassObject

- ea: `0x1800073d0`
- end: `0x18000749d`
- name: `DllGetClassObject`
- size: `205`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004374`
- `0x1800073d0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800073f6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800073f6`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rdx
  const struct _GUID *v8; // r9
  _QWORD *v9; // rax
  struct IUnknown **v11; // [rsp+28h] [rbp-30h]
  int v12; // [rsp+70h] [rbp+18h] BYREF

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180030C88 = 1;
  *ppv = 0;
  v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                 + 32LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                             + 8);
  v7 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                         + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  if ( (unsigned __int64)v6 >= v7 )
    return -2147221231;
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
      return -2147221231;
  }
  v12 = 1;
  return Microsoft::WRL::Details::GetCacheEntry(
           (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
           (struct Microsoft::WRL::Details::ModuleBase *)&v12,
           &riid->Data1,
           v8,
           ppv,
           v11);
}

```

## disassembly

```asm
0x1800073d0  push    rbx
0x1800073d2  push    rbp
0x1800073d3  push    rsi
0x1800073d4  push    rdi
0x1800073d5  sub     rsp, 38h
0x1800073d9  mov     rsi, r8
0x1800073dc  mov     rbp, rdx
0x1800073df  mov     rdi, rcx
0x1800073e2  xor     r9d, r9d; Context
0x1800073e5  xor     r8d, r8d; Parameter
0x1800073e8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800073ef  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800073f6  call    cs:__imp_InitOnceExecuteOnce
0x1800073fc  mov     cs:byte_180030C88, 1
0x180007403  mov     qword ptr [rsi], 0
0x18000740a  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180007411  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180007418  mov     rax, [rax+20h]
0x18000741c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007421  lea     rbx, [rax+8]
0x180007425  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000742c  mov     rax, [rcx+28h]
0x180007430  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180007437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000743c  mov     rdx, rax
0x18000743f  cmp     rbx, rax
0x180007442  jnb     short loc_18000746B
0x180007444  mov     r9, [rbx]; struct _GUID *
0x180007447  test    r9, r9
0x18000744a  jz      short loc_180007462
0x18000744c  mov     rax, [r9+8]
0x180007450  mov     rcx, [rax]
0x180007453  cmp     rcx, [rdi]
0x180007456  jnz     short loc_180007462
0x180007458  mov     rax, [rax+8]
0x18000745c  cmp     rax, [rdi+8]
0x180007460  jz      short loc_180007479
0x180007462  add     rbx, 8
0x180007466  cmp     rbx, rdx
0x180007469  jb      short loc_180007444
0x18000746b  mov     eax, 80040111h
0x180007470  add     rsp, 38h
0x180007474  pop     rdi
0x180007475  pop     rsi
0x180007476  pop     rbp
0x180007477  pop     rbx
0x180007478  retn
0x180007479  mov     [rsp+58h+arg_10], 1
0x180007481  mov     [rsp+58h+Ptr], rsi; Ptr
0x180007486  mov     r8, rbp; unsigned int *
0x180007489  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x18000748e  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180007495  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000749a  jmp     short loc_180007470
```
