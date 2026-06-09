# wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800043d8`
- end: `0x180004409`
- name: `??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `49`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800044d4`
- `0x1800045c8`
- `0x180004704`
- `0x18000c588`

## callees

- `0x1800047c0`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<3,0>(int a1, int a2, int a3, int a4)
{
  wil::details::ReportFailure_NoReturn<3>(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x1800043d8  sub     rsp, 58h
0x1800043dc  mov     rax, [rsp+58h+arg_38]
0x1800043e4  mov     [rsp+58h+var_20], rax
0x1800043e9  mov     rax, [rsp+58h+arg_30]
0x1800043f1  mov     [rsp+58h+var_28], rax
0x1800043f6  mov     rax, [rsp+58h+arg_28]
0x1800043fe  mov     [rsp+58h+var_30], rax
0x180004403  call    ??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
