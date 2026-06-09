# _StoreInstallResultInRegistry_::_1_::catch$2

- ea: `0x180029664`
- end: `0x180029698`
- name: `_StoreInstallResultInRegistry_::_1_::catch$2`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008c18`

## string_xrefs

- `0x180029675`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\installerrequests.cpp`

## pseudocode

```c
__int64 __fastcall StoreInstallResultInRegistry_::_1_::catch_2(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 104),
    (void *)0x13,
    (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\installerrequests.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180029664  mov     [rsp+arg_8], rdx
0x180029669  push    rbp
0x18002966a  sub     rsp, 30h
0x18002966e  mov     rbp, rdx
0x180029671  mov     rcx, [rbp+68h]; this
0x180029675  lea     r8, aOnecoreShellCp_4; "onecore\\shell\\cpls\\internationalsett"...
0x18002967c  mov     edx, 13h; void *
0x180029681  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180029686  nop
0x180029687  mov     rax, 0
0x180029691  add     rsp, 30h
0x180029695  pop     rbp
0x180029696  retn
```
