# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x140007690`
- end: `0x1400077db`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000c914`

## callees

- `0x14000295f`
- `0x140002b88`
- `0x140002be4`
- `0x140004a24`
- `0x140007690`
- `0x14000e1c0`
- `0x14000e280`
- `0x14000f010`

## string_xrefs

- `0x140007750`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`
- `0x1400077a9`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`

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
      46,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h",
      v8);
  }
  wil::details::ReportFailure_Base<1,0>(a1, 46, "onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h");
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140007690  mov     [rsp-8+arg_8], rbx
0x140007695  mov     [rsp-8+arg_10], rsi
0x14000769a  push    rbp
0x14000769b  push    rdi
0x14000769c  push    r14
0x14000769e  lea     rbp, [rsp-0F90h]
0x1400076a6  mov     eax, 1090h
0x1400076ab  call    _alloca_probe
0x1400076b0  sub     rsp, rax
0x1400076b3  mov     rax, cs:__security_cookie
0x1400076ba  xor     rax, rsp
0x1400076bd  mov     [rbp+0FA0h+var_20], rax
0x1400076c4  mov     rdi, [rbp+0FA0h+arg_28]
0x1400076cb  mov     rbx, rcx
0x1400076ce  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x1400076d2  xor     edx, edx; Val
0x1400076d4  mov     r8d, 1000h; Size
0x1400076da  call    memset_0
0x1400076df  xor     r14d, r14d
0x1400076e2  lea     rax, [rbp+0FA0h+var_1020]
0x1400076e6  mov     [rsp+10A0h+var_1050], r14b
0x1400076eb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400076ef  inc     rcx
0x1400076f2  cmp     [rax+rcx*2], r14w
0x1400076f7  jnz     short loc_1400076EF
0x1400076f9  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x140007700  test    rax, rax
0x140007703  jz      loc_140007797
0x140007709  mov     r8d, 800h
0x14000770f  lea     rdx, [rbp+0FA0h+var_1020]
0x140007713  sub     r8, rcx
0x140007716  lea     rdx, [rdx+rcx*2]
0x14000771a  lea     rcx, [rsp+10A0h+var_1038]
0x14000771f  lea     r9, [rsp+10A0h+var_1050]
0x140007724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007729  movsd   xmm0, qword ptr [rax]
0x14000772d  mov     eax, [rax+8]
0x140007730  movd    esi, xmm0
0x140007734  movsd   [rsp+10A0h+var_1048], xmm0
0x14000773a  mov     [rsp+10A0h+var_1040], eax
0x14000773e  test    esi, esi
0x140007740  jns     short loc_140007797
0x140007742  lea     rax, [rbp+0FA0h+var_1020]
0x140007746  mov     edx, 2Eh ; '.'
0x14000774b  mov     [rsp+10A0h+var_1068], rax
0x140007750  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x140007757  lea     rax, [rsp+10A0h+var_1048]
0x14000775c  mov     rcx, rbx
0x14000775f  mov     [rsp+10A0h+var_1070], rax
0x140007764  mov     [rsp+10A0h+var_1078], rdi
0x140007769  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x14000776e  mov     eax, esi
0x140007770  mov     rcx, [rbp+0FA0h+var_20]
0x140007777  xor     rcx, rsp; StackCookie
0x14000777a  call    __security_check_cookie
0x14000777f  lea     r11, [rsp+10A0h+var_10]
0x140007787  mov     rbx, [r11+28h]
0x14000778b  mov     rsi, [r11+30h]
0x14000778f  mov     rsp, r11
0x140007792  pop     r14
0x140007794  pop     rdi
0x140007795  pop     rbp
0x140007796  retn
0x140007797  mov     ecx, 8007023Eh; this
0x14000779c  mov     dword ptr [rsp+10A0h+var_1048], ecx
0x1400077a0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400077a5  mov     dword ptr [rsp+10A0h+var_1048+4], eax
0x1400077a9  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x1400077b0  lea     rax, [rbp+0FA0h+var_1020]
0x1400077b4  mov     [rsp+10A0h+var_1040], r14d
0x1400077b9  mov     [rsp+10A0h+var_1068], rax
0x1400077be  mov     edx, 2Eh ; '.'
0x1400077c3  lea     rax, [rsp+10A0h+var_1048]
0x1400077c8  mov     rcx, rbx
0x1400077cb  mov     [rsp+10A0h+var_1070], rax
0x1400077d0  mov     [rsp+10A0h+var_1078], rdi
0x1400077d5  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
