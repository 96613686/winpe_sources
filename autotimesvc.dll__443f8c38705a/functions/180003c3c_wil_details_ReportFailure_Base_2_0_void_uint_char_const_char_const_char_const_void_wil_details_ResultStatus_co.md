# wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003c3c`
- end: `0x180003c88`
- name: `??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `76`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f08`
- `0x180004008`
- `0x180004268`
- `0x180004990`
- `0x18000c154`

## callees

- `0x18000488c`

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
0x180003c3c  mov     r11, rsp
0x180003c3f  sub     rsp, 58h
0x180003c43  mov     eax, [rsp+58h+arg_48]
0x180003c4a  mov     [rsp+58h+var_10], eax
0x180003c4e  mov     rax, [rsp+58h+arg_38]
0x180003c56  mov     [r11-20h], rax
0x180003c5a  mov     rax, [rsp+58h+arg_30]
0x180003c62  mov     [r11-28h], rax
0x180003c66  mov     rax, [rsp+58h+arg_28]
0x180003c6e  mov     [r11-30h], rax
0x180003c72  mov     rax, [rsp+58h+arg_20]
0x180003c7a  mov     [r11-38h], rax
0x180003c7e  call    ??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180003c83  add     rsp, 58h
0x180003c87  retn
```
