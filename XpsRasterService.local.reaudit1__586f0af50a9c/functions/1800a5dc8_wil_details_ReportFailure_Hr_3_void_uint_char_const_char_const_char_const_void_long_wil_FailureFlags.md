# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1800a5dc8`
- end: `0x1800a5e24`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800a69a8`

## callees

- `0x1800a1f44`
- `0x1800a3b6c`

## string_xrefs

- `0x1800a5de7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v6; // r9d
  _BYTE v7[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v7, 2147549183LL);
  wil::details::ReportFailure_Base<3,0>(
    v6,
    3585,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v6);
}

```

## disassembly

```asm
0x1800a5dc8  sub     rsp, 78h
0x1800a5dcc  mov     r9, rcx
0x1800a5dcf  mov     edx, 8000FFFFh
0x1800a5dd4  lea     rcx, [rsp+78h+var_18]
0x1800a5dd9  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800a5dde  mov     [rsp+78h+var_40], 0
0x1800a5de7  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800a5dee  mov     edx, 0E01h
0x1800a5df3  mov     rcx, r9
0x1800a5df6  movsd   xmm0, qword ptr [rax]
0x1800a5dfa  mov     eax, [rax+8]
0x1800a5dfd  mov     [rsp+78h+var_20], eax
0x1800a5e01  lea     rax, [rsp+78h+var_28]
0x1800a5e06  mov     [rsp+78h+var_48], rax
0x1800a5e0b  mov     rax, [rsp+78h+arg_28]
0x1800a5e13  mov     [rsp+78h+var_50], rax
0x1800a5e18  movsd   [rsp+78h+var_28], xmm0
0x1800a5e1e  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
