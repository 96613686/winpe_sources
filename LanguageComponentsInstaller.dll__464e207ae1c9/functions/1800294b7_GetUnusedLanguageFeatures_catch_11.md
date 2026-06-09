# GetUnusedLanguageFeatures$catch$11

- ea: `0x1800294b7`
- end: `0x1800294f0`
- name: `GetUnusedLanguageFeatures$catch$11`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180009264`

## string_xrefs

- `0x1800294cb`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`

## pseudocode

```c
__int64 __fastcall GetUnusedLanguageFeatures_catch_11(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 568),
                           (void *)0x239,
                           (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\"
                                         "languagecomponentsinstaller.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800294b7  mov     [rsp+arg_8], rdx
0x1800294bc  push    rbp
0x1800294bd  sub     rsp, 20h
0x1800294c1  mov     rbp, rdx
0x1800294c4  mov     rcx, [rbp+238h]; this
0x1800294cb  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x1800294d2  mov     edx, 239h; void *
0x1800294d7  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800294dc  mov     [rbp+20h], eax
0x1800294df  mov     rax, 0
0x1800294e9  add     rsp, 20h
0x1800294ed  pop     rbp
0x1800294ee  retn
```
