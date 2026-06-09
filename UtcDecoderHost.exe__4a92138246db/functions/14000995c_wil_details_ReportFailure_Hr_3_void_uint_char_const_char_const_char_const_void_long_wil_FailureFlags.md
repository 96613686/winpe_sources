# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x14000995c`
- end: `0x1400099ba`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `94`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b194`
- `0x14000d8ec`
- `0x140016244`

## callees

- `0x1400095ec`
- `0x14000b238`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7)
{
  int v7; // r9d
  int v8; // r10d
  int v9; // r11d
  _BYTE v10[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v10, a7);
  wil::details::ReportFailure_Base<3,0>(v9, v8, v7, v7);
}

```

## disassembly

```asm
0x14000995c  sub     rsp, 78h
0x140009960  mov     r11, rcx
0x140009963  mov     r10d, edx
0x140009966  mov     edx, [rsp+78h+arg_30]
0x14000996d  lea     rcx, [rsp+78h+var_18]
0x140009972  mov     r9, r8
0x140009975  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000997a  mov     [rsp+78h+var_40], 0
0x140009983  mov     r8, r9
0x140009986  mov     edx, r10d
0x140009989  mov     rcx, r11
0x14000998c  movsd   xmm0, qword ptr [rax]
0x140009990  mov     eax, [rax+8]
0x140009993  mov     [rsp+78h+var_20], eax
0x140009997  lea     rax, [rsp+78h+var_28]
0x14000999c  mov     [rsp+78h+var_48], rax
0x1400099a1  mov     rax, [rsp+78h+arg_28]
0x1400099a9  mov     [rsp+78h+var_50], rax
0x1400099ae  movsd   [rsp+78h+var_28], xmm0
0x1400099b4  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
