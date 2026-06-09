# __anonymous_namespace_::Win32TextScaleThreadProc_::_1_::catch$4

- ea: `0x180033e2d`
- end: `0x180033e63`
- name: `__anonymous_namespace_::Win32TextScaleThreadProc_::_1_::catch$4`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000e9d4`

## string_xrefs

- `0x180033e3e`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.ui.viewmanagement.core.uisettingscontroller.cpp`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::Win32TextScaleThreadProc_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x78,
                           (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.ui.vi"
                                         "ewmanagement.core.uisettingscontroller.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180033e2d  mov     [rsp+arg_8], rdx
0x180033e32  push    rbp
0x180033e33  sub     rsp, 30h
0x180033e37  mov     rbp, rdx
0x180033e3a  mov     rcx, [rbp+38h]; this
0x180033e3e  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\accessibletech\\ex"...
0x180033e45  mov     edx, 78h ; 'x'; void *
0x180033e4a  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180033e4f  mov     [rbp+40h], eax
0x180033e52  mov     rax, 0
0x180033e5c  add     rsp, 30h
0x180033e60  pop     rbp
0x180033e61  retn
```
