# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180002658`
- end: `0x1800026ab`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e60`
- `0x180007898`

## callees

- `0x180002450`
- `0x180004168`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>()
{
  int v0; // r9d
  int v1; // r10d
  int v2; // r11d
  _BYTE v3[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v3, 2147549183LL);
  wil::details::ReportFailure_Base<3,0>(v2, v1, v0, v0);
}

```

## disassembly

```asm
0x180002658  sub     rsp, 78h
0x18000265c  mov     r11, rcx
0x18000265f  mov     r10d, edx
0x180002662  mov     edx, 8000FFFFh
0x180002667  lea     rcx, [rsp+78h+var_18]
0x18000266c  mov     r9, r8
0x18000266f  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180002674  mov     r8, r9
0x180002677  mov     edx, r10d
0x18000267a  mov     rcx, r11
0x18000267d  movsd   xmm0, qword ptr [rax]
0x180002681  mov     eax, [rax+8]
0x180002684  mov     [rsp+78h+var_20], eax
0x180002688  lea     rax, [rsp+78h+var_28]
0x18000268d  mov     [rsp+78h+var_48], rax
0x180002692  mov     rax, [rsp+78h+arg_28]
0x18000269a  mov     [rsp+78h+var_50], rax
0x18000269f  movsd   [rsp+78h+var_28], xmm0
0x1800026a5  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
