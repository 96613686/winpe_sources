# DllGetClassObject

- ea: `0x180004840`
- end: `0x18000492f`
- name: `DllGetClassObject`
- size: `239`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800038d4`
- `0x180004840`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004878`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004878`

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
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180025408 = 1;
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
0x180004840  mov     [rsp+arg_0], rbx
0x180004845  push    rbp
0x180004846  push    rsi
0x180004847  push    rdi
0x180004848  sub     rsp, 40h
0x18000484c  mov     rax, cs:__security_cookie
0x180004853  xor     rax, rsp
0x180004856  mov     [rsp+58h+var_20], rax
0x18000485b  mov     rsi, r8
0x18000485e  mov     rbp, rdx
0x180004861  mov     rdi, rcx
0x180004864  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000486b  xor     r8d, r8d; Parameter
0x18000486e  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180004875  xor     r9d, r9d; Context
0x180004878  call    cs:__imp_InitOnceExecuteOnce
0x18000487e  mov     cs:byte_180025408, 1
0x180004885  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000488c  mov     qword ptr [rsi], 0
0x180004893  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000489a  mov     rax, [rax+20h]
0x18000489e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048a3  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800048aa  lea     rbx, [rax+8]
0x1800048ae  mov     rax, [rcx+28h]
0x1800048b2  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800048b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048be  mov     rdx, rax
0x1800048c1  cmp     rbx, rax
0x1800048c4  jnb     short loc_1800048ED
0x1800048c6  mov     r9, [rbx]; struct _GUID *
0x1800048c9  test    r9, r9
0x1800048cc  jz      short loc_1800048E4
0x1800048ce  mov     rax, [r9+8]
0x1800048d2  mov     rcx, [rax]
0x1800048d5  cmp     rcx, [rdi]
0x1800048d8  jnz     short loc_1800048E4
0x1800048da  mov     rax, [rax+8]
0x1800048de  cmp     rax, [rdi+8]
0x1800048e2  jz      short loc_18000490C
0x1800048e4  add     rbx, 8
0x1800048e8  cmp     rbx, rdx
0x1800048eb  jb      short loc_1800048C6
0x1800048ed  mov     eax, 80040111h
0x1800048f2  mov     rcx, [rsp+58h+var_20]
0x1800048f7  xor     rcx, rsp; StackCookie
0x1800048fa  call    __security_check_cookie
0x1800048ff  mov     rbx, [rsp+58h+arg_0]
0x180004904  add     rsp, 40h
0x180004908  pop     rdi
0x180004909  pop     rsi
0x18000490a  pop     rbp
0x18000490b  retn
0x18000490c  mov     r8, rbp; unsigned int *
0x18000490f  mov     [rsp+58h+var_28], 1
0x180004917  lea     rdx, [rsp+58h+var_28]; struct Microsoft::WRL::Details::ModuleBase *
0x18000491c  mov     [rsp+58h+var_38], rsi; struct Microsoft::WRL::Details::CreatorMap *
0x180004921  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180004928  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000492d  jmp     short loc_1800048F2
```
