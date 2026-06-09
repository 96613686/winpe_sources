# _winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursorThreadProc_::_1_::catch$2

- ea: `0x180032876`
- end: `0x1800328ac`
- name: `_winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursorThreadProc_::_1_::catch$2`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000e9d4`

## string_xrefs

- `0x180032887`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.internal.accessibility.experience.customcursor.cpp`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::Accessibility::Experience::implementation::CustomCursorThreadProc_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x20,
                           (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.inter"
                                         "nal.accessibility.experience.customcursor.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180032876  mov     [rsp+arg_8], rdx
0x18003287b  push    rbp
0x18003287c  sub     rsp, 20h
0x180032880  mov     rbp, rdx
0x180032883  mov     rcx, [rbp+28h]; this
0x180032887  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\accessibletech\\ex"...
0x18003288e  mov     edx, 20h ; ' '; void *
0x180032893  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032898  mov     [rbp+30h], eax
0x18003289b  mov     rax, 0
0x1800328a5  add     rsp, 20h
0x1800328a9  pop     rbp
0x1800328aa  retn
```
