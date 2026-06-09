# DllGetClassObject

- ea: `0x18000b390`
- end: `0x18000b45d`
- name: `DllGetClassObject`
- size: `205`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000afe4`
- `0x18000b390`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b3b6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b3b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rdx
  const struct _GUID *v8; // r9
  _QWORD *v9; // rax
  int v11; // [rsp+70h] [rbp+18h] BYREF

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18001B3B8 = 1;
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
  v11 = 1;
  return Microsoft::WRL::Details::GetCacheEntry(
           (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
           (struct Microsoft::WRL::Details::ModuleBase *)&v11,
           &riid->Data1,
           v8,
           ppv);
}

```

## disassembly

```asm
0x18000b390  push    rbx
0x18000b392  push    rbp
0x18000b393  push    rsi
0x18000b394  push    rdi
0x18000b395  sub     rsp, 38h
0x18000b399  mov     rsi, r8
0x18000b39c  mov     rbp, rdx
0x18000b39f  mov     rdi, rcx
0x18000b3a2  xor     r9d, r9d; Context
0x18000b3a5  xor     r8d, r8d; Parameter
0x18000b3a8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000b3af  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000b3b6  call    cs:__imp_InitOnceExecuteOnce
0x18000b3bc  mov     cs:byte_18001B3B8, 1
0x18000b3c3  mov     qword ptr [rsi], 0
0x18000b3ca  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b3d1  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b3d8  mov     rax, [rax+20h]
0x18000b3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e1  lea     rbx, [rax+8]
0x18000b3e5  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b3ec  mov     rax, [rcx+28h]
0x18000b3f0  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3fc  mov     rdx, rax
0x18000b3ff  cmp     rbx, rax
0x18000b402  jnb     short loc_18000B42B
0x18000b404  mov     r9, [rbx]; struct _GUID *
0x18000b407  test    r9, r9
0x18000b40a  jz      short loc_18000B422
0x18000b40c  mov     rax, [r9+8]
0x18000b410  mov     rcx, [rax]
0x18000b413  cmp     rcx, [rdi]
0x18000b416  jnz     short loc_18000B422
0x18000b418  mov     rax, [rax+8]
0x18000b41c  cmp     rax, [rdi+8]
0x18000b420  jz      short loc_18000B439
0x18000b422  add     rbx, 8
0x18000b426  cmp     rbx, rdx
0x18000b429  jb      short loc_18000B404
0x18000b42b  mov     eax, 80040111h
0x18000b430  add     rsp, 38h
0x18000b434  pop     rdi
0x18000b435  pop     rsi
0x18000b436  pop     rbp
0x18000b437  pop     rbx
0x18000b438  retn
0x18000b439  mov     [rsp+58h+arg_10], 1
0x18000b441  mov     [rsp+58h+Ptr], rsi; Ptr
0x18000b446  mov     r8, rbp; unsigned int *
0x18000b449  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x18000b44e  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000b455  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000b45a  jmp     short loc_18000B430
```
