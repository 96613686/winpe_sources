# DllGetClassObject

- ea: `0x18000bb20`
- end: `0x18000bbed`
- name: `DllGetClassObject`
- size: `205`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b8a4`
- `0x18000bb20`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000bb46`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000bb46`

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
  byte_180014938 = 1;
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
0x18000bb20  push    rbx
0x18000bb22  push    rbp
0x18000bb23  push    rsi
0x18000bb24  push    rdi
0x18000bb25  sub     rsp, 38h
0x18000bb29  mov     rsi, r8
0x18000bb2c  mov     rbp, rdx
0x18000bb2f  mov     rdi, rcx
0x18000bb32  xor     r9d, r9d; Context
0x18000bb35  xor     r8d, r8d; Parameter
0x18000bb38  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000bb3f  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000bb46  call    cs:__imp_InitOnceExecuteOnce
0x18000bb4c  mov     cs:byte_180014938, 1
0x18000bb53  mov     qword ptr [rsi], 0
0x18000bb5a  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000bb61  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000bb68  mov     rax, [rax+20h]
0x18000bb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb71  lea     rbx, [rax+8]
0x18000bb75  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000bb7c  mov     rax, [rcx+28h]
0x18000bb80  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000bb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb8c  mov     rdx, rax
0x18000bb8f  cmp     rbx, rax
0x18000bb92  jnb     short loc_18000BBBB
0x18000bb94  mov     r9, [rbx]; struct _GUID *
0x18000bb97  test    r9, r9
0x18000bb9a  jz      short loc_18000BBB2
0x18000bb9c  mov     rax, [r9+8]
0x18000bba0  mov     rcx, [rax]
0x18000bba3  cmp     rcx, [rdi]
0x18000bba6  jnz     short loc_18000BBB2
0x18000bba8  mov     rax, [rax+8]
0x18000bbac  cmp     rax, [rdi+8]
0x18000bbb0  jz      short loc_18000BBC9
0x18000bbb2  add     rbx, 8
0x18000bbb6  cmp     rbx, rdx
0x18000bbb9  jb      short loc_18000BB94
0x18000bbbb  mov     eax, 80040111h
0x18000bbc0  add     rsp, 38h
0x18000bbc4  pop     rdi
0x18000bbc5  pop     rsi
0x18000bbc6  pop     rbp
0x18000bbc7  pop     rbx
0x18000bbc8  retn
0x18000bbc9  mov     [rsp+58h+arg_10], 1
0x18000bbd1  mov     [rsp+58h+Ptr], rsi; Ptr
0x18000bbd6  mov     r8, rbp; unsigned int *
0x18000bbd9  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x18000bbde  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000bbe5  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000bbea  jmp     short loc_18000BBC0
```
