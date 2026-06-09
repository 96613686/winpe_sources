# LockscreenBackupRestoreHandler::ComputePictureDetails(void)

- ea: `0x1800bca00`
- end: `0x1800bd328`
- name: `?ComputePictureDetails@LockscreenBackupRestoreHandler@@AEAAXXZ`
- size: `2344`
- prototype: `void __fastcall(LockscreenBackupRestoreHandler *__hidden this)`
- caller_count: `1`
- callee_count: `53`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800be080`

## callees

- `0x18000c6e0`
- `0x18000d688`
- `0x180012b84`
- `0x180012c0c`
- `0x1800162a4`
- `0x18001649c`
- `0x18001666c`
- `0x18001b6f4`
- `0x18001cf84`
- `0x18001cfa4`
- `0x18001d0a8`
- `0x18001d25c`
- `0x18001faa8`
- `0x180031774`
- `0x180036bb8`
- `0x180036ddc`
- `0x18003a3fc`
- `0x18006a090`
- `0x18006f444`
- `0x18008d374`
- `0x1800977e8`
- `0x18009defc`
- `0x1800a43ec`
- `0x1800a7a10`
- `0x1800a8a88`
- `0x1800aa010`
- `0x1800ad43c`
- `0x1800ad564`
- `0x1800ad734`
- `0x1800ad964`
- `0x1800ade3c`
- `0x1800adf58`
- `0x1800ae108`
- `0x1800ae278`
- `0x1800b0378`
- `0x1800b0830`
- `0x1800b0920`
- `0x1800b83a8`
- `0x1800b8450`
- `0x1800b8648`
- `0x1800b86f0`
- `0x1800b8790`
- `0x1800b8838`
- `0x1800b88e0`
- `0x1800b8a30`
- `0x1800b8ad8`
- `0x1800b8b80`
- `0x1800b8c28`
- `0x1800ba644`
- `0x1800bbde8`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1800bcea5`
- `ADVAPI32!RegGetValueW` at `0x1800bcefb`
- `ADVAPI32!RegGetValueW` at `0x1800bd0af`
- `ADVAPI32!RegGetValueW` at `0x1800bcea5`
- `ADVAPI32!RegGetValueW` at `0x1800bcefb`
- `ADVAPI32!RegGetValueW` at `0x1800bd0af`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800bcd33`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800bd188`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800bcd33`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800bd188`

## string_xrefs

- `0x1800bd09a`: `BackedUpLockscreenPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall LockscreenBackupRestoreHandler::ComputePictureDetails(LockscreenBackupRestoreHandler *this)
{
  bool v2; // r13
  __int64 v3; // r15
  DWORD v4; // r12d
  winrt::hstring *BackupInformation; // rax
  const unsigned __int16 *v6; // rax
  OneDriveUtils *v7; // rax
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rcx
  const struct std::filesystem::path *v10; // rdx
  bool v11; // bl
  __int64 v12; // rcx
  OneDriveUtils *v13; // rcx
  __int64 v14; // rcx
  unsigned __int8 IsMicrosoftAccount; // bl
  const wchar_t *v16; // r9
  __int64 matched; // rbx
  unsigned int v18; // eax
  enum AsyncStatus v19; // edx
  char v20; // bl
  __int64 v21; // rbx
  unsigned int v22; // eax
  enum AsyncStatus v23; // edx
  char Results; // bl
  const WCHAR *v25; // rax
  HRESULT v26; // eax
  OneDriveUtils *v27; // rax
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rcx
  const struct winrt::guid *v30; // rdx
  __int64 v31; // rcx
  char IsKnownFolderKFM; // r13
  __int64 IsKnownFolderKFMForAccount; // r13
  unsigned int v34; // eax
  enum AsyncStatus v35; // edx
  LSTATUS ValueW; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  bool v39; // sf
  LSTATUS v40; // eax
  bool v41; // sf
  OneDriveUtils *v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  LSTATUS v46; // eax
  __int64 v47; // rcx
  bool v48; // sf
  const struct std::filesystem::path *v49; // rdx
  const WCHAR *v50; // rax
  const unsigned __int16 *v51; // r8
  bool v52; // r13
  void *v53; // rcx
  HRESULT v54; // eax
  OneDriveUtils *v55; // rax
  __int64 v56; // r8
  void **v57; // rax
  __int64 v58; // r8
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  bool v61; // [rsp+40h] [rbp-C0h]
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v63[8]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbData[2]; // [rsp+58h] [rbp-A8h] BYREF
  void *v65[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v66[32]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v67[2]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD pvData[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR pszPath[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v2 = 0;
  pcbData[0] = 0;
  v65[0] = &qword_18017BC58;
  _InterlockedIncrement64(&qword_18017BC58);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::UserProfile::LockScreen,winrt::Windows::System::UserProfile::ILockScreenStatics> )
  {
    _lambda_1b2a61b495475c7a6ccbfc2658632acb_::operator()(
      this,
      v63,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::System::UserProfile::LockScreen,winrt::Windows::System::UserProfile::ILockScreenStatics>);
    v3 = -1;
    _InterlockedAdd64(&qword_18017BC58, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    v3 = -1;
    _InterlockedAdd64(&qword_18017BC58, 0xFFFFFFFFFFFFFFFFuLL);
    *(_QWORD *)&v67[0] = _lambda_30d70c6889399bb7f7d96e1f26c947d7_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::System::UserProfile::LockScreen,winrt::Windows::System::UserProfile::ILockScreenStatics>::call<winrt::Windows::Foundation::Uri (*)(winrt::Windows::System::UserProfile::ILockScreenStatics const &)>(
      this,
      v63,
      v67);
  }
  v4 = 12;
  *(_QWORD *)&v67[0] = 0;
  if ( !(unsigned __int8)winrt::Windows::Foundation::operator==(v63, v67) )
  {
    BackupInformation = (winrt::hstring *)winrt::impl::consume_Windows_Internal_Shell_AppRestore_Internal_IRestorableAppInternal<winrt::Windows::Internal::Shell::AppRestore::Internal::IRestorableAppInternal>::GetBackupInformation(
                                            v63,
                                            v67);
    v6 = winrt::hstring::c_str(BackupInformation);
    std::wstring::wstring(v66, v6);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v67);
    v7 = (OneDriveUtils *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v66);
    if ( OneDriveUtils::IsSystemImage(v7, v8) )
    {
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(v9, InformationMessage, L"Lockscreen Backup", L"It is a System Image");
      CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[14],unsigned short const (&)[8]>();
LABEL_9:
      *((_QWORD *)this + 116) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 912) = 0;
      *((_QWORD *)this + 112) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 880) = 0;
LABEL_101:
      std::wstring::_Tidy_deallocate(v66);
      goto LABEL_102;
    }
    std::filesystem::path::path((__int64)v65, (__int64)v66);
    v11 = std::filesystem::exists((std::filesystem *)v65, v10);
    std::wstring::_Tidy_deallocate(v65);
    if ( !v11 )
    {
      CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<unsigned short const (&)[22],unsigned short const (&)[21],unsigned short const (&)[24]>();
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(
          v12,
          InformationMessage,
          L"User Preferred Image",
          L"Chosen Image doesn't exist on system");
      goto LABEL_9;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::GetImpl'::`2'::impl) )
    {
      IsMicrosoftAccount = OneDriveUtils::IsMicrosoftAccount(v13);
      v2 = IsMicrosoftAccount != 0;
      v61 = IsMicrosoftAccount != 0;
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      {
        v16 = L"true";
        if ( !IsMicrosoftAccount )
          v16 = L"false";
        McTemplateU0zz_EventWriteTransfer(v14, InformationMessage, L"Background Backup, IsMicrosoftAccount", v16);
      }
      if ( !IsMicrosoftAccount )
        goto LABEL_23;
      matched = OneDriveUtils::ValidateOneDriveAccountMatchAsync(v65);
      v4 = 13;
      pcbData[0] = 13;
      v18 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<bool>>::Status(matched);
      if ( !v18 )
        v18 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<bool>>(matched);
      winrt::impl::check_status_canceled((winrt::impl *)v18, v19);
      if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::GetResults(matched) )
LABEL_23:
        v20 = 0;
      else
        v20 = 1;
      if ( (v4 & 1) != 0 )
      {
        v4 &= ~1u;
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v65);
      }
      if ( v20 )
      {
LABEL_27:
        if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
          McTemplateU0zz_EventWriteTransfer(
            v14,
            InformationMessage,
            L"Lockscreen Backup",
            L"Primary OneDrive account userID does not match with the logged in account's userID");
        CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[50],unsigned short const (&)[8]>();
        *((_QWORD *)this + 116) = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 912) = 0;
        *((_QWORD *)this + 112) = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 880) = 0;
        goto LABEL_101;
      }
    }
    else
    {
      v61 = 0;
      v21 = OneDriveUtils::ValidateOneDriveAccountMatchAsync(v65);
      v22 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<bool>>::Status(v21);
      if ( !v22 )
        v22 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<bool>>(v21);
      winrt::impl::check_status_canceled((winrt::impl *)v22, v23);
      Results = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::GetResults(v21);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v65);
      if ( !Results )
        goto LABEL_27;
    }
    ppv = 0;
    v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v66);
    v26 = SHCreateItemFromParsingName(v25, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
        (const char *)(unsigned int)v26,
        pdwType);
    v27 = (OneDriveUtils *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v66);
    if ( OneDriveUtils::IsPathInOneDrive(v27, v28) )
      goto LABEL_90;
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(v29, InformationMessage, L"Lockscreen Backup", L"It is not a Cloud Image");
    CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[18],unsigned short const (&)[8]>();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::GetImpl'::`2'::impl) )
    {
      if ( v2 )
      {
        *(GUID *)v65 = FOLDERID_Pictures;
        IsKnownFolderKFM = OneDriveUtils::IsKnownFolderKFM((OneDriveUtils *)v65, v30);
      }
      else
      {
        v67[0] = FOLDERID_Pictures;
        IsKnownFolderKFMForAccount = OneDriveUtils::IsKnownFolderKFMForAccount((winrt::Windows::Foundation::IUnknown *)v65);
        v34 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<bool>>::Status(IsKnownFolderKFMForAccount);
        if ( !v34 )
          v34 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<bool>>(IsKnownFolderKFMForAccount);
        winrt::impl::check_status_canceled((winrt::impl *)v34, v35);
        IsKnownFolderKFM = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::GetResults(IsKnownFolderKFMForAccount);
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v65);
      }
      if ( !IsKnownFolderKFM )
      {
        if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
          McTemplateU0zz_EventWriteTransfer(
            v31,
            InformationMessage,
            L"Lockscreen Backup",
            L"Picture Folder does not support KFM");
        CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[36],unsigned short const (&)[8]>();
        *((_QWORD *)this + 116) = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 912) = 0;
        *((_QWORD *)this + 112) = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 880) = 0;
        memset_0(pvData, 0, 0x208u);
        pcbData[0] = 520;
        ValueW = RegGetValueW(HKEY_CURRENT_USER, L"Software\\Microsoft\\OneDrive", L"version", 2u, 0, pvData, pcbData);
        v39 = ValueW < 0;
        if ( ValueW )
        {
          pvData[0] = 0;
          if ( ValueW > 0 )
            v39 = 1;
        }
        if ( !v39 )
          goto LABEL_54;
        pcbData[0] = 520;
        v40 = RegGetValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\OneDrive", L"version", 2u, 0, pvData, pcbData);
        v41 = v40 < 0;
        if ( v40 )
        {
          pvData[0] = 0;
          if ( v40 > 0 )
            v41 = 1;
        }
        if ( !v41 )
        {
LABEL_54:
          if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
            McTemplateU0zz_EventWriteTransfer(v38, InformationMessage, L"Lockscreen Backup", pvData);
          CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[17],unsigned short (&)[260]>(
            v38,
            v37,
            pvData);
        }
        goto LABEL_100;
      }
      if ( !v61 )
      {
LABEL_70:
        *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>>::operator->(
                                (char *)this + 680,
                                v65)
                 + 276LL) = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>>::~test_data_control<tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>>(v65);
        memset_0(pszPath, 0, 0x208u);
        if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
          McTemplateU0zz_EventWriteTransfer(
            v45,
            InformationMessage,
            L"Lockscreen Backup",
            L"Picture Folder supports KFM");
        CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[19],unsigned short const (&)[8]>();
        pcbData[0] = 520;
        v46 = RegGetValueW(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
                L"BackedUpLockscreenPath",
                2u,
                0,
                pszPath,
                pcbData);
        v48 = v46 < 0;
        if ( v46 )
        {
          v47 = 0;
          pszPath[0] = 0;
          v48 = v46 < 0;
          if ( v46 > 0 )
            v48 = 1;
        }
        v52 = 0;
        if ( !v48 )
        {
          std::filesystem::path::path((__int64)v65, (__int64)pszPath);
          v4 |= 2u;
          pcbData[0] = v4;
          if ( std::filesystem::exists((std::filesystem *)v65, v49) )
          {
            v50 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v66);
            if ( OneDriveUtils::IsFileIdentical(v50, pszPath, v51) )
              v52 = 1;
          }
        }
        if ( (v4 & 2) != 0 )
          std::wstring::_Tidy_deallocate(v65);
        if ( v52 )
        {
          if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
            McTemplateU0zz_EventWriteTransfer(
              v47,
              InformationMessage,
              L"Lockscreen Backup",
              L"current lockscreen wallpaper is same as the last backed up wallpaper");
          CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[69],unsigned short const (&)[8]>();
          v53 = ppv;
          ppv = 0;
          if ( v53 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v53 + 16LL))(v53);
          v54 = SHCreateItemFromParsingName(pszPath, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
          if ( v54 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x16B,
              (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\lockscreenbackuprestorehandler.cpp",
              (const char *)(unsigned int)v54,
              pdwTypea);
        }
        else
        {
          std::wstring::wstring(v67, L"LockScreen");
          v55 = (OneDriveUtils *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v66);
          v57 = OneDriveUtils::CopyToPictures(v65, v55, v56);
          wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(
            &ppv,
            v57);
          wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(v65);
        }
LABEL_90:
        if ( ppv )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>>::operator->(
                                  (char *)this + 680,
                                  v65)
                   + 275LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>>::~test_data_control<tip2::details::merged_data<_tip_LockscreenBackupTipTests,_tip_LockscreenBackupTipTests>>(v65);
          OneDriveUtils::GetStorageProviderFileId(v67, ppv);
          if ( *(_QWORD *)&v67[0] )
          {
            v58 = -1;
            do
              ++v58;
            while ( *(_WORD *)(*(_QWORD *)&v67[0] + 2 * v58) );
            std::wstring::_Assign<unsigned short>((char *)this + 880, *(_QWORD *)&v67[0], v58);
          }
          OneDriveUtils::GetStorageProviderContentUri(pcbData, ppv);
          if ( *(_QWORD *)pcbData )
          {
            do
              ++v3;
            while ( *(_WORD *)(*(_QWORD *)pcbData + 2 * v3) );
            std::wstring::_Assign<unsigned short>((char *)this + 912, *(_QWORD *)pcbData, v3);
          }
          CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[17],unsigned short const (&)[8]>();
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(pcbData);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v67);
        }
        else
        {
          CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[21],unsigned short const (&)[8]>();
          *((_QWORD *)this + 116) = 0;
          *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 912) = 0;
          *((_QWORD *)this + 112) = 0;
          *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 880) = 0;
        }
        goto LABEL_100;
      }
    }
    else
    {
      *(GUID *)v65 = FOLDERID_Pictures;
      if ( !OneDriveUtils::IsKnownFolderKFM((OneDriveUtils *)v65, v30) )
      {
        if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
          McTemplateU0zz_EventWriteTransfer(
            v44,
            InformationMessage,
            L"Lockscreen Backup",
            L"Picture Folder does not support KFM");
        CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[36],unsigned short const (&)[8]>();
        goto LABEL_63;
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WASCConsentForOneDrive>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WASCConsentForOneDrive>::GetImpl'::`2'::impl) )
    {
      if ( !OneDriveUtils::IsUserConsentForDataSharing(v42) )
      {
        if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
          McTemplateU0zz_EventWriteTransfer(
            v43,
            InformationMessage,
            L"Lockscreen Backup",
            L"User has not given consent for data sharing");
        CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<unsigned short const (&)[22],unsigned short const (&)[44],unsigned short const (&)[11]>();
LABEL_63:
        *((_QWORD *)this + 116) = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 912) = 0;
        *((_QWORD *)this + 112) = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 880) = 0;
LABEL_100:
        wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&ppv);
        goto LABEL_101;
      }
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(
          v43,
          InformationMessage,
          L"Lockscreen Backup",
          L"going ahead with normal process after checking WASC");
    }
    goto LABEL_70;
  }
LABEL_102:
  _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v63);
}

```

## disassembly

```asm
0x1800bca00  push    rbp
0x1800bca02  push    rbx
0x1800bca03  push    rsi
0x1800bca04  push    rdi
0x1800bca05  push    r12
0x1800bca07  push    r13
0x1800bca09  push    r14
0x1800bca0b  push    r15
0x1800bca0d  lea     rbp, [rsp-3F8h]
0x1800bca15  sub     rsp, 4F8h
0x1800bca1c  mov     rax, cs:__security_cookie
0x1800bca23  xor     rax, rsp
0x1800bca26  mov     [rbp+430h+var_50], rax
0x1800bca2d  mov     r14, rcx
0x1800bca30  xor     r13d, r13d
0x1800bca33  mov     [rsp+530h+var_4D8], r13d
0x1800bca38  lea     rax, qword_18017BC58
0x1800bca3f  mov     [rsp+530h+var_4D0], rax
0x1800bca44  lock inc cs:qword_18017BC58
0x1800bca4c  cmp     cs:??$factory_cache_entry_v@ULockScreen@UserProfile@System@Windows@winrt@@UILockScreenStatics@2345@@impl@winrt@@3U?$factory_cache_entry@ULockScreen@UserProfile@System@Windows@winrt@@UILockScreenStatics@2345@@12@A, r13; factory_cache_entry<winrt::Windows::System::UserProfile::LockScreen,winrt::Windows::System::UserProfile::ILockScreenStatics>::winrt::factory_cache_entry<winrt::Windows::System::UserProfile::LockScreen,winrt::Windows::System::UserProfile::ILockScreenStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::UserProfile::LockScreen,winrt::Windows::System::UserProfile::ILockScreenStatics>
0x1800bca53  jz      short loc_1800BCA75
0x1800bca55  lea     r8, ??$factory_cache_entry_v@ULockScreen@UserProfile@System@Windows@winrt@@UILockScreenStatics@2345@@impl@winrt@@3U?$factory_cache_entry@ULockScreen@UserProfile@System@Windows@winrt@@UILockScreenStatics@2345@@12@A; factory_cache_entry<winrt::Windows::System::UserProfile::LockScreen,winrt::Windows::System::UserProfile::ILockScreenStatics>::winrt::factory_cache_entry<winrt::Windows::System::UserProfile::LockScreen,winrt::Windows::System::UserProfile::ILockScreenStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::UserProfile::LockScreen,winrt::Windows::System::UserProfile::ILockScreenStatics>
0x1800bca5c  lea     rdx, [rsp+530h+var_4E0]
0x1800bca61  call    ??R_lambda_1b2a61b495475c7a6ccbfc2658632acb_@@QEBA@AEBUIEngagementManagerStatics@UserProfile@System@WindowsUdk@winrt@@@Z; _lambda_1b2a61b495475c7a6ccbfc2658632acb_::operator()(winrt::WindowsUdk::System::UserProfile::IEngagementManagerStatics const &)
0x1800bca66  nop
0x1800bca67  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800bca6b  lock add cs:qword_18017BC58, r15
0x1800bca73  jmp     short loc_1800BCA9A
0x1800bca75  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800bca79  lock add cs:qword_18017BC58, r15
0x1800bca81  lea     rax, ?_lambda_invoker_cdecl_@_lambda_30d70c6889399bb7f7d96e1f26c947d7_@@CA@AEBUIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@WindowsUdk@winrt@@@Z; _lambda_30d70c6889399bb7f7d96e1f26c947d7_::_lambda_invoker_cdecl_(winrt::WindowsUdk::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics const &)
0x1800bca88  mov     qword ptr [rbp+430h+var_490], rax
0x1800bca8c  lea     r8, [rbp+430h+var_490]
0x1800bca90  lea     rdx, [rsp+530h+var_4E0]
0x1800bca95  call    ??$call@P6A?AUUri@Foundation@Windows@winrt@@AEBUILockScreenStatics@UserProfile@System@34@@Z@?$factory_cache_entry@ULockScreen@UserProfile@System@Windows@winrt@@UILockScreenStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AUUri@Foundation@Windows@2@AEBUILockScreenStatics@UserProfile@System@52@@Z@Z
0x1800bca9a  mov     r12d, 0Ch
0x1800bcaa0  mov     qword ptr [rbp+430h+var_490], r13
0x1800bcaa4  lea     rdx, [rbp+430h+var_490]
0x1800bcaa8  lea     rcx, [rsp+530h+var_4E0]
0x1800bcaad  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x1800bcab2  test    al, al
0x1800bcab4  jnz     loc_1800BD2D1
0x1800bcaba  lea     rdx, [rbp+430h+var_490]
0x1800bcabe  lea     rcx, [rsp+530h+var_4E0]
0x1800bcac3  call    ?GetBackupInformation@?$consume_Windows_Internal_Shell_AppRestore_Internal_IRestorableAppInternal@UIRestorableAppInternal@Internal@AppRestore@Shell@2Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_AppRestore_Internal_IRestorableAppInternal<winrt::Windows::Internal::Shell::AppRestore::Internal::IRestorableAppInternal>::GetBackupInformation(void)
0x1800bcac8  nop
0x1800bcac9  mov     rcx, rax; this
0x1800bcacc  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800bcad1  mov     rdx, rax
0x1800bcad4  lea     rcx, [rbp+430h+var_4B0]
0x1800bcad8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800bcadd  nop
0x1800bcade  lea     rcx, [rbp+430h+var_490]
0x1800bcae2  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800bcae7  lea     rcx, [rbp+430h+var_4B0]
0x1800bcaeb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800bcaf0  mov     rcx, rax; this
0x1800bcaf3  call    ?IsSystemImage@OneDriveUtils@@YA_NPEBG@Z; OneDriveUtils::IsSystemImage(ushort const *)
0x1800bcaf8  test    al, al
0x1800bcafa  jz      short loc_1800BCB54
0x1800bcafc  mov     dil, 4
0x1800bcaff  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, dil
0x1800bcb06  jz      short loc_1800BCB22
0x1800bcb08  lea     r9, aItIsASystemIma; "It is a System Image"
0x1800bcb0f  lea     r8, aLockscreenBack_0; "Lockscreen Backup"
0x1800bcb16  lea     rdx, InformationMessage
0x1800bcb1d  call    McTemplateU0zz_EventWriteTransfer
0x1800bcb22  call    ??$Lockscreen_ApiActivity@AEAY0L@$$CBGAEAY0O@$$CBGAEAY07$$CBG@LockscreenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0O@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<ushort const (&)[11],ushort const (&)[14],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[14],ushort const (&)[8])
0x1800bcb27  lea     rcx, [r14+390h]
0x1800bcb2e  mov     [rcx+10h], r13
0x1800bcb32  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800bcb37  mov     [rax], r13w
0x1800bcb3b  lea     rcx, [r14+370h]
0x1800bcb42  mov     [rcx+10h], r13
0x1800bcb46  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800bcb4b  mov     [rax], r13w
0x1800bcb4f  jmp     loc_1800BD2C7
0x1800bcb54  lea     rdx, [rbp+430h+var_4B0]
0x1800bcb58  lea     rcx, [rsp+530h+var_4D0]
0x1800bcb5d  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@path@filesystem@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@W4format@012@@Z; std::filesystem::path::path(std::wstring const &,std::filesystem::path::format)
0x1800bcb62  nop
0x1800bcb63  lea     rcx, [rsp+530h+var_4D0]; this
0x1800bcb68  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x1800bcb6d  mov     bl, al
0x1800bcb6f  lea     rcx, [rsp+530h+var_4D0]
0x1800bcb74  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800bcb79  test    bl, bl
0x1800bcb7b  jnz     short loc_1800BCBAD
0x1800bcb7d  call    ??$Lockscreen_ApiActivity@AEAY0BG@$$CBGAEAY0BF@$$CBGAEAY0BI@$$CBG@LockscreenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BG@$$CBGAEAY0BF@$$CBGAEAY0BI@$$CBG@Z; CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<ushort const (&)[22],ushort const (&)[21],ushort const (&)[24]>(ushort const (&)[22],ushort const (&)[21],ushort const (&)[24])
0x1800bcb82  mov     dil, 4
0x1800bcb85  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, dil
0x1800bcb8c  jz      short loc_1800BCB27
0x1800bcb8e  lea     r9, aChosenImageDoe; "Chosen Image doesn't exist on system"
0x1800bcb95  lea     r8, aUserPreferredI; "User Preferred Image"
0x1800bcb9c  lea     rdx, InformationMessage
0x1800bcba3  call    McTemplateU0zz_EventWriteTransfer
0x1800bcba8  jmp     loc_1800BCB27
0x1800bcbad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialWallpaperBackup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialWallpaperBackup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialWallpaperBackup> `wil::Feature<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::GetImpl(void)'::`2'::impl
0x1800bcbb4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialWallpaperBackup@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::__private_IsEnabled(void)
0x1800bcbb9  mov     dil, 4
0x1800bcbbc  lea     rsi, InformationMessage
0x1800bcbc3  test    al, al
0x1800bcbc5  jz      loc_1800BCCC9
0x1800bcbcb  call    ?IsMicrosoftAccount@OneDriveUtils@@YAEXZ; OneDriveUtils::IsMicrosoftAccount(void)
0x1800bcbd0  mov     bl, al
0x1800bcbd2  test    al, al
0x1800bcbd4  setnz   r13b
0x1800bcbd8  mov     [rsp+530h+var_4F0], r13b
0x1800bcbdd  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, dil
0x1800bcbe4  jz      short loc_1800BCC09
0x1800bcbe6  lea     rax, aFalse_0; "false"
0x1800bcbed  lea     r9, aTrue; "true"
0x1800bcbf4  test    bl, bl
0x1800bcbf6  cmovz   r9, rax
0x1800bcbfa  lea     r8, aBackgroundBack; "Background Backup, IsMicrosoftAccount"
0x1800bcc01  mov     rdx, rsi
0x1800bcc04  call    McTemplateU0zz_EventWriteTransfer
0x1800bcc09  test    bl, bl
0x1800bcc0b  jz      short loc_1800BCC50
0x1800bcc0d  lea     rcx, [rsp+530h+var_4D0]
0x1800bcc12  call    ?ValidateOneDriveAccountMatchAsync@OneDriveUtils@@YA?AU?$IAsyncOperation@_N@Foundation@Windows@winrt@@XZ; OneDriveUtils::ValidateOneDriveAccountMatchAsync(void)
0x1800bcc17  mov     rbx, rax
0x1800bcc1a  mov     r12d, 0Dh
0x1800bcc20  mov     [rsp+530h+var_4D8], r12d
0x1800bcc25  mov     rcx, rax
0x1800bcc28  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<bool>>::Status(void)
0x1800bcc2d  test    eax, eax
0x1800bcc2f  jnz     short loc_1800BCC39
0x1800bcc31  mov     rcx, rbx
0x1800bcc34  call    ??$wait_for_completed@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@_N@Foundation@Windows@1@I@Z
0x1800bcc39  mov     ecx, eax; this
0x1800bcc3b  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x1800bcc40  mov     rcx, rbx
0x1800bcc43  call    ?GetResults@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@_N@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::GetResults(void)
0x1800bcc48  test    al, al
0x1800bcc4a  jnz     short loc_1800BCC50
0x1800bcc4c  mov     bl, 1
0x1800bcc4e  jmp     short loc_1800BCC52
0x1800bcc50  xor     bl, bl
0x1800bcc52  test    r12b, 1
0x1800bcc56  jz      short loc_1800BCC66
0x1800bcc58  and     r12d, 0FFFFFFFEh
0x1800bcc5c  lea     rcx, [rsp+530h+var_4D0]; this
0x1800bcc61  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800bcc66  test    bl, bl
0x1800bcc68  jz      loc_1800BCD12
0x1800bcc6e  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, dil
0x1800bcc75  jz      short loc_1800BCC8D
0x1800bcc77  lea     r9, aPrimaryOnedriv; "Primary OneDrive account userID does no"...
0x1800bcc7e  lea     r8, aLockscreenBack_0; "Lockscreen Backup"
0x1800bcc85  mov     rdx, rsi
0x1800bcc88  call    McTemplateU0zz_EventWriteTransfer
0x1800bcc8d  call    ??$Lockscreen_ApiActivity@AEAY0L@$$CBGAEAY0DC@$$CBGAEAY07$$CBG@LockscreenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0DC@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<ushort const (&)[11],ushort const (&)[50],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[50],ushort const (&)[8])
0x1800bcc92  lea     rcx, [r14+390h]
0x1800bcc99  mov     qword ptr [rcx+10h], 0
0x1800bcca1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800bcca6  xor     ecx, ecx
0x1800bcca8  mov     [rax], cx
0x1800bccab  lea     rcx, [r14+370h]
0x1800bccb2  mov     qword ptr [rcx+10h], 0
0x1800bccba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800bccbf  xor     ecx, ecx
0x1800bccc1  mov     [rax], cx
0x1800bccc4  jmp     loc_1800BD2C7
0x1800bccc9  mov     [rsp+530h+var_4F0], r13b
0x1800bccce  lea     rcx, [rsp+530h+var_4D0]
0x1800bccd3  call    ?ValidateOneDriveAccountMatchAsync@OneDriveUtils@@YA?AU?$IAsyncOperation@_N@Foundation@Windows@winrt@@XZ; OneDriveUtils::ValidateOneDriveAccountMatchAsync(void)
0x1800bccd8  mov     rbx, rax
0x1800bccdb  mov     rcx, rax
0x1800bccde  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<bool>>::Status(void)
0x1800bcce3  test    eax, eax
0x1800bcce5  jnz     short loc_1800BCCEF
0x1800bcce7  mov     rcx, rbx
0x1800bccea  call    ??$wait_for_completed@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@_N@Foundation@Windows@1@I@Z
0x1800bccef  mov     ecx, eax; this
0x1800bccf1  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x1800bccf6  mov     rcx, rbx
0x1800bccf9  call    ?GetResults@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@_N@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::GetResults(void)
0x1800bccfe  mov     bl, al
0x1800bcd00  lea     rcx, [rsp+530h+var_4D0]; this
0x1800bcd05  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800bcd0a  test    bl, bl
0x1800bcd0c  jz      loc_1800BCC6E
0x1800bcd12  xor     ebx, ebx
0x1800bcd14  mov     [rsp+530h+ppv], rbx
0x1800bcd19  lea     rcx, [rbp+430h+var_4B0]
0x1800bcd1d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800bcd22  mov     rcx, rax; pszPath
0x1800bcd25  lea     r9, [rsp+530h+ppv]; ppv
0x1800bcd2a  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1800bcd31  xor     edx, edx; pbc
0x1800bcd33  call    cs:__imp_SHCreateItemFromParsingName
0x1800bcd39  mov     rcx, [rbp+438h]; this
0x1800bcd40  test    eax, eax
0x1800bcd42  js      loc_1800BD2FE
0x1800bcd48  lea     rcx, [rbp+430h+var_4B0]
0x1800bcd4c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800bcd51  mov     rcx, rax; this
0x1800bcd54  call    ?IsPathInOneDrive@OneDriveUtils@@YA_NPEBG@Z; OneDriveUtils::IsPathInOneDrive(ushort const *)
0x1800bcd59  test    al, al
0x1800bcd5b  jnz     loc_1800BD1E1
0x1800bcd61  lea     rbx, aLockscreenBack_0; "Lockscreen Backup"
0x1800bcd68  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, dil
0x1800bcd6f  jz      short loc_1800BCD83
0x1800bcd71  lea     r9, aItIsNotACloudI; "It is not a Cloud Image"
0x1800bcd78  mov     r8, rbx
0x1800bcd7b  mov     rdx, rsi
0x1800bcd7e  call    McTemplateU0zz_EventWriteTransfer
0x1800bcd83  call    ??$Lockscreen_ApiActivity@AEAY0L@$$CBGAEAY0BC@$$CBGAEAY07$$CBG@LockscreenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0BC@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<ushort const (&)[11],ushort const (&)[18],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[18],ushort const (&)[8])
0x1800bcd88  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialWallpaperBackup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialWallpaperBackup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialWallpaperBackup> `wil::Feature<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::GetImpl(void)'::`2'::impl
0x1800bcd8f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialWallpaperBackup@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::__private_IsEnabled(void)
0x1800bcd94  movups  xmm0, xmmword ptr cs:FOLDERID_Pictures.Data1
0x1800bcd9b  test    al, al
0x1800bcd9d  jz      loc_1800BCFBC
0x1800bcda3  test    r13b, r13b
0x1800bcda6  jz      short loc_1800BCDBD
0x1800bcda8  movdqu  xmmword ptr [rsp+530h+var_4D0], xmm0
0x1800bcdae  lea     rcx, [rsp+530h+var_4D0]; this
0x1800bcdb3  call    ?IsKnownFolderKFM@OneDriveUtils@@YA_NAEBUguid@winrt@@@Z; OneDriveUtils::IsKnownFolderKFM(winrt::guid const &)
0x1800bcdb8  mov     r13b, al
0x1800bcdbb  jmp     short loc_1800BCE03
0x1800bcdbd  movdqu  [rbp+430h+var_490], xmm0
0x1800bcdc2  lea     rdx, [rbp+430h+var_490]
0x1800bcdc6  lea     rcx, [rsp+530h+var_4D0]; this
0x1800bcdcb  call    ?IsKnownFolderKFMForAccount@OneDriveUtils@@YA?AU?$IAsyncOperation@_N@Foundation@Windows@winrt@@AEBUguid@5@@Z; OneDriveUtils::IsKnownFolderKFMForAccount(winrt::guid const &)
0x1800bcdd0  mov     r13, rax
0x1800bcdd3  mov     rcx, rax
0x1800bcdd6  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<bool>>::Status(void)
0x1800bcddb  test    eax, eax
0x1800bcddd  jnz     short loc_1800BCDE7
0x1800bcddf  mov     rcx, r13
0x1800bcde2  call    ??$wait_for_completed@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@_N@Foundation@Windows@1@I@Z
0x1800bcde7  mov     ecx, eax; this
0x1800bcde9  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x1800bcdee  mov     rcx, r13
0x1800bcdf1  call    ?GetResults@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@_N@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::GetResults(void)
0x1800bcdf6  mov     r13b, al
0x1800bcdf9  lea     rcx, [rsp+530h+var_4D0]; this
0x1800bcdfe  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800bce03  test    r13b, r13b
0x1800bce06  jnz     loc_1800BCF40
0x1800bce0c  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, dil
0x1800bce13  jz      short loc_1800BCE27
0x1800bce15  lea     r9, aPictureFolderD; "Picture Folder does not support KFM"
0x1800bce1c  mov     r8, rbx
0x1800bce1f  mov     rdx, rsi
0x1800bce22  call    McTemplateU0zz_EventWriteTransfer
0x1800bce27  call    ??$Lockscreen_ApiActivity@AEAY0L@$$CBGAEAY0CE@$$CBGAEAY07$$CBG@LockscreenActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0CE@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::LockscreenActivity::Lockscreen_ApiActivity<ushort const (&)[11],ushort const (&)[36],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[36],ushort const (&)[8])
0x1800bce2c  lea     rcx, [r14+390h]
0x1800bce33  xor     r12d, r12d
0x1800bce36  mov     [rcx+10h], r12
0x1800bce3a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800bce3f  mov     [rax], r12w
0x1800bce43  lea     rcx, [r14+370h]
0x1800bce4a  mov     [rcx+10h], r12
0x1800bce4e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800bce53  mov     [rax], r12w
0x1800bce57  mov     r15d, 208h
0x1800bce5d  mov     r8d, r15d; Size
0x1800bce60  xor     edx, edx; Val
0x1800bce62  lea     rcx, [rbp+430h+var_470]; void *
0x1800bce66  call    memset_0
0x1800bce6b  mov     [rsp+530h+var_4D8], r15d
0x1800bce70  lea     rax, [rsp+530h+var_4D8]
0x1800bce75  mov     [rsp+530h+pcbData], rax; pcbData
0x1800bce7a  lea     rax, [rbp+430h+var_470]
0x1800bce7e  mov     [rsp+530h+pvData], rax; pvData
0x1800bce83  mov     [rsp+530h+pdwType], r12; pdwType
0x1800bce88  lea     r14d, [r12+2]
0x1800bce8d  mov     r9d, r14d; dwFlags
0x1800bce90  lea     r8, aVersion; "version"
0x1800bce97  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\OneDrive"
0x1800bce9e  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800bcea5  call    cs:__imp_RegGetValueW
0x1800bceab  mov     r13d, 80070000h
0x1800bceb1  test    eax, eax
0x1800bceb3  jz      short loc_1800BCEC4
0x1800bceb5  mov     [rbp+430h+var_470], r12w
0x1800bceba  jle     short loc_1800BCEC4
0x1800bcebc  movzx   eax, ax
0x1800bcebf  or      eax, r13d
0x1800bcec2  test    eax, eax
0x1800bcec4  jns     short loc_1800BCF1A
0x1800bcec6  mov     [rsp+530h+var_4D8], r15d
0x1800bcecb  lea     rax, [rsp+530h+var_4D8]
0x1800bced0  mov     [rsp+530h+pcbData], rax; pcbData
0x1800bced5  lea     rax, [rbp+430h+var_470]
0x1800bced9  mov     [rsp+530h+pvData], rax; pvData
0x1800bcede  mov     [rsp+530h+pdwType], r12; pdwType
0x1800bcee3  mov     r9d, r14d; dwFlags
0x1800bcee6  lea     r8, aVersion; "version"
0x1800bceed  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\OneDrive"
0x1800bcef4  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800bcefb  call    cs:__imp_RegGetValueW
0x1800bcf01  test    eax, eax
0x1800bcf03  jz      short loc_1800BCF14
0x1800bcf05  mov     [rbp+430h+var_470], r12w
0x1800bcf0a  jle     short loc_1800BCF14
0x1800bcf0c  movzx   eax, ax
0x1800bcf0f  or      eax, r13d
  ... truncated ...
```
