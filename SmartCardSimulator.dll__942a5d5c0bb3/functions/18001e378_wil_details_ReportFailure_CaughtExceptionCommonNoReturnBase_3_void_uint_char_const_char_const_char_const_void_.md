# wil::details::ReportFailure_CaughtExceptionCommonNoReturnBase<3>(void *,uint,char const *,char const *,char const *,void *,ushort *,unsigned __int64,wil::SupportedExceptions)

- ea: `0x18001e378`
- end: `0x18001e45a`
- name: `??$ReportFailure_CaughtExceptionCommonNoReturnBase@$02@details@wil@@YA?AUResultStatus@01@PEAXIPEBD110PEAG_KW4SupportedExceptions@1@@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001e348`

## callees

- `0x1800038fc`
- `0x1800051b8`
- `0x18001e378`
- `0x18005e010`

## string_xrefs

- `0x18001e3f7`: `onecore\internal\ds\inc\private\security\scard\vscr\inc\errorcontract.h`
- `0x18001e428`: `onecore\internal\ds\inc\private\security\scard\vscr\inc\errorcontract.h`

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
        __int64 a8,
        int a9,
        char a10)
{
  __int64 v10; // rcx
  int v13; // r9d
  int v14; // r9d
  _BYTE v15[56]; // [rsp+60h] [rbp-38h] BYREF

  a10 = 0;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(a8 + 2 * v10) );
  if ( g_pfnResultFromCaughtExceptionInternal )
  {
    if ( _mm_cvtsi128_si32((__m128i)*(unsigned __int64 *)g_pfnResultFromCaughtExceptionInternal(
                                                           v15,
                                                           a8 + 2 * v10,
                                                           2048 - v10,
                                                           &a10)) < 0 )
      wil::details::ReportFailure_Base<3,0>(
        a2,
        a3,
        (unsigned int)"onecore\\internal\\ds\\inc\\private\\security\\scard\\vscr\\inc\\errorcontract.h",
        v13);
  }
  wil::details::HrToNtStatus((wil::details *)0x8007023ELL, a2);
  wil::details::ReportFailure_Base<3,0>(
    a2,
    a3,
    (unsigned int)"onecore\\internal\\ds\\inc\\private\\security\\scard\\vscr\\inc\\errorcontract.h",
    v14);
}

```

## disassembly

```asm
0x18001e378  mov     rax, rsp
0x18001e37b  push    rbx
0x18001e37c  push    rbp
0x18001e37d  push    rsi
0x18001e37e  push    rdi
0x18001e37f  sub     rsp, 78h
0x18001e383  mov     rbx, [rsp+98h+arg_38]
0x18001e38b  xor     ebp, ebp
0x18001e38d  mov     [rax+50h], bpl
0x18001e391  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001e395  mov     edi, r8d
0x18001e398  mov     rsi, rdx
0x18001e39b  inc     rcx
0x18001e39e  cmp     [rbx+rcx*2], bp
0x18001e3a2  jnz     short loc_18001E39B
0x18001e3a4  mov     rax, cs:g_pfnResultFromCaughtExceptionInternal
0x18001e3ab  test    rax, rax
0x18001e3ae  jz      short loc_18001E416
0x18001e3b0  lea     rdx, [rbx+rcx*2]
0x18001e3b4  mov     r8d, 800h
0x18001e3ba  sub     r8, rcx
0x18001e3bd  lea     r9, [rsp+98h+arg_48]
0x18001e3c5  lea     rcx, [rsp+98h+var_38]
0x18001e3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3cf  movsd   xmm0, qword ptr [rax]
0x18001e3d3  mov     eax, [rax+8]
0x18001e3d6  mov     [rsp+98h+var_40], eax
0x18001e3da  movd    eax, xmm0
0x18001e3de  movsd   [rsp+98h+var_48], xmm0
0x18001e3e4  test    eax, eax
0x18001e3e6  jns     short loc_18001E416
0x18001e3e8  lea     rax, [rsp+98h+var_48]
0x18001e3ed  mov     [rsp+98h+var_60], rbx
0x18001e3f2  mov     [rsp+98h+var_68], rax
0x18001e3f7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\ds\\inc\\private\\se"...
0x18001e3fe  mov     rax, [rsp+98h+arg_30]
0x18001e406  mov     edx, edi
0x18001e408  mov     rcx, rsi
0x18001e40b  mov     [rsp+98h+var_70], rax
0x18001e410  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18001e416  mov     ecx, 8007023Eh; this
0x18001e41b  mov     dword ptr [rsp+98h+var_48], ecx
0x18001e41f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001e424  mov     dword ptr [rsp+98h+var_48+4], eax
0x18001e428  lea     r8, aOnecoreInterna_0; "onecore\\internal\\ds\\inc\\private\\se"...
0x18001e42f  lea     rax, [rsp+98h+var_48]
0x18001e434  mov     [rsp+98h+var_60], rbx
0x18001e439  mov     [rsp+98h+var_68], rax
0x18001e43e  mov     edx, edi
0x18001e440  mov     rax, [rsp+98h+arg_30]
0x18001e448  mov     rcx, rsi
0x18001e44b  mov     [rsp+98h+var_70], rax
0x18001e450  mov     [rsp+98h+var_40], ebp
0x18001e454  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
