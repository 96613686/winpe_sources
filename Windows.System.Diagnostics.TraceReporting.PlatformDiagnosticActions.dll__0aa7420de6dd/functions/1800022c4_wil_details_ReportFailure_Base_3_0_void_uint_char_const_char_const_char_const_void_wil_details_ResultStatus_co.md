# wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800022c4`
- end: `0x1800022f5`
- name: `??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `49`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022fc`
- `0x1800024f0`
- `0x180006b50`

## callees

- `0x180002554`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<3,0>(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  wil::details::ReportFailure_NoReturn<3>(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800022c4  sub     rsp, 58h
0x1800022c8  mov     rax, [rsp+58h+arg_38]
0x1800022d0  mov     [rsp+58h+var_20], rax
0x1800022d5  mov     rax, [rsp+58h+arg_30]
0x1800022dd  mov     [rsp+58h+var_28], rax
0x1800022e2  mov     rax, [rsp+58h+arg_28]
0x1800022ea  mov     [rsp+58h+var_30], rax
0x1800022ef  call    ??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
