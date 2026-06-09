# wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000703c`
- end: `0x18000706d`
- name: `??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `49`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007334`
- `0x180007438`
- `0x18000749c`

## callees

- `0x18000750c`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<0,0>(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  wil::details::ReportFailure_NoReturn<0>(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000703c  sub     rsp, 58h
0x180007040  mov     rax, [rsp+58h+arg_38]
0x180007048  mov     [rsp+58h+var_20], rax
0x18000704d  mov     rax, [rsp+58h+arg_30]
0x180007055  mov     [rsp+58h+var_28], rax
0x18000705a  mov     rax, [rsp+58h+arg_28]
0x180007062  mov     [rsp+58h+var_30], rax
0x180007067  call    ??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
