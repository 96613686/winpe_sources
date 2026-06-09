# CLanguageComponentsInstallerHandler::RequestFeaturesInstall(std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>> const &)

- ea: `0x18001b3c0`
- end: `0x18001b435`
- name: `?RequestFeaturesInstall@CLanguageComponentsInstallerHandler@@CAXAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000a7fc`
- `0x180012c04`
- `0x1800176b4`
- `0x18001b3c0`
- `0x180025d20`

## string_xrefs

- `0x18001b423`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`

## pseudocode

```c
__int64 __fastcall CLanguageComponentsInstallerHandler::RequestFeaturesInstall(_QWORD *a1)
{
  int v1; // eax
  int v3; // [rsp+20h] [rbp-38h]
  _QWORD v4[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  GetCbsLanguageFeatureIds(v4, *a1, a1[1]);
  v1 = RequestFeaturesInstallation(v4[0], -1431655765 * (unsigned int)((__int64)(v4[1] - v4[0]) >> 3), 0, 0, 0);
  if ( v1 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1E8,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
      (const char *)(unsigned int)v1,
      v3);
  return std::vector<CbsLanguageFeatureId>::~vector<CbsLanguageFeatureId>(v4);
}

```

## disassembly

```asm
0x18001b3c0  sub     rsp, 58h
0x18001b3c4  mov     r8, [rcx+8]
0x18001b3c8  mov     rdx, [rcx]
0x18001b3cb  lea     rcx, [rsp+58h+var_28]
0x18001b3d0  call    ?GetCbsLanguageFeatureIds@@YA?AV?$vector@UCbsLanguageFeatureId@@V?$allocator@UCbsLanguageFeatureId@@@std@@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@2@0@Z; GetCbsLanguageFeatureIds(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>)
0x18001b3d5  nop
0x18001b3d6  mov     rcx, [rsp+58h+var_28]
0x18001b3db  mov     rdx, [rsp+58h+var_20]
0x18001b3e0  sub     rdx, rcx
0x18001b3e3  sar     rdx, 3
0x18001b3e7  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001b3f1  imul    rdx, rax
0x18001b3f5  mov     [rsp+58h+var_38], 0; int
0x18001b3fd  xor     r9d, r9d
0x18001b400  xor     r8d, r8d
0x18001b403  call    RequestFeaturesInstallation
0x18001b408  mov     rcx, [rsp+58h]; this
0x18001b40d  test    eax, eax
0x18001b40f  js      short loc_18001B420
0x18001b411  lea     rcx, [rsp+58h+var_28]
0x18001b416  call    ??1?$vector@UCbsLanguageFeatureId@@V?$allocator@UCbsLanguageFeatureId@@@std@@@std@@QEAA@XZ; std::vector<CbsLanguageFeatureId>::~vector<CbsLanguageFeatureId>(void)
0x18001b41b  add     rsp, 58h
0x18001b41f  retn
0x18001b420  mov     r9d, eax; char *
0x18001b423  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x18001b42a  mov     edx, 1E8h; void *
0x18001b42f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
