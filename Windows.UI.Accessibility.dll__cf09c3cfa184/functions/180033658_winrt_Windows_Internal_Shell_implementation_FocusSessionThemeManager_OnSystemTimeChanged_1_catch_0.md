# _winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::OnSystemTimeChanged_::_1_::catch$0

- ea: `0x180033658`
- end: `0x18003368c`
- name: `_winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::OnSystemTimeChanged_::_1_::catch$0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800150c0`

## string_xrefs

- `0x180033669`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.internal.shell.focussessionthememanager.cpp`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::Shell::implementation::FocusSessionThemeManager::OnSystemTimeChanged_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 56),
    (void *)0x142,
    (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.shell.focussessionthememanager.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180033658  mov     [rsp+arg_8], rdx
0x18003365d  push    rbp
0x18003365e  sub     rsp, 20h
0x180033662  mov     rbp, rdx
0x180033665  mov     rcx, [rbp+38h]; this
0x180033669  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\accessibletech\\ex"...
0x180033670  mov     edx, 142h; void *
0x180033675  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003367a  nop
0x18003367b  mov     rax, 0
0x180033685  add     rsp, 20h
0x180033689  pop     rbp
0x18003368a  retn
```
