# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x180008f04`
- end: `0x18000904f`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `331`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000aa7c`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180008e70`
- `0x180008ecc`
- `0x180008f04`
- `0x180009dd4`
- `0x18001d4b0`
- `0x18001f010`

## string_xrefs

- `0x180008fc4`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`
- `0x18000901d`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmcommandparser.cpp`

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
0x180008f04  mov     [rsp-8+arg_8], rbx
0x180008f09  mov     [rsp-8+arg_10], rsi
0x180008f0e  push    rbp
0x180008f0f  push    rdi
0x180008f10  push    r14
0x180008f12  lea     rbp, [rsp-0F90h]
0x180008f1a  mov     eax, 1090h
0x180008f1f  call    _alloca_probe
0x180008f24  sub     rsp, rax
0x180008f27  mov     rax, cs:__security_cookie
0x180008f2e  xor     rax, rsp
0x180008f31  mov     [rbp+0FA0h+var_20], rax
0x180008f38  mov     rdi, [rbp+0FA0h+arg_28]
0x180008f3f  mov     rbx, rcx
0x180008f42  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x180008f46  xor     edx, edx; Val
0x180008f48  mov     r8d, 1000h; Size
0x180008f4e  call    memset_0
0x180008f53  xor     r14d, r14d
0x180008f56  lea     rax, [rbp+0FA0h+var_1020]
0x180008f5a  mov     [rsp+10A0h+var_1050], r14b
0x180008f5f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008f63  inc     rcx
0x180008f66  cmp     [rax+rcx*2], r14w
0x180008f6b  jnz     short loc_180008F63
0x180008f6d  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x180008f74  test    rax, rax
0x180008f77  jz      loc_18000900B
0x180008f7d  mov     r8d, 800h
0x180008f83  lea     rdx, [rbp+0FA0h+var_1020]
0x180008f87  sub     r8, rcx
0x180008f8a  lea     rdx, [rdx+rcx*2]
0x180008f8e  lea     rcx, [rsp+10A0h+var_1038]
0x180008f93  lea     r9, [rsp+10A0h+var_1050]
0x180008f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f9d  movsd   xmm0, qword ptr [rax]
0x180008fa1  mov     eax, [rax+8]
0x180008fa4  movd    esi, xmm0
0x180008fa8  movsd   [rsp+10A0h+var_1048], xmm0
0x180008fae  mov     [rsp+10A0h+var_1040], eax
0x180008fb2  test    esi, esi
0x180008fb4  jns     short loc_18000900B
0x180008fb6  lea     rax, [rbp+0FA0h+var_1020]
0x180008fba  mov     edx, 87h
0x180008fbf  mov     [rsp+10A0h+var_1068], rax
0x180008fc4  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180008fcb  lea     rax, [rsp+10A0h+var_1048]
0x180008fd0  mov     rcx, rbx
0x180008fd3  mov     [rsp+10A0h+var_1070], rax
0x180008fd8  mov     [rsp+10A0h+var_1078], rdi
0x180008fdd  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180008fe2  mov     eax, esi
0x180008fe4  mov     rcx, [rbp+0FA0h+var_20]
0x180008feb  xor     rcx, rsp; StackCookie
0x180008fee  call    __security_check_cookie
0x180008ff3  lea     r11, [rsp+10A0h+var_10]
0x180008ffb  mov     rbx, [r11+28h]
0x180008fff  mov     rsi, [r11+30h]
0x180009003  mov     rsp, r11
0x180009006  pop     r14
0x180009008  pop     rdi
0x180009009  pop     rbp
0x18000900a  retn
0x18000900b  mov     ecx, 8007023Eh; this
0x180009010  mov     dword ptr [rsp+10A0h+var_1048], ecx
0x180009014  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009019  mov     dword ptr [rsp+10A0h+var_1048+4], eax
0x18000901d  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180009024  lea     rax, [rbp+0FA0h+var_1020]
0x180009028  mov     [rsp+10A0h+var_1040], r14d
0x18000902d  mov     [rsp+10A0h+var_1068], rax
0x180009032  mov     edx, 87h
0x180009037  lea     rax, [rsp+10A0h+var_1048]
0x18000903c  mov     rcx, rbx
0x18000903f  mov     [rsp+10A0h+var_1070], rax
0x180009044  mov     [rsp+10A0h+var_1078], rdi
0x180009049  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
