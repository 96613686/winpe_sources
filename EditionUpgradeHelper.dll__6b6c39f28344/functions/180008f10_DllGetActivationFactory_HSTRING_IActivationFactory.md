# DllGetActivationFactory(HSTRING__ *,IActivationFactory * *)

- ea: `0x180008f10`
- end: `0x1800090cc`
- name: `?DllGetActivationFactory@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *Ptr)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800018e0`
- `0x180008c60`
- `0x180008f10`
- `0x180009184`
- `0x180009978`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180008f6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180008f6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008f9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008f9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180008f80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180008f80`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180009025`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180009025`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180009094`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180009094`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008f4b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180008f4b`

## string_xrefs

- `0x18000905d`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(HSTRING string, _QWORD *Ptr)
{
  PCWSTR StringRawBuffer; // r14
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rbp
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // r8d
  int v11; // edx
  int CacheEntry; // ebx
  const struct _GUID *v13; // r9
  struct IUnknown **v15; // [rsp+28h] [rbp-60h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-58h] BYREF
  int v17; // [rsp+34h] [rbp-54h] BYREF
  __int128 v18; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v19[22]; // [rsp+48h] [rbp-40h]

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18002F938 = 1;
  *Ptr = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    CacheEntry = -2147024809;
    v18 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v19 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v19[14] = *(_QWORD *)L"sId";
    RoOriginateErrorW(2147942487LL, 18, &v18);
    goto LABEL_15;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v5 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                         + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
     + 8;
  v6 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                         + 48LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  if ( v5 >= v6 )
  {
LABEL_11:
    CacheEntry = -2147221231;
    RoOriginateError(2147746065LL, string);
LABEL_15:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(CacheEntry);
    goto LABEL_16;
  }
  while ( 1 )
  {
    if ( *(_QWORD *)v5 )
    {
      v7 = (*(__int64 (**)(void))(*(_QWORD *)v5 + 8LL))();
      v8 = (unsigned __int16 *)StringRawBuffer;
      v9 = v7 - (_QWORD)StringRawBuffer;
      do
      {
        v10 = *(unsigned __int16 *)((char *)v8 + v9);
        v11 = *v8 - v10;
        if ( v11 )
          break;
        ++v8;
      }
      while ( v10 );
      if ( !v11 )
        break;
    }
    v5 += 8LL;
    if ( v5 >= v6 )
      goto LABEL_11;
  }
  v13 = *(const struct _GUID **)v5;
  v17 = 1;
  CacheEntry = Microsoft::WRL::Details::GetCacheEntry(
                 (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
                 (struct Microsoft::WRL::Details::ModuleBase *)&v17,
                 &GUID_00000035_0000_0000_c000_000000000046.Data1,
                 v13,
                 Ptr,
                 v15);
  if ( CacheEntry < 0 )
    goto LABEL_15;
LABEL_16:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)CacheEntry);
  return (unsigned int)CacheEntry;
}

```

## disassembly

```asm
0x180008f10  mov     [rsp+arg_10], rbx
0x180008f15  mov     [rsp+arg_18], rbp
0x180008f1a  push    rsi
0x180008f1b  push    rdi
0x180008f1c  push    r14
0x180008f1e  sub     rsp, 70h
0x180008f22  mov     rax, cs:__security_cookie
0x180008f29  xor     rax, rsp
0x180008f2c  mov     [rsp+88h+var_28], rax
0x180008f31  mov     rsi, rdx
0x180008f34  mov     rdi, rcx
0x180008f37  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180008f3e  xor     r9d, r9d; Context
0x180008f41  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180008f48  xor     r8d, r8d; Parameter
0x180008f4b  call    cs:__imp_InitOnceExecuteOnce
0x180008f51  mov     cs:byte_18002F938, 1
0x180008f58  mov     rcx, rdi; string
0x180008f5b  mov     qword ptr [rsi], 0
0x180008f62  mov     [rsp+88h+hasEmbedNull], 0
0x180008f6a  call    cs:__imp_WindowsIsStringEmpty
0x180008f70  test    eax, eax
0x180008f72  jnz     loc_18000905D
0x180008f78  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x180008f7d  mov     rcx, rdi; string
0x180008f80  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180008f86  test    eax, eax
0x180008f88  js      loc_18000905D
0x180008f8e  cmp     [rsp+88h+hasEmbedNull], 1
0x180008f93  jz      loc_18000905D
0x180008f99  xor     edx, edx; length
0x180008f9b  mov     rcx, rdi; string
0x180008f9e  call    cs:__imp_WindowsGetStringRawBuffer
0x180008fa4  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008fab  mov     r14, rax
0x180008fae  mov     rax, [rcx+28h]
0x180008fb2  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fbe  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008fc5  lea     rbx, [rax+8]
0x180008fc9  mov     rax, [rcx+30h]
0x180008fcd  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180008fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fd9  mov     rbp, rax
0x180008fdc  cmp     rbx, rax
0x180008fdf  jnb     short loc_18000901B
0x180008fe1  mov     rax, [rbx]
0x180008fe4  test    rax, rax
0x180008fe7  jz      short loc_180009012
0x180008fe9  mov     rax, [rax+8]
0x180008fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ff2  mov     rcx, r14
0x180008ff5  sub     rax, r14
0x180008ff8  movzx   edx, word ptr [rcx]
0x180008ffb  movzx   r8d, word ptr [rcx+rax]
0x180009000  sub     edx, r8d
0x180009003  jnz     short loc_18000900E
0x180009005  add     rcx, 2
0x180009009  test    r8d, r8d
0x18000900c  jnz     short loc_180008FF8
0x18000900e  test    edx, edx
0x180009010  jz      short loc_18000902D
0x180009012  add     rbx, 8
0x180009016  cmp     rbx, rbp
0x180009019  jb      short loc_180008FE1
0x18000901b  mov     ebx, 80040111h
0x180009020  mov     rdx, rdi
0x180009023  mov     ecx, ebx
0x180009025  call    cs:__imp_RoOriginateError
0x18000902b  jmp     short loc_18000909A
0x18000902d  mov     r9, [rbx]; struct _GUID *
0x180009030  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180009037  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x18000903c  mov     [rsp+88h+var_54], 1
0x180009044  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000904b  mov     [rsp+88h+Ptr], rsi; Ptr
0x180009050  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180009055  mov     ebx, eax
0x180009057  test    eax, eax
0x180009059  jns     short loc_1800090A1
0x18000905b  jmp     short loc_18000909A
0x18000905d  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180009064  mov     ebx, 80070057h
0x180009069  lea     r8, [rsp+88h+var_50]
0x18000906e  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180009075  mov     edx, 12h
0x18000907a  mov     ecx, ebx
0x18000907c  movups  [rsp+88h+var_50], xmm0
0x180009081  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180009089  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x18000908e  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x180009094  call    cs:__imp_RoOriginateErrorW
0x18000909a  mov     ecx, ebx
0x18000909c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800090a1  mov     ecx, ebx
0x1800090a3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800090a8  mov     eax, ebx
0x1800090aa  mov     rcx, [rsp+88h+var_28]
0x1800090af  xor     rcx, rsp; StackCookie
0x1800090b2  call    __security_check_cookie
0x1800090b7  lea     r11, [rsp+88h+var_18]
0x1800090bc  mov     rbx, [r11+30h]
0x1800090c0  mov     rbp, [r11+38h]
0x1800090c4  mov     rsp, r11
0x1800090c7  pop     r14
0x1800090c9  pop     rdi
0x1800090ca  pop     rsi
0x1800090cb  retn
```
