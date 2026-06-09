# _winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RefreshTimer_::_1_::catch$15

- ea: `0x1800336c8`
- end: `0x1800336fc`
- name: `_winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RefreshTimer_::_1_::catch$15`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800150c0`

## string_xrefs

- `0x1800336d9`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.internal.shell.focussessionthememanager.cpp`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::RefreshTimer_::_1_::catch_15(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 120),
    (void *)0x1B5,
    (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.shell.focussessionthememanager.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800336c8  mov     [rsp+arg_8], rdx
0x1800336cd  push    rbp
0x1800336ce  sub     rsp, 20h
0x1800336d2  mov     rbp, rdx
0x1800336d5  mov     rcx, [rbp+78h]; this
0x1800336d9  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\accessibletech\\ex"...
0x1800336e0  mov     edx, 1B5h; void *
0x1800336e5  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800336ea  nop
0x1800336eb  mov     rax, 0
0x1800336f5  add     rsp, 20h
0x1800336f9  pop     rbp
0x1800336fa  retn
```
