# wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800022bc`
- end: `0x1800022ed`
- name: `??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000237c`
- `0x180002470`
- `0x180002634`

## callees

- `0x180002698`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<3,0>(int a1, int a2, int a3, int a4)
{
  wil::details::ReportFailure_NoReturn<3>(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800022bc  sub     rsp, 58h
0x1800022c0  mov     rax, [rsp+58h+arg_38]
0x1800022c8  mov     [rsp+58h+var_20], rax
0x1800022cd  mov     rax, [rsp+58h+arg_30]
0x1800022d5  mov     [rsp+58h+var_28], rax
0x1800022da  mov     rax, [rsp+58h+arg_28]
0x1800022e2  mov     [rsp+58h+var_30], rax
0x1800022e7  call    ??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
