# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1800032b4`
- end: `0x180003311`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `93`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e44`
- `0x18000952c`

## callees

- `0x180002f34`
- `0x180004ee8`

## string_xrefs

- `0x1800032d6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // r10d
  int v10; // [rsp+20h] [rbp-58h]
  __int64 v11; // [rsp+50h] [rbp-28h] BYREF
  int v12; // [rsp+58h] [rbp-20h]
  _BYTE v13[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = wil::details::ResultStatus::FromResult(v13, 2147549183LL);
  v7 = *(_QWORD *)v6;
  v12 = *(_DWORD *)(v6 + 8);
  v11 = v7;
  wil::details::ReportFailure_Base<3,0>(
    v9,
    v8,
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v8,
    v10,
    a6,
    (__int64)&v11,
    0);
}

```

## disassembly

```asm
0x1800032b4  sub     rsp, 78h
0x1800032b8  mov     r10, rcx
0x1800032bb  mov     r9d, edx
0x1800032be  mov     edx, 8000FFFFh
0x1800032c3  lea     rcx, [rsp+78h+var_18]
0x1800032c8  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800032cd  mov     [rsp+78h+var_40], 0
0x1800032d6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800032dd  mov     edx, r9d
0x1800032e0  mov     rcx, r10
0x1800032e3  movsd   xmm0, qword ptr [rax]
0x1800032e7  mov     eax, [rax+8]
0x1800032ea  mov     [rsp+78h+var_20], eax
0x1800032ee  lea     rax, [rsp+78h+var_28]
0x1800032f3  mov     [rsp+78h+var_48], rax
0x1800032f8  mov     rax, [rsp+78h+arg_28]
0x180003300  mov     [rsp+78h+var_50], rax
0x180003305  movsd   [rsp+78h+var_28], xmm0
0x18000330b  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
