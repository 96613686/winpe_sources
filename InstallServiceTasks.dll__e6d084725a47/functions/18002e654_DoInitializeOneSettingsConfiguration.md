# DoInitializeOneSettingsConfiguration

- ea: `0x18002e654`
- end: `0x18002f1a0`
- name: `DoInitializeOneSettingsConfiguration`
- size: `2892`
- prototype: ``
- caller_count: `1`
- callee_count: `49`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f260`

## callees

- `0x180003450`
- `0x18000760c`
- `0x18000c980`
- `0x18000e958`
- `0x180010d54`
- `0x180010f50`
- `0x180011044`
- `0x180012118`
- `0x180012f10`
- `0x1800156a8`
- `0x18001f584`
- `0x18001fb0c`
- `0x18001fc04`
- `0x1800202c4`
- `0x18002039c`
- `0x1800206dc`
- `0x180028e74`
- `0x180028f68`
- `0x1800292b0`
- `0x180029920`
- `0x180029a64`
- `0x18002a368`
- `0x18002a4a0`
- `0x18002a644`
- `0x18002a908`
- `0x18002a980`
- `0x18002a9fc`
- `0x18002aa3c`
- `0x18002aab4`
- `0x18002aaf0`
- `0x18002ab2c`
- `0x18002ab68`
- `0x18002aba4`
- `0x18002abe0`
- `0x18002ac1c`
- `0x18002ac58`
- `0x18002acd0`
- `0x18002ad0c`
- `0x18002ad84`
- `0x18002adc0`
- `0x18002adfc`
- `0x18002ae38`
- `0x18002ae74`
- `0x18002aeb0`
- `0x18002aeec`
- `0x18002b054`
- `0x18002b0cc`
- `0x18002e654`
- `0x180046010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18002ebf5`

## string_xrefs

- `0x18002f18e`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18002e838`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002f141`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18002e79f`: `SYSTEMCOMPONENTLIST`
- `0x18002e7b7`: `MANDATORYUPDATEALLOWED`
- `0x18002e93b`: `MSIXVCARMSUPPORTENABLED`
- `0x18002eb69`: `INTERACTIVEALLOWLISTUPDATE`
- `0x18002eb81`: `INTERACTIVEDISALLOWLISTUPDATE`
- `0x18002e983`: `BACKGROUNDUPDATECALLERLIST`
- `0x18002ea95`: `IMMEDIATERETRYINSTALLDELAYINMILLISECONDS`
- `0x18002ea50`: `IMMEDIATERETRYINSTALLERRORLIST`
- `0x18002ea78`: `IMMEDIATERETRYINSTALLERRORLIST`
- `0x18002ead5`: `PRESEARCHUPDATEPACKAGEENABLED`
- `0x18002eb19`: `DISABLEWUUPDATEID`
- `0x18002ef80`: `FRAMEWORKPREUPDATEERRORLIST`
- `0x18002ef58`: `ENABLEREPORTPROGRESSWHENDOWNLOADSIZEREADY`
- `0x18002efa8`: `FIXINSTALLUNDERSYSTEMCONTEXT`
- `0x18002f09c`: `UPDATEBLOCKLISTBYPFN`
- `0x18002e705`: `SCCINSTALLSVC`
- `0x18002ec8d`: `CATALOGCACHEITEMSTALETHRESHOLDINHOURS`
- `0x18002ecc4`: `CATALOGCACHEITEMSTALETHRESHOLDINHOURS`
- `0x18002ecbb`: `CATALOGCACHEITEMDELETETHRESHOLDINHOURS`
- `0x18002edfc`: `Error while reading DirectDownloadEnablementState from OneSettings cache, value will remain Disabled`
- `0x18002ee74`: `Error while reading DirectDownloadEnablementLiveCheckThreshold from OneSettings cache, value will remain 15 mins`
- `0x18002ee38`: `Error while reading DirectDownloadEnablementSettings from OneSettings cache, value will remain empty`
- `0x18002eeb0`: `Error while reading ProductCatalogUrl from OneSettings cache, value will remain default`
- `0x18002f05d`: `Error while reading CheckpointAbandonmentRules from OneSettings cache, value will remain empty`
- `0x18002f011`: `Error while reading SfEdgeFallbackEndpointUrl from OneSettings cache, value will remain default`
- `0x18002f0d3`: `Successfully loaded update block list from OneSettings: %s`
- `0x18002f0f5`: `Update block list not found or empty in OneSettings`
- `0x18002f120`: `Error %x while retrieving OneSettings values during one-time initialization, values will remain default.`
- `0x18002e828`: `DoInitializeOneSettingsConfiguration`
- `0x18002f134`: `DoInitializeOneSettingsConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 DoInitializeOneSettingsConfiguration()
{
  int v0; // eax
  __int64 v1; // rdi
  __int64 (__fastcall *v2)(__int64, __int64, struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload **); // rbx
  wil *v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  char *v6; // rax
  const char *v7; // r9
  const char *v8; // r9
  char IsEnabled; // al
  const WCHAR *v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r8
  const char *v14; // r9
  __int64 v15; // [rsp+40h] [rbp-98h]
  struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *v16; // [rsp+50h] [rbp-88h] BYREF
  int v17; // [rsp+58h] [rbp-80h]
  __int64 v18; // [rsp+60h] [rbp-78h] BYREF
  void *v19; // [rsp+68h] [rbp-70h] BYREF
  void *v20; // [rsp+70h] [rbp-68h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-60h] BYREF
  __int64 v22; // [rsp+90h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v17 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::GetImpl'::`2'::impl) )
    byte_180083C49 = 1;
  v18 = 0;
  v16 = 0;
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
    0x3Au,
    0x39u);
  v0 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(
         v22,
         (__int64)&v18);
  if ( v0 >= 0 )
  {
    v1 = v18;
    v2 = *(__int64 (__fastcall **)(__int64, __int64, struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload **))(*(_QWORD *)v18 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    v22 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SCCINSTALLSVC", 0xEu, 0xDu);
    try
    {
      v0 = v2(v1, v22, &v16);
    }
    catch ( ... )
    {
      v17 = wil::ResultFromCaughtException(v3);
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x89D,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
        v14);
      v0 = v17;
    }
  }
  if ( v0 >= 0 && v16 )
  {
    _GetOneSettingsNumberValue<__int64>((__int64)v16, L"QUEUESTUCKTHRESHOLDINSECONDS");
    _GetOneSettingsBooleanValue(v16, L"DISABLEUSOSTOREPROVIDER", &byte_180083C65);
    _GetOneSettingsStringValue(v16, L"OFFLINESHEDDINGEXEMPTLIST", &qword_18006A480);
    _GetOneSettingsStringValue(v16, L"SYSTEMCOMPONENTLIST", &qword_18006A490);
    _GetOneSettingsStringValue(v16, L"MANDATORYUPDATEALLOWED", &lpString1);
    _GetOneSettingsStringValue(v16, L"DOWNLOADSTUCKTHRESHOLDS", &qword_18006A4A0);
    _GetOneSettingsNumberValue<__int64>((__int64)v16, L"ONLINESCANTIMEINTERVALINMINUTES");
    LogMessage(
      4u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0x8ADu,
      "DoInitializeOneSettingsConfiguration",
      -1,
      L"OneSettingsOnlineScanInterval (in seconds) = %d",
      0,
      0,
      qword_180069C30);
    _GetOneSettingsNumberValue<unsigned int>((__int64)v16, L"ONLINESCANSALLOWEDININTERVAL");
    LODWORD(v15) = dword_180069C38;
    LogMessage(
      4u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      0x8AFu,
      "DoInitializeOneSettingsConfiguration",
      -1,
      L"OneSettingsOnlineScansAllowedInInterval = %d",
      0,
      0,
      v15);
    _GetOneSettingsNumberValue<__int64>((__int64)v16, L"ONLINESCANCOOLDOWNINMINUTES");
    v4 = qword_180069C28;
    if ( qword_180069C28 == -1 )
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
      v4 = 0;
      qword_180069C28 = 0;
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
      v4);
    _GetOneSettingsStringValue(v16, L"MSIXVCARMSUPPORTENABLED", &qword_18006A4A8);
    _GetOneSettingsStringValue(v16, L"INTERACTIVEALLOWLIST", &qword_18006A4B0);
    _GetOneSettingsStringValue(v16, L"INTERACTIVEDISALLOWLIST", &qword_18006A4B8);
    _GetOneSettingsStringValue(v16, L"BACKGROUNDUPDATECALLERLIST", &qword_18006A4D8);
    _GetOneSettingsStringValue(v16, L"IMMEDIATERETRYDOWNLOADERRORLIST", &qword_18006A4E0);
    _GetOneSettingsNumberValue<unsigned int>((__int64)v16, L"IMMEDIATERETRYDOWNLOADDELAYINMILLISECONDS");
    _GetOneSettingsStringValue(v16, L"IMMEDIATERETRYSCANERRORLIST", &qword_18006A4E8);
    _GetOneSettingsNumberValue<unsigned int>((__int64)v16, L"IMMEDIATERETRYSCANDELAYINMILLISECONDS");
    _GetOneSettingsStringValue(v16, L"IMMEDIATERETRYACQUIRELICENSEERRORLIST", &qword_18006A4F0);
    _GetOneSettingsNumberValue<unsigned int>((__int64)v16, L"IMMEDIATERETRYACQUIRELICENSEDELAYINMILLISECONDS");
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmediateRetryInstall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ImmediateRetryInstall>::GetImpl'::`2'::impl) )
      _GetOneSettingsStringValue(v16, L"IMMEDIATERETRYINSTALLERRORLIST", &qword_18006A4F8);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixImmediateRetryInstall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixImmediateRetryInstall>::GetImpl'::`2'::impl) )
      _GetOneSettingsStringValue(v16, L"IMMEDIATERETRYINSTALLERRORLIST", &qword_18006A4F8);
    _GetOneSettingsNumberValue<unsigned int>((__int64)v16, L"IMMEDIATERETRYINSTALLDELAYINMILLISECONDS");
    _GetOneSettingsStringValue(v16, L"NETWORKISSUESERRORLIST", &qword_18006A508);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreSearchForPackages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PreSearchForPackages>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v16, L"PRESEARCHUPDATEPACKAGEENABLED", &byte_180083C4F);
    _GetOneSettingsNumberValue<unsigned int>((__int64)v16, L"PRESEARCHONLINESCANTHRESHOLDINMINUTES");
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SurfaceWUUpdateId>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SurfaceWUUpdateId>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v16, L"DISABLEWUUPDATEID", &byte_180083C4E);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RefreshOneSettings>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RefreshOneSettings>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v16, L"DISABLEONESETTINGSREFRESH", &byte_180083C4D);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate>::GetImpl'::`2'::impl) )
    {
      _GetOneSettingsStringValue(v16, L"INTERACTIVEALLOWLISTUPDATE", &qword_18006A4C0);
      _GetOneSettingsStringValue(v16, L"INTERACTIVEDISALLOWLISTUPDATE", &qword_18006A4C8);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall>::GetImpl'::`2'::impl) )
    {
      v20 = 0;
      _GetOneSettingsStringValue(v16, L"EXCLUDEAPPIDLIST", &v20);
      if ( v20 )
      {
        std::wstring::wstring(&hstringHeader, v20);
        v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
        std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
          (unsigned int)&v19,
          v5,
          v5 + 2 * *(_DWORD *)&hstringHeader.Reserved.Reserved2[16],
          v5,
          (__int64)towupper);
        v6 = (char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v19,
          v6,
          0xFFFFFFFFFFFFFFFFuLL,
          v7);
        v17 = 2;
        if ( !v19 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xFF8,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
            v8);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          &qword_18006A510,
          &v19);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
        std::wstring::_Tidy_deallocate(&hstringHeader);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
    }
    _GetOneSettingsNumberValue<__int64>((__int64)v16, L"CATALOGCACHEITEMSTALETHRESHOLDINHOURS");
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_StoreOneSettingsCleanup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StoreOneSettingsCleanup>::GetImpl'::`2'::impl);
    v10 = L"CATALOGCACHEITEMDELETETHRESHOLDINHOURS";
    if ( !IsEnabled )
      v10 = L"CATALOGCACHEITEMSTALETHRESHOLDINHOURS";
    _GetOneSettingsNumberValue<__int64>((__int64)v16, v10);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkItemSelfReference>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WorkItemSelfReference>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v16, L"DISABLEWORKITEMREFCOUNT", &byte_180083C4B);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InteractivityRegulationForResume>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InteractivityRegulationForResume>::GetImpl'::`2'::impl) )
    {
      _GetOneSettingsStringValue(v16, L"INTERACTIVEDISALLOWLISTRESUME", &qword_18006A4D0);
      _GetOneSettingsBooleanValue(v16, L"ENABLEINTERACTIVERESUMEDISALLOWLIST", &byte_180083C64);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UserSessionRecovery>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UserSessionRecovery>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v16, L"DISABLEUSERSESSIONRECOVERY", &byte_180083C4C);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AsyncLicensing>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AsyncLicensing>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v16, L"DISABLEASYNCLICENSING", &byte_180083C49);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PollDownloadProgress>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PollDownloadProgress>::GetImpl'::`2'::impl) )
    {
      _GetOneSettingsBooleanValue(v16, L"ENABLEPOLLDOWNLOADPROGRESS", &byte_180083C4A);
      _GetOneSettingsNumberValue<unsigned int>((__int64)v16, L"POLLDOWNLOADPROGRESSINMILLISECONDS");
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupScan>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BackupScan>::GetImpl'::`2'::impl) )
    {
      if ( (int)_ReadDirectDownloadEnablementState(v16) < 0 )
        LogSimpleMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0x90Du,
          "DoInitializeOneSettingsConfiguration",
          -1,
          L"Error while reading DirectDownloadEnablementState from OneSettings cache, value will remain Disabled",
          0,
          0);
      if ( (int)_ReadDirectDownloadEnablementSettings(v16) < 0 )
        LogSimpleMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0x912u,
          "DoInitializeOneSettingsConfiguration",
          -1,
          L"Error while reading DirectDownloadEnablementSettings from OneSettings cache, value will remain empty",
          0,
          0);
      if ( (int)_ReadDirectDownloadEnablementLiveCheckThreshold(v16) < 0 )
        LogSimpleMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0x917u,
          "DoInitializeOneSettingsConfiguration",
          -1,
          L"Error while reading DirectDownloadEnablementLiveCheckThreshold from OneSettings cache, value will remain 15 mins",
          0,
          0);
      if ( (int)_ReadProductCatalogUrl(v16) < 0 )
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
      _GetOneSettingsStringValue(v16, L"IMMEDIATERETRYFALLBACKERRORLIST", &qword_18006A500);
      _GetOneSettingsNumberValue<unsigned int>((__int64)v16, L"IMMEDIATERETRYFALLBACKDELAYINMILLISECONDS");
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_GetEntitlementIfNotPresent>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v16, L"ENABLEGETENTITLEMENTIFNOTPRESENT", &byte_180083C48);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ReportProgressWhenDownloadSizeReady>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ReportProgressWhenDownloadSizeReady>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v16, L"ENABLEREPORTPROGRESSWHENDOWNLOADSIZEREADY", &byte_180083C42);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixDependencyFrameworkInUse>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixDependencyFrameworkInUse>::GetImpl'::`2'::impl) )
      _GetOneSettingsStringValue(v16, L"FRAMEWORKPREUPDATEERRORLIST", &qword_18006A538);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixInstallUnderSystemContext>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixInstallUnderSystemContext>::GetImpl'::`2'::impl) )
      _GetOneSettingsBooleanValue(v16, L"FIXINSTALLUNDERSYSTEMCONTEXT", &byte_180083C40);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SFEdgeFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SFEdgeFallback>::GetImpl'::`2'::impl) )
    {
      _GetOneSettingsBooleanValue(v16, L"ENABLESFEDGEFALLBACK", &byte_180083C41);
      _GetOneSettingsStringValue(v16, L"SFEDGEFALLBACKSKIPERRORLIST", &qword_18006A560);
      if ( (int)_ReadSfEdgeFallbackEndpointUrl(v16) < 0 )
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
      && (int)_ReadCheckpointAbandonmentRules(v16, v11, v12) < 0 )
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
      _GetOneSettingsStringValue(v16, L"UPDATEBLOCKLISTBYPFN", &qword_18006A568);
      if ( qword_18006A568 )
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
          0x952u,
          "DoInitializeOneSettingsConfiguration",
          -1,
          L"Successfully loaded update block list from OneSettings: %s",
          0,
          0,
          qword_18006A568);
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  return 1;
}

```

## disassembly

```asm
0x18002e654  push    rbx
0x18002e656  push    rsi
0x18002e657  push    rdi
0x18002e658  push    r12
0x18002e65a  push    r13
0x18002e65c  push    r14
0x18002e65e  push    r15
0x18002e660  sub     rsp, 0A0h
0x18002e667  mov     rax, cs:__security_cookie
0x18002e66e  xor     rax, rsp
0x18002e671  mov     [rsp+0D8h+var_40], rax
0x18002e679  xor     esi, esi
0x18002e67b  mov     [rsp+0D8h+var_80], esi
0x18002e67f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing> `wil::Feature<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::GetImpl(void)'::`2'::impl
0x18002e686  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DefaultDisableAsyncLicensing>::__private_IsEnabled(void)
0x18002e68b  lea     r12d, [rsi+1]
0x18002e68f  test    al, al
0x18002e691  jz      short loc_18002E69A
0x18002e693  mov     cs:byte_180083C49, r12b
0x18002e69a  mov     [rsp+0D8h+var_78], rsi
0x18002e69f  mov     [rsp+0D8h+var_88], rsi
0x18002e6a4  mov     [rsp+0D8h+var_48], rsi
0x18002e6ac  mov     r9d, 39h ; '9'; unsigned int
0x18002e6b2  lea     r8d, [r9+1]; unsigned int
0x18002e6b6  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18002e6bd  lea     rcx, [rsp+0D8h+hstringHeader]; hstringHeader
0x18002e6c2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002e6c7  lea     rdx, [rsp+0D8h+var_78]
0x18002e6cc  mov     rcx, [rsp+0D8h+var_48]
0x18002e6d4  call    ??$GetActivationFactory@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>)
0x18002e6d9  test    eax, eax
0x18002e6db  js      short loc_18002E730
0x18002e6dd  mov     rdi, [rsp+0D8h+var_78]
0x18002e6e2  mov     rax, [rdi]
0x18002e6e5  mov     rbx, [rax+30h]
0x18002e6e9  lea     rcx, [rsp+0D8h+var_88]
0x18002e6ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002e6f3  mov     [rsp+0D8h+var_48], rsi
0x18002e6fb  mov     r9d, 0Dh; unsigned int
0x18002e701  lea     r8d, [r9+1]; unsigned int
0x18002e705  lea     rdx, aSccinstallsvc; "SCCINSTALLSVC"
0x18002e70c  lea     rcx, [rsp+0D8h+hstringHeader]; hstringHeader
0x18002e711  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002e716  nop
0x18002e717  lea     r8, [rsp+0D8h+var_88]
0x18002e71c  mov     rdx, [rsp+0D8h+var_48]
0x18002e724  mov     rcx, rdi
0x18002e727  mov     rax, rbx
0x18002e72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e72f  nop
0x18002e730  jmp     short loc_18002E73C
0x18002e732  xor     esi, esi
0x18002e734  lea     r12d, [rsi+1]
0x18002e738  mov     eax, [rsp+0D8h+var_80]
0x18002e73c  test    eax, eax
0x18002e73e  js      loc_18002F112
0x18002e744  mov     rcx, [rsp+0D8h+var_88]
0x18002e749  test    rcx, rcx
0x18002e74c  jz      loc_18002F112
0x18002e752  mov     r9, r12
0x18002e755  lea     r8, qword_180069C40
0x18002e75c  lea     rdx, aQueuestuckthre; "QUEUESTUCKTHRESHOLDINSECONDS"
0x18002e763  call    ??$_GetOneSettingsNumberValue@_J@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_J_J3@Z; _GetOneSettingsNumberValue<__int64>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,__int64 &,__int64,__int64)
0x18002e768  lea     r8, byte_180083C65; bool *
0x18002e76f  lea     rdx, aDisableusostor; "DISABLEUSOSTOREPROVIDER"
0x18002e776  mov     rcx, [rsp+0D8h+var_88]; struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *
0x18002e77b  call    ?_GetOneSettingsBooleanValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_N@Z; _GetOneSettingsBooleanValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,bool &)
0x18002e780  lea     r8, qword_18006A480
0x18002e787  lea     rdx, aOfflinesheddin; "OFFLINESHEDDINGEXEMPTLIST"
0x18002e78e  mov     rcx, [rsp+0D8h+var_88]
0x18002e793  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002e798  lea     r8, qword_18006A490
0x18002e79f  lea     rdx, aSystemcomponen; "SYSTEMCOMPONENTLIST"
0x18002e7a6  mov     rcx, [rsp+0D8h+var_88]
0x18002e7ab  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002e7b0  lea     r8, lpString1
0x18002e7b7  lea     rdx, aMandatoryupdat; "MANDATORYUPDATEALLOWED"
0x18002e7be  mov     rcx, [rsp+0D8h+var_88]
0x18002e7c3  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002e7c8  lea     r8, qword_18006A4A0
0x18002e7cf  lea     rdx, aDownloadstuckt; "DOWNLOADSTUCKTHRESHOLDS"
0x18002e7d6  mov     rcx, [rsp+0D8h+var_88]
0x18002e7db  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002e7e0  mov     r9d, 3Ch ; '<'
0x18002e7e6  lea     r8, qword_180069C30
0x18002e7ed  lea     rdx, aOnlinescantime; "ONLINESCANTIMEINTERVALINMINUTES"
0x18002e7f4  mov     rcx, [rsp+0D8h+var_88]
0x18002e7f9  call    ??$_GetOneSettingsNumberValue@_J@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_J_J3@Z; _GetOneSettingsNumberValue<__int64>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,__int64 &,__int64,__int64)
0x18002e7fe  mov     rax, cs:qword_180069C30
0x18002e805  mov     [rsp+0D8h+var_98], rax
0x18002e80a  mov     [rsp+0D8h+var_A0], rsi; unsigned __int16 *
0x18002e80f  mov     [rsp+0D8h+var_A8], rsi; char *
0x18002e814  lea     rax, aOnesettingsonl_1; "OneSettingsOnlineScanInterval (in secon"...
0x18002e81b  mov     [rsp+0D8h+var_B0], rax; unsigned __int16 *
0x18002e820  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e824  mov     [rsp+0D8h+var_B8], ebx; int
0x18002e828  lea     rdi, aDoinitializeon; "DoInitializeOneSettingsConfiguration"
0x18002e82f  mov     r9, rdi; char *
0x18002e832  mov     r8d, 8ADh; unsigned int
0x18002e838  lea     r14, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\installs"...
0x18002e83f  mov     rdx, r14; char *
0x18002e842  lea     r15d, [rbx+5]
0x18002e846  mov     ecx, r15d; unsigned int
0x18002e849  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18002e84e  mov     [rsp+0D8h+var_B8], esi
0x18002e852  lea     r8, dword_180069C38
0x18002e859  lea     rdx, aOnlinescansall; "ONLINESCANSALLOWEDININTERVAL"
0x18002e860  mov     rcx, [rsp+0D8h+var_88]
0x18002e865  call    ??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z; _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)
0x18002e86a  mov     eax, cs:dword_180069C38
0x18002e870  mov     dword ptr [rsp+0D8h+var_98], eax
0x18002e874  mov     [rsp+0D8h+var_A0], rsi; unsigned __int16 *
0x18002e879  mov     [rsp+0D8h+var_A8], rsi; char *
0x18002e87e  lea     rax, aOnesettingsonl_2; "OneSettingsOnlineScansAllowedInInterval"...
0x18002e885  mov     [rsp+0D8h+var_B0], rax; unsigned __int16 *
0x18002e88a  mov     [rsp+0D8h+var_B8], ebx; int
0x18002e88e  mov     r9, rdi; char *
0x18002e891  mov     r8d, 8AFh; unsigned int
0x18002e897  mov     rdx, r14; char *
0x18002e89a  mov     ecx, r15d; unsigned int
0x18002e89d  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18002e8a2  mov     r9, r12
0x18002e8a5  lea     r8, qword_180069C28
0x18002e8ac  lea     rdx, aOnlinescancool; "ONLINESCANCOOLDOWNINMINUTES"
0x18002e8b3  mov     rcx, [rsp+0D8h+var_88]
0x18002e8b8  call    ??$_GetOneSettingsNumberValue@_J@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_J_J3@Z; _GetOneSettingsNumberValue<__int64>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,__int64 &,__int64,__int64)
0x18002e8bd  mov     rax, cs:qword_180069C28
0x18002e8c4  cmp     rax, rbx
0x18002e8c7  jnz     short loc_18002E901
0x18002e8c9  mov     [rsp+0D8h+var_A0], rsi; unsigned __int16 *
0x18002e8ce  mov     [rsp+0D8h+var_A8], rsi; char *
0x18002e8d3  lea     rax, aOnlineCooldown; "Online cooldown functionality turned of"...
0x18002e8da  mov     [rsp+0D8h+var_B0], rax; unsigned __int16 *
0x18002e8df  mov     [rsp+0D8h+var_B8], ebx; int
0x18002e8e3  mov     r9, rdi; char *
0x18002e8e6  mov     r8d, 8B3h; unsigned int
0x18002e8ec  mov     rdx, r14; char *
0x18002e8ef  lea     ecx, [rbx+4]; unsigned int
0x18002e8f2  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18002e8f7  mov     rax, rsi
0x18002e8fa  mov     cs:qword_180069C28, rax
0x18002e901  mov     [rsp+0D8h+var_98], rax
0x18002e906  mov     [rsp+0D8h+var_A0], rsi; unsigned __int16 *
0x18002e90b  mov     [rsp+0D8h+var_A8], rsi; char *
0x18002e910  lea     rax, aOnesettingsonl_0; "OneSettingsOnlineScanCooldown (in secon"...
0x18002e917  mov     [rsp+0D8h+var_B0], rax; unsigned __int16 *
0x18002e91c  mov     [rsp+0D8h+var_B8], ebx; int
0x18002e920  mov     r9, rdi; char *
0x18002e923  mov     r8d, 8B6h; unsigned int
0x18002e929  mov     rdx, r14; char *
0x18002e92c  mov     ecx, r15d; unsigned int
0x18002e92f  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18002e934  lea     r8, qword_18006A4A8
0x18002e93b  lea     rdx, aMsixvcarmsuppo; "MSIXVCARMSUPPORTENABLED"
0x18002e942  mov     rcx, [rsp+0D8h+var_88]
0x18002e947  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002e94c  lea     r8, qword_18006A4B0
0x18002e953  lea     rdx, aInteractiveall; "INTERACTIVEALLOWLIST"
0x18002e95a  mov     rcx, [rsp+0D8h+var_88]
0x18002e95f  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002e964  lea     r8, qword_18006A4B8
0x18002e96b  lea     rdx, aInteractivedis_1; "INTERACTIVEDISALLOWLIST"
0x18002e972  mov     rcx, [rsp+0D8h+var_88]
0x18002e977  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002e97c  lea     r8, qword_18006A4D8
0x18002e983  lea     rdx, aBackgroundupda; "BACKGROUNDUPDATECALLERLIST"
0x18002e98a  mov     rcx, [rsp+0D8h+var_88]
0x18002e98f  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002e994  lea     r8, qword_18006A4E0
0x18002e99b  lea     rdx, aImmediateretry_3; "IMMEDIATERETRYDOWNLOADERRORLIST"
0x18002e9a2  mov     rcx, [rsp+0D8h+var_88]
0x18002e9a7  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002e9ac  mov     r13d, 0BB8h
0x18002e9b2  mov     [rsp+0D8h+var_B8], r13d
0x18002e9b7  lea     r8, dword_180083C60
0x18002e9be  lea     rdx, aImmediateretry_7; "IMMEDIATERETRYDOWNLOADDELAYINMILLISECON"...
0x18002e9c5  mov     rcx, [rsp+0D8h+var_88]
0x18002e9ca  call    ??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z; _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)
0x18002e9cf  lea     r8, qword_18006A4E8
0x18002e9d6  lea     rdx, aImmediateretry_5; "IMMEDIATERETRYSCANERRORLIST"
0x18002e9dd  mov     rcx, [rsp+0D8h+var_88]
0x18002e9e2  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002e9e7  mov     [rsp+0D8h+var_B8], r13d
0x18002e9ec  lea     r8, dword_180083C5C
0x18002e9f3  lea     rdx, aImmediateretry_4; "IMMEDIATERETRYSCANDELAYINMILLISECONDS"
0x18002e9fa  mov     rcx, [rsp+0D8h+var_88]
0x18002e9ff  call    ??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z; _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)
0x18002ea04  lea     r8, qword_18006A4F0
0x18002ea0b  lea     rdx, aImmediateretry_6; "IMMEDIATERETRYACQUIRELICENSEERRORLIST"
0x18002ea12  mov     rcx, [rsp+0D8h+var_88]
0x18002ea17  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002ea1c  mov     [rsp+0D8h+var_B8], r13d
0x18002ea21  lea     r8, dword_180083C58
0x18002ea28  lea     rdx, aImmediateretry; "IMMEDIATERETRYACQUIRELICENSEDELAYINMILL"...
0x18002ea2f  mov     rcx, [rsp+0D8h+var_88]
0x18002ea34  call    ??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z; _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)
0x18002ea39  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ImmediateRetryInstall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ImmediateRetryInstall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmediateRetryInstall> `wil::Feature<__WilFeatureTraits_Feature_ImmediateRetryInstall>::GetImpl(void)'::`2'::impl
0x18002ea40  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ImmediateRetryInstall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ImmediateRetryInstall>::__private_IsEnabled(void)
0x18002ea45  test    al, al
0x18002ea47  jz      short loc_18002EA61
0x18002ea49  lea     r8, qword_18006A4F8
0x18002ea50  lea     rdx, aImmediateretry_1; "IMMEDIATERETRYINSTALLERRORLIST"
0x18002ea57  mov     rcx, [rsp+0D8h+var_88]
0x18002ea5c  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002ea61  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixImmediateRetryInstall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixImmediateRetryInstall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixImmediateRetryInstall> `wil::Feature<__WilFeatureTraits_Feature_FixImmediateRetryInstall>::GetImpl(void)'::`2'::impl
0x18002ea68  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixImmediateRetryInstall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixImmediateRetryInstall>::__private_IsEnabled(void)
0x18002ea6d  test    al, al
0x18002ea6f  jz      short loc_18002EA89
0x18002ea71  lea     r8, qword_18006A4F8
0x18002ea78  lea     rdx, aImmediateretry_1; "IMMEDIATERETRYINSTALLERRORLIST"
0x18002ea7f  mov     rcx, [rsp+0D8h+var_88]
0x18002ea84  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002ea89  mov     [rsp+0D8h+var_B8], r13d
0x18002ea8e  lea     r8, dword_180083C54
0x18002ea95  lea     rdx, aImmediateretry_0; "IMMEDIATERETRYINSTALLDELAYINMILLISECOND"...
0x18002ea9c  mov     rcx, [rsp+0D8h+var_88]
0x18002eaa1  call    ??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z; _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)
0x18002eaa6  lea     r8, qword_18006A508
0x18002eaad  lea     rdx, aNetworkissuese; "NETWORKISSUESERRORLIST"
0x18002eab4  mov     rcx, [rsp+0D8h+var_88]
0x18002eab9  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002eabe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PreSearchForPackages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PreSearchForPackages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreSearchForPackages> `wil::Feature<__WilFeatureTraits_Feature_PreSearchForPackages>::GetImpl(void)'::`2'::impl
0x18002eac5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PreSearchForPackages@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreSearchForPackages>::__private_IsEnabled(void)
0x18002eaca  test    al, al
0x18002eacc  jz      short loc_18002EAE6
0x18002eace  lea     r8, byte_180083C4F; bool *
0x18002ead5  lea     rdx, aPresearchupdat; "PRESEARCHUPDATEPACKAGEENABLED"
0x18002eadc  mov     rcx, [rsp+0D8h+var_88]; struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *
0x18002eae1  call    ?_GetOneSettingsBooleanValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_N@Z; _GetOneSettingsBooleanValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,bool &)
0x18002eae6  mov     [rsp+0D8h+var_B8], esi
0x18002eaea  lea     r8, dword_180069C20
0x18002eaf1  lea     rdx, aPresearchonlin; "PRESEARCHONLINESCANTHRESHOLDINMINUTES"
0x18002eaf8  mov     rcx, [rsp+0D8h+var_88]
0x18002eafd  call    ??$_GetOneSettingsNumberValue@I@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAI_JI@Z; _GetOneSettingsNumberValue<uint>(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,uint &,__int64,uint)
0x18002eb02  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SurfaceWUUpdateId@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SurfaceWUUpdateId@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SurfaceWUUpdateId> `wil::Feature<__WilFeatureTraits_Feature_SurfaceWUUpdateId>::GetImpl(void)'::`2'::impl
0x18002eb09  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SurfaceWUUpdateId@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SurfaceWUUpdateId>::__private_IsEnabled(void)
0x18002eb0e  test    al, al
0x18002eb10  jz      short loc_18002EB2A
0x18002eb12  lea     r8, byte_180083C4E; bool *
0x18002eb19  lea     rdx, aDisablewuupdat; "DISABLEWUUPDATEID"
0x18002eb20  mov     rcx, [rsp+0D8h+var_88]; struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *
0x18002eb25  call    ?_GetOneSettingsBooleanValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_N@Z; _GetOneSettingsBooleanValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,bool &)
0x18002eb2a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RefreshOneSettings@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RefreshOneSettings@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RefreshOneSettings> `wil::Feature<__WilFeatureTraits_Feature_RefreshOneSettings>::GetImpl(void)'::`2'::impl
0x18002eb31  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RefreshOneSettings@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RefreshOneSettings>::__private_IsEnabled(void)
0x18002eb36  test    al, al
0x18002eb38  jz      short loc_18002EB52
0x18002eb3a  lea     r8, byte_180083C4D; bool *
0x18002eb41  lea     rdx, aDisableonesett; "DISABLEONESETTINGSREFRESH"
0x18002eb48  mov     rcx, [rsp+0D8h+var_88]; struct Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *
0x18002eb4d  call    ?_GetOneSettingsBooleanValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEA_N@Z; _GetOneSettingsBooleanValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,bool &)
0x18002eb52  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InterActivityRegulationForUpdate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InterActivityRegulationForUpdate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate> `wil::Feature<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate>::GetImpl(void)'::`2'::impl
0x18002eb59  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InterActivityRegulationForUpdate@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InterActivityRegulationForUpdate>::__private_IsEnabled(void)
0x18002eb5e  test    al, al
0x18002eb60  jz      short loc_18002EB92
0x18002eb62  lea     r8, qword_18006A4C0
0x18002eb69  lea     rdx, aInteractiveall_0; "INTERACTIVEALLOWLISTUPDATE"
0x18002eb70  mov     rcx, [rsp+0D8h+var_88]
0x18002eb75  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002eb7a  lea     r8, qword_18006A4C8
0x18002eb81  lea     rdx, aInteractivedis_0; "INTERACTIVEDISALLOWLISTUPDATE"
0x18002eb88  mov     rcx, [rsp+0D8h+var_88]
0x18002eb8d  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002eb92  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall> `wil::Feature<__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall>::GetImpl(void)'::`2'::impl
0x18002eb99  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExcludeMissingProductFromCatalogCall>::__private_IsEnabled(void)
0x18002eb9e  test    al, al
0x18002eba0  jz      loc_18002EC7D
0x18002eba6  mov     [rsp+0D8h+var_68], rsi
0x18002ebab  lea     r8, [rsp+0D8h+var_68]
0x18002ebb0  lea     rdx, aExcludeappidli; "EXCLUDEAPPIDLIST"
0x18002ebb7  mov     rcx, [rsp+0D8h+var_88]
0x18002ebbc  call    ?_GetOneSettingsStringValue@@YAXPEAUIOneSettingsPayload@OneSettings@Flighting@Internal@Windows@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; _GetOneSettingsStringValue(Windows::Internal::Flighting::OneSettings::IOneSettingsPayload *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002ebc1  mov     rdx, [rsp+0D8h+var_68]
0x18002ebc6  test    rdx, rdx
0x18002ebc9  jnz     short loc_18002EBD4
0x18002ebcb  lea     r15d, [rdx+2]
0x18002ebcf  jmp     loc_18002EC71
0x18002ebd4  lea     rcx, [rsp+0D8h+hstringHeader]
0x18002ebd9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002ebde  nop
0x18002ebdf  lea     rcx, [rsp+0D8h+hstringHeader]
0x18002ebe4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ebe9  mov     rcx, qword ptr [rsp+0D8h+hstringHeader.Reserved+10h]
0x18002ebf1  lea     r8, [rax+rcx*2]
0x18002ebf5  mov     rcx, cs:__imp_towupper
0x18002ebfc  mov     qword ptr [rsp+0D8h+var_B8], rcx
0x18002ec01  mov     r9, rax
0x18002ec04  mov     rdx, rax
0x18002ec07  lea     rcx, [rsp+0D8h+var_70]
0x18002ec0c  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x18002ec11  lea     rcx, [rsp+0D8h+hstringHeader]
0x18002ec16  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ec1b  nop
0x18002ec1c  mov     r8, rbx
0x18002ec1f  mov     rdx, rax
0x18002ec22  lea     rcx, [rsp+0D8h+var_70]
0x18002ec27  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002ec2c  mov     r15d, 2
0x18002ec32  mov     [rsp+0D8h+var_80], r15d
0x18002ec37  mov     rcx, [rsp+0D8h]; this
0x18002ec3f  cmp     [rsp+0D8h+var_70], rsi
  ... truncated ...
```
