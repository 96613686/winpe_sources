# SystemSettings::Personalization::PersonalizePreview::GetNamedValue(HSTRING__ *,IInspectable * *)

- ea: `0x180173360`
- end: `0x180173dc4`
- name: `?GetNamedValue@PersonalizePreview@Personalization@SystemSettings@@MEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `2660`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::PersonalizePreview *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180013194`
- `0x180013d4c`
- `0x180019a20`
- `0x180020170`
- `0x1800201c4`
- `0x180020224`
- `0x180020af0`
- `0x180021398`
- `0x1800234c4`
- `0x180032208`
- `0x18004d1ac`
- `0x18005019c`
- `0x1800d55c0`
- `0x18012e960`
- `0x18015fc44`
- `0x18017312c`
- `0x18017328c`
- `0x180173360`
- `0x1801745dc`
- `0x180174614`
- `0x18017469c`
- `0x180175954`
- `0x180197700`
- `0x180197a9c`
- `0x180197b20`
- `0x180197f28`
- `0x180197f4c`
- `0x18019cb48`
- `0x18019dd30`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180173602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017368e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180173d11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180173d91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180173602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017368e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180173d11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180173d91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180173654`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180173654`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::Personalization::PersonalizePreview::GetNamedValue(
        SystemSettings::Personalization::PersonalizePreview *this,
        SystemSettings::DataModel *a2,
        HSTRING *a3)
{
  const unsigned __int16 *v6; // r8
  HSTRING v7; // rcx
  const char *v8; // r9
  bool *v10; // rdx
  const unsigned __int16 *v11; // r8
  int IsWallpaperDisabledDueToEaseOfAccess; // ebx
  __int64 v13; // rdx
  unsigned int v14; // ecx
  SystemSettings::Personalization::DesktopWallpaperHelper *DesktopWallpaperHelper; // rax
  const unsigned __int16 *v16; // r8
  SystemSettings::Personalization::DesktopWallpaperHelper *v17; // rax
  bool *v18; // rdx
  const unsigned __int16 *v19; // r8
  SystemSettings::Personalization::DesktopWallpaperHelper *v20; // rax
  bool *v21; // rdx
  const unsigned __int16 *v22; // r8
  HSTRING *v23; // r8
  int v24; // eax
  unsigned int v25; // esi
  HSTRING v26; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v28; // eax
  HKEY v29; // rcx
  const unsigned __int16 *v30; // r8
  int RegBoolean; // eax
  TabletModeHelpers *v32; // rcx
  bool v33; // zf
  unsigned int v34; // eax
  unsigned int Color; // eax
  const unsigned __int16 *v36; // r8
  int IsTransparencyEnabled; // eax
  double v38; // xmm0_8
  HKEY v39; // rcx
  const unsigned __int16 *v40; // r8
  int v41; // eax
  unsigned int v42; // eax
  const unsigned __int16 *v43; // r8
  int v44; // eax
  double v45; // xmm0_8
  HKEY v46; // rcx
  const unsigned __int16 *v47; // r8
  int v48; // eax
  unsigned int v49; // eax
  const unsigned __int16 *v50; // r8
  unsigned int v51; // eax
  const unsigned __int16 *v52; // r8
  unsigned int v53; // eax
  const unsigned __int16 *v54; // r8
  unsigned int v55; // eax
  const unsigned __int16 *v56; // r8
  unsigned int v57; // eax
  SystemSettings::Personalization::PersonalizePreview *v58; // rcx
  const unsigned __int16 *v59; // r8
  unsigned int TitlebarColor; // eax
  SystemSettings::Personalization::PersonalizePreview *v61; // rcx
  const unsigned __int16 *v62; // r8
  unsigned int v63; // eax
  __int64 v64; // rcx
  unsigned int v65; // eax
  const unsigned __int16 *v66; // r8
  SystemSettings::Personalization::DesktopWallpaperHelper *v67; // rax
  SystemSettings::Personalization *v68; // rcx
  SystemSettings::Personalization::DesktopWallpaperHelper *v69; // rbx
  int v70; // eax
  __int64 v71; // rdx
  const unsigned __int16 *v72; // r8
  const unsigned __int16 *v73; // r8
  HSTRING *v74; // r8
  int ResourceStringById; // eax
  int v76; // eax
  unsigned __int16 *v77; // [rsp+20h] [rbp-38h] BYREF
  __int64 v78; // [rsp+28h] [rbp-30h]
  __int64 v79; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HSTRING string; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v82; // [rsp+78h] [rbp+20h] BYREF

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180313630, (const unsigned __int16 *)a3) )
  {
    Microsoft::WRL::Wrappers::SRWLock::LockShared(&v82, (char *)this + 352);
    if ( *((_QWORD *)this + 45) )
    {
      try
      {
        winrt::impl::consume_WindowsUdk_UI_IMenuItem<winrt::WindowsUdk::UI::IMenuItem>::InvokeAsync(
          (char *)this + 360,
          &string);
        v7 = string;
        if ( string )
        {
          *a3 = string;
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v7 + 8LL))(v7);
        }
        else
        {
          *a3 = 0;
        }
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&string);
      }
      catch ( ... )
      {
        LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                            retaddr,
                            (void *)0x1BC,
                            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
                            v8);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v82);
        return (unsigned int)string;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v82);
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180308140, v6) )
  {
    LOBYTE(string) = 0;
    IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::Personalization::IsWallpaperDisabledDueToEaseOfAccess(
                                             (SystemSettings::Personalization *)&string,
                                             v10);
    if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
    {
      v13 = 450;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
        (const char *)(unsigned int)IsWallpaperDisabledDueToEaseOfAccess,
        (int)v77);
      return (unsigned int)IsWallpaperDisabledDueToEaseOfAccess;
    }
    v14 = 0;
    v82 = 0;
    if ( !(_BYTE)string )
    {
      DesktopWallpaperHelper = SystemSettings::Personalization::PersonalizePreview::GetDesktopWallpaperHelper(this);
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::Personalization::DesktopWallpaperHelper::GetBackgroundColor(
                                               DesktopWallpaperHelper,
                                               &v82);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 459;
        goto LABEL_13;
      }
      v14 = v82;
    }
    IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateUInt32(
                                             v14,
                                             (struct IInspectable **)a3);
    if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
    {
      v13 = 461;
      goto LABEL_13;
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180313508, v11) )
  {
    v82 = 0;
    v17 = SystemSettings::Personalization::PersonalizePreview::GetDesktopWallpaperHelper(this);
    IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::Personalization::DesktopWallpaperHelper::GetPosition(
                                             v17,
                                             (enum DESKTOP_WALLPAPER_POSITION *)&v82);
    if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
    {
      v13 = 466;
      goto LABEL_13;
    }
    if ( v82 == 1 )
    {
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateBoolean(
                                               0,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 470;
        goto LABEL_13;
      }
    }
    else
    {
      LOBYTE(string) = 0;
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::Personalization::IsPreviewVisible(
                                               (SystemSettings::Personalization *)&string,
                                               v18);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 475;
        goto LABEL_13;
      }
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateBoolean(
                                               (unsigned __int8)string,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 476;
        goto LABEL_13;
      }
    }
    return 0;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803134D0, v16) )
  {
    v82 = 0;
    v20 = SystemSettings::Personalization::PersonalizePreview::GetDesktopWallpaperHelper(this);
    IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::Personalization::DesktopWallpaperHelper::GetPosition(
                                             v20,
                                             (enum DESKTOP_WALLPAPER_POSITION *)&v82);
    if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
    {
      v13 = 482;
      goto LABEL_13;
    }
    if ( v82 == 1 )
    {
      LOBYTE(string) = 0;
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::Personalization::IsPreviewVisible(
                                               (SystemSettings::Personalization *)&string,
                                               v21);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 491;
        goto LABEL_13;
      }
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateBoolean(
                                               (unsigned __int8)string,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 492;
        goto LABEL_13;
      }
    }
    else
    {
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateBoolean(
                                               0,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 486;
        goto LABEL_13;
      }
    }
    return 0;
  }
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180313608, v19) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803137F0, v22) )
    {
      LOBYTE(string) = 0;
      RegBoolean = SystemSettings::Personalization::ColorSingleton::GetRegBoolean(
                     v29,
                     L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize",
                     L"ColorPrevalence",
                     (unsigned __int8 *)&string);
      if ( RegBoolean < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1FA,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
          (const char *)(unsigned int)RegBoolean,
          (int)v77);
      if ( !(_BYTE)string || (v33 = !TabletModeHelpers::IsTabletMode(v32), v34 = 6, !v33) )
        v34 = 215;
      Color = CImmersiveColor::GetColor(v34);
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateUInt32(
                                               Color,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess >= 0 )
        return 0;
      v13 = 510;
      goto LABEL_13;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803137D0, v30) )
    {
      LOBYTE(string) = 0;
      IsTransparencyEnabled = SystemSettings::Personalization::ColorSingleton::get_IsTransparencyEnabled((unsigned __int8 *)&string);
      if ( IsTransparencyEnabled < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x204,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
          (const char *)(unsigned int)IsTransparencyEnabled,
          (int)v77);
      if ( (_BYTE)string )
        v38 = DOUBLE_0_95;
      else
        v38 = DOUBLE_1_0;
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateDouble(
                                               v38,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess >= 0 )
        return 0;
      v13 = 518;
      goto LABEL_13;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803137B8, v36) )
    {
      LOBYTE(string) = 0;
      v41 = SystemSettings::Personalization::ColorSingleton::GetRegBoolean(
              v39,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize",
              L"ColorPrevalence",
              (unsigned __int8 *)&string);
      if ( v41 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x20C,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
          (const char *)(unsigned int)v41,
          (int)v77);
      v42 = CImmersiveColor::GetColor((_BYTE)string != 0 ? 5 : 215);
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateUInt32(
                                               v42,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess >= 0 )
        return 0;
      v13 = 528;
      goto LABEL_13;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180313798, v40) )
    {
      LOBYTE(string) = 0;
      v44 = SystemSettings::Personalization::ColorSingleton::get_IsTransparencyEnabled((unsigned __int8 *)&string);
      if ( v44 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x216,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
          (const char *)(unsigned int)v44,
          (int)v77);
      if ( (_BYTE)string )
        v45 = DOUBLE_0_85;
      else
        v45 = DOUBLE_1_0;
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateDouble(
                                               v45,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess >= 0 )
        return 0;
      v13 = 537;
      goto LABEL_13;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180313778, v43) )
    {
      LOBYTE(string) = 0;
      v48 = SystemSettings::Personalization::ColorSingleton::GetRegBoolean(
              v46,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize",
              L"ColorPrevalence",
              (unsigned __int8 *)&string);
      if ( v48 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x21F,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
          (const char *)(unsigned int)v48,
          (int)v77);
      v49 = CImmersiveColor::GetColor((_BYTE)string != 0 ? 255 : 8);
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateUInt32(
                                               v49,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess >= 0 )
        return 0;
      v13 = 547;
      goto LABEL_13;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180313718, v47) )
    {
      v51 = CImmersiveColor::GetColor(210);
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateUInt32(
                                               v51,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 552;
        goto LABEL_13;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)L"WindowColor", v50) )
    {
      v53 = CImmersiveColor::GetColor(4);
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateUInt32(
                                               v53,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 557;
        goto LABEL_13;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180313748, v52) )
    {
      v55 = CImmersiveColor::GetColor(4);
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateUInt32(
                                               v55,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 562;
        goto LABEL_13;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180313680, v54) )
    {
      v57 = CImmersiveColor::GetColor(0);
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateUInt32(
                                               v57,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 567;
        goto LABEL_13;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803136D0, v56) )
    {
      TitlebarColor = SystemSettings::Personalization::PersonalizePreview::_GetTitlebarColor(v58);
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateUInt32(
                                               TitlebarColor,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 571;
        goto LABEL_13;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803136A0, v59) )
    {
      v63 = SystemSettings::Personalization::PersonalizePreview::_GetTitlebarColor(v61);
      v64 = 321;
      if ( BYTE2(v63) + 5 * BYTE1(v63) + 2 * (unsigned int)(unsigned __int8)v63 <= 0x400 )
        v64 = 292;
      v65 = CImmersiveColor::GetColor(v64);
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateUInt32(
                                               v65,
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess >= 0 )
        return 0;
      v13 = 580;
      goto LABEL_13;
    }
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180313810, v62) )
    {
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18030E090, v66) )
      {
        IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateBoolean(
                                                 0,
                                                 (struct IInspectable **)a3);
        if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
        {
          v13 = 632;
          goto LABEL_13;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1803138C0, v72) )
      {
        IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateBoolean(
                                                 0,
                                                 (struct IInspectable **)a3);
        if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
        {
          v13 = 636;
          goto LABEL_13;
        }
        return 0;
      }
      if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180313898, v73) )
      {
        IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetNamedValue(
                                                 this,
                                                 a2,
                                                 a3);
        if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
        {
          v13 = 646;
          goto LABEL_13;
        }
        return 0;
      }
      WindowsDeleteString(0);
      string = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_PersonalizePerview_SampleTextContent",
                             &string,
                             v74);
      v25 = ResourceStringById;
      if ( ResourceStringById < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x281,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
          (const char *)(unsigned int)ResourceStringById,
          (int)v77);
        v26 = string;
        goto LABEL_46;
      }
      v26 = string;
      v76 = SystemSettings::DataModel::PropValueHelper::CreateString(string, (struct IInspectable **)a3);
      v25 = v76;
      if ( v76 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x282,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
          (const char *)(unsigned int)v76,
          (int)v77);
        goto LABEL_46;
      }
      goto LABEL_140;
    }
    LODWORD(string) = 0;
    v67 = SystemSettings::Personalization::PersonalizePreview::GetDesktopWallpaperHelper(this);
    IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::Personalization::DesktopWallpaperHelper::GetPosition(
                                             v67,
                                             (enum DESKTOP_WALLPAPER_POSITION *)&string);
    if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
    {
      v13 = 585;
      goto LABEL_13;
    }
    switch ( (_DWORD)string )
    {
      case 0:
        IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateString(
                                                 L"None",
                                                 (struct IInspectable **)a3);
        if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
        {
          v13 = 589;
          goto LABEL_13;
        }
        return 0;
      case 2:
        IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateString(
                                                 L"Fill",
                                                 (struct IInspectable **)a3);
        if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
        {
          v13 = 593;
          goto LABEL_13;
        }
        return 0;
      case 3:
        IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateString(
                                                 L"Uniform",
                                                 (struct IInspectable **)a3);
        if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
        {
          v13 = 597;
          goto LABEL_13;
        }
        return 0;
      case 4:
        IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateString(
                                                 L"UniformToFill",
                                                 (struct IInspectable **)a3);
        if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
        {
          v13 = 601;
          goto LABEL_13;
        }
        return 0;
    }
    if ( (_DWORD)string != 1 )
    {
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateString(
                                               L"UniformToFill",
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 627;
        goto LABEL_13;
      }
      return 0;
    }
    if ( !SystemSettings::Personalization::IsVideoWallpaperSupported(v68) )
    {
      IsWallpaperDisabledDueToEaseOfAccess = SystemSettings::DataModel::PropValueHelper::CreateString(
                                               L"None",
                                               (struct IInspectable **)a3);
      if ( IsWallpaperDisabledDueToEaseOfAccess < 0 )
      {
        v13 = 622;
        goto LABEL_13;
      }
      return 0;
    }
    v77 = 0;
    v78 = 0;
    v79 = 0;
    v69 = SystemSettings::Personalization::PersonalizePreview::GetDesktopWallpaperHelper(this);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v77);
    v78 = -1;
    v79 = -1;
    SystemSettings::Personalization::DesktopWallpaperHelper::GetWallpaper(v69, &v77);
    if ( (unsigned __int8)anonymous_namespace_::IsVideoFile(v77) )
    {
      v70 = SystemSettings::DataModel::PropValueHelper::CreateString(L"Fill", (struct IInspectable **)a3);
      IsWallpaperDisabledDueToEaseOfAccess = v70;
      if ( v70 < 0 )
      {
        v71 = 613;
LABEL_123:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v71,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
          (const char *)(unsigned int)v70,
          (int)v77);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v77);
        return (unsigned int)IsWallpaperDisabledDueToEaseOfAccess;
      }
    }
    else
    {
      v70 = SystemSettings::DataModel::PropValueHelper::CreateString(L"None", (struct IInspectable **)a3);
      IsWallpaperDisabledDueToEaseOfAccess = v70;
      if ( v70 < 0 )
      {
        v71 = 617;
        goto LABEL_123;
      }
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v77);
    return 0;
  }
  WindowsDeleteString(0);
  string = 0;
  v24 = SystemSettings::DataModel::GetResourceStringById(
          (SystemSettings::DataModel *)L"SystemSettings_PersonalizePreviewDescription",
          &string,
          v23);
  v25 = v24;
  if ( v24 >= 0 )
  {
    v26 = string;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v28 = SystemSettings::DataModel::PropValueHelper::CreateString(StringRawBuffer, (struct IInspectable **)a3);
    v25 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F3,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
        (const char *)(unsigned int)v28,
        (int)v77);
      goto LABEL_46;
    }
LABEL_140:
    WindowsDeleteString(v26);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F2,
    (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\personalizepreview.cpp",
    (const char *)(unsigned int)v24,
    (int)v77);
  v26 = string;
LABEL_46:
  WindowsDeleteString(v26);
  return v25;
}

```

## disassembly

```asm
0x180173360  mov     [rsp+arg_0], rbx
0x180173365  push    rsi
0x180173366  push    rdi
0x180173367  push    r14
0x180173369  sub     rsp, 40h
0x18017336d  mov     rdi, r8
0x180173370  mov     rbx, rdx
0x180173373  mov     rsi, rcx
0x180173376  xor     r14d, r14d
0x180173379  mov     [r8], r14
0x18017337c  lea     rdx, stru_180313630; HSTRING
0x180173383  mov     rcx, rbx; this
0x180173386  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18017338b  test    al, al
0x18017338d  jz      short loc_18017340D
0x18017338f  lea     rdx, [rsi+160h]
0x180173396  lea     rcx, [rsp+58h+arg_18]
0x18017339b  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x1801733a0  nop
0x1801733a1  lea     rcx, [rsi+168h]
0x1801733a8  cmp     [rcx], r14
0x1801733ab  jz      short loc_1801733F2
0x1801733ad  lea     rdx, [rsp+58h+string]
0x1801733b2  call    ?InvokeAsync@?$consume_WindowsUdk_UI_IMenuItem@UIMenuItem@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_IMenuItem<winrt::WindowsUdk::UI::IMenuItem>::InvokeAsync(void)
0x1801733b7  nop
0x1801733b8  mov     rcx, [rsp+58h+string]
0x1801733bd  test    rcx, rcx
0x1801733c0  jz      short loc_1801733D3
0x1801733c2  mov     [rdi], rcx
0x1801733c5  mov     rax, [rcx]
0x1801733c8  mov     rax, [rax+8]
0x1801733cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801733d1  jmp     short loc_1801733D6
0x1801733d3  mov     [rdi], r14
0x1801733d6  lea     rcx, [rsp+58h+string]; this
0x1801733db  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x1801733e0  jmp     short loc_1801733F2
0x1801733e2  lea     rcx, [rsp+58h+arg_18]
0x1801733e7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801733ec  mov     eax, dword ptr [rsp+58h+string]
0x1801733f0  jmp     short loc_1801733FE
0x1801733f2  lea     rcx, [rsp+58h+arg_18]
0x1801733f7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801733fc  xor     eax, eax
0x1801733fe  mov     rbx, [rsp+58h+arg_0]
0x180173403  add     rsp, 40h
0x180173407  pop     r14
0x180173409  pop     rdi
0x18017340a  pop     rsi
0x18017340b  retn
0x18017340d  lea     rdx, stru_180308140; HSTRING
0x180173414  mov     rcx, rbx; this
0x180173417  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18017341c  test    al, al
0x18017341e  jz      short loc_18017349F
0x180173420  mov     byte ptr [rsp+58h+string], r14b
0x180173425  lea     rcx, [rsp+58h+string]; this
0x18017342a  call    ?IsWallpaperDisabledDueToEaseOfAccess@Personalization@SystemSettings@@YAJAEA_N@Z; SystemSettings::Personalization::IsWallpaperDisabledDueToEaseOfAccess(bool &)
0x18017342f  mov     ebx, eax
0x180173431  test    eax, eax
0x180173433  jns     short loc_180173452
0x180173435  mov     edx, 1C2h; void *
0x18017343a  lea     r8, aShellSystemset_87; "shell\\systemsettingsthreshold\\handler"...
0x180173441  mov     r9d, ebx; char *
0x180173444  mov     rcx, [rsp+58h]; this
0x180173449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017344e  mov     eax, ebx
0x180173450  jmp     short loc_1801733FE
0x180173452  mov     ecx, r14d
0x180173455  mov     [rsp+58h+arg_18], ecx
0x180173459  cmp     byte ptr [rsp+58h+string], r14b
0x18017345e  jnz     short loc_180173486
0x180173460  mov     rcx, rsi; this
0x180173463  call    ?GetDesktopWallpaperHelper@PersonalizePreview@Personalization@SystemSettings@@AEAAAEAVDesktopWallpaperHelper@23@XZ; SystemSettings::Personalization::PersonalizePreview::GetDesktopWallpaperHelper(void)
0x180173468  lea     rdx, [rsp+58h+arg_18]; unsigned int *
0x18017346d  mov     rcx, rax; this
0x180173470  call    ?GetBackgroundColor@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJPEAK@Z; SystemSettings::Personalization::DesktopWallpaperHelper::GetBackgroundColor(ulong *)
0x180173475  mov     ebx, eax
0x180173477  test    eax, eax
0x180173479  jns     short loc_180173482
0x18017347b  mov     edx, 1CBh
0x180173480  jmp     short loc_18017343A
0x180173482  mov     ecx, [rsp+58h+arg_18]; unsigned int
0x180173486  mov     rdx, rdi; struct IInspectable **
0x180173489  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x18017348e  mov     ebx, eax
0x180173490  test    eax, eax
0x180173492  jns     loc_1801733FC
0x180173498  mov     edx, 1CDh
0x18017349d  jmp     short loc_18017343A
0x18017349f  lea     rdx, stru_180313508; HSTRING
0x1801734a6  mov     rcx, rbx; this
0x1801734a9  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801734ae  test    al, al
0x1801734b0  jz      loc_180173544
0x1801734b6  mov     [rsp+58h+arg_18], r14d
0x1801734bb  mov     rcx, rsi; this
0x1801734be  call    ?GetDesktopWallpaperHelper@PersonalizePreview@Personalization@SystemSettings@@AEAAAEAVDesktopWallpaperHelper@23@XZ; SystemSettings::Personalization::PersonalizePreview::GetDesktopWallpaperHelper(void)
0x1801734c3  lea     rdx, [rsp+58h+arg_18]; enum DESKTOP_WALLPAPER_POSITION *
0x1801734c8  mov     rcx, rax; this
0x1801734cb  call    ?GetPosition@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJPEAW4DESKTOP_WALLPAPER_POSITION@@@Z; SystemSettings::Personalization::DesktopWallpaperHelper::GetPosition(DESKTOP_WALLPAPER_POSITION *)
0x1801734d0  mov     ebx, eax
0x1801734d2  test    eax, eax
0x1801734d4  jns     short loc_1801734E0
0x1801734d6  mov     edx, 1D2h
0x1801734db  jmp     loc_18017343A
0x1801734e0  cmp     [rsp+58h+arg_18], 1
0x1801734e5  jnz     short loc_180173505
0x1801734e7  mov     rdx, rdi; struct IInspectable **
0x1801734ea  xor     ecx, ecx; unsigned __int8
0x1801734ec  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1801734f1  mov     ebx, eax
0x1801734f3  test    eax, eax
0x1801734f5  jns     loc_1801733FC
0x1801734fb  mov     edx, 1D6h
0x180173500  jmp     loc_18017343A
0x180173505  mov     byte ptr [rsp+58h+string], r14b
0x18017350a  lea     rcx, [rsp+58h+string]; this
0x18017350f  call    ?IsPreviewVisible@Personalization@SystemSettings@@YAJPEA_N@Z; SystemSettings::Personalization::IsPreviewVisible(bool *)
0x180173514  mov     ebx, eax
0x180173516  test    eax, eax
0x180173518  jns     short loc_180173524
0x18017351a  mov     edx, 1DBh
0x18017351f  jmp     loc_18017343A
0x180173524  mov     rdx, rdi; struct IInspectable **
0x180173527  mov     cl, byte ptr [rsp+58h+string]; unsigned __int8
0x18017352b  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x180173530  mov     ebx, eax
0x180173532  test    eax, eax
0x180173534  jns     loc_1801733FC
0x18017353a  mov     edx, 1DCh
0x18017353f  jmp     loc_18017343A
0x180173544  lea     rdx, stru_1803134D0; HSTRING
0x18017354b  mov     rcx, rbx; this
0x18017354e  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180173553  test    al, al
0x180173555  jz      loc_1801735E9
0x18017355b  mov     [rsp+58h+arg_18], r14d
0x180173560  mov     rcx, rsi; this
0x180173563  call    ?GetDesktopWallpaperHelper@PersonalizePreview@Personalization@SystemSettings@@AEAAAEAVDesktopWallpaperHelper@23@XZ; SystemSettings::Personalization::PersonalizePreview::GetDesktopWallpaperHelper(void)
0x180173568  lea     rdx, [rsp+58h+arg_18]; enum DESKTOP_WALLPAPER_POSITION *
0x18017356d  mov     rcx, rax; this
0x180173570  call    ?GetPosition@DesktopWallpaperHelper@Personalization@SystemSettings@@QEAAJPEAW4DESKTOP_WALLPAPER_POSITION@@@Z; SystemSettings::Personalization::DesktopWallpaperHelper::GetPosition(DESKTOP_WALLPAPER_POSITION *)
0x180173575  mov     ebx, eax
0x180173577  test    eax, eax
0x180173579  jns     short loc_180173585
0x18017357b  mov     edx, 1E2h
0x180173580  jmp     loc_18017343A
0x180173585  cmp     [rsp+58h+arg_18], 1
0x18017358a  jz      short loc_1801735AA
0x18017358c  mov     rdx, rdi; struct IInspectable **
0x18017358f  xor     ecx, ecx; unsigned __int8
0x180173591  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x180173596  mov     ebx, eax
0x180173598  test    eax, eax
0x18017359a  jns     loc_1801733FC
0x1801735a0  mov     edx, 1E6h
0x1801735a5  jmp     loc_18017343A
0x1801735aa  mov     byte ptr [rsp+58h+string], r14b
0x1801735af  lea     rcx, [rsp+58h+string]; this
0x1801735b4  call    ?IsPreviewVisible@Personalization@SystemSettings@@YAJPEA_N@Z; SystemSettings::Personalization::IsPreviewVisible(bool *)
0x1801735b9  mov     ebx, eax
0x1801735bb  test    eax, eax
0x1801735bd  jns     short loc_1801735C9
0x1801735bf  mov     edx, 1EBh
0x1801735c4  jmp     loc_18017343A
0x1801735c9  mov     rdx, rdi; struct IInspectable **
0x1801735cc  mov     cl, byte ptr [rsp+58h+string]; unsigned __int8
0x1801735d0  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x1801735d5  mov     ebx, eax
0x1801735d7  test    eax, eax
0x1801735d9  jns     loc_1801733FC
0x1801735df  mov     edx, 1ECh
0x1801735e4  jmp     loc_18017343A
0x1801735e9  lea     rdx, stru_180313608; HSTRING
0x1801735f0  mov     rcx, rbx; this
0x1801735f3  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801735f8  test    al, al
0x1801735fa  jz      loc_1801736A6
0x180173600  xor     ecx, ecx; string
0x180173602  call    cs:__imp_WindowsDeleteString
0x180173609  nop     dword ptr [rax+rax+00h]
0x18017360e  mov     [rsp+58h+string], r14
0x180173613  lea     rdx, [rsp+58h+string]; HSTRING *
0x180173618  lea     rcx, aSystemsettings_1487; "SystemSettings_PersonalizePreviewDescri"...
0x18017361f  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180173624  mov     esi, eax
0x180173626  test    eax, eax
0x180173628  jns     short loc_18017364A
0x18017362a  mov     rcx, [rsp+58h]; this
0x18017362f  mov     r9d, eax; char *
0x180173632  lea     r8, aShellSystemset_87; "shell\\systemsettingsthreshold\\handler"...
0x180173639  mov     edx, 1F2h; void *
0x18017363e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180173643  mov     rbx, [rsp+58h+string]
0x180173648  jmp     short loc_18017368B
0x18017364a  xor     edx, edx; length
0x18017364c  mov     rbx, [rsp+58h+string]
0x180173651  mov     rcx, rbx; string
0x180173654  call    cs:__imp_WindowsGetStringRawBuffer
0x18017365b  nop     dword ptr [rax+rax+00h]
0x180173660  mov     rdx, rdi; struct IInspectable **
0x180173663  mov     rcx, rax; unsigned __int16 *
0x180173666  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18017366b  mov     esi, eax
0x18017366d  test    eax, eax
0x18017366f  jns     short loc_1801736A1
0x180173671  mov     rcx, [rsp+58h]; this
0x180173676  mov     r9d, eax; char *
0x180173679  lea     r8, aShellSystemset_87; "shell\\systemsettingsthreshold\\handler"...
0x180173680  mov     edx, 1F3h; void *
0x180173685  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017368a  nop
0x18017368b  mov     rcx, rbx; string
0x18017368e  call    cs:__imp_WindowsDeleteString
0x180173695  nop     dword ptr [rax+rax+00h]
0x18017369a  mov     eax, esi
0x18017369c  jmp     loc_1801733FE
0x1801736a1  jmp     loc_180173D8E
0x1801736a6  lea     rdx, stru_1803137F0; HSTRING
0x1801736ad  mov     rcx, rbx; this
0x1801736b0  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801736b5  test    al, al
0x1801736b7  jz      short loc_180173732
0x1801736b9  mov     byte ptr [rsp+58h+string], r14b
0x1801736be  lea     r9, [rsp+58h+string]; unsigned __int8 *
0x1801736c3  lea     r8, aColorprevalenc_1; "ColorPrevalence"
0x1801736ca  lea     rdx, aSoftwareMicros_36; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801736d1  call    ?GetRegBoolean@ColorSingleton@Personalization@SystemSettings@@KAJPEAUHKEY__@@PEAG1PEAE@Z; SystemSettings::Personalization::ColorSingleton::GetRegBoolean(HKEY__ *,ushort *,ushort *,uchar *)
0x1801736d6  test    eax, eax
0x1801736d8  jns     short loc_1801736F3
0x1801736da  mov     rcx, [rsp+58h]; this
0x1801736df  mov     r9d, eax; char *
0x1801736e2  lea     r8, aShellSystemset_87; "shell\\systemsettingsthreshold\\handler"...
0x1801736e9  mov     edx, 1FAh; void *
0x1801736ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801736f3  cmp     byte ptr [rsp+58h+string], r14b
0x1801736f8  jz      short loc_180173708
0x1801736fa  call    ?IsTabletMode@TabletModeHelpers@@YA_NXZ; TabletModeHelpers::IsTabletMode(void)
0x1801736ff  test    al, al
0x180173701  mov     eax, 6
0x180173706  jz      short loc_18017370D
0x180173708  mov     eax, 0D7h
0x18017370d  mov     ecx, eax
0x18017370f  call    ?GetColor@CImmersiveColor@@SAKW4IMMERSIVE_COLOR_TYPE@@@Z; CImmersiveColor::GetColor(IMMERSIVE_COLOR_TYPE)
0x180173714  mov     rdx, rdi; struct IInspectable **
0x180173717  mov     ecx, eax; unsigned int
0x180173719  call    ?CreateUInt32@PropValueHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateUInt32(uint,IInspectable * *)
0x18017371e  mov     ebx, eax
0x180173720  test    eax, eax
0x180173722  jns     loc_1801733FC
0x180173728  mov     edx, 1FEh
0x18017372d  jmp     loc_18017343A
0x180173732  lea     rdx, stru_1803137D0; HSTRING
0x180173739  mov     rcx, rbx; this
0x18017373c  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180173741  test    al, al
0x180173743  jz      short loc_1801737A6
0x180173745  mov     byte ptr [rsp+58h+string], r14b
0x18017374a  lea     rcx, [rsp+58h+string]; unsigned __int8 *
0x18017374f  call    ?get_IsTransparencyEnabled@ColorSingleton@Personalization@SystemSettings@@SAJPEAE@Z; SystemSettings::Personalization::ColorSingleton::get_IsTransparencyEnabled(uchar *)
0x180173754  test    eax, eax
0x180173756  jns     short loc_180173771
0x180173758  mov     rcx, [rsp+58h]; this
0x18017375d  mov     r9d, eax; char *
0x180173760  lea     r8, aShellSystemset_87; "shell\\systemsettingsthreshold\\handler"...
0x180173767  mov     edx, 204h; void *
0x18017376c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180173771  cmp     byte ptr [rsp+58h+string], r14b
0x180173776  jz      short loc_180173782
0x180173778  movsd   xmm0, cs:__real@3fee666666666666
0x180173780  jmp     short loc_18017378A
0x180173782  movsd   xmm0, cs:__real@3ff0000000000000; double
0x18017378a  mov     rdx, rdi; struct IInspectable **
0x18017378d  call    ?CreateDouble@PropValueHelper@DataModel@SystemSettings@@SAJNPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateDouble(double,IInspectable * *)
0x180173792  mov     ebx, eax
0x180173794  test    eax, eax
0x180173796  jns     loc_1801733FC
0x18017379c  mov     edx, 206h
0x1801737a1  jmp     loc_18017343A
0x1801737a6  lea     rdx, stru_1803137B8; HSTRING
0x1801737ad  mov     rcx, rbx; this
0x1801737b0  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1801737b5  test    al, al
0x1801737b7  jz      short loc_18017382A
0x1801737b9  mov     byte ptr [rsp+58h+string], r14b
0x1801737be  lea     r9, [rsp+58h+string]; unsigned __int8 *
0x1801737c3  lea     r8, aColorprevalenc_1; "ColorPrevalence"
0x1801737ca  lea     rdx, aSoftwareMicros_36; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1801737d1  call    ?GetRegBoolean@ColorSingleton@Personalization@SystemSettings@@KAJPEAUHKEY__@@PEAG1PEAE@Z; SystemSettings::Personalization::ColorSingleton::GetRegBoolean(HKEY__ *,ushort *,ushort *,uchar *)
0x1801737d6  test    eax, eax
0x1801737d8  jns     short loc_1801737F3
0x1801737da  mov     rcx, [rsp+58h]; this
0x1801737df  mov     r9d, eax; char *
0x1801737e2  lea     r8, aShellSystemset_87; "shell\\systemsettingsthreshold\\handler"...
0x1801737e9  mov     edx, 20Ch; void *
0x1801737ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801737f3  mov     al, byte ptr [rsp+58h+string]
0x1801737f7  neg     al
0x1801737f9  sbb     ecx, ecx
  ... truncated ...
```
