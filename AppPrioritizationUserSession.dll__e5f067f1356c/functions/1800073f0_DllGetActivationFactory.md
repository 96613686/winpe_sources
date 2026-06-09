# DllGetActivationFactory

- ea: `0x1800073f0`
- end: `0x18000759b`
- name: `DllGetActivationFactory`
- size: `427`
- prototype: `__int64 __fastcall(HSTRING string, struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002650`
- `0x180004994`
- `0x1800073f0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000742b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000742b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000747e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000747e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000744a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000744a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180007460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180007460`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180007570`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180007570`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180007505`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180007505`

## string_xrefs

- `0x180007539`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DllGetActivationFactory(HSTRING string, struct Microsoft::WRL::Details::CreatorMap *a2)
{
  PCWSTR StringRawBuffer; // r14
  const struct _GUID **v5; // rbx
  unsigned __int64 v6; // rbp
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // rax
  int v10; // r8d
  int v11; // edx
  unsigned int v12; // ebx
  struct IUnknown **v14; // [rsp+28h] [rbp-60h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-58h] BYREF
  int v16; // [rsp+34h] [rbp-54h] BYREF
  __int128 v17; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v18[22]; // [rsp+48h] [rbp-40h]

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    `Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_1800144E8 = 1;
  *(_QWORD *)a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v17 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v18 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v18[14] = *(_QWORD *)L"sId";
    v12 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v17);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                   + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                               + 8);
    v6 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                           + 48LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
    if ( (unsigned __int64)v5 >= v6 )
    {
LABEL_11:
      v12 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *v5 )
        {
          v7 = (*(__int64 (**)(void))(*v5)->Data4)();
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
        if ( (unsigned __int64)++v5 >= v6 )
          goto LABEL_11;
      }
      v16 = 1;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v16,
                             &GUID_00000035_0000_0000_c000_000000000046.Data1,
                             *v5,
                             a2,
                             v14);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x1800073f0  mov     [rsp+arg_10], rbx
0x1800073f5  mov     [rsp+arg_18], rbp
0x1800073fa  push    rsi
0x1800073fb  push    rdi
0x1800073fc  push    r14
0x1800073fe  sub     rsp, 70h
0x180007402  mov     rax, cs:__security_cookie
0x180007409  xor     rax, rsp
0x18000740c  mov     [rsp+88h+var_28], rax
0x180007411  mov     rsi, rdx
0x180007414  mov     rdi, rcx
0x180007417  xor     r9d, r9d; Context
0x18000741a  xor     r8d, r8d; Parameter
0x18000741d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@45@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180007424  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000742b  call    cs:__imp_InitOnceExecuteOnce
0x180007431  mov     cs:byte_1800144E8, 1
0x180007438  mov     qword ptr [rsi], 0
0x18000743f  mov     [rsp+88h+hasEmbedNull], 0
0x180007447  mov     rcx, rdi; string
0x18000744a  call    cs:__imp_WindowsIsStringEmpty
0x180007450  test    eax, eax
0x180007452  jnz     loc_180007539
0x180007458  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x18000745d  mov     rcx, rdi; string
0x180007460  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180007466  test    eax, eax
0x180007468  js      loc_180007539
0x18000746e  cmp     [rsp+88h+hasEmbedNull], 1
0x180007473  jz      loc_180007539
0x180007479  xor     edx, edx; length
0x18000747b  mov     rcx, rdi; string
0x18000747e  call    cs:__imp_WindowsGetStringRawBuffer
0x180007484  mov     r14, rax
0x180007487  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000748e  mov     rax, [rcx+28h]
0x180007492  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180007499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000749e  lea     rbx, [rax+8]
0x1800074a2  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800074a9  mov     rax, [rcx+30h]
0x1800074ad  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x1800074b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074b9  mov     rbp, rax
0x1800074bc  cmp     rbx, rax
0x1800074bf  jnb     short loc_1800074FB
0x1800074c1  mov     rax, [rbx]
0x1800074c4  test    rax, rax
0x1800074c7  jz      short loc_1800074F2
0x1800074c9  mov     rax, [rax+8]
0x1800074cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074d2  mov     rcx, r14
0x1800074d5  sub     rax, r14
0x1800074d8  movzx   edx, word ptr [rcx]
0x1800074db  movzx   r8d, word ptr [rcx+rax]
0x1800074e0  sub     edx, r8d
0x1800074e3  jnz     short loc_1800074EE
0x1800074e5  add     rcx, 2
0x1800074e9  test    r8d, r8d
0x1800074ec  jnz     short loc_1800074D8
0x1800074ee  test    edx, edx
0x1800074f0  jz      short loc_18000750D
0x1800074f2  add     rbx, 8
0x1800074f6  cmp     rbx, rbp
0x1800074f9  jb      short loc_1800074C1
0x1800074fb  mov     rdx, rdi
0x1800074fe  mov     ebx, 80040111h
0x180007503  mov     ecx, ebx
0x180007505  call    cs:__imp_RoOriginateError
0x18000750b  jmp     short loc_180007577
0x18000750d  mov     [rsp+88h+var_54], 1
0x180007515  mov     [rsp+88h+var_68], rsi; struct Microsoft::WRL::Details::CreatorMap *
0x18000751a  mov     r9, [rbx]; struct _GUID *
0x18000751d  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180007524  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x180007529  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180007530  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180007535  mov     ebx, eax
0x180007537  jmp     short loc_180007577
0x180007539  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180007540  movups  [rsp+88h+var_50], xmm0
0x180007545  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18000754c  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x180007551  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180007559  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x18000755f  lea     r8, [rsp+88h+var_50]
0x180007564  mov     edx, 12h
0x180007569  mov     ebx, 80070057h
0x18000756e  mov     ecx, ebx
0x180007570  call    cs:__imp_RoOriginateErrorW
0x180007576  nop
0x180007577  mov     eax, ebx
0x180007579  mov     rcx, [rsp+88h+var_28]
0x18000757e  xor     rcx, rsp; StackCookie
0x180007581  call    __security_check_cookie
0x180007586  lea     r11, [rsp+88h+var_18]
0x18000758b  mov     rbx, [r11+30h]
0x18000758f  mov     rbp, [r11+38h]
0x180007593  mov     rsp, r11
0x180007596  pop     r14
0x180007598  pop     rdi
0x180007599  pop     rsi
0x18000759a  retn
```
