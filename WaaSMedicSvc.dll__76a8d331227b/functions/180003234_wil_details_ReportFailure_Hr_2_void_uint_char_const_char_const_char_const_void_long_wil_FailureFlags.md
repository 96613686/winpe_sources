# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180003234`
- end: `0x18000328f`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000312c`
- `0x1800049d0`
- `0x180004a38`
- `0x180005080`

## callees

- `0x180003018`
- `0x180004ebc`

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
  return wil::details::ReportFailure_Base<2,0>(v10, v7, v8, v9, a5, a6, (__int64)v12, 0);
}

```

## disassembly

```asm
0x180003234  sub     rsp, 68h
0x180003238  mov     r10, rcx
0x18000323b  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180003242  mov     [rsp+68h+var_18], ecx
0x180003246  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000324b  mov     [rsp+68h+var_14], eax
0x18000324f  mov     rcx, r10
0x180003252  xor     eax, eax
0x180003254  mov     [rsp+68h+var_20], eax
0x180003258  mov     [rsp+68h+var_30], rax
0x18000325d  mov     [rsp+68h+var_10], eax
0x180003261  lea     rax, [rsp+68h+var_18]
0x180003266  mov     [rsp+68h+var_38], rax
0x18000326b  mov     rax, [rsp+68h+arg_28]
0x180003273  mov     [rsp+68h+var_40], rax
0x180003278  mov     rax, [rsp+68h+arg_20]
0x180003280  mov     [rsp+68h+var_48], rax
0x180003285  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000328a  add     rsp, 68h
0x18000328e  retn
```
