# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1800042d0`
- end: `0x18000432d`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `93`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006794`

## callees

- `0x180003c90`
- `0x180006838`

## string_xrefs

- `0x1800042f2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v6; // rax
  __int64 v7; // xmm0_8
  int v8; // r9d
  int v9; // r10d
  int v10; // [rsp+20h] [rbp-58h]
  __int64 v11; // [rsp+50h] [rbp-28h] BYREF
  int v12; // [rsp+58h] [rbp-20h]
  _BYTE v13[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = wil::details::ResultStatus::FromResult(v13, 2147549183LL, a3, a2);
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
0x1800042d0  sub     rsp, 78h
0x1800042d4  mov     r10, rcx
0x1800042d7  mov     r9d, edx
0x1800042da  mov     edx, 8000FFFFh
0x1800042df  lea     rcx, [rsp+78h+var_18]
0x1800042e4  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1800042e9  mov     [rsp+78h+var_40], 0
0x1800042f2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800042f9  mov     edx, r9d
0x1800042fc  mov     rcx, r10
0x1800042ff  movsd   xmm0, qword ptr [rax]
0x180004303  mov     eax, [rax+8]
0x180004306  mov     [rsp+78h+var_20], eax
0x18000430a  lea     rax, [rsp+78h+var_28]
0x18000430f  mov     [rsp+78h+var_48], rax
0x180004314  mov     rax, [rsp+78h+arg_28]
0x18000431c  mov     [rsp+78h+var_50], rax
0x180004321  movsd   [rsp+78h+var_28], xmm0
0x180004327  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
