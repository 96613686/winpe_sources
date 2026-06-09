# wil::details::ReportFailure_NtStatus<3>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x140015038`
- end: `0x140015098`
- name: `??$ReportFailure_NtStatus@$02@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `96`
- prototype: `void __fastcall __noreturn(int, __int64, __int64, __int64, int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001a950`

## callees

- `0x1400051b4`
- `0x140014f04`

## string_xrefs

- `0x14001505b`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NtStatus<3>(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7)
{
  int v8; // r9d
  _BYTE v9[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromStatus(v9, a7);
  wil::details::ReportFailure_Base<3,0>(a1, 7235, (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h", v8);
}

```

## disassembly

```asm
0x140015038  push    rbx
0x14001503a  sub     rsp, 70h
0x14001503e  mov     edx, [rsp+78h+arg_30]
0x140015045  mov     rbx, rcx
0x140015048  lea     rcx, [rsp+78h+var_18]
0x14001504d  call    ?FromStatus@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromStatus(long)
0x140015052  mov     [rsp+78h+var_40], 0
0x14001505b  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140015062  mov     edx, 1C43h
0x140015067  mov     rcx, rbx
0x14001506a  movsd   xmm0, qword ptr [rax]
0x14001506e  mov     eax, [rax+8]
0x140015071  mov     [rsp+78h+var_20], eax
0x140015075  lea     rax, [rsp+78h+var_28]
0x14001507a  mov     [rsp+78h+var_48], rax
0x14001507f  mov     rax, [rsp+78h+arg_28]
0x140015087  mov     [rsp+78h+var_50], rax
0x14001508c  movsd   [rsp+78h+var_28], xmm0
0x140015092  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
