# DllGetClassObject

- ea: `0x18000d260`
- end: `0x18000d32d`
- name: `DllGetClassObject`
- size: `205`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009800`
- `0x18000d260`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000d286`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000d286`

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
  byte_180019748 = 1;
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
0x18000d260  push    rbx
0x18000d262  push    rbp
0x18000d263  push    rsi
0x18000d264  push    rdi
0x18000d265  sub     rsp, 38h
0x18000d269  mov     rsi, r8
0x18000d26c  mov     rbp, rdx
0x18000d26f  mov     rdi, rcx
0x18000d272  xor     r9d, r9d; Context
0x18000d275  xor     r8d, r8d; Parameter
0x18000d278  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000d27f  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000d286  call    cs:__imp_InitOnceExecuteOnce
0x18000d28c  mov     cs:byte_180019748, 1
0x18000d293  mov     qword ptr [rsi], 0
0x18000d29a  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000d2a1  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000d2a8  mov     rax, [rax+20h]
0x18000d2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2b1  lea     rbx, [rax+8]
0x18000d2b5  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000d2bc  mov     rax, [rcx+28h]
0x18000d2c0  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000d2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2cc  mov     rdx, rax
0x18000d2cf  cmp     rbx, rax
0x18000d2d2  jnb     short loc_18000D2FB
0x18000d2d4  mov     r9, [rbx]; struct _GUID *
0x18000d2d7  test    r9, r9
0x18000d2da  jz      short loc_18000D2F2
0x18000d2dc  mov     rax, [r9+8]
0x18000d2e0  mov     rcx, [rax]
0x18000d2e3  cmp     rcx, [rdi]
0x18000d2e6  jnz     short loc_18000D2F2
0x18000d2e8  mov     rax, [rax+8]
0x18000d2ec  cmp     rax, [rdi+8]
0x18000d2f0  jz      short loc_18000D309
0x18000d2f2  add     rbx, 8
0x18000d2f6  cmp     rbx, rdx
0x18000d2f9  jb      short loc_18000D2D4
0x18000d2fb  mov     eax, 80040111h
0x18000d300  add     rsp, 38h
0x18000d304  pop     rdi
0x18000d305  pop     rsi
0x18000d306  pop     rbp
0x18000d307  pop     rbx
0x18000d308  retn
0x18000d309  mov     [rsp+58h+arg_10], 1
0x18000d311  mov     [rsp+58h+Ptr], rsi; Ptr
0x18000d316  mov     r8, rbp; unsigned int *
0x18000d319  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x18000d31e  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000d325  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000d32a  jmp     short loc_18000D300
```
