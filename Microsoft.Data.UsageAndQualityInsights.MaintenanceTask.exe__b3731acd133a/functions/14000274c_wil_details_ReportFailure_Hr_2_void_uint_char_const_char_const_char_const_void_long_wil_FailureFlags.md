# wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x14000274c`
- end: `0x1400027a8`
- name: `??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `92`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, __int64, __int64, wil::details *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000265c`
- `0x140004fd0`
- `0x140005038`
- `0x14000575c`

## callees

- `0x140002560`
- `0x1400054b0`

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
0x14000274c  sub     rsp, 68h
0x140002750  mov     r10, rcx
0x140002753  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x14000275a  mov     [rsp+68h+var_18], ecx
0x14000275e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002763  mov     [rsp+68h+var_14], eax
0x140002767  mov     rcx, r10
0x14000276a  mov     [rsp+68h+var_20], 0
0x140002772  lea     rax, [rsp+68h+var_18]
0x140002777  mov     [rsp+68h+var_38], rax
0x14000277c  mov     rax, [rsp+68h+arg_28]
0x140002784  mov     [rsp+68h+var_40], rax
0x140002789  mov     rax, [rsp+68h+arg_20]
0x140002791  mov     [rsp+68h+var_48], rax
0x140002796  mov     [rsp+68h+var_10], 0
0x14000279e  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1400027a3  add     rsp, 68h
0x1400027a7  retn
```
