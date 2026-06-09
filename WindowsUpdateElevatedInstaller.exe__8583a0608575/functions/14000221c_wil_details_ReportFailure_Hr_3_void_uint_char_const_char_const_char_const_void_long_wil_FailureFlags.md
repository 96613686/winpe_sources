# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x14000221c`
- end: `0x140002271`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `85`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003340`
- `0x140005da8`

## callees

- `0x140002004`
- `0x1400033e8`

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

  v7 = wil::details::ResultStatus::FromResult(v15, a7);
  v8 = *(_QWORD *)v7;
  v14 = *(_DWORD *)(v7 + 8);
  v13 = v8;
  wil::details::ReportFailure_Base<3,0>(v11, v10, v9, v9, v12, a6, (__int64)&v13);
}

```

## disassembly

```asm
0x14000221c  sub     rsp, 78h
0x140002220  mov     r11, rcx
0x140002223  mov     r10d, edx
0x140002226  mov     edx, [rsp+78h+arg_30]
0x14000222d  lea     rcx, [rsp+78h+var_18]
0x140002232  mov     r9, r8
0x140002235  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000223a  mov     r8, r9
0x14000223d  mov     edx, r10d
0x140002240  mov     rcx, r11
0x140002243  movsd   xmm0, qword ptr [rax]
0x140002247  mov     eax, [rax+8]
0x14000224a  mov     [rsp+78h+var_20], eax
0x14000224e  lea     rax, [rsp+78h+var_28]
0x140002253  mov     [rsp+78h+var_48], rax
0x140002258  mov     rax, [rsp+78h+arg_28]
0x140002260  mov     [rsp+78h+var_50], rax
0x140002265  movsd   [rsp+78h+var_28], xmm0
0x14000226b  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
