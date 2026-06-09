# DllGetClassObject

- ea: `0x1800075b0`
- end: `0x1800076a0`
- name: `DllGetClassObject`
- size: `240`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002650`
- `0x180004994`
- `0x1800075b0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800075e8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800075e8`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rdx
  const struct _GUID *v8; // r9
  _QWORD *v9; // rax
  struct IUnknown **v11; // [rsp+28h] [rbp-30h]
  int v12; // [rsp+30h] [rbp-28h] BYREF

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    `Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_1800144E8 = 1;
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
           (const struct Microsoft::WRL::Details::CreatorMap *)ppv,
           v11);
}

```

## disassembly

```asm
0x1800075b0  mov     [rsp+arg_0], rbx
0x1800075b5  push    rbp
0x1800075b6  push    rsi
0x1800075b7  push    rdi
0x1800075b8  sub     rsp, 40h
0x1800075bc  mov     rax, cs:__security_cookie
0x1800075c3  xor     rax, rsp
0x1800075c6  mov     [rsp+58h+var_20], rax
0x1800075cb  mov     rsi, r8
0x1800075ce  mov     rbp, rdx
0x1800075d1  mov     rdi, rcx
0x1800075d4  xor     r9d, r9d; Context
0x1800075d7  xor     r8d, r8d; Parameter
0x1800075da  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800075e1  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800075e8  call    cs:__imp_InitOnceExecuteOnce
0x1800075ee  mov     cs:byte_1800144E8, 1
0x1800075f5  mov     qword ptr [rsi], 0
0x1800075fc  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180007603  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000760a  mov     rax, [rax+20h]
0x18000760e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007613  lea     rbx, [rax+8]
0x180007617  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000761e  mov     rax, [rcx+28h]
0x180007622  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180007629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000762e  mov     rdx, rax
0x180007631  cmp     rbx, rax
0x180007634  jnb     short loc_18000765D
0x180007636  mov     r9, [rbx]; struct _GUID *
0x180007639  test    r9, r9
0x18000763c  jz      short loc_180007654
0x18000763e  mov     rax, [r9+8]
0x180007642  mov     rcx, [rax]
0x180007645  cmp     rcx, [rdi]
0x180007648  jnz     short loc_180007654
0x18000764a  mov     rax, [rax+8]
0x18000764e  cmp     rax, [rdi+8]
0x180007652  jz      short loc_18000767C
0x180007654  add     rbx, 8
0x180007658  cmp     rbx, rdx
0x18000765b  jb      short loc_180007636
0x18000765d  mov     eax, 80040111h
0x180007662  mov     rcx, [rsp+58h+var_20]
0x180007667  xor     rcx, rsp; StackCookie
0x18000766a  call    __security_check_cookie
0x18000766f  mov     rbx, [rsp+58h+arg_0]
0x180007674  add     rsp, 40h
0x180007678  pop     rdi
0x180007679  pop     rsi
0x18000767a  pop     rbp
0x18000767b  retn
0x18000767c  mov     [rsp+58h+var_28], 1
0x180007684  mov     [rsp+58h+var_38], rsi; struct Microsoft::WRL::Details::CreatorMap *
0x180007689  mov     r8, rbp; unsigned int *
0x18000768c  lea     rdx, [rsp+58h+var_28]; struct Microsoft::WRL::Details::ModuleBase *
0x180007691  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180007698  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000769d  jmp     short loc_180007662
```
