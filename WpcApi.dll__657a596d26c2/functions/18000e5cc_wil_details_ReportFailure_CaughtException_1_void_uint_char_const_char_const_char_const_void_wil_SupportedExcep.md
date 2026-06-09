# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x18000e5cc`
- end: `0x18000e717`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `331`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001277c`

## callees

- `0x1800032a0`
- `0x180003d14`
- `0x180004f90`
- `0x180004fec`
- `0x180008250`
- `0x18000e5cc`
- `0x180028fe0`
- `0x18002c010`

## string_xrefs

- `0x18000e68c`: `shellcommon\internal\shell\inc\wpccore\CoreLib\ApiBoundary.h`
- `0x18000e6e5`: `shellcommon\internal\shell\inc\wpccore\CoreLib\ApiBoundary.h`

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
      63,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\wpccore\\CoreLib\\ApiBoundary.h",
      v8);
  }
  wil::details::ReportFailure_Base<1,0>(a1, 63, "shellcommon\\internal\\shell\\inc\\wpccore\\CoreLib\\ApiBoundary.h");
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e5cc  mov     [rsp-8+arg_8], rbx
0x18000e5d1  mov     [rsp-8+arg_10], rsi
0x18000e5d6  push    rbp
0x18000e5d7  push    rdi
0x18000e5d8  push    r14
0x18000e5da  lea     rbp, [rsp-0F90h]
0x18000e5e2  mov     eax, 1090h
0x18000e5e7  call    _alloca_probe
0x18000e5ec  sub     rsp, rax
0x18000e5ef  mov     rax, cs:__security_cookie
0x18000e5f6  xor     rax, rsp
0x18000e5f9  mov     [rbp+0FA0h+var_20], rax
0x18000e600  mov     rdi, [rbp+0FA0h+arg_28]
0x18000e607  mov     rbx, rcx
0x18000e60a  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x18000e60e  xor     edx, edx; Val
0x18000e610  mov     r8d, 1000h; Size
0x18000e616  call    memset_0
0x18000e61b  xor     r14d, r14d
0x18000e61e  lea     rax, [rbp+0FA0h+var_1020]
0x18000e622  mov     [rsp+10A0h+var_1050], r14b
0x18000e627  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e62b  inc     rcx
0x18000e62e  cmp     [rax+rcx*2], r14w
0x18000e633  jnz     short loc_18000E62B
0x18000e635  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18000e63c  test    rax, rax
0x18000e63f  jz      loc_18000E6D3
0x18000e645  mov     r8d, 800h
0x18000e64b  lea     rdx, [rbp+0FA0h+var_1020]
0x18000e64f  sub     r8, rcx
0x18000e652  lea     rdx, [rdx+rcx*2]
0x18000e656  lea     rcx, [rsp+10A0h+var_1038]
0x18000e65b  lea     r9, [rsp+10A0h+var_1050]
0x18000e660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e665  movsd   xmm0, qword ptr [rax]
0x18000e669  mov     eax, [rax+8]
0x18000e66c  movd    esi, xmm0
0x18000e670  movsd   [rsp+10A0h+var_1048], xmm0
0x18000e676  mov     [rsp+10A0h+var_1040], eax
0x18000e67a  test    esi, esi
0x18000e67c  jns     short loc_18000E6D3
0x18000e67e  lea     rax, [rbp+0FA0h+var_1020]
0x18000e682  mov     edx, 3Fh ; '?'
0x18000e687  mov     [rsp+10A0h+var_1068], rax
0x18000e68c  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\wpcc"...
0x18000e693  lea     rax, [rsp+10A0h+var_1048]
0x18000e698  mov     rcx, rbx
0x18000e69b  mov     [rsp+10A0h+var_1070], rax
0x18000e6a0  mov     [rsp+10A0h+var_1078], rdi
0x18000e6a5  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000e6aa  mov     eax, esi
0x18000e6ac  mov     rcx, [rbp+0FA0h+var_20]
0x18000e6b3  xor     rcx, rsp; StackCookie
0x18000e6b6  call    __security_check_cookie
0x18000e6bb  lea     r11, [rsp+10A0h+var_10]
0x18000e6c3  mov     rbx, [r11+28h]
0x18000e6c7  mov     rsi, [r11+30h]
0x18000e6cb  mov     rsp, r11
0x18000e6ce  pop     r14
0x18000e6d0  pop     rdi
0x18000e6d1  pop     rbp
0x18000e6d2  retn
0x18000e6d3  mov     ecx, 8007023Eh; this
0x18000e6d8  mov     dword ptr [rsp+10A0h+var_1048], ecx
0x18000e6dc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e6e1  mov     dword ptr [rsp+10A0h+var_1048+4], eax
0x18000e6e5  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\wpcc"...
0x18000e6ec  lea     rax, [rbp+0FA0h+var_1020]
0x18000e6f0  mov     [rsp+10A0h+var_1040], r14d
0x18000e6f5  mov     [rsp+10A0h+var_1068], rax
0x18000e6fa  mov     edx, 3Fh ; '?'
0x18000e6ff  lea     rax, [rsp+10A0h+var_1048]
0x18000e704  mov     rcx, rbx
0x18000e707  mov     [rsp+10A0h+var_1070], rax
0x18000e70c  mov     [rsp+10A0h+var_1078], rdi
0x18000e711  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
