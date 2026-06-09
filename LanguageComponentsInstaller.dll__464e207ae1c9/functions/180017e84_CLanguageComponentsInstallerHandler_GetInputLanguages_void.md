# CLanguageComponentsInstallerHandler::GetInputLanguages(void)

- ea: `0x180017e84`
- end: `0x1800180ad`
- name: `?GetInputLanguages@CLanguageComponentsInstallerHandler@@AEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `553`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013e1c`
- `0x1800140e0`
- `0x180014788`

## callees

- `0x180003520`
- `0x1800045cc`
- `0x180005954`
- `0x180006380`
- `0x1800072bc`
- `0x180007594`
- `0x18000a7fc`
- `0x18000c32c`
- `0x180017e84`
- `0x1800214f4`
- `0x180021af4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017f87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018044`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017f87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018044`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017fb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017fb6`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180017ec5`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180017ec5`
- `ext-ms-win-globalization-input-l1-1-3!WGIGetInputLanguagesForAllUsers` at `0x180017f9e`
- `ext-ms-win-globalization-input-l1-1-3!WGIGetInputLanguagesForAllUsers` at `0x180017f9e`

## string_xrefs

- `0x180018071`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`
- `0x180018086`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`
- `0x18001809b`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagecomponentsinstaller.cpp`

## pseudocode

```c
__int64 __fastcall CLanguageComponentsInstallerHandler::GetInputLanguages(__int64 a1, __int64 a2)
{
  int Instance; // eax
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  int AllInstalledKeyboardLanguages; // eax
  int v6; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v8; // r8
  struct CKeyboardHandler *v10[2]; // [rsp+28h] [rbp-58h] BYREF
  __int128 v11; // [rsp+38h] [rbp-48h]
  __int128 v12; // [rsp+48h] [rbp-38h] BYREF
  __int64 v13; // [rsp+58h] [rbp-28h]
  __int64 v14; // [rsp+60h] [rbp-20h]
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  int v16; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v14 = a2;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() )
  {
    string = 0;
    v10[0] = (struct CKeyboardHandler *)&string;
    v10[1] = 0;
    LOBYTE(v11) = 1;
    Instance = CKeyboardHandler::CreateInstance(&v10[1]);
    if ( Instance < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
        (const char *)(unsigned int)Instance,
        1);
    if ( (_BYTE)v11 )
    {
      v4 = *(void (__fastcall ****)(_QWORD, __int64))v10[0];
      *(_QWORD *)v10[0] = v10[1];
      if ( v4 )
        (**v4)(v4, 1);
    }
    AllInstalledKeyboardLanguages = CKeyboardHandler::GetAllInstalledKeyboardLanguages(string, a2);
    if ( AllInstalledKeyboardLanguages < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
        (const char *)(unsigned int)AllInstalledKeyboardLanguages,
        1);
    if ( string )
      (**(void (__fastcall ***)(HSTRING, __int64))string)(string, 1);
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_KSOD>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_KSOD>::GetImpl'::`2'::impl)
         && (unsigned __int8)IsWGIGetInputLanguagesForAllUsersPresent() )
  {
    v16 = 0;
    WindowsDeleteString(0);
    string = 0;
    v6 = WGIGetInputLanguagesForAllUsers(59, &string, &v16);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagecomponentsinstaller.cpp",
        (const char *)(unsigned int)v6,
        1);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    *(_OWORD *)v10 = 0;
    v11 = 0;
    v8 = -1;
    do
      ++v8;
    while ( StringRawBuffer[v8] );
    std::wstring::_Construct<1,unsigned short const *>(v10);
    WstringContainerFromDelimitedString<std::vector<std::wstring>>(&v12, v10);
    std::wstring::~wstring(v10);
    if ( (__int128 *)a2 != &v12 )
    {
      std::vector<std::wstring>::_Tidy(a2);
      *(_OWORD *)a2 = v12;
      *(_QWORD *)(a2 + 16) = v13;
      v12 = 0;
      v13 = 0;
    }
    std::vector<std::wstring>::_Tidy(&v12);
    if ( string )
      WindowsDeleteString(string);
  }
  return a2;
}

```

## disassembly

```asm
0x180017e84  mov     [rsp-8+arg_0], rbx
0x180017e89  mov     [rsp-8+arg_10], rdi
0x180017e8e  push    rbp
0x180017e8f  mov     rbp, rsp
0x180017e92  sub     rsp, 80h
0x180017e99  mov     rax, cs:__security_cookie
0x180017ea0  xor     rax, rsp
0x180017ea3  mov     [rbp+var_8], rax
0x180017ea7  mov     rbx, rdx
0x180017eaa  mov     [rbp+var_20], rdx
0x180017eae  xor     edi, edi
0x180017eb0  mov     [rbp+var_60], edi
0x180017eb3  mov     [rdx], rdi
0x180017eb6  mov     [rdx+8], rdi
0x180017eba  mov     [rdx+10h], rdi
0x180017ebe  mov     [rbp+var_60], 1
0x180017ec5  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x180017ecb  test    al, al
0x180017ecd  jz      loc_180017F5D
0x180017ed3  mov     [rbp+string], rdi
0x180017ed7  lea     rax, [rbp+string]
0x180017edb  mov     [rbp+var_58], rax
0x180017edf  mov     [rbp+var_58+8], rdi
0x180017ee3  mov     byte ptr [rbp+var_48], 1
0x180017ee7  lea     rcx, [rbp+var_58+8]; struct CKeyboardHandler **
0x180017eeb  call    ?CreateInstance@CKeyboardHandler@@SAJPEAPEAV1@@Z; CKeyboardHandler::CreateInstance(CKeyboardHandler * *)
0x180017ef0  mov     rcx, [rbp+8]; this
0x180017ef4  test    eax, eax
0x180017ef6  js      loc_180018083
0x180017efc  cmp     byte ptr [rbp+var_48], dil
0x180017f00  jz      short loc_180017F23
0x180017f02  mov     rdx, [rbp+var_58]
0x180017f06  mov     rcx, [rdx]
0x180017f09  mov     rax, [rbp+var_58+8]
0x180017f0d  mov     [rdx], rax
0x180017f10  test    rcx, rcx
0x180017f13  jz      short loc_180017F23
0x180017f15  mov     rax, [rcx]
0x180017f18  lea     edx, [rdi+1]
0x180017f1b  mov     rax, [rax]
0x180017f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f23  mov     rdx, rbx
0x180017f26  mov     rcx, [rbp+string]
0x180017f2a  call    ?GetAllInstalledKeyboardLanguages@CKeyboardHandler@@QEAAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; CKeyboardHandler::GetAllInstalledKeyboardLanguages(std::vector<std::wstring> *)
0x180017f2f  mov     rcx, [rbp+8]; this
0x180017f33  test    eax, eax
0x180017f35  js      loc_180018098
0x180017f3b  mov     rcx, [rbp+string]
0x180017f3f  test    rcx, rcx
0x180017f42  jz      loc_18001804A
0x180017f48  mov     rax, [rcx]
0x180017f4b  mov     edx, 1
0x180017f50  mov     rax, [rax]
0x180017f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f58  jmp     loc_18001804A
0x180017f5d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KSOD@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KSOD@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KSOD> `wil::Feature<__WilFeatureTraits_Feature_KSOD>::GetImpl(void)'::`2'::impl
0x180017f64  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KSOD@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KSOD>::__private_IsEnabled(void)
0x180017f69  test    al, al
0x180017f6b  jz      loc_18001804A
0x180017f71  call    IsWGIGetInputLanguagesForAllUsersPresent
0x180017f76  test    al, al
0x180017f78  jz      loc_18001804A
0x180017f7e  mov     [rbp+string], rdi
0x180017f82  mov     [rbp+var_10], edi
0x180017f85  xor     ecx, ecx; string
0x180017f87  call    cs:__imp_WindowsDeleteString
0x180017f8d  mov     [rbp+string], rdi
0x180017f91  mov     ecx, 3Bh ; ';'
0x180017f96  lea     r8, [rbp+var_10]
0x180017f9a  lea     rdx, [rbp+string]
0x180017f9e  call    cs:__imp_WGIGetInputLanguagesForAllUsers
0x180017fa4  mov     rcx, [rbp+8]; this
0x180017fa8  test    eax, eax
0x180017faa  js      loc_18001806E
0x180017fb0  xor     edx, edx; length
0x180017fb2  mov     rcx, [rbp+string]; string
0x180017fb6  call    cs:__imp_WindowsGetStringRawBuffer
0x180017fbc  xorps   xmm0, xmm0
0x180017fbf  movups  xmmword ptr [rbp+var_58], xmm0
0x180017fc3  xorps   xmm1, xmm1
0x180017fc6  movdqu  [rbp+var_48], xmm1
0x180017fcb  or      r8, 0FFFFFFFFFFFFFFFFh
0x180017fcf  inc     r8
0x180017fd2  cmp     [rax+r8*2], di
0x180017fd7  jnz     short loc_180017FCF
0x180017fd9  mov     rdx, rax
0x180017fdc  lea     rcx, [rbp+var_58]
0x180017fe0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017fe5  nop
0x180017fe6  lea     rdx, [rbp+var_58]
0x180017fea  lea     rcx, [rbp+var_38]
0x180017fee  call    ??$WstringContainerFromDelimitedString@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@G@Z; WstringContainerFromDelimitedString<std::vector<std::wstring>>(std::wstring const &,ushort)
0x180017ff3  nop
0x180017ff4  lea     rcx, [rbp+var_58]; void *
0x180017ff8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180017ffd  lea     rax, [rbp+var_38]
0x180018001  cmp     rbx, rax
0x180018004  jz      short loc_180018031
0x180018006  mov     rcx, rbx
0x180018009  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001800e  mov     rax, qword ptr [rbp+var_38]
0x180018012  mov     [rbx], rax
0x180018015  mov     rax, qword ptr [rbp+var_38+8]
0x180018019  mov     [rbx+8], rax
0x18001801d  mov     rax, [rbp+var_28]
0x180018021  mov     [rbx+10h], rax
0x180018025  xorps   xmm0, xmm0
0x180018028  movdqu  [rbp+var_38], xmm0
0x18001802d  mov     [rbp+var_28], rdi
0x180018031  lea     rcx, [rbp+var_38]
0x180018035  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001803a  nop
0x18001803b  mov     rcx, [rbp+string]; string
0x18001803f  test    rcx, rcx
0x180018042  jz      short loc_18001804A
0x180018044  call    cs:__imp_WindowsDeleteString
0x18001804a  mov     rax, rbx
0x18001804d  mov     rcx, [rbp+var_8]
0x180018051  xor     rcx, rsp; StackCookie
0x180018054  call    __security_check_cookie
0x180018059  lea     r11, [rsp+80h+var_s0]
0x180018061  mov     rbx, [r11+10h]
0x180018065  mov     rdi, [r11+20h]
0x180018069  mov     rsp, r11
0x18001806c  pop     rbp
0x18001806d  retn
0x18001806e  mov     r9d, eax; char *
0x180018071  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x180018078  mov     edx, 0F8h; void *
0x18001807d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018083  mov     r9d, eax; char *
0x180018086  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x18001808d  mov     edx, 0F0h; void *
0x180018092  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180018098  mov     r9d, eax; char *
0x18001809b  lea     r8, aOnecoreShellCp_1; "onecore\\shell\\cpls\\internationalsett"...
0x1800180a2  mov     edx, 0F1h; void *
0x1800180a7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
