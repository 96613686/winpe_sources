# BackgroundBackupRestoreHandler::FillSlideShowData(wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper> &)

- ea: `0x1800ab0ec`
- end: `0x1800ab670`
- name: `?FillSlideShowData@BackgroundBackupRestoreHandler@@AEAA_NAEAV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@@Z`
- size: `1412`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ae540`

## callees

- `0x18000c6e0`
- `0x180015668`
- `0x18001649c`
- `0x18001666c`
- `0x18001ac54`
- `0x18001cf84`
- `0x18001cfa4`
- `0x18001d0a8`
- `0x18001faa8`
- `0x180031774`
- `0x1800977e8`
- `0x18009cbec`
- `0x1800a4288`
- `0x1800a56b8`
- `0x1800a93a8`
- `0x1800ab0ec`
- `0x1800ab764`
- `0x1800ad43c`
- `0x1800ad564`
- `0x1800adf58`
- `0x18012d010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x1800ab13d`
- `OLE32!CoCreateInstance` at `0x1800ab13d`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800ab31a`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800ab31a`

## string_xrefs

- `0x1800ab3d6`: `BackedUpWallpaperPath`
- `0x1800ab2e7`: `ImageFilePath`
- `0x1800ab23f`: `Background Slideshow folder Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
char __fastcall BackgroundBackupRestoreHandler::FillSlideShowData(__int64 a1, __int64 a2)
{
  HRESULT v3; // eax
  __int64 v4; // rax
  int v5; // eax
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  int v9; // eax
  const unsigned __int16 *v10; // rdx
  bool IsPathInOneDrive; // si
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rsi
  __int64 v15; // rax
  __int64 v16; // rcx
  const WCHAR *v17; // rax
  HRESULT v18; // eax
  __int64 v19; // r8
  __int64 v20; // r8
  const unsigned __int16 *v21; // rax
  HKEY v22; // rcx
  int v23; // eax
  __int64 *v24; // rsi
  bool v25; // sf
  __int64 v26; // rax
  int v27; // ecx
  char v28; // al
  int v29; // r9d
  __int64 v30; // rcx
  __int64 v31; // rcx
  int ppv; // [rsp+20h] [rbp-F8h]
  __int64 *v34; // [rsp+30h] [rbp-E8h] BYREF
  int v35; // [rsp+38h] [rbp-E0h] BYREF
  unsigned int v36; // [rsp+3Ch] [rbp-DCh] BYREF
  unsigned int v37; // [rsp+40h] [rbp-D8h] BYREF
  OneDriveUtils *v38; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-C8h] BYREF
  LPVOID v40; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+60h] [rbp-B8h] BYREF
  void *v42; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+70h] [rbp-A8h] BYREF
  _BYTE v44[32]; // [rsp+78h] [rbp-A0h] BYREF
  _BYTE v45[32]; // [rsp+98h] [rbp-80h] BYREF
  _BYTE v46[32]; // [rsp+B8h] [rbp-60h] BYREF
  _BYTE v47[32]; // [rsp+D8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v40 = 0;
  v3 = CoCreateInstance(&CLSID_DesktopWallpaper, 0, 4u, &GUID_b92b56a9_8b55_4e14_9a89_0199bbb6f93b, &v40);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15F,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  v34 = 0;
  v4 = *(_QWORD *)v40;
  v34 = 0;
  v5 = (*(__int64 (__fastcall **)(LPVOID, __int64 **))(v4 + 104))(v40, &v34);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x163,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  v35 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v34 + 56))(v34, &v35);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
      (const char *)(unsigned int)v6,
      ppv);
  if ( !v35 )
  {
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        retaddr,
        &InformationMessage,
        L"Background Slideshow Backup",
        L"No slideshow shell item present");
    goto LABEL_42;
  }
  v39 = 0;
  v7 = *v34;
  v39 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v7 + 64))(v34, 0, &v39);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x16C,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
      (const char *)(unsigned int)v8,
      ppv);
  v38 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, OneDriveUtils **))(*(_QWORD *)v39 + 40LL))(v39, 2147647488LL, &v38);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
      (const char *)(unsigned int)v9,
      ppv);
  IsPathInOneDrive = OneDriveUtils::IsPathInOneDrive(v38, v10);
  v12 = (unsigned int)Microsoft_Windows_CloudRestoreLauncherEnableBits;
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    McTemplateU0zz_EventWriteTransfer(
      (unsigned int)Microsoft_Windows_CloudRestoreLauncherEnableBits,
      &InformationMessage,
      L"Background Slideshow folder Path",
      v38);
    v12 = (unsigned int)Microsoft_Windows_CloudRestoreLauncherEnableBits;
  }
  if ( !IsPathInOneDrive )
  {
    if ( (v12 & 4) != 0 )
    {
      McTemplateU0zz_EventWriteTransfer(
        v12,
        &InformationMessage,
        L"Background Slideshow Backup",
        L"Slideshow Folder is Not OneDrive folder");
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0xxx_EventWriteTransfer(
          Microsoft_Windows_CloudRestoreLauncherEnableBits,
          (unsigned int)&BackupAssociatedBackgroundSlideshowSettingsData,
          0,
          *(unsigned __int8 *)(a2 + 88),
          *(_QWORD *)(a2 + 80));
    }
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&v39);
LABEL_42:
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&v34);
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&v40);
    return 0;
  }
  if ( (v12 & 4) != 0 )
    McTemplateU0zz_EventWriteTransfer(
      v12,
      &InformationMessage,
      L"Background Slideshow Backup",
      L"Slideshow Folder is OneDrive folder");
  std::wstring::wstring(v47, v38);
  std::wstring::wstring(v45, &word_1801382A0);
  v13 = std::wstring::wstring(v44, v47);
  v14 = -1;
  if ( (unsigned __int8)OneDriveUtils::FindSlideshowImageFile(v13, v45) )
  {
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    {
      v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
      McTemplateU0zz_EventWriteTransfer(v16, &InformationMessage, L"ImageFilePath", v15);
    }
    v42 = 0;
    v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
    v18 = SHCreateItemFromParsingName(v17, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &v42);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x181,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
        (const char *)(unsigned int)v18,
        ppv);
    OneDriveUtils::GetStorageProviderContentUri(&v41, v42);
    if ( v41 )
    {
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)(v41 + 2 * v19) );
      std::wstring::_Assign<unsigned short>(a2 + 48, v41, v19);
    }
    OneDriveUtils::GetStorageProviderFileId(&v43, v42);
    if ( v43 )
    {
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)(v43 + 2 * v20) );
      std::wstring::_Assign<unsigned short>(a2 + 16, v43, v20);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v43);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v41);
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&v42);
  }
  std::wstring::wstring(v46, &word_1801382A0);
  v21 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
  v23 = SHRegSetString(
          v22,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Wallpapers",
          L"BackedUpWallpaperPath",
          v21);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x190,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundbackuprestorehandler.cpp",
      (const char *)(unsigned int)v23,
      ppv);
  do
    ++v14;
  while ( *((_WORD *)v38 + v14) );
  std::wstring::_Assign<unsigned short>(a2 + 96, v38, v14);
  v36 = 0;
  v24 = (__int64 *)(a2 + 80);
  v25 = (int)SHRegGetDWORD(HKEY_CURRENT_USER, L"Control Panel\\Personalization\\Desktop Slideshow", L"Interval", &v36) < 0;
  v26 = v36;
  if ( v25 )
    v26 = 1800000;
  *v24 = v26;
  v37 = 0;
  if ( (int)SHRegGetDWORD(HKEY_CURRENT_USER, L"Control Panel\\Personalization\\Desktop Slideshow", L"Shuffle", &v37) >= 0
    && v37 )
  {
    v28 = 1;
    v29 = 1;
  }
  else
  {
    v28 = 0;
    v29 = 0;
  }
  *(_BYTE *)(a2 + 88) = v28;
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
    McTemplateU0xxx_EventWriteTransfer(
      v27,
      (unsigned int)&BackupAssociatedBackgroundSlideshowSettingsData,
      1,
      v29,
      *v24);
  v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 96);
  CloudRestoreLauncherTelemetry::BackgroundActivity::Background_SlideshowActivity<unsigned short const (&)[24],unsigned short const *,bool &,unsigned __int64 &>(
    v30,
    &v41,
    a2 + 88,
    a2 + 80);
  std::wstring::_Tidy_deallocate(v46);
  std::wstring::_Tidy_deallocate(v45);
  std::wstring::_Tidy_deallocate(v47);
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&v39);
  BackgroundBackupRestoreHandler::ComputeBackgroundFit(v31, a2);
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&v34);
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&v40);
  return 1;
}

```

## disassembly

```asm
0x1800ab0ec  mov     [rsp+arg_0], rbx
0x1800ab0f1  mov     [rsp+arg_10], rsi
0x1800ab0f6  push    rdi
0x1800ab0f7  push    r14
0x1800ab0f9  push    r15
0x1800ab0fb  sub     rsp, 100h
0x1800ab102  mov     rax, cs:__security_cookie
0x1800ab109  xor     rax, rsp
0x1800ab10c  mov     [rsp+118h+var_20], rax
0x1800ab114  mov     rdi, rdx
0x1800ab117  xor     r15d, r15d
0x1800ab11a  mov     [rsp+118h+var_C0], r15
0x1800ab11f  lea     rax, [rsp+118h+var_C0]
0x1800ab124  mov     qword ptr [rsp+118h+ppv], rax; int
0x1800ab129  lea     r9, _GUID_b92b56a9_8b55_4e14_9a89_0199bbb6f93b; riid
0x1800ab130  xor     edx, edx; pUnkOuter
0x1800ab132  lea     r8d, [r15+4]; dwClsContext
0x1800ab136  lea     rcx, CLSID_DesktopWallpaper; rclsid
0x1800ab13d  call    cs:__imp_CoCreateInstance
0x1800ab143  mov     rcx, [rsp+118h]; this
0x1800ab14b  test    eax, eax
0x1800ab14d  js      loc_1800AB5F2
0x1800ab153  mov     [rsp+118h+var_E8], r15
0x1800ab158  mov     rcx, [rsp+118h+var_C0]
0x1800ab15d  mov     rax, [rcx]
0x1800ab160  mov     [rsp+118h+var_E8], r15
0x1800ab165  lea     rdx, [rsp+118h+var_E8]
0x1800ab16a  mov     rax, [rax+68h]
0x1800ab16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab173  mov     rcx, [rsp+118h]; this
0x1800ab17b  test    eax, eax
0x1800ab17d  js      loc_1800AB607
0x1800ab183  mov     [rsp+118h+var_E0], r15d
0x1800ab188  mov     rcx, [rsp+118h+var_E8]
0x1800ab18d  mov     rax, [rcx]
0x1800ab190  lea     rdx, [rsp+118h+var_E0]
0x1800ab195  mov     rax, [rax+38h]
0x1800ab199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab19e  mov     rcx, [rsp+118h]; this
0x1800ab1a6  test    eax, eax
0x1800ab1a8  js      loc_1800AB61C
0x1800ab1ae  cmp     [rsp+118h+var_E0], r15d
0x1800ab1b3  jbe     loc_1800AB579
0x1800ab1b9  mov     [rsp+118h+var_C8], r15
0x1800ab1be  mov     rcx, [rsp+118h+var_E8]
0x1800ab1c3  mov     rax, [rcx]
0x1800ab1c6  mov     [rsp+118h+var_C8], r15
0x1800ab1cb  lea     r8, [rsp+118h+var_C8]
0x1800ab1d0  xor     edx, edx
0x1800ab1d2  mov     rax, [rax+40h]
0x1800ab1d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab1db  mov     rcx, [rsp+118h]; this
0x1800ab1e3  test    eax, eax
0x1800ab1e5  js      loc_1800AB631
0x1800ab1eb  mov     [rsp+118h+var_D0], r15
0x1800ab1f0  mov     rcx, [rsp+118h+var_C8]
0x1800ab1f5  mov     rax, [rcx]
0x1800ab1f8  lea     r8, [rsp+118h+var_D0]
0x1800ab1fd  mov     edx, 80028000h
0x1800ab202  mov     rax, [rax+28h]
0x1800ab206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab20b  mov     rcx, [rsp+118h]; this
0x1800ab213  test    eax, eax
0x1800ab215  js      loc_1800AB646
0x1800ab21b  mov     rcx, [rsp+118h+var_D0]; this
0x1800ab220  call    ?IsPathInOneDrive@OneDriveUtils@@YA_NPEBG@Z; OneDriveUtils::IsPathInOneDrive(ushort const *)
0x1800ab225  mov     sil, al
0x1800ab228  mov     ecx, cs:Microsoft_Windows_CloudRestoreLauncherEnableBits
0x1800ab22e  lea     rbx, InformationMessage
0x1800ab235  test    cl, 4
0x1800ab238  jz      short loc_1800AB254
0x1800ab23a  mov     r9, [rsp+118h+var_D0]
0x1800ab23f  lea     r8, aBackgroundSlid_2; "Background Slideshow folder Path"
0x1800ab246  mov     rdx, rbx
0x1800ab249  call    McTemplateU0zz_EventWriteTransfer
0x1800ab24e  mov     ecx, cs:Microsoft_Windows_CloudRestoreLauncherEnableBits
0x1800ab254  test    sil, sil
0x1800ab257  jz      loc_1800AB529
0x1800ab25d  test    cl, 4
0x1800ab260  jz      short loc_1800AB278
0x1800ab262  lea     r9, aSlideshowFolde_0; "Slideshow Folder is OneDrive folder"
0x1800ab269  lea     r8, aBackgroundSlid_0; "Background Slideshow Backup"
0x1800ab270  mov     rdx, rbx
0x1800ab273  call    McTemplateU0zz_EventWriteTransfer
0x1800ab278  mov     rdx, [rsp+118h+var_D0]
0x1800ab27d  lea     rcx, [rsp+118h+var_40]
0x1800ab285  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ab28a  nop
0x1800ab28b  lea     rdx, word_1801382A0
0x1800ab292  lea     rcx, [rsp+118h+var_80]
0x1800ab29a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ab29f  nop
0x1800ab2a0  lea     rdx, [rsp+118h+var_40]
0x1800ab2a8  lea     rcx, [rsp+118h+var_A0]
0x1800ab2ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800ab2b2  lea     rdx, [rsp+118h+var_80]
0x1800ab2ba  mov     rcx, rax
0x1800ab2bd  call    ?FindSlideshowImageFile@OneDriveUtils@@YA_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; OneDriveUtils::FindSlideshowImageFile(std::wstring,std::wstring &)
0x1800ab2c2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800ab2c6  test    al, al
0x1800ab2c8  jz      loc_1800AB3B1
0x1800ab2ce  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ab2d5  jz      short loc_1800AB2F7
0x1800ab2d7  lea     rcx, [rsp+118h+var_80]
0x1800ab2df  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ab2e4  mov     r9, rax
0x1800ab2e7  lea     r8, aImagefilepath; "ImageFilePath"
0x1800ab2ee  mov     rdx, rbx
0x1800ab2f1  call    McTemplateU0zz_EventWriteTransfer
0x1800ab2f6  nop
0x1800ab2f7  mov     [rsp+118h+var_B0], r15
0x1800ab2fc  lea     rcx, [rsp+118h+var_80]
0x1800ab304  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ab309  mov     rcx, rax; pszPath
0x1800ab30c  lea     r9, [rsp+118h+var_B0]; ppv
0x1800ab311  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x1800ab318  xor     edx, edx; pbc
0x1800ab31a  call    cs:__imp_SHCreateItemFromParsingName
0x1800ab320  mov     rcx, [rsp+118h]; this
0x1800ab328  test    eax, eax
0x1800ab32a  js      loc_1800AB65B
0x1800ab330  mov     rdx, [rsp+118h+var_B0]
0x1800ab335  lea     rcx, [rsp+118h+var_B8]
0x1800ab33a  call    ?GetStorageProviderContentUri@OneDriveUtils@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIShellItem2@@@Z; OneDriveUtils::GetStorageProviderContentUri(IShellItem2 *)
0x1800ab33f  nop
0x1800ab340  mov     rdx, [rsp+118h+var_B8]
0x1800ab345  test    rdx, rdx
0x1800ab348  jz      short loc_1800AB360
0x1800ab34a  mov     r8, rsi
0x1800ab34d  inc     r8
0x1800ab350  cmp     [rdx+r8*2], r15w
0x1800ab355  jnz     short loc_1800AB34D
0x1800ab357  lea     rcx, [rdi+30h]
0x1800ab35b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ab360  mov     rdx, [rsp+118h+var_B0]
0x1800ab365  lea     rcx, [rsp+118h+var_A8]
0x1800ab36a  call    ?GetStorageProviderFileId@OneDriveUtils@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIShellItem2@@@Z; OneDriveUtils::GetStorageProviderFileId(IShellItem2 *)
0x1800ab36f  nop
0x1800ab370  mov     rdx, [rsp+118h+var_A8]
0x1800ab375  test    rdx, rdx
0x1800ab378  jz      short loc_1800AB391
0x1800ab37a  mov     r8, rsi
0x1800ab37d  inc     r8
0x1800ab380  cmp     [rdx+r8*2], r15w
0x1800ab385  jnz     short loc_1800AB37D
0x1800ab387  lea     rcx, [rdi+10h]
0x1800ab38b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ab390  nop
0x1800ab391  lea     rcx, [rsp+118h+var_A8]
0x1800ab396  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ab39b  nop
0x1800ab39c  lea     rcx, [rsp+118h+var_B8]
0x1800ab3a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800ab3a6  nop
0x1800ab3a7  lea     rcx, [rsp+118h+var_B0]
0x1800ab3ac  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800ab3b1  lea     rdx, word_1801382A0
0x1800ab3b8  lea     rcx, [rsp+118h+var_60]
0x1800ab3c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ab3c5  nop
0x1800ab3c6  lea     rcx, [rsp+118h+var_60]
0x1800ab3ce  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ab3d3  mov     r9, rax; unsigned __int16 *
0x1800ab3d6  lea     r8, aBackedupwallpa; "BackedUpWallpaperPath"
0x1800ab3dd  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ab3e4  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800ab3e9  mov     rcx, [rsp+118h]; this
0x1800ab3f1  test    eax, eax
0x1800ab3f3  js      loc_1800AB5DD
0x1800ab3f9  mov     rdx, [rsp+118h+var_D0]
0x1800ab3fe  inc     rsi
0x1800ab401  cmp     [rdx+rsi*2], r15w
0x1800ab406  jnz     short loc_1800AB3FE
0x1800ab408  mov     r8, rsi
0x1800ab40b  lea     rcx, [rdi+60h]
0x1800ab40f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ab414  mov     [rsp+118h+var_DC], r15d
0x1800ab419  lea     rsi, [rdi+50h]
0x1800ab41d  lea     r9, [rsp+118h+var_DC]; unsigned int *
0x1800ab422  lea     r8, aInterval; "Interval"
0x1800ab429  lea     rdx, aControlPanelPe; "Control Panel\\Personalization\\Desktop"...
0x1800ab430  mov     rbx, 0FFFFFFFF80000001h
0x1800ab437  mov     rcx, rbx; HKEY
0x1800ab43a  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ab43f  test    eax, eax
0x1800ab441  mov     eax, [rsp+118h+var_DC]
0x1800ab445  jns     short loc_1800AB44C
0x1800ab447  mov     eax, 1B7740h
0x1800ab44c  mov     [rsi], rax
0x1800ab44f  mov     [rsp+118h+var_D8], r15d
0x1800ab454  lea     r9, [rsp+118h+var_D8]; unsigned int *
0x1800ab459  lea     r8, aShuffle_0; "Shuffle"
0x1800ab460  lea     rdx, aControlPanelPe; "Control Panel\\Personalization\\Desktop"...
0x1800ab467  mov     rcx, rbx; HKEY
0x1800ab46a  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800ab46f  test    eax, eax
0x1800ab471  js      short loc_1800AB484
0x1800ab473  cmp     [rsp+118h+var_D8], r15d
0x1800ab478  jz      short loc_1800AB484
0x1800ab47a  mov     al, 1
0x1800ab47c  mov     r9d, 1
0x1800ab482  jmp     short loc_1800AB48A
0x1800ab484  mov     al, r15b
0x1800ab487  mov     r9, r15
0x1800ab48a  mov     [rdi+58h], al
0x1800ab48d  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ab494  jz      short loc_1800AB4B0
0x1800ab496  mov     rax, [rsi]
0x1800ab499  mov     qword ptr [rsp+118h+ppv], rax
0x1800ab49e  mov     r8d, 1
0x1800ab4a4  lea     rdx, BackupAssociatedBackgroundSlideshowSettingsData
0x1800ab4ab  call    McTemplateU0xxx_EventWriteTransfer
0x1800ab4b0  lea     rcx, [rdi+60h]
0x1800ab4b4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ab4b9  mov     [rsp+118h+var_B8], rax
0x1800ab4be  mov     r9, rsi
0x1800ab4c1  lea     r8, [rdi+58h]
0x1800ab4c5  lea     rdx, [rsp+118h+var_B8]
0x1800ab4ca  call    ??$Background_SlideshowActivity@AEAY0BI@$$CBGPEBGAEA_NAEA_K@BackgroundActivity@CloudRestoreLauncherTelemetry@@SAXAEAY0BI@$$CBG$$QEAPEBGAEA_NAEA_K@Z; CloudRestoreLauncherTelemetry::BackgroundActivity::Background_SlideshowActivity<ushort const (&)[24],ushort const *,bool &,unsigned __int64 &>(ushort const (&)[24],ushort const * &&,bool &,unsigned __int64 &)
0x1800ab4cf  nop
0x1800ab4d0  lea     rcx, [rsp+118h+var_60]
0x1800ab4d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ab4dd  nop
0x1800ab4de  lea     rcx, [rsp+118h+var_80]
0x1800ab4e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ab4eb  nop
0x1800ab4ec  lea     rcx, [rsp+118h+var_40]
0x1800ab4f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ab4f9  nop
0x1800ab4fa  lea     rcx, [rsp+118h+var_C8]
0x1800ab4ff  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800ab504  mov     rdx, rdi
0x1800ab507  call    ?ComputeBackgroundFit@BackgroundBackupRestoreHandler@@AEAAXAEAV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@@Z; BackgroundBackupRestoreHandler::ComputeBackgroundFit(wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper> &)
0x1800ab50c  nop
0x1800ab50d  lea     rcx, [rsp+118h+var_E8]
0x1800ab512  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800ab517  nop
0x1800ab518  lea     rcx, [rsp+118h+var_C0]
0x1800ab51d  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800ab522  mov     al, 1
0x1800ab524  jmp     loc_1800AB5B4
0x1800ab529  test    cl, 4
0x1800ab52c  jz      short loc_1800AB56D
0x1800ab52e  lea     r9, aSlideshowFolde; "Slideshow Folder is Not OneDrive folder"
0x1800ab535  lea     r8, aBackgroundSlid_0; "Background Slideshow Backup"
0x1800ab53c  mov     rdx, rbx
0x1800ab53f  call    McTemplateU0zz_EventWriteTransfer
0x1800ab544  mov     ecx, cs:Microsoft_Windows_CloudRestoreLauncherEnableBits
0x1800ab54a  test    cl, 4
0x1800ab54d  jz      short loc_1800AB56D
0x1800ab54f  movzx   r9d, byte ptr [rdi+58h]
0x1800ab554  mov     rax, [rdi+50h]
0x1800ab558  mov     qword ptr [rsp+118h+ppv], rax
0x1800ab55d  xor     r8d, r8d
0x1800ab560  lea     rdx, BackupAssociatedBackgroundSlideshowSettingsData
0x1800ab567  call    McTemplateU0xxx_EventWriteTransfer
0x1800ab56c  nop
0x1800ab56d  lea     rcx, [rsp+118h+var_C8]
0x1800ab572  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800ab577  jmp     short loc_1800AB59D
0x1800ab579  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800ab580  jz      short loc_1800AB59D
0x1800ab582  lea     r9, aNoSlideshowShe; "No slideshow shell item present"
0x1800ab589  lea     r8, aBackgroundSlid_0; "Background Slideshow Backup"
0x1800ab590  lea     rdx, InformationMessage
0x1800ab597  call    McTemplateU0zz_EventWriteTransfer
0x1800ab59c  nop
0x1800ab59d  lea     rcx, [rsp+118h+var_E8]
0x1800ab5a2  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800ab5a7  nop
0x1800ab5a8  lea     rcx, [rsp+118h+var_C0]
0x1800ab5ad  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800ab5b2  xor     al, al
0x1800ab5b4  mov     rcx, [rsp+118h+var_20]
0x1800ab5bc  xor     rcx, rsp; StackCookie
0x1800ab5bf  call    __security_check_cookie
0x1800ab5c4  lea     r11, [rsp+118h+var_18]
0x1800ab5cc  mov     rbx, [r11+20h]
0x1800ab5d0  mov     rsi, [r11+30h]
0x1800ab5d4  mov     rsp, r11
0x1800ab5d7  pop     r15
0x1800ab5d9  pop     r14
0x1800ab5db  pop     rdi
0x1800ab5dc  retn
0x1800ab5dd  mov     r9d, eax; char *
0x1800ab5e0  lea     r8, aPcshellShellCl_20; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800ab5e7  mov     edx, 190h; void *
0x1800ab5ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ab5f2  mov     r9d, eax; char *
0x1800ab5f5  lea     r8, aPcshellShellCl_20; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800ab5fc  mov     edx, 15Fh; void *
0x1800ab601  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ab607  mov     r9d, eax; char *
0x1800ab60a  lea     r8, aPcshellShellCl_20; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800ab611  mov     edx, 163h; void *
0x1800ab616  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ab61c  mov     r9d, eax; char *
0x1800ab61f  lea     r8, aPcshellShellCl_20; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800ab626  mov     edx, 167h; void *
0x1800ab62b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
