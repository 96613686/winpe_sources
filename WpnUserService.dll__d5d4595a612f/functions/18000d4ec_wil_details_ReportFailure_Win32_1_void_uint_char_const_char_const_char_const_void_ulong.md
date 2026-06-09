# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000d4ec`
- end: `0x18000d55c`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `112`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000e9c4`

## callees

- `0x1800037f8`
- `0x180005800`
- `0x18000d4ec`

## string_xrefs

- `0x18000d51c`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\servicebase\servicebase.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        wil::details *a7)
{
  unsigned int v7; // ebx
  int v8; // r9d
  int v10; // [rsp+20h] [rbp-48h]
  _DWORD v11[6]; // [rsp+50h] [rbp-18h] BYREF

  v7 = (unsigned int)a7;
  if ( (int)a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  v11[0] = v7;
  v11[1] = wil::details::HrToNtStatus((wil::details *)v7, a2);
  v11[2] = 0;
  wil::details::ReportFailure_Base<1,0>(
    v8,
    655,
    (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\servicebase\\servicebase.cpp",
    v8,
    v10,
    a6,
    (int)v11,
    0);
  return v7;
}

```

## disassembly

```asm
0x18000d4ec  push    rbx
0x18000d4ee  sub     rsp, 60h
0x18000d4f2  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000d4f9  mov     r9, rcx
0x18000d4fc  test    ebx, ebx
0x18000d4fe  jle     short loc_18000D509
0x18000d500  movzx   ebx, bx
0x18000d503  or      ebx, 80070000h
0x18000d509  mov     ecx, ebx; this
0x18000d50b  mov     [rsp+68h+var_18], ebx
0x18000d50f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d514  mov     rcx, [rsp+68h+arg_28]
0x18000d51c  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000d523  mov     [rsp+68h+var_14], eax
0x18000d527  mov     edx, 28Fh
0x18000d52c  lea     rax, [rsp+68h+var_18]
0x18000d531  mov     [rsp+68h+var_30], 0
0x18000d53a  mov     [rsp+68h+var_38], rax
0x18000d53f  mov     [rsp+68h+var_40], rcx
0x18000d544  mov     rcx, r9
0x18000d547  mov     [rsp+68h+var_10], 0
0x18000d54f  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000d554  mov     eax, ebx
0x18000d556  add     rsp, 60h
0x18000d55a  pop     rbx
0x18000d55b  retn
```
