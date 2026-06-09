# wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18000afa8`
- end: `0x18000b018`
- name: `??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `112`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, __int64, wil::details *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ba00`

## callees

- `0x180002ed8`
- `0x180005b68`
- `0x18000afa8`

## string_xrefs

- `0x18000afd8`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\persistentlocationhelper.h`

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
    31,
    (int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\persistentlocationhelper.h",
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
0x18000afa8  push    rbx
0x18000afaa  sub     rsp, 60h
0x18000afae  mov     ebx, dword ptr [rsp+68h+arg_30]
0x18000afb5  mov     r9, rcx
0x18000afb8  test    ebx, ebx
0x18000afba  jle     short loc_18000AFC5
0x18000afbc  movzx   ebx, bx
0x18000afbf  or      ebx, 80070000h
0x18000afc5  mov     ecx, ebx; this
0x18000afc7  mov     [rsp+68h+var_18], ebx
0x18000afcb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000afd0  mov     rcx, [rsp+68h+arg_28]
0x18000afd8  lea     r8, aShellcommondes; "shellcommondesktopbase\\base\\embedded"...
0x18000afdf  mov     [rsp+68h+var_14], eax
0x18000afe3  mov     edx, 1Fh
0x18000afe8  lea     rax, [rsp+68h+var_18]
0x18000afed  mov     [rsp+68h+var_30], 0
0x18000aff6  mov     [rsp+68h+var_38], rax
0x18000affb  mov     [rsp+68h+var_40], rcx
0x18000b000  mov     rcx, r9
0x18000b003  mov     [rsp+68h+var_10], 0
0x18000b00b  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x18000b010  mov     eax, ebx
0x18000b012  add     rsp, 60h
0x18000b016  pop     rbx
0x18000b017  retn
```
