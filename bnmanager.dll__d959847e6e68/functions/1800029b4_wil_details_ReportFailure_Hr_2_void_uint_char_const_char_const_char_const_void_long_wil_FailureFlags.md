# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x1800029b4`
- end: `0x180002a10`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800028c4`
- `0x180008110`
- `0x180008178`
- `0x1800088d8`

## callees

- `0x1800027c8`
- `0x1800086c0`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<2>(
        __int64 a1,
        int a2,
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
  v12[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7, a2);
  v12[2] = 0;
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12);
}

```

## disassembly

```asm
0x1800029b4  sub     rsp, 68h
0x1800029b8  mov     r10, rcx
0x1800029bb  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x1800029c2  mov     [rsp+68h+var_18], ecx
0x1800029c6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800029cb  mov     [rsp+68h+var_14], eax
0x1800029cf  mov     rcx, r10
0x1800029d2  mov     [rsp+68h+var_20], 0
0x1800029da  lea     rax, [rsp+68h+var_18]
0x1800029df  mov     [rsp+68h+var_38], rax
0x1800029e4  mov     rax, [rsp+68h+arg_28]
0x1800029ec  mov     [rsp+68h+var_40], rax
0x1800029f1  mov     rax, [rsp+68h+arg_20]
0x1800029f9  mov     [rsp+68h+var_48], rax
0x1800029fe  mov     [rsp+68h+var_10], 0
0x180002a06  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180002a0b  add     rsp, 68h
0x180002a0f  retn
```
