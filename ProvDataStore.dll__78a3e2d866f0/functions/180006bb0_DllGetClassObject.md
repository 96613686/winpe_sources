# DllGetClassObject

- ea: `0x180006bb0`
- end: `0x180006c7d`
- name: `DllGetClassObject`
- size: `205`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003ea4`
- `0x180006bb0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006bd6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006bd6`

## pseudocode

```c
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
  byte_1800199D8 = 1;
  *ppv = 0;
  v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                    + 32))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                             + 8);
  v7 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                            + 40))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
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
0x180006bb0  push    rbx
0x180006bb2  push    rbp
0x180006bb3  push    rsi
0x180006bb4  push    rdi
0x180006bb5  sub     rsp, 38h
0x180006bb9  mov     rsi, r8
0x180006bbc  mov     rbp, rdx
0x180006bbf  mov     rdi, rcx
0x180006bc2  xor     r9d, r9d; Context
0x180006bc5  xor     r8d, r8d; Parameter
0x180006bc8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180006bcf  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180006bd6  call    cs:__imp_InitOnceExecuteOnce
0x180006bdc  mov     cs:byte_1800199D8, 1
0x180006be3  mov     qword ptr [rsi], 0
0x180006bea  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006bf1  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006bf8  mov     rax, [rax+20h]
0x180006bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c01  lea     rbx, [rax+8]
0x180006c05  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006c0c  mov     rax, [rcx+28h]
0x180006c10  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c1c  mov     rdx, rax
0x180006c1f  cmp     rbx, rax
0x180006c22  jnb     short loc_180006C4B
0x180006c24  mov     r9, [rbx]; struct _GUID *
0x180006c27  test    r9, r9
0x180006c2a  jz      short loc_180006C42
0x180006c2c  mov     rax, [r9+8]
0x180006c30  mov     rcx, [rax]
0x180006c33  cmp     rcx, [rdi]
0x180006c36  jnz     short loc_180006C42
0x180006c38  mov     rax, [rax+8]
0x180006c3c  cmp     rax, [rdi+8]
0x180006c40  jz      short loc_180006C59
0x180006c42  add     rbx, 8
0x180006c46  cmp     rbx, rdx
0x180006c49  jb      short loc_180006C24
0x180006c4b  mov     eax, 80040111h
0x180006c50  add     rsp, 38h
0x180006c54  pop     rdi
0x180006c55  pop     rsi
0x180006c56  pop     rbp
0x180006c57  pop     rbx
0x180006c58  retn
0x180006c59  mov     [rsp+58h+arg_10], 1
0x180006c61  mov     [rsp+58h+Ptr], rsi; Ptr
0x180006c66  mov     r8, rbp; unsigned int *
0x180006c69  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x180006c6e  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180006c75  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180006c7a  jmp     short loc_180006C50
```
