# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x18000234c`
- end: `0x1800023a8`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002244`
- `0x180003ac0`
- `0x180003b28`
- `0x180004168`
- `0x18000a0a0`

## callees

- `0x180002148`
- `0x180003fa4`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        wil::details *a7)
{
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  int v10; // r10d
  _DWORD v12[6]; // [rsp+50h] [rbp-18h] BYREF

  v12[0] = (_DWORD)a7;
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12);
}

```

## disassembly

```asm
0x18000234c  sub     rsp, 68h
0x180002350  mov     r10, rcx
0x180002353  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x18000235a  mov     [rsp+68h+var_18], ecx
0x18000235e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002363  mov     [rsp+68h+var_14], eax
0x180002367  mov     rcx, r10
0x18000236a  mov     [rsp+68h+var_20], 0
0x180002372  lea     rax, [rsp+68h+var_18]
0x180002377  mov     [rsp+68h+var_38], rax
0x18000237c  mov     rax, [rsp+68h+arg_28]
0x180002384  mov     [rsp+68h+var_40], rax
0x180002389  mov     rax, [rsp+68h+arg_20]
0x180002391  mov     [rsp+68h+var_48], rax
0x180002396  mov     [rsp+68h+var_10], 0
0x18000239e  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800023a3  add     rsp, 68h
0x1800023a7  retn
```
