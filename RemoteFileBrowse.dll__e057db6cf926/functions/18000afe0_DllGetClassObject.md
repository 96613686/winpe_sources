# DllGetClassObject

- ea: `0x18000afe0`
- end: `0x18000b0ad`
- name: `DllGetClassObject`
- size: `205`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009ef4`
- `0x18000afe0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b006`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b006`

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
  byte_180023708 = 1;
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
0x18000afe0  push    rbx
0x18000afe2  push    rbp
0x18000afe3  push    rsi
0x18000afe4  push    rdi
0x18000afe5  sub     rsp, 38h
0x18000afe9  mov     rsi, r8
0x18000afec  mov     rbp, rdx
0x18000afef  mov     rdi, rcx
0x18000aff2  xor     r9d, r9d; Context
0x18000aff5  xor     r8d, r8d; Parameter
0x18000aff8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000afff  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000b006  call    cs:__imp_InitOnceExecuteOnce
0x18000b00c  mov     cs:byte_180023708, 1
0x18000b013  mov     qword ptr [rsi], 0
0x18000b01a  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b021  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b028  mov     rax, [rax+20h]
0x18000b02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b031  lea     rbx, [rax+8]
0x18000b035  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b03c  mov     rax, [rcx+28h]
0x18000b040  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b04c  mov     rdx, rax
0x18000b04f  cmp     rbx, rax
0x18000b052  jnb     short loc_18000B07B
0x18000b054  mov     r9, [rbx]; struct _GUID *
0x18000b057  test    r9, r9
0x18000b05a  jz      short loc_18000B072
0x18000b05c  mov     rax, [r9+8]
0x18000b060  mov     rcx, [rax]
0x18000b063  cmp     rcx, [rdi]
0x18000b066  jnz     short loc_18000B072
0x18000b068  mov     rax, [rax+8]
0x18000b06c  cmp     rax, [rdi+8]
0x18000b070  jz      short loc_18000B089
0x18000b072  add     rbx, 8
0x18000b076  cmp     rbx, rdx
0x18000b079  jb      short loc_18000B054
0x18000b07b  mov     eax, 80040111h
0x18000b080  add     rsp, 38h
0x18000b084  pop     rdi
0x18000b085  pop     rsi
0x18000b086  pop     rbp
0x18000b087  pop     rbx
0x18000b088  retn
0x18000b089  mov     [rsp+58h+arg_10], 1
0x18000b091  mov     [rsp+58h+Ptr], rsi; Ptr
0x18000b096  mov     r8, rbp; unsigned int *
0x18000b099  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x18000b09e  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000b0a5  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000b0aa  jmp     short loc_18000B080
```
