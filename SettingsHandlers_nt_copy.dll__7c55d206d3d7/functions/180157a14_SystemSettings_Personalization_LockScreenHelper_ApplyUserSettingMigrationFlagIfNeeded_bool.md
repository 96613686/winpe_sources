# SystemSettings::Personalization::LockScreenHelper::ApplyUserSettingMigrationFlagIfNeeded(bool *)

- ea: `0x180157a14`
- end: `0x180158103`
- name: `?ApplyUserSettingMigrationFlagIfNeeded@LockScreenHelper@Personalization@SystemSettings@@SA_NPEA_N@Z`
- size: `1775`
- prototype: `bool __fastcall(bool *)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18015fcb0`

## callees

- `0x18000c840`
- `0x18001ecfc`
- `0x18002373c`
- `0x18004e884`
- `0x1800d55c0`
- `0x1800df1e4`
- `0x180119138`
- `0x180119ef0`
- `0x180127acc`
- `0x180149f9c`
- `0x18014b8a0`
- `0x18014d9f0`
- `0x180151070`
- `0x1801510d8`
- `0x1801511bc`
- `0x180152594`
- `0x1801553d4`
- `0x18015558c`
- `0x180157724`
- `0x180157a14`
- `0x18015c0d4`
- `0x18015cef4`
- `0x18015fc44`
- `0x180161480`
- `0x180161528`
- `0x180164cdc`
- `0x180164d34`
- `0x18016d01c`
- `0x18016df64`
- `0x18016dfe0`
- `0x1801720c4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180157dbf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180157df4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180157dbf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180157df4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180157a92`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180157a92`
- `SHLWAPI!SHSetValueW` at `0x180157af4`
- `SHLWAPI!SHSetValueW` at `0x180157b6a`
- `SHLWAPI!SHSetValueW` at `0x180157f64`
- `SHLWAPI!SHSetValueW` at `0x180157af4`
- `SHLWAPI!SHSetValueW` at `0x180157b6a`
- `SHLWAPI!SHSetValueW` at `0x180157f64`

## string_xrefs

- `0x180157b30`: `PreplacedWidgetsApplied`
- `0x180158025`: `HasLockCanvasWithRecommendationsMigratedFromLockCanvasV1`
- `0x1801580a0`: `HasLockCanvasWithRecommendationsMigratedFromLockCanvasV1`
- `0x180157bb6`: `HasLockCanvasWithRecommendationsMigratedFromDetailedStatus`
- `0x180158000`: `HasLockCanvasWithRecommendationsMigratedFromDetailedStatus`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
char __fastcall SystemSettings::Personalization::LockScreenHelper::ApplyUserSettingMigrationFlagIfNeeded(bool *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  winrt::hstring *CustomProperty; // rax
  const unsigned __int16 *v15; // rax
  int v16; // ebx
  __int64 v17; // rax
  const WCHAR *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  const WCHAR *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  unsigned int *v25; // rcx
  winrt::hstring *v26; // rax
  const unsigned __int16 *v27; // rax
  int v28; // ebx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v33; // [rsp+40h] [rbp-E8h] BYREF
  int pvData; // [rsp+44h] [rbp-E4h] BYREF
  unsigned int v35; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v36; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v37[8]; // [rsp+58h] [rbp-D0h] BYREF
  _BYTE v38[8]; // [rsp+60h] [rbp-C8h] BYREF
  _BYTE v39[8]; // [rsp+68h] [rbp-C0h] BYREF
  _BYTE v40[8]; // [rsp+70h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp-B0h] BYREF
  _BYTE v42[8]; // [rsp+80h] [rbp-A8h] BYREF
  _BYTE v43[8]; // [rsp+88h] [rbp-A0h] BYREF
  _BYTE v44[8]; // [rsp+90h] [rbp-98h] BYREF
  _BYTE v45[8]; // [rsp+98h] [rbp-90h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-88h] BYREF
  _BYTE v47[8]; // [rsp+A8h] [rbp-80h] BYREF
  _BYTE v48[8]; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v49[32]; // [rsp+B8h] [rbp-70h] BYREF
  _BYTE v50[32]; // [rsp+D8h] [rbp-50h] BYREF

  *a1 = 0;
  pvData = 0;
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
         L"HasMigratedDetailedStatus",
         0x10u,
         0,
         &pvData,
         &pcbData) == 2 )
  {
    if ( SystemSettings::Personalization::LockScreenHelper::HasUserSeenLockScreenSinceLastOSSwap() )
    {
      if ( ((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57383290>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_57383290>::GetImpl'::`2'::impl)
         || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_55707948>::GetImpl'::`2'::impl))
        && (v35 = 0,
            !(unsigned int)SHRegGetDWORD(
                             HKEY_CURRENT_USER,
                             L"Software\\Microsoft\\Windows\\CurrentVersion\\Dsh\\Widgets\\WidgetOnLock",
                             L"PreplacedWidgetsApplied",
                             &v35)) )
      {
        PersonalizeSettingsTelemetry::LockScreenWidgetSkipMigrateDetailStatus();
        SHSetValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
          L"HasMigratedDetailedStatus",
          4u,
          &pvData,
          4u);
        *a1 = 1;
        v33 = 1;
        wil::reg::set_value<int>(v6, v5, L"LockScreenWidgetsEnabled", &v33);
        return 1;
      }
      else
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_55707948>::GetImpl'::`2'::impl) )
        {
          v33 = 1;
          wil::reg::set_value<int>(v8, v7, L"HasLockCanvasWithRecommendationsMigratedFromDetailedStatus", &v33);
          v33 = 0;
          wil::reg::set_value<unsigned long>(v10, v9, v11, &v33);
          v33 = 0;
          wil::reg::set_value<int>(v13, v12, L"LockScreenWidgetsSystemCurationEnabled", &v33);
        }
        PersonalizeSettingsTelemetry::LockScreenWidgetStartMigrateDetailStatus();
        winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager::CuratedTileCollectionManager((winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager *)v40);
        winrt::param::hstring::hstring((winrt::param::hstring *)v50, L"LockScreenPinnedTiles");
        winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTileCollectionManager<winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollectionManager>::GetCollection(
          v40,
          v48,
          v50);
        winrt::impl::consume_WindowsUdk_UI_IMenuItem<winrt::WindowsUdk::UI::IMenuItem>::InvokeAsync(v48, v47);
        winrt::impl::get_begin_iterator<winrt::Windows::Foundation::Collections::IMapView<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>,0>(
          v39,
          v47);
        v46 = 0;
        while ( !(unsigned __int8)winrt::Windows::Foundation::operator==(v39, &v46) )
        {
          winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>>::operator*(
            v39,
            v38);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_55707948>::GetImpl'::`2'::impl) )
          {
            winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>,winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>::Value(
              v38,
              &v35);
            winrt::param::hstring::hstring((winrt::param::hstring *)v50, L"PinnedTileSlot");
            if ( (unsigned __int8)winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTile<winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>::HasCustomProperty(
                                    &v35,
                                    v50) )
            {
              winrt::param::hstring::hstring((winrt::param::hstring *)v49, L"PinnedTileSlot");
              CustomProperty = (winrt::hstring *)winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTile<winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>::GetCustomProperty(
                                                   &v35,
                                                   v43,
                                                   v49);
              v15 = winrt::hstring::c_str(CustomProperty);
              std::wstring::wstring(v50, v15);
              v16 = std::stoi(v50);
              std::wstring::_Tidy_deallocate(v50);
              winrt::handle_type<winrt::impl::hstring_traits>::close(v43);
              if ( v16 == 0x10000 )
              {
                *a1 = 1;
                winrt::impl::consume_Windows_ApplicationModel_Core_IAppListEntry<winrt::Windows::ApplicationModel::Core::IAppListEntry>::DisplayInfo(
                  &v35,
                  v45);
                v17 = winrt::Windows::Foundation::IUnknown::as<winrt::WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(
                        v45,
                        v44);
                winrt::impl::consume_Windows_ApplicationModel_Core_IAppListEntry<winrt::Windows::ApplicationModel::Core::IAppListEntry>::DisplayInfo(
                  v17,
                  v42);
                _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v44);
                v18 = winrt::hstring::c_str((winrt::hstring *)v42);
                if ( CompareStringOrdinal(v18, -1, L"MicrosoftWindows.Dashboard_cw5n1h2txyewy!Widgets", -1, 1) == 2
                  || (v22 = winrt::hstring::c_str((winrt::hstring *)v42),
                      CompareStringOrdinal(
                        v22,
                        -1,
                        L"MicrosoftWindows.Client.WebExperience_cw5n1h2txyewy!Widgets",
                        -1,
                        1) == 2) )
                {
                  v33 = 1;
                  wil::reg::set_value<unsigned long>(v20, v19, v21, &v33);
                  v33 = 1;
                  wil::reg::set_value<int>(v24, v23, L"LockScreenWidgetsSystemCurationEnabled", &v33);
                }
                else
                {
                  v33 = 2;
                  wil::reg::set_value<unsigned long>(v20, v19, v21, &v33);
                }
                winrt::handle_type<winrt::impl::hstring_traits>::close(v42);
                _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v45);
              }
            }
            v25 = &v35;
          }
          else
          {
            winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>,winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>::Value(
              v38,
              v37);
            winrt::param::hstring::hstring((winrt::param::hstring *)v49, L"PinnedTileSlot");
            if ( (unsigned __int8)winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTile<winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>::HasCustomProperty(
                                    v37,
                                    v49) )
            {
              winrt::param::hstring::hstring((winrt::param::hstring *)v49, L"PinnedTileSlot");
              v26 = (winrt::hstring *)winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTile<winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>::GetCustomProperty(
                                        v37,
                                        &v36,
                                        v49);
              v27 = winrt::hstring::c_str(v26);
              std::wstring::wstring(v50, v27);
              v28 = std::stoi(v50);
              std::wstring::_Tidy_deallocate(v50);
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v36);
              if ( v28 == 0x10000 )
              {
                *a1 = 1;
                _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v37);
                _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v38);
                break;
              }
            }
            v25 = (unsigned int *)v37;
          }
          _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v25);
          _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v38);
          winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>>::operator++(v39);
        }
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v46);
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v39);
        SHSetValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
          L"HasMigratedDetailedStatus",
          4u,
          &pvData,
          4u);
        PersonalizeSettingsTelemetry::LockScreenWidgetMigrateDetailStatusCompleted<bool &>(a1);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57383290>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_57383290>::GetImpl'::`2'::impl)
          || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_55707948>::GetImpl'::`2'::impl) )
        {
          v33 = *a1;
          wil::reg::set_value<int>(v30, v29, L"LockScreenWidgetsEnabled", &v33);
        }
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v47);
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v48);
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v40);
        return 1;
      }
    }
    else
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_55707948>::GetImpl'::`2'::impl) )
      {
        v35 = 1;
        wil::reg::set_value<int>(v3, v2, L"LockScreenWidgetsSystemCurationEnabled", &v35);
      }
      SHSetValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
        L"HasMigratedDetailedStatus",
        4u,
        &pvData,
        4u);
      return 0;
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_55707948>::GetImpl'::`2'::impl) )
    {
      v36 = -2147483647;
      wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<unsigned int>(
        &v36,
        v44,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
        L"HasLockCanvasWithRecommendationsMigratedFromDetailedStatus",
        16);
      v36 = -2147483647;
      wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<unsigned int>(
        &v36,
        v43,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
        L"HasLockCanvasWithRecommendationsMigratedFromLockCanvasV1",
        16);
      v36 = -2147483647;
      wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<unsigned int>(
        &v36,
        v40,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen",
        L"LockScreenWidgetsSystemCurationEnabled",
        16);
      if ( !v44[4] && !v43[4] )
      {
        if ( !v40[4] )
        {
          v33 = 0;
          wil::reg::set_value<int>(v32, v31, L"LockScreenWidgetsSystemCurationEnabled", &v33);
        }
        v33 = 1;
        wil::reg::set_value<int>(v32, v31, L"HasLockCanvasWithRecommendationsMigratedFromLockCanvasV1", &v33);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180157a14  mov     [rsp+arg_8], rbx
0x180157a19  mov     [rsp+arg_10], rsi
0x180157a1e  push    rdi
0x180157a1f  push    r12
0x180157a21  push    r13
0x180157a23  push    r14
0x180157a25  push    r15
0x180157a27  sub     rsp, 100h
0x180157a2e  mov     rax, cs:__security_cookie
0x180157a35  xor     rax, rsp
0x180157a38  mov     [rsp+128h+var_30], rax
0x180157a40  mov     rdi, rcx
0x180157a43  xor     esi, esi
0x180157a45  mov     [rcx], sil
0x180157a48  lea     r15, aSoftwareMicros_91; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180157a4f  lea     r13, aHasmigrateddet; "HasMigratedDetailedStatus"
0x180157a56  mov     [rsp+128h+var_E4], esi
0x180157a5a  lea     r12d, [rsi+4]
0x180157a5e  mov     [rsp+128h+var_B0], r12d
0x180157a63  lea     rax, [rsp+128h+var_B0]
0x180157a68  mov     [rsp+128h+pcbData], rax; pcbData
0x180157a6d  lea     rax, [rsp+128h+var_E4]
0x180157a72  mov     [rsp+128h+pvData], rax; pvData
0x180157a77  mov     [rsp+128h+pdwType], rsi; pdwType
0x180157a7c  lea     ebx, [rsi+10h]
0x180157a7f  mov     r9d, ebx; dwFlags
0x180157a82  mov     r8, r13; lpValue
0x180157a85  mov     rdx, r15; lpSubKey
0x180157a88  mov     r14, 0FFFFFFFF80000001h
0x180157a8f  mov     rcx, r14; hkey
0x180157a92  call    cs:__imp_RegGetValueW
0x180157a99  nop     dword ptr [rax+rax+00h]
0x180157a9e  cmp     eax, 2
0x180157aa1  jnz     loc_180157FE3
0x180157aa7  call    ?HasUserSeenLockScreenSinceLastOSSwap@LockScreenHelper@Personalization@SystemSettings@@SA_NXZ; SystemSettings::Personalization::LockScreenHelper::HasUserSeenLockScreenSinceLastOSSwap(void)
0x180157aac  test    al, al
0x180157aae  jnz     short loc_180157B07
0x180157ab0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55707948@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55707948@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948> `wil::Feature<__WilFeatureTraits_Feature_55707948>::GetImpl(void)'::`2'::impl
0x180157ab7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55707948@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948>::__private_IsEnabled(void)
0x180157abc  test    al, al
0x180157abe  jz      short loc_180157AD9
0x180157ac0  mov     [rsp+128h+var_E0], 1
0x180157ac8  lea     r9, [rsp+128h+var_E0]
0x180157acd  lea     r8, aLockscreenwidg_4; "LockScreenWidgetsSystemCurationEnabled"
0x180157ad4  call    ??$set_value@H@reg@wil@@YAXPEAUHKEY__@@PEBG1AEBH@Z; wil::reg::set_value<int>(HKEY__ *,ushort const *,ushort const *,int const &)
0x180157ad9  mov     dword ptr [rsp+128h+pvData], r12d; cbData
0x180157ade  lea     rax, [rsp+128h+var_E4]
0x180157ae3  mov     [rsp+128h+pdwType], rax; pvData
0x180157ae8  mov     r9d, r12d; dwType
0x180157aeb  mov     r8, r13; pszValue
0x180157aee  mov     rdx, r15; pszSubKey
0x180157af1  mov     rcx, r14; hkey
0x180157af4  call    cs:__imp_SHSetValueW
0x180157afb  nop     dword ptr [rax+rax+00h]
0x180157b00  xor     al, al
0x180157b02  jmp     loc_1801580AF
0x180157b07  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57383290@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57383290@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57383290> `wil::Feature<__WilFeatureTraits_Feature_57383290>::GetImpl(void)'::`2'::impl
0x180157b0e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57383290@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57383290>::__private_IsEnabled(void)
0x180157b13  test    al, al
0x180157b15  jnz     short loc_180157B27
0x180157b17  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55707948@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55707948@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948> `wil::Feature<__WilFeatureTraits_Feature_55707948>::GetImpl(void)'::`2'::impl
0x180157b1e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55707948@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948>::__private_IsEnabled(void)
0x180157b23  test    al, al
0x180157b25  jz      short loc_180157B99
0x180157b27  mov     [rsp+128h+var_E0], esi
0x180157b2b  lea     r9, [rsp+128h+var_E0]; unsigned int *
0x180157b30  lea     r8, aPreplacedwidge; "PreplacedWidgetsApplied"
0x180157b37  lea     rdx, aSoftwareMicros_79; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180157b3e  mov     rcx, r14; HKEY
0x180157b41  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180157b46  test    eax, eax
0x180157b48  jnz     short loc_180157B99
0x180157b4a  call    ?LockScreenWidgetSkipMigrateDetailStatus@PersonalizeSettingsTelemetry@@SAXXZ; PersonalizeSettingsTelemetry::LockScreenWidgetSkipMigrateDetailStatus(void)
0x180157b4f  mov     dword ptr [rsp+128h+pvData], r12d; cbData
0x180157b54  lea     rax, [rsp+128h+var_E4]
0x180157b59  mov     [rsp+128h+pdwType], rax; pvData
0x180157b5e  mov     r9d, r12d; dwType
0x180157b61  mov     r8, r13; pszValue
0x180157b64  mov     rdx, r15; pszSubKey
0x180157b67  mov     rcx, r14; hkey
0x180157b6a  call    cs:__imp_SHSetValueW
0x180157b71  nop     dword ptr [rax+rax+00h]
0x180157b76  mov     byte ptr [rdi], 1
0x180157b79  mov     [rsp+128h+var_E8], 1
0x180157b81  lea     r9, [rsp+128h+var_E8]
0x180157b86  lea     r8, aLockscreenwidg_8; "LockScreenWidgetsEnabled"
0x180157b8d  call    ??$set_value@H@reg@wil@@YAXPEAUHKEY__@@PEBG1AEBH@Z; wil::reg::set_value<int>(HKEY__ *,ushort const *,ushort const *,int const &)
0x180157b92  mov     al, 1
0x180157b94  jmp     loc_1801580AF
0x180157b99  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55707948@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55707948@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948> `wil::Feature<__WilFeatureTraits_Feature_55707948>::GetImpl(void)'::`2'::impl
0x180157ba0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55707948@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948>::__private_IsEnabled(void)
0x180157ba5  test    al, al
0x180157ba7  jz      short loc_180157BE5
0x180157ba9  mov     [rsp+128h+var_E8], 1
0x180157bb1  lea     r9, [rsp+128h+var_E8]
0x180157bb6  lea     r8, aHaslockcanvasw; "HasLockCanvasWithRecommendationsMigrate"...
0x180157bbd  call    ??$set_value@H@reg@wil@@YAXPEAUHKEY__@@PEBG1AEBH@Z; wil::reg::set_value<int>(HKEY__ *,ushort const *,ushort const *,int const &)
0x180157bc2  mov     [rsp+128h+var_E8], esi
0x180157bc6  lea     r9, [rsp+128h+var_E8]
0x180157bcb  call    ??$set_value@K@reg@wil@@YAXPEAUHKEY__@@PEBG1AEBK@Z; wil::reg::set_value<ulong>(HKEY__ *,ushort const *,ushort const *,ulong const &)
0x180157bd0  mov     [rsp+128h+var_E8], esi
0x180157bd4  lea     r9, [rsp+128h+var_E8]
0x180157bd9  lea     r8, aLockscreenwidg_4; "LockScreenWidgetsSystemCurationEnabled"
0x180157be0  call    ??$set_value@H@reg@wil@@YAXPEAUHKEY__@@PEBG1AEBH@Z; wil::reg::set_value<int>(HKEY__ *,ushort const *,ushort const *,int const &)
0x180157be5  call    ?LockScreenWidgetStartMigrateDetailStatus@PersonalizeSettingsTelemetry@@SAXXZ; PersonalizeSettingsTelemetry::LockScreenWidgetStartMigrateDetailStatus(void)
0x180157bea  lea     rcx, [rsp+128h+var_B8]; this
0x180157bef  call    ??0CuratedTileCollectionManager@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@winrt@@QEAA@XZ; winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedTileCollectionManager::CuratedTileCollectionManager(void)
0x180157bf4  nop
0x180157bf5  lea     rdx, aLockscreenpinn; "LockScreenPinnedTiles"
0x180157bfc  lea     rcx, [rsp+128h+var_50]; this
0x180157c04  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180157c09  lea     r8, [rsp+128h+var_50]
0x180157c11  lea     rdx, [rsp+128h+var_78]
0x180157c19  lea     rcx, [rsp+128h+var_B8]
0x180157c1e  call    ?GetCollection@?$consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTileCollectionManager@UICuratedTileCollectionManager@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTileCollectionManager<winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollectionManager>::GetCollection(winrt::param::hstring const &)
0x180157c23  nop
0x180157c24  lea     rdx, [rsp+128h+var_80]
0x180157c2c  lea     rcx, [rsp+128h+var_78]
0x180157c34  call    ?InvokeAsync@?$consume_WindowsUdk_UI_IMenuItem@UIMenuItem@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_IMenuItem<winrt::WindowsUdk::UI::IMenuItem>::InvokeAsync(void)
0x180157c39  nop
0x180157c3a  lea     rdx, [rsp+128h+var_80]
0x180157c42  lea     rcx, [rsp+128h+var_C0]
0x180157c47  call    ??$get_begin_iterator@U?$IMapView@Uguid@winrt@@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@2@@Collections@Foundation@Windows@winrt@@$0A@@impl@winrt@@YA?AU?$IIterator@U?$IKeyValuePair@Uguid@winrt@@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@1@AEBU?$IMapView@Uguid@winrt@@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@2@@3451@@Z; winrt::impl::get_begin_iterator<winrt::Windows::Foundation::Collections::IMapView<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>,0>(winrt::Windows::Foundation::Collections::IMapView<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile> const &)
0x180157c4c  nop
0x180157c4d  mov     [rsp+128h+var_88], rsi
0x180157c55  lea     r13, aPinnedtileslot; "PinnedTileSlot"
0x180157c5c  lea     rdx, [rsp+128h+var_88]
0x180157c64  lea     rcx, [rsp+128h+var_C0]
0x180157c69  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180157c6e  test    al, al
0x180157c70  jnz     loc_180157F2D
0x180157c76  lea     rdx, [rsp+128h+var_C8]
0x180157c7b  lea     rcx, [rsp+128h+var_C0]
0x180157c80  call    ??D?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@U?$IKeyValuePair@Uguid@winrt@@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@winrt@@U?$IKeyValuePair@Uguid@winrt@@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@2@@2345@@impl@winrt@@QEBA?AU?$IKeyValuePair@Uguid@winrt@@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@2@@Collections@Foundation@Windows@2@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>>::operator*(void)
0x180157c85  nop
0x180157c86  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55707948@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55707948@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948> `wil::Feature<__WilFeatureTraits_Feature_55707948>::GetImpl(void)'::`2'::impl
0x180157c8d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55707948@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948>::__private_IsEnabled(void)
0x180157c92  lea     rcx, [rsp+128h+var_C8]
0x180157c97  test    al, al
0x180157c99  jz      loc_180157E6B
0x180157c9f  lea     rdx, [rsp+128h+var_E0]
0x180157ca4  call    ?Value@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uguid@winrt@@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@2@@Collections@Foundation@Windows@winrt@@Uguid@5@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>,winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>::Value(void)
0x180157ca9  nop
0x180157caa  mov     rdx, r13; unsigned __int16 *
0x180157cad  lea     rcx, [rsp+128h+var_50]; this
0x180157cb5  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180157cba  lea     rdx, [rsp+128h+var_50]
0x180157cc2  lea     rcx, [rsp+128h+var_E0]
0x180157cc7  call    ?HasCustomProperty@?$consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTile@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTile<winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>::HasCustomProperty(winrt::param::hstring const &)
0x180157ccc  test    al, al
0x180157cce  jz      loc_180157E61
0x180157cd4  mov     rdx, r13; unsigned __int16 *
0x180157cd7  lea     rcx, [rsp+128h+var_70]; this
0x180157cdf  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180157ce4  lea     r8, [rsp+128h+var_70]
0x180157cec  lea     rdx, [rsp+128h+var_A0]
0x180157cf4  lea     rcx, [rsp+128h+var_E0]
0x180157cf9  call    ?GetCustomProperty@?$consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTile@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTile<winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>::GetCustomProperty(winrt::param::hstring const &)
0x180157cfe  nop
0x180157cff  mov     rcx, rax; this
0x180157d02  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180157d07  mov     rdx, rax
0x180157d0a  lea     rcx, [rsp+128h+var_50]
0x180157d12  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180157d17  nop
0x180157d18  lea     rcx, [rsp+128h+var_50]
0x180157d20  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x180157d25  mov     ebx, eax
0x180157d27  lea     rcx, [rsp+128h+var_50]
0x180157d2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157d34  nop
0x180157d35  lea     rcx, [rsp+128h+var_A0]
0x180157d3d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180157d42  cmp     ebx, 10000h
0x180157d48  jnz     loc_180157E61
0x180157d4e  mov     byte ptr [rdi], 1
0x180157d51  lea     rdx, [rsp+128h+var_90]
0x180157d59  lea     rcx, [rsp+128h+var_E0]
0x180157d5e  call    ?DisplayInfo@?$consume_Windows_ApplicationModel_Core_IAppListEntry@UIAppListEntry@Core@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_Core_IAppListEntry<winrt::Windows::ApplicationModel::Core::IAppListEntry>::DisplayInfo(void)
0x180157d63  nop
0x180157d64  lea     rdx, [rsp+128h+var_98]
0x180157d6c  lea     rcx, [rsp+128h+var_90]
0x180157d74  call    ??$as@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x180157d79  nop
0x180157d7a  lea     rdx, [rsp+128h+var_A8]
0x180157d82  mov     rcx, rax
0x180157d85  call    ?DisplayInfo@?$consume_Windows_ApplicationModel_Core_IAppListEntry@UIAppListEntry@Core@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_Core_IAppListEntry<winrt::Windows::ApplicationModel::Core::IAppListEntry>::DisplayInfo(void)
0x180157d8a  nop
0x180157d8b  lea     rcx, [rsp+128h+var_98]; this
0x180157d93  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180157d98  lea     rcx, [rsp+128h+var_A8]; this
0x180157da0  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180157da5  mov     rcx, rax; lpString1
0x180157da8  mov     dword ptr [rsp+128h+pdwType], 1; bIgnoreCase
0x180157db0  or      ebx, 0FFFFFFFFh
0x180157db3  mov     r9d, ebx; cchCount2
0x180157db6  lea     r8, aMicrosoftwindo_3; "MicrosoftWindows.Dashboard_cw5n1h2txyew"...
0x180157dbd  mov     edx, ebx; cchCount1
0x180157dbf  call    cs:__imp_CompareStringOrdinal
0x180157dc6  nop     dword ptr [rax+rax+00h]
0x180157dcb  cmp     eax, 2
0x180157dce  jz      short loc_180157E19
0x180157dd0  lea     rcx, [rsp+128h+var_A8]; this
0x180157dd8  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180157ddd  mov     rcx, rax; lpString1
0x180157de0  mov     dword ptr [rsp+128h+pdwType], 1; bIgnoreCase
0x180157de8  mov     r9d, ebx; cchCount2
0x180157deb  lea     r8, aMicrosoftwindo_1; "MicrosoftWindows.Client.WebExperience_c"...
0x180157df2  mov     edx, ebx; cchCount1
0x180157df4  call    cs:__imp_CompareStringOrdinal
0x180157dfb  nop     dword ptr [rax+rax+00h]
0x180157e00  cmp     eax, 2
0x180157e03  jz      short loc_180157E19
0x180157e05  mov     [rsp+128h+var_E8], 2
0x180157e0d  lea     r9, [rsp+128h+var_E8]
0x180157e12  call    ??$set_value@K@reg@wil@@YAXPEAUHKEY__@@PEBG1AEBK@Z; wil::reg::set_value<ulong>(HKEY__ *,ushort const *,ushort const *,ulong const &)
0x180157e17  jmp     short loc_180157E45
0x180157e19  mov     [rsp+128h+var_E8], 1
0x180157e21  lea     r9, [rsp+128h+var_E8]
0x180157e26  call    ??$set_value@K@reg@wil@@YAXPEAUHKEY__@@PEBG1AEBK@Z; wil::reg::set_value<ulong>(HKEY__ *,ushort const *,ushort const *,ulong const &)
0x180157e2b  mov     [rsp+128h+var_E8], 1
0x180157e33  lea     r9, [rsp+128h+var_E8]
0x180157e38  lea     r8, aLockscreenwidg_4; "LockScreenWidgetsSystemCurationEnabled"
0x180157e3f  call    ??$set_value@H@reg@wil@@YAXPEAUHKEY__@@PEBG1AEBH@Z; wil::reg::set_value<int>(HKEY__ *,ushort const *,ushort const *,int const &)
0x180157e44  nop
0x180157e45  lea     rcx, [rsp+128h+var_A8]
0x180157e4d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180157e52  nop
0x180157e53  lea     rcx, [rsp+128h+var_90]; this
0x180157e5b  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180157e60  nop
0x180157e61  lea     rcx, [rsp+128h+var_E0]
0x180157e66  jmp     loc_1801580E2
0x180157e6b  lea     rdx, [rsp+128h+var_D0]
0x180157e70  call    ?Value@?$consume_Windows_Foundation_Collections_IKeyValuePair@U?$IKeyValuePair@Uguid@winrt@@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@2@@Collections@Foundation@Windows@winrt@@Uguid@5@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IKeyValuePair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>,winrt::guid,winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>::Value(void)
0x180157e75  nop
0x180157e76  mov     rdx, r13; unsigned __int16 *
0x180157e79  lea     rcx, [rsp+128h+var_70]; this
0x180157e81  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180157e86  lea     rdx, [rsp+128h+var_70]
0x180157e8e  lea     rcx, [rsp+128h+var_D0]
0x180157e93  call    ?HasCustomProperty@?$consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTile@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTile<winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>::HasCustomProperty(winrt::param::hstring const &)
0x180157e98  test    al, al
0x180157e9a  jz      loc_1801580DD
0x180157ea0  mov     rdx, r13; unsigned __int16 *
0x180157ea3  lea     rcx, [rsp+128h+var_70]; this
0x180157eab  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180157eb0  lea     r8, [rsp+128h+var_70]
0x180157eb8  lea     rdx, [rsp+128h+var_D8]
0x180157ebd  lea     rcx, [rsp+128h+var_D0]
0x180157ec2  call    ?GetCustomProperty@?$consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTile@UICuratedTile@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_ICuratedTile<winrt::WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTile>::GetCustomProperty(winrt::param::hstring const &)
0x180157ec7  nop
0x180157ec8  mov     rcx, rax; this
0x180157ecb  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x180157ed0  mov     rdx, rax
0x180157ed3  lea     rcx, [rsp+128h+var_50]
0x180157edb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180157ee0  nop
0x180157ee1  lea     rcx, [rsp+128h+var_50]
0x180157ee9  call    ?stoi@std@@YAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x180157eee  mov     ebx, eax
0x180157ef0  lea     rcx, [rsp+128h+var_50]
0x180157ef8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180157efd  nop
0x180157efe  lea     rcx, [rsp+128h+var_D8]
0x180157f03  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180157f08  cmp     ebx, 10000h
0x180157f0e  jnz     loc_1801580DD
0x180157f14  mov     byte ptr [rdi], 1
0x180157f17  lea     rcx, [rsp+128h+var_D0]; this
0x180157f1c  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180157f21  nop
0x180157f22  lea     rcx, [rsp+128h+var_C8]; this
0x180157f27  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180157f2c  nop
0x180157f2d  lea     rcx, [rsp+128h+var_88]; this
0x180157f35  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180157f3a  nop
0x180157f3b  lea     rcx, [rsp+128h+var_C0]; this
0x180157f40  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x180157f45  mov     dword ptr [rsp+128h+pvData], r12d; cbData
0x180157f4a  lea     rax, [rsp+128h+var_E4]
0x180157f4f  mov     [rsp+128h+pdwType], rax; pvData
0x180157f54  mov     r9d, r12d; dwType
0x180157f57  lea     r8, aHasmigrateddet; "HasMigratedDetailedStatus"
0x180157f5e  mov     rdx, r15; pszSubKey
0x180157f61  mov     rcx, r14; hkey
0x180157f64  call    cs:__imp_SHSetValueW
0x180157f6b  nop     dword ptr [rax+rax+00h]
0x180157f70  mov     rcx, rdi
0x180157f73  call    ??$LockScreenWidgetMigrateDetailStatusCompleted@AEA_N@PersonalizeSettingsTelemetry@@SAXAEA_N@Z; PersonalizeSettingsTelemetry::LockScreenWidgetMigrateDetailStatusCompleted<bool &>(bool &)
0x180157f78  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57383290@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57383290@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57383290> `wil::Feature<__WilFeatureTraits_Feature_57383290>::GetImpl(void)'::`2'::impl
0x180157f7f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57383290@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57383290>::__private_IsEnabled(void)
0x180157f84  test    al, al
0x180157f86  jnz     short loc_180157F98
0x180157f88  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55707948@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55707948@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948> `wil::Feature<__WilFeatureTraits_Feature_55707948>::GetImpl(void)'::`2'::impl
0x180157f8f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55707948@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55707948>::__private_IsEnabled(void)
0x180157f94  test    al, al
0x180157f96  jz      short loc_180157FB6
0x180157f98  mov     eax, esi
  ... truncated ...
```
