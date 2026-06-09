# DeviceSettingsBackupRestoreHandler::OnBackup(_GUID const &,char const *,wil::cloud_store)

- ea: `0x1800fce10`
- end: `0x1800fd2b4`
- name: `?OnBackup@DeviceSettingsBackupRestoreHandler@@UEAAXAEBU_GUID@@PEBDVcloud_store@wil@@@Z`
- size: `1188`
- prototype: `void __high(const struct _GUID *, const char *, struct wil::cloud_store)`
- caller_count: `0`
- callee_count: `36`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800162a4`
- `0x18001649c`
- `0x180016cec`
- `0x18001ac54`
- `0x18001cf64`
- `0x18001cfa4`
- `0x18002236c`
- `0x1800225d4`
- `0x180027000`
- `0x180036a3c`
- `0x180036ddc`
- `0x18004623c`
- `0x18007ea5c`
- `0x1800920d8`
- `0x180096af4`
- `0x1800974b0`
- `0x180097550`
- `0x1800977e8`
- `0x1800fadd0`
- `0x1800faf20`
- `0x1800fafac`
- `0x1800fb14c`
- `0x1800fb1d4`
- `0x1800fb25c`
- `0x1800fbeac`
- `0x1800fbf74`
- `0x1800fc314`
- `0x1800fc9a8`
- `0x1800fcab0`
- `0x1800fcaf8`
- `0x1800fce10`
- `0x1800fd854`
- `0x1800fd90c`
- `0x1800fdd9c`
- `0x1800fe33c`
- `0x1800fe4cc`

## string_xrefs

- `0x1800fcf30`: `Schema Load Completed`
- `0x1800fcf58`: `Schema Load Completed`
- `0x1800fd235`: `Backup Completed`
- `0x1800fd19f`: `Schema save Completed`
- `0x1800fd1c0`: `Schema save Completed`
- `0x1800fd1f2`: `Device setting Backup Completed`
- `0x1800fd216`: `Device setting Backup Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall DeviceSettingsBackupRestoreHandler::OnBackup(__int64 a1, __int64 a2, __int64 a3, wil::cloud_store *a4)
{
  CloudRestoreLauncherTelemetry::DeviceSettingsActivity *v6; // rsi
  char IsEnabled; // al
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rcx
  _BYTE *v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  char v13; // dl
  int v14; // ecx
  __int64 v15; // rcx
  int DWORD; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rcx
  unsigned __int8 v21; // al
  unsigned int v22; // ebx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  int v28; // edx
  int v29; // ecx
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // [rsp+20h] [rbp-E0h]
  bool v33[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v34; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v35; // [rsp+40h] [rbp-C0h] BYREF
  char v36[16]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h]
  _BYTE v39[12]; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+74h] [rbp-8Ch]
  char v41; // [rsp+78h] [rbp-88h]
  __int64 v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h]
  _BYTE v44[12]; // [rsp+90h] [rbp-70h] BYREF
  int v45; // [rsp+9Ch] [rbp-64h]
  char v46; // [rsp+A0h] [rbp-60h]
  _BYTE **v47; // [rsp+A8h] [rbp-58h]
  _BYTE *v48; // [rsp+B0h] [rbp-50h]
  char v49; // [rsp+B8h] [rbp-48h]
  _BYTE v50[56]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v6 = (CloudRestoreLauncherTelemetry::DeviceSettingsActivity *)(a1 + 8);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl);
  v8 = L"Backup Started";
  if ( !IsEnabled )
    v8 = L"Device setting Backup Started";
  CloudRestoreLauncherTelemetry::DeviceSettingsActivity::StartActivity(v6, v8);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BRCLogImprovements>::GetImpl'::`2'::impl)
    && (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v9, BackupAssociatedDeviceSettingHandler, L"Device setting Backup Started");
  }
  *(_QWORD *)v36 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>>::start_and_watch_errors(
    v36,
    v50);
  wil::com_ptr_t<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>,wil::err_returncode_policy>(v36);
  v10 = (_BYTE *)v51;
  v34 = (_BYTE *)v51;
  if ( v51 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v51 + 280));
    v10 = v34;
  }
  tip2::details::shared_data<0,0,0>::begin_update(v10 + 8);
  v47 = &v34;
  v48 = v50;
  v49 = 1;
  wil::cloud_store::load<Windows::Data::DeviceSettings::DeviceSettingsData>(a4, &v42, 2);
  v34[272] = 1;
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    v12 = std::_String_val<std::_Simple_types<char>>::_Myptr(Windows::Data::DeviceSettings::DeviceSettingsData::Schema::metadata);
    McTemplateU0sxt_EventWriteTransfer(v14, (unsigned int)CloudDataLoaded, v12, v43, v13);
  }
  CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[22]>(
    v11,
    L"Schema Load Completed");
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BRCLogImprovements>::GetImpl'::`2'::impl)
    && (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    McTemplateU0zz_EventWriteTransfer(
      v15,
      BackupAssociatedDeviceSettingBondActivity,
      L"Backup",
      L"Schema Load Completed");
  }
  v37 = v42;
  v38 = v43;
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>(
    v39,
    v44);
  v39[8] = v44[8];
  v39[9] = v44[9];
  v40 = v45;
  v41 = v46;
  v35 = 0;
  DWORD = SHRegGetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows",
            L"LegacyDefaultPrinterMode",
            &v35);
  if ( DWORD < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\devicesettingsbackuprestorehandler.cpp",
      (const char *)(unsigned int)DWORD,
      v32);
  LODWORD(v37) = v35;
  v33[0] = v35 == 0;
  CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_SettingsData<unsigned short const (&)[27],bool>(
    retaddr,
    v33);
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    McTemplateU0zt_EventWriteTransfer(v17, BackupAssociatedDeviceSettingData, L"ManageDefaultPrinterToggle", v35 == 0);
  v34[274] = 1;
  v18 = winrt::get_activation_factory<winrt::Windows::Internal::Data::Activities::ActivityPrivacyManager,winrt::Windows::Internal::Data::Activities::IActivityPrivacyManagerStatics>(v36);
  v19 = a1 + 344;
  winrt::Windows::Foundation::IUnknown::operator=(v19, v18);
  _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v36);
  *(_QWORD *)v36 = 0;
  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(v19, v36) )
  {
    v34[275] = 1;
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 8) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        v20,
        AssociatedDeviceSettingHandlerWarning,
        L"Backup",
        L"Skiiping StoreMyActivityHistoryOnThisDeviceToggle Backup as m_activityPrivacyManager is not initialized");
    CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_Warning<unsigned short const (&)[7],unsigned short const (&)[104]>();
  }
  else
  {
    v21 = winrt::impl::consume_Windows_Internal_Data_Activities_IActivityPrivacyManagerStatics<winrt::Windows::Internal::Data::Activities::IActivityPrivacyManagerStatics>::ActivityHistoryCollectionAllowedByUser(v19);
    v22 = v21;
    BYTE4(v37) = v21 != 0;
    v33[0] = v21;
    CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_SettingsData<unsigned short const (&)[41],bool>(
      v23,
      v33);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zt_EventWriteTransfer(
        v24,
        BackupAssociatedDeviceSettingData,
        L"StoreMyActivityHistoryOnThisDeviceToggle",
        v22);
    v34[275] = 1;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[32],unsigned short const (&)[8]>();
  if ( (_DWORD)v42 == (_DWORD)v37 && BYTE4(v42) == BYTE4(v37) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BRCLogImprovements>::GetImpl'::`2'::impl)
      && (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v25, CloudDataSkipSave, L"Device Settings Backup");
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
      CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[21]>();
    wil::cloud_store::save<Windows::Data::DeviceSettings::DeviceSettingsData>(a4, v36, &v37);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      v27 = std::_String_val<std::_Simple_types<char>>::_Myptr(Windows::Data::DeviceSettings::DeviceSettingsData::Schema::metadata);
      McTemplateU0sxx_EventWriteTransfer(v29, v28, v27, v38, v36[0]);
    }
    CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[22]>(
      v26,
      L"Schema save Completed");
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BRCLogImprovements>::GetImpl'::`2'::impl)
      && (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      McTemplateU0zz_EventWriteTransfer(
        v30,
        BackupAssociatedDeviceSettingBondActivity,
        L"Backup",
        L"Schema save Completed");
    }
  }
  v34[273] = 1;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::DeviceSettingsActivity::Stop(v6, L"Device setting Backup Completed");
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BRCLogImprovements>::GetImpl'::`2'::impl)
    && (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v31, BackupAssociatedDeviceSettingHandler, L"Device setting Backup Completed");
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::DeviceSettingsActivity::Stop(v6, L"Backup Completed");
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(v39);
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(v44);
  tip2::test_data_control<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>>::close(&v34);
  tip2::details::shared_data<0,0,0>::complete_without_lock(v51 + 8);
  tip2::test_data_control<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>>(&v34);
  tip2::test_watcher<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>>::~test_watcher<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>>(v50);
  wil::cloud_store::~cloud_store(a4);
}

```

## disassembly

```asm
0x1800fce10  mov     [rsp-8+arg_18], r9
0x1800fce15  push    rbp
0x1800fce16  push    rbx
0x1800fce17  push    rsi
0x1800fce18  push    rdi
0x1800fce19  push    r12
0x1800fce1b  push    r13
0x1800fce1d  lea     rbp, [rsp-8]
0x1800fce22  sub     rsp, 108h
0x1800fce29  mov     rdi, r9
0x1800fce2c  mov     rbx, rcx
0x1800fce2f  lea     rsi, [rcx+8]
0x1800fce33  lea     r13, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800fce3a  mov     rcx, r13
0x1800fce3d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800fce42  lea     r12, aDeviceSettingB; "Device setting Backup Started"
0x1800fce49  lea     rdx, aBackupStarted; "Backup Started"
0x1800fce50  test    al, al
0x1800fce52  cmovz   rdx, r12; unsigned __int16 *
0x1800fce56  mov     rcx, rsi; this
0x1800fce59  call    ?StartActivity@DeviceSettingsActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::DeviceSettingsActivity::StartActivity(ushort const *)
0x1800fce5e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BRCLogImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BRCLogImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements> `wil::Feature<__WilFeatureTraits_Feature_BRCLogImprovements>::GetImpl(void)'::`2'::impl
0x1800fce65  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BRCLogImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(void)
0x1800fce6a  test    al, al
0x1800fce6c  jnz     short loc_1800FCE86
0x1800fce6e  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800fce75  jz      short loc_1800FCE86
0x1800fce77  mov     r8, r12
0x1800fce7a  lea     rdx, BackupAssociatedDeviceSettingHandler
0x1800fce81  call    McTemplateU0z_EventWriteTransfer
0x1800fce86  mov     qword ptr [rsp+130h+var_E8], 0
0x1800fce8f  lea     rdx, [rbp+30h+var_70]
0x1800fce93  lea     rcx, [rsp+130h+var_E8]
0x1800fce98  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_DeviceSettingsBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_DeviceSettingsBackupTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>>::start_and_watch_errors(void)
0x1800fce9d  lea     rcx, [rsp+130h+var_E8]
0x1800fcea2  call    ??1?$com_ptr_t@V?$merged_data@U_tip_DeviceSettingsBackupTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>,wil::err_returncode_policy>(void)
0x1800fcea7  nop
0x1800fcea8  mov     rcx, [rbp+30h+var_38]
0x1800fceac  mov     [rsp+130h+var_F8], rcx
0x1800fceb1  test    rcx, rcx
0x1800fceb4  jz      short loc_1800FCEC2
0x1800fceb6  lock inc dword ptr [rcx+118h]
0x1800fcebd  mov     rcx, [rsp+130h+var_F8]
0x1800fcec2  add     rcx, 8
0x1800fcec6  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800fcecb  nop
0x1800fcecc  lea     rax, [rsp+130h+var_F8]
0x1800fced1  mov     [rbp+30h+var_88], rax
0x1800fced5  lea     rax, [rbp+30h+var_70]
0x1800fced9  mov     [rbp+30h+var_80], rax
0x1800fcedd  mov     [rbp+30h+var_78], 1
0x1800fcee1  mov     r8d, 2
0x1800fcee7  lea     rdx, [rbp+30h+var_B0]
0x1800fceeb  mov     rcx, rdi
0x1800fceee  call    ??$load@UDeviceSettingsData@DeviceSettings@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UDeviceSettingsData@DeviceSettings@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::DeviceSettings::DeviceSettingsData>(wil::cloud_store_load_options,char const *)
0x1800fcef3  nop
0x1800fcef4  mov     rax, [rsp+130h+var_F8]
0x1800fcef9  mov     byte ptr [rax+110h], 1
0x1800fcf00  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800fcf07  jz      short loc_1800FCF30
0x1800fcf09  movzx   edx, [rbp+30h+var_98]
0x1800fcf0d  lea     rcx, ?metadata@Schema@DeviceSettingsData@DeviceSettings@Data@Windows@@2UMetadata@bond@@B; bond::Metadata const Windows::Data::DeviceSettings::DeviceSettingsData::Schema::metadata
0x1800fcf14  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800fcf19  mov     r8, rax
0x1800fcf1c  mov     [rsp+130h+var_110], edx; int
0x1800fcf20  mov     r9, [rbp+30h+var_A8]
0x1800fcf24  lea     rdx, CloudDataLoaded
0x1800fcf2b  call    McTemplateU0sxt_EventWriteTransfer
0x1800fcf30  lea     rdx, aSchemaLoadComp_0; "Schema Load Completed"
0x1800fcf37  call    ??$DeviceSettings_BondSchemaActivity@AEAY06$$CBGAEAY0BG@$$CBG@DeviceSettingsActivity@CloudRestoreLauncherTelemetry@@SAXAEAY06$$CBGAEAY0BG@$$CBG@Z; CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_BondSchemaActivity<ushort const (&)[7],ushort const (&)[22]>(ushort const (&)[7],ushort const (&)[22])
0x1800fcf3c  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BRCLogImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BRCLogImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements> `wil::Feature<__WilFeatureTraits_Feature_BRCLogImprovements>::GetImpl(void)'::`2'::impl
0x1800fcf43  mov     rcx, r12
0x1800fcf46  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BRCLogImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(void)
0x1800fcf4b  test    al, al
0x1800fcf4d  jnz     short loc_1800FCF72
0x1800fcf4f  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800fcf56  jz      short loc_1800FCF72
0x1800fcf58  lea     r9, aSchemaLoadComp_0; "Schema Load Completed"
0x1800fcf5f  lea     r8, aBackup; "Backup"
0x1800fcf66  lea     rdx, BackupAssociatedDeviceSettingBondActivity
0x1800fcf6d  call    McTemplateU0zz_EventWriteTransfer
0x1800fcf72  mov     rax, [rbp+30h+var_B0]
0x1800fcf76  mov     [rsp+130h+var_D8], rax
0x1800fcf7b  mov     rax, [rbp+30h+var_A8]
0x1800fcf7f  mov     [rsp+130h+var_D0], rax
0x1800fcf84  lea     rdx, [rbp+30h+var_A0]
0x1800fcf88  lea     rcx, [rsp+130h+var_C8]
0x1800fcf8d  call    ??0?$com_ptr_t@UICloudStore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy>(wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStore,wil::err_exception_policy> const &)
0x1800fcf92  mov     al, [rbp+30h+var_98]
0x1800fcf95  mov     [rsp+130h+var_C0], al
0x1800fcf99  mov     al, [rbp+30h+var_97]
0x1800fcf9c  mov     [rsp+130h+var_BF], al
0x1800fcfa0  mov     eax, [rbp+30h+var_94]
0x1800fcfa3  mov     [rsp+130h+var_BC], eax
0x1800fcfa7  mov     al, [rbp+30h+var_90]
0x1800fcfaa  mov     [rsp+130h+var_B8], al
0x1800fcfae  mov     [rsp+130h+var_F0], 0
0x1800fcfb6  lea     r9, [rsp+130h+var_F0]; unsigned int *
0x1800fcfbb  lea     r8, aLegacydefaultp; "LegacyDefaultPrinterMode"
0x1800fcfc2  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800fcfc9  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800fcfd0  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800fcfd5  mov     rcx, [rbp+38h]; this
0x1800fcfd9  test    eax, eax
0x1800fcfdb  js      loc_1800FD29F
0x1800fcfe1  mov     eax, [rsp+130h+var_F0]
0x1800fcfe5  mov     dword ptr [rsp+130h+var_D8], eax
0x1800fcfe9  test    eax, eax
0x1800fcfeb  setz    [rsp+130h+var_100]
0x1800fcff0  lea     rdx, [rsp+130h+var_100]
0x1800fcff5  call    ??$DeviceSettings_SettingsData@AEAY0BL@$$CBG_N@DeviceSettingsActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BL@$$CBG$$QEA_N@Z; CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_SettingsData<ushort const (&)[27],bool>(ushort const (&)[27],bool &&)
0x1800fcffa  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800fd001  jz      short loc_1800FD022
0x1800fd003  xor     r9d, r9d
0x1800fd006  cmp     [rsp+130h+var_F0], r9d
0x1800fd00b  setz    r9b
0x1800fd00f  lea     r8, aManagedefaultp; "ManageDefaultPrinterToggle"
0x1800fd016  lea     rdx, BackupAssociatedDeviceSettingData
0x1800fd01d  call    McTemplateU0zt_EventWriteTransfer
0x1800fd022  mov     rax, [rsp+130h+var_F8]
0x1800fd027  mov     byte ptr [rax+112h], 1
0x1800fd02e  lea     rcx, [rsp+130h+var_E8]
0x1800fd033  call    ??$get_activation_factory@UActivityPrivacyManager@Activities@Data@Internal@Windows@winrt@@UIActivityPrivacyManagerStatics@23456@@winrt@@YA?A_PXZ
0x1800fd038  add     rbx, 158h
0x1800fd03f  mov     rdx, rax
0x1800fd042  mov     rcx, rbx
0x1800fd045  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800fd04a  lea     rcx, [rsp+130h+var_E8]; this
0x1800fd04f  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800fd054  mov     qword ptr [rsp+130h+var_E8], 0
0x1800fd05d  lea     rdx, [rsp+130h+var_E8]
0x1800fd062  mov     rcx, rbx
0x1800fd065  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800fd06a  test    al, al
0x1800fd06c  jnz     short loc_1800FD0BB
0x1800fd06e  mov     rcx, rbx
0x1800fd071  call    ?ActivityHistoryCollectionAllowedByUser@?$consume_Windows_Internal_Data_Activities_IActivityPrivacyManagerStatics@UIActivityPrivacyManagerStatics@Activities@Data@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Data_Activities_IActivityPrivacyManagerStatics<winrt::Windows::Internal::Data::Activities::IActivityPrivacyManagerStatics>::ActivityHistoryCollectionAllowedByUser(void)
0x1800fd076  movzx   ebx, al
0x1800fd079  test    al, al
0x1800fd07b  setnz   byte ptr [rsp+130h+var_D8+4]
0x1800fd080  mov     [rsp+130h+var_100], bl
0x1800fd084  lea     rdx, [rsp+130h+var_100]
0x1800fd089  call    ??$DeviceSettings_SettingsData@AEAY0CJ@$$CBG_N@DeviceSettingsActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0CJ@$$CBG$$QEA_N@Z; CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_SettingsData<ushort const (&)[41],bool>(ushort const (&)[41],bool &&)
0x1800fd08e  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800fd095  jz      short loc_1800FD0AD
0x1800fd097  mov     r9d, ebx
0x1800fd09a  lea     r8, aStoremyactivit; "StoreMyActivityHistoryOnThisDeviceToggl"...
0x1800fd0a1  lea     rdx, BackupAssociatedDeviceSettingData
0x1800fd0a8  call    McTemplateU0zt_EventWriteTransfer
0x1800fd0ad  mov     rax, [rsp+130h+var_F8]
0x1800fd0b2  mov     byte ptr [rax+113h], 1
0x1800fd0b9  jmp     short loc_1800FD0EF
0x1800fd0bb  mov     rax, [rsp+130h+var_F8]
0x1800fd0c0  mov     byte ptr [rax+113h], 1
0x1800fd0c7  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 8
0x1800fd0ce  jz      short loc_1800FD0EA
0x1800fd0d0  lea     r9, aSkiipingStorem; "Skiiping StoreMyActivityHistoryOnThisDe"...
0x1800fd0d7  lea     r8, aBackup; "Backup"
0x1800fd0de  lea     rdx, AssociatedDeviceSettingHandlerWarning
0x1800fd0e5  call    McTemplateU0zz_EventWriteTransfer
0x1800fd0ea  call    ??$DeviceSettings_Warning@AEAY06$$CBGAEAY0GI@$$CBG@DeviceSettingsActivity@CloudRestoreLauncherTelemetry@@SAXAEAY06$$CBGAEAY0GI@$$CBG@Z; CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_Warning<ushort const (&)[7],ushort const (&)[104]>(ushort const (&)[7],ushort const (&)[104])
0x1800fd0ef  mov     rcx, r13
0x1800fd0f2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800fd0f7  test    al, al
0x1800fd0f9  jz      short loc_1800FD100
0x1800fd0fb  call    ??$DeviceSettings_ApiActivity@AEAY0L@$$CBGAEAY0CA@$$CBGAEAY07$$CBG@DeviceSettingsActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0CA@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_ApiActivity<ushort const (&)[11],ushort const (&)[32],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[32],ushort const (&)[8])
0x1800fd100  mov     rax, [rbp+30h+var_B0]
0x1800fd104  cmp     eax, dword ptr [rsp+130h+var_D8]
0x1800fd108  jnz     short loc_1800FD150
0x1800fd10a  mov     rcx, [rsp+130h+var_D8]
0x1800fd10f  shr     rcx, 20h
0x1800fd113  shr     rax, 20h
0x1800fd117  cmp     al, cl
0x1800fd119  jnz     short loc_1800FD150
0x1800fd11b  mov     rcx, r12
0x1800fd11e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BRCLogImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(void)
0x1800fd123  test    al, al
0x1800fd125  jz      loc_1800FD1DA
0x1800fd12b  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800fd132  jz      loc_1800FD1DA
0x1800fd138  lea     r8, aDeviceSettings; "Device Settings Backup"
0x1800fd13f  lea     rdx, CloudDataSkipSave
0x1800fd146  call    McTemplateU0z_EventWriteTransfer
0x1800fd14b  jmp     loc_1800FD1DA
0x1800fd150  mov     rcx, r13
0x1800fd153  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800fd158  test    al, al
0x1800fd15a  jz      short loc_1800FD161
0x1800fd15c  call    ??$DeviceSettings_BondSchemaActivity@AEAY06$$CBGAEAY0BF@$$CBG@DeviceSettingsActivity@CloudRestoreLauncherTelemetry@@SAXAEAY06$$CBGAEAY0BF@$$CBG@Z; CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_BondSchemaActivity<ushort const (&)[7],ushort const (&)[21]>(ushort const (&)[7],ushort const (&)[21])
0x1800fd161  lea     r8, [rsp+130h+var_D8]
0x1800fd166  lea     rdx, [rsp+130h+var_E8]
0x1800fd16b  mov     rcx, rdi
0x1800fd16e  call    ??$save@UDeviceSettingsData@DeviceSettings@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UDeviceSettingsData@DeviceSettings@Data@Windows@@@1@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::DeviceSettings::DeviceSettingsData>(wil::cloud_store_data<Windows::Data::DeviceSettings::DeviceSettingsData> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x1800fd173  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800fd17a  jz      short loc_1800FD19F
0x1800fd17c  lea     rcx, ?metadata@Schema@DeviceSettingsData@DeviceSettings@Data@Windows@@2UMetadata@bond@@B; bond::Metadata const Windows::Data::DeviceSettings::DeviceSettingsData::Schema::metadata
0x1800fd183  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800fd188  mov     r8, rax
0x1800fd18b  mov     rax, qword ptr [rsp+130h+var_E8]
0x1800fd190  mov     qword ptr [rsp+130h+var_110], rax
0x1800fd195  mov     r9, [rsp+130h+var_D0]
0x1800fd19a  call    McTemplateU0sxx_EventWriteTransfer
0x1800fd19f  lea     rdx, aSchemaSaveComp_1; "Schema save Completed"
0x1800fd1a6  call    ??$DeviceSettings_BondSchemaActivity@AEAY06$$CBGAEAY0BG@$$CBG@DeviceSettingsActivity@CloudRestoreLauncherTelemetry@@SAXAEAY06$$CBGAEAY0BG@$$CBG@Z; CloudRestoreLauncherTelemetry::DeviceSettingsActivity::DeviceSettings_BondSchemaActivity<ushort const (&)[7],ushort const (&)[22]>(ushort const (&)[7],ushort const (&)[22])
0x1800fd1ab  mov     rcx, r12
0x1800fd1ae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BRCLogImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(void)
0x1800fd1b3  test    al, al
0x1800fd1b5  jnz     short loc_1800FD1DA
0x1800fd1b7  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800fd1be  jz      short loc_1800FD1DA
0x1800fd1c0  lea     r9, aSchemaSaveComp_1; "Schema save Completed"
0x1800fd1c7  lea     r8, aBackup; "Backup"
0x1800fd1ce  lea     rdx, BackupAssociatedDeviceSettingBondActivity
0x1800fd1d5  call    McTemplateU0zz_EventWriteTransfer
0x1800fd1da  mov     rax, [rsp+130h+var_F8]
0x1800fd1df  mov     byte ptr [rax+111h], 1
0x1800fd1e6  mov     rcx, r13
0x1800fd1e9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800fd1ee  test    al, al
0x1800fd1f0  jnz     short loc_1800FD201
0x1800fd1f2  lea     rdx, aDeviceSettingB_0; "Device setting Backup Completed"
0x1800fd1f9  mov     rcx, rsi; this
0x1800fd1fc  call    ?Stop@DeviceSettingsActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::DeviceSettingsActivity::Stop(ushort const *)
0x1800fd201  mov     rcx, r12
0x1800fd204  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BRCLogImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(void)
0x1800fd209  test    al, al
0x1800fd20b  jnz     short loc_1800FD229
0x1800fd20d  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800fd214  jz      short loc_1800FD229
0x1800fd216  lea     r8, aDeviceSettingB_0; "Device setting Backup Completed"
0x1800fd21d  lea     rdx, BackupAssociatedDeviceSettingHandler
0x1800fd224  call    McTemplateU0z_EventWriteTransfer
0x1800fd229  mov     rcx, r13
0x1800fd22c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800fd231  test    al, al
0x1800fd233  jz      short loc_1800FD245
0x1800fd235  lea     rdx, aBackupComplete; "Backup Completed"
0x1800fd23c  mov     rcx, rsi; this
0x1800fd23f  call    ?Stop@DeviceSettingsActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::DeviceSettingsActivity::Stop(ushort const *)
0x1800fd244  nop
0x1800fd245  lea     rcx, [rsp+130h+var_C8]
0x1800fd24a  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800fd24f  nop
0x1800fd250  lea     rcx, [rbp+30h+var_A0]
0x1800fd254  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800fd259  nop
0x1800fd25a  lea     rcx, [rsp+130h+var_F8]
0x1800fd25f  call    ?close@?$test_data_control@V?$merged_data@U_tip_DeviceSettingsBackupTipTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>>::close(void)
0x1800fd264  mov     rcx, [rbp+30h+var_38]
0x1800fd268  add     rcx, 8
0x1800fd26c  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x1800fd271  nop
0x1800fd272  lea     rcx, [rsp+130h+var_F8]
0x1800fd277  call    ??1?$test_data_control@V?$merged_data@U_tip_DeviceSettingsBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>>(void)
0x1800fd27c  nop
0x1800fd27d  lea     rcx, [rbp+30h+var_70]
0x1800fd281  call    ??1?$test_watcher@V?$merged_data@U_tip_DeviceSettingsBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>>::~test_watcher<tip2::details::merged_data<_tip_DeviceSettingsBackupTipTest,_tip_DeviceSettingsBackupTipTest>>(void)
0x1800fd286  nop
0x1800fd287  mov     rcx, rdi; this
0x1800fd28a  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x1800fd28f  add     rsp, 108h
0x1800fd296  pop     r13
0x1800fd298  pop     r12
0x1800fd29a  pop     rdi
0x1800fd29b  pop     rsi
0x1800fd29c  pop     rbx
0x1800fd29d  pop     rbp
0x1800fd29e  retn
0x1800fd29f  mov     r9d, eax; char *
0x1800fd2a2  lea     r8, aPcshellShellCl_1; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800fd2a9  mov     edx, 52h ; 'R'; void *
0x1800fd2ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
