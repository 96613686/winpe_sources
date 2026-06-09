# DllGetClassObject

- ea: `0x18000c910`
- end: `0x18000c9dd`
- name: `DllGetClassObject`
- size: `205`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000c584`
- `0x18000c910`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000c936`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000c936`

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
  byte_180014998 = 1;
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
0x18000c910  push    rbx
0x18000c912  push    rbp
0x18000c913  push    rsi
0x18000c914  push    rdi
0x18000c915  sub     rsp, 38h
0x18000c919  mov     rsi, r8
0x18000c91c  mov     rbp, rdx
0x18000c91f  mov     rdi, rcx
0x18000c922  xor     r9d, r9d; Context
0x18000c925  xor     r8d, r8d; Parameter
0x18000c928  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000c92f  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000c936  call    cs:__imp_InitOnceExecuteOnce
0x18000c93c  mov     cs:byte_180014998, 1
0x18000c943  mov     qword ptr [rsi], 0
0x18000c94a  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000c951  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000c958  mov     rax, [rax+20h]
0x18000c95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c961  lea     rbx, [rax+8]
0x18000c965  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000c96c  mov     rax, [rcx+28h]
0x18000c970  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000c977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c97c  mov     rdx, rax
0x18000c97f  cmp     rbx, rax
0x18000c982  jnb     short loc_18000C9AB
0x18000c984  mov     r9, [rbx]; struct _GUID *
0x18000c987  test    r9, r9
0x18000c98a  jz      short loc_18000C9A2
0x18000c98c  mov     rax, [r9+8]
0x18000c990  mov     rcx, [rax]
0x18000c993  cmp     rcx, [rdi]
0x18000c996  jnz     short loc_18000C9A2
0x18000c998  mov     rax, [rax+8]
0x18000c99c  cmp     rax, [rdi+8]
0x18000c9a0  jz      short loc_18000C9B9
0x18000c9a2  add     rbx, 8
0x18000c9a6  cmp     rbx, rdx
0x18000c9a9  jb      short loc_18000C984
0x18000c9ab  mov     eax, 80040111h
0x18000c9b0  add     rsp, 38h
0x18000c9b4  pop     rdi
0x18000c9b5  pop     rsi
0x18000c9b6  pop     rbp
0x18000c9b7  pop     rbx
0x18000c9b8  retn
0x18000c9b9  mov     [rsp+58h+arg_10], 1
0x18000c9c1  mov     [rsp+58h+Ptr], rsi; Ptr
0x18000c9c6  mov     r8, rbp; unsigned int *
0x18000c9c9  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x18000c9ce  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000c9d5  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000c9da  jmp     short loc_18000C9B0
```
