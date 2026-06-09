# wil::details::ReportFailure_Win32<2>(void *,uint,char const *,char const *,char const *,void *,ulong)

- ea: `0x18002887c`
- end: `0x1800288e8`
- name: `??$ReportFailure_Win32@$01@details@wil@@YAJPEAXIPEBD110K@Z`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180029790`

## callees

- `0x180005280`
- `0x180006084`

## string_xrefs

- `0x1800288d2`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_Win32<2>(__int64 a1, int a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  int v6; // r10d
  _DWORD v8[6]; // [rsp+50h] [rbp-18h] BYREF

  v8[0] = -2147023436;
  v8[1] = wil::details::HrToNtStatus((wil::details *)0x800705B4LL, a2);
  v8[2] = 0;
  wil::details::ReportFailure_Base<2,0>(
    v6,
    142,
    (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.uiset"
                  "tingscontroller.cpp",
    0,
    0,
    a6,
    (__int64)v8,
    0);
  return 2147943860LL;
}

```

## disassembly

```asm
0x18002887c  sub     rsp, 68h
0x180028880  mov     r10, rcx
0x180028883  mov     [rsp+68h+var_18], 800705B4h
0x18002888b  mov     ecx, 800705B4h; this
0x180028890  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180028895  mov     rdx, [rsp+68h+arg_28]
0x18002889d  lea     rcx, [rsp+68h+var_18]
0x1800288a2  xor     r8d, r8d
0x1800288a5  mov     [rsp+68h+var_14], eax
0x1800288a9  mov     [rsp+68h+var_20], r8d
0x1800288ae  xor     r9d, r9d
0x1800288b1  mov     [rsp+68h+var_30], r8
0x1800288b6  mov     [rsp+68h+var_38], rcx
0x1800288bb  mov     rcx, r10
0x1800288be  mov     [rsp+68h+var_40], rdx
0x1800288c3  mov     edx, 8Eh
0x1800288c8  mov     [rsp+68h+var_48], r8
0x1800288cd  mov     [rsp+68h+var_10], r8d
0x1800288d2  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x1800288d9  call    ??$ReportFailure_Base@$01$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<2,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x1800288de  mov     eax, 800705B4h
0x1800288e3  add     rsp, 68h
0x1800288e7  retn
```
