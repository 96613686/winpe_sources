# RequestFeaturesInstallation$catch$10

- ea: `0x1800296b0`
- end: `0x1800296e9`
- name: `RequestFeaturesInstallation$catch$10`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180009264`

## string_xrefs

- `0x1800296c4`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\installerrequests.cpp`

## pseudocode

```c
__int64 __fastcall RequestFeaturesInstallation_catch_10(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 456),
                           (void *)0x3A,
                           (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\"
                                         "installerrequests.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800296b0  mov     [rsp+arg_8], rdx
0x1800296b5  push    rbp
0x1800296b6  sub     rsp, 30h
0x1800296ba  mov     rbp, rdx
0x1800296bd  mov     rcx, [rbp+1C8h]; this
0x1800296c4  lea     r8, aOnecoreShellCp_4; "onecore\\shell\\cpls\\internationalsett"...
0x1800296cb  mov     edx, 3Ah ; ':'; void *
0x1800296d0  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800296d5  mov     [rbp+30h], eax
0x1800296d8  mov     rax, 0
0x1800296e2  add     rsp, 30h
0x1800296e6  pop     rbp
0x1800296e7  retn
```
