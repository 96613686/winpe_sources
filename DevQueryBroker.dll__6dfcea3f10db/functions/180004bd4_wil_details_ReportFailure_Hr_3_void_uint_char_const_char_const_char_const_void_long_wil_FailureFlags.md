# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180004bd4`
- end: `0x180004c27`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `83`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006544`
- `0x180009cc8`

## callees

- `0x1800049d4`
- `0x1800068b8`

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
  int v8; // r11d
  _BYTE v9[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v9, 2147549183LL);
  wil::details::ReportFailure_Base<3,0>(v8, v7, v6, v6);
}

```

## disassembly

```asm
0x180004bd4  sub     rsp, 78h
0x180004bd8  mov     r11, rcx
0x180004bdb  mov     r10d, edx
0x180004bde  mov     edx, 8000FFFFh
0x180004be3  lea     rcx, [rsp+78h+var_18]
0x180004be8  mov     r9, r8
0x180004beb  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180004bf0  mov     r8, r9
0x180004bf3  mov     edx, r10d
0x180004bf6  mov     rcx, r11
0x180004bf9  movsd   xmm0, qword ptr [rax]
0x180004bfd  mov     eax, [rax+8]
0x180004c00  mov     [rsp+78h+var_20], eax
0x180004c04  lea     rax, [rsp+78h+var_28]
0x180004c09  mov     [rsp+78h+var_48], rax
0x180004c0e  mov     rax, [rsp+78h+arg_28]
0x180004c16  mov     [rsp+78h+var_50], rax
0x180004c1b  movsd   [rsp+78h+var_28], xmm0
0x180004c21  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
