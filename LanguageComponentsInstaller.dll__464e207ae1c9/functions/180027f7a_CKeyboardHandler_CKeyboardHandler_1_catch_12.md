# _CKeyboardHandler::_CKeyboardHandler_::_1_::catch$12

- ea: `0x180027f7a`
- end: `0x180027fae`
- name: `_CKeyboardHandler::_CKeyboardHandler_::_1_::catch$12`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008c18`

## string_xrefs

- `0x180027f8b`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`

## pseudocode

```c
__int64 __fastcall CKeyboardHandler::_CKeyboardHandler_::_1_::catch_12(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x25,
    (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180027f7a  mov     [rsp+arg_8], rdx
0x180027f7f  push    rbp
0x180027f80  sub     rsp, 20h
0x180027f84  mov     rbp, rdx
0x180027f87  mov     rcx, [rbp+28h]; this
0x180027f8b  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x180027f92  mov     edx, 25h ; '%'; void *
0x180027f97  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180027f9c  nop
0x180027f9d  mov     rax, 0
0x180027fa7  add     rsp, 20h
0x180027fab  pop     rbp
0x180027fac  retn
```
