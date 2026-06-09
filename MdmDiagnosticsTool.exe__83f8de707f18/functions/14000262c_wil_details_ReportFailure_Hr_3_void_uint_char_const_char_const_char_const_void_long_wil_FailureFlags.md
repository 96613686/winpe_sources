# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x14000262c`
- end: `0x140002681`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `85`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140004258`
- `0x1400073b8`
- `0x1400073e4`

## callees

- `0x14000242c`
- `0x140004328`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7)
{
  int v7; // r9d
  int v8; // r10d
  int v9; // r11d
  _BYTE v10[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v10, a7, a3, a3);
  wil::details::ReportFailure_Base<3,0>(v9, v8, v7, v7);
}

```

## disassembly

```asm
0x14000262c  sub     rsp, 78h
0x140002630  mov     r11, rcx
0x140002633  mov     r10d, edx
0x140002636  mov     edx, [rsp+78h+arg_30]
0x14000263d  lea     rcx, [rsp+78h+var_18]
0x140002642  mov     r9, r8
0x140002645  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000264a  mov     r8, r9
0x14000264d  mov     edx, r10d
0x140002650  mov     rcx, r11
0x140002653  movsd   xmm0, qword ptr [rax]
0x140002657  mov     eax, [rax+8]
0x14000265a  mov     [rsp+78h+var_20], eax
0x14000265e  lea     rax, [rsp+78h+var_28]
0x140002663  mov     [rsp+78h+var_48], rax
0x140002668  mov     rax, [rsp+78h+arg_28]
0x140002670  mov     [rsp+78h+var_50], rax
0x140002675  movsd   [rsp+78h+var_28], xmm0
0x14000267b  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
