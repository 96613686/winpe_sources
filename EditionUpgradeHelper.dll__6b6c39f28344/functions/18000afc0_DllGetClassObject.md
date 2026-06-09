# DllGetClassObject

- ea: `0x18000afc0`
- end: `0x18000b097`
- name: `DllGetClassObject`
- size: `215`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009184`
- `0x180009978`
- `0x18000afc0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000afe6`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000afe6`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rdx
  const struct _GUID *v8; // r9
  _QWORD *v9; // rax
  int CacheEntry; // ebx
  int v12; // [rsp+70h] [rbp+18h] BYREF

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18002F938 = 1;
  *ppv = 0;
  v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                 + 32LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                             + 8);
  v7 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                         + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  if ( (unsigned __int64)v6 >= v7 )
  {
LABEL_6:
    CacheEntry = -2147221231;
  }
  else
  {
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
        goto LABEL_6;
    }
    v12 = 1;
    CacheEntry = Microsoft::WRL::Details::GetCacheEntry(
                   (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
                   (struct Microsoft::WRL::Details::ModuleBase *)&v12,
                   &riid->Data1,
                   v8,
                   ppv);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(CacheEntry);
  return CacheEntry;
}

```

## disassembly

```asm
0x18000afc0  push    rbx
0x18000afc2  push    rbp
0x18000afc3  push    rsi
0x18000afc4  push    rdi
0x18000afc5  sub     rsp, 38h
0x18000afc9  mov     rsi, r8
0x18000afcc  mov     rbp, rdx
0x18000afcf  mov     rdi, rcx
0x18000afd2  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000afd9  xor     r8d, r8d; Parameter
0x18000afdc  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000afe3  xor     r9d, r9d; Context
0x18000afe6  call    cs:__imp_InitOnceExecuteOnce
0x18000afec  mov     cs:byte_18002F938, 1
0x18000aff3  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000affa  mov     qword ptr [rsi], 0
0x18000b001  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b008  mov     rax, [rax+20h]
0x18000b00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b011  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b018  lea     rbx, [rax+8]
0x18000b01c  mov     rax, [rcx+28h]
0x18000b020  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000b027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b02c  mov     rdx, rax
0x18000b02f  cmp     rbx, rax
0x18000b032  jnb     short loc_18000B05B
0x18000b034  mov     r9, [rbx]; struct _GUID *
0x18000b037  test    r9, r9
0x18000b03a  jz      short loc_18000B052
0x18000b03c  mov     rax, [r9+8]
0x18000b040  mov     rcx, [rax]
0x18000b043  cmp     rcx, [rdi]
0x18000b046  jnz     short loc_18000B052
0x18000b048  mov     rax, [rax+8]
0x18000b04c  cmp     rax, [rdi+8]
0x18000b050  jz      short loc_18000B072
0x18000b052  add     rbx, 8
0x18000b056  cmp     rbx, rdx
0x18000b059  jb      short loc_18000B034
0x18000b05b  mov     ebx, 80040111h
0x18000b060  mov     ecx, ebx
0x18000b062  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b067  mov     eax, ebx
0x18000b069  add     rsp, 38h
0x18000b06d  pop     rdi
0x18000b06e  pop     rsi
0x18000b06f  pop     rbp
0x18000b070  pop     rbx
0x18000b071  retn
0x18000b072  mov     r8, rbp; unsigned int *
0x18000b075  mov     [rsp+58h+arg_10], 1
0x18000b07d  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x18000b082  mov     [rsp+58h+Ptr], rsi; Ptr
0x18000b087  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000b08e  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000b093  mov     ebx, eax
0x18000b095  jmp     short loc_18000B060
```
