# wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000cc94`
- end: `0x18000ccf0`
- name: `??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `92`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180017dc0`

## callees

- `0x18000740c`
- `0x18000c970`
- `0x18000cc94`

## string_xrefs

- `0x18000ccbc`: `onecoreuap\windows\dwm\capture\svc\dll\CaptureTraceLogging.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_Win32<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7)
{
  unsigned __int64 v7; // rcx
  int v8; // r9d

  v7 = (unsigned int)a7;
  if ( a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)v7, a2);
  wil::details::ReportFailure_Base<0,0>(
    v8,
    114,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\CaptureTraceLogging.h",
    v8);
}

```

## disassembly

```asm
0x18000cc94  sub     rsp, 68h
0x18000cc98  mov     r9, rcx
0x18000cc9b  mov     ecx, [rsp+68h+arg_30]
0x18000cca2  test    ecx, ecx
0x18000cca4  jle     short loc_18000CCAF
0x18000cca6  movzx   ecx, cx
0x18000cca9  or      ecx, 80070000h; this
0x18000ccaf  mov     [rsp+68h+var_18], ecx
0x18000ccb3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ccb8  mov     [rsp+68h+var_14], eax
0x18000ccbc  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18000ccc3  lea     rax, [rsp+68h+var_18]
0x18000ccc8  mov     [rsp+68h+var_10], 0
0x18000ccd0  mov     [rsp+68h+var_38], rax
0x18000ccd5  mov     edx, 72h ; 'r'
0x18000ccda  mov     rax, [rsp+68h+arg_28]
0x18000cce2  mov     rcx, r9
0x18000cce5  mov     [rsp+68h+var_40], rax
0x18000ccea  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
