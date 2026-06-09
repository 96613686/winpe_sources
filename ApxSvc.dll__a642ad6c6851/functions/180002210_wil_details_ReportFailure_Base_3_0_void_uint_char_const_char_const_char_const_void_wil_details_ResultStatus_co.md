# wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002210`
- end: `0x180002234`
- name: `??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `36`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000223c`
- `0x180002410`

## callees

- `0x180002464`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<3,0>(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  wil::details::ReportFailure_NoReturn<3>(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180002210  sub     rsp, 58h
0x180002214  mov     rax, [rsp+58h+arg_30]
0x18000221c  mov     [rsp+58h+var_28], rax
0x180002221  mov     rax, [rsp+58h+arg_28]
0x180002229  mov     [rsp+58h+var_30], rax
0x18000222e  call    ??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
