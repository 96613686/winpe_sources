# InkPenBackupRestoreHandler::OnBackup(_GUID const &,char const *,wil::cloud_store)

- ea: `0x1800ec1e0`
- end: `0x1800ec87b`
- name: `?OnBackup@InkPenBackupRestoreHandler@@UEAAXAEBU_GUID@@PEBDVcloud_store@wil@@@Z`
- size: `1691`
- prototype: `void __high(const struct _GUID *, const char *, struct wil::cloud_store)`
- caller_count: `0`
- callee_count: `43`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000c6e0`
- `0x18001ac54`
- `0x18001cf64`
- `0x18001cf84`
- `0x18001d0a8`
- `0x18001faa8`
- `0x18002236c`
- `0x180027000`
- `0x1800284d0`
- `0x180036a3c`
- `0x18004623c`
- `0x180096af4`
- `0x1800974b0`
- `0x180097550`
- `0x1800977e8`
- `0x1800e86f0`
- `0x1800e8798`
- `0x1800e8840`
- `0x1800e88e0`
- `0x1800e8988`
- `0x1800e8a30`
- `0x1800e8ad8`
- `0x1800e9010`
- `0x1800e909c`
- `0x1800e9124`
- `0x1800eab40`
- `0x1800ead9c`
- `0x1800eb4b8`
- `0x1800eb6c8`
- `0x1800eb794`
- `0x1800eb7bc`
- `0x1800eb894`
- `0x1800eb8dc`
- `0x1800eb9a8`
- `0x1800ebabc`
- `0x1800ebe48`
- `0x1800ebeec`
- `0x1800ec1e0`
- `0x1800ed1d0`
- `0x1800ed288`
- `0x1800edcdc`
- `0x1800ede6c`
- `0x1800edffc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800ec5ad`
- `KERNEL32!GetLastError` at `0x1800ec5ad`
- `USER32!SystemParametersInfoW` at `0x1800ec548`
- `USER32!SystemParametersInfoW` at `0x1800ec548`

## string_xrefs

- `0x1800ec279`: `Schema Load Completed`
- `0x1800ec7df`: `Backup Completed`
- `0x1800ec79e`: `Schema save Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall InkPenBackupRestoreHandler::OnBackup(__int64 a1, __int64 a2, __int64 a3, wil::cloud_store *a4)
{
  __int64 v6; // rcx
  int v7; // eax
  char v8; // dl
  int v9; // ecx
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rbx
  signed int DWORD; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rbx
  signed int LastError; // eax
  wil::details::in1diag3 *v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // r10
  __int64 v31; // r11
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rdx
  int v35; // eax
  int v36; // edx
  int v37; // ecx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rbx
  int v41; // [rsp+20h] [rbp-E0h]
  unsigned int v42; // [rsp+80h] [rbp-80h] BYREF
  int pvParam; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE *v44; // [rsp+88h] [rbp-78h] BYREF
  char v45; // [rsp+90h] [rbp-70h]
  wil::cloud_store *v46; // [rsp+98h] [rbp-68h]
  _BYTE v47[56]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-28h]
  char v49[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v50; // [rsp+100h] [rbp+0h] BYREF
  __int64 v51; // [rsp+108h] [rbp+8h] BYREF
  __int64 v52; // [rsp+110h] [rbp+10h] BYREF
  __int64 v53; // [rsp+118h] [rbp+18h] BYREF
  __int64 v54; // [rsp+120h] [rbp+20h] BYREF
  __int64 v55; // [rsp+128h] [rbp+28h] BYREF
  char v56; // [rsp+130h] [rbp+30h]
  unsigned __int8 v57; // [rsp+131h] [rbp+31h]
  _BYTE v58[32]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v59[32]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v60[32]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v61[32]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v62[32]; // [rsp+1B8h] [rbp+B8h] BYREF
  int v63[18]; // [rsp+1D8h] [rbp+D8h] BYREF
  _BYTE v64[248]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v65; // [rsp+318h] [rbp+218h]
  unsigned __int8 v66; // [rsp+328h] [rbp+228h]
  _BYTE v67[256]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v68[256]; // [rsp+440h] [rbp+340h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+568h] [rbp+468h]

  v46 = a4;
  *(_QWORD *)v49 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>::start_and_watch_errors(
    v49,
    v47);
  wil::com_ptr_t<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>,wil::err_returncode_policy>(v49);
  v44 = v47;
  v45 = 1;
  CloudRestoreLauncherTelemetry::InkPenActivity::StartActivity(
    (CloudRestoreLauncherTelemetry::InkPenActivity *)(a1 + 8),
    L"Backup Started");
  wil::cloud_store::load<Windows::Data::Input::Devices::PenPerDevice>(a4, v64, 2);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[22]>(
      v6,
      L"Schema Load Completed");
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    v7 = std::_String_val<std::_Simple_types<char>>::_Myptr(
           &Windows::Data::Input::Devices::PenPerDevice::Schema::metadata,
           v66);
    McTemplateU0sxt_EventWriteTransfer(v9, (unsigned int)&CloudDataLoaded, v7, v65, v8);
  }
  v10 = v48;
  *(_QWORD *)v49 = v48;
  if ( v48 )
    _InterlockedIncrement((volatile signed __int32 *)(v48 + 280));
  tip2::details::shared_data<0,0,0>::begin_update(v10 + 8);
  *(_BYTE *)(v10 + 272) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>(v49);
  wil::cloud_store_data<Windows::Data::Input::Devices::PenPerDevice>::cloud_store_data<Windows::Data::Input::Devices::PenPerDevice>(&v50);
  std::wstring::wstring(
    v49,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\ClickNote\\UserCustomization\\SingleClickBelowLock");
  InkPenBackupRestoreHandler::GetClickActions(v11, &v50, &v51, (__int64)v58, (__int64)v61, (__int64)v49);
  std::wstring::_Tidy_deallocate(v49);
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    McTemplateU0zz_EventWriteTransfer(v12, &InkPenSettingStatus, L"Single-Click", L"Done");
  CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[33],unsigned short const (&)[8]>(
    v12,
    L"GetClickActions for single-click");
  std::wstring::wstring(
    v49,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\ClickNote\\UserCustomization\\DoubleClickBelowLock");
  InkPenBackupRestoreHandler::GetClickActions(v13, &v52, &v53, (__int64)v59, (__int64)v62, (__int64)v49);
  std::wstring::_Tidy_deallocate(v49);
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    McTemplateU0zz_EventWriteTransfer(v14, &InkPenSettingStatus, L"Double-Click", L"Done");
  CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[33],unsigned short const (&)[8]>(
    v14,
    L"GetClickActions for double-click");
  std::wstring::wstring(
    v49,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\ClickNote\\UserCustomization\\LongPressBelowLock");
  InkPenBackupRestoreHandler::GetClickActions(v15, &v54, &v55, (__int64)v60, (__int64)v63, (__int64)v49);
  std::wstring::_Tidy_deallocate(v49);
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    McTemplateU0zz_EventWriteTransfer(v16, &InkPenSettingStatus, L"Long-Press", L"Done");
  CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[31],unsigned short const (&)[8]>();
  v17 = v48;
  *(_QWORD *)v49 = v48;
  if ( v48 )
    _InterlockedIncrement((volatile signed __int32 *)(v48 + 280));
  tip2::details::shared_data<0,0,0>::begin_update(v17 + 8);
  *(_BYTE *)(v17 + 274) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>(v49);
  v42 = 1;
  DWORD = SHRegGetDWORD(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\PenWorkspace",
            L"PenWorkspaceAppLaunchOnPenDetachEnabled",
            &v42);
  if ( !DWORD || DWORD == -2147024894 )
  {
    v56 = v42 != 0;
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(v19, &InkPenSettingStatus, L"PenWorkspaceAppLaunchOnPenDetachEnabled", L"Done");
    CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[58],unsigned short const (&)[8]>();
    v21 = v48;
    *(_QWORD *)v49 = v48;
    if ( v48 )
      _InterlockedIncrement((volatile signed __int32 *)(v48 + 280));
    tip2::details::shared_data<0,0,0>::begin_update(v21 + 8);
    *(_BYTE *)(v21 + 275) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>(v49);
  }
  else
  {
    if ( DWORD > 0 )
      DWORD = (unsigned __int16)DWORD | 0x80070000;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\inkpenbackuprestorehandler.cpp",
      (const char *)(unsigned int)DWORD,
      v41);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        v20,
        &InkPenSettingStatus,
        L"PenWorkspaceAppLaunchOnPenDetachEnabled",
        L"Failed");
    CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[58],unsigned short const (&)[7]>(v20);
  }
  pvParam = 0;
  if ( SystemParametersInfoW(0x1052u, 0, &pvParam, 0) )
  {
    v57 = pvParam == 0;
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(v22, &InkPenSettingStatus, L"PenEnablePenButtonOverride", L"Done");
    CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[52],unsigned short const (&)[8]>();
    v23 = v48;
    *(_QWORD *)v49 = v48;
    if ( v48 )
      _InterlockedIncrement((volatile signed __int32 *)(v48 + 280));
    tip2::details::shared_data<0,0,0>::begin_update(v23 + 8);
    *(_BYTE *)(v23 + 276) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>(v49);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v25 = retaddr;
    if ( LastError < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\inkpenbackuprestorehandler.cpp",
        (const char *)(unsigned int)LastError,
        v41);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(v25, &InkPenSettingStatus, L"PenEnablePenButtonOverride", L"Failed");
    CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[52],unsigned short const (&)[7]>(v25);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
    CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[32],unsigned short const (&)[8]>();
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v63);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v62);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v60);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v59);
    v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
    McTemplateU0xxxxxxxxzzzzzz_EventWriteTransfer(
      v57,
      (unsigned int)&BackupAssociatedInkPenSettingCloudFile,
      v50,
      v51,
      v52,
      v53,
      v54,
      v55,
      v56,
      v57,
      v27,
      v28,
      v29,
      v30,
      v31,
      v26);
  }
  v32 = Windows::Data::Input::Devices::PenPerDevice::PenPerDevice(
          (Windows::Data::Input::Devices::PenPerDevice *)v68,
          (const struct Windows::Data::Input::Devices::PenPerDevice *)v64);
  v33 = Windows::Data::Input::Devices::PenPerDevice::PenPerDevice(
          (Windows::Data::Input::Devices::PenPerDevice *)v67,
          (const struct Windows::Data::Input::Devices::PenPerDevice *)&v50);
  LOBYTE(v32) = Windows::Data::Input::Devices::PenPerDevice::operator==(v32, v33);
  Windows::Data::Input::Devices::PenPerDevice::~PenPerDevice((Windows::Data::Input::Devices::PenPerDevice *)v67);
  Windows::Data::Input::Devices::PenPerDevice::~PenPerDevice((Windows::Data::Input::Devices::PenPerDevice *)v68);
  if ( (_BYTE)v32 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BRCLogImprovements>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_BRCLogImprovements>::GetImpl'::`2'::impl)
      && (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v39, &CloudDataSkipSave, L"InkPen Backup");
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
      CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[21]>();
    Windows::Data::Input::Devices::PenPerDevice::swap(
      (Windows::Data::Input::Devices::PenPerDevice *)v64,
      (struct Windows::Data::Input::Devices::PenPerDevice *)&v50);
    wil::cloud_store::save<Windows::Data::Input::Devices::PenPerDevice>(a4, v49, v64);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      v35 = std::_String_val<std::_Simple_types<char>>::_Myptr(
              &Windows::Data::Input::Devices::PenPerDevice::Schema::metadata,
              v34);
      McTemplateU0sxx_EventWriteTransfer(v37, v36, v35, v65, v49[0]);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl'::`2'::impl) )
      CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[22]>(
        v38,
        L"Schema save Completed");
    else
      CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_BondSchemaActivity<unsigned short const (&)[7],unsigned short const (&)[36]>();
  }
  CloudRestoreLauncherTelemetry::InkPenActivity::Stop(
    (CloudRestoreLauncherTelemetry::InkPenActivity *)(a1 + 8),
    L"Backup Completed");
  v40 = v48;
  *(_QWORD *)v49 = v48;
  if ( v48 )
    _InterlockedIncrement((volatile signed __int32 *)(v48 + 280));
  tip2::details::shared_data<0,0,0>::begin_update(v40 + 8);
  *(_BYTE *)(v40 + 273) = 1;
  tip2::test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>(v49);
  wil::cloud_store_data<Windows::Data::Input::Devices::PenPerDevice>::~cloud_store_data<Windows::Data::Input::Devices::PenPerDevice>((Windows::Data::Input::Devices::PenPerDevice *)&v50);
  wil::cloud_store_data<Windows::Data::Input::Devices::PenPerDevice>::~cloud_store_data<Windows::Data::Input::Devices::PenPerDevice>((Windows::Data::Input::Devices::PenPerDevice *)v64);
  v45 = 0;
  lambda_afec3c304865bd792bb2f46aa354f58f_::operator()(&v44);
  tip2::test_watcher<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>::~test_watcher<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>(v47);
  wil::cloud_store::~cloud_store(a4);
}

```

## disassembly

```asm
0x1800ec1e0  mov     [rsp-8+arg_8], rbx
0x1800ec1e5  mov     [rsp-8+arg_10], rsi
0x1800ec1ea  push    rbp
0x1800ec1eb  push    rdi
0x1800ec1ec  push    r13
0x1800ec1ee  lea     rbp, [rsp-450h]
0x1800ec1f6  sub     rsp, 550h
0x1800ec1fd  mov     rax, cs:__security_cookie
0x1800ec204  xor     rax, rsp
0x1800ec207  mov     [rbp+460h+var_20], rax
0x1800ec20e  mov     rdi, r9
0x1800ec211  mov     rsi, rcx
0x1800ec214  mov     [rbp+460h+var_4C8], r9
0x1800ec218  mov     qword ptr [rbp+460h+var_480], 0
0x1800ec220  lea     rdx, [rbp+460h+var_4C0]
0x1800ec224  lea     rcx, [rbp+460h+var_480]
0x1800ec228  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_InkPenBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_InkPenBackupTipTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>::start_and_watch_errors(void)
0x1800ec22d  lea     rcx, [rbp+460h+var_480]
0x1800ec231  call    ??1?$com_ptr_t@V?$merged_data@U_tip_InkPenBackupTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>,wil::err_returncode_policy>(void)
0x1800ec236  nop
0x1800ec237  lea     rax, [rbp+460h+var_4C0]
0x1800ec23b  mov     [rbp+460h+var_4D8], rax
0x1800ec23f  mov     [rbp+460h+var_4D0], 1
0x1800ec243  lea     rdx, aBackupStarted; "Backup Started"
0x1800ec24a  lea     rcx, [rsi+8]; this
0x1800ec24e  call    ?StartActivity@InkPenActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::StartActivity(ushort const *)
0x1800ec253  mov     r8d, 2
0x1800ec259  lea     rdx, [rbp+460h+var_340]
0x1800ec260  mov     rcx, rdi
0x1800ec263  call    ??$load@UPenPerDevice@Devices@Input@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UPenPerDevice@Devices@Input@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Input::Devices::PenPerDevice>(wil::cloud_store_load_options,char const *)
0x1800ec268  nop
0x1800ec269  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800ec270  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800ec275  test    al, al
0x1800ec277  jz      short loc_1800EC285
0x1800ec279  lea     rdx, aSchemaLoadComp_0; "Schema Load Completed"
0x1800ec280  call    ??$InkPen_BondSchemaActivity@AEAY06$$CBGAEAY0BG@$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY06$$CBGAEAY0BG@$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_BondSchemaActivity<ushort const (&)[7],ushort const (&)[22]>(ushort const (&)[7],ushort const (&)[22])
0x1800ec285  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ec28c  jz      short loc_1800EC2BB
0x1800ec28e  movzx   edx, [rbp+460h+var_238]
0x1800ec295  lea     rcx, ?metadata@Schema@PenPerDevice@Devices@Input@Data@Windows@@2UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::PenPerDevice::Schema::metadata
0x1800ec29c  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800ec2a1  mov     r8, rax
0x1800ec2a4  mov     [rsp+560h+var_540], edx
0x1800ec2a8  mov     r9, [rbp+460h+var_248]
0x1800ec2af  lea     rdx, CloudDataLoaded
0x1800ec2b6  call    McTemplateU0sxt_EventWriteTransfer
0x1800ec2bb  mov     rbx, [rbp+460h+var_488]
0x1800ec2bf  mov     qword ptr [rbp+460h+var_480], rbx
0x1800ec2c3  test    rbx, rbx
0x1800ec2c6  jz      short loc_1800EC2CF
0x1800ec2c8  lock inc dword ptr [rbx+118h]
0x1800ec2cf  lea     rcx, [rbx+8]
0x1800ec2d3  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800ec2d8  mov     byte ptr [rbx+110h], 1
0x1800ec2df  lea     rcx, [rbp+460h+var_480]
0x1800ec2e3  call    ??1?$test_data_control@V?$merged_data@U_tip_InkPenBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>(void)
0x1800ec2e8  lea     rcx, [rbp+460h+var_460]
0x1800ec2ec  call    ??0?$cloud_store_data@UPenPerDevice@Devices@Input@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::Input::Devices::PenPerDevice>::cloud_store_data<Windows::Data::Input::Devices::PenPerDevice>(void)
0x1800ec2f1  nop
0x1800ec2f2  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ec2f9  lea     rcx, [rbp+460h+var_480]
0x1800ec2fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ec302  nop
0x1800ec303  lea     rax, [rbp+460h+var_480]
0x1800ec307  mov     [rsp+560h+var_538], rax
0x1800ec30c  lea     rax, [rbp+460h+var_3C8]
0x1800ec313  mov     qword ptr [rsp+560h+var_540], rax
0x1800ec318  lea     r9, [rbp+460h+var_428]
0x1800ec31c  lea     r8, [rbp+460h+var_458]
0x1800ec320  lea     rdx, [rbp+460h+var_460]
0x1800ec324  call    ?GetClickActions@InkPenBackupRestoreHandler@@AEAAXAEA_K0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEBV23@@Z; InkPenBackupRestoreHandler::GetClickActions(unsigned __int64 &,unsigned __int64 &,std::wstring &,std::wstring &,std::wstring const &)
0x1800ec329  nop
0x1800ec32a  lea     rcx, [rbp+460h+var_480]
0x1800ec32e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ec333  lea     rbx, aDone; "Done"
0x1800ec33a  lea     r13, InkPenSettingStatus
0x1800ec341  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ec348  jz      short loc_1800EC35C
0x1800ec34a  mov     r9, rbx
0x1800ec34d  lea     r8, aSingleClick; "Single-Click"
0x1800ec354  mov     rdx, r13
0x1800ec357  call    McTemplateU0zz_EventWriteTransfer
0x1800ec35c  lea     rdx, aGetclickaction_0; "GetClickActions for single-click"
0x1800ec363  call    ??$InkPen_ApiActivity@AEAY0L@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[11],ushort const (&)[33],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[33],ushort const (&)[8])
0x1800ec368  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ec36f  lea     rcx, [rbp+460h+var_480]
0x1800ec373  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ec378  nop
0x1800ec379  lea     rax, [rbp+460h+var_480]
0x1800ec37d  mov     [rsp+560h+var_538], rax
0x1800ec382  lea     rax, [rbp+460h+var_3A8]
0x1800ec389  mov     qword ptr [rsp+560h+var_540], rax
0x1800ec38e  lea     r9, [rbp+460h+var_408]
0x1800ec392  lea     r8, [rbp+460h+var_448]
0x1800ec396  lea     rdx, [rbp+460h+var_450]
0x1800ec39a  call    ?GetClickActions@InkPenBackupRestoreHandler@@AEAAXAEA_K0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEBV23@@Z; InkPenBackupRestoreHandler::GetClickActions(unsigned __int64 &,unsigned __int64 &,std::wstring &,std::wstring &,std::wstring const &)
0x1800ec39f  nop
0x1800ec3a0  lea     rcx, [rbp+460h+var_480]
0x1800ec3a4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ec3a9  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ec3b0  jz      short loc_1800EC3C4
0x1800ec3b2  mov     r9, rbx
0x1800ec3b5  lea     r8, aDoubleClick; "Double-Click"
0x1800ec3bc  mov     rdx, r13
0x1800ec3bf  call    McTemplateU0zz_EventWriteTransfer
0x1800ec3c4  lea     rdx, aGetclickaction; "GetClickActions for double-click"
0x1800ec3cb  call    ??$InkPen_ApiActivity@AEAY0L@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0CB@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[11],ushort const (&)[33],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[33],ushort const (&)[8])
0x1800ec3d0  lea     rdx, aSoftwareMicros_23; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ec3d7  lea     rcx, [rbp+460h+var_480]
0x1800ec3db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ec3e0  nop
0x1800ec3e1  lea     rax, [rbp+460h+var_480]
0x1800ec3e5  mov     [rsp+560h+var_538], rax
0x1800ec3ea  lea     rax, [rbp+460h+var_388]
0x1800ec3f1  mov     qword ptr [rsp+560h+var_540], rax; int
0x1800ec3f6  lea     r9, [rbp+460h+var_3E8]
0x1800ec3fa  lea     r8, [rbp+460h+var_438]
0x1800ec3fe  lea     rdx, [rbp+460h+var_440]
0x1800ec402  call    ?GetClickActions@InkPenBackupRestoreHandler@@AEAAXAEA_K0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEBV23@@Z; InkPenBackupRestoreHandler::GetClickActions(unsigned __int64 &,unsigned __int64 &,std::wstring &,std::wstring &,std::wstring const &)
0x1800ec407  nop
0x1800ec408  lea     rcx, [rbp+460h+var_480]
0x1800ec40c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ec411  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ec418  jz      short loc_1800EC42C
0x1800ec41a  mov     r9, rbx
0x1800ec41d  lea     r8, aLongPress; "Long-Press"
0x1800ec424  mov     rdx, r13
0x1800ec427  call    McTemplateU0zz_EventWriteTransfer
0x1800ec42c  call    ??$InkPen_ApiActivity@AEAY0L@$$CBGAEAY0BP@$$CBGAEAY07$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0BP@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[11],ushort const (&)[31],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[31],ushort const (&)[8])
0x1800ec431  mov     rbx, [rbp+460h+var_488]
0x1800ec435  mov     qword ptr [rbp+460h+var_480], rbx
0x1800ec439  test    rbx, rbx
0x1800ec43c  jz      short loc_1800EC445
0x1800ec43e  lock inc dword ptr [rbx+118h]
0x1800ec445  lea     rcx, [rbx+8]
0x1800ec449  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800ec44e  mov     byte ptr [rbx+112h], 1
0x1800ec455  lea     rcx, [rbp+460h+var_480]
0x1800ec459  call    ??1?$test_data_control@V?$merged_data@U_tip_InkPenBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>(void)
0x1800ec45e  mov     [rbp+460h+var_4E0], 1
0x1800ec465  lea     r9, [rbp+460h+var_4E0]; unsigned int *
0x1800ec469  lea     rbx, aPenworkspaceap_1; "PenWorkspaceAppLaunchOnPenDetachEnabled"
0x1800ec470  mov     r8, rbx; unsigned __int16 *
0x1800ec473  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ec47a  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800ec481  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ec486  test    eax, eax
0x1800ec488  jz      short loc_1800EC4DE
0x1800ec48a  cmp     eax, 80070002h
0x1800ec48f  jz      short loc_1800EC4DE
0x1800ec491  test    eax, eax
0x1800ec493  jle     short loc_1800EC49D
0x1800ec495  movzx   eax, ax
0x1800ec498  or      eax, 80070000h
0x1800ec49d  mov     rcx, [rbp+468h]; this
0x1800ec4a4  test    eax, eax
0x1800ec4a6  jns     short loc_1800EC4BC
0x1800ec4a8  mov     r9d, eax; char *
0x1800ec4ab  lea     r8, aPcshellShellCl_29; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800ec4b2  mov     edx, 72h ; 'r'; void *
0x1800ec4b7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ec4bc  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ec4c3  jz      short loc_1800EC4D7
0x1800ec4c5  lea     r9, aFailed; "Failed"
0x1800ec4cc  mov     r8, rbx
0x1800ec4cf  mov     rdx, r13
0x1800ec4d2  call    McTemplateU0zz_EventWriteTransfer
0x1800ec4d7  call    ??$InkPen_ApiActivity@AEAY0L@$$CBGAEAY0DK@$$CBGAEAY06$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0DK@$$CBGAEAY06$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[11],ushort const (&)[58],ushort const (&)[7]>(ushort const (&)[11],ushort const (&)[58],ushort const (&)[7])
0x1800ec4dc  jmp     short loc_1800EC533
0x1800ec4de  cmp     [rbp+460h+var_4E0], 0
0x1800ec4e2  setnz   [rbp+460h+var_430]
0x1800ec4e6  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ec4ed  jz      short loc_1800EC501
0x1800ec4ef  lea     r9, aDone; "Done"
0x1800ec4f6  mov     r8, rbx
0x1800ec4f9  mov     rdx, r13
0x1800ec4fc  call    McTemplateU0zz_EventWriteTransfer
0x1800ec501  call    ??$InkPen_ApiActivity@AEAY0L@$$CBGAEAY0DK@$$CBGAEAY07$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0DK@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[11],ushort const (&)[58],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[58],ushort const (&)[8])
0x1800ec506  mov     rbx, [rbp+460h+var_488]
0x1800ec50a  mov     qword ptr [rbp+460h+var_480], rbx
0x1800ec50e  test    rbx, rbx
0x1800ec511  jz      short loc_1800EC51A
0x1800ec513  lock inc dword ptr [rbx+118h]
0x1800ec51a  lea     rcx, [rbx+8]
0x1800ec51e  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800ec523  mov     byte ptr [rbx+113h], 1
0x1800ec52a  lea     rcx, [rbp+460h+var_480]
0x1800ec52e  call    ??1?$test_data_control@V?$merged_data@U_tip_InkPenBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>(void)
0x1800ec533  mov     [rbp+460h+pvParam], 0
0x1800ec53a  xor     r9d, r9d; fWinIni
0x1800ec53d  lea     r8, [rbp+460h+pvParam]; pvParam
0x1800ec541  xor     edx, edx; uiParam
0x1800ec543  mov     ecx, 1052h; uiAction
0x1800ec548  call    cs:__imp_SystemParametersInfoW
0x1800ec54e  test    eax, eax
0x1800ec550  jz      short loc_1800EC5AD
0x1800ec552  cmp     [rbp+460h+pvParam], 0
0x1800ec556  setz    [rbp+460h+var_42F]
0x1800ec55a  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ec561  jz      short loc_1800EC579
0x1800ec563  lea     r9, aDone; "Done"
0x1800ec56a  lea     r8, aPenenablepenbu_2; "PenEnablePenButtonOverride"
0x1800ec571  mov     rdx, r13
0x1800ec574  call    McTemplateU0zz_EventWriteTransfer
0x1800ec579  call    ??$InkPen_ApiActivity@AEAY0L@$$CBGAEAY0DE@$$CBGAEAY07$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0DE@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[11],ushort const (&)[52],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[52],ushort const (&)[8])
0x1800ec57e  mov     rbx, [rbp+460h+var_488]
0x1800ec582  mov     qword ptr [rbp+460h+var_480], rbx
0x1800ec586  test    rbx, rbx
0x1800ec589  jz      short loc_1800EC592
0x1800ec58b  lock inc dword ptr [rbx+118h]
0x1800ec592  lea     rcx, [rbx+8]
0x1800ec596  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800ec59b  mov     byte ptr [rbx+114h], 1
0x1800ec5a2  lea     rcx, [rbp+460h+var_480]
0x1800ec5a6  call    ??1?$test_data_control@V?$merged_data@U_tip_InkPenBackupTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>::~test_data_control<tip2::details::merged_data<_tip_InkPenBackupTipTest,_tip_InkPenBackupTipTest>>(void)
0x1800ec5ab  jmp     short loc_1800EC602
0x1800ec5ad  call    cs:__imp_GetLastError
0x1800ec5b3  test    eax, eax
0x1800ec5b5  jle     short loc_1800EC5BF
0x1800ec5b7  movzx   eax, ax
0x1800ec5ba  or      eax, 80070000h
0x1800ec5bf  mov     rcx, [rbp+468h]; this
0x1800ec5c6  test    eax, eax
0x1800ec5c8  jns     short loc_1800EC5DE
0x1800ec5ca  mov     r9d, eax; char *
0x1800ec5cd  lea     r8, aPcshellShellCl_29; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800ec5d4  mov     edx, 81h; void *
0x1800ec5d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ec5de  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ec5e5  jz      short loc_1800EC5FD
0x1800ec5e7  lea     r9, aFailed; "Failed"
0x1800ec5ee  lea     r8, aPenenablepenbu_2; "PenEnablePenButtonOverride"
0x1800ec5f5  mov     rdx, r13
0x1800ec5f8  call    McTemplateU0zz_EventWriteTransfer
0x1800ec5fd  call    ??$InkPen_ApiActivity@AEAY0L@$$CBGAEAY0DE@$$CBGAEAY06$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0DE@$$CBGAEAY06$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[11],ushort const (&)[52],ushort const (&)[7]>(ushort const (&)[11],ushort const (&)[52],ushort const (&)[7])
0x1800ec602  lea     r13, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::GetImpl(void)'::`2'::impl
0x1800ec609  mov     rcx, r13
0x1800ec60c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialBrFailureReasonTelemetry>::__private_IsEnabled(void)
0x1800ec611  test    al, al
0x1800ec613  jz      short loc_1800EC61A
0x1800ec615  call    ??$InkPen_ApiActivity@AEAY0L@$$CBGAEAY0CA@$$CBGAEAY07$$CBG@InkPenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0CA@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::InkPenActivity::InkPen_ApiActivity<ushort const (&)[11],ushort const (&)[32],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[32],ushort const (&)[8])
0x1800ec61a  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ec621  jz      loc_1800EC6DD
0x1800ec627  lea     rcx, [rbp+460h+var_388]
0x1800ec62e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ec633  mov     rbx, rax
0x1800ec636  lea     rcx, [rbp+460h+var_3A8]
0x1800ec63d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ec642  mov     r11, rax
0x1800ec645  lea     rcx, [rbp+460h+var_3C8]
0x1800ec64c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ec651  mov     r10, rax
0x1800ec654  lea     rcx, [rbp+460h+var_3E8]
0x1800ec658  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ec65d  mov     r9, rax
0x1800ec660  lea     rcx, [rbp+460h+var_408]
0x1800ec664  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ec669  mov     r8, rax
0x1800ec66c  lea     rcx, [rbp+460h+var_428]
0x1800ec670  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ec675  movzx   ecx, [rbp+460h+var_42F]
0x1800ec679  movzx   edx, [rbp+460h+var_430]
0x1800ec67d  mov     [rsp+560h+var_4E8], rbx
0x1800ec682  mov     [rsp+560h+var_4F0], r11
0x1800ec687  mov     [rsp+560h+var_4F8], r10
0x1800ec68c  mov     [rsp+560h+var_500], r9
0x1800ec691  mov     [rsp+560h+var_508], r8
0x1800ec696  mov     [rsp+560h+var_510], rax
0x1800ec69b  mov     [rsp+560h+var_518], rcx
0x1800ec6a0  mov     [rsp+560h+var_520], rdx
0x1800ec6a5  mov     rax, [rbp+460h+var_438]
0x1800ec6a9  mov     [rsp+560h+var_528], rax
0x1800ec6ae  mov     rax, [rbp+460h+var_440]
0x1800ec6b2  mov     [rsp+560h+var_530], rax
0x1800ec6b7  mov     rax, [rbp+460h+var_448]
0x1800ec6bb  mov     [rsp+560h+var_538], rax
0x1800ec6c0  mov     rax, [rbp+460h+var_450]
0x1800ec6c4  mov     qword ptr [rsp+560h+var_540], rax
0x1800ec6c9  mov     r9, [rbp+460h+var_458]
0x1800ec6cd  mov     r8, [rbp+460h+var_460]
0x1800ec6d1  lea     rdx, BackupAssociatedInkPenSettingCloudFile
0x1800ec6d8  call    McTemplateU0xxxxxxxxzzzzzz_EventWriteTransfer
0x1800ec6dd  lea     rdx, [rbp+460h+var_340]; struct Windows::Data::Input::Devices::PenPerDevice *
0x1800ec6e4  lea     rcx, [rbp+460h+var_120]; this
0x1800ec6eb  call    ??0PenPerDevice@Devices@Input@Data@Windows@@QEAA@AEBU01234@@Z; Windows::Data::Input::Devices::PenPerDevice::PenPerDevice(Windows::Data::Input::Devices::PenPerDevice const &)
0x1800ec6f0  mov     rbx, rax
0x1800ec6f3  lea     rdx, [rbp+460h+var_460]; struct Windows::Data::Input::Devices::PenPerDevice *
0x1800ec6f7  lea     rcx, [rbp+460h+var_220]; this
0x1800ec6fe  call    ??0PenPerDevice@Devices@Input@Data@Windows@@QEAA@AEBU01234@@Z; Windows::Data::Input::Devices::PenPerDevice::PenPerDevice(Windows::Data::Input::Devices::PenPerDevice const &)
0x1800ec703  mov     rdx, rax
0x1800ec706  mov     rcx, rbx
0x1800ec709  call    ??8PenPerDevice@Devices@Input@Data@Windows@@QEBA_NAEBU01234@@Z; Windows::Data::Input::Devices::PenPerDevice::operator==(Windows::Data::Input::Devices::PenPerDevice const &)
0x1800ec70e  mov     bl, al
0x1800ec710  lea     rcx, [rbp+460h+var_220]; this
0x1800ec717  call    ??1PenPerDevice@Devices@Input@Data@Windows@@QEAA@XZ; Windows::Data::Input::Devices::PenPerDevice::~PenPerDevice(void)
0x1800ec71c  nop
0x1800ec71d  lea     rcx, [rbp+460h+var_120]; this
0x1800ec724  call    ??1PenPerDevice@Devices@Input@Data@Windows@@QEAA@XZ; Windows::Data::Input::Devices::PenPerDevice::~PenPerDevice(void)
0x1800ec729  test    bl, bl
  ... truncated ...
```
