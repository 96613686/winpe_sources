# wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002064`
- end: `0x1400020a1`
- name: `??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400020a8`
- `0x14000220c`
- `0x140002424`

## callees

- `0x14000249c`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Base<3,0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  wil::details::ReportFailure_NoReturn<3>(a1, a2, a3, a4, a5, a6, a7, a8);
}

```

## disassembly

```asm
0x140002064  mov     r11, rsp
0x140002067  sub     rsp, 58h
0x14000206b  mov     rax, [rsp+58h+arg_38]
0x140002073  mov     [r11-20h], rax
0x140002077  mov     rax, [rsp+58h+arg_30]
0x14000207f  mov     [r11-28h], rax
0x140002083  mov     rax, [rsp+58h+arg_28]
0x14000208b  mov     [r11-30h], rax
0x14000208f  mov     rax, [rsp+58h+arg_20]
0x140002097  mov     [r11-38h], rax
0x14000209b  call    ??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
