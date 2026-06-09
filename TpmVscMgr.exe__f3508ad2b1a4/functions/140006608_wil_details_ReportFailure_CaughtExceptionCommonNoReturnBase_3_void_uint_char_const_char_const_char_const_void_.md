# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x140006608`
- end: `0x1400066f6`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400065d8`

## callees

- `0x140002520`
- `0x1400042f0`
- `0x140006608`
- `0x140013010`

## string_xrefs

- `0x14000668d`: `onecore\internal\ds\inc\private\security\scard\vscr\inc\errorcontract.h`
- `0x1400066c1`: `onecore\internal\ds\inc\private\security\scard\vscr\inc\errorcontract.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v8; // rcx
  int v10; // r9d
  int v11; // r9d
  _BYTE v12[24]; // [rsp+60h] [rbp-18h] BYREF
  int v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  LOBYTE(v13) = 0;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(a8 + 2 * v8) );
  if ( g_pfnResultFromCaughtExceptionInternal )
  {
    if ( _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(
                                                           v12,
                                                           a8 + 2 * v8,
                                                           2048 - v8,
                                                           &v13)) < 0 )
      wil::details::ReportFailure_Base<3,0>(
        a2,
        97,
        (unsigned int)"onecore\\internal\\ds\\inc\\private\\security\\scard\\vscr\\inc\\errorcontract.h",
        v10);
  }
  wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  wil::details::ReportFailure_Base<3,0>(
    a2,
    97,
    (unsigned int)"onecore\\internal\\ds\\inc\\private\\security\\scard\\vscr\\inc\\errorcontract.h",
    v11);
}

```

## disassembly

```asm
0x140006608  mov     rax, rsp
0x14000660b  mov     [rax+8], rbx
0x14000660f  mov     [rax+10h], rsi
0x140006613  mov     [rax+18h], r8d
0x140006617  push    rdi
0x140006618  sub     rsp, 70h
0x14000661c  mov     rbx, [rsp+78h+arg_38]
0x140006624  xor     esi, esi
0x140006626  mov     [rax+18h], sil
0x14000662a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000662e  mov     rdi, rdx
0x140006631  inc     rcx
0x140006634  cmp     [rbx+rcx*2], si
0x140006638  jnz     short loc_140006631
0x14000663a  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x140006641  test    rax, rax
0x140006644  jz      short loc_1400066AF
0x140006646  lea     rdx, [rbx+rcx*2]
0x14000664a  mov     r8d, 800h
0x140006650  sub     r8, rcx
0x140006653  lea     r9, [rsp+78h+arg_10]
0x14000665b  lea     rcx, [rsp+78h+var_18]
0x140006660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006665  movsd   xmm0, qword ptr [rax]
0x140006669  mov     eax, [rax+8]
0x14000666c  mov     [rsp+78h+var_20], eax
0x140006670  movd    eax, xmm0
0x140006674  movsd   [rsp+78h+var_28], xmm0
0x14000667a  test    eax, eax
0x14000667c  jns     short loc_1400066AF
0x14000667e  lea     rax, [rsp+78h+var_28]
0x140006683  mov     [rsp+78h+var_40], rbx
0x140006688  mov     [rsp+78h+var_48], rax
0x14000668d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\ds\\inc\\private\\se"...
0x140006694  mov     rax, [rsp+78h+arg_30]
0x14000669c  mov     edx, 61h ; 'a'
0x1400066a1  mov     rcx, rdi
0x1400066a4  mov     [rsp+78h+var_50], rax
0x1400066a9  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1400066af  mov     ecx, 8007023Eh; this
0x1400066b4  mov     dword ptr [rsp+78h+var_28], ecx
0x1400066b8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400066bd  mov     dword ptr [rsp+78h+var_28+4], eax
0x1400066c1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\ds\\inc\\private\\se"...
0x1400066c8  lea     rax, [rsp+78h+var_28]
0x1400066cd  mov     [rsp+78h+var_40], rbx
0x1400066d2  mov     [rsp+78h+var_48], rax
0x1400066d7  mov     edx, 61h ; 'a'
0x1400066dc  mov     rax, [rsp+78h+arg_30]
0x1400066e4  mov     rcx, rdi
0x1400066e7  mov     [rsp+78h+var_50], rax
0x1400066ec  mov     [rsp+78h+var_20], esi
0x1400066f0  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
