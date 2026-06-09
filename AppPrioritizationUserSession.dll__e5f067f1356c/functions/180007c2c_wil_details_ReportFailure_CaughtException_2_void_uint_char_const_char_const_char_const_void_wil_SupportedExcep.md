# wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x180007c2c`
- end: `0x180007d8f`
- name: `??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180009e78`

## callees

- `0x180002650`
- `0x1800032a4`
- `0x18000349c`
- `0x1800034f0`
- `0x180005590`
- `0x180007c2c`
- `0x18000bec0`
- `0x18000d010`

## string_xrefs

- `0x180007cfb`: `onecoreuap\net\wcm\service\base\appprioritizationusersessionhost\lib\appprioritizationusersession.cpp`
- `0x180007d60`: `onecoreuap\net\wcm\service\base\appprioritizationusersessionhost\lib\appprioritizationusersession.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<2>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v8; // edx
  __int64 v9; // rcx
  __int64 v10; // rax
  int v12; // r9d
  unsigned __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+58h] [rbp-A8h]
  _BYTE v15[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[16]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v17[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v17, 0, sizeof(v17));
  v16[0] = 0;
  v9 = -1;
  do
    ++v9;
  while ( v17[v9] );
  v13 = 0;
  v14 = 1;
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v10 = g_pfnResultFromCaughtExceptionInternal(v15, &v17[v9], 2048 - v9, v16),
        v13 = *(_QWORD *)v10,
        v14 = *(_DWORD *)(v10 + 8),
        _mm_cvtsi128_si32((__m128i)v13) >= 0) )
  {
    LODWORD(v13) = -2147024322;
    HIDWORD(v13) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v8);
    v14 = 0;
    wil::details::ReportFailure_Base<3,0>(
      a1,
      a2,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\appprioritizationusersessionhost\\lib\\appprioritizationusersession.cpp",
      v12);
  }
  wil::details::ReportFailure_Base<2,0>(
    a1,
    a2,
    (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\appprioritizationusersessionhost\\lib\\appprioritizationusersession.cpp",
    0,
    0,
    a6,
    (__int64)&v13,
    (__int64)v17);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180007c2c  mov     [rsp-8+arg_10], rbx
0x180007c31  mov     [rsp-8+arg_18], rsi
0x180007c36  push    rbp
0x180007c37  push    rdi
0x180007c38  push    r14
0x180007c3a  lea     rbp, [rsp-0F90h]
0x180007c42  mov     eax, 1090h
0x180007c47  call    _alloca_probe
0x180007c4c  sub     rsp, rax
0x180007c4f  mov     rax, cs:__security_cookie
0x180007c56  xor     rax, rsp
0x180007c59  mov     [rbp+0FA0h+var_20], rax
0x180007c60  mov     rsi, [rbp+0FA0h+arg_28]
0x180007c67  mov     edi, edx
0x180007c69  mov     rbx, rcx
0x180007c6c  xor     edx, edx; Val
0x180007c6e  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x180007c72  mov     r8d, 1000h; Size
0x180007c78  call    memset_0
0x180007c7d  xor     r14d, r14d
0x180007c80  lea     rax, [rbp+0FA0h+var_1020]
0x180007c84  mov     [rsp+10A0h+var_1030], r14b
0x180007c89  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007c8d  inc     rcx
0x180007c90  cmp     [rax+rcx*2], r14w
0x180007c95  jnz     short loc_180007C8D
0x180007c97  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180007c9e  mov     [rsp+10A0h+var_1050], r14
0x180007ca3  mov     [rsp+10A0h+var_1048], 1
0x180007cab  test    rax, rax
0x180007cae  jz      loc_180007D4E
0x180007cb4  mov     r8d, 800h
0x180007cba  lea     rdx, [rbp+0FA0h+var_1020]
0x180007cbe  sub     r8, rcx
0x180007cc1  lea     rdx, [rdx+rcx*2]
0x180007cc5  lea     rcx, [rsp+10A0h+var_1040]
0x180007cca  lea     r9, [rsp+10A0h+var_1030]
0x180007ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cd4  movsd   xmm0, qword ptr [rax]
0x180007cd8  movsd   [rsp+10A0h+var_1050], xmm0
0x180007cde  mov     eax, [rax+8]
0x180007ce1  mov     [rsp+10A0h+var_1048], eax
0x180007ce5  movd    eax, xmm0
0x180007ce9  test    eax, eax
0x180007ceb  jns     short loc_180007D4E
0x180007ced  mov     [rsp+10A0h+var_1058], r14d
0x180007cf2  lea     rax, [rbp+0FA0h+var_1020]
0x180007cf6  mov     [rsp+10A0h+var_1068], rax
0x180007cfb  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\service\\base\\ap"...
0x180007d02  lea     rax, [rsp+10A0h+var_1050]
0x180007d07  xor     r9d, r9d
0x180007d0a  mov     [rsp+10A0h+var_1070], rax
0x180007d0f  mov     edx, edi
0x180007d11  mov     [rsp+10A0h+var_1078], rsi
0x180007d16  mov     rcx, rbx
0x180007d19  mov     [rsp+10A0h+var_1080], r14
0x180007d1e  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180007d23  mov     eax, dword ptr [rsp+10A0h+var_1050]
0x180007d27  mov     rcx, [rbp+0FA0h+var_20]
0x180007d2e  xor     rcx, rsp; StackCookie
0x180007d31  call    __security_check_cookie
0x180007d36  lea     r11, [rsp+10A0h+var_10]
0x180007d3e  mov     rbx, [r11+30h]
0x180007d42  mov     rsi, [r11+38h]
0x180007d46  mov     rsp, r11
0x180007d49  pop     r14
0x180007d4b  pop     rdi
0x180007d4c  pop     rbp
0x180007d4d  retn
0x180007d4e  mov     ecx, 8007023Eh; this
0x180007d53  mov     dword ptr [rsp+10A0h+var_1050], ecx
0x180007d57  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007d5c  mov     dword ptr [rsp+10A0h+var_1050+4], eax
0x180007d60  lea     r8, aOnecoreuapNetW; "onecoreuap\\net\\wcm\\service\\base\\ap"...
0x180007d67  lea     rax, [rbp+0FA0h+var_1020]
0x180007d6b  mov     [rsp+10A0h+var_1048], r14d
0x180007d70  mov     [rsp+10A0h+var_1068], rax
0x180007d75  mov     edx, edi
0x180007d77  lea     rax, [rsp+10A0h+var_1050]
0x180007d7c  mov     rcx, rbx
0x180007d7f  mov     [rsp+10A0h+var_1070], rax
0x180007d84  mov     [rsp+10A0h+var_1078], rsi
0x180007d89  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
