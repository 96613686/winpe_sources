# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18002a0f4`
- end: `0x18002a12a`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `54`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180029170`

## callees

- `0x180005498`

## string_xrefs

- `0x18002a113`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    154,
    (int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.viewmanagement.core.uisettingscontroller.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18002a0f4  sub     rsp, 48h
0x18002a0f8  mov     rax, [rsp+48h]
0x18002a0fd  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18002a102  mov     [rsp+48h+var_20], rax; __int64
0x18002a107  mov     [rsp+48h+var_28], 0; __int64
0x18002a110  xor     r9d, r9d; int
0x18002a113  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002a11a  mov     edx, 9Ah; int
0x18002a11f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002a124  nop
0x18002a125  add     rsp, 48h
0x18002a129  retn
```
