# _RequiredLanguageFeaturesInstaller::RemoveNotApplicableFeatures_::_1_::catch$0

- ea: `0x180029280`
- end: `0x1800292b4`
- name: `_RequiredLanguageFeaturesInstaller::RemoveNotApplicableFeatures_::_1_::catch$0`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008c18`

## string_xrefs

- `0x180029291`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\RequiredLanguageComponentsInstaller.h`

## pseudocode

```c
__int64 __fastcall RequiredLanguageFeaturesInstaller::RemoveNotApplicableFeatures_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 72),
    (void *)0xC5,
    (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\RequiredLanguageComponentsInstaller.h",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180029280  mov     [rsp+arg_8], rdx
0x180029285  push    rbp
0x180029286  sub     rsp, 20h
0x18002928a  mov     rbp, rdx
0x18002928d  mov     rcx, [rbp+48h]; this
0x180029291  lea     r8, aOnecoreShellCp; "onecore\\shell\\cpls\\internationalsett"...
0x180029298  mov     edx, 0C5h; void *
0x18002929d  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800292a2  nop
0x1800292a3  mov     rax, 0
0x1800292ad  add     rsp, 20h
0x1800292b1  pop     rbp
0x1800292b2  retn
```
