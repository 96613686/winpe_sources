# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x18009eb18`
- end: `0x18009eb74`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18009f4a4`

## callees

- `0x1800979b4`
- `0x1800995c0`

## string_xrefs

- `0x18009eb37`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    3546,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v6);
}

```

## disassembly

```asm
0x18009eb18  sub     rsp, 78h
0x18009eb1c  mov     r9, rcx
0x18009eb1f  mov     edx, 8000FFFFh
0x18009eb24  lea     rcx, [rsp+78h+var_18]
0x18009eb29  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18009eb2e  mov     [rsp+78h+var_40], 0
0x18009eb37  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18009eb3e  mov     edx, 0DDAh
0x18009eb43  mov     rcx, r9
0x18009eb46  movsd   xmm0, qword ptr [rax]
0x18009eb4a  mov     eax, [rax+8]
0x18009eb4d  mov     [rsp+78h+var_20], eax
0x18009eb51  lea     rax, [rsp+78h+var_28]
0x18009eb56  mov     [rsp+78h+var_48], rax
0x18009eb5b  mov     rax, [rsp+78h+arg_28]
0x18009eb63  mov     [rsp+78h+var_50], rax
0x18009eb68  movsd   [rsp+78h+var_28], xmm0
0x18009eb6e  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
