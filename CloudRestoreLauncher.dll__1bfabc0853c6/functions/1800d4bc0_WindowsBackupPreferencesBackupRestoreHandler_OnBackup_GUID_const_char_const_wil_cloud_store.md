# WindowsBackupPreferencesBackupRestoreHandler::OnBackup(_GUID const &,char const *,wil::cloud_store)

- ea: `0x1800d4bc0`
- end: `0x1800d526a`
- name: `?OnBackup@WindowsBackupPreferencesBackupRestoreHandler@@UEAAXAEBU_GUID@@PEBDVcloud_store@wil@@@Z`
- size: `1706`
- prototype: ``
- caller_count: `0`
- callee_count: `49`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000c6e0`
- `0x180012c0c`
- `0x1800154e4`
- `0x1800161ec`
- `0x1800162a4`
- `0x18001cf64`
- `0x18001d0a8`
- `0x18001faa8`
- `0x18002236c`
- `0x180027000`
- `0x180031dc0`
- `0x180036a3c`
- `0x18004623c`
- `0x1800462bc`
- `0x180066c34`
- `0x1800920d8`
- `0x180096af4`
- `0x1800974b0`
- `0x180097550`
- `0x1800977e8`
- `0x1800a80dc`
- `0x1800ad09c`
- `0x1800d0b4c`
- `0x1800d0de4`
- `0x1800d1050`
- `0x1800d11a0`
- `0x1800d122c`
- `0x1800d13cc`
- `0x1800d1588`
- `0x1800d256c`
- `0x1800d2f3c`
- `0x1800d3510`
- `0x1800d3d50`
- `0x1800d3d78`
- `0x1800d3e80`
- `0x1800d3ec8`
- `0x1800d3f44`
- `0x1800d4024`
- `0x1800d41b4`
- `0x1800d4ad0`
- `0x1800d4bc0`
- `0x1800d58c0`
- `0x1800d5af8`
- `0x1800d5bb0`
- `0x1800d6234`
- `0x1800d6270`
- `0x1800d689c`
- `0x1800d6a2c`
- `0x1800d6ac4`

## string_xrefs

- `0x1800d4d9f`: `Schema Load Completed`
- `0x1800d51df`: `Backup Completed`
- `0x1800d517d`: `Schema save Completed`
- `0x1800d51c3`: `Schema save Completed`
- `0x1800d4f7f`: `GetPolicy Completed`
- `0x1800d503c`: `GetPolicy Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall WindowsBackupPreferencesBackupRestoreHandler::OnBackup(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        wil::cloud_store *a4)
{
  int v6; // esi
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  char v10; // dl
  int v11; // ecx
  wchar_t **v12; // r14
  int *v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rcx
  int Policy; // ebx
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  int *v21; // rax
  int v22; // edx
  int v23; // ecx
  _BYTE *v24; // rcx
  __int64 v25; // rax
  int *v26; // rax
  int v27; // ecx
  char IsEnabled; // al
  const unsigned __int16 *v29; // rdx
  __int64 v30; // rbx
  __int64 v31; // rax
  int *v32; // rax
  __int64 v33; // rax
  _BYTE *v34; // rcx
  __int64 v35; // rax
  int *v36; // rax
  char v37; // al
  const wchar_t *v38; // rdx
  const wchar_t *v39; // rcx
  __int64 v40; // r8
  wil::cloud_store *v41; // r15
  char IsAllTogglesPolicyCovered; // al
  char v43; // bl
  int v44; // eax
  int v45; // edx
  int v46; // ecx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v52[2]; // [rsp+40h] [rbp-C0h] BYREF
  wil::cloud_store *v53[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v54[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v55[16]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v56; // [rsp+78h] [rbp-88h]
  _BYTE v57[8]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v58; // [rsp+88h] [rbp-78h]
  int v59; // [rsp+8Ch] [rbp-74h]
  char v60; // [rsp+90h] [rbp-70h]
  _BYTE v61[16]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-58h]
  _BYTE v63[8]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-48h]
  char v65; // [rsp+C0h] [rbp-40h]
  _QWORD v66[4]; // [rsp+C8h] [rbp-38h] BYREF
  char v67; // [rsp+E8h] [rbp-18h]
  wil::cloud_store *v68; // [rsp+F0h] [rbp-10h]
  _BYTE v69[56]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v70; // [rsp+138h] [rbp+38h]
  _QWORD v71[4]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v72[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v73[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v74[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v75[42]; // [rsp+1C0h] [rbp+C0h] BYREF

  v53[0] = a4;
  v68 = a4;
  v6 = 0;
  LODWORD(v50) = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsBackupPrefrencesBackupRestoreHandler>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_WindowsBackupPrefrencesBackupRestoreHandler>::GetImpl'::`2'::impl,
    a2);
  wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v75);
  v75[0] = &CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::`vftable';
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::StartActivity(
      (CloudRestoreLauncherTelemetry::BackupPrefrencesActivity *)v75,
      L"Backup Started");
  v50 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_WindowsBackupPrefrencesSettingsBackupTipTests,_tip_WindowsBackupPrefrencesSettingsBackupTipTests>>::start_and_watch_errors(
    &v50,
    v69);
  wil::com_ptr_t<tip2::details::merged_data<_tip_WindowsBackupPrefrencesSettingsBackupTipTests,_tip_WindowsBackupPrefrencesSettingsBackupTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WindowsBackupPrefrencesSettingsBackupTipTests,_tip_WindowsBackupPrefrencesSettingsBackupTipTests>,wil::err_returncode_policy>(&v50);
  v7 = v70;
  v51 = v70;
  if ( v70 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v70 + 328));
    v7 = v51;
  }
  tip2::details::shared_data<0,0,0>::begin_update(v7 + 8);
  v66[0] = v75;
  v66[1] = a1;
  v66[2] = &v51;
  v66[3] = v69;
  v67 = 1;
  v50 = 0;
  v52[0] = 0;
  v71[0] = 0;
  winrt::Windows::Internal::Storage::Cloud::Policy::CloudStorePolicy::CloudStorePolicy(
    (winrt::Windows::Internal::Storage::Cloud::Policy::CloudStorePolicy *)v54,
    (const struct winrt::Windows::Security::Credentials::WebAccount *)&v50,
    (const struct winrt::param::hstring *)v71);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v52);
  _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v50);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::StartActivity(
      (CloudRestoreLauncherTelemetry::BackupPrefrencesActivity *)v75,
      L"Backup Started");
  wil::cloud_store::load<Windows::Data::WindowsBackup::Preference::Toggles>(a4, v61, 2);
  std::_Tree<std::_Tmap_traits<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>>::_Tree<std::_Tmap_traits<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>>(
    v55,
    v61);
  v56 = v62;
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>(
    v57,
    v63);
  v8 = v64;
  v58 = v64;
  v59 = HIDWORD(v64);
  v60 = v65;
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    v9 = std::_String_val<std::_Simple_types<char>>::_Myptr(Windows::Data::WindowsBackup::Preference::Toggles::Schema::metadata);
    McTemplateU0sxt_EventWriteTransfer(v11, (unsigned int)CloudDataLoaded, v9, v62, v10);
  }
  CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::BackupPrefrences_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[22]>(
    v8,
    L"Schema Load Completed");
  v12 = &g_GroupToPermissionScope;
  do
  {
    v13 = (int *)&g_PermissionScopes;
    do
    {
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                              *(_QWORD *)v13,
                              *((_QWORD *)v13 + 1),
                              v12[2],
                              v12[3]) )
        break;
      v13 += 12;
    }
    while ( v13 != &load_config_used );
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement>::GetImpl'::`2'::impl) )
    {
      v52[0] = *(_QWORD *)v13;
      CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::BackupPrefrences_CloudStorePolicyAPIActivity<unsigned short const (&)[18],unsigned short const *>(
        v14,
        v52);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix>::GetImpl'::`2'::impl) )
      {
        if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
          McTemplateU0qz_EventWriteTransfer(v15, BackupPrefrences_CloudStorePolicyAPICallEvent_V2, 0, *(_QWORD *)v13);
      }
      else if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      {
        McTemplateU0zz_EventWriteTransfer(
          v15,
          BackupPrefrences_CloudStorePolicyAPICallEvent,
          L"GetPolicy Started",
          *(_QWORD *)v13);
      }
    }
    winrt::param::hstring::hstring((winrt::param::hstring *)v71, *(const unsigned __int16 *const *)v13);
    Policy = winrt::impl::consume_Windows_Internal_Storage_Cloud_Policy_ICloudStorePolicy<winrt::Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy>::GetPolicy(
               v54,
               v71);
    v17 = std::wstring::wstring(v71, *(_QWORD *)v13);
    if ( Policy == 2 )
      *(_DWORD *)std::map<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>::operator[](
                   v55,
                   v17) = 1;
    else
      *(_DWORD *)std::map<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>::operator[](
                   v55,
                   v17) = Policy;
    std::wstring::_Tidy_deallocate(v71);
    v18 = v51;
    v19 = std::wstring::wstring(v71, *(_QWORD *)v13);
    std::vector<std::wstring>::push_back(v18 + 280, v19);
    std::wstring::_Tidy_deallocate(v71);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix>::GetImpl'::`2'::impl) )
    {
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      {
        v20 = std::wstring::wstring(v72, *(_QWORD *)v13);
        v6 |= 1u;
        LODWORD(v50) = v6;
        v21 = (int *)std::map<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>::operator[](
                       v55,
                       v20);
        McTemplateU0qzz_EventWriteTransfer(v23, v22, 1, *(_QWORD *)v13, (__int64)off_18017A0E0[*v21]);
      }
      if ( (v6 & 1) != 0 )
      {
        v6 &= ~1u;
        v24 = v72;
LABEL_31:
        std::wstring::_Tidy_deallocate(v24);
      }
    }
    else
    {
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      {
        v25 = std::wstring::wstring(v71, *(_QWORD *)v13);
        v6 |= 2u;
        LODWORD(v50) = v6;
        v26 = (int *)std::map<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>::operator[](
                       v55,
                       v25);
        McTemplateU0zzz_EventWriteTransfer(
          v27,
          (unsigned int)BackupPrefrences_CloudStorePolicyAPIDataEvent,
          (unsigned int)L"GetPolicy Completed",
          *(_QWORD *)v13,
          (__int64)off_18017A0E0[*v26]);
      }
      if ( (v6 & 2) != 0 )
      {
        v6 &= ~2u;
        v24 = v71;
        goto LABEL_31;
      }
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement>::GetImpl'::`2'::impl);
    v29 = *(const unsigned __int16 **)v13;
    if ( IsEnabled )
    {
      v30 = v51;
      v31 = std::wstring::wstring(v74, v29);
      v32 = (int *)std::map<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>::operator[](
                     v55,
                     v31);
      v33 = std::wstring::wstring(v73, off_18017A0E0[*v32]);
      std::vector<std::wstring>::push_back(v30 + 304, v33);
      std::wstring::_Tidy_deallocate(v73);
      v34 = v74;
    }
    else
    {
      v35 = std::wstring::wstring(v71, v29);
      v36 = (int *)std::map<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>::operator[](
                     v55,
                     v35);
      v52[0] = *(_QWORD *)v13;
      CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::BackupPrefrences_CloudStorePolicyAPIActivity<unsigned short const (&)[20],unsigned short const *,unsigned short * &>(
        L"GetPolicy Completed",
        v52,
        &off_18017A0E0[*v36]);
      v34 = v71;
    }
    std::wstring::_Tidy_deallocate(v34);
    v12 += 4;
  }
  while ( v12 != &g_PermissionScopes );
  v37 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl);
  v41 = v53[0];
  if ( v37 )
    CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::BackupPrefrences_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[32],unsigned short const (&)[8]>(
      v39,
      v38,
      v40);
  IsAllTogglesPolicyCovered = WindowsBackupPreferencesBackupRestoreHandler::IsAllTogglesPolicyCovered(v39, v51 + 280);
  *(_BYTE *)(v51 + 272) = IsAllTogglesPolicyCovered;
  *(_DWORD *)(v51 + 276) = (int)(100 * ((__int64)(*(_QWORD *)(v51 + 288) - *(_QWORD *)(v51 + 280)) >> 5)) / 24;
  std::_Tree<std::_Tmap_traits<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>>::_Tree<std::_Tmap_traits<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>>(
    v52,
    v55);
  std::_Tree<std::_Tmap_traits<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>>::_Tree<std::_Tmap_traits<std::wstring,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,enum Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>>(
    v53,
    v61);
  v43 = Windows::Data::NetworkUX::Cellular::ImsiMeteredPairs::operator==(v52, v53);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,enum Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,enum Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue>,void *>>>(
    v53,
    v53);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,enum Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,enum Windows::Data::NetworkUX::Cellular::_bond_enumerators::MeteredValue::MeteredValue>,void *>>>(
    v52,
    v52);
  if ( v43 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BRCLogImprovements>::GetImpl'::`2'::impl)
      && (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v48, CloudDataSkipSave, L"Windows Backup Preferences");
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
      CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::BackupPrefrences_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[21]>();
    wil::cloud_store::save<Windows::Data::WindowsBackup::Preference::Toggles>(v41, v53, v55);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      v44 = std::_String_val<std::_Simple_types<char>>::_Myptr(Windows::Data::WindowsBackup::Preference::Toggles::Schema::metadata);
      McTemplateU0sxx_EventWriteTransfer(v46, v45, v44, v56, (char)v53[0]);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
      CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::BackupPrefrences_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[22]>(
        v47,
        L"Schema save Completed");
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::BackupPrefrences_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[22]>(
      v49,
      L"Schema save Completed");
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::Stop(
      (CloudRestoreLauncherTelemetry::BackupPrefrencesActivity *)v75,
      L"Backup Completed");
  wil::cloud_store_data<Windows::Data::WindowsBackup::Preference::Toggles>::~cloud_store_data<Windows::Data::WindowsBackup::Preference::Toggles>(v55);
  wil::cloud_store_data<Windows::Data::WindowsBackup::Preference::Toggles>::~cloud_store_data<Windows::Data::WindowsBackup::Preference::Toggles>(v61);
  _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v54);
  v67 = 0;
  _lambda_40921c60176e5341fc940d62c6fca9a4_::operator()(v66);
  tip2::test_data_control<tip2::details::merged_data<_tip_WindowsBackupPrefrencesSettingsBackupTipTests,_tip_WindowsBackupPrefrencesSettingsBackupTipTests>>::~test_data_control<tip2::details::merged_data<_tip_WindowsBackupPrefrencesSettingsBackupTipTests,_tip_WindowsBackupPrefrencesSettingsBackupTipTests>>(&v51);
  tip2::test_watcher<tip2::details::merged_data<_tip_WindowsBackupPrefrencesSettingsBackupTipTests,_tip_WindowsBackupPrefrencesSettingsBackupTipTests>>::~test_watcher<tip2::details::merged_data<_tip_WindowsBackupPrefrencesSettingsBackupTipTests,_tip_WindowsBackupPrefrencesSettingsBackupTipTests>>(v69);
  CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::~BackupPrefrencesActivity((CloudRestoreLauncherTelemetry::BackupPrefrencesActivity *)v75);
  wil::cloud_store::~cloud_store(v41);
}

```

## disassembly

```asm
0x1800d4bc0  push    rbp
0x1800d4bc2  push    rbx
0x1800d4bc3  push    rsi
0x1800d4bc4  push    rdi
0x1800d4bc5  push    r14
0x1800d4bc7  push    r15
0x1800d4bc9  lea     rbp, [rsp-228h]
0x1800d4bd1  sub     rsp, 328h
0x1800d4bd8  mov     rax, cs:__security_cookie
0x1800d4bdf  xor     rax, rsp
0x1800d4be2  mov     [rbp+250h+var_40], rax
0x1800d4be9  mov     r15, r9
0x1800d4bec  mov     [rsp+350h+var_300], r9
0x1800d4bf1  mov     rbx, rcx
0x1800d4bf4  mov     [rbp+250h+var_260], r9
0x1800d4bf8  xor     esi, esi
0x1800d4bfa  mov     dword ptr [rsp+350h+var_320], esi
0x1800d4bfe  mov     dl, 1
0x1800d4c00  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsBackupPrefrencesBackupRestoreHandler@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsBackupPrefrencesBackupRestoreHandler@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsBackupPrefrencesBackupRestoreHandler> `wil::Feature<__WilFeatureTraits_Feature_WindowsBackupPrefrencesBackupRestoreHandler>::GetImpl(void)'::`2'::impl
0x1800d4c07  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsBackupPrefrencesBackupRestoreHandler@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsBackupPrefrencesBackupRestoreHandler>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800d4c0c  lea     rdx, aBackupprefrenc; "BackupPrefrencesActivity"
0x1800d4c13  lea     rcx, [rbp+250h+var_190]; struct wil::details::IFailureCallback *
0x1800d4c1a  call    ??0?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800d4c1f  lea     rax, ??_7BackupPrefrencesActivity@CloudRestoreLauncherTelemetry@@6B@; const CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::`vftable'
0x1800d4c26  mov     [rbp+250h+var_190], rax
0x1800d4c2d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800d4c34  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800d4c39  test    al, al
0x1800d4c3b  jz      short loc_1800D4C50
0x1800d4c3d  lea     rdx, aBackupStarted; "Backup Started"
0x1800d4c44  lea     rcx, [rbp+250h+var_190]; this
0x1800d4c4b  call    ?StartActivity@BackupPrefrencesActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::StartActivity(ushort const *)
0x1800d4c50  mov     [rsp+350h+var_320], 0
0x1800d4c59  lea     rdx, [rbp+250h+var_250]
0x1800d4c5d  lea     rcx, [rsp+350h+var_320]
0x1800d4c62  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_WindowsBackupPrefrencesSettingsBackupTipTests@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_WindowsBackupPrefrencesSettingsBackupTipTests@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_WindowsBackupPrefrencesSettingsBackupTipTests,_tip_WindowsBackupPrefrencesSettingsBackupTipTests>>::start_and_watch_errors(void)
0x1800d4c67  lea     rcx, [rsp+350h+var_320]
0x1800d4c6c  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WindowsBackupPrefrencesSettingsBackupTipTests@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WindowsBackupPrefrencesSettingsBackupTipTests,_tip_WindowsBackupPrefrencesSettingsBackupTipTests>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WindowsBackupPrefrencesSettingsBackupTipTests,_tip_WindowsBackupPrefrencesSettingsBackupTipTests>,wil::err_returncode_policy>(void)
0x1800d4c71  nop
0x1800d4c72  mov     rcx, [rbp+250h+var_218]
0x1800d4c76  mov     [rsp+350h+var_318], rcx
0x1800d4c7b  test    rcx, rcx
0x1800d4c7e  jz      short loc_1800D4C8C
0x1800d4c80  lock inc dword ptr [rcx+148h]
0x1800d4c87  mov     rcx, [rsp+350h+var_318]
0x1800d4c8c  add     rcx, 8
0x1800d4c90  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800d4c95  nop
0x1800d4c96  lea     rax, [rbp+250h+var_190]
0x1800d4c9d  mov     [rbp+250h+var_288], rax
0x1800d4ca1  mov     [rbp+250h+var_280], rbx
0x1800d4ca5  lea     rax, [rsp+350h+var_318]
0x1800d4caa  mov     [rbp+250h+var_278], rax
0x1800d4cae  lea     rax, [rbp+250h+var_250]
0x1800d4cb2  mov     [rbp+250h+var_270], rax
0x1800d4cb6  mov     [rbp+250h+var_268], 1
0x1800d4cba  mov     [rsp+350h+var_320], 0
0x1800d4cc3  mov     [rsp+350h+var_310], 0
0x1800d4ccc  mov     [rbp+250h+var_210], 0
0x1800d4cd4  lea     r8, [rbp+250h+var_210]; struct winrt::param::hstring *
0x1800d4cd8  lea     rdx, [rsp+350h+var_320]; struct winrt::Windows::Security::Credentials::WebAccount *
0x1800d4cdd  lea     rcx, [rsp+350h+var_2F0]; this
0x1800d4ce2  call    ??0CloudStorePolicy@Policy@Cloud@Storage@Internal@Windows@winrt@@QEAA@AEBUWebAccount@Credentials@Security@56@AEBUhstring@param@6@@Z; winrt::Windows::Internal::Storage::Cloud::Policy::CloudStorePolicy::CloudStorePolicy(winrt::Windows::Security::Credentials::WebAccount const &,winrt::param::hstring const &)
0x1800d4ce7  nop
0x1800d4ce8  lea     rcx, [rsp+350h+var_310]
0x1800d4ced  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800d4cf2  nop
0x1800d4cf3  lea     rcx, [rsp+350h+var_320]; this
0x1800d4cf8  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800d4cfd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800d4d04  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800d4d09  test    al, al
0x1800d4d0b  jnz     short loc_1800D4D20
0x1800d4d0d  lea     rdx, aBackupStarted; "Backup Started"
0x1800d4d14  lea     rcx, [rbp+250h+var_190]; this
0x1800d4d1b  call    ?StartActivity@BackupPrefrencesActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::StartActivity(ushort const *)
0x1800d4d20  mov     r8d, 2
0x1800d4d26  lea     rdx, [rbp+250h+var_2B8]
0x1800d4d2a  mov     rcx, r15
0x1800d4d2d  call    ??$load@UToggles@Preference@WindowsBackup@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UToggles@Preference@WindowsBackup@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::WindowsBackup::Preference::Toggles>(wil::cloud_store_load_options,char const *)
0x1800d4d32  nop
0x1800d4d33  lea     rdx, [rbp+250h+var_2B8]
0x1800d4d37  lea     rcx, [rsp+350h+var_2E8]
0x1800d4d3c  call    ??$?0V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@@std@@PEAX@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@@std@@@2@$0A@@std@@@std@@QEAA@AEBV01@$$QEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@@std@@PEAX@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>>::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>>(std::_Tree<std::_Tmap_traits<std::wstring,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>>,0>> const &,std::allocator<std::_Tree_node<std::pair<std::wstring const,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>,void *>> &&)
0x1800d4d41  mov     rax, [rbp+250h+var_2A8]
0x1800d4d45  mov     [rsp+350h+var_2D8], rax
0x1800d4d4a  lea     rdx, [rbp+250h+var_2A0]
0x1800d4d4e  lea     rcx, [rbp+250h+var_2D0]
0x1800d4d52  call    ??0?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>(wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy> const &)
0x1800d4d57  mov     rcx, [rbp+250h+var_298]
0x1800d4d5b  mov     byte ptr [rbp+250h+var_2C8], cl
0x1800d4d5e  mov     al, byte ptr [rbp+250h+var_298+1]
0x1800d4d61  mov     byte ptr [rbp+250h+var_2C8+1], al
0x1800d4d64  mov     eax, dword ptr [rbp+250h+var_298+4]
0x1800d4d67  mov     [rbp+250h+var_2C4], eax
0x1800d4d6a  mov     al, [rbp+250h+var_290]
0x1800d4d6d  mov     [rbp+250h+var_2C0], al
0x1800d4d70  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800d4d77  jz      short loc_1800D4D9F
0x1800d4d79  movzx   edx, cl
0x1800d4d7c  lea     rcx, ?metadata@Schema@Toggles@Preference@WindowsBackup@Data@Windows@@2UMetadata@bond@@B; bond::Metadata const Windows::Data::WindowsBackup::Preference::Toggles::Schema::metadata
0x1800d4d83  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800d4d88  mov     r8, rax
0x1800d4d8b  mov     dword ptr [rsp+350h+var_330], edx
0x1800d4d8f  mov     r9, [rbp+250h+var_2A8]
0x1800d4d93  lea     rdx, CloudDataLoaded
0x1800d4d9a  call    McTemplateU0sxt_EventWriteTransfer
0x1800d4d9f  lea     rdx, aSchemaLoadComp_0; "Schema Load Completed"
0x1800d4da6  call    ??$BackupPrefrences_BondSchemaActivity@AEAY06$$CBGAEAY0BG@$$CBG@BackupPrefrencesActivity@CloudRestoreLauncherTelemetry@@SAXAEAY06$$CBGAEAY0BG@$$CBG@Z; CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::BackupPrefrences_BondSchemaActivity<ushort const (&)[7],ushort const (&)[22]>(ushort const (&)[7],ushort const (&)[22])
0x1800d4dab  lea     r14, ?g_GroupToPermissionScope@@3V?$array@UPermissionGroup@@$0BI@@std@@B; std::array<PermissionGroup,24> const g_GroupToPermissionScope
0x1800d4db2  lea     r15, off_18017A0E0; "SyncEnabled"
0x1800d4db9  lea     rdi, ?g_PermissionScopes@@3V?$array@UPermissionScopeItem@@$0BJ@@std@@B; std::array<PermissionScopeItem,25> const g_PermissionScopes
0x1800d4dc0  mov     r9, [r14+18h]
0x1800d4dc4  mov     r8, [r14+10h]
0x1800d4dc8  mov     rdx, [rdi+8]
0x1800d4dcc  mov     rcx, [rdi]
0x1800d4dcf  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800d4dd4  test    al, al
0x1800d4dd6  jnz     short loc_1800D4DE8
0x1800d4dd8  add     rdi, 30h ; '0'
0x1800d4ddc  lea     rax, _load_config_used
0x1800d4de3  cmp     rdi, rax
0x1800d4de6  jnz     short loc_1800D4DC0
0x1800d4de8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement> `wil::Feature<__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement>::GetImpl(void)'::`2'::impl
0x1800d4def  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement>::__private_IsEnabled(void)
0x1800d4df4  test    al, al
0x1800d4df6  jnz     short loc_1800D4E56
0x1800d4df8  mov     rax, [rdi]
0x1800d4dfb  mov     [rsp+350h+var_310], rax
0x1800d4e00  lea     rdx, [rsp+350h+var_310]
0x1800d4e05  call    ??$BackupPrefrences_CloudStorePolicyAPIActivity@AEAY0BC@$$CBGPEBG@BackupPrefrencesActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BC@$$CBG$$QEAPEBG@Z; CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::BackupPrefrences_CloudStorePolicyAPIActivity<ushort const (&)[18],ushort const *>(ushort const (&)[18],ushort const * &&)
0x1800d4e0a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix> `wil::Feature<__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix>::GetImpl(void)'::`2'::impl
0x1800d4e11  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix>::__private_IsEnabled(void)
0x1800d4e16  test    al, al
0x1800d4e18  jz      short loc_1800D4E37
0x1800d4e1a  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800d4e21  jz      short loc_1800D4E56
0x1800d4e23  mov     r9, [rdi]
0x1800d4e26  xor     r8d, r8d
0x1800d4e29  lea     rdx, BackupPrefrences_CloudStorePolicyAPICallEvent_V2
0x1800d4e30  call    McTemplateU0qz_EventWriteTransfer
0x1800d4e35  jmp     short loc_1800D4E56
0x1800d4e37  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800d4e3e  jz      short loc_1800D4E56
0x1800d4e40  mov     r9, [rdi]
0x1800d4e43  lea     r8, aGetpolicyStart; "GetPolicy Started"
0x1800d4e4a  lea     rdx, BackupPrefrences_CloudStorePolicyAPICallEvent
0x1800d4e51  call    McTemplateU0zz_EventWriteTransfer
0x1800d4e56  mov     rdx, [rdi]; unsigned __int16 *
0x1800d4e59  lea     rcx, [rbp+250h+var_210]; this
0x1800d4e5d  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800d4e62  lea     rdx, [rbp+250h+var_210]
0x1800d4e66  lea     rcx, [rsp+350h+var_2F0]
0x1800d4e6b  call    ?GetPolicy@?$consume_Windows_Internal_Storage_Cloud_Policy_ICloudStorePolicy@UICloudStorePolicy@Policy@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Internal_Storage_Cloud_Policy_ICloudStorePolicy<winrt::Windows::Internal::Storage::Cloud::Policy::ICloudStorePolicy>::GetPolicy(winrt::param::hstring const &)
0x1800d4e70  mov     ebx, eax
0x1800d4e72  mov     rdx, [rdi]
0x1800d4e75  lea     rcx, [rbp+250h+var_210]
0x1800d4e79  cmp     eax, 2
0x1800d4e7c  jz      short loc_1800D4E95
0x1800d4e7e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d4e83  nop
0x1800d4e84  mov     rdx, rax
0x1800d4e87  lea     rcx, [rsp+350h+var_2E8]
0x1800d4e8c  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@@std@@@2@@std@@QEAAAEAW4CloudStorePolicyEnum@2_bond_enumerators@Preference@WindowsBackup@Data@Windows@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>::operator[](std::wstring &&)
0x1800d4e91  mov     [rax], ebx
0x1800d4e93  jmp     short loc_1800D4EAE
0x1800d4e95  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d4e9a  nop
0x1800d4e9b  mov     rdx, rax
0x1800d4e9e  lea     rcx, [rsp+350h+var_2E8]
0x1800d4ea3  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@@std@@@2@@std@@QEAAAEAW4CloudStorePolicyEnum@2_bond_enumerators@Preference@WindowsBackup@Data@Windows@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>::operator[](std::wstring &&)
0x1800d4ea8  mov     dword ptr [rax], 1
0x1800d4eae  lea     rcx, [rbp+250h+var_210]
0x1800d4eb2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d4eb7  mov     rbx, [rsp+350h+var_318]
0x1800d4ebc  mov     rdx, [rdi]
0x1800d4ebf  lea     rcx, [rbp+250h+var_210]
0x1800d4ec3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d4ec8  nop
0x1800d4ec9  mov     rdx, rax
0x1800d4ecc  lea     rcx, [rbx+118h]
0x1800d4ed3  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800d4ed8  nop
0x1800d4ed9  lea     rcx, [rbp+250h+var_210]
0x1800d4edd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d4ee2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix> `wil::Feature<__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix>::GetImpl(void)'::`2'::impl
0x1800d4ee9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudBackupRestore_LocalizationFix>::__private_IsEnabled(void)
0x1800d4eee  test    al, al
0x1800d4ef0  jz      short loc_1800D4F46
0x1800d4ef2  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800d4ef9  jz      short loc_1800D4F37
0x1800d4efb  mov     rdx, [rdi]
0x1800d4efe  lea     rcx, [rbp+250h+var_1F0]
0x1800d4f02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d4f07  nop
0x1800d4f08  or      esi, 1
0x1800d4f0b  mov     dword ptr [rsp+350h+var_320], esi
0x1800d4f0f  mov     rdx, rax
0x1800d4f12  lea     rcx, [rsp+350h+var_2E8]
0x1800d4f17  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@@std@@@2@@std@@QEAAAEAW4CloudStorePolicyEnum@2_bond_enumerators@Preference@WindowsBackup@Data@Windows@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>::operator[](std::wstring &&)
0x1800d4f1c  movsxd  rax, dword ptr [rax]
0x1800d4f1f  mov     rax, [r15+rax*8]
0x1800d4f23  mov     [rsp+350h+var_330], rax
0x1800d4f28  mov     r9, [rdi]
0x1800d4f2b  mov     r8d, 1
0x1800d4f31  call    McTemplateU0qzz_EventWriteTransfer
0x1800d4f36  nop
0x1800d4f37  test    sil, 1
0x1800d4f3b  jz      short loc_1800D4FA5
0x1800d4f3d  and     esi, 0FFFFFFFEh
0x1800d4f40  lea     rcx, [rbp+250h+var_1F0]
0x1800d4f44  jmp     short loc_1800D4FA0
0x1800d4f46  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800d4f4d  jz      short loc_1800D4F93
0x1800d4f4f  mov     rdx, [rdi]
0x1800d4f52  lea     rcx, [rbp+250h+var_210]
0x1800d4f56  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d4f5b  nop
0x1800d4f5c  or      esi, 2
0x1800d4f5f  mov     dword ptr [rsp+350h+var_320], esi
0x1800d4f63  mov     rdx, rax
0x1800d4f66  lea     rcx, [rsp+350h+var_2E8]
0x1800d4f6b  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@@std@@@2@@std@@QEAAAEAW4CloudStorePolicyEnum@2_bond_enumerators@Preference@WindowsBackup@Data@Windows@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>::operator[](std::wstring &&)
0x1800d4f70  movsxd  rax, dword ptr [rax]
0x1800d4f73  mov     rax, [r15+rax*8]
0x1800d4f77  mov     [rsp+350h+var_330], rax
0x1800d4f7c  mov     r9, [rdi]
0x1800d4f7f  lea     r8, aGetpolicyCompl; "GetPolicy Completed"
0x1800d4f86  lea     rdx, BackupPrefrences_CloudStorePolicyAPIDataEvent
0x1800d4f8d  call    McTemplateU0zzz_EventWriteTransfer
0x1800d4f92  nop
0x1800d4f93  test    sil, 2
0x1800d4f97  jz      short loc_1800D4FA5
0x1800d4f99  and     esi, 0FFFFFFFDh
0x1800d4f9c  lea     rcx, [rbp+250h+var_210]
0x1800d4fa0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d4fa5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement> `wil::Feature<__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement>::GetImpl(void)'::`2'::impl
0x1800d4fac  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Backup_Preferences_TelemetryImprovement>::__private_IsEnabled(void)
0x1800d4fb1  mov     rdx, [rdi]
0x1800d4fb4  test    al, al
0x1800d4fb6  jz      short loc_1800D5011
0x1800d4fb8  mov     rbx, [rsp+350h+var_318]
0x1800d4fbd  lea     rcx, [rbp+250h+var_1B0]
0x1800d4fc4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d4fc9  nop
0x1800d4fca  mov     rdx, rax
0x1800d4fcd  lea     rcx, [rsp+350h+var_2E8]
0x1800d4fd2  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@@std@@@2@@std@@QEAAAEAW4CloudStorePolicyEnum@2_bond_enumerators@Preference@WindowsBackup@Data@Windows@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>::operator[](std::wstring &&)
0x1800d4fd7  movsxd  rdx, dword ptr [rax]
0x1800d4fda  mov     rdx, [r15+rdx*8]
0x1800d4fde  lea     rcx, [rbp+250h+var_1D0]
0x1800d4fe5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d4fea  nop
0x1800d4feb  mov     rdx, rax
0x1800d4fee  lea     rcx, [rbx+130h]
0x1800d4ff5  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800d4ffa  nop
0x1800d4ffb  lea     rcx, [rbp+250h+var_1D0]
0x1800d5002  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d5007  nop
0x1800d5008  lea     rcx, [rbp+250h+var_1B0]
0x1800d500f  jmp     short loc_1800D504D
0x1800d5011  lea     rcx, [rbp+250h+var_210]
0x1800d5015  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d501a  nop
0x1800d501b  mov     rdx, rax
0x1800d501e  lea     rcx, [rsp+350h+var_2E8]
0x1800d5023  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CloudStorePolicyEnum@3_bond_enumerators@Preference@WindowsBackup@Data@Windows@@@std@@@2@@std@@QEAAAEAW4CloudStorePolicyEnum@2_bond_enumerators@Preference@WindowsBackup@Data@Windows@@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,Windows::Data::WindowsBackup::Preference::_bond_enumerators::CloudStorePolicyEnum::CloudStorePolicyEnum>::operator[](std::wstring &&)
0x1800d5028  mov     rcx, [rdi]
0x1800d502b  mov     [rsp+350h+var_310], rcx
0x1800d5030  movsxd  rax, dword ptr [rax]
0x1800d5033  lea     r8, [r15+rax*8]
0x1800d5037  lea     rdx, [rsp+350h+var_310]
0x1800d503c  lea     rcx, aGetpolicyCompl; "GetPolicy Completed"
0x1800d5043  call    ??$BackupPrefrences_CloudStorePolicyAPIActivity@AEAY0BE@$$CBGPEBGAEAPEAG@BackupPrefrencesActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BE@$$CBG$$QEAPEBGAEAPEAG@Z; CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::BackupPrefrences_CloudStorePolicyAPIActivity<ushort const (&)[20],ushort const *,ushort * &>(ushort const (&)[20],ushort const * &&,ushort * &)
0x1800d5048  nop
0x1800d5049  lea     rcx, [rbp+250h+var_210]
0x1800d504d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d5052  add     r14, 20h ; ' '
0x1800d5056  lea     rax, ?g_PermissionScopes@@3V?$array@UPermissionScopeItem@@$0BJ@@std@@B; std::array<PermissionScopeItem,25> const g_PermissionScopes
0x1800d505d  cmp     r14, rax
0x1800d5060  jnz     loc_1800D4DB9
0x1800d5066  lea     rdi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800d506d  mov     rcx, rdi
0x1800d5070  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800d5075  test    al, al
0x1800d5077  mov     r15, [rsp+350h+var_300]
0x1800d507c  jz      short loc_1800D5083
0x1800d507e  call    ??$BackupPrefrences_ApiActivity@AEAY0L@$$CBGAEAY0CA@$$CBGAEAY07$$CBG@BackupPrefrencesActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0CA@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::BackupPrefrencesActivity::BackupPrefrences_ApiActivity<ushort const (&)[11],ushort const (&)[32],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[32],ushort const (&)[8])
0x1800d5083  mov     rdx, [rsp+350h+var_318]
0x1800d5088  add     rdx, 118h
0x1800d508f  call    ?IsAllTogglesPolicyCovered@WindowsBackupPreferencesBackupRestoreHandler@@AEAA_NAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; WindowsBackupPreferencesBackupRestoreHandler::IsAllTogglesPolicyCovered(std::vector<std::wstring> const &)
0x1800d5094  mov     rcx, [rsp+350h+var_318]
0x1800d5099  mov     [rcx+110h], al
0x1800d509f  mov     rcx, [rsp+350h+var_318]
0x1800d50a4  mov     rax, [rcx+120h]
0x1800d50ab  sub     rax, [rcx+118h]
0x1800d50b2  sar     rax, 5
0x1800d50b6  imul    edx, eax, 64h ; 'd'
0x1800d50b9  mov     eax, 2AAAAAABh
  ... truncated ...
```
