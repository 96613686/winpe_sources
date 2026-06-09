# wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x140002364`
- end: `0x1400023b8`
- name: `??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `84`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, wil::details *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400063f0`
- `0x1400080f4`

## callees

- `0x140002004`
- `0x1400057fc`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Hr<1>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        wil::details *a7)
{
  int v7; // edx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // r10
  int v11[6]; // [rsp+50h] [rbp-18h] BYREF

  v11[0] = (int)a7;
  v11[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)a7);
  v11[2] = 0;
  wil::details::ReportFailure_Base<1,0>(v10, v7, v8, v9, a5, a6, v11);
}

```

## disassembly

```asm
0x140002364  sub     rsp, 68h
0x140002368  mov     r10, rcx
0x14000236b  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x140002372  mov     [rsp+68h+var_18], ecx
0x140002376  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000237b  mov     [rsp+68h+var_14], eax
0x14000237f  mov     rcx, r10
0x140002382  lea     rax, [rsp+68h+var_18]
0x140002387  mov     [rsp+68h+var_10], 0
0x14000238f  mov     [rsp+68h+var_38], rax
0x140002394  mov     rax, [rsp+68h+arg_28]
0x14000239c  mov     [rsp+68h+var_40], rax
0x1400023a1  mov     rax, [rsp+68h+arg_20]
0x1400023a9  mov     [rsp+68h+var_48], rax
0x1400023ae  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1400023b3  add     rsp, 68h
0x1400023b7  retn
```
