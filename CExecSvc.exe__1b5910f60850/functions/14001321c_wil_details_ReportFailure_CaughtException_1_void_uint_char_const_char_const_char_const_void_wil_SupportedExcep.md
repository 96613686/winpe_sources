# wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)

- ea: `0x14001321c`
- end: `0x140013367`
- name: `??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z`
- size: `331`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140014194`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x140005154`
- `0x1400051b4`
- `0x140009f4c`
- `0x14001321c`
- `0x140021f90`
- `0x140024010`

## string_xrefs

- `0x1400132dc`: `onecore\vm\common\vml\VmModules.h`
- `0x140013335`: `onecore\vm\common\vml\VmModules.h`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_CaughtException<1>(__int64 a1)
{
  int v2; // edx
  __int64 v3; // rcx
  int v4; // esi
  int v6; // r9d
  _BYTE v7[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v8[16]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v9[2048]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(v9, 0, sizeof(v9));
  v8[0] = 0;
  v3 = -1;
  do
    ++v3;
  while ( v9[v3] );
  if ( !g_pfnResultFromCaughtExceptionInternal
    || (v4 = _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(
                                                               v7,
                                                               &v9[v3],
                                                               2048 - v3,
                                                               v8)),
        v4 >= 0) )
  {
    wil::details::HrToNtStatus((wil::details *)0x8007023ELL, v2);
    wil::details::ReportFailure_Base<3,0>(a1, 3224, (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h", v6);
  }
  wil::details::ReportFailure_Base<1,0>(a1, 3224, "onecore\\vm\\common\\vml\\VmModules.h");
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14001321c  mov     [rsp-8+arg_8], rbx
0x140013221  mov     [rsp-8+arg_10], rsi
0x140013226  push    rbp
0x140013227  push    rdi
0x140013228  push    r14
0x14001322a  lea     rbp, [rsp-0F90h]
0x140013232  mov     eax, 1090h
0x140013237  call    _alloca_probe
0x14001323c  sub     rsp, rax
0x14001323f  mov     rax, cs:__security_cookie
0x140013246  xor     rax, rsp
0x140013249  mov     [rbp+0FA0h+var_20], rax
0x140013250  mov     rdi, [rbp+0FA0h+arg_28]
0x140013257  mov     rbx, rcx
0x14001325a  lea     rcx, [rbp+0FA0h+var_1020]; void *
0x14001325e  xor     edx, edx; Val
0x140013260  mov     r8d, 1000h; Size
0x140013266  call    memset_0
0x14001326b  xor     r14d, r14d
0x14001326e  lea     rax, [rbp+0FA0h+var_1020]
0x140013272  mov     [rsp+10A0h+var_1030], r14b
0x140013277  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14001327b  inc     rcx
0x14001327e  cmp     [rax+rcx*2], r14w
0x140013283  jnz     short loc_14001327B
0x140013285  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x14001328c  test    rax, rax
0x14001328f  jz      loc_140013323
0x140013295  mov     r8d, 800h
0x14001329b  lea     rdx, [rbp+0FA0h+var_1020]
0x14001329f  sub     r8, rcx
0x1400132a2  lea     rdx, [rdx+rcx*2]
0x1400132a6  lea     rcx, [rsp+10A0h+var_1040]
0x1400132ab  lea     r9, [rsp+10A0h+var_1030]
0x1400132b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400132b5  movsd   xmm0, qword ptr [rax]
0x1400132b9  mov     eax, [rax+8]
0x1400132bc  movd    esi, xmm0
0x1400132c0  movsd   [rsp+10A0h+var_1050], xmm0
0x1400132c6  mov     [rsp+10A0h+var_1048], eax
0x1400132ca  test    esi, esi
0x1400132cc  jns     short loc_140013323
0x1400132ce  lea     rax, [rbp+0FA0h+var_1020]
0x1400132d2  mov     edx, 0C98h
0x1400132d7  mov     [rsp+10A0h+var_1068], rax
0x1400132dc  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x1400132e3  lea     rax, [rsp+10A0h+var_1050]
0x1400132e8  mov     rcx, rbx
0x1400132eb  mov     [rsp+10A0h+var_1070], rax
0x1400132f0  mov     [rsp+10A0h+var_1078], rdi
0x1400132f5  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1400132fa  mov     eax, esi
0x1400132fc  mov     rcx, [rbp+0FA0h+var_20]
0x140013303  xor     rcx, rsp; StackCookie
0x140013306  call    __security_check_cookie
0x14001330b  lea     r11, [rsp+10A0h+var_10]
0x140013313  mov     rbx, [r11+28h]
0x140013317  mov     rsi, [r11+30h]
0x14001331b  mov     rsp, r11
0x14001331e  pop     r14
0x140013320  pop     rdi
0x140013321  pop     rbp
0x140013322  retn
0x140013323  mov     ecx, 8007023Eh; this
0x140013328  mov     dword ptr [rsp+10A0h+var_1050], ecx
0x14001332c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140013331  mov     dword ptr [rsp+10A0h+var_1050+4], eax
0x140013335  lea     r8, aOnecoreVmCommo; "onecore\\vm\\common\\vml\\VmModules.h"
0x14001333c  lea     rax, [rbp+0FA0h+var_1020]
0x140013340  mov     [rsp+10A0h+var_1048], r14d
0x140013345  mov     [rsp+10A0h+var_1068], rax
0x14001334a  mov     edx, 0C98h
0x14001334f  lea     rax, [rsp+10A0h+var_1050]
0x140013354  mov     rcx, rbx
0x140013357  mov     [rsp+10A0h+var_1070], rax
0x14001335c  mov     [rsp+10A0h+var_1078], rdi
0x140013361  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
