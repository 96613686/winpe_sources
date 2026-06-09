# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000434c`
- end: `0x1800043bc`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000e858`

## callees

- `0x1800035e4`
- `0x18000434c`
- `0x180008f00`

## string_xrefs

- `0x18000437e`: `pcshell\shell\applistbackuplauncher\dll\applistbackuplauncher.cpp`

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
    111,
    (unsigned int)"pcshell\\shell\\applistbackuplauncher\\dll\\applistbackuplauncher.cpp",
    0,
    v8,
    a6,
    (__int64)v11);
  return v7;
}

```

## disassembly

```asm
0x18000434c  push    rbx
0x18000434e  sub     rsp, 60h
0x180004352  mov     ebx, dword ptr [rsp+68h+arg_30]
0x180004359  xor     edx, edx; int
0x18000435b  mov     r10, rcx
0x18000435e  test    ebx, ebx
0x180004360  jle     short loc_18000436B
0x180004362  movzx   ebx, bx
0x180004365  or      ebx, 80070000h
0x18000436b  mov     ecx, ebx; this
0x18000436d  mov     [rsp+68h+var_18], ebx
0x180004371  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004376  mov     rcx, [rsp+68h+arg_28]
0x18000437e  lea     r8, aPcshellShellAp; "pcshell\\shell\\applistbackuplauncher\\"...
0x180004385  mov     [rsp+68h+var_20], edx
0x180004389  xor     r9d, r9d
0x18000438c  mov     [rsp+68h+var_14], eax
0x180004390  lea     rax, [rsp+68h+var_18]
0x180004395  mov     [rsp+68h+var_38], rax
0x18000439a  mov     [rsp+68h+var_40], rcx
0x18000439f  mov     rcx, r10
0x1800043a2  mov     [rsp+68h+var_48], rdx
0x1800043a7  mov     [rsp+68h+var_10], edx
0x1800043ab  lea     edx, [r9+6Fh]
0x1800043af  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800043b4  mov     eax, ebx
0x1800043b6  add     rsp, 60h
0x1800043ba  pop     rbx
0x1800043bb  retn
```
