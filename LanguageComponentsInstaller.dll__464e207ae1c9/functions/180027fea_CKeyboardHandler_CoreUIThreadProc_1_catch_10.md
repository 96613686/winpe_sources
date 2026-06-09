# _CKeyboardHandler::CoreUIThreadProc_::_1_::catch$10

- ea: `0x180027fea`
- end: `0x180028020`
- name: `_CKeyboardHandler::CoreUIThreadProc_::_1_::catch$10`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180009264`

## string_xrefs

- `0x180027ffb`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`

## pseudocode

```c
__int64 __fastcall CKeyboardHandler::CoreUIThreadProc_::_1_::catch_10(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0x67,
                           (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\"
                                         "keyboardhandler.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180027fea  mov     [rsp+arg_8], rdx
0x180027fef  push    rbp
0x180027ff0  sub     rsp, 30h
0x180027ff4  mov     rbp, rdx
0x180027ff7  mov     rcx, [rbp+68h]; this
0x180027ffb  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x180028002  mov     edx, 67h ; 'g'; void *
0x180028007  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002800c  mov     [rbp+48h], eax
0x18002800f  mov     rax, 0
0x180028019  add     rsp, 30h
0x18002801d  pop     rbp
0x18002801e  retn
```
