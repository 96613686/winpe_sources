# PersonalizationThemeBackupRestoreHandler::ApplyInboxPersonalizationTheme(wil::cloud_store_data<Windows::Data::PersonalizationThemes::Theme> const &)

- ea: `0x18009ac3c`
- end: `0x18009ae89`
- name: `?ApplyInboxPersonalizationTheme@PersonalizationThemeBackupRestoreHandler@@AEAAXAEBV?$cloud_store_data@UTheme@PersonalizationThemes@Data@Windows@@@wil@@@Z`
- size: `589`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009c380`

## callees

- `0x18000c6e0`
- `0x18001666c`
- `0x18001a96c`
- `0x18001cf84`
- `0x18001cfa4`
- `0x18001d0a8`
- `0x18001da4c`
- `0x1800284d0`
- `0x180031dc0`
- `0x18004712c`
- `0x180095d1c`
- `0x1800977e8`
- `0x180098178`
- `0x1800984dc`
- `0x18009862c`
- `0x18009a6b8`
- `0x18009ac3c`
- `0x18009c90c`
- `0x18009cbec`
- `0x18009d8e8`
- `0x18009defc`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009acee`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009acee`

## string_xrefs

- `0x18009adee`: `Theme Registry set successfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PersonalizationThemeBackupRestoreHandler::ApplyInboxPersonalizationTheme(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rcx
  const WCHAR *v6; // rax
  HRESULT v7; // eax
  __int64 v8; // rdx
  const struct std::filesystem::path *v9; // rdx
  bool v10; // bl
  HKEY v11; // rcx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  HKEY v15; // rcx
  __int64 v16; // rcx
  PWSTR ppszPathOut; // [rsp+20h] [rbp-40h] BYREF
  PWSTR v19; // [rsp+28h] [rbp-38h] BYREF
  PCWSTR pszPathIn; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v21[32]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  ppszPathOut = 0;
  v3 = a2 + 8;
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 8);
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                          v4,
                          *(_QWORD *)(v3 + 16),
                          &word_1801382A0,
                          0) )
  {
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        v5,
        &InformationMessage,
        L"Personalization Theme Restore",
        L"Base personalization theme not found");
  }
  else
  {
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
      &pszPathIn,
      L"%windir%\\Resources\\Themes");
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v3);
    v7 = PathAllocCombine(pszPathIn, v6, 1u, &ppszPathOut);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x177,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\personalizationthemebackuprestorehandler.cpp",
        (const char *)(unsigned int)v7,
        (int)ppszPathOut);
    LOBYTE(v8) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler>::GetImpl'::`2'::impl,
      v8);
    v19 = ppszPathOut;
    std::filesystem::path::path(v21, &v19);
    v10 = std::filesystem::exists((std::filesystem *)v21, v9);
    std::wstring::_Tidy_deallocate(v21);
    if ( v10 )
    {
      v12 = SHRegSetBOOL(v11, L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes", L"ThemeRestored", 1);
      v11 = (HKEY)retaddr;
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x17D,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\personalizationthemebackuprestorehandler.cpp",
          (const char *)(unsigned int)v12,
          (int)ppszPathOut);
    }
    v13 = SHRegSetString(v11, L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes", L"CurrentTheme", ppszPathOut);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x180,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\personalizationthemebackuprestorehandler.cpp",
        (const char *)(unsigned int)v13,
        (int)ppszPathOut);
    LOBYTE(v14) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PersonalizationCustomThemeRestoreHandler>::ReportUsage(
      &`wil::Feature<__WilFeatureTraits_Feature_PersonalizationCustomThemeRestoreHandler>::GetImpl'::`2'::impl,
      v14);
    if ( SHRegSetString(
           v15,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
           L"RestoredInboxTheme",
           ppszPathOut) < 0 )
    {
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(
          v16,
          &InformationMessage,
          L"Personalization Theme Restore",
          L"Failed to set RestoredInboxTheme");
      CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_ApiActivity<unsigned short const (&)[12],unsigned short const (&)[45],unsigned short const (&)[7]>();
    }
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        v16,
        &InformationMessage,
        L"Personalization Theme Restore",
        L"Theme Registry set successfully");
    CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_ApiActivity<unsigned short const (&)[12],unsigned short const (&)[32],unsigned short const (&)[8]>();
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>>::data(
                            a1 + 8,
                            &v19)
             + 273LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>>(&v19);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPathIn);
  }
  return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPathOut);
}

```

## disassembly

```asm
0x18009ac3c  mov     [rsp-8+arg_10], rbx
0x18009ac41  mov     [rsp-8+arg_18], rdi
0x18009ac46  push    rbp
0x18009ac47  mov     rbp, rsp
0x18009ac4a  sub     rsp, 60h
0x18009ac4e  mov     rax, cs:__security_cookie
0x18009ac55  xor     rax, rsp
0x18009ac58  mov     [rbp+var_8], rax
0x18009ac5c  mov     rdi, rcx
0x18009ac5f  mov     [rbp+ppszPathOut], 0
0x18009ac67  lea     rbx, [rdx+8]
0x18009ac6b  mov     rcx, rbx
0x18009ac6e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009ac73  xor     r9d, r9d
0x18009ac76  lea     r8, word_1801382A0
0x18009ac7d  mov     rdx, [rbx+10h]
0x18009ac81  mov     rcx, rax
0x18009ac84  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18009ac89  test    al, al
0x18009ac8b  jz      short loc_18009ACB9
0x18009ac8d  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x18009ac94  jz      loc_18009AE38
0x18009ac9a  lea     r9, aBasePersonaliz; "Base personalization theme not found"
0x18009aca1  lea     r8, aPersonalizatio_4; "Personalization Theme Restore"
0x18009aca8  lea     rdx, InformationMessage
0x18009acaf  call    McTemplateU0zz_EventWriteTransfer
0x18009acb4  jmp     loc_18009AE38
0x18009acb9  lea     rdx, aWindirResource; "%windir%\\Resources\\Themes"
0x18009acc0  lea     rcx, [rbp+pszPathIn]
0x18009acc4  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x18009acc9  nop
0x18009acca  xor     edx, edx
0x18009accc  lea     rcx, [rbp+ppszPathOut]
0x18009acd0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009acd5  mov     rcx, rbx
0x18009acd8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009acdd  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x18009ace1  mov     r8d, 1; dwFlags
0x18009ace7  mov     rdx, rax; pszMore
0x18009acea  mov     rcx, [rbp+pszPathIn]; pszPathIn
0x18009acee  call    cs:__imp_PathAllocCombine
0x18009acf4  mov     rcx, [rbp+8]; this
0x18009acf8  test    eax, eax
0x18009acfa  js      loc_18009AE74
0x18009ad00  mov     dl, 1
0x18009ad02  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler>::GetImpl(void)'::`2'::impl
0x18009ad09  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlightV2RestoreHandler>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009ad0e  mov     rax, [rbp+ppszPathOut]
0x18009ad12  mov     [rbp+var_38], rax
0x18009ad16  lea     rdx, [rbp+var_38]
0x18009ad1a  lea     rcx, [rbp+var_28]
0x18009ad1e  call    ??$?0PEAG$0A@@path@filesystem@std@@QEAA@AEBQEAGW4format@012@@Z; std::filesystem::path::path(ushort * const &,std::filesystem::path::format)
0x18009ad23  nop
0x18009ad24  lea     rcx, [rbp+var_28]; this
0x18009ad28  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x18009ad2d  mov     bl, al
0x18009ad2f  lea     rcx, [rbp+var_28]
0x18009ad33  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009ad38  test    bl, bl
0x18009ad3a  jz      short loc_18009AD71
0x18009ad3c  mov     r9d, 1; int
0x18009ad42  lea     r8, aThemerestored; "ThemeRestored"
0x18009ad49  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009ad50  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18009ad55  mov     rcx, [rbp+8]; this
0x18009ad59  test    eax, eax
0x18009ad5b  jns     short loc_18009AD71
0x18009ad5d  mov     r9d, eax; char *
0x18009ad60  lea     r8, aPcshellShellCl; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x18009ad67  mov     edx, 17Dh; void *
0x18009ad6c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009ad71  mov     r9, [rbp+ppszPathOut]; unsigned __int16 *
0x18009ad75  lea     r8, aCurrenttheme; "CurrentTheme"
0x18009ad7c  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009ad83  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18009ad88  mov     rcx, [rbp+8]; this
0x18009ad8c  test    eax, eax
0x18009ad8e  js      loc_18009AE5F
0x18009ad94  mov     dl, 1
0x18009ad96  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PersonalizationCustomThemeRestoreHandler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PersonalizationCustomThemeRestoreHandler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PersonalizationCustomThemeRestoreHandler> `wil::Feature<__WilFeatureTraits_Feature_PersonalizationCustomThemeRestoreHandler>::GetImpl(void)'::`2'::impl
0x18009ad9d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_PersonalizationCustomThemeRestoreHandler@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PersonalizationCustomThemeRestoreHandler>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009ada2  mov     r9, [rbp+ppszPathOut]; unsigned __int16 *
0x18009ada6  lea     r8, aRestoredinboxt; "RestoredInboxTheme"
0x18009adad  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009adb4  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18009adb9  test    eax, eax
0x18009adbb  jns     short loc_18009ADE5
0x18009adbd  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x18009adc4  jz      short loc_18009ADE0
0x18009adc6  lea     r9, aFailedToSetRes; "Failed to set RestoredInboxTheme"
0x18009adcd  lea     r8, aPersonalizatio_4; "Personalization Theme Restore"
0x18009add4  lea     rdx, InformationMessage
0x18009addb  call    McTemplateU0zz_EventWriteTransfer
0x18009ade0  call    ??$PersonalizationTheme_ApiActivity@AEAY0M@$$CBGAEAY0CN@$$CBGAEAY06$$CBG@PersonalizationThemeActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0CN@$$CBGAEAY06$$CBG@Z; CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_ApiActivity<ushort const (&)[12],ushort const (&)[45],ushort const (&)[7]>(ushort const (&)[12],ushort const (&)[45],ushort const (&)[7])
0x18009ade5  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x18009adec  jz      short loc_18009AE08
0x18009adee  lea     r9, aThemeRegistryS; "Theme Registry set successfully"
0x18009adf5  lea     r8, aPersonalizatio_4; "Personalization Theme Restore"
0x18009adfc  lea     rdx, InformationMessage
0x18009ae03  call    McTemplateU0zz_EventWriteTransfer
0x18009ae08  call    ??$PersonalizationTheme_ApiActivity@AEAY0M@$$CBGAEAY0CA@$$CBGAEAY07$$CBG@PersonalizationThemeActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0CA@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_ApiActivity<ushort const (&)[12],ushort const (&)[32],ushort const (&)[8]>(ushort const (&)[12],ushort const (&)[32],ushort const (&)[8])
0x18009ae0d  lea     rcx, [rdi+8]
0x18009ae11  lea     rdx, [rbp+var_38]
0x18009ae15  call    ?data@?$tip_test@V?$merged_data@U_tip_PersonalizationThemeRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeRestoreTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>>::data(void)
0x18009ae1a  mov     rcx, [rax]
0x18009ae1d  mov     byte ptr [rcx+111h], 1
0x18009ae24  lea     rcx, [rbp+var_38]
0x18009ae28  call    ??1?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeRestoreTipTest,_tip_PersonalizationThemeRestoreTipTest>>(void)
0x18009ae2d  nop
0x18009ae2e  lea     rcx, [rbp+pszPathIn]
0x18009ae32  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18009ae37  nop
0x18009ae38  lea     rcx, [rbp+ppszPathOut]
0x18009ae3c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18009ae41  mov     rcx, [rbp+var_8]
0x18009ae45  xor     rcx, rsp; StackCookie
0x18009ae48  call    __security_check_cookie
0x18009ae4d  lea     r11, [rsp+60h+var_s0]
0x18009ae52  mov     rbx, [r11+20h]
0x18009ae56  mov     rdi, [r11+28h]
0x18009ae5a  mov     rsp, r11
0x18009ae5d  pop     rbp
0x18009ae5e  retn
0x18009ae5f  mov     r9d, eax; char *
0x18009ae62  lea     r8, aPcshellShellCl; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x18009ae69  mov     edx, 180h; void *
0x18009ae6e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009ae74  mov     r9d, eax; char *
0x18009ae77  lea     r8, aPcshellShellCl; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x18009ae7e  mov     edx, 177h; void *
0x18009ae83  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
