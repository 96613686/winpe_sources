# wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180026804`
- end: `0x180026863`
- name: `??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `95`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026fbc`

## callees

- `0x180006a68`
- `0x180015dac`

## string_xrefs

- `0x180026828`: `onecore\windows\directx\dxg\common\etwtracesession\tracesession.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<0>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7)
{
  int v7; // r9d
  int v8; // r10d
  _BYTE v9[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v9, a7, a3, a2);
  wil::details::ReportFailure_Base<0,0>(
    v8,
    v7,
    (unsigned int)"onecore\\windows\\directx\\dxg\\common\\etwtracesession\\tracesession.cpp",
    v7);
}

```

## disassembly

```asm
0x180026804  sub     rsp, 78h
0x180026808  mov     r10, rcx
0x18002680b  mov     r9d, edx
0x18002680e  mov     edx, [rsp+78h+arg_30]
0x180026815  lea     rcx, [rsp+78h+var_18]
0x18002681a  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x18002681f  mov     [rsp+78h+var_40], 0
0x180026828  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\dxg\\common"...
0x18002682f  mov     edx, r9d
0x180026832  mov     rcx, r10
0x180026835  movsd   xmm0, qword ptr [rax]
0x180026839  mov     eax, [rax+8]
0x18002683c  mov     [rsp+78h+var_20], eax
0x180026840  lea     rax, [rsp+78h+var_28]
0x180026845  mov     [rsp+78h+var_48], rax
0x18002684a  mov     rax, [rsp+78h+arg_28]
0x180026852  mov     [rsp+78h+var_50], rax
0x180026857  movsd   [rsp+78h+var_28], xmm0
0x18002685d  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
