# wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180001cc0`
- end: `0x180001d07`
- name: `??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `71`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002c40`

## callees

- `0x180001c88`
- `0x1800028ac`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Hr<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  __int64 v7; // r8

  wil::details::HrToNtStatus((wil::details *)(unsigned int)a7, a2);
  return wil::details::ReportFailure_Base<1,0>(v7);
}

```

## disassembly

```asm
0x180001cc0  sub     rsp, 68h
0x180001cc4  mov     r8, rcx
0x180001cc7  mov     ecx, dword ptr [rsp+68h+arg_30]; this
0x180001cce  mov     [rsp+68h+var_18], ecx
0x180001cd2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180001cd7  mov     [rsp+68h+var_14], eax
0x180001cdb  mov     rcx, r8
0x180001cde  lea     rax, [rsp+68h+var_18]
0x180001ce3  mov     [rsp+68h+var_10], 0
0x180001ceb  mov     [rsp+68h+var_38], rax
0x180001cf0  mov     rax, [rsp+68h+arg_28]
0x180001cf8  mov     [rsp+68h+var_40], rax
0x180001cfd  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180001d02  add     rsp, 68h
0x180001d06  retn
```
