# wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180010cdc`
- end: `0x180010d41`
- name: `??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `101`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180014d84`

## callees

- `0x180004650`
- `0x180005a44`
- `0x180010cdc`

## string_xrefs

- `0x180010d04`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
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
    223,
    (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
    v8);
}

```

## disassembly

```asm
0x180010cdc  sub     rsp, 68h
0x180010ce0  mov     r9, rcx
0x180010ce3  mov     ecx, [rsp+68h+arg_30]
0x180010cea  test    ecx, ecx
0x180010cec  jle     short loc_180010CF7
0x180010cee  movzx   ecx, cx
0x180010cf1  or      ecx, 80070000h; this
0x180010cf7  mov     [rsp+68h+var_18], ecx
0x180010cfb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010d00  mov     [rsp+68h+var_14], eax
0x180010d04  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180010d0b  lea     rax, [rsp+68h+var_18]
0x180010d10  mov     [rsp+68h+var_30], 0
0x180010d19  mov     [rsp+68h+var_38], rax
0x180010d1e  mov     edx, 0DFh
0x180010d23  mov     rax, [rsp+68h+arg_28]
0x180010d2b  mov     rcx, r9
0x180010d2e  mov     [rsp+68h+var_40], rax
0x180010d33  mov     [rsp+68h+var_10], 0
0x180010d3b  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
