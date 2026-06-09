# wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002010`
- end: `0x14000205c`
- name: `??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400020a8`
- `0x1400023c0`

## callees

- `0x140002a48`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Base<2,0>(
        int a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  return wil::details::ReportFailure_Return<2>(a1, a2, a3, a4, a5, a6, a7, a8);
}

```

## disassembly

```asm
0x140002010  mov     r11, rsp
0x140002013  sub     rsp, 58h
0x140002017  mov     eax, [rsp+58h+arg_48]
0x14000201e  mov     [rsp+58h+var_10], eax
0x140002022  mov     rax, [rsp+58h+arg_38]
0x14000202a  mov     [r11-20h], rax
0x14000202e  mov     rax, [rsp+58h+arg_30]
0x140002036  mov     [r11-28h], rax
0x14000203a  mov     rax, [rsp+58h+arg_28]
0x140002042  mov     [r11-30h], rax
0x140002046  mov     rax, [rsp+58h+arg_20]
0x14000204e  mov     [r11-38h], rax
0x140002052  call    ??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140002057  add     rsp, 58h
0x14000205b  retn
```
