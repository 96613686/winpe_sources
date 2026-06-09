# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180018c54`
- end: `0x180018cca`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `118`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001ba28`

## callees

- `0x180009cec`
- `0x18000db8c`
- `0x180018c54`

## string_xrefs

- `0x180018c86`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<2>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // r10d
  _DWORD v11[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v11[0] = v7;
  v11[1] = wil::details::HrToNtStatus((wil::details *)v7, 0);
  v11[2] = v8;
  wil::details::ReportFailure_Base<2,0>(
    v9,
    870,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
    0,
    v8,
    a6,
    (__int64)v11,
    v8);
  return v7;
}

```

## disassembly

```asm
0x180018c54  push    rbx
0x180018c56  sub     rsp, 60h
0x180018c5a  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180018c61  xor     edx, edx; int
0x180018c63  mov     r10, rcx
0x180018c66  test    ebx, ebx
0x180018c68  jle     short loc_180018C73
0x180018c6a  movzx   ebx, bx
0x180018c6d  or      ebx, 80070000h
0x180018c73  mov     ecx, ebx; this
0x180018c75  mov     [rsp+68h+var_18], ebx
0x180018c79  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180018c7e  mov     rcx, [rsp+68h+arg_28]
0x180018c86  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018c8d  mov     [rsp+68h+var_20], edx
0x180018c91  xor     r9d, r9d
0x180018c94  mov     [rsp+68h+var_30], rdx
0x180018c99  mov     [rsp+68h+var_14], eax
0x180018c9d  lea     rax, [rsp+68h+var_18]
0x180018ca2  mov     [rsp+68h+var_38], rax
0x180018ca7  mov     [rsp+68h+var_40], rcx
0x180018cac  mov     rcx, r10
0x180018caf  mov     [rsp+68h+var_48], rdx
0x180018cb4  mov     [rsp+68h+var_10], edx
0x180018cb8  mov     edx, 366h
0x180018cbd  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180018cc2  mov     eax, ebx
0x180018cc4  add     rsp, 60h
0x180018cc8  pop     rbx
0x180018cc9  retn
```
