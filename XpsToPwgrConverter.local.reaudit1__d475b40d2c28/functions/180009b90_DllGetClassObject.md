# DllGetClassObject

- ea: `0x180009b90`
- end: `0x180009c5d`
- name: `DllGetClassObject`
- size: `205`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009914`
- `0x180009b90`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009bb6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009bb6`

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
  byte_180017718 = 1;
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
0x180009b90  push    rbx
0x180009b92  push    rbp
0x180009b93  push    rsi
0x180009b94  push    rdi
0x180009b95  sub     rsp, 38h
0x180009b99  mov     rsi, r8
0x180009b9c  mov     rbp, rdx
0x180009b9f  mov     rdi, rcx
0x180009ba2  xor     r9d, r9d; Context
0x180009ba5  xor     r8d, r8d; Parameter
0x180009ba8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180009baf  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180009bb6  call    cs:__imp_InitOnceExecuteOnce
0x180009bbc  mov     cs:byte_180017718, 1
0x180009bc3  mov     qword ptr [rsi], 0
0x180009bca  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180009bd1  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180009bd8  mov     rax, [rax+20h]
0x180009bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009be1  lea     rbx, [rax+8]
0x180009be5  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180009bec  mov     rax, [rcx+28h]
0x180009bf0  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180009bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bfc  mov     rdx, rax
0x180009bff  cmp     rbx, rax
0x180009c02  jnb     short loc_180009C2B
0x180009c04  mov     r9, [rbx]; struct _GUID *
0x180009c07  test    r9, r9
0x180009c0a  jz      short loc_180009C22
0x180009c0c  mov     rax, [r9+8]
0x180009c10  mov     rcx, [rax]
0x180009c13  cmp     rcx, [rdi]
0x180009c16  jnz     short loc_180009C22
0x180009c18  mov     rax, [rax+8]
0x180009c1c  cmp     rax, [rdi+8]
0x180009c20  jz      short loc_180009C39
0x180009c22  add     rbx, 8
0x180009c26  cmp     rbx, rdx
0x180009c29  jb      short loc_180009C04
0x180009c2b  mov     eax, 80040111h
0x180009c30  add     rsp, 38h
0x180009c34  pop     rdi
0x180009c35  pop     rsi
0x180009c36  pop     rbp
0x180009c37  pop     rbx
0x180009c38  retn
0x180009c39  mov     [rsp+58h+arg_10], 1
0x180009c41  mov     [rsp+58h+Ptr], rsi; Ptr
0x180009c46  mov     r8, rbp; unsigned int *
0x180009c49  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x180009c4e  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180009c55  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180009c5a  jmp     short loc_180009C30
```
