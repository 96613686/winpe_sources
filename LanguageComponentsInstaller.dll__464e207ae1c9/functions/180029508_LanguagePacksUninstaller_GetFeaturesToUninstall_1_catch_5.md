# _LanguagePacksUninstaller::GetFeaturesToUninstall_::_1_::catch$5

- ea: `0x180029508`
- end: `0x18002953f`
- name: `_LanguagePacksUninstaller::GetFeaturesToUninstall_::_1_::catch$5`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008c18`

## string_xrefs

- `0x18002951c`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagepacksuninstaller.cpp`

## pseudocode

```c
__int64 __fastcall LanguagePacksUninstaller::GetFeaturesToUninstall_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 360),
    (void *)0x35,
    (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagepacksuninstaller.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180029508  mov     [rsp+arg_8], rdx
0x18002950d  push    rbp
0x18002950e  sub     rsp, 20h
0x180029512  mov     rbp, rdx
0x180029515  mov     rcx, [rbp+168h]; this
0x18002951c  lea     r8, aOnecoreShellCp_2; "onecore\\shell\\cpls\\internationalsett"...
0x180029523  mov     edx, 35h ; '5'; void *
0x180029528  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18002952d  nop
0x18002952e  mov     rax, 0
0x180029538  add     rsp, 20h
0x18002953c  pop     rbp
0x18002953d  retn
```
