# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1800063ac`
- end: `0x180006409`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007a70`
- `0x180009be4`

## callees

- `0x18000380c`
- `0x180005f78`

## string_xrefs

- `0x1800063ce`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v6; // r9d
  int v7; // r10d
  _BYTE v8[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v8, 2147549183LL, a3, a2);
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v6);
}

```

## disassembly

```asm
0x1800063ac  sub     rsp, 78h
0x1800063b0  mov     r10, rcx
0x1800063b3  mov     r9d, edx
0x1800063b6  mov     edx, 8000FFFFh
0x1800063bb  lea     rcx, [rsp+78h+var_18]
0x1800063c0  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800063c5  mov     [rsp+78h+var_40], 0
0x1800063ce  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800063d5  mov     edx, r9d
0x1800063d8  mov     rcx, r10
0x1800063db  movsd   xmm0, qword ptr [rax]
0x1800063df  mov     eax, [rax+8]
0x1800063e2  mov     [rsp+78h+var_20], eax
0x1800063e6  lea     rax, [rsp+78h+var_28]
0x1800063eb  mov     [rsp+78h+var_48], rax
0x1800063f0  mov     rax, [rsp+78h+arg_28]
0x1800063f8  mov     [rsp+78h+var_50], rax
0x1800063fd  movsd   [rsp+78h+var_28], xmm0
0x180006403  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
