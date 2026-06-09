# BackgroundSlideShowRestoreHandler::SetSlideShow(wil::cloud_store_data<Windows::Data::Background::DesktopWallpaper> const &)

- ea: `0x1800a35e8`
- end: `0x1800a3c58`
- name: `?SetSlideShow@BackgroundSlideShowRestoreHandler@@AEAAXAEBV?$cloud_store_data@UDesktopWallpaper@Background@Data@Windows@@@wil@@@Z`
- size: `1648`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a32c0`

## callees

- `0x18000c6e0`
- `0x18000d688`
- `0x180011408`
- `0x180015668`
- `0x18001649c`
- `0x18001666c`
- `0x18001cf84`
- `0x18001cfa4`
- `0x18001d0a8`
- `0x18001faa8`
- `0x180036b18`
- `0x1800462bc`
- `0x18009256c`
- `0x180097194`
- `0x1800972b4`
- `0x1800977e8`
- `0x180098178`
- `0x1800a1e48`
- `0x1800a2acc`
- `0x1800a2b64`
- `0x1800a2cc4`
- `0x1800a2fa0`
- `0x1800a3248`
- `0x1800a35e8`
- `0x1800a4218`
- `0x1800a4288`
- `0x18012d010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800a373b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800a373b`
- `OLE32!CoCreateInstance` at `0x1800a3957`
- `OLE32!CoCreateInstance` at `0x1800a3957`
- `ADVAPI32!RegGetValueW` at `0x1800a37d6`
- `ADVAPI32!RegGetValueW` at `0x1800a37d6`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x1800a391a`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x1800a391a`
- `SHELL32!SHParseDisplayName` at `0x1800a38e2`
- `SHELL32!SHParseDisplayName` at `0x1800a38e2`

## string_xrefs

- `0x1800a37c1`: `FilePath`
- `0x1800a3b07`: `Background Slideshow Restore failed as syncRootRelativePath is empty`
- `0x1800a38af`: `image Copy completed`
- `0x1800a375f`: `Slideshow One Drive folder Path`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall BackgroundSlideShowRestoreHandler::SetSlideShow(__int64 a1, __int64 a2)
{
  char v4; // al
  int v5; // eax
  int v6; // ecx
  __int64 v7; // r8
  int v8; // r9d
  __int64 v9; // rax
  __int64 v10; // rax
  const WCHAR *v11; // rax
  HRESULT v12; // eax
  BackgroundSlideShowRestoreHandler *v13; // rcx
  __int64 v14; // rcx
  LSTATUS ValueW; // eax
  bool v16; // sf
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rcx
  HRESULT v20; // eax
  HRESULT v21; // eax
  HRESULT v22; // eax
  __int64 WallpaperPosition; // rbx
  int v24; // eax
  int v25; // edx
  int v26; // r9d
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int pdwType; // [rsp+20h] [rbp-2F8h]
  int pdwTypea; // [rsp+20h] [rbp-2F8h]
  int pdwTypeb; // [rsp+20h] [rbp-2F8h]
  PCWSTR pszPathIn; // [rsp+40h] [rbp-2D8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-2D0h] BYREF
  PWSTR ppszPathOut; // [rsp+50h] [rbp-2C8h] BYREF
  IShellItemArray *ppsiItemArray; // [rsp+58h] [rbp-2C0h] BYREF
  DWORD pcbData[2]; // [rsp+60h] [rbp-2B8h] BYREF
  LPITEMIDLIST ppidl[2]; // [rsp+68h] [rbp-2B0h] BYREF
  _BYTE v42[32]; // [rsp+78h] [rbp-2A0h] BYREF
  _BYTE v43[16]; // [rsp+98h] [rbp-280h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-270h]
  _BYTE v45[40]; // [rsp+B8h] [rbp-260h] BYREF
  _WORD pvData[264]; // [rsp+E0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  v4 = Microsoft_Windows_CloudRestoreLauncherEnableBits;
  if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
  {
    McTemplateU0zz_EventWriteTransfer(
      a1,
      InformationMessage,
      L"Slideshow Restore",
      L"Background Slideshow Restore started");
    v4 = Microsoft_Windows_CloudRestoreLauncherEnableBits;
  }
  if ( *(_QWORD *)(a2 + 112) )
  {
    if ( (v4 & 4) != 0 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 96);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 48);
      v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 16);
      McTemplateU0zzz_EventWriteTransfer(v6, (unsigned int)RestoreAssociatedCloudFile, v5, v8, v7);
    }
    ppszPathOut = 0;
    std::wstring::wstring(v43, a2 + 96);
    v9 = std::wstring::find(v43, L"OneDrive");
    v10 = std::wstring::substr(v43, v45, v9);
    std::wstring::operator=(v43, v10);
    std::wstring::_Tidy_deallocate(v45);
    if ( v44 )
    {
      wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
        &pszPathIn,
        L"%userprofile%\\");
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &ppszPathOut,
        0);
      v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v43);
      v12 = PathAllocCombine(pszPathIn, v11, 1u, &ppszPathOut);
      v13 = retaddr;
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundslideshowrestorehandler.cpp",
          (const char *)(unsigned int)v12,
          pdwType);
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
        McTemplateU0zz_EventWriteTransfer(retaddr, InformationMessage, L"Slideshow One Drive folder Path", ppszPathOut);
      if ( BackgroundSlideShowRestoreHandler::CreateFolderPath(v13, ppszPathOut) )
      {
        memset_0(pvData, 0, 0x208u);
        pcbData[0] = 520;
        ValueW = RegGetValueW(
                   HKEY_CURRENT_USER,
                   L"Software\\Microsoft\\Windows\\CurrentVersion\\CloudRestore\\Wallpaper",
                   L"FilePath",
                   2u,
                   0,
                   pvData,
                   pcbData);
        v16 = ValueW < 0;
        if ( ValueW )
        {
          pvData[0] = 0;
          v16 = ValueW < 0;
          if ( ValueW > 0 )
            v16 = 1;
        }
        if ( !v16 )
        {
          *(_QWORD *)pcbData = v45;
          v17 = std::wstring::wstring(v45, ppszPathOut);
          v18 = std::wstring::wstring(v42, pvData);
          OneDriveUtils::CopySlideShowImage(v18, v17);
        }
      }
      else if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      {
        McTemplateU0zz_EventWriteTransfer(
          v14,
          InformationMessage,
          L"Slideshow Restore",
          L"Background Slideshow Restore OneDrive folder creation failed");
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPathIn);
    }
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::operator->(
                            a1 + 8,
                            &pszPathIn)
             + 275LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>(&pszPathIn);
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::operator->(
                            a1 + 8,
                            &pszPathIn)
             + 274LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>(&pszPathIn);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(v19, InformationMessage, L"Slideshow Restore", L"image Copy completed");
    ppidl[0] = 0;
    v20 = SHParseDisplayName(ppszPathOut, 0, ppidl, 0, 0);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundslideshowrestorehandler.cpp",
        (const char *)(unsigned int)v20,
        pdwTypea);
    ppsiItemArray = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppsiItemArray);
    v21 = SHCreateShellItemArrayFromIDLists(1u, (LPCITEMIDLIST *)ppidl, &ppsiItemArray);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundslideshowrestorehandler.cpp",
        (const char *)(unsigned int)v21,
        pdwTypea);
    ppv = 0;
    v22 = CoCreateInstance(&CLSID_DesktopWallpaper, 0, 4u, &GUID_b92b56a9_8b55_4e14_9a89_0199bbb6f93b, &ppv);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundslideshowrestorehandler.cpp",
        (const char *)(unsigned int)v22,
        pdwTypeb);
    WallpaperPosition = BackgroundSlideShowRestoreHandler::GetWallpaperPosition(retaddr, *(_DWORD *)(a2 + 4));
    v24 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 80LL))(ppv, WallpaperPosition);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB7,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundslideshowrestorehandler.cpp",
        (const char *)(unsigned int)v24,
        pdwTypeb);
    if ( (_DWORD)WallpaperPosition == 3 || !(_DWORD)WallpaperPosition )
    {
      if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      {
        LOBYTE(v26) = *(_BYTE *)(a2 + 8);
        McTemplateU0zuuu_EventWriteTransfer(
          (_DWORD)retaddr,
          v25,
          (unsigned int)L"Slideshow Restore",
          v26,
          *(_BYTE *)(a2 + 9),
          *(_BYTE *)(a2 + 10));
      }
      v27 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 64LL))(
              ppv,
              *(unsigned __int8 *)(a2 + 8)
            | ((unsigned __int8)BYTE2(*(_DWORD *)(a2 + 8)) << 16)
            | ((unsigned __int8)BYTE1(*(_DWORD *)(a2 + 8)) << 8));
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC3,
          (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundslideshowrestorehandler.cpp",
          (const char *)(unsigned int)v27,
          pdwTypeb);
    }
    v28 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 96LL))(ppv, 0);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundslideshowrestorehandler.cpp",
        (const char *)(unsigned int)v28,
        pdwTypeb);
    v29 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 144LL))(ppv, 1);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundslideshowrestorehandler.cpp",
        (const char *)(unsigned int)v29,
        pdwTypeb);
    v30 = (*(__int64 (__fastcall **)(LPVOID, IShellItemArray *))(*(_QWORD *)ppv + 96LL))(ppv, ppsiItemArray);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundslideshowrestorehandler.cpp",
        (const char *)(unsigned int)v30,
        pdwTypeb);
    v31 = (*(__int64 (__fastcall **)(LPVOID, bool, _QWORD))(*(_QWORD *)ppv + 112LL))(
            ppv,
            *(_BYTE *)(a2 + 88) != 0,
            *(unsigned int *)(a2 + 80));
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\backgroundslideshowrestorehandler.cpp",
        (const char *)(unsigned int)v31,
        pdwTypeb);
    if ( (Microsoft_Windows_CloudRestoreLauncherEnableBits & 4) != 0 )
      McTemplateU0xxx_EventWriteTransfer(
        (_DWORD)retaddr,
        (unsigned int)RestoreAssociatedBackgroundSlideshowSettingsData,
        1,
        *(unsigned __int8 *)(a2 + 88),
        *(_QWORD *)(a2 + 80));
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(&ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppsiItemArray);
    std::wstring::_Tidy_deallocate(v43);
    return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  }
  else
  {
    if ( (v4 & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(
        a1,
        InformationMessage,
        L"Slideshow Restore",
        L"Background Slideshow Restore failed as syncRootRelativePath is empty");
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::operator->(
                            a1 + 8,
                            &pszPathIn)
             + 274LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>(&pszPathIn);
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::operator->(
                            a1 + 8,
                            &pszPathIn)
             + 275LL) = 1;
    return tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>(&pszPathIn);
  }
}

```

## disassembly

```asm
0x1800a35e8  mov     [rsp+arg_10], rbx
0x1800a35ed  mov     [rsp+arg_18], rsi
0x1800a35f2  push    rdi
0x1800a35f3  push    r12
0x1800a35f5  push    r13
0x1800a35f7  sub     rsp, 300h
0x1800a35fe  mov     rax, cs:__security_cookie
0x1800a3605  xor     rax, rsp
0x1800a3608  mov     [rsp+318h+var_28], rax
0x1800a3610  mov     rdi, rdx
0x1800a3613  mov     rsi, rcx
0x1800a3616  mov     eax, cs:Microsoft_Windows_CloudRestoreLauncherEnableBits
0x1800a361c  lea     r13, aSlideshowResto_1; "Slideshow Restore"
0x1800a3623  lea     r12, InformationMessage
0x1800a362a  test    al, 4
0x1800a362c  jz      short loc_1800A3646
0x1800a362e  lea     r9, aBackgroundSlid_3; "Background Slideshow Restore started"
0x1800a3635  mov     r8, r13
0x1800a3638  mov     rdx, r12
0x1800a363b  call    McTemplateU0zz_EventWriteTransfer
0x1800a3640  mov     eax, cs:Microsoft_Windows_CloudRestoreLauncherEnableBits
0x1800a3646  cmp     qword ptr [rdi+70h], 0
0x1800a364b  jz      loc_1800A3B03
0x1800a3651  test    al, 4
0x1800a3653  jz      short loc_1800A368A
0x1800a3655  lea     rcx, [rdi+60h]
0x1800a3659  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a365e  mov     r8, rax
0x1800a3661  lea     rcx, [rdi+30h]
0x1800a3665  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a366a  mov     r9, rax
0x1800a366d  lea     rcx, [rdi+10h]
0x1800a3671  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a3676  mov     [rsp+318h+pdwType], r8; int
0x1800a367b  mov     r8, rax
0x1800a367e  lea     rdx, RestoreAssociatedCloudFile
0x1800a3685  call    McTemplateU0zzz_EventWriteTransfer
0x1800a368a  mov     [rsp+318h+ppszPathOut], 0
0x1800a3693  lea     rdx, [rdi+60h]
0x1800a3697  lea     rcx, [rsp+318h+var_280]
0x1800a369f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a36a4  nop
0x1800a36a5  lea     rdx, aOnedrive; "OneDrive"
0x1800a36ac  lea     rcx, [rsp+318h+var_280]
0x1800a36b4  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x1800a36b9  mov     r8, rax
0x1800a36bc  lea     rdx, [rsp+318h+var_260]
0x1800a36c4  lea     rcx, [rsp+318h+var_280]
0x1800a36cc  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800a36d1  mov     rdx, rax
0x1800a36d4  lea     rcx, [rsp+318h+var_280]
0x1800a36dc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a36e1  lea     rcx, [rsp+318h+var_260]
0x1800a36e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a36ee  cmp     [rsp+318h+var_270], 0
0x1800a36f7  jz      loc_1800A3862
0x1800a36fd  lea     rdx, aUserprofile; "%userprofile%\\"
0x1800a3704  lea     rcx, [rsp+318h+pszPathIn]
0x1800a3709  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x1800a370e  nop
0x1800a370f  xor     edx, edx
0x1800a3711  lea     rcx, [rsp+318h+ppszPathOut]
0x1800a3716  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a371b  lea     rcx, [rsp+318h+var_280]
0x1800a3723  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a3728  mov     rdx, rax; pszMore
0x1800a372b  lea     r9, [rsp+318h+ppszPathOut]; ppszPathOut
0x1800a3730  mov     r8d, 1; dwFlags
0x1800a3736  mov     rcx, [rsp+318h+pszPathIn]; pszPathIn
0x1800a373b  call    cs:__imp_PathAllocCombine
0x1800a3741  mov     rcx, [rsp+318h]; this
0x1800a3749  test    eax, eax
0x1800a374b  js      loc_1800A3B9B
0x1800a3751  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800a3758  jz      short loc_1800A376E
0x1800a375a  mov     r9, [rsp+318h+ppszPathOut]
0x1800a375f  lea     r8, aSlideshowOneDr; "Slideshow One Drive folder Path"
0x1800a3766  mov     rdx, r12
0x1800a3769  call    McTemplateU0zz_EventWriteTransfer
0x1800a376e  mov     rdx, [rsp+318h+ppszPathOut]; unsigned __int16 *
0x1800a3773  call    ?CreateFolderPath@BackgroundSlideShowRestoreHandler@@AEAA_NPEBG@Z; BackgroundSlideShowRestoreHandler::CreateFolderPath(ushort const *)
0x1800a3778  test    al, al
0x1800a377a  jz      loc_1800A383C
0x1800a3780  mov     ebx, 208h
0x1800a3785  mov     r8d, ebx; Size
0x1800a3788  xor     edx, edx; Val
0x1800a378a  lea     rcx, [rsp+318h+var_238]; void *
0x1800a3792  call    memset_0
0x1800a3797  mov     [rsp+318h+var_2B8], ebx
0x1800a379b  lea     rax, [rsp+318h+var_2B8]
0x1800a37a0  mov     [rsp+318h+pcbData], rax; pcbData
0x1800a37a5  lea     rax, [rsp+318h+var_238]
0x1800a37ad  mov     [rsp+318h+pvData], rax; pvData
0x1800a37b2  mov     [rsp+318h+pdwType], 0; pdwType
0x1800a37bb  mov     r9d, 2; dwFlags
0x1800a37c1  lea     r8, aFilepath; "FilePath"
0x1800a37c8  lea     rdx, aSoftwareMicros_27; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800a37cf  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800a37d6  call    cs:__imp_RegGetValueW
0x1800a37dc  test    eax, eax
0x1800a37de  jz      short loc_1800A37F8
0x1800a37e0  xor     ecx, ecx
0x1800a37e2  mov     [rsp+318h+var_238], cx
0x1800a37ea  test    eax, eax
0x1800a37ec  jle     short loc_1800A37F8
0x1800a37ee  movzx   eax, ax
0x1800a37f1  or      eax, 80070000h
0x1800a37f6  test    eax, eax
0x1800a37f8  js      short loc_1800A3858
0x1800a37fa  lea     rax, [rsp+318h+var_260]
0x1800a3802  mov     qword ptr [rsp+318h+var_2B8], rax
0x1800a3807  mov     rdx, [rsp+318h+ppszPathOut]
0x1800a380c  lea     rcx, [rsp+318h+var_260]
0x1800a3814  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a3819  mov     rbx, rax
0x1800a381c  lea     rdx, [rsp+318h+var_238]
0x1800a3824  lea     rcx, [rsp+318h+var_2A0]
0x1800a3829  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a382e  nop
0x1800a382f  mov     rdx, rbx
0x1800a3832  mov     rcx, rax
0x1800a3835  call    ?CopySlideShowImage@OneDriveUtils@@YAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; OneDriveUtils::CopySlideShowImage(std::wstring,std::wstring)
0x1800a383a  jmp     short loc_1800A3858
0x1800a383c  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800a3843  jz      short loc_1800A3858
0x1800a3845  lea     r9, aBackgroundSlid_1; "Background Slideshow Restore OneDrive f"...
0x1800a384c  mov     r8, r13
0x1800a384f  mov     rdx, r12
0x1800a3852  call    McTemplateU0zz_EventWriteTransfer
0x1800a3857  nop
0x1800a3858  lea     rcx, [rsp+318h+pszPathIn]
0x1800a385d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800a3862  lea     rdx, [rsp+318h+pszPathIn]
0x1800a3867  lea     rcx, [rsi+8]
0x1800a386b  call    ??C?$tip_test@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::operator->(void)
0x1800a3870  mov     rdx, [rax]
0x1800a3873  mov     byte ptr [rdx+113h], 1
0x1800a387a  lea     rcx, [rsp+318h+pszPathIn]
0x1800a387f  call    ??1?$test_data_control@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>(void)
0x1800a3884  lea     rdx, [rsp+318h+pszPathIn]
0x1800a3889  lea     rcx, [rsi+8]
0x1800a388d  call    ??C?$tip_test@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::operator->(void)
0x1800a3892  mov     rcx, [rax]
0x1800a3895  mov     byte ptr [rcx+112h], 1
0x1800a389c  lea     rcx, [rsp+318h+pszPathIn]
0x1800a38a1  call    ??1?$test_data_control@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>(void)
0x1800a38a6  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800a38ad  jz      short loc_1800A38C1
0x1800a38af  lea     r9, aImageCopyCompl; "image Copy completed"
0x1800a38b6  mov     r8, r13
0x1800a38b9  mov     rdx, r12
0x1800a38bc  call    McTemplateU0zz_EventWriteTransfer
0x1800a38c1  mov     [rsp+318h+ppidl], 0
0x1800a38ca  mov     [rsp+318h+pdwType], 0; int
0x1800a38d3  xor     r9d, r9d; sfgaoIn
0x1800a38d6  lea     r8, [rsp+318h+ppidl]; ppidl
0x1800a38db  xor     edx, edx; pbc
0x1800a38dd  mov     rcx, [rsp+318h+ppszPathOut]; pszName
0x1800a38e2  call    cs:__imp_SHParseDisplayName
0x1800a38e8  mov     rcx, [rsp+318h]; this
0x1800a38f0  test    eax, eax
0x1800a38f2  js      loc_1800A3BB0
0x1800a38f8  mov     [rsp+318h+ppsiItemArray], 0
0x1800a3901  lea     rcx, [rsp+318h+ppsiItemArray]
0x1800a3906  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a390b  lea     r8, [rsp+318h+ppsiItemArray]; ppsiItemArray
0x1800a3910  lea     rdx, [rsp+318h+ppidl]; rgpidl
0x1800a3915  mov     ecx, 1; cidl
0x1800a391a  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x1800a3920  mov     rcx, [rsp+318h]; this
0x1800a3928  test    eax, eax
0x1800a392a  js      loc_1800A3BC5
0x1800a3930  mov     [rsp+318h+ppv], 0
0x1800a3939  lea     rax, [rsp+318h+ppv]
0x1800a393e  mov     [rsp+318h+pdwType], rax; int
0x1800a3943  lea     r9, _GUID_b92b56a9_8b55_4e14_9a89_0199bbb6f93b; riid
0x1800a394a  xor     edx, edx; pUnkOuter
0x1800a394c  lea     r8d, [rdx+4]; dwClsContext
0x1800a3950  lea     rcx, CLSID_DesktopWallpaper; rclsid
0x1800a3957  call    cs:__imp_CoCreateInstance
0x1800a395d  mov     rcx, [rsp+318h]; this
0x1800a3965  test    eax, eax
0x1800a3967  js      loc_1800A3BDA
0x1800a396d  mov     edx, [rdi+4]; unsigned int
0x1800a3970  call    ?GetWallpaperPosition@BackgroundSlideShowRestoreHandler@@AEAAKK@Z; BackgroundSlideShowRestoreHandler::GetWallpaperPosition(ulong)
0x1800a3975  mov     ebx, eax
0x1800a3977  mov     rcx, [rsp+318h+ppv]
0x1800a397c  mov     rdx, [rcx]
0x1800a397f  mov     rax, [rdx+50h]
0x1800a3983  mov     edx, ebx
0x1800a3985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a398a  mov     rcx, [rsp+318h]; this
0x1800a3992  test    eax, eax
0x1800a3994  js      loc_1800A3BEF
0x1800a399a  cmp     ebx, 3
0x1800a399d  jz      short loc_1800A39A3
0x1800a399f  test    ebx, ebx
0x1800a39a1  jnz     short loc_1800A3A0A
0x1800a39a3  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800a39aa  jz      short loc_1800A39C6
0x1800a39ac  mov     al, [rdi+0Ah]
0x1800a39af  mov     byte ptr [rsp+318h+pvData], al
0x1800a39b3  mov     al, [rdi+9]
0x1800a39b6  mov     byte ptr [rsp+318h+pdwType], al; int
0x1800a39ba  mov     r9b, [rdi+8]
0x1800a39be  mov     r8, r13
0x1800a39c1  call    McTemplateU0zuuu_EventWriteTransfer
0x1800a39c6  mov     rcx, [rsp+318h+ppv]
0x1800a39cb  mov     r9, [rcx]
0x1800a39ce  mov     eax, [rdi+8]
0x1800a39d1  shr     eax, 8
0x1800a39d4  movzx   edx, al
0x1800a39d7  shl     edx, 8
0x1800a39da  mov     eax, [rdi+8]
0x1800a39dd  shr     eax, 10h
0x1800a39e0  movzx   r8d, al
0x1800a39e4  shl     r8d, 10h
0x1800a39e8  or      edx, r8d
0x1800a39eb  movzx   eax, byte ptr [rdi+8]
0x1800a39ef  or      edx, eax
0x1800a39f1  mov     rax, [r9+40h]
0x1800a39f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a39fa  mov     rcx, [rsp+318h]; this
0x1800a3a02  test    eax, eax
0x1800a3a04  js      loc_1800A3C04
0x1800a3a0a  mov     rcx, [rsp+318h+ppv]
0x1800a3a0f  mov     rax, [rcx]
0x1800a3a12  xor     edx, edx
0x1800a3a14  mov     rax, [rax+60h]
0x1800a3a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3a1d  mov     rcx, [rsp+318h]; this
0x1800a3a25  test    eax, eax
0x1800a3a27  js      loc_1800A3C19
0x1800a3a2d  mov     rcx, [rsp+318h+ppv]
0x1800a3a32  mov     rax, [rcx]
0x1800a3a35  mov     edx, 1
0x1800a3a3a  mov     rax, [rax+90h]
0x1800a3a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3a46  mov     rcx, [rsp+318h]; this
0x1800a3a4e  test    eax, eax
0x1800a3a50  js      loc_1800A3C2E
0x1800a3a56  mov     rcx, [rsp+318h+ppv]
0x1800a3a5b  mov     rax, [rcx]
0x1800a3a5e  mov     rdx, [rsp+318h+ppsiItemArray]
0x1800a3a63  mov     rax, [rax+60h]
0x1800a3a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3a6c  mov     rcx, [rsp+318h]; this
0x1800a3a74  test    eax, eax
0x1800a3a76  js      loc_1800A3C43
0x1800a3a7c  mov     rcx, [rsp+318h+ppv]
0x1800a3a81  mov     rax, [rcx]
0x1800a3a84  xor     edx, edx
0x1800a3a86  cmp     [rdi+58h], dl
0x1800a3a89  setnz   dl
0x1800a3a8c  mov     r8d, [rdi+50h]
0x1800a3a90  mov     rax, [rax+70h]
0x1800a3a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3a99  mov     rcx, [rsp+318h]; this
0x1800a3aa1  test    eax, eax
0x1800a3aa3  js      loc_1800A3B86
0x1800a3aa9  test    byte ptr cs:Microsoft_Windows_CloudRestoreLauncherEnableBits, 4
0x1800a3ab0  jz      short loc_1800A3AD3
0x1800a3ab2  movzx   r9d, byte ptr [rdi+58h]
0x1800a3ab7  mov     rax, [rdi+50h]
0x1800a3abb  mov     [rsp+318h+pdwType], rax
0x1800a3ac0  mov     r8d, 1
0x1800a3ac6  lea     rdx, RestoreAssociatedBackgroundSlideshowSettingsData
0x1800a3acd  call    McTemplateU0xxx_EventWriteTransfer
0x1800a3ad2  nop
0x1800a3ad3  lea     rcx, [rsp+318h+ppv]
0x1800a3ad8  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x1800a3add  nop
0x1800a3ade  lea     rcx, [rsp+318h+ppsiItemArray]
0x1800a3ae3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a3ae8  nop
0x1800a3ae9  lea     rcx, [rsp+318h+var_280]
0x1800a3af1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3af6  nop
0x1800a3af7  lea     rcx, [rsp+318h+ppszPathOut]
0x1800a3afc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a3b01  jmp     short loc_1800A3B5D
0x1800a3b03  test    al, 4
0x1800a3b05  jz      short loc_1800A3B19
0x1800a3b07  lea     r9, aBackgroundSlid_4; "Background Slideshow Restore failed as "...
0x1800a3b0e  mov     r8, r13
0x1800a3b11  mov     rdx, r12
0x1800a3b14  call    McTemplateU0zz_EventWriteTransfer
0x1800a3b19  lea     rdx, [rsp+318h+pszPathIn]
0x1800a3b1e  lea     rcx, [rsi+8]
0x1800a3b22  call    ??C?$tip_test@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::operator->(void)
0x1800a3b27  mov     rdx, [rax]
0x1800a3b2a  mov     byte ptr [rdx+112h], 1
0x1800a3b31  lea     rcx, [rsp+318h+pszPathIn]
0x1800a3b36  call    ??1?$test_data_control@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::~test_data_control<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>(void)
0x1800a3b3b  lea     rdx, [rsp+318h+pszPathIn]
0x1800a3b40  lea     rcx, [rsi+8]
0x1800a3b44  call    ??C?$tip_test@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_BackgroundSlideshowRestoreTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_BackgroundSlideshowRestoreTipTest,_tip_BackgroundSlideshowRestoreTipTest>>::operator->(void)
0x1800a3b49  mov     rcx, [rax]
0x1800a3b4c  mov     byte ptr [rcx+113h], 1
0x1800a3b53  lea     rcx, [rsp+318h+pszPathIn]
  ... truncated ...
```
