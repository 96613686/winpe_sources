# DllGetActivationFactory

- ea: `0x1800062c0`
- end: `0x18000646b`
- name: `DllGetActivationFactory`
- size: `427`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800016a0`
- `0x180005d34`
- `0x1800062c0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000631a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000631a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180006330`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180006330`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000634e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000634e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180006440`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180006440`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800063d5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800063d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800062fb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800062fb`

## string_xrefs

- `0x180006409`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(HSTRING string, _QWORD *Ptr)
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
  BOOL hasEmbedNull; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+34h] [rbp-54h] BYREF
  __int128 v16; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v17[22]; // [rsp+48h] [rbp-40h]

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180015488 = 1;
  *Ptr = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v16 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v17 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v17[14] = *(_QWORD *)L"sId";
    v12 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v16);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v5 = (const struct _GUID **)((*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                      + 40))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                               + 8);
    v6 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                              + 48))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
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
      v15 = 1;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v15,
                             &GUID_00000035_0000_0000_c000_000000000046.Data1,
                             *v5,
                             Ptr);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x1800062c0  mov     [rsp+arg_10], rbx
0x1800062c5  mov     [rsp+arg_18], rbp
0x1800062ca  push    rsi
0x1800062cb  push    rdi
0x1800062cc  push    r14
0x1800062ce  sub     rsp, 70h
0x1800062d2  mov     rax, cs:__security_cookie
0x1800062d9  xor     rax, rsp
0x1800062dc  mov     [rsp+88h+var_28], rax
0x1800062e1  mov     rsi, rdx
0x1800062e4  mov     rdi, rcx
0x1800062e7  xor     r9d, r9d; Context
0x1800062ea  xor     r8d, r8d; Parameter
0x1800062ed  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800062f4  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x1800062fb  call    cs:__imp_InitOnceExecuteOnce
0x180006301  mov     cs:byte_180015488, 1
0x180006308  mov     qword ptr [rsi], 0
0x18000630f  mov     [rsp+88h+hasEmbedNull], 0
0x180006317  mov     rcx, rdi; string
0x18000631a  call    cs:__imp_WindowsIsStringEmpty
0x180006320  test    eax, eax
0x180006322  jnz     loc_180006409
0x180006328  lea     rdx, [rsp+88h+hasEmbedNull]; hasEmbedNull
0x18000632d  mov     rcx, rdi; string
0x180006330  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180006336  test    eax, eax
0x180006338  js      loc_180006409
0x18000633e  cmp     [rsp+88h+hasEmbedNull], 1
0x180006343  jz      loc_180006409
0x180006349  xor     edx, edx; length
0x18000634b  mov     rcx, rdi; string
0x18000634e  call    cs:__imp_WindowsGetStringRawBuffer
0x180006354  mov     r14, rax
0x180006357  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000635e  mov     rax, [rcx+28h]
0x180006362  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636e  lea     rbx, [rax+8]
0x180006372  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006379  mov     rax, [rcx+30h]
0x18000637d  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006389  mov     rbp, rax
0x18000638c  cmp     rbx, rax
0x18000638f  jnb     short loc_1800063CB
0x180006391  mov     rax, [rbx]
0x180006394  test    rax, rax
0x180006397  jz      short loc_1800063C2
0x180006399  mov     rax, [rax+8]
0x18000639d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063a2  mov     rcx, r14
0x1800063a5  sub     rax, r14
0x1800063a8  movzx   edx, word ptr [rcx]
0x1800063ab  movzx   r8d, word ptr [rcx+rax]
0x1800063b0  sub     edx, r8d
0x1800063b3  jnz     short loc_1800063BE
0x1800063b5  add     rcx, 2
0x1800063b9  test    r8d, r8d
0x1800063bc  jnz     short loc_1800063A8
0x1800063be  test    edx, edx
0x1800063c0  jz      short loc_1800063DD
0x1800063c2  add     rbx, 8
0x1800063c6  cmp     rbx, rbp
0x1800063c9  jb      short loc_180006391
0x1800063cb  mov     rdx, rdi
0x1800063ce  mov     ebx, 80040111h
0x1800063d3  mov     ecx, ebx
0x1800063d5  call    cs:__imp_RoOriginateError
0x1800063db  jmp     short loc_180006447
0x1800063dd  mov     [rsp+88h+var_54], 1
0x1800063e5  mov     [rsp+88h+Ptr], rsi; Ptr
0x1800063ea  mov     r9, [rbx]; struct _GUID *
0x1800063ed  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x1800063f4  lea     rdx, [rsp+88h+var_54]; struct Microsoft::WRL::Details::ModuleBase *
0x1800063f9  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180006400  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180006405  mov     ebx, eax
0x180006407  jmp     short loc_180006447
0x180006409  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180006410  movups  [rsp+88h+var_50], xmm0
0x180006415  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18000641c  movups  xmmword ptr [rsp+88h+var_40], xmm1
0x180006421  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180006429  movsd   qword ptr [rsp+88h+var_40+0Eh], xmm0
0x18000642f  lea     r8, [rsp+88h+var_50]
0x180006434  mov     edx, 12h
0x180006439  mov     ebx, 80070057h
0x18000643e  mov     ecx, ebx
0x180006440  call    cs:__imp_RoOriginateErrorW
0x180006446  nop
0x180006447  mov     eax, ebx
0x180006449  mov     rcx, [rsp+88h+var_28]
0x18000644e  xor     rcx, rsp; StackCookie
0x180006451  call    __security_check_cookie
0x180006456  lea     r11, [rsp+88h+var_18]
0x18000645b  mov     rbx, [r11+30h]
0x18000645f  mov     rbp, [r11+38h]
0x180006463  mov     rsp, r11
0x180006466  pop     r14
0x180006468  pop     rdi
0x180006469  pop     rsi
0x18000646a  retn
```
