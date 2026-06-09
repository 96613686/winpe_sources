# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x180017330`
- end: `0x1800173a1`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `113`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017b28`

## callees

- `0x18000a36c`
- `0x18000ee8c`
- `0x180017330`

## string_xrefs

- `0x180017362`: `onecore\ds\security\identity\certpoleng\cproviderentry.cpp`

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
    144,
    (unsigned int)"onecore\\ds\\security\\identity\\certpoleng\\cproviderentry.cpp",
    0,
    v8,
    a6,
    (__int64)v11);
  return v7;
}

```

## disassembly

```asm
0x180017330  push    rbx
0x180017332  sub     rsp, 60h
0x180017336  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18001733d  xor     edx, edx; int
0x18001733f  mov     r10, rcx
0x180017342  test    ebx, ebx
0x180017344  jle     short loc_18001734F
0x180017346  movzx   ebx, bx
0x180017349  or      ebx, 80070000h
0x18001734f  mov     ecx, ebx; this
0x180017351  mov     [rsp+68h+var_18], ebx
0x180017355  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001735a  mov     rcx, [rsp+68h+arg_28]
0x180017362  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\identity\\certpo"...
0x180017369  mov     [rsp+68h+var_20], edx
0x18001736d  xor     r9d, r9d
0x180017370  mov     [rsp+68h+var_14], eax
0x180017374  lea     rax, [rsp+68h+var_18]
0x180017379  mov     [rsp+68h+var_38], rax
0x18001737e  mov     [rsp+68h+var_40], rcx
0x180017383  mov     rcx, r10
0x180017386  mov     [rsp+68h+var_48], rdx
0x18001738b  mov     [rsp+68h+var_10], edx
0x18001738f  mov     edx, 90h
0x180017394  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x180017399  mov     eax, ebx
0x18001739b  add     rsp, 60h
0x18001739f  pop     rbx
0x1800173a0  retn
```
