# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x140002258`
- end: `0x1400022ad`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `85`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002cf0`
- `0x140004a2c`
- `0x1400050b8`
- `0x1400050e4`

## callees

- `0x140002094`
- `0x140002da8`

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
  __int64 v7; // rax
  __int64 v8; // xmm0_8
  int v9; // r9d
  int v10; // r10d
  int v11; // r11d
  int v12; // [rsp+20h] [rbp-58h]
  __int64 v13; // [rsp+50h] [rbp-28h] BYREF
  int v14; // [rsp+58h] [rbp-20h]
  _BYTE v15[24]; // [rsp+60h] [rbp-18h] BYREF

  v7 = wil::details::ResultStatus::FromResult(v15, a7, a3, a3);
  v8 = *(_QWORD *)v7;
  v14 = *(_DWORD *)(v7 + 8);
  v13 = v8;
  wil::details::ReportFailure_Base<3,0>(v11, v10, v9, v9, v12, a6, (__int64)&v13);
}

```

## disassembly

```asm
0x140002258  sub     rsp, 78h
0x14000225c  mov     r11, rcx
0x14000225f  mov     r10d, edx
0x140002262  mov     edx, [rsp+78h+arg_30]
0x140002269  lea     rcx, [rsp+78h+var_18]
0x14000226e  mov     r9, r8
0x140002271  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x140002276  mov     r8, r9
0x140002279  mov     edx, r10d
0x14000227c  mov     rcx, r11
0x14000227f  movsd   xmm0, qword ptr [rax]
0x140002283  mov     eax, [rax+8]
0x140002286  mov     [rsp+78h+var_20], eax
0x14000228a  lea     rax, [rsp+78h+var_28]
0x14000228f  mov     [rsp+78h+var_48], rax
0x140002294  mov     rax, [rsp+78h+arg_28]
0x14000229c  mov     [rsp+78h+var_50], rax
0x1400022a1  movsd   [rsp+78h+var_28], xmm0
0x1400022a7  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
