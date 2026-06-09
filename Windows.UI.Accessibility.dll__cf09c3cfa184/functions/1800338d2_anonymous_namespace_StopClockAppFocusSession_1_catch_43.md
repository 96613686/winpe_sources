# __anonymous_namespace_::StopClockAppFocusSession_::_1_::catch$43

- ea: `0x1800338d2`
- end: `0x180033909`
- name: `__anonymous_namespace_::StopClockAppFocusSession_::_1_::catch$43`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800150c0`

## string_xrefs

- `0x1800338e6`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\windows.internal.shell.focussessionthememanager.cpp`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::StopClockAppFocusSession_::_1_::catch_43(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 184),
    (void *)0x58,
    (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\windows.internal.shell.focussessionthememanager.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800338d2  mov     [rsp+arg_8], rdx
0x1800338d7  push    rbp
0x1800338d8  sub     rsp, 20h
0x1800338dc  mov     rbp, rdx
0x1800338df  mov     rcx, [rbp+0B8h]; this
0x1800338e6  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\accessibletech\\ex"...
0x1800338ed  mov     edx, 58h ; 'X'; void *
0x1800338f2  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800338f7  nop
0x1800338f8  mov     rax, 0
0x180033902  add     rsp, 20h
0x180033906  pop     rbp
0x180033907  retn
```
