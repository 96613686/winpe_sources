# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180001d10`
- end: `0x180001d57`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `71`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039dc`

## callees

- `0x180001c94`
- `0x180002448`

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
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  int v11; // [rsp+20h] [rbp-58h]
  __int64 v12; // [rsp+50h] [rbp-28h] BYREF
  int v13; // [rsp+58h] [rbp-20h]
  _BYTE v14[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = wil::details::ResultStatus::FromResult(v14, 2147549183LL, a3, a1);
  v7 = *(_QWORD *)v6;
  v13 = *(_DWORD *)(v6 + 8);
  v12 = v7;
  wil::details::ReportFailure_Base<3,0>(v10, v8, v9, v10, v11, a6, (__int64)&v12);
}

```

## disassembly

```asm
0x180001d10  sub     rsp, 78h
0x180001d14  mov     r9, rcx
0x180001d17  mov     edx, 8000FFFFh
0x180001d1c  lea     rcx, [rsp+78h+var_18]
0x180001d21  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180001d26  mov     rcx, r9
0x180001d29  movsd   xmm0, qword ptr [rax]
0x180001d2d  mov     eax, [rax+8]
0x180001d30  mov     [rsp+78h+var_20], eax
0x180001d34  lea     rax, [rsp+78h+var_28]
0x180001d39  mov     [rsp+78h+var_48], rax
0x180001d3e  mov     rax, [rsp+78h+arg_28]
0x180001d46  mov     [rsp+78h+var_50], rax
0x180001d4b  movsd   [rsp+78h+var_28], xmm0
0x180001d51  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
