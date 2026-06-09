# wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18001cd50`
- end: `0x18001cda7`
- name: `??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `87`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180024eac`
- `0x1800257c8`

## callees

- `0x18000706c`
- `0x18001cb40`
- `0x18001cd50`

## string_xrefs

- `0x18001cd78`: `onecoreuap\windows\iot\winrt\sysadmin\lib\systemupdate\systemupdatemanager.cpp`

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
  int v8; // edx
  int v9; // r9d

  v7 = (unsigned int)a7;
  if ( a7 > 0 )
    v7 = (unsigned __int16)a7 | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)v7, a2);
  wil::details::ReportFailure_Base<0,0>(
    v9,
    v8,
    (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\systemupdate\\systemupdatemanager.cpp",
    v9);
}

```

## disassembly

```asm
0x18001cd50  sub     rsp, 68h
0x18001cd54  mov     r9, rcx
0x18001cd57  mov     ecx, [rsp+68h+arg_30]
0x18001cd5e  test    ecx, ecx
0x18001cd60  jle     short loc_18001CD6B
0x18001cd62  movzx   ecx, cx
0x18001cd65  or      ecx, 80070000h; this
0x18001cd6b  mov     [rsp+68h+var_18], ecx
0x18001cd6f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001cd74  mov     [rsp+68h+var_14], eax
0x18001cd78  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x18001cd7f  lea     rax, [rsp+68h+var_18]
0x18001cd84  mov     [rsp+68h+var_10], 0
0x18001cd8c  mov     [rsp+68h+var_38], rax
0x18001cd91  mov     rcx, r9
0x18001cd94  mov     rax, [rsp+68h+arg_28]
0x18001cd9c  mov     [rsp+68h+var_40], rax
0x18001cda1  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
