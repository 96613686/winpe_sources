# SystemSettings::PenSettings::DevicesPenSetActionBase::GetValue(IInspectable * *)

- ea: `0x180028910`
- end: `0x180029579`
- name: `?GetValue@DevicesPenSetActionBase@PenSettings@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `3177`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::DevicesPenSetActionBase *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `42`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18000a2bc`
- `0x18001033c`
- `0x180012868`
- `0x180014710`
- `0x180019fcc`
- `0x18001a378`
- `0x18001bb34`
- `0x18001da60`
- `0x18001dcf8`
- `0x180020780`
- `0x180021a44`
- `0x180022654`
- `0x18002668c`
- `0x18002674c`
- `0x1800271d0`
- `0x180027dcc`
- `0x180028910`
- `0x18002bb6c`
- `0x18002bbb0`
- `0x18002c00c`
- `0x18002c14c`
- `0x18002c190`
- `0x18002c1d0`
- `0x18002c3c8`
- `0x18002c44c`
- `0x18002c580`
- `0x18002cc6c`
- `0x18002efa4`
- `0x18002efec`
- `0x18002f090`
- `0x18003149c`
- `0x180031514`
- `0x180032104`
- `0x1800515d4`
- `0x1800525c4`
- `0x180052dc4`
- `0x180052eec`
- `0x180054394`
- `0x1800543f4`
- `0x1800550e0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029034`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800290a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800290fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029034`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800290a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800290fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028ff6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029329`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028ff6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029329`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180029051`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002907d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800290bd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800292b2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800292d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180029051`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002907d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800290bd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800292b2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800292d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028c7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028c7c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028cb6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028cb6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028ccc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180028ccc`

## string_xrefs

- `0x1800293d0`: `SystemSettings_Devices_Pen_ButtonCustomization_ActionType_OemOverride`
- `0x180028e19`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180028f0e`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x1800293a1`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180029476`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::PenSettings::DevicesPenSetActionBase::GetValue(
        SystemSettings::PenSettings::DevicesPenSetActionBase *this,
        struct IInspectable **a2)
{
  bool IsOneNoteDesktopInstalled; // r14
  const unsigned __int16 *v4; // r15
  SystemSettings::PenSettings *v5; // rcx
  const WCHAR *v6; // rax
  const unsigned __int16 *v7; // rdx
  SystemSettings::PenSettings *v8; // rax
  const unsigned __int16 *v9; // rdx
  unsigned int v10; // edi
  const wchar_t *v11; // rbx
  bool IsDesktop; // al
  _DWORD **v13; // r13
  AIXPolicyHelper *v14; // rcx
  unsigned int v15; // eax
  HKEY v16; // rcx
  AIXPolicyHelper *v17; // rcx
  HKEY v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // r9d
  bool v21; // r14
  _DWORD *i; // rax
  LSTATUS v23; // eax
  bool v24; // sf
  __int64 v25; // rcx
  unsigned __int16 *v26; // r14
  const wchar_t *v27; // rcx
  HKEY v28; // rcx
  const unsigned __int16 *v29; // rax
  int v30; // eax
  unsigned int ResourceStringValue; // ebx
  struct SystemSettings::PenSettings::PenButtonCustomizationSingleton *v32; // rax
  __int128 *v33; // rcx
  const unsigned __int16 *v35; // rax
  int String; // eax
  struct SystemSettings::PenSettings::PenButtonCustomizationSingleton *Instance; // rax
  SystemSettings::PenSettings *v38; // rcx
  SystemSettings::PenSettings *v39; // rcx
  int (__fastcall *v40)(SystemSettings::PenSettings::DevicesPenSetActionBase *, LPCWSTR *); // rbx
  AIXPolicyHelper *v41; // rcx
  const WCHAR *v42; // rax
  const WCHAR *v43; // rax
  const WCHAR *v44; // rax
  const WCHAR *StringRawBuffer; // rbx
  SystemSettings::PenSettings *v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rdx
  int v51; // ebx
  struct IInspectable **v52; // r8
  const unsigned __int16 *v53; // rax
  struct IInspectable **v54; // r15
  int v55; // eax
  char v56; // bl
  struct SystemSettings::PenSettings::PenButtonCustomizationSingleton *v57; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  bool v59; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v61; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 length[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v63; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v64; // [rsp+58h] [rbp-A8h] BYREF
  struct IInspectable **v65; // [rsp+60h] [rbp-A0h]
  _DWORD **v66; // [rsp+68h] [rbp-98h] BYREF
  __int128 v67; // [rsp+70h] [rbp-90h] BYREF
  __m128i si128; // [rsp+80h] [rbp-80h]
  _BYTE v69[16]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h]
  _BYTE v71[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v72[32]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v73[28]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR String2[56]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v65 = a2;
  *a2 = 0;
  SystemSettings::PenSettings::PenSettingsCacheSingleton::EnsureActionValueInitialized(*((unsigned int *)this + 68));
  lpSubKey = 0;
  v63 = 0;
  v66 = 0;
  v64 = 0;
  *(_QWORD *)length = 0;
  SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(
    *((_DWORD *)this + 68),
    (unsigned int)&lpSubKey,
    (unsigned int)&v63,
    (unsigned int)&v66,
    (__int64)&v64,
    (__int64)length);
  IsOneNoteDesktopInstalled = SystemSettings::PenSettings::ActionTypeOptionManager::IsOneNoteDesktopInstalled();
  v61 = -1;
  v4 = lpSubKey;
  if ( (int)SHRegGetDWORD(HKEY_CURRENT_USER, lpSubKey, L"Override", &v61) < 0
    && !SystemSettings::PenSettings::IsDesktop(v5) )
  {
    std::wstring::wstring(&v67, v64);
    SystemSettings::PenSettings::GetOemPolicyValue(v69, &v67);
    std::wstring::_Tidy_deallocate(&v67);
    std::wstring::wstring(v72, *(_QWORD *)length);
    SystemSettings::PenSettings::GetOemPolicyValue(v71, v72);
    std::wstring::_Tidy_deallocate(v72);
    if ( v70
      && (v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69),
          SystemSettings::PenSettings::IsOemAumidAlreadyDisplayed(v6, v7))
      && (v8 = (SystemSettings::PenSettings *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v71),
          SystemSettings::PenSettings::IsOemUriAlreadyDisplayed(v8, v9)) )
    {
      v61 = 12;
    }
    else
    {
      SHRegGetDWORD(HKEY_LOCAL_MACHINE, v4, L"Override", &v61);
    }
    std::wstring::_Tidy_deallocate(v71);
    std::wstring::_Tidy_deallocate(v69);
  }
  v10 = v61;
  v11 = L"SystemSettings_Devices_Pen_ButtonCustomization_ActionType_NoneSelected";
  if ( v61 == -1 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl) )
      goto LABEL_109;
    v10 = 4 * SystemSettings::PenSettings::IsDesktop(v38) + 1;
    if ( !SystemSettings::PenSettings::IsDesktop(v39) )
      goto LABEL_109;
    lpSubKey = 0;
    v40 = *(int (__fastcall **)(SystemSettings::PenSettings::DevicesPenSetActionBase *, LPCWSTR *))(*(_QWORD *)this
                                                                                                  + 48LL);
    WindowsDeleteString(0);
    lpSubKey = 0;
    if ( v40(this, &lpSubKey) < 0 )
    {
LABEL_108:
      SHRegSetDWORD((HKEY)v41, v4, L"Override", v10);
      SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionCache(*((unsigned int *)this + 68), v10);
      WindowsDeleteString((HSTRING)lpSubKey);
      v11 = L"SystemSettings_Devices_Pen_ButtonCustomization_ActionType_NoneSelected";
LABEL_109:
      v13 = v66;
      v26 = (unsigned __int16 *)SystemSettings::PenSettings::FindResourceTagFromEnum<enum PenClickOverride,SystemSettings::PenSettings::PenActionTypeResourceMapping_>(
                                  v10,
                                  v66);
      goto LABEL_110;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57308850>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID57308850>::GetImpl'::`2'::impl) )
    {
      length[0] = 0;
      StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)lpSubKey, length);
      wcscpy(String2, L"SystemSettings_Devices_Pen_SetPenSingleClickAction");
      wcscpy((wchar_t *)v73, L"SystemSettings_Devices_Pen_SetPenLongPressAction");
      if ( CompareStringOrdinal(StringRawBuffer, length[0], String2, 50, 0) == 2 )
        goto LABEL_98;
      if ( CompareStringOrdinal(StringRawBuffer, length[0], (LPCWCH)v73, 48, 0) != 2 )
        goto LABEL_99;
      if ( !SystemSettings::PenSettings::ActionTypeOptionManager::IsCopilotInstalled() )
      {
LABEL_98:
        v10 = IsOneNoteDesktopInstalled ? 13 : 8;
        goto LABEL_99;
      }
      v10 = 16;
    }
    else
    {
      v42 = WindowsGetStringRawBuffer((HSTRING)lpSubKey, 0);
      if ( CompareStringOrdinal(v42, -1, L"SystemSettings_Devices_Pen_SetPenSingleClickAction", -1, 0) == 2 )
        goto LABEL_98;
      v43 = WindowsGetStringRawBuffer((HSTRING)lpSubKey, 0);
      if ( CompareStringOrdinal(v43, -1, L"SystemSettings_Devices_Pen_SetPenLongPressAction", -1, 0) == 2 )
        goto LABEL_98;
    }
LABEL_99:
    v44 = WindowsGetStringRawBuffer((HSTRING)lpSubKey, 0);
    if ( CompareStringOrdinal(v44, -1, L"SystemSettings_Devices_Pen_SetPenDoubleClickAction", -1, 0) == 2 )
    {
      if ( !AIXPolicyHelper::IsC2DAllowedOnDeviceByPolicy(v41) || AIXPolicyHelper::IsC2DDisabledByUserSetting(v41) )
        v10 = IsOneNoteDesktopInstalled + 5;
      else
        v10 = 14;
    }
    goto LABEL_108;
  }
  IsDesktop = SystemSettings::PenSettings::IsDesktop(v5);
  v13 = v66;
  if ( !IsDesktop )
    goto LABEL_55;
  v59 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl) )
  {
    v15 = 0;
    if ( v10 != 4 )
      v15 = v10;
    v10 = v15;
    if ( v15 == 6 || v15 == 13 )
      v10 = IsOneNoteDesktopInstalled ? v15 : 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57308850>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID57308850>::GetImpl'::`2'::impl)
      && v10 == 15 )
    {
      if ( !SystemSettings::PenSettings::ActionTypeOptionManager::IsCopilotInstalled() )
        v10 = 0;
      goto LABEL_31;
    }
    if ( v10 == 5 )
    {
      length[0] = -1;
      SHRegGetDWORD(HKEY_CURRENT_USER, v4, L"PenWorkspaceVerb", length);
      if ( length[0] == 1 )
      {
        v10 = 11;
      }
      else
      {
        SHRegSetDWORD(v16, v4, L"PenWorkspaceVerb", 0);
        SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCachePenWorkspace(
          *((unsigned int *)this + 68),
          0);
      }
      goto LABEL_31;
    }
  }
  if ( v10 == 14
    && (!AIXPolicyHelper::IsC2DAllowedOnDeviceByPolicy(v14) || AIXPolicyHelper::IsC2DDisabledByUserSetting(v17)) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl) )
    {
      v10 = -1;
      v59 = 1;
    }
    else
    {
      v10 = 6;
    }
  }
LABEL_31:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl) )
    goto LABEL_55;
  if ( !SystemSettings::PenSettings::DevicesPenSetActionBase::IsActionMigrated(v4) )
  {
    v19 = SystemSettings::PenSettings::DevicesPenSetActionBase::MigrateLegacyAction(v10, v4);
    if ( v19 != v10 )
      v10 = v19;
  }
  if ( v10 == 2 )
  {
    v20 = 0;
LABEL_37:
    v21 = 1;
    v10 = 18;
    SHRegSetDWORD(v18, v4, L"AppType", v20);
    goto LABEL_41;
  }
  if ( v10 == 3 )
  {
    v20 = 1;
    goto LABEL_37;
  }
  v21 = v59;
LABEL_41:
  for ( i = *v13; i != v13[1]; i += 4 )
  {
    if ( *i == v10 )
      goto LABEL_47;
  }
  if ( v10 != 18 )
  {
    v10 = -1;
    goto LABEL_48;
  }
LABEL_47:
  if ( !v21 )
    goto LABEL_49;
LABEL_48:
  SHRegSetDWORD(v18, v4, L"Override", v10);
  SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionCache(*((unsigned int *)this + 68), v10);
LABEL_49:
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  v23 = RegOpenKeyExW(HKEY_CURRENT_USER, v4, 0, 3u, (PHKEY)&lpSubKey);
  v24 = v23 < 0;
  if ( v23 > 0 )
    v24 = 1;
  if ( !v24 && !RegQueryValueExW((HKEY)lpSubKey, L"PenWorkspaceVerb", 0, 0, 0, 0) )
    RegDeleteValueW((HKEY)lpSubKey, L"PenWorkspaceVerb");
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&lpSubKey);
LABEL_55:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl) )
  {
    if ( v10 == 9
      && (v59 = 1,
          SystemSettings::PenSettings::ActionTypeOptionManager::CheckIfPackageIsInstalled(
            L"Microsoft.Whiteboard_8wekyb3d8bbwe",
            &v59),
          !v59)
      || v10 == 10
      && (v59 = 1,
          SystemSettings::PenSettings::ActionTypeOptionManager::CheckIfPackageIsInstalled(
            L"Microsoft.Office.OneNote_8wekyb3d8bbwe",
            &v59),
          !v59) )
    {
      v10 = 8;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl)
    || v10
    || !(unsigned int)SHRegSubKeyExistsW(v25, v63) )
  {
    v26 = (unsigned __int16 *)SystemSettings::PenSettings::FindResourceTagFromEnum<enum PenClickOverride,SystemSettings::PenSettings::PenActionTypeResourceMapping_>(
                                v10,
                                v13);
  }
  else
  {
    v26 = L"SystemSettings_Devices_Pen_ButtonCustomization_ActionType_DeviceDefault";
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl) )
  {
    v27 = L"SystemSettings_Devices_Pen_ButtonCustomization_ActionType_NoneSelected";
    if ( v10 != -1 )
      v27 = v26;
    v26 = (unsigned __int16 *)v27;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl)
    && v10 == 18 )
  {
    length[0] = 0;
    SHRegGetDWORD(HKEY_CURRENT_USER, v4, L"AppType", length);
    if ( length[0] )
    {
      SystemSettings::PenSettings::DevicesPenSetActionBase::GetCustomDesktopAppDisplayName(this, &v67);
      if ( si128.m128i_i64[0] && SystemSettings::PenSettings::DevicesPenSetActionBase::IsCustomDesktopAppAvailable(this) )
      {
        v35 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v67);
        String = SystemSettings::DataModel::PropValueHelper::CreateString(v35, v65);
        ResourceStringValue = String;
        if ( String < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x668,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
            (const char *)(unsigned int)String,
            phkResult);
          goto LABEL_80;
        }
        if ( !*((_BYTE *)this + 280) )
        {
          *((_DWORD *)this + 69) = 18;
          LODWORD(v63) = *((_DWORD *)this + 68);
          HIDWORD(v63) = 18;
          Instance = SystemSettings::PenSettings::PenButtonCustomizationSingleton::GetInstance();
          v64 = &v63;
          SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenGestureActionChangedEventArgs>::_Notify<_lambda_6640fc61c1b66f34ece762adb396642f_>(
            Instance,
            &v64);
          *((_BYTE *)this + 280) = 1;
        }
        goto LABEL_79;
      }
    }
    else
    {
      SystemSettings::PenSettings::DevicesPenSetActionBase::SetAppsList(this);
      SystemSettings::PenSettings::DevicesPenSetActionBase::GetCustomAppDisplayName(this, &v67);
      if ( si128.m128i_i64[0] && SystemSettings::PenSettings::DevicesPenSetActionBase::IsCustomAppAvailable(this) )
      {
        v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v67);
        v30 = SystemSettings::DataModel::PropValueHelper::CreateString(v29, v65);
        ResourceStringValue = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x64B,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
            (const char *)(unsigned int)v30,
            phkResult);
LABEL_80:
          v33 = &v67;
LABEL_81:
          std::wstring::_Tidy_deallocate(v33);
          return ResourceStringValue;
        }
        if ( !*((_BYTE *)this + 280) )
        {
          *((_DWORD *)this + 69) = 18;
          LODWORD(v63) = *((_DWORD *)this + 68);
          HIDWORD(v63) = 18;
          v32 = SystemSettings::PenSettings::PenButtonCustomizationSingleton::GetInstance();
          v64 = &v63;
          SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenGestureActionChangedEventArgs>::_Notify<_lambda_6640fc61c1b66f34ece762adb396642f_>(
            v32,
            &v64);
          *((_BYTE *)this + 280) = 1;
        }
LABEL_79:
        SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionCache(*((unsigned int *)this + 68), v61);
        ResourceStringValue = 0;
        goto LABEL_80;
      }
    }
    v10 = -1;
    SHRegSetDWORD(v28, v4, L"Override", 0xFFFFFFFF);
    SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionCache(
      *((unsigned int *)this + 68),
      0xFFFFFFFFLL);
    v26 = L"SystemSettings_Devices_Pen_ButtonCustomization_ActionType_NoneSelected";
    std::wstring::_Tidy_deallocate(&v67);
  }
LABEL_110:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl'::`2'::impl) )
  {
    if ( v10 != -1 )
      v11 = v26;
    v26 = (unsigned __int16 *)v11;
  }
  if ( !SystemSettings::PenSettings::IsDesktop(v46) )
  {
    if ( v26 && SystemSettings::PenSettings::ActionTypeOptionManager::IsActionValid(v26) )
      goto LABEL_122;
    v26 = (unsigned __int16 *)SystemSettings::PenSettings::FindResourceTagFromEnum<enum PenClickOverride,SystemSettings::PenSettings::PenActionTypeResourceMapping_>(
                                1,
                                v13);
  }
  if ( !v26 )
  {
    v47 = 1761;
LABEL_120:
    ResourceStringValue = -2147418113;
LABEL_121:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v47,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
      (const char *)ResourceStringValue,
      phkResult);
    return ResourceStringValue;
  }
LABEL_122:
  v48 = std::wstring::wstring(v71, v26);
  v49 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v48);
  v51 = std::_Traits_compare<std::char_traits<unsigned short>>(
          v49,
          v50,
          L"SystemSettings_Devices_Pen_ButtonCustomization_ActionType_OemOverride",
          69);
  std::wstring::_Tidy_deallocate(v71);
  if ( v51 )
  {
    v54 = v65;
  }
  else
  {
    std::wstring::wstring(v71, v64);
    SystemSettings::PenSettings::GetOemPolicyValue(v69, v71);
    std::wstring::_Tidy_deallocate(v71);
    v67 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v67) = 0;
    if ( v70 && (int)SystemSettings::PenSettings::GetAppDisplayNameByAumid(v69, &v67) >= 0 )
    {
      v53 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v67);
      v54 = v65;
      v55 = SystemSettings::DataModel::PropValueHelper::CreateString(v53, v65);
      ResourceStringValue = v55;
      if ( v55 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6EA,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
          (const char *)(unsigned int)v55,
          phkResult);
        std::wstring::_Tidy_deallocate(&v67);
        v33 = (__int128 *)v69;
        goto LABEL_81;
      }
      v56 = 1;
    }
    else
    {
      v56 = 0;
      v26 = (unsigned __int16 *)SystemSettings::PenSettings::FindResourceTagFromEnum<enum PenClickOverride,SystemSettings::PenSettings::PenActionTypeResourceMapping_>(
                                  1,
                                  v13);
      v54 = v65;
    }
    std::wstring::_Tidy_deallocate(&v67);
    std::wstring::_Tidy_deallocate(v69);
    if ( v56 )
      goto LABEL_135;
    if ( !v26 )
    {
      v47 = 1781;
      goto LABEL_120;
    }
  }
  ResourceStringValue = SystemSettings::DataModel::GetResourceStringValue((SystemSettings::DataModel *)v26, v54, v52);
  if ( (ResourceStringValue & 0x80000000) != 0 )
  {
    v47 = 1782;
    goto LABEL_121;
  }
LABEL_135:
  if ( !*((_BYTE *)this + 280) )
  {
    *((_DWORD *)this + 69) = v10;
    LODWORD(v63) = *((_DWORD *)this + 68);
    HIDWORD(v63) = v10;
    v57 = SystemSettings::PenSettings::PenButtonCustomizationSingleton::GetInstance();
    v64 = &v63;
    SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenGestureActionChangedEventArgs>::_Notify<_lambda_6640fc61c1b66f34ece762adb396642f_>(
      v57,
      &v64);
    *((_BYTE *)this + 280) = 1;
  }
  SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionCache(*((unsigned int *)this + 68), v61);
  return 0;
}

```

## disassembly

```asm
0x180028910  mov     [rsp-8+arg_10], rbx
0x180028915  push    rbp
0x180028916  push    rsi
0x180028917  push    rdi
0x180028918  push    r12
0x18002891a  push    r13
0x18002891c  push    r14
0x18002891e  push    r15
0x180028920  lea     rbp, [rsp-0E0h]
0x180028928  sub     rsp, 1E0h
0x18002892f  mov     rax, cs:__security_cookie
0x180028936  xor     rax, rsp
0x180028939  mov     [rbp+110h+var_40], rax
0x180028940  mov     [rsp+210h+var_1B0], rdx
0x180028945  mov     rsi, rcx
0x180028948  xor     r13d, r13d
0x18002894b  mov     [rdx], r13
0x18002894e  mov     ecx, [rcx+110h]
0x180028954  call    ?EnsureActionValueInitialized@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::EnsureActionValueInitialized(PenClickType)
0x180028959  mov     [rsp+210h+lpSubKey], r13
0x18002895e  mov     [rsp+210h+var_1C0], r13
0x180028963  mov     [rsp+210h+var_1A8], r13
0x180028968  mov     [rsp+210h+var_1B8], r13
0x18002896d  mov     qword ptr [rsp+210h+length], r13
0x180028972  lea     rax, [rsp+210h+length]
0x180028977  mov     [rsp+210h+lpcbData], rax
0x18002897c  lea     rax, [rsp+210h+var_1B8]
0x180028981  mov     [rsp+210h+phkResult], rax
0x180028986  lea     r9, [rsp+210h+var_1A8]
0x18002898b  lea     r8, [rsp+210h+var_1C0]
0x180028990  lea     rdx, [rsp+210h+lpSubKey]
0x180028995  mov     ecx, [rsi+110h]
0x18002899b  call    ?GetPrimitiveSpecificParameters@ActionTypeOptionManager@PenSettings@SystemSettings@@SAXW4PenClickType@@PEAPEBG1PEAPEAV?$vector@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@V?$allocator@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@@std@@@std@@11@Z; SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(PenClickType,ushort const * *,ushort const * *,std::vector<SystemSettings::PenSettings::PenActionTypeResourceMapping_> * *,ushort const * *,ushort const * *)
0x1800289a0  call    ?IsOneNoteDesktopInstalled@ActionTypeOptionManager@PenSettings@SystemSettings@@SA_NXZ; SystemSettings::PenSettings::ActionTypeOptionManager::IsOneNoteDesktopInstalled(void)
0x1800289a5  mov     r14b, al
0x1800289a8  mov     [rsp+210h+var_1D0], 0FFFFFFFFh
0x1800289b0  lea     r9, [rsp+210h+var_1D0]; unsigned int *
0x1800289b5  lea     r8, aOverride; "Override"
0x1800289bc  mov     r15, [rsp+210h+lpSubKey]
0x1800289c1  mov     rdx, r15; unsigned __int16 *
0x1800289c4  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800289cb  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800289d0  test    eax, eax
0x1800289d2  jns     loc_180028A9C
0x1800289d8  call    ?IsDesktop@PenSettings@SystemSettings@@YA_NXZ; SystemSettings::PenSettings::IsDesktop(void)
0x1800289dd  test    al, al
0x1800289df  jnz     loc_180028A9C
0x1800289e5  mov     rdx, [rsp+210h+var_1B8]
0x1800289ea  lea     rcx, [rsp+210h+var_1A0]
0x1800289ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800289f4  nop
0x1800289f5  lea     rdx, [rsp+210h+var_1A0]
0x1800289fa  lea     rcx, [rbp+110h+var_180]
0x1800289fe  call    ?GetOemPolicyValue@PenSettings@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; SystemSettings::PenSettings::GetOemPolicyValue(std::wstring const &)
0x180028a03  nop
0x180028a04  lea     rcx, [rsp+210h+var_1A0]
0x180028a09  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028a0e  mov     rdx, qword ptr [rsp+210h+length]
0x180028a13  lea     rcx, [rbp+110h+var_140]
0x180028a17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028a1c  nop
0x180028a1d  lea     rdx, [rbp+110h+var_140]
0x180028a21  lea     rcx, [rbp+110h+var_160]
0x180028a25  call    ?GetOemPolicyValue@PenSettings@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; SystemSettings::PenSettings::GetOemPolicyValue(std::wstring const &)
0x180028a2a  nop
0x180028a2b  lea     rcx, [rbp+110h+var_140]
0x180028a2f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028a34  cmp     [rbp+110h+var_170], r13
0x180028a38  jz      short loc_180028A6E
0x180028a3a  lea     rcx, [rbp+110h+var_180]
0x180028a3e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180028a43  mov     rcx, rax; lpString1
0x180028a46  call    ?IsOemAumidAlreadyDisplayed@PenSettings@SystemSettings@@YA_NPEBG@Z; SystemSettings::PenSettings::IsOemAumidAlreadyDisplayed(ushort const *)
0x180028a4b  test    al, al
0x180028a4d  jz      short loc_180028A6E
0x180028a4f  lea     rcx, [rbp+110h+var_160]
0x180028a53  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180028a58  mov     rcx, rax; this
0x180028a5b  call    ?IsOemUriAlreadyDisplayed@PenSettings@SystemSettings@@YA_NPEBG@Z; SystemSettings::PenSettings::IsOemUriAlreadyDisplayed(ushort const *)
0x180028a60  test    al, al
0x180028a62  jz      short loc_180028A6E
0x180028a64  mov     [rsp+210h+var_1D0], 0Ch
0x180028a6c  jmp     short loc_180028A89
0x180028a6e  lea     r9, [rsp+210h+var_1D0]; unsigned int *
0x180028a73  lea     r8, aOverride; "Override"
0x180028a7a  mov     rdx, r15; unsigned __int16 *
0x180028a7d  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180028a84  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180028a89  lea     rcx, [rbp+110h+var_160]
0x180028a8d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028a92  nop
0x180028a93  lea     rcx, [rbp+110h+var_180]
0x180028a97  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028a9c  mov     edi, [rsp+210h+var_1D0]
0x180028aa0  lea     rbx, aSystemsettings_19; "SystemSettings_Devices_Pen_ButtonCustom"...
0x180028aa7  cmp     edi, 0FFFFFFFFh
0x180028aaa  jz      loc_180028FB5
0x180028ab0  call    ?IsDesktop@PenSettings@SystemSettings@@YA_NXZ; SystemSettings::PenSettings::IsDesktop(void)
0x180028ab5  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization> `wil::Feature<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::GetImpl(void)'::`2'::impl
0x180028abc  mov     r13, [rsp+210h+var_1A8]
0x180028ac1  test    al, al
0x180028ac3  jz      loc_180028CDC
0x180028ac9  xor     al, al
0x180028acb  mov     [rsp+210h+var_1E0], al
0x180028acf  mov     rcx, r12
0x180028ad2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x180028ad7  test    al, al
0x180028ad9  jnz     loc_180028B7A
0x180028adf  xor     eax, eax
0x180028ae1  cmp     edi, 4
0x180028ae4  cmovnz  eax, edi
0x180028ae7  mov     edi, eax
0x180028ae9  cmp     eax, 6
0x180028aec  jz      short loc_180028AF3
0x180028aee  cmp     eax, 0Dh
0x180028af1  jnz     short loc_180028AFA
0x180028af3  neg     r14b
0x180028af6  sbb     eax, eax
0x180028af8  and     edi, eax
0x180028afa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID57308850@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID57308850@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57308850> `wil::Feature<__WilFeatureTraits_Feature_ID57308850>::GetImpl(void)'::`2'::impl
0x180028b01  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID57308850@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57308850>::__private_IsEnabled(void)
0x180028b06  test    al, al
0x180028b08  jz      short loc_180028B23
0x180028b0a  cmp     edi, 0Fh
0x180028b0d  jnz     short loc_180028B23
0x180028b0f  call    ?IsCopilotInstalled@ActionTypeOptionManager@PenSettings@SystemSettings@@SA_NXZ; SystemSettings::PenSettings::ActionTypeOptionManager::IsCopilotInstalled(void)
0x180028b14  test    al, al
0x180028b16  jnz     loc_180028BAC
0x180028b1c  xor     edi, edi
0x180028b1e  jmp     loc_180028BAC
0x180028b23  cmp     edi, 5
0x180028b26  jnz     short loc_180028B7A
0x180028b28  mov     [rsp+210h+length], 0FFFFFFFFh
0x180028b30  lea     r9, [rsp+210h+length]; unsigned int *
0x180028b35  lea     r8, aPenworkspaceve; "PenWorkspaceVerb"
0x180028b3c  mov     rdx, r15; unsigned __int16 *
0x180028b3f  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180028b46  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180028b4b  cmp     [rsp+210h+length], 1
0x180028b50  jnz     short loc_180028B59
0x180028b52  mov     edi, 0Bh
0x180028b57  jmp     short loc_180028BAC
0x180028b59  xor     r9d, r9d; unsigned int
0x180028b5c  lea     r8, aPenworkspaceve; "PenWorkspaceVerb"
0x180028b63  mov     rdx, r15; unsigned __int16 *
0x180028b66  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180028b6b  xor     edx, edx
0x180028b6d  mov     ecx, [rsi+110h]
0x180028b73  call    ?UpdateActionValueCachePenWorkspace@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@K@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCachePenWorkspace(PenClickType,ulong)
0x180028b78  jmp     short loc_180028BAC
0x180028b7a  cmp     edi, 0Eh
0x180028b7d  jnz     short loc_180028BAC
0x180028b7f  call    ?IsC2DAllowedOnDeviceByPolicy@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsC2DAllowedOnDeviceByPolicy(void)
0x180028b84  test    al, al
0x180028b86  jz      short loc_180028B91
0x180028b88  call    ?IsC2DDisabledByUserSetting@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsC2DDisabledByUserSetting(void)
0x180028b8d  test    al, al
0x180028b8f  jz      short loc_180028BAC
0x180028b91  mov     rcx, r12
0x180028b94  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x180028b99  test    al, al
0x180028b9b  jz      short loc_180028BA7
0x180028b9d  or      edi, 0FFFFFFFFh
0x180028ba0  mov     [rsp+210h+var_1E0], 1
0x180028ba5  jmp     short loc_180028BAC
0x180028ba7  mov     edi, 6
0x180028bac  mov     rcx, r12
0x180028baf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x180028bb4  test    al, al
0x180028bb6  jz      loc_180028CDC
0x180028bbc  mov     rcx, r15; unsigned __int16 *
0x180028bbf  call    ?IsActionMigrated@DevicesPenSetActionBase@PenSettings@SystemSettings@@CA_NPEBG@Z; SystemSettings::PenSettings::DevicesPenSetActionBase::IsActionMigrated(ushort const *)
0x180028bc4  test    al, al
0x180028bc6  jnz     short loc_180028BD7
0x180028bc8  mov     rdx, r15
0x180028bcb  mov     ecx, edi
0x180028bcd  call    ?MigrateLegacyAction@DevicesPenSetActionBase@PenSettings@SystemSettings@@CA?AW4PenClickOverride@@W44@PEBG@Z; SystemSettings::PenSettings::DevicesPenSetActionBase::MigrateLegacyAction(PenClickOverride,ushort const *)
0x180028bd2  cmp     eax, edi
0x180028bd4  cmovnz  edi, eax
0x180028bd7  cmp     edi, 2
0x180028bda  jnz     short loc_180028BF8
0x180028bdc  xor     r9d, r9d; unsigned int
0x180028bdf  mov     r14b, 1
0x180028be2  mov     edi, 12h
0x180028be7  lea     r8, aApptype; "AppType"
0x180028bee  mov     rdx, r15; unsigned __int16 *
0x180028bf1  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180028bf6  jmp     short loc_180028C08
0x180028bf8  cmp     edi, 3
0x180028bfb  jnz     short loc_180028C03
0x180028bfd  lea     r9d, [rdi-2]
0x180028c01  jmp     short loc_180028BDF
0x180028c03  mov     r14b, [rsp+210h+var_1E0]
0x180028c08  mov     rax, [r13+0]
0x180028c0c  jmp     short loc_180028C16
0x180028c0e  cmp     [rax], edi
0x180028c10  jz      short loc_180028C26
0x180028c12  add     rax, 10h
0x180028c16  cmp     rax, [r13+8]
0x180028c1a  jnz     short loc_180028C0E
0x180028c1c  cmp     edi, 12h
0x180028c1f  jz      short loc_180028C26
0x180028c21  or      edi, 0FFFFFFFFh
0x180028c24  jmp     short loc_180028C2B
0x180028c26  test    r14b, r14b
0x180028c29  jz      short loc_180028C4A
0x180028c2b  mov     r9d, edi; unsigned int
0x180028c2e  lea     r8, aOverride; "Override"
0x180028c35  mov     rdx, r15; unsigned __int16 *
0x180028c38  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180028c3d  mov     edx, edi
0x180028c3f  mov     ecx, [rsi+110h]
0x180028c45  call    ?UpdateActionCache@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@K@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionCache(PenClickType,ulong)
0x180028c4a  mov     [rsp+210h+lpSubKey], 0
0x180028c53  xor     edx, edx
0x180028c55  lea     rcx, [rsp+210h+lpSubKey]
0x180028c5a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180028c5f  lea     rax, [rsp+210h+lpSubKey]
0x180028c64  mov     [rsp+210h+phkResult], rax; phkResult
0x180028c69  mov     r9d, 3; samDesired
0x180028c6f  xor     r8d, r8d; ulOptions
0x180028c72  mov     rdx, r15; lpSubKey
0x180028c75  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180028c7c  call    cs:__imp_RegOpenKeyExW
0x180028c82  test    eax, eax
0x180028c84  jle     short loc_180028C90
0x180028c86  movzx   eax, ax
0x180028c89  or      eax, 80070000h
0x180028c8e  test    eax, eax
0x180028c90  js      short loc_180028CD2
0x180028c92  mov     [rsp+210h+lpcbData], 0; lpcbData
0x180028c9b  mov     [rsp+210h+phkResult], 0; int
0x180028ca4  xor     r9d, r9d; lpType
0x180028ca7  xor     r8d, r8d; lpReserved
0x180028caa  lea     rdx, aPenworkspaceve; "PenWorkspaceVerb"
0x180028cb1  mov     rcx, [rsp+210h+lpSubKey]; hKey
0x180028cb6  call    cs:__imp_RegQueryValueExW
0x180028cbc  test    eax, eax
0x180028cbe  jnz     short loc_180028CD2
0x180028cc0  lea     rdx, aPenworkspaceve; "PenWorkspaceVerb"
0x180028cc7  mov     rcx, [rsp+210h+lpSubKey]; hKey
0x180028ccc  call    cs:__imp_RegDeleteValueW
0x180028cd2  lea     rcx, [rsp+210h+lpSubKey]
0x180028cd7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180028cdc  mov     rcx, r12
0x180028cdf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x180028ce4  test    al, al
0x180028ce6  jnz     short loc_180028D31
0x180028ce8  cmp     edi, 9
0x180028ceb  jnz     short loc_180028D0A
0x180028ced  mov     [rsp+210h+var_1E0], 1
0x180028cf2  lea     rdx, [rsp+210h+var_1E0]; bool *
0x180028cf7  lea     rcx, packageFamilyName; "Microsoft.Whiteboard_8wekyb3d8bbwe"
0x180028cfe  call    ?CheckIfPackageIsInstalled@ActionTypeOptionManager@PenSettings@SystemSettings@@SAJPEBGPEA_N@Z; SystemSettings::PenSettings::ActionTypeOptionManager::CheckIfPackageIsInstalled(ushort const *,bool *)
0x180028d03  cmp     [rsp+210h+var_1E0], 0
0x180028d08  jz      short loc_180028D2C
0x180028d0a  cmp     edi, 0Ah
0x180028d0d  jnz     short loc_180028D31
0x180028d0f  mov     [rsp+210h+var_1E0], 1
0x180028d14  lea     rdx, [rsp+210h+var_1E0]; bool *
0x180028d19  lea     rcx, aMicrosoftOffic_0; "Microsoft.Office.OneNote_8wekyb3d8bbwe"
0x180028d20  call    ?CheckIfPackageIsInstalled@ActionTypeOptionManager@PenSettings@SystemSettings@@SAJPEBGPEA_N@Z; SystemSettings::PenSettings::ActionTypeOptionManager::CheckIfPackageIsInstalled(ushort const *,bool *)
0x180028d25  cmp     [rsp+210h+var_1E0], 0
0x180028d2a  jnz     short loc_180028D31
0x180028d2c  mov     edi, 8
0x180028d31  mov     rcx, r12
0x180028d34  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x180028d39  test    al, al
0x180028d3b  jnz     short loc_180028D58
0x180028d3d  test    edi, edi
0x180028d3f  jnz     short loc_180028D58
0x180028d41  mov     rdx, [rsp+210h+var_1C0]
0x180028d46  call    SHRegSubKeyExistsW
0x180028d4b  test    eax, eax
0x180028d4d  jz      short loc_180028D58
0x180028d4f  lea     r14, String1; "SystemSettings_Devices_Pen_ButtonCustom"...
0x180028d56  jmp     short loc_180028D65
0x180028d58  mov     rdx, r13
0x180028d5b  mov     ecx, edi
0x180028d5d  call    ??$FindResourceTagFromEnum@W4PenClickOverride@@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@@PenSettings@SystemSettings@@YAPEBGW4PenClickOverride@@PEBV?$vector@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@V?$allocator@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@@std@@@std@@@Z; SystemSettings::PenSettings::FindResourceTagFromEnum<PenClickOverride,SystemSettings::PenSettings::PenActionTypeResourceMapping_>(PenClickOverride,std::vector<SystemSettings::PenSettings::PenActionTypeResourceMapping_> const *)
0x180028d62  mov     r14, rax
0x180028d65  mov     rcx, r12
0x180028d68  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x180028d6d  test    al, al
0x180028d6f  jz      short loc_180028D7E
0x180028d71  mov     rcx, rbx
0x180028d74  cmp     edi, 0FFFFFFFFh
0x180028d77  cmovnz  rcx, r14
0x180028d7b  mov     r14, rcx
0x180028d7e  mov     rcx, r12
0x180028d81  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PenButtonSettingsModernization@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenButtonSettingsModernization>::__private_IsEnabled(void)
0x180028d86  test    al, al
0x180028d88  jz      loc_180029348
0x180028d8e  cmp     edi, 12h
0x180028d91  jnz     loc_180029348
0x180028d97  xor     edi, edi
0x180028d99  mov     [rsp+210h+length], edi
0x180028d9d  lea     r9, [rsp+210h+length]; unsigned int *
0x180028da2  lea     r8, aApptype; "AppType"
0x180028da9  mov     rdx, r15; unsigned __int16 *
  ... truncated ...
```
