# SystemSettings::Personalization::ThemeHelper::GetThemeImageName(ITheme *,HSTRING__ * *)

- ea: `0x18011045c`
- end: `0x1801109be`
- name: `?GetThemeImageName@ThemeHelper@Personalization@SystemSettings@@QEAAJPEAUITheme@@PEAPEAUHSTRING__@@@Z`
- size: `1378`
- prototype: `int(SystemSettings::Personalization::ThemeHelper *__hidden this, struct ITheme *, HSTRING *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180191810`

## callees

- `0x18000c840`
- `0x180014fd8`
- `0x180019a20`
- `0x18004d01c`
- `0x180066808`
- `0x180078f3c`
- `0x18009afb8`
- `0x18010ecf0`
- `0x18011045c`
- `0x18011100c`
- `0x1801110a0`
- `0x18011113c`
- `0x180111338`
- `0x180112604`
- `0x180113370`
- `0x18026459c`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801106c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011075e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801106c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18011075e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801108cd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1801108cd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1801108b6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1801108b6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1801105b5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1801105f9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1801105b5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1801105f9`
- `SHLWAPI!__imp_IsOS` at `0x1801106e1`
- `SHLWAPI!__imp_IsOS` at `0x180110776`
- `SHLWAPI!__imp_IsOS` at `0x1801106e1`
- `SHLWAPI!__imp_IsOS` at `0x180110776`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::Personalization::ThemeHelper::GetThemeImageName(
        SystemSettings::Personalization::ThemeHelper *this,
        struct ITheme *a2,
        HSTRING *a3)
{
  int v5; // r14d
  __int64 v6; // rdx
  int v8; // eax
  unsigned int v9; // edi
  SystemSettings::Personalization::ThemeHelper *v10; // rcx
  const char *v11; // r9
  const char *v12; // r9
  EduThemeHelpers *v13; // rcx
  const struct _GUID *v14; // rdx
  const enum EduThemeTypes *v15; // r8
  const enum EduThemeTypes *v16; // r8
  int ResourceStringById; // eax
  __int64 v18; // rdx
  BOOL v19; // eax
  struct Windows::ApplicationModel::Resources::Core::IResourceMap *v20; // rdx
  BOOL v21; // eax
  struct Windows::ApplicationModel::Resources::Core::IResourceMap *v22; // rdx
  const enum EduThemeTypes *v23; // r8
  const char *v24; // r9
  const unsigned __int16 *v25; // rdx
  SystemSettings::Personalization::ThemeHelper *v26; // rcx
  WCHAR *FileNameW; // rax
  HSTRING *v28; // r8
  SystemSettings::DataModel *v29; // rsi
  HSTRING *v30; // r8
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  struct _GUID v32; // [rsp+30h] [rbp-D0h] BYREF
  int v33; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v35; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String2[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v33 = 0;
  v34 = 0;
  v5 = (*(__int64 (__fastcall **)(struct ITheme *, int *))(*(_QWORD *)a2 + 264LL))(a2, &v33);
  if ( v5 < 0 )
  {
    v6 = 689;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\themehelper.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
    return (unsigned int)v5;
  }
  v5 = (*(__int64 (__fastcall **)(struct ITheme *, int *))(*(_QWORD *)a2 + 432LL))(a2, &v34);
  if ( v5 < 0 )
  {
    v6 = 690;
    goto LABEL_3;
  }
  if ( ((unsigned int)CSlideshowSettings::s_PolicyAllowsSlideshow() || !v33) && !v34 )
  {
    *(_QWORD *)v32.Data4 = 0;
    if ( (*(int (__fastcall **)(struct ITheme *, unsigned __int8 *))(*(_QWORD *)a2 + 168LL))(a2, v32.Data4) < 0
      || SystemSettings::Personalization::ThemeHelper::DoesBackgroundImageExist(
           v10,
           *(const unsigned __int16 **)v32.Data4) )
    {
      ResourceStringById = GetResourceStringById(
                             L"SystemSettings_Personalize_Themes_SolidColor",
                             *(struct Windows::ApplicationModel::Resources::Core::IResourceMap **)(qword_1803A1F30 + 64),
                             a3);
      v9 = ResourceStringById;
      if ( ResourceStringById < 0 )
      {
        v18 = 778;
        goto LABEL_54;
      }
      goto LABEL_55;
    }
    if ( (unsigned int)SHExpandEnvironmentStringsW(L"%SystemRoot%\\web\\wallpaper\\windows\\img0.jpg", String2, 260) )
    {
      if ( CompareStringOrdinal(*(LPCWCH *)v32.Data4, -1, String2, -1, 1) == 2 )
      {
        v19 = IsOS(0x1Du);
        v20 = *(struct Windows::ApplicationModel::Resources::Core::IResourceMap **)(qword_1803A1F30 + 64);
        if ( v19 )
        {
          ResourceStringById = GetResourceStringById(L"SystemSettings_Personalize_Themes_DefaultServerName", v20, a3);
          v9 = ResourceStringById;
          if ( ResourceStringById < 0 )
          {
            v18 = 715;
            goto LABEL_54;
          }
        }
        else
        {
          ResourceStringById = GetResourceStringById(
                                 L"SystemSettings_Personalize_Themes_DefaultClientNameLight",
                                 v20,
                                 a3);
          v9 = ResourceStringById;
          if ( ResourceStringById < 0 )
          {
            v18 = 719;
            goto LABEL_54;
          }
        }
        goto LABEL_55;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x2C6,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\themehelper.cpp",
        v11);
    }
    if ( (unsigned int)SHExpandEnvironmentStringsW(L"%SystemRoot%\\web\\wallpaper\\windows\\img19.jpg", String2, 260) )
    {
      if ( CompareStringOrdinal(*(LPCWCH *)v32.Data4, -1, String2, -1, 1) == 2 )
      {
        v21 = IsOS(0x1Du);
        v22 = *(struct Windows::ApplicationModel::Resources::Core::IResourceMap **)(qword_1803A1F30 + 64);
        if ( v21 )
        {
          ResourceStringById = GetResourceStringById(L"SystemSettings_Personalize_Themes_DefaultServerName", v22, a3);
          v9 = ResourceStringById;
          if ( ResourceStringById < 0 )
          {
            v18 = 727;
            goto LABEL_54;
          }
        }
        else
        {
          ResourceStringById = GetResourceStringById(
                                 L"SystemSettings_Personalize_Themes_DefaultClientNameDark",
                                 v22,
                                 a3);
          v9 = ResourceStringById;
          if ( ResourceStringById < 0 )
          {
            v18 = 731;
            goto LABEL_54;
          }
        }
        goto LABEL_55;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x2D2,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\themehelper.cpp",
        v12);
    }
    v35 = 0;
    if ( EduThemeHelpers::ShouldEnableEduThemes(v13)
      && (*(int (__fastcall **)(struct ITheme *, __int128 *))(*(_QWORD *)a2 + 120LL))(a2, &v35) >= 0
      && EduThemeHelpers::IsEduTheme((EduThemeHelpers *)&v35, v14) )
    {
      v32.Data1 = 1;
      if ( EduThemeHelpers::IsEduThemeWithType((EduThemeHelpers *)&v35, &v32, v15) )
      {
        ResourceStringById = GetResourceStringById(
                               L"SystemSettings_Personalize_Themes_DefaultClientNameEdu",
                               *(struct Windows::ApplicationModel::Resources::Core::IResourceMap **)(qword_1803A1F30 + 64),
                               a3);
        v9 = ResourceStringById;
        if ( ResourceStringById < 0 )
        {
          v18 = 740;
LABEL_54:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\themehelper.cpp",
            (const char *)(unsigned int)ResourceStringById,
            bIgnoreCase);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v32.Data4);
          return v9;
        }
      }
      else
      {
        v32.Data1 = 2;
        if ( EduThemeHelpers::IsEduThemeWithType((EduThemeHelpers *)&v35, &v32, v16) )
        {
          ResourceStringById = GetResourceStringById(
                                 L"SystemSettings_Personalize_Themes_PlanetsClientNameEdu",
                                 *(struct Windows::ApplicationModel::Resources::Core::IResourceMap **)(qword_1803A1F30 + 64),
                                 a3);
          v9 = ResourceStringById;
          if ( ResourceStringById < 0 )
          {
            v18 = 744;
            goto LABEL_54;
          }
        }
        else
        {
          v32.Data1 = 4;
          if ( !EduThemeHelpers::IsEduThemeWithType((EduThemeHelpers *)&v35, &v32, v23) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x2F0,
              (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\themehelper.cpp",
              v24);
          ResourceStringById = GetResourceStringById(
                                 L"SystemSettingNamePersonalize_Themes_SunsetClientNameEdu",
                                 *(struct Windows::ApplicationModel::Resources::Core::IResourceMap **)(qword_1803A1F30 + 64),
                                 a3);
          v9 = ResourceStringById;
          if ( ResourceStringById < 0 )
          {
            v18 = 748;
            goto LABEL_54;
          }
        }
      }
    }
    else
    {
      LOBYTE(v14) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlight>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlight>::GetImpl'::`2'::impl,
        v14,
        0);
      if ( CreativeFramework::TargetedContent::ConfigurationHelper::IsSubscriptionEnabled(
             (CreativeFramework::TargetedContent::ConfigurationHelper *)L"Desktop",
             v25)
        || SystemSettings::Personalization::ThemeHelper::IsUndockedDesktopSpotlightEnabled(v26) )
      {
        ResourceStringById = GetResourceStringById(
                               L"SystemSettings_Personalize_Background_Spotlight",
                               *(struct Windows::ApplicationModel::Resources::Core::IResourceMap **)(qword_1803A1F30 + 64),
                               a3);
        v9 = ResourceStringById;
        if ( ResourceStringById < 0 )
        {
          v18 = 758;
          goto LABEL_54;
        }
      }
      else
      {
        FileNameW = PathFindFileNameW(*(LPCWSTR *)v32.Data4);
        v29 = (SystemSettings::DataModel *)FileNameW;
        if ( FileNameW )
        {
          PathRemoveExtensionW(FileNameW);
          ResourceStringById = SystemSettings::DataModel::WindowsCreateString(v29, (const unsigned __int16 *)a3, v30);
          v9 = ResourceStringById;
          if ( ResourceStringById < 0 )
          {
            v18 = 767;
            goto LABEL_54;
          }
        }
        else
        {
          ResourceStringById = SystemSettings::DataModel::WindowsCreateString(
                                 *(SystemSettings::DataModel **)v32.Data4,
                                 (const unsigned __int16 *)a3,
                                 v28);
          v9 = ResourceStringById;
          if ( ResourceStringById < 0 )
          {
            v18 = 771;
            goto LABEL_54;
          }
        }
      }
    }
LABEL_55:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v32.Data4);
    return 0;
  }
  v8 = GetResourceStringById(
         L"SystemSettings_Personalize_Themes_Slideshow",
         *(struct Windows::ApplicationModel::Resources::Core::IResourceMap **)(qword_1803A1F30 + 64),
         a3);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B7,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\themehelper.cpp",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
    return v9;
  }
  return 0;
}

```

## disassembly

```asm
0x18011045c  mov     [rsp-8+arg_0], rbx
0x180110461  mov     [rsp-8+arg_18], rsi
0x180110466  push    rbp
0x180110467  push    rdi
0x180110468  push    r14
0x18011046a  lea     rbp, [rsp-180h]
0x180110472  sub     rsp, 280h
0x180110479  mov     rax, cs:__security_cookie
0x180110480  xor     rax, rsp
0x180110483  mov     [rbp+190h+var_20], rax
0x18011048a  mov     rdi, r8
0x18011048d  mov     rsi, rdx
0x180110490  mov     [rsp+290h+var_250], 0
0x180110498  mov     [rsp+290h+var_24C], 0
0x1801104a0  mov     rax, [rdx]
0x1801104a3  lea     rdx, [rsp+290h+var_250]
0x1801104a8  mov     rcx, rsi
0x1801104ab  mov     rax, [rax+108h]
0x1801104b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801104b7  mov     r14d, eax
0x1801104ba  test    eax, eax
0x1801104bc  jns     short loc_1801104E1
0x1801104be  mov     edx, 2B1h; void *
0x1801104c3  lea     r8, aShellSystemset_30; "shell\\systemsettingsthreshold\\handler"...
0x1801104ca  mov     r9d, r14d; char *
0x1801104cd  mov     rcx, [rbp+198h]; this
0x1801104d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801104d9  mov     eax, r14d
0x1801104dc  jmp     loc_180110996
0x1801104e1  mov     rax, [rsi]
0x1801104e4  lea     rdx, [rsp+290h+var_24C]
0x1801104e9  mov     rcx, rsi
0x1801104ec  mov     rax, [rax+1B0h]
0x1801104f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801104f8  mov     r14d, eax
0x1801104fb  test    eax, eax
0x1801104fd  jns     short loc_180110506
0x1801104ff  mov     edx, 2B2h
0x180110504  jmp     short loc_1801104C3
0x180110506  call    ?s_PolicyAllowsSlideshow@CSlideshowSettings@@SAJXZ; CSlideshowSettings::s_PolicyAllowsSlideshow(void)
0x18011050b  test    eax, eax
0x18011050d  jnz     short loc_180110515
0x18011050f  cmp     [rsp+290h+var_250], eax
0x180110513  jnz     short loc_18011051C
0x180110515  cmp     [rsp+290h+var_24C], 0
0x18011051a  jz      short loc_180110562
0x18011051c  mov     r8, rdi; HSTRING *
0x18011051f  mov     rdx, cs:qword_1803A1F30
0x180110526  mov     rdx, [rdx+40h]; struct Windows::ApplicationModel::Resources::Core::IResourceMap *
0x18011052a  lea     rcx, aSystemsettings_1502; "SystemSettings_Personalize_Themes_Slide"...
0x180110531  call    ?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z; GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)
0x180110536  mov     edi, eax
0x180110538  test    eax, eax
0x18011053a  jns     loc_180110994
0x180110540  mov     rcx, [rbp+198h]; this
0x180110547  mov     r9d, eax; char *
0x18011054a  lea     r8, aShellSystemset_30; "shell\\systemsettingsthreshold\\handler"...
0x180110551  mov     edx, 2B7h; void *
0x180110556  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011055b  mov     eax, edi
0x18011055d  jmp     loc_180110996
0x180110562  mov     qword ptr [rsp+290h+var_260.Data4], 0
0x18011056b  mov     rax, [rsi]
0x18011056e  lea     rdx, [rsp+290h+var_260.Data4]
0x180110573  mov     rcx, rsi
0x180110576  mov     rax, [rax+0A8h]
0x18011057d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110582  test    eax, eax
0x180110584  js      loc_18011093F
0x18011058a  mov     rdx, qword ptr [rsp+290h+var_260.Data4]; unsigned __int16 *
0x18011058f  call    ?DoesBackgroundImageExist@ThemeHelper@Personalization@SystemSettings@@AEAA_NPEBG@Z; SystemSettings::Personalization::ThemeHelper::DoesBackgroundImageExist(ushort const *)
0x180110594  test    al, al
0x180110596  jnz     loc_18011093F
0x18011059c  mov     r14, [rbp+198h]
0x1801105a3  mov     r8d, 104h
0x1801105a9  lea     rdx, [rsp+290h+String2]
0x1801105ae  lea     rcx, aSystemrootWebW; "%SystemRoot%\\web\\wallpaper\\windows\\"...
0x1801105b5  call    cs:__imp_SHExpandEnvironmentStringsW
0x1801105bc  nop     dword ptr [rax+rax+00h]
0x1801105c1  lea     rbx, aShellSystemset_30; "shell\\systemsettingsthreshold\\handler"...
0x1801105c8  test    eax, eax
0x1801105ca  jnz     loc_1801106B0
0x1801105d0  mov     r8, rbx; unsigned int
0x1801105d3  mov     edx, 2C6h; void *
0x1801105d8  mov     rcx, r14; this
0x1801105db  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1801105e0  mov     r14, [rbp+198h]
0x1801105e7  mov     r8d, 104h
0x1801105ed  lea     rdx, [rsp+290h+String2]
0x1801105f2  lea     rcx, aSystemrootWebW_0; "%SystemRoot%\\web\\wallpaper\\windows\\"...
0x1801105f9  call    cs:__imp_SHExpandEnvironmentStringsW
0x180110600  nop     dword ptr [rax+rax+00h]
0x180110605  test    eax, eax
0x180110607  jnz     loc_180110745
0x18011060d  mov     r8, rbx; unsigned int
0x180110610  mov     edx, 2D2h; void *
0x180110615  mov     rcx, r14; this
0x180110618  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18011061d  xorps   xmm0, xmm0
0x180110620  movups  [rsp+290h+var_248], xmm0
0x180110625  call    ?ShouldEnableEduThemes@EduThemeHelpers@@YA_NXZ; EduThemeHelpers::ShouldEnableEduThemes(void)
0x18011062a  test    al, al
0x18011062c  jz      loc_180110887
0x180110632  mov     rax, [rsi]
0x180110635  lea     rdx, [rsp+290h+var_248]
0x18011063a  mov     rcx, rsi
0x18011063d  mov     rax, [rax+78h]
0x180110641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110646  test    eax, eax
0x180110648  js      loc_180110887
0x18011064e  lea     rcx, [rsp+290h+var_248]; this
0x180110653  call    ?IsEduTheme@EduThemeHelpers@@YA_NAEBU_GUID@@@Z; EduThemeHelpers::IsEduTheme(_GUID const &)
0x180110658  test    al, al
0x18011065a  jz      loc_180110887
0x180110660  mov     [rsp+290h+var_260.Data1], 1
0x180110668  lea     rdx, [rsp+290h+var_260]; struct _GUID *
0x18011066d  lea     rcx, [rsp+290h+var_248]; this
0x180110672  call    ?IsEduThemeWithType@EduThemeHelpers@@YA_NAEBU_GUID@@AEBW4EduThemeTypes@@@Z; EduThemeHelpers::IsEduThemeWithType(_GUID const &,EduThemeTypes const &)
0x180110677  test    al, al
0x180110679  jz      loc_1801107DA
0x18011067f  mov     r8, rdi; HSTRING *
0x180110682  mov     rdx, cs:qword_1803A1F30
0x180110689  mov     rdx, [rdx+40h]; struct Windows::ApplicationModel::Resources::Core::IResourceMap *
0x18011068d  lea     rcx, aSystemsettings_366; "SystemSettings_Personalize_Themes_Defau"...
0x180110694  call    ?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z; GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)
0x180110699  mov     edi, eax
0x18011069b  test    eax, eax
0x18011069d  jns     loc_18011098A
0x1801106a3  mov     r8, rbx
0x1801106a6  mov     edx, 2E4h
0x1801106ab  jmp     loc_18011096B
0x1801106b0  mov     [rsp+290h+bIgnoreCase], 1; bIgnoreCase
0x1801106b8  or      r9d, 0FFFFFFFFh; cchCount2
0x1801106bc  lea     r8, [rsp+290h+String2]; lpString2
0x1801106c1  or      edx, r9d; cchCount1
0x1801106c4  mov     rcx, qword ptr [rsp+290h+var_260.Data4]; lpString1
0x1801106c9  call    cs:__imp_CompareStringOrdinal
0x1801106d0  nop     dword ptr [rax+rax+00h]
0x1801106d5  cmp     eax, 2
0x1801106d8  jnz     loc_1801105E0
0x1801106de  lea     ecx, [rax+1Bh]; dwOS
0x1801106e1  call    cs:__imp_IsOS
0x1801106e8  nop     dword ptr [rax+rax+00h]
0x1801106ed  mov     r8, rdi; HSTRING *
0x1801106f0  mov     rdx, cs:qword_1803A1F30
0x1801106f7  mov     rdx, [rdx+40h]; struct Windows::ApplicationModel::Resources::Core::IResourceMap *
0x1801106fb  test    eax, eax
0x1801106fd  jz      short loc_180110722
0x1801106ff  lea     rcx, aSystemsettings_1349; "SystemSettings_Personalize_Themes_Defau"...
0x180110706  call    ?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z; GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)
0x18011070b  mov     edi, eax
0x18011070d  test    eax, eax
0x18011070f  jns     loc_18011098A
0x180110715  mov     r8, rbx
0x180110718  mov     edx, 2CBh
0x18011071d  jmp     loc_18011096B
0x180110722  lea     rcx, aSystemsettings_1361; "SystemSettings_Personalize_Themes_Defau"...
0x180110729  call    ?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z; GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)
0x18011072e  mov     edi, eax
0x180110730  test    eax, eax
0x180110732  jns     loc_18011098A
0x180110738  mov     r8, rbx
0x18011073b  mov     edx, 2CFh
0x180110740  jmp     loc_18011096B
0x180110745  mov     [rsp+290h+bIgnoreCase], 1; bIgnoreCase
0x18011074d  or      r9d, 0FFFFFFFFh; cchCount2
0x180110751  lea     r8, [rsp+290h+String2]; lpString2
0x180110756  or      edx, r9d; cchCount1
0x180110759  mov     rcx, qword ptr [rsp+290h+var_260.Data4]; lpString1
0x18011075e  call    cs:__imp_CompareStringOrdinal
0x180110765  nop     dword ptr [rax+rax+00h]
0x18011076a  cmp     eax, 2
0x18011076d  jnz     loc_18011061D
0x180110773  lea     ecx, [rax+1Bh]; dwOS
0x180110776  call    cs:__imp_IsOS
0x18011077d  nop     dword ptr [rax+rax+00h]
0x180110782  mov     r8, rdi; HSTRING *
0x180110785  mov     rdx, cs:qword_1803A1F30
0x18011078c  mov     rdx, [rdx+40h]; struct Windows::ApplicationModel::Resources::Core::IResourceMap *
0x180110790  test    eax, eax
0x180110792  jz      short loc_1801107B7
0x180110794  lea     rcx, aSystemsettings_1349; "SystemSettings_Personalize_Themes_Defau"...
0x18011079b  call    ?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z; GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)
0x1801107a0  mov     edi, eax
0x1801107a2  test    eax, eax
0x1801107a4  jns     loc_18011098A
0x1801107aa  mov     r8, rbx
0x1801107ad  mov     edx, 2D7h
0x1801107b2  jmp     loc_18011096B
0x1801107b7  lea     rcx, aSystemsettings_114; "SystemSettings_Personalize_Themes_Defau"...
0x1801107be  call    ?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z; GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)
0x1801107c3  mov     edi, eax
0x1801107c5  test    eax, eax
0x1801107c7  jns     loc_18011098A
0x1801107cd  mov     r8, rbx
0x1801107d0  mov     edx, 2DBh
0x1801107d5  jmp     loc_18011096B
0x1801107da  mov     [rsp+290h+var_260.Data1], 2
0x1801107e2  lea     rdx, [rsp+290h+var_260]; struct _GUID *
0x1801107e7  lea     rcx, [rsp+290h+var_248]; this
0x1801107ec  call    ?IsEduThemeWithType@EduThemeHelpers@@YA_NAEBU_GUID@@AEBW4EduThemeTypes@@@Z; EduThemeHelpers::IsEduThemeWithType(_GUID const &,EduThemeTypes const &)
0x1801107f1  test    al, al
0x1801107f3  jz      short loc_180110826
0x1801107f5  mov     r8, rdi; HSTRING *
0x1801107f8  mov     rdx, cs:qword_1803A1F30
0x1801107ff  mov     rdx, [rdx+40h]; struct Windows::ApplicationModel::Resources::Core::IResourceMap *
0x180110803  lea     rcx, aSystemsettings_706; "SystemSettings_Personalize_Themes_Plane"...
0x18011080a  call    ?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z; GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)
0x18011080f  mov     edi, eax
0x180110811  test    eax, eax
0x180110813  jns     loc_18011098A
0x180110819  mov     r8, rbx
0x18011081c  mov     edx, 2E8h
0x180110821  jmp     loc_18011096B
0x180110826  mov     [rsp+290h+var_260.Data1], 4
0x18011082e  lea     rdx, [rsp+290h+var_260]; struct _GUID *
0x180110833  lea     rcx, [rsp+290h+var_248]; this
0x180110838  call    ?IsEduThemeWithType@EduThemeHelpers@@YA_NAEBU_GUID@@AEBW4EduThemeTypes@@@Z; EduThemeHelpers::IsEduThemeWithType(_GUID const &,EduThemeTypes const &)
0x18011083d  test    al, al
0x18011083f  jz      short loc_180110872
0x180110841  mov     r8, rdi; HSTRING *
0x180110844  mov     rdx, cs:qword_1803A1F30
0x18011084b  mov     rdx, [rdx+40h]; struct Windows::ApplicationModel::Resources::Core::IResourceMap *
0x18011084f  lea     rcx, aSystemsettingn; "SystemSettingNamePersonalize_Themes_Sun"...
0x180110856  call    ?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z; GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)
0x18011085b  mov     edi, eax
0x18011085d  test    eax, eax
0x18011085f  jns     loc_18011098A
0x180110865  mov     r8, rbx
0x180110868  mov     edx, 2ECh
0x18011086d  jmp     loc_18011096B
0x180110872  mov     rcx, [rbp+198h]; this
0x180110879  mov     r8, rbx; unsigned int
0x18011087c  mov     edx, 2F0h; void *
0x180110881  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180110887  xor     r8d, r8d
0x18011088a  mov     dl, 1
0x18011088c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DesktopSpotlight@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlight@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlight> `wil::Feature<__WilFeatureTraits_Feature_DesktopSpotlight>::GetImpl(void)'::`2'::impl
0x180110893  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DesktopSpotlight@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DesktopSpotlight>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180110898  lea     rcx, ?c_desktop@SubscriptionIds@TargetedContent@CreativeFramework@@3QBGB; "Desktop"
0x18011089f  call    ?IsSubscriptionEnabled@ConfigurationHelper@TargetedContent@CreativeFramework@@YA_NPEBG@Z; CreativeFramework::TargetedContent::ConfigurationHelper::IsSubscriptionEnabled(ushort const *)
0x1801108a4  test    al, al
0x1801108a6  jnz     short loc_180110915
0x1801108a8  call    ?IsUndockedDesktopSpotlightEnabled@ThemeHelper@Personalization@SystemSettings@@AEAA_NXZ; SystemSettings::Personalization::ThemeHelper::IsUndockedDesktopSpotlightEnabled(void)
0x1801108ad  test    al, al
0x1801108af  jnz     short loc_180110915
0x1801108b1  mov     rcx, qword ptr [rsp+290h+var_260.Data4]; pszPath
0x1801108b6  call    cs:__imp_PathFindFileNameW
0x1801108bd  nop     dword ptr [rax+rax+00h]
0x1801108c2  mov     rsi, rax
0x1801108c5  test    rax, rax
0x1801108c8  jz      short loc_1801108F8
0x1801108ca  mov     rcx, rax; pszPath
0x1801108cd  call    cs:__imp_PathRemoveExtensionW
0x1801108d4  nop     dword ptr [rax+rax+00h]
0x1801108d9  mov     rdx, rdi; unsigned __int16 *
0x1801108dc  mov     rcx, rsi; this
0x1801108df  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x1801108e4  mov     edi, eax
0x1801108e6  test    eax, eax
0x1801108e8  jns     loc_18011098A
0x1801108ee  mov     r8, rbx
0x1801108f1  mov     edx, 2FFh
0x1801108f6  jmp     short loc_18011096B
0x1801108f8  mov     rdx, rdi; unsigned __int16 *
0x1801108fb  mov     rcx, qword ptr [rsp+290h+var_260.Data4]; this
0x180110900  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x180110905  mov     edi, eax
0x180110907  test    eax, eax
0x180110909  jns     short loc_18011098A
0x18011090b  mov     r8, rbx
0x18011090e  mov     edx, 303h
0x180110913  jmp     short loc_18011096B
0x180110915  mov     r8, rdi; HSTRING *
0x180110918  mov     rdx, cs:qword_1803A1F30
0x18011091f  mov     rdx, [rdx+40h]; struct Windows::ApplicationModel::Resources::Core::IResourceMap *
0x180110923  lea     rcx, aSystemsettings_872; "SystemSettings_Personalize_Background_S"...
0x18011092a  call    ?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z; GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)
0x18011092f  mov     edi, eax
0x180110931  test    eax, eax
0x180110933  jns     short loc_18011098A
0x180110935  mov     r8, rbx
0x180110938  mov     edx, 2F6h
0x18011093d  jmp     short loc_18011096B
0x18011093f  mov     r8, rdi; HSTRING *
0x180110942  mov     rdx, cs:qword_1803A1F30
0x180110949  mov     rdx, [rdx+40h]; struct Windows::ApplicationModel::Resources::Core::IResourceMap *
0x18011094d  lea     rcx, aSystemsettings_1029; "SystemSettings_Personalize_Themes_Solid"...
0x180110954  call    ?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z; GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)
0x180110959  mov     edi, eax
0x18011095b  test    eax, eax
0x18011095d  jns     short loc_18011098A
0x18011095f  lea     r8, aShellSystemset_30; "shell\\systemsettingsthreshold\\handler"...
0x180110966  mov     edx, 30Ah; void *
0x18011096b  mov     r9d, eax; char *
0x18011096e  mov     rcx, [rbp+198h]; this
0x180110975  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011097a  nop
0x18011097b  lea     rcx, [rsp+290h+var_260.Data4]
0x180110980  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
  ... truncated ...
```
