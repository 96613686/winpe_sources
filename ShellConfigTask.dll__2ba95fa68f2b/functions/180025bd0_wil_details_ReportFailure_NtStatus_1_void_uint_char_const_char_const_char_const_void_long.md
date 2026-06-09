# wil::details::ReportFailure_NtStatus<1>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x180025bd0`
- end: `0x180025c48`
- name: `??$ReportFailure_NtStatus@$00@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `120`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002b840`

## callees

- `0x180003fbc`
- `0x1800086c4`

## string_xrefs

- `0x180025bf8`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v9; // [rsp+50h] [rbp-18h]

  v9 = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  wil::details::ReportFailure_Base<1,0>(
    a1,
    122,
    "pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h");
  return v9;
}

```

## disassembly

```asm
0x180025bd0  mov     [rsp+arg_0], rbx
0x180025bd5  mov     [rsp+arg_8], rsi
0x180025bda  push    rdi
0x180025bdb  sub     rsp, 60h
0x180025bdf  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180025be6  mov     rsi, rcx
0x180025be9  mov     ecx, ebx; this
0x180025beb  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180025bf0  mov     rdx, [rsp+68h+arg_28]
0x180025bf8  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180025bff  mov     edi, eax
0x180025c01  mov     [rsp+68h+var_18], eax
0x180025c05  lea     rax, [rsp+68h+var_18]
0x180025c0a  mov     [rsp+68h+var_30], 0
0x180025c13  mov     [rsp+68h+var_38], rax
0x180025c18  mov     rcx, rsi
0x180025c1b  mov     [rsp+68h+var_40], rdx
0x180025c20  mov     edx, 7Ah ; 'z'
0x180025c25  mov     [rsp+68h+var_14], ebx
0x180025c29  mov     [rsp+68h+var_10], 1
0x180025c31  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180025c36  mov     rbx, [rsp+68h+arg_0]
0x180025c3b  mov     eax, edi
0x180025c3d  mov     rsi, [rsp+68h+arg_8]
0x180025c42  add     rsp, 60h
0x180025c46  pop     rdi
0x180025c47  retn
```
