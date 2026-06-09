# wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002a64`
- end: `0x180002a95`
- name: `??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `49`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a9c`
- `0x180002c84`
- `0x1800064bc`
- `0x1800065e8`

## callees

- `0x180002ce4`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<3,0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v8; // [rsp+20h] [rbp-38h]

  wil::details::ReportFailure_NoReturn<3>(a1, a2, a3, a4, v8, a6, a7, a8);
}

```

## disassembly

```asm
0x180002a64  sub     rsp, 58h
0x180002a68  mov     rax, [rsp+58h+arg_38]
0x180002a70  mov     [rsp+58h+var_20], rax
0x180002a75  mov     rax, [rsp+58h+arg_30]
0x180002a7d  mov     [rsp+58h+var_28], rax
0x180002a82  mov     rax, [rsp+58h+arg_28]
0x180002a8a  mov     [rsp+58h+var_30], rax
0x180002a8f  call    ??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
