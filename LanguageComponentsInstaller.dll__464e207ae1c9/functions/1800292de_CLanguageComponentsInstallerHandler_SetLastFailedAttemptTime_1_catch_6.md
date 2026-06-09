# _CLanguageComponentsInstallerHandler::SetLastFailedAttemptTime_::_1_::catch$6

- ea: `0x1800292de`
- end: `0x180029315`
- name: `_CLanguageComponentsInstallerHandler::SetLastFailedAttemptTime_::_1_::catch$6`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008c18`

## string_xrefs

- `0x1800292f2`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`

## pseudocode

```c
__int64 __fastcall CLanguageComponentsInstallerHandler::SetLastFailedAttemptTime_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 152),
    (void *)0x1B1,
    (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800292de  mov     [rsp+arg_8], rdx
0x1800292e3  push    rbp
0x1800292e4  sub     rsp, 50h
0x1800292e8  mov     rbp, rdx
0x1800292eb  mov     rcx, [rbp+98h]; this
0x1800292f2  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x1800292f9  mov     edx, 1B1h; void *
0x1800292fe  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180029303  nop
0x180029304  mov     rax, 0
0x18002930e  add     rsp, 50h
0x180029312  pop     rbp
0x180029313  retn
```
