# BackgroundBackupRestoreHandler::ComputePictureDetails(wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper> &)

- ea: `0x1800a96f0`
- end: `0x1800aa009`
- name: `?ComputePictureDetails@BackgroundBackupRestoreHandler@@AEAAXAEAV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@@Z`
- size: `2329`
- prototype: `_WORD *__fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `49`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ae540`

## callees

- `0x18000c6e0`
- `0x18000d688`
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
- `0x18004623c`
- `0x18006a090`
- `0x18006f444`
- `0x1800977e8`
- `0x18009defc`
- `0x1800a43ec`
- `0x1800a499c`
- `0x1800a4a3c`
- `0x1800a4ae4`
- `0x1800a4b84`
- `0x1800a4cd4`
- `0x1800a4d7c`
- `0x1800a4e24`
- `0x1800a4ecc`
- `0x1800a4f74`
- `0x1800a501c`
- `0x1800a516c`
- `0x1800a5520`
- `0x1800a7a10`
- `0x1800a8688`
- `0x1800a8954`
- `0x1800a93a8`
- `0x1800a96f0`
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
- `0x18012d010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1800a977e`
- `ADVAPI32!RegGetValueW` at `0x1800a9b34`
- `ADVAPI32!RegGetValueW` at `0x1800a9b8b`
- `ADVAPI32!RegGetValueW` at `0x1800a9d1b`
- `ADVAPI32!RegGetValueW` at `0x1800a977e`
- `ADVAPI32!RegGetValueW` at `0x1800a9b34`
- `ADVAPI32!RegGetValueW` at `0x1800a9b8b`
- `ADVAPI32!RegGetValueW` at `0x1800a9d1b`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800a9de3`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800a9f3d`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800a9de3`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800a9f3d`

## string_xrefs

- `0x1800a9d06`: `BackedUpWallpaperPath`

## pseudocode

```c
_WORD *__fastcall BackgroundBackupRestoreHandler::ComputePictureDetails(__int64 a1, __int64 a2)
{
  char v4; // r15
  DWORD v5; // r14d
  LSTATUS ValueW; // eax
  unsigned __int64 v7; // r9
  wil::details::in1diag3 *v8; // rcx
  const unsigned __int16 *v9; // rdx
  __int64 v10; // rcx
  _WORD *result; // rax
  const struct std::filesystem::path *v12; // rdx
  bool v13; // bl
  __int64 v14; // rcx
  OneDriveUtils *v15; // rcx
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rcx
  unsigned __int8 IsMicrosoftAccount; // bl
  bool v19; // r12
  const wchar_t *v20; // r9
  __int64 matched; // rbx
  unsigned int v22; // eax
  enum AsyncStatus v23; // edx
  char Results; // al
  char v25; // bl
  __int64 v26; // rbx
  unsigned int v27; // eax
  enum AsyncStatus v28; // edx
  char v29; // bl
  __int64 v30; // rcx
  const struct winrt::guid *v31; // rdx
  __int64 v32; // rcx
  char IsKnownFolderKFM; // r15
  __int64 IsKnownFolderKFMForAccount; // r15
  unsigned int v35; // eax
  enum AsyncStatus v36; // edx
  LSTATUS v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rcx
  bool v40; // sf
  LSTATUS v41; // eax
  bool v42; // sf
  OneDriveUtils *v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  LSTATUS v48; // eax
  __int64 v49; // rcx
  bool v50; // sf
  const struct std::filesystem::path *v51; // rdx
  const unsigned __int16 *v52; // r8
  void *v53; // rcx
  HRESULT v54; // eax
  wil::details::in1diag3 *v55; // rcx
  __int64 v56; // rax
  void **v57; // rax
  __int64 v58; // rbx
  __int64 v59; // r8
  __int64 v60; // rcx
  HRESULT v61; // eax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  void *ppv; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  void *v66[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v67[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pvData[264]; // [rsp+90h] [rbp-70h] BYREF
  _WORD v69[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR pszPath[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+708h] [rbp+608h]

  v4 = 0;
  v5 = 0;
  BackgroundBackupRestoreHandler::ComputeBackgroundFit();
  memset_0(pvData, 0, 0x208u);
  pcbData[0] = 520;
  ValueW = RegGetValueW(HKEY_CURRENT_USER, L"Control Panel\\Desktop", L"Wallpaper", 2u, 0, pvData, pcbData);
  v7 = (unsigned int)ValueW;
  if ( ValueW )
  {
    pvData[0] = 0;
    if ( ValueW > 0 )
      v7 = (unsigned __int16)ValueW | 0x80070000;
  }
  v8 = retaddr;
  if ( (v7 & 0x80000000) != 0LL )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
      (const char *)v7,
      pdwType);
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    McTemplateU0z_EventWriteTransfer(retaddr, &BackupAssociatedLocalFile, pvData);
  CloudRestoreLauncherTelemetry::BackgroundActivity::Background_LocalPathActivity<unsigned short const (&)[12],unsigned short (&)[260]>(
    v8,
    pvData);
  if ( OneDriveUtils::IsSystemImage((OneDriveUtils *)pvData, v9) )
  {
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(v10, &InformationMessage, L"Background Backup", L"It is a System Image");
    CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[14],unsigned short const (&)[8]>();
LABEL_11:
    *(_QWORD *)(a2 + 64) = 0;
    *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 48) = 0;
    *(_QWORD *)(a2 + 32) = 0;
    result = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 16);
    *result = 0;
    return result;
  }
  std::filesystem::path::path(v66, pvData);
  v13 = std::filesystem::exists((std::filesystem *)v66, v12);
  std::wstring::_Tidy_deallocate(v66);
  if ( !v13 )
  {
    *(_QWORD *)&v67[0] = L"Doesn't Exist on system";
    *(_QWORD *)pcbData = L"User Preferred Image";
    v66[0] = L"Backup API";
    CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const *,unsigned short const *,unsigned short const *>(
      v66,
      pcbData,
      v67);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        v14,
        &InformationMessage,
        L"User Preferred Image",
        L"Chosen Image doesn't exist on system");
    goto LABEL_11;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::GetImpl'::`2'::impl) )
  {
    IsMicrosoftAccount = OneDriveUtils::IsMicrosoftAccount(v15);
    v19 = IsMicrosoftAccount != 0;
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      v20 = L"true";
      if ( !IsMicrosoftAccount )
        v20 = L"false";
      McTemplateU0zz_EventWriteTransfer(v17, &InformationMessage, L"Background Backup, IsMicrosoftAccount", v20);
    }
    if ( !IsMicrosoftAccount )
      goto LABEL_24;
    matched = OneDriveUtils::ValidateOneDriveAccountMatchAsync(v66);
    v5 = 1;
    pcbData[0] = 1;
    v22 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<bool>>::Status(matched);
    if ( !v22 )
      v22 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<bool>>(matched);
    winrt::impl::check_status_canceled((winrt::impl *)v22, v23);
    Results = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::GetResults(matched);
    v25 = 1;
    if ( Results )
LABEL_24:
      v25 = 0;
    if ( (v5 & 1) != 0 )
    {
      v5 &= ~1u;
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v66);
    }
    if ( v25 )
    {
LABEL_28:
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(
          v17,
          &InformationMessage,
          L"Background Backup",
          L"Primary OneDrive account userID does not match with the logged in account's userID");
      CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[50],unsigned short const (&)[8]>();
      goto LABEL_11;
    }
  }
  else
  {
    v19 = 0;
    v26 = OneDriveUtils::ValidateOneDriveAccountMatchAsync(v66);
    v27 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<bool>>::Status(v26);
    if ( !v27 )
      v27 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<bool>>(v26);
    winrt::impl::check_status_canceled((winrt::impl *)v27, v28);
    v29 = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::GetResults(v26);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v66);
    if ( !v29 )
      goto LABEL_28;
  }
  ppv = 0;
  if ( OneDriveUtils::IsPathInOneDrive((OneDriveUtils *)pvData, v16) )
  {
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(v30, &InformationMessage, L"Background Backup", L"It is a Cloud Image");
    CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[15],unsigned short const (&)[8]>();
    ppv = 0;
    v61 = SHCreateItemFromParsingName(pvData, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
    v55 = retaddr;
    if ( v61 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x140,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
        (const char *)(unsigned int)v61,
        pdwType);
    goto LABEL_88;
  }
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    McTemplateU0zz_EventWriteTransfer(v30, &InformationMessage, L"Background Backup", L"It is not a Cloud Image");
  CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[18],unsigned short const (&)[8]>();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::GetImpl'::`2'::impl) )
  {
    if ( v19 )
    {
      *(GUID *)v66 = FOLDERID_Pictures;
      IsKnownFolderKFM = OneDriveUtils::IsKnownFolderKFM((OneDriveUtils *)v66, v31);
    }
    else
    {
      v67[0] = FOLDERID_Pictures;
      IsKnownFolderKFMForAccount = OneDriveUtils::IsKnownFolderKFMForAccount((winrt::Windows::Foundation::IUnknown *)v66);
      v35 = winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<bool>>::Status(IsKnownFolderKFMForAccount);
      if ( !v35 )
        v35 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<bool>>(IsKnownFolderKFMForAccount);
      winrt::impl::check_status_canceled((winrt::impl *)v35, v36);
      IsKnownFolderKFM = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::GetResults(IsKnownFolderKFMForAccount);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v66);
    }
    if ( !IsKnownFolderKFM )
    {
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(
          v32,
          &InformationMessage,
          L"Background Backup",
          L"Picture Folder does not support KFM");
      CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[36],unsigned short const (&)[8]>();
      *(_QWORD *)(a2 + 64) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 48) = 0;
      *(_QWORD *)(a2 + 32) = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 16) = 0;
      memset_0(v69, 0, 0x208u);
      pcbData[0] = 520;
      v37 = RegGetValueW(HKEY_CURRENT_USER, L"Software\\Microsoft\\OneDrive", L"version", 2u, 0, v69, pcbData);
      v40 = v37 < 0;
      if ( v37 )
      {
        v69[0] = 0;
        if ( v37 > 0 )
          v40 = 1;
      }
      if ( !v40 )
        goto LABEL_54;
      pcbData[0] = 520;
      v41 = RegGetValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\OneDrive", L"version", 2u, 0, v69, pcbData);
      v42 = v41 < 0;
      if ( v41 )
      {
        v69[0] = 0;
        if ( v41 > 0 )
          v42 = 1;
      }
      if ( !v42 )
      {
LABEL_54:
        if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
          McTemplateU0zz_EventWriteTransfer(v39, &InformationMessage, L"Background Backup", v69);
        CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[17],unsigned short (&)[260]>(
          v39,
          v38,
          v69);
      }
      return (_WORD *)wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&ppv);
    }
    v4 = 0;
    if ( !v19 )
      goto LABEL_69;
  }
  else
  {
    *(GUID *)v66 = FOLDERID_Pictures;
    if ( !OneDriveUtils::IsKnownFolderKFM((OneDriveUtils *)v66, v31) )
    {
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(
          v45,
          &InformationMessage,
          L"Background Backup",
          L"Picture Folder does not support KFM");
      CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[36],unsigned short const (&)[8]>();
      goto LABEL_104;
    }
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WASCConsentForOneDrive>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_WASCConsentForOneDrive>::GetImpl'::`2'::impl) )
  {
LABEL_69:
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>>::operator->(
                            a1 + 8,
                            v66)
             + 276LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>>(v66);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(v46, &InformationMessage, L"Background Backup", L"Picture Folder supports KFM");
    memset_0(pszPath, 0, 0x208u);
    CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[19],unsigned short const (&)[8]>(
      v47,
      L"Picture Folder KFM");
    pcbData[0] = 520;
    v48 = RegGetValueW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
            L"BackedUpWallpaperPath",
            2u,
            0,
            pszPath,
            pcbData);
    v50 = v48 < 0;
    if ( v48 )
    {
      pszPath[0] = 0;
      if ( v48 > 0 )
        v50 = 1;
    }
    if ( !v50 )
    {
      std::filesystem::path::path(v66, pszPath);
      v5 |= 2u;
      pcbData[0] = v5;
      if ( std::filesystem::exists((std::filesystem *)v66, v51) )
      {
        if ( OneDriveUtils::IsFileIdentical(pvData, pszPath, v52) )
          v4 = 1;
      }
    }
    if ( (v5 & 2) != 0 )
      std::wstring::_Tidy_deallocate(v66);
    if ( v4 )
    {
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(
          v49,
          &InformationMessage,
          L"Background Backup",
          L"current background wallpaper is same as the last backed up wallpaper");
      CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[69],unsigned short const (&)[8]>();
      v53 = ppv;
      ppv = 0;
      if ( v53 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v53 + 16LL))(v53);
      v54 = SHCreateItemFromParsingName(pszPath, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
      v55 = retaddr;
      if ( v54 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x134,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
          (const char *)(unsigned int)v54,
          pdwTypea);
    }
    else
    {
      v56 = std::wstring::wstring(v67, L"Background");
      v57 = OneDriveUtils::CopyToPictures(v66, pvData, v56);
      wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>::operator=(&ppv, v57);
      wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(v66);
    }
LABEL_88:
    if ( ppv )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>>::operator->(
                              a1 + 8,
                              v66)
               + 275LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundBackupTipTests,_tip_BackgroundBackupTipTests>>(v66);
      OneDriveUtils::GetStorageProviderContentUri(v67, ppv);
      v58 = -1;
      if ( *(_QWORD *)&v67[0] )
      {
        v59 = -1;
        do
          ++v59;
        while ( *(_WORD *)(*(_QWORD *)&v67[0] + 2 * v59) );
        std::wstring::_Assign<unsigned short>(a2 + 48, *(_QWORD *)&v67[0], v59);
      }
      OneDriveUtils::GetStorageProviderFileId(pcbData, ppv);
      if ( *(_QWORD *)pcbData )
      {
        do
          ++v58;
        while ( *(_WORD *)(*(_QWORD *)pcbData + 2 * v58) );
        std::wstring::_Assign<unsigned short>(a2 + 16, *(_QWORD *)pcbData, v58);
      }
      CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[19],unsigned short const (&)[8]>(
        v60,
        L"Shell Item Fetched");
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(pcbData);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v67);
      return (_WORD *)wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&ppv);
    }
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(v55, &InformationMessage, L"Background Backup", L"ShellItem not fetched");
    CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[23],unsigned short const (&)[8]>(v55);
    goto LABEL_104;
  }
  if ( OneDriveUtils::IsUserConsentForDataSharing(v43) )
  {
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        v44,
        &InformationMessage,
        L"Background Backup",
        L"going ahead with normal process after checking WASC");
    goto LABEL_69;
  }
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    McTemplateU0zz_EventWriteTransfer(
      v44,
      &InformationMessage,
      L"Background Backup",
      L"User has not given consent for data sharing");
  CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<unsigned short const (&)[11],unsigned short const (&)[44],unsigned short const (&)[11]>();
LABEL_104:
  *(_QWORD *)(a2 + 64) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 48) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 16) = 0;
  return (_WORD *)wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&ppv);
}

```

## disassembly

```asm
0x1800a96f0  mov     [rsp-8+arg_10], rbx
0x1800a96f5  push    rbp
0x1800a96f6  push    rsi
0x1800a96f7  push    rdi
0x1800a96f8  push    r12
0x1800a96fa  push    r13
0x1800a96fc  push    r14
0x1800a96fe  push    r15
0x1800a9700  lea     rbp, [rsp-5D0h]
0x1800a9708  sub     rsp, 6D0h
0x1800a970f  mov     rax, cs:__security_cookie
0x1800a9716  xor     rax, rsp
0x1800a9719  mov     [rbp+600h+var_40], rax
0x1800a9720  mov     rsi, rdx
0x1800a9723  mov     r13, rcx
0x1800a9726  xor     r15d, r15d
0x1800a9729  mov     r14d, r15d
0x1800a972c  mov     [rsp+700h+var_6B8], r15d
0x1800a9731  call    ?ComputeBackgroundFit@BackgroundBackupRestoreHandler@@AEAAXAEAV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@@Z; BackgroundBackupRestoreHandler::ComputeBackgroundFit(wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper> &)
0x1800a9736  mov     ebx, 208h
0x1800a973b  mov     r8d, ebx; Size
0x1800a973e  xor     edx, edx; Val
0x1800a9740  lea     rcx, [rbp+600h+var_670]; void *
0x1800a9744  call    memset_0
0x1800a9749  mov     [rsp+700h+var_6B8], ebx
0x1800a974d  lea     rax, [rsp+700h+var_6B8]
0x1800a9752  mov     [rsp+700h+pcbData], rax; pcbData
0x1800a9757  lea     rax, [rbp+600h+var_670]
0x1800a975b  mov     [rsp+700h+pvData], rax; pvData
0x1800a9760  mov     [rsp+700h+pdwType], r15; int
0x1800a9765  lea     r9d, [r15+2]; dwFlags
0x1800a9769  lea     r8, aWallpaper; "Wallpaper"
0x1800a9770  lea     rdx, aControlPanelDe_0; "Control Panel\\Desktop"
0x1800a9777  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800a977e  call    cs:__imp_RegGetValueW
0x1800a9784  mov     r9d, eax
0x1800a9787  test    eax, eax
0x1800a9789  jz      short loc_1800A979D
0x1800a978b  mov     [rbp+600h+var_670], r15w
0x1800a9790  jle     short loc_1800A979D
0x1800a9792  movzx   r9d, ax
0x1800a9796  or      r9d, 80070000h; char *
0x1800a979d  mov     rcx, [rbp+608h]; this
0x1800a97a4  test    r9d, r9d
0x1800a97a7  js      loc_1800A9FCD
0x1800a97ad  mov     dil, 4
0x1800a97b0  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, dil
0x1800a97b7  jz      short loc_1800A97C9
0x1800a97b9  lea     r8, [rbp+600h+var_670]
0x1800a97bd  lea     rdx, BackupAssociatedLocalFile
0x1800a97c4  call    McTemplateU0z_EventWriteTransfer
0x1800a97c9  lea     rdx, [rbp+600h+var_670]
0x1800a97cd  call    ??$Background_LocalPathActivity@AEAY0M@$$CBGAEAY0BAE@G@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0M@$$CBGAEAY0BAE@G@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_LocalPathActivity<ushort const (&)[12],ushort (&)[260]>(ushort const (&)[12],ushort (&)[260])
0x1800a97d2  lea     rcx, [rbp+600h+var_670]; this
0x1800a97d6  call    ?IsSystemImage@OneDriveUtils@@YA_NPEBG@Z; OneDriveUtils::IsSystemImage(ushort const *)
0x1800a97db  test    al, al
0x1800a97dd  jz      short loc_1800A982E
0x1800a97df  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, dil
0x1800a97e6  jz      short loc_1800A9802
0x1800a97e8  lea     r9, aItIsASystemIma; "It is a System Image"
0x1800a97ef  lea     r8, aBackgroundBack_0; "Background Backup"
0x1800a97f6  lea     rdx, InformationMessage
0x1800a97fd  call    McTemplateU0zz_EventWriteTransfer
0x1800a9802  call    ??$Background_ApiActivity@AEAY0L@$$CBGAEAY0O@$$CBGAEAY07$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0O@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<ushort const (&)[11],ushort const (&)[14],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[14],ushort const (&)[8])
0x1800a9807  lea     rcx, [rsi+30h]
0x1800a980b  mov     [rcx+10h], r15
0x1800a980f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a9814  mov     [rax], r15w
0x1800a9818  lea     rcx, [rsi+10h]
0x1800a981c  mov     [rcx+10h], r15
0x1800a9820  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a9825  mov     [rax], r15w
0x1800a9829  jmp     loc_1800A9FA3
0x1800a982e  lea     rdx, [rbp+600h+var_670]
0x1800a9832  lea     rcx, [rsp+700h+var_6B0]
0x1800a9837  call    ??$?0$$BY0BAE@G$0A@@path@filesystem@std@@QEAA@AEAY0BAE@$$CBGW4format@012@@Z; std::filesystem::path::path(ushort const (&)[260],std::filesystem::path::format)
0x1800a983c  nop
0x1800a983d  lea     rcx, [rsp+700h+var_6B0]; this
0x1800a9842  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x1800a9847  mov     bl, al
0x1800a9849  lea     rcx, [rsp+700h+var_6B0]
0x1800a984e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a9853  test    bl, bl
0x1800a9855  jnz     short loc_1800A98B7
0x1800a9857  lea     rax, aDoesnTExistOnS; "Doesn't Exist on system"
0x1800a985e  mov     qword ptr [rsp+700h+var_690], rax
0x1800a9863  lea     rbx, aUserPreferredI; "User Preferred Image"
0x1800a986a  mov     qword ptr [rsp+700h+var_6B8], rbx
0x1800a986f  lea     rax, aBackupApi; "Backup API"
0x1800a9876  mov     [rsp+700h+var_6B0], rax
0x1800a987b  lea     r8, [rsp+700h+var_690]
0x1800a9880  lea     rdx, [rsp+700h+var_6B8]
0x1800a9885  lea     rcx, [rsp+700h+var_6B0]
0x1800a988a  call    ??$Background_ApiActivity@PEBGPEBGPEBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAX$$QEAPEBG00@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<ushort const *,ushort const *,ushort const *>(ushort const * &&,ushort const * &&,ushort const * &&)
0x1800a988f  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, dil
0x1800a9896  jz      loc_1800A9807
0x1800a989c  lea     r9, aChosenImageDoe; "Chosen Image doesn't exist on system"
0x1800a98a3  mov     r8, rbx
0x1800a98a6  lea     rdx, InformationMessage
0x1800a98ad  call    McTemplateU0zz_EventWriteTransfer
0x1800a98b2  jmp     loc_1800A9807
0x1800a98b7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialWallpaperBackup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialWallpaperBackup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialWallpaperBackup> `wil::Feature<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::GetImpl(void)'::`2'::impl
0x1800a98be  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialWallpaperBackup@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::__private_IsEnabled(void)
0x1800a98c3  lea     rdi, InformationMessage
0x1800a98ca  test    al, al
0x1800a98cc  jz      loc_1800A9995
0x1800a98d2  call    ?IsMicrosoftAccount@OneDriveUtils@@YAEXZ; OneDriveUtils::IsMicrosoftAccount(void)
0x1800a98d7  mov     bl, al
0x1800a98d9  test    al, al
0x1800a98db  setnz   r12b
0x1800a98df  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800a98e6  jz      short loc_1800A990B
0x1800a98e8  lea     rax, aFalse_0; "false"
0x1800a98ef  lea     r9, aTrue; "true"
0x1800a98f6  test    bl, bl
0x1800a98f8  cmovz   r9, rax
0x1800a98fc  lea     r8, aBackgroundBack; "Background Backup, IsMicrosoftAccount"
0x1800a9903  mov     rdx, rdi
0x1800a9906  call    McTemplateU0zz_EventWriteTransfer
0x1800a990b  test    bl, bl
0x1800a990d  jz      short loc_1800A9951
0x1800a990f  lea     rcx, [rsp+700h+var_6B0]
0x1800a9914  call    ?ValidateOneDriveAccountMatchAsync@OneDriveUtils@@YA?AU?$IAsyncOperation@_N@Foundation@Windows@winrt@@XZ; OneDriveUtils::ValidateOneDriveAccountMatchAsync(void)
0x1800a9919  mov     rbx, rax
0x1800a991c  mov     r14d, 1
0x1800a9922  mov     [rsp+700h+var_6B8], r14d
0x1800a9927  mov     rcx, rax
0x1800a992a  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<bool>>::Status(void)
0x1800a992f  test    eax, eax
0x1800a9931  jnz     short loc_1800A993B
0x1800a9933  mov     rcx, rbx
0x1800a9936  call    ??$wait_for_completed@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@_N@Foundation@Windows@1@I@Z
0x1800a993b  mov     ecx, eax; this
0x1800a993d  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x1800a9942  mov     rcx, rbx
0x1800a9945  call    ?GetResults@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@_N@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::GetResults(void)
0x1800a994a  test    al, al
0x1800a994c  mov     bl, r14b
0x1800a994f  jz      short loc_1800A9954
0x1800a9951  mov     bl, r15b
0x1800a9954  test    r14b, 1
0x1800a9958  jz      short loc_1800A9968
0x1800a995a  and     r14d, 0FFFFFFFEh
0x1800a995e  lea     rcx, [rsp+700h+var_6B0]; this
0x1800a9963  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800a9968  test    bl, bl
0x1800a996a  jz      short loc_1800A99D8
0x1800a996c  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800a9973  jz      short loc_1800A998B
0x1800a9975  lea     r9, aPrimaryOnedriv; "Primary OneDrive account userID does no"...
0x1800a997c  lea     r8, aBackgroundBack_0; "Background Backup"
0x1800a9983  mov     rdx, rdi
0x1800a9986  call    McTemplateU0zz_EventWriteTransfer
0x1800a998b  call    ??$Background_ApiActivity@AEAY0L@$$CBGAEAY0DC@$$CBGAEAY07$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0DC@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<ushort const (&)[11],ushort const (&)[50],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[50],ushort const (&)[8])
0x1800a9990  jmp     loc_1800A9807
0x1800a9995  mov     r12b, r15b
0x1800a9998  lea     rcx, [rsp+700h+var_6B0]
0x1800a999d  call    ?ValidateOneDriveAccountMatchAsync@OneDriveUtils@@YA?AU?$IAsyncOperation@_N@Foundation@Windows@winrt@@XZ; OneDriveUtils::ValidateOneDriveAccountMatchAsync(void)
0x1800a99a2  mov     rbx, rax
0x1800a99a5  mov     rcx, rax
0x1800a99a8  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<bool>>::Status(void)
0x1800a99ad  test    eax, eax
0x1800a99af  jnz     short loc_1800A99B9
0x1800a99b1  mov     rcx, rbx
0x1800a99b4  call    ??$wait_for_completed@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@_N@Foundation@Windows@1@I@Z
0x1800a99b9  mov     ecx, eax; this
0x1800a99bb  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x1800a99c0  mov     rcx, rbx
0x1800a99c3  call    ?GetResults@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@_N@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::GetResults(void)
0x1800a99c8  mov     bl, al
0x1800a99ca  lea     rcx, [rsp+700h+var_6B0]; this
0x1800a99cf  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800a99d4  test    bl, bl
0x1800a99d6  jz      short loc_1800A996C
0x1800a99d8  mov     [rsp+700h+ppv], r15
0x1800a99dd  lea     rcx, [rbp+600h+var_670]; this
0x1800a99e1  call    ?IsPathInOneDrive@OneDriveUtils@@YA_NPEBG@Z; OneDriveUtils::IsPathInOneDrive(ushort const *)
0x1800a99e6  lea     rbx, aBackgroundBack_0; "Background Backup"
0x1800a99ed  test    al, al
0x1800a99ef  jnz     loc_1800A9EEE
0x1800a99f5  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800a99fc  jz      short loc_1800A9A10
0x1800a99fe  lea     r9, aItIsNotACloudI; "It is not a Cloud Image"
0x1800a9a05  mov     r8, rbx
0x1800a9a08  mov     rdx, rdi
0x1800a9a0b  call    McTemplateU0zz_EventWriteTransfer
0x1800a9a10  call    ??$Background_ApiActivity@AEAY0L@$$CBGAEAY0BC@$$CBGAEAY07$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0BC@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<ushort const (&)[11],ushort const (&)[18],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[18],ushort const (&)[8])
0x1800a9a15  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialWallpaperBackup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialWallpaperBackup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialWallpaperBackup> `wil::Feature<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::GetImpl(void)'::`2'::impl
0x1800a9a1c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialWallpaperBackup@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialWallpaperBackup>::__private_IsEnabled(void)
0x1800a9a21  movups  xmm0, xmmword ptr cs:FOLDERID_Pictures.Data1
0x1800a9a28  test    al, al
0x1800a9a2a  jz      loc_1800A9C29
0x1800a9a30  test    r12b, r12b
0x1800a9a33  jz      short loc_1800A9A4A
0x1800a9a35  movdqu  xmmword ptr [rsp+700h+var_6B0], xmm0
0x1800a9a3b  lea     rcx, [rsp+700h+var_6B0]; this
0x1800a9a40  call    ?IsKnownFolderKFM@OneDriveUtils@@YA_NAEBUguid@winrt@@@Z; OneDriveUtils::IsKnownFolderKFM(winrt::guid const &)
0x1800a9a45  mov     r15b, al
0x1800a9a48  jmp     short loc_1800A9A92
0x1800a9a4a  movdqu  [rsp+700h+var_690], xmm0
0x1800a9a50  lea     rdx, [rsp+700h+var_690]
0x1800a9a55  lea     rcx, [rsp+700h+var_6B0]; this
0x1800a9a5a  call    ?IsKnownFolderKFMForAccount@OneDriveUtils@@YA?AU?$IAsyncOperation@_N@Foundation@Windows@winrt@@AEBUguid@5@@Z; OneDriveUtils::IsKnownFolderKFMForAccount(winrt::guid const &)
0x1800a9a5f  mov     r15, rax
0x1800a9a62  mov     rcx, rax
0x1800a9a65  call    ?Status@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<bool>>::Status(void)
0x1800a9a6a  test    eax, eax
0x1800a9a6c  jnz     short loc_1800A9A76
0x1800a9a6e  mov     rcx, r15
0x1800a9a71  call    ??$wait_for_completed@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@_N@Foundation@Windows@1@I@Z
0x1800a9a76  mov     ecx, eax; this
0x1800a9a78  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x1800a9a7d  mov     rcx, r15
0x1800a9a80  call    ?GetResults@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@_N@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<bool>,bool>::GetResults(void)
0x1800a9a85  mov     r15b, al
0x1800a9a88  lea     rcx, [rsp+700h+var_6B0]; this
0x1800a9a8d  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1800a9a92  test    r15b, r15b
0x1800a9a95  jnz     loc_1800A9BDB
0x1800a9a9b  mov     r15b, 4
0x1800a9a9e  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, r15b
0x1800a9aa5  jz      short loc_1800A9AB9
0x1800a9aa7  lea     r9, aPictureFolderD; "Picture Folder does not support KFM"
0x1800a9aae  mov     r8, rbx
0x1800a9ab1  mov     rdx, rdi
0x1800a9ab4  call    McTemplateU0zz_EventWriteTransfer
0x1800a9ab9  call    ??$Background_ApiActivity@AEAY0L@$$CBGAEAY0CE@$$CBGAEAY07$$CBG@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0CE@$$CBGAEAY07$$CBG@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<ushort const (&)[11],ushort const (&)[36],ushort const (&)[8]>(ushort const (&)[11],ushort const (&)[36],ushort const (&)[8])
0x1800a9abe  lea     rcx, [rsi+30h]
0x1800a9ac2  xor     r14d, r14d
0x1800a9ac5  mov     [rcx+10h], r14
0x1800a9ac9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a9ace  mov     [rax], r14w
0x1800a9ad2  lea     rcx, [rsi+10h]
0x1800a9ad6  mov     [rcx+10h], r14
0x1800a9ada  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a9adf  mov     [rax], r14w
0x1800a9ae3  mov     esi, 208h
0x1800a9ae8  mov     r8d, esi; Size
0x1800a9aeb  xor     edx, edx; Val
0x1800a9aed  lea     rcx, [rbp+600h+var_460]; void *
0x1800a9af4  call    memset_0
0x1800a9af9  mov     [rsp+700h+var_6B8], esi
0x1800a9afd  lea     rax, [rsp+700h+var_6B8]
0x1800a9b02  mov     [rsp+700h+pcbData], rax; pcbData
0x1800a9b07  lea     rax, [rbp+600h+var_460]
0x1800a9b0e  mov     [rsp+700h+pvData], rax; pvData
0x1800a9b13  mov     [rsp+700h+pdwType], r14; pdwType
0x1800a9b18  lea     r12d, [r14+2]
0x1800a9b1c  mov     r9d, r12d; dwFlags
0x1800a9b1f  lea     r8, aVersion; "version"
0x1800a9b26  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\OneDrive"
0x1800a9b2d  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800a9b34  call    cs:__imp_RegGetValueW
0x1800a9b3a  test    eax, eax
0x1800a9b3c  jz      short loc_1800A9B52
0x1800a9b3e  mov     [rbp+600h+var_460], r14w
0x1800a9b46  jle     short loc_1800A9B52
0x1800a9b48  movzx   eax, ax
0x1800a9b4b  or      eax, 80070000h
0x1800a9b50  test    eax, eax
0x1800a9b52  jns     short loc_1800A9BAF
0x1800a9b54  mov     [rsp+700h+var_6B8], esi
0x1800a9b58  lea     rax, [rsp+700h+var_6B8]
0x1800a9b5d  mov     [rsp+700h+pcbData], rax; pcbData
0x1800a9b62  lea     rax, [rbp+600h+var_460]
0x1800a9b69  mov     [rsp+700h+pvData], rax; pvData
0x1800a9b6e  mov     [rsp+700h+pdwType], r14; pdwType
0x1800a9b73  mov     r9d, r12d; dwFlags
0x1800a9b76  lea     r8, aVersion; "version"
0x1800a9b7d  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\OneDrive"
0x1800a9b84  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800a9b8b  call    cs:__imp_RegGetValueW
0x1800a9b91  test    eax, eax
0x1800a9b93  jz      short loc_1800A9BA9
0x1800a9b95  mov     [rbp+600h+var_460], r14w
0x1800a9b9d  jle     short loc_1800A9BA9
0x1800a9b9f  movzx   eax, ax
0x1800a9ba2  or      eax, 80070000h
0x1800a9ba7  test    eax, eax
0x1800a9ba9  js      loc_1800A9F99
0x1800a9baf  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, r15b
0x1800a9bb6  jz      short loc_1800A9BCA
0x1800a9bb8  lea     r9, [rbp+600h+var_460]
0x1800a9bbf  mov     r8, rbx
0x1800a9bc2  mov     rdx, rdi
0x1800a9bc5  call    McTemplateU0zz_EventWriteTransfer
0x1800a9bca  lea     r8, [rbp+600h+var_460]
0x1800a9bd1  call    ??$Background_ApiActivity@AEAY0L@$$CBGAEAY0BB@$$CBGAEAY0BAE@G@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0L@$$CBGAEAY0BB@$$CBGAEAY0BAE@G@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_ApiActivity<ushort const (&)[11],ushort const (&)[17],ushort (&)[260]>(ushort const (&)[11],ushort const (&)[17],ushort (&)[260])
0x1800a9bd6  jmp     loc_1800A9F99
0x1800a9bdb  xor     r15d, r15d
0x1800a9bde  test    r12b, r12b
0x1800a9be1  jz      loc_1800A9C7D
0x1800a9be7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WASCConsentForOneDrive@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WASCConsentForOneDrive@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WASCConsentForOneDrive> `wil::Feature<__WilFeatureTraits_Feature_WASCConsentForOneDrive>::GetImpl(void)'::`2'::impl
0x1800a9bee  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WASCConsentForOneDrive@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WASCConsentForOneDrive>::__private_IsEnabled(void)
0x1800a9bf3  test    al, al
0x1800a9bf5  jz      loc_1800A9C7D
0x1800a9bfb  call    ?IsUserConsentForDataSharing@OneDriveUtils@@YAEXZ; OneDriveUtils::IsUserConsentForDataSharing(void)
0x1800a9c00  test    al, al
0x1800a9c02  jnz     short loc_1800A9C62
0x1800a9c04  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
  ... truncated ...
```
