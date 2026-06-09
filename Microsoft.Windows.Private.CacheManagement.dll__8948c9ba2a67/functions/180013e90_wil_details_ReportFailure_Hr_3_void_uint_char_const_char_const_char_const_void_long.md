# wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x180013e90`
- end: `0x180013eec`
- name: `??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110J@Z`
- size: `92`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013fd0`

## callees

- `0x1800035f0`
- `0x180012da0`

## string_xrefs

- `0x180013eaf`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.2.142\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  int v6; // r9d
  int v7; // r10d
  _BYTE v8[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v8, 2147549183LL);
  wil::details::ReportFailure_Base<3,0>(
    v7,
    3111,
    (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.2.142\\inc\\wil\\opensource\\wil\\resource.h",
    v6);
}

```

## disassembly

```asm
0x180013e90  sub     rsp, 78h
0x180013e94  mov     r10, rcx
0x180013e97  mov     edx, 8000FFFFh
0x180013e9c  lea     rcx, [rsp+78h+var_18]
0x180013ea1  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180013ea6  mov     [rsp+78h+var_40], 0
0x180013eaf  lea     r8, aCW1SPackagesMi; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180013eb6  mov     edx, 0C27h
0x180013ebb  mov     rcx, r10
0x180013ebe  movsd   xmm0, qword ptr [rax]
0x180013ec2  mov     eax, [rax+8]
0x180013ec5  mov     [rsp+78h+var_20], eax
0x180013ec9  lea     rax, [rsp+78h+var_28]
0x180013ece  mov     [rsp+78h+var_48], rax
0x180013ed3  mov     rax, [rsp+78h+arg_28]
0x180013edb  mov     [rsp+78h+var_50], rax
0x180013ee0  movsd   [rsp+78h+var_28], xmm0
0x180013ee6  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)
```
