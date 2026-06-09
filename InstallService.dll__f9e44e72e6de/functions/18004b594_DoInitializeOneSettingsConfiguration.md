# DoInitializeOneSettingsConfiguration

- ea: `0x18004b594`
- end: `0x18004c104`
- name: `DoInitializeOneSettingsConfiguration`
- size: `2928`
- prototype: ``
- caller_count: `1`
- callee_count: `49`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004c1c0`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x1800127c8`
- `0x18001c108`
- `0x18001c414`
- `0x18001c964`
- `0x1800252e8`
- `0x18002ec4c`
- `0x1800321d4`
- `0x180034328`
- `0x180034f04`
- `0x180034ffc`
- `0x180035e74`
- `0x1800362f8`
- `0x180037914`
- `0x180042dcc`
- `0x180042ec0`
- `0x180043410`
- `0x180043a70`
- `0x180043bb4`
- `0x1800444b8`
- `0x1800445f0`
- `0x180044794`
- `0x180044b48`
- `0x180044bc0`
- `0x180044c3c`
- `0x180044c7c`
- `0x180044cf4`
- `0x180044d30`
- `0x180044d6c`
- `0x180044da8`
- `0x180044de4`
- `0x180044e20`
- `0x180044e5c`
- `0x180044e98`
- `0x180044f10`
- `0x180044f4c`
- `0x180044f88`
- `0x180044fc4`
- `0x180045000`
- `0x18004503c`
- `0x180045078`
- `0x1800450b4`
- `0x1800450f0`
- `0x180045294`
- `0x1800452d0`
- `0x180045838`
- `0x18004b594`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18004bb56`

## string_xrefs

- `0x18004b778`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18004c0a5`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18004b6df`: `SYSTEMCOMPONENTLIST`
- `0x18004b6f7`: `MANDATORYUPDATEALLOWED`
- `0x18004b87b`: `MSIXVCARMSUPPORTENABLED`
- `0x18004baa9`: `INTERACTIVEALLOWLISTUPDATE`
- `0x18004bac1`: `INTERACTIVEDISALLOWLISTUPDATE`
- `0x18004b8c3`: `BACKGROUNDUPDATECALLERLIST`
- `0x18004b990`: `IMMEDIATERETRYINSTALLERRORLIST`
- `0x18004b9b8`: `IMMEDIATERETRYINSTALLERRORLIST`
- `0x18004b9d5`: `IMMEDIATERETRYINSTALLDELAYINMILLISECONDS`
- `0x18004ba15`: `PRESEARCHUPDATEPACKAGEENABLED`
- `0x18004ba59`: `DISABLEWUUPDATEID`
- `0x18004bebc`: `ENABLEREPORTPROGRESSWHENDOWNLOADSIZEREADY`
- `0x18004bee4`: `FRAMEWORKPREUPDATEERRORLIST`
- `0x18004bf0c`: `FIXINSTALLUNDERSYSTEMCONTEXT`
- `0x18004c000`: `UPDATEBLOCKLISTBYPFN`
- `0x18004b645`: `SCCINSTALLSVC`
- `0x18004bbf1`: `CATALOGCACHEITEMSTALETHRESHOLDINHOURS`
- `0x18004bc28`: `CATALOGCACHEITEMSTALETHRESHOLDINHOURS`
- `0x18004bc1f`: `CATALOGCACHEITEMDELETETHRESHOLDINHOURS`
- `0x18004bd60`: `Error while reading DirectDownloadEnablementState from OneSettings cache, value will remain Disabled`
- `0x18004bd9c`: `Error while reading DirectDownloadEnablementSettings from OneSettings cache, value will remain empty`
- `0x18004bdd8`: `Error while reading DirectDownloadEnablementLiveCheckThreshold from OneSettings cache, value will remain 15 mins`
- `0x18004be14`: `Error while reading ProductCatalogUrl from OneSettings cache, value will remain default`
- `0x18004bfc1`: `Error while reading CheckpointAbandonmentRules from OneSettings cache, value will remain empty`
- `0x18004bf75`: `Error while reading SfEdgeFallbackEndpointUrl from OneSettings cache, value will remain default`
- `0x18004c037`: `Successfully loaded update block list from OneSettings: %s`
- `0x18004c059`: `Update block list not found or empty in OneSettings`
- `0x18004c084`: `Error %x while retrieving OneSettings values during one-time initialization, values will remain default.`
- `0x18004b768`: `DoInitializeOneSettingsConfiguration`
- `0x18004c098`: `DoInitializeOneSettingsConfiguration`
- `0x18004c0f2`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 DoInitializeOneSettingsConfiguration()
{
  int v0; // eax
  __int64 v1; // rdi
  __int64 (__fastcall *v2)(__int64, unsigned __int64, struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload **); // rbx
  wil *v3; // rcx
  int v4; // r9d
  __int64 v5; // rax
  int v6; // r9d
  int v7; // r9d
  int v8; // r9d
  int v9; // r9d
  int v10; // r9d
  _QWORD *v11; // rax
  int v12; // r9d
  HSTRING_HEADER *p_hstringHeader; // rdx
  void *Reserved1; // rdx
  const char *v15; // r9
  char IsEnabled; // al
  const WCHAR *v17; // rdx
  int v18; // r9d
  int v19; // r9d
  const char *v21; // r9
  __int64 v22; // [rsp+40h] [rbp-98h]
  struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *v23; // [rsp+50h] [rbp-88h] BYREF
  int v24; // [rsp+58h] [rbp-80h] BYREF
  __int64 v25; // [rsp+60h] [rbp-78h] BYREF
  __int64 v26; // [rsp+68h] [rbp-70h] BYREF
  __int64 v27; // [rsp+70h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-60h] BYREF
  unsigned __int64 v29; // [rsp+90h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v24 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::GetImpl'::`2'::impl) )
    byte_1802E4F42 = 1;
  v25 = 0;
  v23 = 0;
  v29 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
    0x3Au,
    0x39u);
  v0 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(
         v29,
         &v25);
  if ( v0 >= 0 )
  {
    v1 = v25;
    v2 = *(__int64 (__fastcall **)(__int64, unsigned __int64, struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload **))(*(_QWORD *)v25 + 48LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v23);
    v29 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SCCINSTALLSVC", 0xEu, 0xDu);
    try
    {
      v0 = v2(v1, v29, &v23);
    }
    catch ( ... )
    {
      v24 = wil::ResultFromCaughtException(v3);
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x89D,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        v21);
      v0 = v24;
    }
  }
  if ( v0 >= 0 && v23 )
  {
    _GetOneSettingsNumberValue<__int64>(v23, L"QUEUESTUCKTHRESHOLDINSECONDS", &qword_1802CA678, 1);
    _GetOneSettingsBooleanValue(v23, L"DISABLEUSOSTOREPROVIDER", &byte_1802E4F5D);
    _GetOneSettingsStringValue(v23, L"OFFLINESHEDDINGEXEMPTLIST", &qword_1802CAEA8);
    _GetOneSettingsStringValue(v23, L"SYSTEMCOMPONENTLIST", &qword_1802CAEB8);
    _GetOneSettingsStringValue(v23, L"MANDATORYUPDATEALLOWED", &qword_1802CAEC0);
    _GetOneSettingsStringValue(v23, L"DOWNLOADSTUCKTHRESHOLDS", &qword_1802CAEC8);
    _GetOneSettingsNumberValue<__int64>(v23, L"ONLINESCANTIMEINTERVALINMINUTES", &qword_1802CA670, 60);
    LogMessage(
      4u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0x8ADu,
      "DoInitializeOneSettingsConfiguration",
      -1,
      L"OneSettingsOnlineScanInterval (in seconds) = %d",
      0,
      0,
      qword_1802CA670);
    _GetOneSettingsNumberValue<unsigned int>(
      (_DWORD)v23,
      (unsigned int)L"ONLINESCANSALLOWEDININTERVAL",
      (unsigned int)&dword_1802CA668,
      v4,
      0);
    LODWORD(v22) = dword_1802CA668;
    LogMessage(
      4u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0x8AFu,
      "DoInitializeOneSettingsConfiguration",
      -1,
      L"OneSettingsOnlineScansAllowedInInterval = %d",
      0,
      0,
      v22);
    _GetOneSettingsNumberValue<__int64>(v23, L"ONLINESCANCOOLDOWNINMINUTES", &qword_1802CA660, 1);
    v5 = qword_1802CA660;
    if ( qword_1802CA660 == -1 )
    {
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        0x8B3u,
        "DoInitializeOneSettingsConfiguration",
        -1,
        L"Online cooldown functionality turned off",
        0,
        0);
      v5 = 0;
      qword_1802CA660 = 0;
    }
    LogMessage(
      4u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0x8B6u,
      "DoInitializeOneSettingsConfiguration",
      -1,
      L"OneSettingsOnlineScanCooldown (in seconds) = %d",
      0,
      0,
      v5);
    _GetOneSettingsStringValue(v23, L"MSIXVCARMSUPPORTENABLED", &lpString1);
    _GetOneSettingsStringValue(v23, L"INTERACTIVEALLOWLIST", &qword_1802CAED8);
    _GetOneSettingsStringValue(v23, L"INTERACTIVEDISALLOWLIST", &qword_1802CAEE0);
    _GetOneSettingsStringValue(v23, L"BACKGROUNDUPDATECALLERLIST", &qword_1802CAF00);
    _GetOneSettingsStringValue(v23, L"IMMEDIATERETRYDOWNLOADERRORLIST", &qword_1802CAF08);
    _GetOneSettingsNumberValue<unsigned int>(
      (_DWORD)v23,
      (unsigned int)L"IMMEDIATERETRYDOWNLOADDELAYINMILLISECONDS",
      (unsigned int)&dword_1802E4F58,
      v6,
      3000);
    _GetOneSettingsStringValue(v23, L"IMMEDIATERETRYSCANERRORLIST", &qword_1802CAF10);
    _GetOneSettingsNumberValue<unsigned int>(
      (_DWORD)v23,
      (unsigned int)L"IMMEDIATERETRYSCANDELAYINMILLISECONDS",
      (unsigned int)&dword_1802E4F54,
      v7,
      3000);
    _GetOneSettingsStringValue(v23, L"IMMEDIATERETRYACQUIRELICENSEERRORLIST", &qword_1802CAF18);
    _GetOneSettingsNumberValue<unsigned int>(
      (_DWORD)v23,
      (unsigned int)L"IMMEDIATERETRYACQUIRELICENSEDELAYINMILLISECONDS",
      (unsigned int)&dwMilliseconds,
      v8,
      3000);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmediateRetryInstall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ImmediateRetryInstall>::GetImpl'::`2'::impl) )
      _GetOneSettingsStringValue(v23, L"IMMEDIATERETRYINSTALLERRORLIST", &qword_1802CAF20);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixImmediateRetryInstall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixImmediateRetryInstall>::GetImpl'::`2'::impl) )
      _GetOneSettingsStringValue(v23, L"IMMEDIATERETRYINSTALLERRORLIST", &qword_1802CAF20);
    _GetOneSettingsNumberValue<unsigned int>(
      (_DWORD)v23,
      (unsigned int)L"IMMEDIATERETRYINSTALLDELAYINMILLISECONDS",
      (unsigned int)&dword_1802E4F4C,
      v9,
      3000);
    _GetOneSettingsStringValue(v23, L"NETWORKISSUESERRORLIST", &qword_1802CAF30);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreSearchForPackages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PreSearchForPackages>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v23, L"PRESEARCHUPDATEPACKAGEENABLED", &byte_1802E4F47);
    _GetOneSettingsNumberValue<unsigned int>(
      (_DWORD)v23,
      (unsigned int)L"PRESEARCHONLINESCANTHRESHOLDINMINUTES",
      (unsigned int)&dword_1802CA658,
      v10,
      0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SurfaceWUUpdateId>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SurfaceWUUpdateId>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v23, L"DISABLEWUUPDATEID", &byte_1802E4F46);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RefreshOneSettings>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RefreshOneSettings>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v23, L"DISABLEONESETTINGSREFRESH", &byte_1802E4F45);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate>::GetImpl'::`2'::impl) )
    {
      _GetOneSettingsStringValue(v23, L"INTERACTIVEALLOWLISTUPDATE", &qword_1802CAEE8);
      _GetOneSettingsStringValue(v23, L"INTERACTIVEDISALLOWLISTUPDATE", &qword_1802CAEF0);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall>::GetImpl'::`2'::impl) )
    {
      v27 = 0;
      _GetOneSettingsStringValue(v23, L"EXCLUDEAPPIDLIST", &v27);
      if ( v27 )
      {
        std::wstring::wstring(&hstringHeader, v27);
        v11 = (_QWORD *)std::wstring::end(&hstringHeader, &v26);
        p_hstringHeader = &hstringHeader;
        if ( v29 > 7 )
          LODWORD(p_hstringHeader) = hstringHeader.Reserved.Reserved1;
        std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
          (unsigned int)&v24,
          (_DWORD)p_hstringHeader,
          *v11,
          v12,
          (__int64)towupper);
        Reserved1 = &hstringHeader;
        if ( v29 > 7 )
          Reserved1 = hstringHeader.Reserved.Reserved1;
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v26,
          Reserved1,
          -1);
        v24 = 2;
        if ( !v26 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xFF8,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
            v15);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &qword_1802CAF38,
          &v26);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
        std::wstring::_Tidy_deallocate(&hstringHeader);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
    }
    _GetOneSettingsNumberValue<__int64>(v23, L"CATALOGCACHEITEMSTALETHRESHOLDINHOURS", &qword_1802CA650, 1);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreOneSettingsCleanup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StoreOneSettingsCleanup>::GetImpl'::`2'::impl);
    v17 = L"CATALOGCACHEITEMDELETETHRESHOLDINHOURS";
    if ( !IsEnabled )
      v17 = L"CATALOGCACHEITEMSTALETHRESHOLDINHOURS";
    _GetOneSettingsNumberValue<__int64>(v23, v17, &qword_1802CA648, 1);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkItemSelfReference>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WorkItemSelfReference>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v23, L"DISABLEWORKITEMREFCOUNT", &byte_1802E4F44);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InteractivityRegulationForResume>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InteractivityRegulationForResume>::GetImpl'::`2'::impl) )
    {
      _GetOneSettingsStringValue(v23, L"INTERACTIVEDISALLOWLISTRESUME", &qword_1802CAEF8);
      _GetOneSettingsBooleanValue(v23, L"ENABLEINTERACTIVERESUMEDISALLOWLIST", &byte_1802E4F5C);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserSessionRecovery>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UserSessionRecovery>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v23, L"DISABLEUSERSESSIONRECOVERY", &byte_1802E4F43);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v23, L"DISABLEASYNCLICENSING", &byte_1802E4F42);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PollDownloadProgress>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PollDownloadProgress>::GetImpl'::`2'::impl) )
    {
      _GetOneSettingsBooleanValue(v23, L"ENABLEPOLLDOWNLOADPROGRESS", &byte_1802E4F41);
      _GetOneSettingsNumberValue<unsigned int>(
        (_DWORD)v23,
        (unsigned int)L"POLLDOWNLOADPROGRESSINMILLISECONDS",
        (unsigned int)&dword_1802CA644,
        v18,
        1800000);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScan>::GetImpl'::`2'::impl) )
    {
      if ( (int)_ReadDirectDownloadEnablementState(v23) < 0 )
        LogSimpleMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0x90Du,
          "DoInitializeOneSettingsConfiguration",
          -1,
          L"Error while reading DirectDownloadEnablementState from OneSettings cache, value will remain Disabled",
          0,
          0);
      if ( (int)_ReadDirectDownloadEnablementSettings(v23) < 0 )
        LogSimpleMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0x912u,
          "DoInitializeOneSettingsConfiguration",
          -1,
          L"Error while reading DirectDownloadEnablementSettings from OneSettings cache, value will remain empty",
          0,
          0);
      if ( (int)_ReadDirectDownloadEnablementLiveCheckThreshold(v23) < 0 )
        LogSimpleMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0x917u,
          "DoInitializeOneSettingsConfiguration",
          -1,
          L"Error while reading DirectDownloadEnablementLiveCheckThreshold from OneSettings cache, value will remain 15 mins",
          0,
          0);
      if ( (int)_ReadProductCatalogUrl(v23) < 0 )
        LogSimpleMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0x91Cu,
          "DoInitializeOneSettingsConfiguration",
          -1,
          L"Error while reading ProductCatalogUrl from OneSettings cache, value will remain default",
          0,
          0);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FallbackRetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FallbackRetry>::GetImpl'::`2'::impl) )
    {
      _GetOneSettingsStringValue(v23, L"IMMEDIATERETRYFALLBACKERRORLIST", &qword_1802CAF28);
      _GetOneSettingsNumberValue<unsigned int>(
        (_DWORD)v23,
        (unsigned int)L"IMMEDIATERETRYFALLBACKDELAYINMILLISECONDS",
        (unsigned int)&dword_1802E4F48,
        v19,
        3000);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v23, L"ENABLEGETENTITLEMENTIFNOTPRESENT", &byte_1802E4F40);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ReportProgressWhenDownloadSizeReady>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ReportProgressWhenDownloadSizeReady>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v23, L"ENABLEREPORTPROGRESSWHENDOWNLOADSIZEREADY", &byte_1802E4F3A);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDependencyFrameworkInUse>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixDependencyFrameworkInUse>::GetImpl'::`2'::impl) )
      _GetOneSettingsStringValue(v23, L"FRAMEWORKPREUPDATEERRORLIST", &qword_1802CAF60);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixInstallUnderSystemContext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixInstallUnderSystemContext>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v23, L"FIXINSTALLUNDERSYSTEMCONTEXT", &byte_1802E4F39);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SFEdgeFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SFEdgeFallback>::GetImpl'::`2'::impl) )
    {
      _GetOneSettingsBooleanValue(v23, L"ENABLESFEDGEFALLBACK", &byte_1802E4F38);
      _GetOneSettingsStringValue(v23, L"SFEDGEFALLBACKSKIPERRORLIST", &qword_1802CAF88);
      if ( (int)_ReadSfEdgeFallbackEndpointUrl(v23) < 0 )
        LogSimpleMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0x941u,
          "DoInitializeOneSettingsConfiguration",
          -1,
          L"Error while reading SfEdgeFallbackEndpointUrl from OneSettings cache, value will remain default",
          0,
          0);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AbandonStaleWindowsStoreCheckpoints>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AbandonStaleWindowsStoreCheckpoints>::GetImpl'::`2'::impl)
      && (int)_ReadCheckpointAbandonmentRules(v23) < 0 )
    {
      LogSimpleMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        0x949u,
        "DoInitializeOneSettingsConfiguration",
        -1,
        L"Error while reading CheckpointAbandonmentRules from OneSettings cache, value will remain empty",
        0,
        0);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BlockUpdatesByPfnAndVersion>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BlockUpdatesByPfnAndVersion>::GetImpl'::`2'::impl) )
    {
      _GetOneSettingsStringValue(v23, L"UPDATEBLOCKLISTBYPFN", &qword_1802CAF90);
      if ( qword_1802CAF90 )
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0x952u,
          "DoInitializeOneSettingsConfiguration",
          -1,
          L"Successfully loaded update block list from OneSettings: %s",
          0,
          0,
          qword_1802CAF90);
      else
        LogSimpleMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0x956u,
          "DoInitializeOneSettingsConfiguration",
          -1,
          L"Update block list not found or empty in OneSettings",
          0,
          0);
    }
  }
  else
  {
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0x8A2u,
      "DoInitializeOneSettingsConfiguration",
      -1,
      L"Error %x while retrieving OneSettings values during one-time initialization, values will remain default.",
      0,
      0,
      v0);
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
  return 1;
}

```

## disassembly

```asm
0x18004b594  push    rbx
0x18004b596  push    rsi
0x18004b597  push    rdi
0x18004b598  push    r12
0x18004b59a  push    r13
0x18004b59c  push    r14
0x18004b59e  push    r15
0x18004b5a0  sub     rsp, 0A0h
0x18004b5a7  mov     rax, cs:__security_cookie
0x18004b5ae  xor     rax, rsp
0x18004b5b1  mov     [rsp+0D8h+var_40], rax
0x18004b5b9  xor     esi, esi
0x18004b5bb  mov     [rsp+0D8h+var_80], esi
0x18004b5bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing> `wil::Feature<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::GetImpl(void)'::`2'::impl
0x18004b5c6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::__private_IsEnabled(void)
0x18004b5cb  lea     r15d, [rsi+1]
0x18004b5cf  test    al, al
0x18004b5d1  jz      short loc_18004B5DA
0x18004b5d3  mov     cs:byte_1802E4F42, r15b
0x18004b5da  mov     [rsp+0D8h+var_78], rsi
0x18004b5df  mov     [rsp+0D8h+var_88], rsi
0x18004b5e4  mov     [rsp+0D8h+var_48], rsi
0x18004b5ec  mov     r9d, 39h ; '9'; unsigned int
0x18004b5f2  lea     r8d, [r9+1]; unsigned int
0x18004b5f6  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18004b5fd  lea     rcx, [rsp+0D8h+hstringHeader]; hstringHeader
0x18004b602  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004b607  lea     rdx, [rsp+0D8h+var_78]
0x18004b60c  mov     rcx, [rsp+0D8h+var_48]
0x18004b614  call    ??$GetActivationFactory@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>)
0x18004b619  test    eax, eax
0x18004b61b  js      short loc_18004B670
0x18004b61d  mov     rdi, [rsp+0D8h+var_78]
0x18004b622  mov     rax, [rdi]
0x18004b625  mov     rbx, [rax+30h]
0x18004b629  lea     rcx, [rsp+0D8h+var_88]
0x18004b62e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18004b633  mov     [rsp+0D8h+var_48], rsi
0x18004b63b  mov     r9d, 0Dh; unsigned int
0x18004b641  lea     r8d, [r9+1]; unsigned int
0x18004b645  lea     rdx, aSccinstallsvc; "SCCINSTALLSVC"
0x18004b64c  lea     rcx, [rsp+0D8h+hstringHeader]; hstringHeader
0x18004b651  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004b656  nop
0x18004b657  lea     r8, [rsp+0D8h+var_88]
0x18004b65c  mov     rdx, [rsp+0D8h+var_48]
0x18004b664  mov     rcx, rdi
0x18004b667  mov     rax, rbx
0x18004b66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b66f  nop
0x18004b670  jmp     short loc_18004B67C
0x18004b672  xor     esi, esi
0x18004b674  lea     r15d, [rsi+1]
0x18004b678  mov     eax, [rsp+0D8h+var_80]
0x18004b67c  test    eax, eax
0x18004b67e  js      loc_18004C076
0x18004b684  mov     rcx, [rsp+0D8h+var_88]
0x18004b689  test    rcx, rcx
0x18004b68c  jz      loc_18004C076
0x18004b692  mov     r9, r15
0x18004b695  lea     r8, qword_1802CA678
0x18004b69c  lea     rdx, aQueuestuckthre; "QUEUESTUCKTHRESHOLDINSECONDS"
0x18004b6a3  call    ??$_GetOneSettingsNumberValue@_J@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_J_J3@Z; _GetOneSettingsNumberValue<__int64>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,__int64 &,__int64,__int64)
0x18004b6a8  lea     r8, byte_1802E4F5D; bool *
0x18004b6af  lea     rdx, aDisableusostor; "DISABLEUSOSTOREPROVIDER"
0x18004b6b6  mov     rcx, [rsp+0D8h+var_88]; struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *
0x18004b6bb  call    ?_GetOneSettingsBooleanValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_N@Z; _GetOneSettingsBooleanValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,bool &)
0x18004b6c0  lea     r8, qword_1802CAEA8
0x18004b6c7  lea     rdx, aOfflinesheddin; "OFFLINESHEDDINGEXEMPTLIST"
0x18004b6ce  mov     rcx, [rsp+0D8h+var_88]
0x18004b6d3  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b6d8  lea     r8, qword_1802CAEB8
0x18004b6df  lea     rdx, aSystemcomponen; "SYSTEMCOMPONENTLIST"
0x18004b6e6  mov     rcx, [rsp+0D8h+var_88]
0x18004b6eb  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b6f0  lea     r8, qword_1802CAEC0
0x18004b6f7  lea     rdx, aMandatoryupdat; "MANDATORYUPDATEALLOWED"
0x18004b6fe  mov     rcx, [rsp+0D8h+var_88]
0x18004b703  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b708  lea     r8, qword_1802CAEC8
0x18004b70f  lea     rdx, aDownloadstuckt_0; "DOWNLOADSTUCKTHRESHOLDS"
0x18004b716  mov     rcx, [rsp+0D8h+var_88]
0x18004b71b  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b720  mov     r9d, 3Ch ; '<'
0x18004b726  lea     r8, qword_1802CA670
0x18004b72d  lea     rdx, aOnlinescantime; "ONLINESCANTIMEINTERVALINMINUTES"
0x18004b734  mov     rcx, [rsp+0D8h+var_88]
0x18004b739  call    ??$_GetOneSettingsNumberValue@_J@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_J_J3@Z; _GetOneSettingsNumberValue<__int64>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,__int64 &,__int64,__int64)
0x18004b73e  mov     rax, cs:qword_1802CA670
0x18004b745  mov     [rsp+0D8h+var_98], rax
0x18004b74a  mov     [rsp+0D8h+var_A0], rsi; unsigned __int16 *
0x18004b74f  mov     [rsp+0D8h+var_A8], rsi; char *
0x18004b754  lea     rax, aOnesettingsonl_1; "OneSettingsOnlineScanInterval (in secon"...
0x18004b75b  mov     [rsp+0D8h+var_B0], rax; unsigned __int16 *
0x18004b760  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004b764  mov     [rsp+0D8h+var_B8], ebx; int
0x18004b768  lea     rdi, aDoinitializeon; "DoInitializeOneSettingsConfiguration"
0x18004b76f  mov     r9, rdi; char *
0x18004b772  mov     r8d, 8ADh; unsigned int
0x18004b778  lea     r14, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18004b77f  mov     rdx, r14; char *
0x18004b782  lea     r12d, [rbx+5]
0x18004b786  mov     ecx, r12d; unsigned int
0x18004b789  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18004b78e  mov     [rsp+0D8h+var_B8], esi
0x18004b792  lea     r8, dword_1802CA668
0x18004b799  lea     rdx, aOnlinescansall; "ONLINESCANSALLOWEDININTERVAL"
0x18004b7a0  mov     rcx, [rsp+0D8h+var_88]
0x18004b7a5  call    ??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z; _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)
0x18004b7aa  mov     eax, cs:dword_1802CA668
0x18004b7b0  mov     dword ptr [rsp+0D8h+var_98], eax
0x18004b7b4  mov     [rsp+0D8h+var_A0], rsi; unsigned __int16 *
0x18004b7b9  mov     [rsp+0D8h+var_A8], rsi; char *
0x18004b7be  lea     rax, aOnesettingsonl_2; "OneSettingsOnlineScansAllowedInInterval"...
0x18004b7c5  mov     [rsp+0D8h+var_B0], rax; unsigned __int16 *
0x18004b7ca  mov     [rsp+0D8h+var_B8], ebx; int
0x18004b7ce  mov     r9, rdi; char *
0x18004b7d1  mov     r8d, 8AFh; unsigned int
0x18004b7d7  mov     rdx, r14; char *
0x18004b7da  mov     ecx, r12d; unsigned int
0x18004b7dd  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18004b7e2  mov     r9, r15
0x18004b7e5  lea     r8, qword_1802CA660
0x18004b7ec  lea     rdx, aOnlinescancool; "ONLINESCANCOOLDOWNINMINUTES"
0x18004b7f3  mov     rcx, [rsp+0D8h+var_88]
0x18004b7f8  call    ??$_GetOneSettingsNumberValue@_J@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_J_J3@Z; _GetOneSettingsNumberValue<__int64>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,__int64 &,__int64,__int64)
0x18004b7fd  mov     rax, cs:qword_1802CA660
0x18004b804  cmp     rax, rbx
0x18004b807  jnz     short loc_18004B841
0x18004b809  mov     [rsp+0D8h+var_A0], rsi; unsigned __int16 *
0x18004b80e  mov     [rsp+0D8h+var_A8], rsi; char *
0x18004b813  lea     rax, aOnlineCooldown; "Online cooldown functionality turned of"...
0x18004b81a  mov     [rsp+0D8h+var_B0], rax; unsigned __int16 *
0x18004b81f  mov     [rsp+0D8h+var_B8], ebx; int
0x18004b823  mov     r9, rdi; char *
0x18004b826  mov     r8d, 8B3h; unsigned int
0x18004b82c  mov     rdx, r14; char *
0x18004b82f  lea     ecx, [rbx+4]; unsigned int
0x18004b832  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18004b837  mov     rax, rsi
0x18004b83a  mov     cs:qword_1802CA660, rax
0x18004b841  mov     [rsp+0D8h+var_98], rax
0x18004b846  mov     [rsp+0D8h+var_A0], rsi; unsigned __int16 *
0x18004b84b  mov     [rsp+0D8h+var_A8], rsi; char *
0x18004b850  lea     rax, aOnesettingsonl_0; "OneSettingsOnlineScanCooldown (in secon"...
0x18004b857  mov     [rsp+0D8h+var_B0], rax; unsigned __int16 *
0x18004b85c  mov     [rsp+0D8h+var_B8], ebx; int
0x18004b860  mov     r9, rdi; char *
0x18004b863  mov     r8d, 8B6h; unsigned int
0x18004b869  mov     rdx, r14; char *
0x18004b86c  mov     ecx, r12d; unsigned int
0x18004b86f  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18004b874  lea     r8, lpString1
0x18004b87b  lea     rdx, aMsixvcarmsuppo; "MSIXVCARMSUPPORTENABLED"
0x18004b882  mov     rcx, [rsp+0D8h+var_88]
0x18004b887  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b88c  lea     r8, qword_1802CAED8
0x18004b893  lea     rdx, aInteractiveall; "INTERACTIVEALLOWLIST"
0x18004b89a  mov     rcx, [rsp+0D8h+var_88]
0x18004b89f  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b8a4  lea     r8, qword_1802CAEE0
0x18004b8ab  lea     rdx, aInteractivedis_1; "INTERACTIVEDISALLOWLIST"
0x18004b8b2  mov     rcx, [rsp+0D8h+var_88]
0x18004b8b7  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b8bc  lea     r8, qword_1802CAF00
0x18004b8c3  lea     rdx, aBackgroundupda; "BACKGROUNDUPDATECALLERLIST"
0x18004b8ca  mov     rcx, [rsp+0D8h+var_88]
0x18004b8cf  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b8d4  lea     r8, qword_1802CAF08
0x18004b8db  lea     rdx, aImmediateretry_8; "IMMEDIATERETRYDOWNLOADERRORLIST"
0x18004b8e2  mov     rcx, [rsp+0D8h+var_88]
0x18004b8e7  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b8ec  mov     r13d, 0BB8h
0x18004b8f2  mov     [rsp+0D8h+var_B8], r13d
0x18004b8f7  lea     r8, dword_1802E4F58
0x18004b8fe  lea     rdx, aImmediateretry_15; "IMMEDIATERETRYDOWNLOADDELAYINMILLISECON"...
0x18004b905  mov     rcx, [rsp+0D8h+var_88]
0x18004b90a  call    ??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z; _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)
0x18004b90f  lea     r8, qword_1802CAF10
0x18004b916  lea     rdx, aImmediateretry_13; "IMMEDIATERETRYSCANERRORLIST"
0x18004b91d  mov     rcx, [rsp+0D8h+var_88]
0x18004b922  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b927  mov     [rsp+0D8h+var_B8], r13d
0x18004b92c  lea     r8, dword_1802E4F54
0x18004b933  lea     rdx, aImmediateretry_11; "IMMEDIATERETRYSCANDELAYINMILLISECONDS"
0x18004b93a  mov     rcx, [rsp+0D8h+var_88]
0x18004b93f  call    ??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z; _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)
0x18004b944  lea     r8, qword_1802CAF18
0x18004b94b  lea     rdx, aImmediateretry_14; "IMMEDIATERETRYACQUIRELICENSEERRORLIST"
0x18004b952  mov     rcx, [rsp+0D8h+var_88]
0x18004b957  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b95c  mov     [rsp+0D8h+var_B8], r13d
0x18004b961  lea     r8, dwMilliseconds
0x18004b968  lea     rdx, aImmediateretry_0; "IMMEDIATERETRYACQUIRELICENSEDELAYINMILL"...
0x18004b96f  mov     rcx, [rsp+0D8h+var_88]
0x18004b974  call    ??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z; _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)
0x18004b979  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ImmediateRetryInstall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ImmediateRetryInstall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmediateRetryInstall> `wil::Feature<__WilFeatureTraits_Feature_ImmediateRetryInstall>::GetImpl(void)'::`2'::impl
0x18004b980  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ImmediateRetryInstall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmediateRetryInstall>::__private_IsEnabled(void)
0x18004b985  test    al, al
0x18004b987  jz      short loc_18004B9A1
0x18004b989  lea     r8, qword_1802CAF20
0x18004b990  lea     rdx, aImmediateretry_5; "IMMEDIATERETRYINSTALLERRORLIST"
0x18004b997  mov     rcx, [rsp+0D8h+var_88]
0x18004b99c  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b9a1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixImmediateRetryInstall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixImmediateRetryInstall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixImmediateRetryInstall> `wil::Feature<__WilFeatureTraits_Feature_FixImmediateRetryInstall>::GetImpl(void)'::`2'::impl
0x18004b9a8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixImmediateRetryInstall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixImmediateRetryInstall>::__private_IsEnabled(void)
0x18004b9ad  test    al, al
0x18004b9af  jz      short loc_18004B9C9
0x18004b9b1  lea     r8, qword_1802CAF20
0x18004b9b8  lea     rdx, aImmediateretry_5; "IMMEDIATERETRYINSTALLERRORLIST"
0x18004b9bf  mov     rcx, [rsp+0D8h+var_88]
0x18004b9c4  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b9c9  mov     [rsp+0D8h+var_B8], r13d
0x18004b9ce  lea     r8, dword_1802E4F4C
0x18004b9d5  lea     rdx, aImmediateretry_2; "IMMEDIATERETRYINSTALLDELAYINMILLISECOND"...
0x18004b9dc  mov     rcx, [rsp+0D8h+var_88]
0x18004b9e1  call    ??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z; _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)
0x18004b9e6  lea     r8, qword_1802CAF30
0x18004b9ed  lea     rdx, aNetworkissuese; "NETWORKISSUESERRORLIST"
0x18004b9f4  mov     rcx, [rsp+0D8h+var_88]
0x18004b9f9  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004b9fe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PreSearchForPackages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PreSearchForPackages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreSearchForPackages> `wil::Feature<__WilFeatureTraits_Feature_PreSearchForPackages>::GetImpl(void)'::`2'::impl
0x18004ba05  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PreSearchForPackages@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreSearchForPackages>::__private_IsEnabled(void)
0x18004ba0a  test    al, al
0x18004ba0c  jz      short loc_18004BA26
0x18004ba0e  lea     r8, byte_1802E4F47; bool *
0x18004ba15  lea     rdx, aPresearchupdat_0; "PRESEARCHUPDATEPACKAGEENABLED"
0x18004ba1c  mov     rcx, [rsp+0D8h+var_88]; struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *
0x18004ba21  call    ?_GetOneSettingsBooleanValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_N@Z; _GetOneSettingsBooleanValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,bool &)
0x18004ba26  mov     [rsp+0D8h+var_B8], esi
0x18004ba2a  lea     r8, dword_1802CA658
0x18004ba31  lea     rdx, aPresearchonlin; "PRESEARCHONLINESCANTHRESHOLDINMINUTES"
0x18004ba38  mov     rcx, [rsp+0D8h+var_88]
0x18004ba3d  call    ??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z; _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)
0x18004ba42  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SurfaceWUUpdateId@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SurfaceWUUpdateId@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SurfaceWUUpdateId> `wil::Feature<__WilFeatureTraits_Feature_SurfaceWUUpdateId>::GetImpl(void)'::`2'::impl
0x18004ba49  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SurfaceWUUpdateId@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SurfaceWUUpdateId>::__private_IsEnabled(void)
0x18004ba4e  test    al, al
0x18004ba50  jz      short loc_18004BA6A
0x18004ba52  lea     r8, byte_1802E4F46; bool *
0x18004ba59  lea     rdx, aDisablewuupdat; "DISABLEWUUPDATEID"
0x18004ba60  mov     rcx, [rsp+0D8h+var_88]; struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *
0x18004ba65  call    ?_GetOneSettingsBooleanValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_N@Z; _GetOneSettingsBooleanValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,bool &)
0x18004ba6a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RefreshOneSettings@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RefreshOneSettings@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RefreshOneSettings> `wil::Feature<__WilFeatureTraits_Feature_RefreshOneSettings>::GetImpl(void)'::`2'::impl
0x18004ba71  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RefreshOneSettings@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RefreshOneSettings>::__private_IsEnabled(void)
0x18004ba76  test    al, al
0x18004ba78  jz      short loc_18004BA92
0x18004ba7a  lea     r8, byte_1802E4F45; bool *
0x18004ba81  lea     rdx, aDisableonesett; "DISABLEONESETTINGSREFRESH"
0x18004ba88  mov     rcx, [rsp+0D8h+var_88]; struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *
0x18004ba8d  call    ?_GetOneSettingsBooleanValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_N@Z; _GetOneSettingsBooleanValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,bool &)
0x18004ba92  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InterActivityRegulationForUpdate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InterActivityRegulationForUpdate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate> `wil::Feature<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate>::GetImpl(void)'::`2'::impl
0x18004ba99  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InterActivityRegulationForUpdate@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate>::__private_IsEnabled(void)
0x18004ba9e  test    al, al
0x18004baa0  jz      short loc_18004BAD2
0x18004baa2  lea     r8, qword_1802CAEE8
0x18004baa9  lea     rdx, aInteractiveall_1; "INTERACTIVEALLOWLISTUPDATE"
0x18004bab0  mov     rcx, [rsp+0D8h+var_88]
0x18004bab5  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004baba  lea     r8, qword_1802CAEF0
0x18004bac1  lea     rdx, aInteractivedis_0; "INTERACTIVEDISALLOWLISTUPDATE"
0x18004bac8  mov     rcx, [rsp+0D8h+var_88]
0x18004bacd  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004bad2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall> `wil::Feature<__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall>::GetImpl(void)'::`2'::impl
0x18004bad9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall>::__private_IsEnabled(void)
0x18004bade  test    al, al
0x18004bae0  jz      loc_18004BBE1
0x18004bae6  mov     [rsp+0D8h+var_68], rsi
0x18004baeb  lea     r8, [rsp+0D8h+var_68]
0x18004baf0  lea     rdx, aExcludeappidli; "EXCLUDEAPPIDLIST"
0x18004baf7  mov     rcx, [rsp+0D8h+var_88]
0x18004bafc  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18004bb01  mov     rdx, [rsp+0D8h+var_68]
0x18004bb06  test    rdx, rdx
0x18004bb09  jnz     short loc_18004BB14
0x18004bb0b  lea     r12d, [rdx+2]
0x18004bb0f  jmp     loc_18004BBD5
0x18004bb14  lea     rcx, [rsp+0D8h+hstringHeader]
0x18004bb19  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004bb1e  nop
0x18004bb1f  lea     r9, [rsp+0D8h+hstringHeader]
0x18004bb24  cmp     [rsp+0D8h+var_48], 7
0x18004bb2d  cmova   r9, qword ptr [rsp+0D8h+hstringHeader.Reserved]
0x18004bb33  lea     rdx, [rsp+0D8h+var_70]
0x18004bb38  lea     rcx, [rsp+0D8h+hstringHeader]
0x18004bb3d  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x18004bb42  lea     rdx, [rsp+0D8h+hstringHeader]
0x18004bb47  cmp     [rsp+0D8h+var_48], 7
0x18004bb50  cmova   rdx, qword ptr [rsp+0D8h+hstringHeader.Reserved]
0x18004bb56  mov     rcx, cs:__imp_towupper
0x18004bb5d  mov     qword ptr [rsp+0D8h+var_B8], rcx
0x18004bb62  mov     r8, [rax]
0x18004bb65  lea     rcx, [rsp+0D8h+var_80]
0x18004bb6a  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x18004bb6f  lea     rdx, [rsp+0D8h+hstringHeader]
0x18004bb74  cmp     [rsp+0D8h+var_48], 7
0x18004bb7d  cmova   rdx, qword ptr [rsp+0D8h+hstringHeader.Reserved]
0x18004bb83  mov     r8, rbx
0x18004bb86  lea     rcx, [rsp+0D8h+var_70]
0x18004bb8b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004bb90  mov     r12d, 2
  ... truncated ...
```
