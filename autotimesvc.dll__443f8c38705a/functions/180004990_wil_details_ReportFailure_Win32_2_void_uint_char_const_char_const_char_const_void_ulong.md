# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180004990`
- end: `0x180004a06`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `118`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180007e44`

## callees

- `0x180003c3c`
- `0x180004990`
- `0x180007278`

## string_xrefs

- `0x1800049c2`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`

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
    943,
    (int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
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
0x180004990  push    rbx
0x180004992  sub     rsp, 60h
0x180004996  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000499d  xor     edx, edx; int
0x18000499f  mov     r10, rcx
0x1800049a2  test    ebx, ebx
0x1800049a4  jle     short loc_1800049AF
0x1800049a6  movzx   ebx, bx
0x1800049a9  or      ebx, 80070000h
0x1800049af  mov     ecx, ebx; this
0x1800049b1  mov     [rsp+68h+var_18], ebx
0x1800049b5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800049ba  mov     rcx, [rsp+68h+arg_28]
0x1800049c2  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x1800049c9  mov     [rsp+68h+var_20], edx
0x1800049cd  xor     r9d, r9d
0x1800049d0  mov     [rsp+68h+var_30], rdx
0x1800049d5  mov     [rsp+68h+var_14], eax
0x1800049d9  lea     rax, [rsp+68h+var_18]
0x1800049de  mov     [rsp+68h+var_38], rax
0x1800049e3  mov     [rsp+68h+var_40], rcx
0x1800049e8  mov     rcx, r10
0x1800049eb  mov     [rsp+68h+var_48], rdx
0x1800049f0  mov     [rsp+68h+var_10], edx
0x1800049f4  mov     edx, 3AFh
0x1800049f9  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800049fe  mov     eax, ebx
0x180004a00  add     rsp, 60h
0x180004a04  pop     rbx
0x180004a05  retn
```
