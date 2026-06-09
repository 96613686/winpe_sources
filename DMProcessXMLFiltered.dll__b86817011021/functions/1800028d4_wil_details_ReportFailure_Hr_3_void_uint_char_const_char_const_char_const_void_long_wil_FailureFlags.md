# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1800028d4`
- end: `0x180002930`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003c70`

## callees

- `0x180002554`
- `0x180003d08`

## string_xrefs

- `0x1800028f3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v6; // rax
  __int64 v7; // xmm0_8
  int v8; // r9d
  int v9; // [rsp+20h] [rbp-58h]
  __int64 v10; // [rsp+50h] [rbp-28h] BYREF
  int v11; // [rsp+58h] [rbp-20h]
  _BYTE v12[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = wil::details::ResultStatus::FromResult(v12, 2147549183LL);
  v7 = *(_QWORD *)v6;
  v11 = *(_DWORD *)(v6 + 8);
  v10 = v7;
  wil::details::ReportFailure_Base<3,0>(
    v8,
    3585,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v8,
    v9,
    a6,
    (__int64)&v10,
    0);
}

```

## disassembly

```asm
0x1800028d4  sub     rsp, 78h
0x1800028d8  mov     r9, rcx
0x1800028db  mov     edx, 8000FFFFh
0x1800028e0  lea     rcx, [rsp+78h+var_18]
0x1800028e5  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800028ea  mov     [rsp+78h+var_40], 0
0x1800028f3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800028fa  mov     edx, 0E01h
0x1800028ff  mov     rcx, r9
0x180002902  movsd   xmm0, qword ptr [rax]
0x180002906  mov     eax, [rax+8]
0x180002909  mov     [rsp+78h+var_20], eax
0x18000290d  lea     rax, [rsp+78h+var_28]
0x180002912  mov     [rsp+78h+var_48], rax
0x180002917  mov     rax, [rsp+78h+arg_28]
0x18000291f  mov     [rsp+78h+var_50], rax
0x180002924  movsd   [rsp+78h+var_28], xmm0
0x18000292a  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
