# wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180027834`
- end: `0x180027889`
- name: `??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a3a0`

## callees

- `0x180007dfc`
- `0x18000beb8`

## string_xrefs

- `0x18002784c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7)
{
  int v7; // r9d
  _BYTE v8[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v8, a7);
  wil::details::ReportFailure_Base<0,0>(
    v7,
    5331,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v7);
}

```

## disassembly

```asm
0x180027834  sub     rsp, 78h
0x180027838  mov     edx, [rsp+78h+arg_30]
0x18002783f  mov     r9, rcx
0x180027842  lea     rcx, [rsp+78h+var_18]
0x180027847  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18002784c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180027853  mov     edx, 14D3h
0x180027858  mov     rcx, r9
0x18002785b  movsd   xmm0, qword ptr [rax]
0x18002785f  mov     eax, [rax+8]
0x180027862  mov     [rsp+78h+var_20], eax
0x180027866  lea     rax, [rsp+78h+var_28]
0x18002786b  mov     [rsp+78h+var_48], rax
0x180027870  mov     rax, [rsp+78h+arg_28]
0x180027878  mov     [rsp+78h+var_50], rax
0x18002787d  movsd   [rsp+78h+var_28], xmm0
0x180027883  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
