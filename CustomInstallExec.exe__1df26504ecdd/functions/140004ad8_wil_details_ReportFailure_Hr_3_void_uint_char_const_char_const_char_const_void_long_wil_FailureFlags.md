# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x140004ad8`
- end: `0x140004b2b`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `83`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005820`

## callees

- `0x140004900`
- `0x1400058c8`

## string_xrefs

- `0x140004aee`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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

  wil::details::ResultStatus::FromResult(v7, 2147549183LL, a3, a1);
  wil::details::ReportFailure_Base<3,0>(
    v6,
    3585,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v6);
}

```

## disassembly

```asm
0x140004ad8  sub     rsp, 78h
0x140004adc  mov     r9, rcx
0x140004adf  mov     edx, 8000FFFFh
0x140004ae4  lea     rcx, [rsp+78h+var_18]
0x140004ae9  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x140004aee  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004af5  mov     edx, 0E01h
0x140004afa  mov     rcx, r9
0x140004afd  movsd   xmm0, qword ptr [rax]
0x140004b01  mov     eax, [rax+8]
0x140004b04  mov     [rsp+78h+var_20], eax
0x140004b08  lea     rax, [rsp+78h+var_28]
0x140004b0d  mov     [rsp+78h+var_48], rax
0x140004b12  mov     rax, [rsp+78h+arg_28]
0x140004b1a  mov     [rsp+78h+var_50], rax
0x140004b1f  movsd   [rsp+78h+var_28], xmm0
0x140004b25  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
