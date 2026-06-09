# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180004aac`
- end: `0x180004b09`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006e7c`
- `0x18001e508`

## callees

- `0x180004880`
- `0x180006eac`

## string_xrefs

- `0x180004ace`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v7; // r10d
  _BYTE v8[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v8, 2147549183LL);
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v6);
}

```

## disassembly

```asm
0x180004aac  sub     rsp, 78h
0x180004ab0  mov     r10, rcx
0x180004ab3  mov     r9d, edx
0x180004ab6  mov     edx, 8000FFFFh
0x180004abb  lea     rcx, [rsp+78h+var_18]
0x180004ac0  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180004ac5  mov     [rsp+78h+var_40], 0
0x180004ace  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004ad5  mov     edx, r9d
0x180004ad8  mov     rcx, r10
0x180004adb  movsd   xmm0, qword ptr [rax]
0x180004adf  mov     eax, [rax+8]
0x180004ae2  mov     [rsp+78h+var_20], eax
0x180004ae6  lea     rax, [rsp+78h+var_28]
0x180004aeb  mov     [rsp+78h+var_48], rax
0x180004af0  mov     rax, [rsp+78h+arg_28]
0x180004af8  mov     [rsp+78h+var_50], rax
0x180004afd  movsd   [rsp+78h+var_28], xmm0
0x180004b03  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
