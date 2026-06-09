# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x1800090bc`
- end: `0x180009208`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000aca4`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180009028`
- `0x180009084`
- `0x1800090bc`
- `0x180009fd0`
- `0x18001db90`
- `0x18001f010`

## string_xrefs

- `0x18000917c`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x1800091d6`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<1>(__int64 a1)
{
  int v2; // edx
  __int64 v3; // rcx
  unsigned __int64 *v4; // rax
  __m128i v5; // xmm0
  int v6; // esi
  int v8; // r9d
  _BYTE v9[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v10; // [rsp+58h] [rbp-A8h]
  int v11; // [rsp+60h] [rbp-A0h]
  _BYTE v12[24]; // [rsp+68h] [rbp-98h] BYREF
  _WORD v13[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v13, 0, sizeof(v13));
  v9[0] = 0;
  v3 = -1;
  do
    ++v3;
  while ( v13[v3] );
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v4 = (unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(v12, &v13[v3], 2048 - v3, v9),
        v5 = (__m128i)*v4,
        LODWORD(v4) = *((_DWORD *)v4 + 2),
        v6 = _mm_cvtsi128_si32(v5),
        v10 = v5.m128i_i64[0],
        v11 = (int)v4,
        v6 >= 0) )
  {
    LODWORD(v10) = -2147024322;
    HIDWORD(v10) = wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v2);
    v11 = 0;
    wil::details::ReportFailure_Base<3,0>(
      a1,
      135,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp",
      v8);
  }
  wil::details::ReportFailure_Base<1,0>(
    a1,
    135,
    "onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmcommandparser.cpp");
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800090bc  mov     [rsp-8+arg_8], rbx
0x1800090c1  mov     [rsp-8+arg_10], rsi
0x1800090c6  push    rbp
0x1800090c7  push    rdi
0x1800090c8  push    r14
0x1800090ca  lea     rbp, [rsp-0F90h]
0x1800090d2  mov     eax, 1090h
0x1800090d7  call    _alloca_probe
0x1800090dc  sub     rsp, rax
0x1800090df  mov     rax, cs:__security_cookie
0x1800090e6  xor     rax, rsp
0x1800090e9  mov     [rbp+0FA0h+var_20], rax
0x1800090f0  mov     rdi, [rbp+0FA0h+arg_28]
0x1800090f7  mov     rbx, rcx
0x1800090fa  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x1800090fe  xor     edx, edx; Val
0x180009100  mov     r8d, 1000h; Size
0x180009106  call    memset_0
0x18000910b  xor     r14d, r14d
0x18000910e  lea     rax, [rbp+0FA0h+var_1020]
0x180009112  mov     [rsp+10A0h+var_1050], r14b
0x180009117  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000911b  inc     rcx
0x18000911e  cmp     [rax+rcx*2], r14w
0x180009123  jnz     short loc_18000911B
0x180009125  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000912c  test    rax, rax
0x18000912f  jz      loc_1800091C4
0x180009135  mov     r8d, 800h
0x18000913b  lea     rdx, [rbp+0FA0h+var_1020]
0x18000913f  sub     r8, rcx
0x180009142  lea     rdx, [rdx+rcx*2]
0x180009146  lea     rcx, [rsp+10A0h+var_1038]
0x18000914b  lea     r9, [rsp+10A0h+var_1050]
0x180009150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009155  movsd   xmm0, qword ptr [rax]
0x180009159  mov     eax, [rax+8]
0x18000915c  movd    esi, xmm0
0x180009160  movsd   [rsp+10A0h+var_1048], xmm0
0x180009166  mov     [rsp+10A0h+var_1040], eax
0x18000916a  test    esi, esi
0x18000916c  jns     short loc_1800091C4
0x18000916e  lea     rax, [rbp+0FA0h+var_1020]
0x180009172  mov     edx, 87h
0x180009177  mov     [rsp+10A0h+var_1068], rax
0x18000917c  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180009183  lea     rax, [rsp+10A0h+var_1048]
0x180009188  mov     rcx, rbx
0x18000918b  mov     [rsp+10A0h+var_1070], rax
0x180009190  mov     [rsp+10A0h+var_1078], rdi
0x180009195  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000919a  mov     eax, esi
0x18000919c  mov     rcx, [rbp+0FA0h+var_20]
0x1800091a3  xor     rcx, rsp; StackCookie
0x1800091a6  call    __security_check_cookie
0x1800091ab  lea     r11, [rsp+10A0h+var_10]
0x1800091b3  mov     rbx, [r11+28h]
0x1800091b7  mov     rsi, [r11+30h]
0x1800091bb  mov     rsp, r11
0x1800091be  pop     r14
0x1800091c0  pop     rdi
0x1800091c1  pop     rbp
0x1800091c2  retn
0x1800091c4  mov     ecx, 8007023Eh; this
0x1800091c9  mov     dword ptr [rsp+10A0h+var_1048], ecx
0x1800091cd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800091d2  mov     dword ptr [rsp+10A0h+var_1048+4], eax
0x1800091d6  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800091dd  lea     rax, [rbp+0FA0h+var_1020]
0x1800091e1  mov     [rsp+10A0h+var_1040], r14d
0x1800091e6  mov     [rsp+10A0h+var_1068], rax
0x1800091eb  mov     edx, 87h
0x1800091f0  lea     rax, [rsp+10A0h+var_1048]
0x1800091f5  mov     rcx, rbx
0x1800091f8  mov     [rsp+10A0h+var_1070], rax
0x1800091fd  mov     [rsp+10A0h+var_1078], rdi
0x180009202  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
