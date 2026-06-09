# wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002390`
- end: `0x1400023b4`
- name: `??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `36`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002758`
- `0x140009d64`
- `0x14000a870`

## callees

- `0x140002a34`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<0,0>(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  wil::details::ReportFailure_NoReturn<0>(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x140002390  sub     rsp, 58h
0x140002394  mov     rax, [rsp+58h+arg_30]
0x14000239c  mov     [rsp+58h+var_28], rax
0x1400023a1  mov     rax, [rsp+58h+arg_28]
0x1400023a9  mov     [rsp+58h+var_30], rax
0x1400023ae  call    ??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
