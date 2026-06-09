# DllGetActivationFactory

- ea: `0x180004690`
- end: `0x18000483a`
- name: `DllGetActivationFactory`
- size: `426`
- prototype: `__int64 __fastcall(HSTRING string, struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x1800038d4`
- `0x180004690`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800046cb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800046cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000471e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000471e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800046ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800046ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180004700`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180004700`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800047a5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800047a5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180004810`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180004810`

## string_xrefs

- `0x1800047d9`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(HSTRING string, struct Microsoft::WRL::Details::CreatorMap *a2)
{
  PCWSTR StringRawBuffer; // r14
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rbp
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // r8d
  int v11; // edx
  unsigned int v12; // ebx
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
  byte_180025408 = 1;
  *(_QWORD *)a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v12 = -2147024809;
    v18 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v19 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v19[14] = *(_QWORD *)L"sId";
    RoOriginateErrorW(2147942487LL, 18, &v18);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                           + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
       + 8;
    v6 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                           + 48LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    if ( v5 >= v6 )
    {
LABEL_11:
      v12 = -2147221231;
      RoOriginateError(2147746065LL);
    }
    else
    {
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
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v17,
                             &GUID_00000035_0000_0000_c000_000000000046.Data1,
                             v13,
                             a2,
                             v15);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180004690  mov     [rsp+arg_10], rbx
0x180004695  mov     [rsp+arg_18], rbp
0x18000469a  push    rsi
0x18000469b  push    rdi
0x18000469c  push    r14
0x18000469e  sub     rsp, 70h
0x1800046a2  mov     rax, cs:__security_cookie
0x1800046a9  xor     rax, rsp
0x1800046ac  mov     [rsp+88h+var_28], rax
0x1800046b1  mov     rsi, rdx
0x1800046b4  mov     rdi, rcx
0x1800046b7  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800046be  xor     r9d, r9d; Context
0x1800046c1  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800046c8  xor     r8d, r8d; Parameter
0x1800046cb  call    cs:__imp_InitOnceExecuteOnce
0x1800046d1  mov     cs:byte_180025408, 1
0x1800046d8  mov     rcx, rdi; string
0x1800046db  mov     qword ptr [rsi], 0
0x1800046e2  mov     [rsp+88h+hasEmbedNull], 0
0x1800046ea  call    cs:__imp_WindowsIsStringEmpty
0x1800046f0  test    eax, eax
0x1800046f2  jnz     loc_1800047D9
0x1800046f8  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x1800046fd  mov     rcx, rdi; string
0x180004700  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180004706  test    eax, eax
0x180004708  js      loc_1800047D9
0x18000470e  cmp     [rsp+88h+hasEmbedNull], 1
0x180004713  jz      loc_1800047D9
0x180004719  xor     edx, edx; length
0x18000471b  mov     rcx, rdi; string
0x18000471e  call    cs:__imp_WindowsGetStringRawBuffer
0x180004724  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000472b  mov     r14, rax
0x18000472e  mov     rax, [rcx+28h]
0x180004732  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473e  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004745  lea     rbx, [rax+8]
0x180004749  mov     rax, [rcx+30h]
0x18000474d  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004759  mov     rbp, rax
0x18000475c  cmp     rbx, rax
0x18000475f  jnb     short loc_18000479B
0x180004761  mov     rax, [rbx]
0x180004764  test    rax, rax
0x180004767  jz      short loc_180004792
0x180004769  mov     rax, [rax+8]
0x18000476d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004772  mov     rcx, r14
0x180004775  sub     rax, r14
0x180004778  movzx   edx, word ptr [rcx]
0x18000477b  movzx   r8d, word ptr [rcx+rax]
0x180004780  sub     edx, r8d
0x180004783  jnz     short loc_18000478E
0x180004785  add     rcx, 2
0x180004789  test    r8d, r8d
0x18000478c  jnz     short loc_180004778
0x18000478e  test    edx, edx
0x180004790  jz      short loc_1800047AD
0x180004792  add     rbx, 8
0x180004796  cmp     rbx, rbp
0x180004799  jb      short loc_180004761
0x18000479b  mov     ebx, 80040111h
0x1800047a0  mov     rdx, rdi
0x1800047a3  mov     ecx, ebx
0x1800047a5  call    cs:__imp_RoOriginateError
0x1800047ab  jmp     short loc_180004816
0x1800047ad  mov     r9, [rbx]; struct _GUID *
0x1800047b0  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x1800047b7  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x1800047bc  mov     [rsp+88h+var_54], 1
0x1800047c4  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x1800047cb  mov     [rsp+88h+var_68], rsi; struct Microsoft::WRL::Details::CreatorMap *
0x1800047d0  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x1800047d5  mov     ebx, eax
0x1800047d7  jmp     short loc_180004816
0x1800047d9  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x1800047e0  mov     ebx, 80070057h
0x1800047e5  lea     r8, [rsp+88h+var_50]
0x1800047ea  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x1800047f1  mov     edx, 12h
0x1800047f6  mov     ecx, ebx
0x1800047f8  movups  [rsp+88h+var_50], xmm0
0x1800047fd  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180004805  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x18000480a  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x180004810  call    cs:__imp_RoOriginateErrorW
0x180004816  mov     eax, ebx
0x180004818  mov     rcx, [rsp+88h+var_28]
0x18000481d  xor     rcx, rsp; StackCookie
0x180004820  call    __security_check_cookie
0x180004825  lea     r11, [rsp+88h+var_18]
0x18000482a  mov     rbx, [r11+30h]
0x18000482e  mov     rbp, [r11+38h]
0x180004832  mov     rsp, r11
0x180004835  pop     r14
0x180004837  pop     rdi
0x180004838  pop     rsi
0x180004839  retn
```
