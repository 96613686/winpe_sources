# wil::details::ReportFailure_NtStatus<2>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x180025c50`
- end: `0x180025cd2`
- name: `??$ReportFailure_NtStatus@$01@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `130`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002a788`

## callees

- `0x180003fc8`
- `0x1800086c4`

## string_xrefs

- `0x180025c78`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_NtStatus<2>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v8; // edi
  _DWORD v10[6]; // [rsp+50h] [rbp-18h] BYREF

  v10[0] = wil::details::NtStatusToHr((wil::details *)(unsigned int)a7, a2);
  v8 = v10[0];
  v10[1] = (_DWORD)a7;
  v10[2] = 1;
  wil::details::ReportFailure_Base<2,0>(
    a1,
    211,
    (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
    0,
    0,
    a6,
    (__int64)v10,
    0);
  return v8;
}

```

## disassembly

```asm
0x180025c50  mov     [rsp+arg_0], rbx
0x180025c55  mov     [rsp+arg_8], rsi
0x180025c5a  push    rdi
0x180025c5b  sub     rsp, 60h
0x180025c5f  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180025c66  mov     rsi, rcx
0x180025c69  mov     ecx, ebx; this
0x180025c6b  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180025c70  mov     rdx, [rsp+68h+arg_28]
0x180025c78  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180025c7f  xor     ecx, ecx
0x180025c81  mov     [rsp+68h+var_18], eax
0x180025c85  mov     [rsp+68h+var_20], ecx
0x180025c89  mov     edi, eax
0x180025c8b  mov     [rsp+68h+var_30], rcx
0x180025c90  lea     rax, [rsp+68h+var_18]
0x180025c95  mov     [rsp+68h+var_38], rax
0x180025c9a  xor     r9d, r9d
0x180025c9d  mov     [rsp+68h+var_40], rdx
0x180025ca2  mov     edx, 0D3h
0x180025ca7  mov     [rsp+68h+var_48], rcx
0x180025cac  mov     rcx, rsi
0x180025caf  mov     [rsp+68h+var_14], ebx
0x180025cb3  mov     [rsp+68h+var_10], 1
0x180025cbb  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180025cc0  mov     rbx, [rsp+68h+arg_0]
0x180025cc5  mov     eax, edi
0x180025cc7  mov     rsi, [rsp+68h+arg_8]
0x180025ccc  add     rsp, 60h
0x180025cd0  pop     rdi
0x180025cd1  retn
```
