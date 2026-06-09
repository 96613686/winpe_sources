# PersonalizationThemeBackupRestoreHandler::OnBackup(_GUID const &,char const *,wil::cloud_store)

- ea: `0x18009b7f0`
- end: `0x18009c36d`
- name: `?OnBackup@PersonalizationThemeBackupRestoreHandler@@UEAAXAEBU_GUID@@PEBDVcloud_store@wil@@@Z`
- size: `2941`
- prototype: ``
- caller_count: `0`
- callee_count: `58`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000c6e0`
- `0x18000d688`
- `0x180012470`
- `0x1800154e4`
- `0x180015668`
- `0x180015a58`
- `0x18001649c`
- `0x18001cf64`
- `0x18001cf84`
- `0x18001cfa4`
- `0x18001d0a8`
- `0x18001faa8`
- `0x1800225d4`
- `0x180022ef0`
- `0x180024084`
- `0x180027000`
- `0x180031774`
- `0x180031dc0`
- `0x180036a3c`
- `0x180044c14`
- `0x18004623c`
- `0x180096af4`
- `0x180097194`
- `0x1800974b0`
- `0x180097550`
- `0x1800977e8`
- `0x18009823c`
- `0x1800982e4`
- `0x18009838c`
- `0x180098434`
- `0x1800986d4`
- `0x180098760`
- `0x18009956c`
- `0x1800996b4`
- `0x180099910`
- `0x180099e80`
- `0x180099f78`
- `0x18009a528`
- `0x18009a550`
- `0x18009a694`
- `0x18009a6dc`
- `0x18009a75c`
- `0x18009aa30`
- `0x18009ae90`
- `0x18009b7a4`
- `0x18009b7f0`
- `0x18009c7f4`
- `0x18009c880`
- `0x18009c998`
- `0x18009cc4c`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18009ba17`
- `ADVAPI32!RegGetValueW` at `0x18009bc78`
- `ADVAPI32!RegGetValueW` at `0x18009bdba`
- `ADVAPI32!RegGetValueW` at `0x18009bf5d`
- `ADVAPI32!RegGetValueW` at `0x18009bfd7`
- `ADVAPI32!RegGetValueW` at `0x18009c036`
- `ADVAPI32!RegGetValueW` at `0x18009ba17`
- `ADVAPI32!RegGetValueW` at `0x18009bc78`
- `ADVAPI32!RegGetValueW` at `0x18009bdba`
- `ADVAPI32!RegGetValueW` at `0x18009bf5d`
- `ADVAPI32!RegGetValueW` at `0x18009bfd7`
- `ADVAPI32!RegGetValueW` at `0x18009c036`

## string_xrefs

- `0x18009ba50`: `Current theme path registry doesn't exist.`
- `0x18009bbe3`: `Schema Load Completed`
- `0x18009c2a8`: `Backup Completed`
- `0x18009c260`: `Schema save Completed`
- `0x18009b9a2`: `Failed to refresh current theme path`
- `0x18009bfc2`: `InstallTheme`
- `0x18009c021`: `InstallTheme`
- `0x18009c2b1`: `Personalization theme backup completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall PersonalizationThemeBackupRestoreHandler::OnBackup(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        wil::cloud_store *a4)
{
  char v5; // r14
  _QWORD *v6; // rax
  __int64 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rdx
  LSTATUS ValueW; // eax
  __int64 v14; // rcx
  unsigned __int64 v15; // r9
  char IsEnabled; // al
  const unsigned __int16 *v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  char v21; // dl
  int v22; // ecx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rcx
  const wchar_t *v28; // r9
  __int64 v29; // rax
  __int64 v30; // rbx
  const unsigned __int16 *v31; // rdx
  const unsigned __int16 *last_path_segment; // rax
  int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rcx
  const WCHAR *v37; // rax
  const unsigned __int16 *v38; // rdx
  const unsigned __int16 *v39; // rax
  LSTATUS v40; // eax
  const unsigned __int16 *v41; // rdx
  bool v42; // zf
  LSTATUS v43; // eax
  const unsigned __int16 *v44; // rdx
  bool v45; // sf
  LSTATUS v46; // eax
  bool v47; // sf
  __int64 v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rbx
  __int64 v51; // rcx
  __int64 ThemeTypeName; // rax
  __int64 v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // r8
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // rcx
  int v60; // eax
  int v61; // edx
  int v62; // ecx
  char v63; // al
  const unsigned __int16 *v64; // rdx
  __int64 v65; // rax
  int pdwType; // [rsp+20h] [rbp-E0h]
  __int64 v67; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v68; // [rsp+48h] [rbp-B8h] BYREF
  char v69; // [rsp+50h] [rbp-B0h]
  wil::cloud_store *v70; // [rsp+58h] [rbp-A8h]
  void **v71; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v72[48]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v73; // [rsp+98h] [rbp-68h]
  _BYTE v74[240]; // [rsp+A0h] [rbp-60h] BYREF
  DWORD pcbData[8]; // [rsp+190h] [rbp+90h] BYREF
  _OWORD v76[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v77; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v78[16]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v79; // [rsp+1E8h] [rbp+E8h]
  __int64 v80; // [rsp+1F8h] [rbp+F8h]
  int v81; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v82[16]; // [rsp+228h] [rbp+128h] BYREF
  __int64 v83; // [rsp+238h] [rbp+138h]
  __int64 v84; // [rsp+248h] [rbp+148h]
  unsigned __int8 v85; // [rsp+258h] [rbp+158h]
  _QWORD v86[42]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v87[264]; // [rsp+3C0h] [rbp+2C0h] BYREF
  WCHAR StringSource[264]; // [rsp+5D0h] [rbp+4D0h] BYREF
  _WORD pvData[264]; // [rsp+7E0h] [rbp+6E0h] BYREF
  _WORD v90[1568]; // [rsp+9F0h] [rbp+8F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1678h] [rbp+1578h]

  v70 = a4;
  v5 = 0;
  pcbData[0] = 0;
  LOBYTE(a3) = 3;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_PersonalizationThemeBackupHandler>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_PersonalizationThemeBackupHandler>::GetImpl'::`2'::impl,
    a2,
    a3);
  v67 = 0;
  wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v86);
  v86[0] = &CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::`vftable';
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::StartActivity(
      (CloudRestoreLauncherTelemetry::PersonalizationThemeActivity *)v86,
      L"Backup Started");
  v6 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::ensure_data(&v67);
  tip2::details::shared_data<0,0,0>::start(*v6 + 8LL, &v68);
  v7 = (__int64 *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::ensure_data(&v67);
  v71 = &tip2::test_watcher<tip2::details::merged_data<_tip_NightlightRestoreTipTest,_tip_NightlightRestoreTipTest>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v72,
    (struct wil::details::IFailureCallback *)&v71,
    0,
    1);
  v8 = *v7;
  v73 = v8;
  if ( v8 )
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 280));
  v68 = &v67;
  v69 = 1;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::StartActivity(
      (CloudRestoreLauncherTelemetry::PersonalizationThemeActivity *)v86,
      L"Personalization theme backup started");
  memset_0(StringSource, 0, 0x208u);
  memset_0(pvData, 0, 0x208u);
  LOBYTE(v9) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler>::GetImpl'::`2'::impl,
    v9);
  PersonalizationThemeBackupRestoreHandler::CreateThemeManager(v10, pcbData);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 208LL))(*(_QWORD *)pcbData)
    && (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    McTemplateU0zz_EventWriteTransfer(
      v11,
      &InformationMessage,
      L"Personalization Theme Backup",
      L"Failed to refresh current theme path");
  }
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(pcbData);
  LOBYTE(v12) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixTipFileNotFoundPersonalizationThemeBackupHandler>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_FixTipFileNotFoundPersonalizationThemeBackupHandler>::GetImpl'::`2'::impl,
    v12);
  pcbData[0] = 520;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
             L"CurrentTheme",
             2u,
             0,
             StringSource,
             pcbData);
  v15 = (unsigned int)ValueW;
  if ( ValueW )
  {
    StringSource[0] = 0;
    if ( ValueW > 0 )
      v15 = (unsigned __int16)ValueW | 0x80070000;
  }
  if ( (_DWORD)v15 == -2147024894 )
  {
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        v14,
        &InformationMessage,
        L"Personalization Theme Backup",
        L"Current theme path registry doesn't exist.");
    CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[38],unsigned short const (&)[7]>();
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(
                            &v67,
                            pcbData)
             + 274LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(pcbData);
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(
                            &v67,
                            pcbData)
             + 272LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(pcbData);
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(
                            &v67,
                            pcbData)
             + 275LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(pcbData);
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(
                            &v67,
                            pcbData)
             + 273LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(pcbData);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl);
    v17 = L"Backup Exited - Personalization theme backup failed";
    if ( !IsEnabled )
      v17 = L"Personalization theme backup failed";
    CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::Stop(
      (CloudRestoreLauncherTelemetry::PersonalizationThemeActivity *)v86,
      v17);
    goto LABEL_94;
  }
  if ( (v15 & 0x80000000) != 0LL )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\personalizationthemebackuprestorehandler.cpp",
      (const char *)v15,
      pdwType);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(
                          &v67,
                          pcbData)
           + 274LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(pcbData);
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    McTemplateU0zz_EventWriteTransfer(
      v18,
      &InformationMessage,
      L"Personalization Theme Backup",
      L"Current theme name retrieved successfully from registries.");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[45],unsigned short const (&)[8]>();
  wil::cloud_store::load<Windows::Data::PersonalizationThemes::Theme>(a4, &v81, 2);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(
                          &v67,
                          pcbData)
           + 272LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(pcbData);
  CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[22]>(
    v19,
    L"Schema Load Completed");
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    v20 = std::_String_val<std::_Simple_types<char>>::_Myptr(
            &Windows::Data::PersonalizationThemes::Theme::Schema::metadata,
            v85);
    McTemplateU0sxt_EventWriteTransfer(v22, (unsigned int)&CloudDataLoaded, v20, v84, v21);
  }
  wil::cloud_store_data<Windows::Data::PersonalizationThemes::Theme>::cloud_store_data<Windows::Data::PersonalizationThemes::Theme>(
    &v77,
    &v81);
  pcbData[0] = 520;
  v23 = RegGetValueW(HKEY_CURRENT_USER, L"Control Panel\\Appearance", L"Current", 2u, 0, pvData, pcbData);
  if ( v23 )
  {
    pvData[0] = 0;
    if ( v23 > 0 )
      v23 = (unsigned __int16)v23 | 0x80070000;
  }
  v25 = -1;
  if ( !v23 )
  {
    v26 = -1;
    do
      ++v26;
    while ( pvData[v26] );
    if ( v26 )
    {
      v77 = 1;
      std::wstring::_Assign<unsigned short>(v78, &word_1801382A0, 0);
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(
                              &v67,
                              pcbData)
               + 275LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(pcbData);
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      {
        v28 = L"Current theme is high contrast theme.";
LABEL_71:
        McTemplateU0zz_EventWriteTransfer(v27, &InformationMessage, L"Personalization Theme Backup", v28);
        goto LABEL_72;
      }
      goto LABEL_72;
    }
  }
  v77 = 0;
  LOBYTE(v24) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler>::ReportUsage(
    &`wil::Feature<__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler>::GetImpl'::`2'::impl,
    v24);
  v29 = std::wstring::wstring(v76, StringSource);
  v30 = std::wstring::find(v29, L"AppData");
  std::wstring::_Tidy_deallocate(v76);
  if ( v30 == -1 )
  {
    last_path_segment = wil::find_last_path_segment(StringSource, v31);
    do
      ++v25;
    while ( last_path_segment[v25] );
LABEL_68:
    std::wstring::_Assign<unsigned short>(v78, last_path_segment, v25);
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(
                            &v67,
                            pcbData)
             + 275LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(pcbData);
    goto LABEL_69;
  }
  pcbData[0] = 3132;
  v33 = RegGetValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
          L"ThemeMRU",
          2u,
          0,
          v90,
          pcbData);
  if ( v33 )
  {
    v90[0] = 0;
    if ( v33 > 0 )
      v33 = (unsigned __int16)v33 | 0x80070000;
  }
  if ( v33 )
  {
    pcbData[0] = 520;
    v40 = RegGetValueW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
            L"RestoredInboxTheme",
            2u,
            0,
            v87,
            pcbData);
    v42 = v40 == 0;
    if ( !v40 )
      goto LABEL_54;
    v87[0] = 0;
    if ( v40 > 0 )
      v42 = 0;
    if ( !v42 )
    {
      pcbData[0] = 520;
      v43 = RegGetValueW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
              L"InstallTheme",
              2u,
              0,
              v87,
              pcbData);
      v45 = v43 < 0;
      if ( v43 )
      {
        v87[0] = 0;
        if ( v43 > 0 )
          v45 = 1;
      }
      if ( v45 )
      {
        pcbData[0] = 520;
        v46 = RegGetValueW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes",
                L"InstallTheme",
                2u,
                0,
                v87,
                pcbData);
        v47 = v46 < 0;
        if ( v46 )
        {
          v87[0] = 0;
          if ( v46 > 0 )
            v47 = 1;
        }
        if ( v47 )
          StringCchCopyW(v87, 0x104u, L"%ResourceDir%\\Themes\\aero.theme");
      }
      last_path_segment = wil::find_last_path_segment(v87, v44);
      do
        ++v25;
      while ( last_path_segment[v25] );
    }
    else
    {
LABEL_54:
      last_path_segment = wil::find_last_path_segment(v87, v41);
      do
        ++v25;
      while ( last_path_segment[v25] );
    }
    goto LABEL_68;
  }
  std::wstring::wstring(pcbData, v90);
  std::basic_istringstream<unsigned short>::basic_istringstream<unsigned short>(v74, pcbData);
  std::wstring::_Tidy_deallocate(pcbData);
  v76[0] = 0;
  v76[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v76[0]) = 0;
  std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v74, v76);
  v34 = std::wstring::wstring(pcbData, v76);
  v35 = std::wstring::find(v34, L"AppData");
  std::wstring::_Tidy_deallocate(pcbData);
  if ( v35 != -1 )
  {
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        v36,
        &InformationMessage,
        L"Personalization Theme Backup",
        L"ThemeMRU doesn't have last inbox theme.");
    CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[42],unsigned short const (&)[7]>();
  }
  v37 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v76);
  v39 = wil::find_last_path_segment(v37, v38);
  do
    ++v25;
  while ( v39[v25] );
  std::wstring::_Assign<unsigned short>(v78, v39, v25);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(
                          &v67,
                          pcbData)
           + 275LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(pcbData);
  std::wstring::_Tidy_deallocate(v76);
  std::basic_istringstream<unsigned short>::`vbase destructor'(v74);
LABEL_69:
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    v28 = L"Current theme is personalization theme.";
    goto LABEL_71;
  }
LABEL_72:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[32],unsigned short const (&)[8]>();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_BRCLogImprovements>::GetImpl'::`2'::impl) )
  {
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      v50 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v78);
      ThemeTypeName = PersonalizationThemeBackupRestoreHandler::GetThemeTypeName(v51, v76, &v77);
      v5 = 1;
      v53 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ThemeTypeName);
      McTemplateU0zz_EventWriteTransfer(v54, &BackupAssociatedPersonalizationThemeCloudFileNew, v53, v50);
    }
    if ( (v5 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v76);
  }
  else if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    v48 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v78);
    McTemplateU0xz_EventWriteTransfer(v49, &BackupAssociatedPersonalizationThemeCloudFile, v77, v48);
  }
  if ( v81 == v77
    && (std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v78),
        v55 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v82),
        (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v55, v83, v56, v79)) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_BRCLogImprovements>::GetImpl'::`2'::impl)
      && (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v57, &CloudDataSkipSave, L"Personalization Theme Backup");
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
      CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[21]>();
    wil::cloud_store::save<Windows::Data::PersonalizationThemes::Theme>(a4, pcbData, &v77);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      v60 = std::_String_val<std::_Simple_types<char>>::_Myptr(
              &Windows::Data::PersonalizationThemes::Theme::Schema::metadata,
              v58);
      McTemplateU0sxx_EventWriteTransfer(v62, v61, v60, v80, pcbData[0]);
    }
    CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[22]>(
      v59,
      L"Schema save Completed");
  }
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(
                          &v67,
                          pcbData)
           + 273LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(pcbData);
  v63 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl);
  v64 = L"Backup Completed";
  if ( !v63 )
    v64 = L"Personalization theme backup completed";
  CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::Stop(
    (CloudRestoreLauncherTelemetry::PersonalizationThemeActivity *)v86,
    v64);
  wil::cloud_store_data<Windows::Data::PersonalizationThemes::Theme>::~cloud_store_data<Windows::Data::PersonalizationThemes::Theme>(&v77);
  wil::cloud_store_data<Windows::Data::PersonalizationThemes::Theme>::~cloud_store_data<Windows::Data::PersonalizationThemes::Theme>(&v81);
LABEL_94:
  v65 = tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(
          &v67,
          pcbData);
  tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::close(v65);
  tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(pcbData);
  if ( v67 )
    tip2::details::shared_data<0,0,0>::complete_without_lock(v67 + 8);
  tip2::test_watcher<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_watcher<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(&v71);
  CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::~PersonalizationThemeActivity((CloudRestoreLauncherTelemetry::PersonalizationThemeActivity *)v86);
  wil::com_ptr_t<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>,wil::err_returncode_policy>(&v67);
  wil::cloud_store::~cloud_store(a4);
}

```

## disassembly

```asm
0x18009b7f0  push    rbp
0x18009b7f2  push    rbx
0x18009b7f3  push    rsi
0x18009b7f4  push    rdi
0x18009b7f5  push    r14
0x18009b7f7  push    r15
0x18009b7f9  lea     rbp, [rsp-1548h]
0x18009b801  mov     eax, 1648h
0x18009b806  call    _alloca_probe
0x18009b80b  sub     rsp, rax
0x18009b80e  mov     rax, cs:__security_cookie
0x18009b815  xor     rax, rsp
0x18009b818  mov     [rbp+1570h+var_40], rax
0x18009b81f  mov     rsi, r9
0x18009b822  mov     [rsp+1670h+var_1618], r9
0x18009b827  xor     r15d, r15d
0x18009b82a  mov     r14d, r15d
0x18009b82d  mov     [rbp+1570h+var_14E0], r15d
0x18009b834  mov     r8b, 3
0x18009b837  mov     dl, 1
0x18009b839  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PersonalizationThemeBackupHandler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PersonalizationThemeBackupHandler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PersonalizationThemeBackupHandler> `wil::Feature<__WilFeatureTraits_Feature_PersonalizationThemeBackupHandler>::GetImpl(void)'::`2'::impl
0x18009b840  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_PersonalizationThemeBackupHandler@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PersonalizationThemeBackupHandler>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009b845  mov     [rsp+1670h+var_1630], r15
0x18009b84a  lea     rdx, aPersonalizatio; "PersonalizationThemeActivity"
0x18009b851  lea     rcx, [rbp+1570h+var_1400]; struct wil::details::IFailureCallback *
0x18009b858  call    ??0?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18009b85d  lea     rax, ??_7PersonalizationThemeActivity@CloudRestoreLauncherTelemetry@@6B@; const CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::`vftable'
0x18009b864  mov     [rbp+1570h+var_1400], rax
0x18009b86b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x18009b872  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x18009b877  test    al, al
0x18009b879  jz      short loc_18009B88E
0x18009b87b  lea     rdx, aBackupStarted; "Backup Started"
0x18009b882  lea     rcx, [rbp+1570h+var_1400]; this
0x18009b889  call    ?StartActivity@PersonalizationThemeActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::StartActivity(ushort const *)
0x18009b88e  mov     rcx, [rsp+1670h+var_1630]
0x18009b893  test    rcx, rcx
0x18009b896  jz      short loc_18009B8AF
0x18009b898  add     rcx, 8
0x18009b89c  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x18009b8a1  test    al, al
0x18009b8a3  jz      short loc_18009B8AF
0x18009b8a5  lea     rcx, [rsp+1670h+var_1630]
0x18009b8aa  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>,wil::err_returncode_policy>::reset(void)
0x18009b8af  lea     rcx, [rsp+1670h+var_1630]
0x18009b8b4  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::ensure_data(void)
0x18009b8b9  mov     rcx, [rax]
0x18009b8bc  add     rcx, 8
0x18009b8c0  lea     rdx, [rsp+1670h+var_1628]
0x18009b8c5  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18009b8ca  lea     rcx, [rsp+1670h+var_1630]
0x18009b8cf  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::ensure_data(void)
0x18009b8d4  mov     rbx, rax
0x18009b8d7  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_NightlightRestoreTipTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_NightlightRestoreTipTest,_tip_NightlightRestoreTipTest>>::`vftable'
0x18009b8de  mov     [rsp+1670h+var_1610], rax
0x18009b8e3  mov     r9b, 1; bool
0x18009b8e6  xor     r8d, r8d; struct wil::CallContextInfo *
0x18009b8e9  lea     rdx, [rsp+1670h+var_1610]; struct wil::details::IFailureCallback *
0x18009b8ee  lea     rcx, [rsp+1670h+var_1608]; this
0x18009b8f3  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18009b8f8  mov     rax, [rbx]
0x18009b8fb  mov     [rbp+1570h+var_15D8], rax
0x18009b8ff  test    rax, rax
0x18009b902  jz      short loc_18009B90B
0x18009b904  lock inc dword ptr [rax+118h]
0x18009b90b  lea     rax, [rsp+1670h+var_1630]
0x18009b910  mov     [rsp+1670h+var_1628], rax
0x18009b915  mov     [rsp+1670h+var_1620], 1
0x18009b91a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x18009b921  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x18009b926  test    al, al
0x18009b928  jnz     short loc_18009B93D
0x18009b92a  lea     rdx, aPersonalizatio_3; "Personalization theme backup started"
0x18009b931  lea     rcx, [rbp+1570h+var_1400]; this
0x18009b938  call    ?StartActivity@PersonalizationThemeActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::StartActivity(ushort const *)
0x18009b93d  mov     ebx, 208h
0x18009b942  mov     r8d, ebx; Size
0x18009b945  xor     edx, edx; Val
0x18009b947  lea     rcx, [rbp+1570h+StringSource]; void *
0x18009b94e  call    memset_0
0x18009b953  mov     r8d, ebx; Size
0x18009b956  xor     edx, edx; Val
0x18009b958  lea     rcx, [rbp+1570h+var_E90]; void *
0x18009b95f  call    memset_0
0x18009b964  mov     dl, 1
0x18009b966  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler> `wil::Feature<__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler>::GetImpl(void)'::`2'::impl
0x18009b96d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009b972  lea     rdx, [rbp+1570h+var_14E0]
0x18009b979  call    ?CreateThemeManager@PersonalizationThemeBackupRestoreHandler@@AEAA?AV?$com_ptr_t@UIThemeManager2@@Uerr_exception_policy@wil@@@wil@@XZ; PersonalizationThemeBackupRestoreHandler::CreateThemeManager(void)
0x18009b97e  nop
0x18009b97f  mov     rcx, qword ptr [rbp+1570h+var_14E0]
0x18009b986  mov     rax, [rcx]
0x18009b989  mov     rax, [rax+0D0h]
0x18009b990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b995  test    eax, eax
0x18009b997  jz      short loc_18009B9BD
0x18009b999  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x18009b9a0  jz      short loc_18009B9BD
0x18009b9a2  lea     r9, aFailedToRefres; "Failed to refresh current theme path"
0x18009b9a9  lea     r8, aPersonalizatio_7; "Personalization Theme Backup"
0x18009b9b0  lea     rdx, InformationMessage
0x18009b9b7  call    McTemplateU0zz_EventWriteTransfer
0x18009b9bc  nop
0x18009b9bd  lea     rcx, [rbp+1570h+var_14E0]
0x18009b9c4  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x18009b9c9  mov     dl, 1
0x18009b9cb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixTipFileNotFoundPersonalizationThemeBackupHandler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixTipFileNotFoundPersonalizationThemeBackupHandler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixTipFileNotFoundPersonalizationThemeBackupHandler> `wil::Feature<__WilFeatureTraits_Feature_FixTipFileNotFoundPersonalizationThemeBackupHandler>::GetImpl(void)'::`2'::impl
0x18009b9d2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_FixTipFileNotFoundPersonalizationThemeBackupHandler@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixTipFileNotFoundPersonalizationThemeBackupHandler>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009b9d7  mov     [rbp+1570h+var_14E0], ebx
0x18009b9dd  lea     rax, [rbp+1570h+var_14E0]
0x18009b9e4  mov     [rsp+1670h+pcbData], rax; pcbData
0x18009b9e9  lea     rax, [rbp+1570h+StringSource]
0x18009b9f0  mov     [rsp+1670h+pvData], rax; pvData
0x18009b9f5  mov     [rsp+1670h+pdwType], r15; int
0x18009b9fa  mov     edi, 2
0x18009b9ff  mov     r9d, edi; dwFlags
0x18009ba02  lea     r8, aCurrenttheme; "CurrentTheme"
0x18009ba09  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009ba10  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18009ba17  call    cs:__imp_RegGetValueW
0x18009ba1d  mov     r9d, eax
0x18009ba20  mov     ebx, 80070000h
0x18009ba25  test    eax, eax
0x18009ba27  jz      short loc_18009BA3A
0x18009ba29  mov     [rbp+1570h+StringSource], r15w
0x18009ba31  jle     short loc_18009BA3A
0x18009ba33  movzx   r9d, ax
0x18009ba37  or      r9d, ebx; char *
0x18009ba3a  cmp     r9d, 80070002h
0x18009ba41  jnz     loc_18009BB3A
0x18009ba47  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x18009ba4e  jz      short loc_18009BA6A
0x18009ba50  lea     r9, aCurrentThemePa; "Current theme path registry doesn't exi"...
0x18009ba57  lea     r8, aPersonalizatio_7; "Personalization Theme Backup"
0x18009ba5e  lea     rdx, InformationMessage
0x18009ba65  call    McTemplateU0zz_EventWriteTransfer
0x18009ba6a  call    ??$PersonalizationTheme_ApiActivity@AEAY0L@$$CBGAEAY0CG@$$CBGAEAY06$$CBG@PersonalizationThemeActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0CG@$$CBGAEAY06$$CBG@Z; CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_ApiActivity<ushort const (&)[11],ushort const (&)[38],ushort const (&)[7]>(ushort const (&)[11],ushort const (&)[38],ushort const (&)[7])
0x18009ba6f  lea     rdx, [rbp+1570h+var_14E0]
0x18009ba76  lea     rcx, [rsp+1670h+var_1630]
0x18009ba7b  call    ?data@?$tip_test@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(void)
0x18009ba80  mov     rcx, [rax]
0x18009ba83  mov     byte ptr [rcx+112h], 1
0x18009ba8a  lea     rcx, [rbp+1570h+var_14E0]
0x18009ba91  call    ??1?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(void)
0x18009ba96  lea     rdx, [rbp+1570h+var_14E0]
0x18009ba9d  lea     rcx, [rsp+1670h+var_1630]
0x18009baa2  call    ?data@?$tip_test@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(void)
0x18009baa7  mov     rcx, [rax]
0x18009baaa  mov     byte ptr [rcx+110h], 1
0x18009bab1  lea     rcx, [rbp+1570h+var_14E0]
0x18009bab8  call    ??1?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(void)
0x18009babd  lea     rdx, [rbp+1570h+var_14E0]
0x18009bac4  lea     rcx, [rsp+1670h+var_1630]
0x18009bac9  call    ?data@?$tip_test@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(void)
0x18009bace  mov     rcx, [rax]
0x18009bad1  mov     byte ptr [rcx+113h], 1
0x18009bad8  lea     rcx, [rbp+1570h+var_14E0]
0x18009badf  call    ??1?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(void)
0x18009bae4  lea     rdx, [rbp+1570h+var_14E0]
0x18009baeb  lea     rcx, [rsp+1670h+var_1630]
0x18009baf0  call    ?data@?$tip_test@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(void)
0x18009baf5  mov     rcx, [rax]
0x18009baf8  mov     byte ptr [rcx+111h], 1
0x18009baff  lea     rcx, [rbp+1570h+var_14E0]
0x18009bb06  call    ??1?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(void)
0x18009bb0b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x18009bb12  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x18009bb17  lea     rcx, [rbp+1570h+var_1400]; this
0x18009bb1e  test    al, al
0x18009bb20  lea     rdx, aBackupExitedPe; "Backup Exited - Personalization theme b"...
0x18009bb27  jnz     short loc_18009BB30
0x18009bb29  lea     rdx, aPersonalizatio_2; "Personalization theme backup failed"
0x18009bb30  call    ?Stop@PersonalizationThemeActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::Stop(ushort const *)
0x18009bb35  jmp     loc_18009C2D8
0x18009bb3a  mov     rcx, [rbp+1578h]; this
0x18009bb41  test    r9d, r9d
0x18009bb44  js      loc_18009C35B
0x18009bb4a  lea     rdx, [rbp+1570h+var_14E0]
0x18009bb51  lea     rcx, [rsp+1670h+var_1630]
0x18009bb56  call    ?data@?$tip_test@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(void)
0x18009bb5b  mov     rcx, [rax]
0x18009bb5e  mov     byte ptr [rcx+112h], 1
0x18009bb65  lea     rcx, [rbp+1570h+var_14E0]
0x18009bb6c  call    ??1?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(void)
0x18009bb71  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x18009bb78  jz      short loc_18009BB94
0x18009bb7a  lea     r9, aCurrentThemeNa; "Current theme name retrieved successful"...
0x18009bb81  lea     r8, aPersonalizatio_7; "Personalization Theme Backup"
0x18009bb88  lea     rdx, InformationMessage
0x18009bb8f  call    McTemplateU0zz_EventWriteTransfer
0x18009bb94  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x18009bb9b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x18009bba0  test    al, al
0x18009bba2  jz      short loc_18009BBA9
0x18009bba4  call    ??$PersonalizationTheme_ApiActivity@AEAY0L@$$CBGAEAY0CN@$$CBGAEAY07$$CBG@PersonalizationThemeActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0CN@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_ApiActivity<ushort const (&)[11],ushort const (&)[45],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[45],ushort const (&)[8])
0x18009bba9  mov     r8d, edi
0x18009bbac  lea     rdx, [rbp+1570h+var_1450]
0x18009bbb3  mov     rcx, rsi
0x18009bbb6  call    ??$load@UTheme@PersonalizationThemes@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UTheme@PersonalizationThemes@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::PersonalizationThemes::Theme>(wil::cloud_store_load_options,char const *)
0x18009bbbb  nop
0x18009bbbc  lea     rdx, [rbp+1570h+var_14E0]
0x18009bbc3  lea     rcx, [rsp+1670h+var_1630]
0x18009bbc8  call    ?data@?$tip_test@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(void)
0x18009bbcd  mov     rcx, [rax]
0x18009bbd0  mov     byte ptr [rcx+110h], 1
0x18009bbd7  lea     rcx, [rbp+1570h+var_14E0]
0x18009bbde  call    ??1?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(void)
0x18009bbe3  lea     rdx, aSchemaLoadComp_0; "Schema Load Completed"
0x18009bbea  call    ??$PersonalizationTheme_BondSchemaActivity@AEAY06$$CBGAEAY0BG@$$CBG@PersonalizationThemeActivity@CloudRestoreLauncherTelemetry@@SAXAEAY06$$CBGAEAY0BG@$$CBG@Z; CloudRestoreLauncherTelemetry::PersonalizationThemeActivity::PersonalizationTheme_BondSchemaActivity<ushort const (&)[7],ushort const (&)[22]>(ushort const (&)[7],ushort const (&)[22])
0x18009bbef  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x18009bbf6  jz      short loc_18009BC25
0x18009bbf8  movzx   edx, [rbp+1570h+var_1418]
0x18009bbff  lea     rcx, ?metadata@Schema@Theme@PersonalizationThemes@Data@Windows@@2UMetadata@bond@@B; bond::Metadata const Windows::Data::PersonalizationThemes::Theme::Schema::metadata
0x18009bc06  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18009bc0b  mov     r8, rax
0x18009bc0e  mov     dword ptr [rsp+1670h+pdwType], edx
0x18009bc12  mov     r9, [rbp+1570h+var_1428]
0x18009bc19  lea     rdx, CloudDataLoaded
0x18009bc20  call    McTemplateU0sxt_EventWriteTransfer
0x18009bc25  lea     rdx, [rbp+1570h+var_1450]
0x18009bc2c  lea     rcx, [rbp+1570h+var_14A0]
0x18009bc33  call    ??0?$cloud_store_data@UTheme@PersonalizationThemes@Data@Windows@@@wil@@QEAA@AEBV01@@Z; wil::cloud_store_data<Windows::Data::PersonalizationThemes::Theme>::cloud_store_data<Windows::Data::PersonalizationThemes::Theme>(wil::cloud_store_data<Windows::Data::PersonalizationThemes::Theme> const &)
0x18009bc38  nop
0x18009bc39  mov     [rbp+1570h+var_14E0], 208h
0x18009bc43  lea     rax, [rbp+1570h+var_14E0]
0x18009bc4a  mov     [rsp+1670h+pcbData], rax; pcbData
0x18009bc4f  lea     rax, [rbp+1570h+var_E90]
0x18009bc56  mov     [rsp+1670h+pvData], rax; pvData
0x18009bc5b  mov     [rsp+1670h+pdwType], r15; pdwType
0x18009bc60  mov     r9d, edi; dwFlags
0x18009bc63  lea     r8, aCurrent; "Current"
0x18009bc6a  lea     rdx, aControlPanelAp; "Control Panel\\Appearance"
0x18009bc71  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18009bc78  call    cs:__imp_RegGetValueW
0x18009bc7e  test    eax, eax
0x18009bc80  jz      short loc_18009BC91
0x18009bc82  mov     [rbp+1570h+var_E90], r15w
0x18009bc8a  jle     short loc_18009BC91
0x18009bc8c  movzx   eax, ax
0x18009bc8f  or      eax, ebx
0x18009bc91  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009bc95  test    eax, eax
0x18009bc97  jnz     short loc_18009BD12
0x18009bc99  lea     rcx, [rbp+1570h+var_E90]
0x18009bca0  mov     rax, rdi
0x18009bca3  inc     rax
0x18009bca6  cmp     [rcx+rax*2], r15w
0x18009bcab  jnz     short loc_18009BCA3
0x18009bcad  test    rax, rax
0x18009bcb0  jz      short loc_18009BD12
0x18009bcb2  mov     [rbp+1570h+var_14A0], 1
0x18009bcbc  xor     r8d, r8d
0x18009bcbf  lea     rdx, word_1801382A0
0x18009bcc6  lea     rcx, [rbp+1570h+var_1498]
0x18009bccd  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18009bcd2  lea     rdx, [rbp+1570h+var_14E0]
0x18009bcd9  lea     rcx, [rsp+1670h+var_1630]
0x18009bcde  call    ?data@?$tip_test@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::data(void)
0x18009bce3  mov     rcx, [rax]
0x18009bce6  mov     byte ptr [rcx+113h], 1
0x18009bced  lea     rcx, [rbp+1570h+var_14E0]
0x18009bcf4  call    ??1?$test_data_control@V?$merged_data@U_tip_PersonalizationThemeBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_PersonalizationThemeBackupTipTest,_tip_PersonalizationThemeBackupTipTest>>(void)
0x18009bcf9  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x18009bd00  jz      loc_18009C0DD
0x18009bd06  lea     r9, aCurrentThemeIs; "Current theme is high contrast theme."
0x18009bd0d  jmp     loc_18009C0CA
0x18009bd12  mov     [rbp+1570h+var_14A0], r15d
0x18009bd19  mov     dl, 1
0x18009bd1b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler> `wil::Feature<__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler>::GetImpl(void)'::`2'::impl
0x18009bd22  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PersonalizationCustomThemeBackupHandler>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009bd27  lea     rdx, [rbp+1570h+StringSource]
0x18009bd2e  lea     rcx, [rbp+1570h+var_14C0]
0x18009bd35  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009bd3a  lea     rdx, aAppdata; "AppData"
0x18009bd41  mov     rcx, rax
0x18009bd44  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18009bd49  mov     rbx, rax
0x18009bd4c  lea     rcx, [rbp+1570h+var_14C0]
0x18009bd53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009bd58  cmp     rbx, rdi
0x18009bd5b  jnz     short loc_18009BD78
0x18009bd5d  lea     rcx, [rbp+1570h+StringSource]; lpStringSource
0x18009bd64  call    ?find_last_path_segment@wil@@YAPEBGPEBG@Z; wil::find_last_path_segment(ushort const *)
0x18009bd69  inc     rdi
0x18009bd6c  cmp     [rax+rdi*2], r15w
0x18009bd71  jnz     short loc_18009BD69
0x18009bd73  jmp     loc_18009C081
0x18009bd78  mov     [rbp+1570h+var_14E0], 0C3Ch
0x18009bd82  lea     rax, [rbp+1570h+var_14E0]
0x18009bd89  mov     [rsp+1670h+pcbData], rax; pcbData
0x18009bd8e  lea     rax, [rbp+1570h+var_C80]
0x18009bd95  mov     [rsp+1670h+pvData], rax; pvData
0x18009bd9a  mov     [rsp+1670h+pdwType], r15; pdwType
0x18009bd9f  mov     r9d, 2; dwFlags
0x18009bda5  lea     r8, aThememru; "ThemeMRU"
0x18009bdac  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18009bdb3  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18009bdba  call    cs:__imp_RegGetValueW
0x18009bdc0  test    eax, eax
0x18009bdc2  jz      short loc_18009BDDA
  ... truncated ...
```
