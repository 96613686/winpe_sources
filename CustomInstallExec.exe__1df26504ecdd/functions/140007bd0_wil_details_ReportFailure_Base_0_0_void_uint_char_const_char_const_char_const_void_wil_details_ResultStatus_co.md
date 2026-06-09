# wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140007bd0`
- end: `0x140007c01`
- name: `??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `49`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140007c08`
- `0x140007f74`
- `0x14000804c`
- `0x1400080bc`

## callees

- `0x140007c6c`

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
0x140007bd0  sub     rsp, 58h
0x140007bd4  mov     rax, [rsp+58h+arg_38]
0x140007bdc  mov     [rsp+58h+var_20], rax
0x140007be1  mov     rax, [rsp+58h+arg_30]
0x140007be9  mov     [rsp+58h+var_28], rax
0x140007bee  mov     rax, [rsp+58h+arg_28]
0x140007bf6  mov     [rsp+58h+var_30], rax
0x140007bfb  call    ??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
