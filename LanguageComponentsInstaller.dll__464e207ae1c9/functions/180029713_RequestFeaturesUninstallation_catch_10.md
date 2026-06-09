# RequestFeaturesUninstallation$catch$10

- ea: `0x180029713`
- end: `0x18002974c`
- name: `RequestFeaturesUninstallation$catch$10`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180009264`

## string_xrefs

- `0x180029727`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\installerrequests.cpp`

## pseudocode

```c
__int64 __fastcall RequestFeaturesUninstallation_catch_10(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 424),
                           (void *)0x56,
                           (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\"
                                         "installerrequests.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029713  mov     [rsp+arg_8], rdx
0x180029718  push    rbp
0x180029719  sub     rsp, 20h
0x18002971d  mov     rbp, rdx
0x180029720  mov     rcx, [rbp+1A8h]; this
0x180029727  lea     r8, aOnecoreShellCp_4; "onecore\\shell\\cpls\\internationalsett"...
0x18002972e  mov     edx, 56h ; 'V'; void *
0x180029733  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029738  mov     [rbp+20h], eax
0x18002973b  mov     rax, 0
0x180029745  add     rsp, 20h
0x180029749  pop     rbp
0x18002974a  retn
```
