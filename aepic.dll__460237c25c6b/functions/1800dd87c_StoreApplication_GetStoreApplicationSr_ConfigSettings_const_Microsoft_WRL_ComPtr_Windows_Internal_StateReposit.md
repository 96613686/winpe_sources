# StoreApplication::GetStoreApplicationSr(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)

- ea: `0x1800dd87c`
- end: `0x1800de634`
- name: `?GetStoreApplicationSr@StoreApplication@@QEAAXAEBVConfigSettings@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `3512`
- prototype: `__int64 __fastcall(Application *this, struct ConfigSettings *)`
- caller_count: `1`
- callee_count: `48`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d78b4`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18000f0bc`
- `0x18000faf0`
- `0x18001082c`
- `0x1800108a8`
- `0x18001c5f0`
- `0x18001c6d8`
- `0x18001df50`
- `0x18002248c`
- `0x1800224dc`
- `0x1800295dc`
- `0x1800c1d68`
- `0x1800c224c`
- `0x1800c2404`
- `0x1800c30d4`
- `0x1800c3280`
- `0x1800c3478`
- `0x1800c83e0`
- `0x1800c97f0`
- `0x1800c993c`
- `0x1800ca928`
- `0x1800cea08`
- `0x1800d05d0`
- `0x1800d0e00`
- `0x1800d0fb0`
- `0x1800d18a0`
- `0x1800d2ccc`
- `0x1800d5110`
- `0x1800d5388`
- `0x1800d541c`
- `0x1800d5470`
- `0x1800d54c4`
- `0x1800d579c`
- `0x1800d57c4`
- `0x1800d57ec`
- `0x1800d8684`
- `0x1800d9cd0`
- `0x1800da084`
- `0x1800dae40`
- `0x1800db168`
- `0x1800db8b8`
- `0x1800dbff4`
- `0x1800dc490`
- `0x1800dc75c`
- `0x1800dd87c`
- `0x1800dffc4`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ddad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ddc8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800de032`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ddad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ddc8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800de032`

## string_xrefs

- `0x1800dd904`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dd94c`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dd9e4`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dda2d`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800ddab7`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800ddc75`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800ddf45`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800ddfae`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800de019`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=49
__int64 __fastcall StoreApplication::GetStoreApplicationSr(Application *this, struct ConfigSettings *a2, HSTRING *a3)
{
  HSTRING *v3; // r14
  HSTRING v6; // rdi
  __int64 (__fastcall *v7)(HSTRING, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  PCWSTR StringRawBuffer; // rax
  HSTRING v20; // rcx
  int StoreAppLanguageSr; // edi
  _QWORD *v22; // rcx
  int *v23; // rax
  const struct ConfigSettings *v24; // rdx
  unsigned int v25; // r12d
  HSTRING v26; // rdi
  __int64 (__fastcall *v27)(HSTRING, HSTRING *); // rbx
  int v28; // eax
  PCWSTR v29; // rax
  __int64 ExtractedAppxPackagePath; // rax
  __int64 ExtractedAppxManifestPath; // rax
  __int64 v32; // rax
  __int64 StoreAppType; // rax
  __int64 ExtractedAppxBundlePath; // rax
  struct File **v35; // rcx
  HSTRING v36; // rcx
  __int64 StoreAppInstallLocationFromPackageSr; // rax
  HSTRING v38; // rcx
  __int64 v39; // rax
  HSTRING v40; // rcx
  HSTRING v41; // rcx
  __int64 StoreAppTypeSr; // rax
  HSTRING v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  HSTRING v46; // rbx
  int v47; // eax
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, HSTRING *); // rbx
  int v50; // eax
  PCWSTR v51; // rax
  __int64 v52; // rax
  HSTRING v53; // rcx
  __int64 StoreAppManifestPathFromPackageSr; // rax
  HSTRING v55; // rcx
  __int64 v56; // rax
  int v57; // ebx
  int v58; // eax
  const struct File *v59; // rdi
  _QWORD *v60; // rax
  __int64 i; // rbx
  __int64 v62; // r12
  HSTRING v63; // rcx
  HSTRING v64; // rcx
  __int64 result; // rax
  int v66; // [rsp+20h] [rbp-E0h]
  int v67; // [rsp+20h] [rbp-E0h]
  int v68; // [rsp+20h] [rbp-E0h]
  char v69; // [rsp+40h] [rbp-C0h] BYREF
  char v70; // [rsp+41h] [rbp-BFh]
  HSTRING v71; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v72; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v73; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v74; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v75; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  __int64 v77; // [rsp+78h] [rbp-88h] BYREF
  __int128 v78; // [rsp+80h] [rbp-80h] BYREF
  __int64 v79; // [rsp+90h] [rbp-70h]
  __int64 v80; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v81[2]; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING *v82; // [rsp+B0h] [rbp-50h]
  _OWORD v83[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v84; // [rsp+D8h] [rbp-28h] BYREF
  __m128i v85; // [rsp+E8h] [rbp-18h]
  __int128 v86; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v87; // [rsp+108h] [rbp+8h]
  struct File *v88[2]; // [rsp+118h] [rbp+18h] BYREF
  __m128i si128; // [rsp+128h] [rbp+28h]
  _QWORD v90[4]; // [rsp+138h] [rbp+38h] BYREF
  int v91[2]; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int64 v92; // [rsp+170h] [rbp+70h]
  _BYTE v93[16]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v94; // [rsp+188h] [rbp+88h]
  wchar_t Buffer[16]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v96[40]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v97[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v98[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v99[24]; // [rsp+220h] [rbp+120h] BYREF
  _QWORD v100[80]; // [rsp+238h] [rbp+138h] BYREF
  char v101[32]; // [rsp+4B8h] [rbp+3B8h] BYREF
  char v102[120]; // [rsp+4D8h] [rbp+3D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+598h] [rbp+498h]

  v3 = a3;
  v82 = a3;
  v78 = 0;
  v79 = 0;
  v73 = 0;
  v74 = 0;
  v6 = *a3;
  v7 = *(__int64 (__fastcall **)(HSTRING, __int64 *))(*(_QWORD *)*a3 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  v8 = v7(v6, &v73);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v8,
      v66);
  v9 = v73;
  v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 64LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v74,
    0);
  v11 = v10(v9, &v74);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v11,
      v66);
  StoreApplication::GetLocalizedStringValue(v93, v74);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_EmptyPackageName>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_EmptyPackageName>::GetImpl'::`2'::impl)
    || v94 )
  {
    v77 = 0;
    v12 = v73;
    v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 72LL);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v77,
      0);
    v14 = v13(v12, &v77);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x17F,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v14,
        v66);
    StoreApplication::GetLocalizedStringValue(v96, v77);
    v80 = 0;
    v15 = (*(__int64 (__fastcall **)(HSTRING, __int64 *))(*(_QWORD *)*v3 + 104LL))(*v3, &v80);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v15,
        v66);
    v67 = WORD1(v80);
    Utility::FormatWstring(Buffer, (wchar_t *)L"%hu.%hu.%hu.%hu");
    string = 0;
    v16 = v73;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v73 + 88LL);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &string,
      0);
    v18 = v17(v16, &string);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x18D,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v18,
        v67);
    v70 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(v91, StringRawBuffer);
    std::wstring::operator=((char *)this + 776, v91);
    v20 = *v3;
    v71 = v20;
    if ( v20 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v20 + 8LL))(v20);
    StoreAppLanguageSr = StoreApplication::GetStoreAppLanguageSr();
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
    Application::ComputeProgramId(
      (unsigned int)v90,
      (unsigned int)v93,
      (unsigned int)v96,
      (unsigned int)Buffer,
      StoreAppLanguageSr);
    v22 = v90;
    if ( v90[3] > 7u )
      v22 = (_QWORD *)v90[0];
    v23 = v91;
    if ( v92 > 7 )
      v23 = *(int **)v91;
    AslLogCallPrintf(3, "StoreApplication::GetStoreApplicationSr", 409, "%ws | %ws", v23, v22);
    v25 = *((_DWORD *)a2 + 56);
    if ( !Application::ForceFullAppScan && v25 > 1 )
      Application::GetApplicationFromCache(this);
    if ( Application::IsValid(this, v24) )
    {
      if ( !*((_QWORD *)this + 115) )
      {
        *(_OWORD *)v88 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v88[0]) = 0;
        v53 = *v3;
        v71 = v53;
        if ( v53 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v53 + 8LL))(v53);
        StoreAppManifestPathFromPackageSr = StoreApplication::GetStoreAppManifestPathFromPackageSr(v83, &v71, 1);
        std::wstring::operator=(v88, StoreAppManifestPathFromPackageSr);
        std::wstring::_Tidy_deallocate(v83);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
        std::wstring::operator=((char *)this + 904, v88);
        v84 = 0;
        v85 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v84) = 0;
        v55 = *v3;
        v71 = v55;
        if ( v55 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v55 + 8LL))(v55);
        v56 = StoreApplication::GetStoreAppManifestPathFromPackageSr(v83, &v71, 2);
        std::wstring::operator=(&v84, v56);
        std::wstring::_Tidy_deallocate(v83);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
        std::wstring::operator=((char *)this + 936, &v84);
        std::wstring::_Tidy_deallocate(&v84);
        std::wstring::_Tidy_deallocate(v88);
      }
    }
    else
    {
      Application::SetName(this, v93);
      Application::SetPublisher(this, v96);
      Application::SetVersion(this, Buffer);
      *((_DWORD *)this + 116) = StoreAppLanguageSr;
      std::wstring::operator=((char *)this + 56, v90);
      std::wstring::operator=((char *)this + 776, v91);
      std::wstring::operator=((char *)this + 336, &Application::ApplicationSourceAppxPackage);
      std::wstring::operator=((char *)this + 368, Application::ApplicationTypeApplication);
      v71 = 0;
      v26 = *v3;
      v27 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*v3 + 112LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &v71,
        0);
      v28 = v27(v26, &v71);
      if ( v28 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1B8,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v28,
          v68);
      v29 = WindowsGetStringRawBuffer(v71, 0);
      std::wstring::wstring(v83, v29);
      std::wstring::operator=((char *)this + 744, v83);
      if ( v25 )
      {
        v36 = *v3;
        v72 = v36;
        if ( v36 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v36 + 8LL))(v36);
        StoreAppInstallLocationFromPackageSr = StoreApplication::GetStoreAppInstallLocationFromPackageSr(&v84, &v72);
        Application::SetInstallLocation(this, StoreAppInstallLocationFromPackageSr);
        std::wstring::_Tidy_deallocate(&v84);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
        *(_OWORD *)v88 = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v88[0]) = 0;
        v38 = *v3;
        v72 = v38;
        if ( v38 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v38 + 8LL))(v38);
        v39 = StoreApplication::GetStoreAppManifestPathFromPackageSr(&v84, &v72, 1);
        std::wstring::operator=(v88, v39);
        std::wstring::_Tidy_deallocate(&v84);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
        std::wstring::operator=((char *)this + 904, v88);
        v40 = *v3;
        v72 = v40;
        if ( v40 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v40 + 8LL))(v40);
        StoreApplication::GetPackageRelativeAppIDsSr(&v72, &v78);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
        v41 = *v3;
        v72 = v41;
        if ( v41 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v41 + 8LL))(v41);
        StoreAppTypeSr = StoreApplication::GetStoreAppTypeSr(&v84, &v72);
        std::wstring::operator=((char *)this + 808, StoreAppTypeSr);
        std::wstring::_Tidy_deallocate(&v84);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
        v84 = 0;
        v85 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v84) = 0;
        v43 = *v3;
        v72 = v43;
        if ( v43 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v43 + 8LL))(v43);
        v44 = StoreApplication::GetStoreAppManifestPathFromPackageSr(&v86, &v72, 2);
        std::wstring::operator=(&v84, v44);
        std::wstring::_Tidy_deallocate(&v86);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
        std::wstring::operator=((char *)this + 936, &v84);
        v69 = 0;
        v45 = (*(__int64 (__fastcall **)(HSTRING, char *))(*(_QWORD *)*v3 + 120LL))(*v3, &v69);
        if ( v45 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1E2,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)(unsigned int)v45,
            v68);
        *((_BYTE *)this + 968) = v69 != 0;
        v46 = *v3;
        v81[0] = v46;
        if ( v46 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v46 + 8LL))(v46);
        LODWORD(v72) = 0;
        v47 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v46 + 128LL))(v46, &v72);
        if ( v47 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x2E6,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)(unsigned int)v47,
            v68);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v81);
        *((_BYTE *)this + 969) = ((unsigned __int8)v72 & 2) != 0;
        v75 = 0;
        v48 = v73;
        v49 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v73 + 64LL);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          &v75,
          0);
        v50 = v49(v48, &v75);
        if ( v50 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1EB,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)(unsigned int)v50,
            v68);
        v51 = WindowsGetStringRawBuffer(v75, 0);
        std::wstring::wstring(&v86, v51);
        std::wstring::operator=((char *)this + 712, &v86);
        std::wstring::_Tidy_deallocate(&v86);
        v52 = Application::ComputeProgramInstanceId(this, &v86);
        std::wstring::operator=((char *)this + 400, v52);
        std::wstring::_Tidy_deallocate(&v86);
        v70 = 1;
        Windows::Internal::String::~String((Windows::Internal::String *)&v75);
        std::wstring::_Tidy_deallocate(&v84);
        v35 = v88;
      }
      else
      {
        ExtractedAppxPackagePath = ConfigSettings::GetExtractedAppxPackagePath(a2, &v84);
        Application::SetInstallLocation(this, ExtractedAppxPackagePath);
        std::wstring::_Tidy_deallocate(&v84);
        ExtractedAppxManifestPath = ConfigSettings::GetExtractedAppxManifestPath(a2, &v84);
        std::wstring::operator=((char *)this + 904, ExtractedAppxManifestPath);
        std::wstring::_Tidy_deallocate(&v84);
        v32 = ConfigSettings::GetExtractedAppxManifestPath(a2, v88);
        StoreAppType = StoreApplication::GetStoreAppType(&v84, v32);
        std::wstring::operator=((char *)this + 808, StoreAppType);
        std::wstring::_Tidy_deallocate(&v84);
        std::wstring::_Tidy_deallocate(v88);
        ExtractedAppxBundlePath = ConfigSettings::GetExtractedAppxBundlePath(a2, &v84);
        std::wstring::operator=((char *)this + 936, ExtractedAppxBundlePath);
        v35 = (struct File **)&v84;
      }
      std::wstring::_Tidy_deallocate(v35);
      std::wstring::_Tidy_deallocate(v83);
      Windows::Internal::String::~String((Windows::Internal::String *)&v71);
    }
    if ( *((_DWORD *)a2 + 2) != 5 && v25 != 2 )
    {
      v86 = 0;
      v87 = 0;
      std::wstring::wstring(v83, L".exe");
      std::vector<std::wstring>::push_back(&v86, v83);
      std::wstring::_Tidy_deallocate(v83);
      if ( *((_DWORD *)a2 + 2) == 1 )
      {
        std::wstring::wstring(v83, L".dll");
        std::vector<std::wstring>::push_back(&v86, v83);
        std::wstring::_Tidy_deallocate(v83);
        std::wstring::wstring(v83, L".js");
        std::vector<std::wstring>::push_back(&v86, v83);
        std::wstring::_Tidy_deallocate(v83);
        std::wstring::wstring(v83, L".pri");
        std::vector<std::wstring>::push_back(&v86, v83);
        std::wstring::_Tidy_deallocate(v83);
        std::wstring::wstring(v83, L".htm");
        std::vector<std::wstring>::push_back(&v86, v83);
        std::wstring::_Tidy_deallocate(v83);
        std::wstring::wstring(v83, L".html");
        std::vector<std::wstring>::push_back(&v86, v83);
        std::wstring::_Tidy_deallocate(v83);
        std::wstring::wstring(v83, L".xhtml");
        std::vector<std::wstring>::push_back(&v86, v83);
        std::wstring::_Tidy_deallocate(v83);
        std::wstring::wstring(v83, L".winmd");
        std::vector<std::wstring>::push_back(&v86, v83);
        std::wstring::_Tidy_deallocate(v83);
      }
      v81[0] = &v84;
      v57 = std::vector<std::wstring>::vector<std::wstring>(&v84, &v86);
      v58 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 2) + 40LL))((char *)this + 16);
      File::SearchForPeFiles((unsigned int)v88, (_DWORD)a2, v58, v57, v68, (__int64)v90);
      v59 = v88[0];
      if ( v88[0] != v88[1] )
      {
        do
        {
          File::File((File *)v99, v59);
          v60 = v100;
          if ( v100[3] > 7u )
            v60 = (_QWORD *)v100[0];
          AslLogCallPrintf(3, "StoreApplication::GetStoreApplicationSr", 539, "%ws", v60);
          Utility::ToLower(v83, v100);
          v62 = *((_QWORD *)&v78 + 1);
          for ( i = v78; i != v62; i += 64 )
          {
            std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(v97, i);
            if ( std::wstring::find(v83, v98) != -1 )
            {
              std::wstring::operator=(v102, v97);
              std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v97);
              break;
            }
            std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v97);
          }
          std::wstring::operator=(v101, (char *)this + 744);
          std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::emplace<File &>(
            (char *)this + 24,
            v81,
            v99);
          std::wstring::_Tidy_deallocate(v83);
          File::~File((File *)v99);
          v59 = (const struct File *)((char *)v59 + 816);
        }
        while ( v59 != v88[1] );
        v3 = v82;
      }
      std::vector<File>::_Tidy(v88);
      std::vector<std::wstring>::_Tidy(&v86);
    }
    if ( v70 )
      Application::SaveApplicationToCache(this, a2);
    if ( *((_BYTE *)a2 + 220) )
    {
      v63 = *v3;
      v71 = v63;
      if ( v63 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v63 + 8LL))(v63);
      StoreApplication::GetStoreAppManifestXmlSr(&v84, &v71, 1);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
      std::wstring::operator=((char *)this + 840, &v84);
      v64 = *v3;
      v71 = v64;
      if ( v64 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v64 + 8LL))(v64);
      StoreApplication::GetStoreAppManifestXmlSr(v83, &v71, 0);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71);
      std::wstring::operator=((char *)this + 872, v83);
      std::wstring::_Tidy_deallocate(v83);
      std::wstring::_Tidy_deallocate(&v84);
    }
    std::wstring::_Tidy_deallocate(v90);
    std::wstring::_Tidy_deallocate(v91);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    std::wstring::_Tidy_deallocate(Buffer);
    std::wstring::_Tidy_deallocate(v96);
    Windows::Internal::String::~String((Windows::Internal::String *)&v77);
  }
  else
  {
    AslLogCallPrintf(1, "StoreApplication::GetStoreApplicationSr", 376, "Name is empty.");
  }
  std::wstring::_Tidy_deallocate(v93);
  Windows::Internal::String::~String((Windows::Internal::String *)&v74);
  result = Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
  if ( (_QWORD)v78 )
  {
    std::_Destroy_range<std::allocator<std::pair<std::wstring,std::wstring>>>(v78, *((_QWORD *)&v78 + 1));
    return std::_Deallocate<16>(v78, (v79 - v78) & 0xFFFFFFFFFFFFFFC0uLL);
  }
  return result;
}

```

## disassembly

```asm
0x1800dd87c  mov     [rsp-8+arg_18], rbx
0x1800dd881  push    rbp
0x1800dd882  push    rsi
0x1800dd883  push    rdi
0x1800dd884  push    r12
0x1800dd886  push    r13
0x1800dd888  push    r14
0x1800dd88a  push    r15
0x1800dd88c  lea     rbp, [rsp-460h]
0x1800dd894  sub     rsp, 560h
0x1800dd89b  mov     rax, cs:__security_cookie
0x1800dd8a2  xor     rax, rsp
0x1800dd8a5  mov     [rbp+490h+var_40], rax
0x1800dd8ac  mov     r14, r8
0x1800dd8af  mov     [rbp+490h+var_4E0], r8
0x1800dd8b3  mov     r13, rdx
0x1800dd8b6  mov     rsi, rcx
0x1800dd8b9  xorps   xmm0, xmm0
0x1800dd8bc  movdqu  [rbp+490h+var_510], xmm0
0x1800dd8c1  xor     r12d, r12d
0x1800dd8c4  mov     [rbp+490h+var_500], r12
0x1800dd8c8  mov     [rsp+590h+var_538], r12
0x1800dd8cd  mov     [rsp+590h+var_530], r12
0x1800dd8d2  mov     rdi, [r8]
0x1800dd8d5  mov     rax, [rdi]
0x1800dd8d8  mov     rbx, [rax+48h]
0x1800dd8dc  lea     rcx, [rsp+590h+var_538]
0x1800dd8e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dd8e6  lea     rdx, [rsp+590h+var_538]
0x1800dd8eb  mov     rcx, rdi
0x1800dd8ee  mov     rax, rbx
0x1800dd8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd8f6  mov     rcx, [rbp+498h]; this
0x1800dd8fd  test    eax, eax
0x1800dd8ff  jns     short loc_1800DD916
0x1800dd901  mov     r9d, eax; char *
0x1800dd904  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dd90b  mov     edx, 170h; void *
0x1800dd910  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dd916  mov     rdi, [rsp+590h+var_538]
0x1800dd91b  mov     rax, [rdi]
0x1800dd91e  mov     rbx, [rax+40h]
0x1800dd922  xor     edx, edx
0x1800dd924  lea     rcx, [rsp+590h+var_530]
0x1800dd929  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800dd92e  lea     rdx, [rsp+590h+var_530]
0x1800dd933  mov     rcx, rdi
0x1800dd936  mov     rax, rbx
0x1800dd939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd93e  mov     rcx, [rbp+498h]; this
0x1800dd945  test    eax, eax
0x1800dd947  jns     short loc_1800DD95E
0x1800dd949  mov     r9d, eax; char *
0x1800dd94c  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dd953  mov     edx, 171h; void *
0x1800dd958  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dd95e  mov     rdx, [rsp+590h+var_530]
0x1800dd963  lea     rcx, [rbp+490h+var_418]
0x1800dd967  call    ?GetLocalizedStringValue@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHSTRING__@@@Z; StoreApplication::GetLocalizedStringValue(HSTRING__ *)
0x1800dd96c  nop
0x1800dd96d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppInv_EmptyPackageName@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppInv_EmptyPackageName@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_EmptyPackageName> `wil::Feature<__WilFeatureTraits_Feature_AppInv_EmptyPackageName>::GetImpl(void)'::`2'::impl
0x1800dd974  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppInv_EmptyPackageName@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_EmptyPackageName>::__private_IsEnabled(void)
0x1800dd979  test    al, al
0x1800dd97b  jz      short loc_1800DD9A9
0x1800dd97d  cmp     [rbp+490h+var_408], r12
0x1800dd984  jnz     short loc_1800DD9A9
0x1800dd986  lea     r9, aNameIsEmpty; "Name is empty."
0x1800dd98d  mov     r8d, 178h
0x1800dd993  lea     rdx, aStoreapplicati_0; "StoreApplication::GetStoreApplicationSr"
0x1800dd99a  mov     ecx, 1
0x1800dd99f  call    AslLogCallPrintf
0x1800dd9a4  jmp     loc_1800DE5C4
0x1800dd9a9  mov     [rsp+590h+var_518], r12
0x1800dd9ae  mov     rdi, [rsp+590h+var_538]
0x1800dd9b3  mov     rax, [rdi]
0x1800dd9b6  mov     rbx, [rax+48h]
0x1800dd9ba  xor     edx, edx
0x1800dd9bc  lea     rcx, [rsp+590h+var_518]
0x1800dd9c1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800dd9c6  lea     rdx, [rsp+590h+var_518]
0x1800dd9cb  mov     rcx, rdi
0x1800dd9ce  mov     rax, rbx
0x1800dd9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd9d6  mov     rcx, [rbp+498h]; this
0x1800dd9dd  test    eax, eax
0x1800dd9df  jns     short loc_1800DD9F6
0x1800dd9e1  mov     r9d, eax; char *
0x1800dd9e4  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dd9eb  mov     edx, 17Fh; void *
0x1800dd9f0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dd9f6  mov     rdx, [rsp+590h+var_518]
0x1800dd9fb  lea     rcx, [rbp+490h+var_3D8]
0x1800dda02  call    ?GetLocalizedStringValue@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHSTRING__@@@Z; StoreApplication::GetLocalizedStringValue(HSTRING__ *)
0x1800dda07  nop
0x1800dda08  mov     [rbp+490h+var_4F8], r12
0x1800dda0c  mov     rcx, [r14]
0x1800dda0f  mov     rax, [rcx]
0x1800dda12  lea     rdx, [rbp+490h+var_4F8]
0x1800dda16  mov     rax, [rax+68h]
0x1800dda1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dda1f  mov     rcx, [rbp+498h]; this
0x1800dda26  test    eax, eax
0x1800dda28  jns     short loc_1800DDA3F
0x1800dda2a  mov     r9d, eax; char *
0x1800dda2d  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dda34  mov     edx, 184h; void *
0x1800dda39  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dda3f  mov     r8, [rbp+490h+var_4F8]
0x1800dda43  movzx   edx, r8w
0x1800dda47  mov     rax, r8
0x1800dda4a  shr     rax, 10h
0x1800dda4e  movzx   ecx, ax
0x1800dda51  mov     rax, r8
0x1800dda54  shr     rax, 20h
0x1800dda58  movzx   r9d, ax
0x1800dda5c  shr     r8, 30h
0x1800dda60  mov     dword ptr [rsp+590h+var_568], edx
0x1800dda64  mov     [rsp+590h+var_570], ecx; int
0x1800dda68  lea     rdx, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x1800dda6f  lea     rcx, [rbp+490h+Buffer]; Buffer
0x1800dda76  call    ?FormatWstring@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Utility::FormatWstring(ushort const *,...)
0x1800dda7b  nop
0x1800dda7c  mov     [rsp+590h+string], r12
0x1800dda81  mov     rdi, [rsp+590h+var_538]
0x1800dda86  mov     rax, [rdi]
0x1800dda89  mov     rbx, [rax+58h]
0x1800dda8d  xor     edx, edx
0x1800dda8f  lea     rcx, [rsp+590h+string]
0x1800dda94  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800dda99  lea     rdx, [rsp+590h+string]
0x1800dda9e  mov     rcx, rdi
0x1800ddaa1  mov     rax, rbx
0x1800ddaa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddaa9  mov     rcx, [rbp+498h]; this
0x1800ddab0  test    eax, eax
0x1800ddab2  jns     short loc_1800DDAC9
0x1800ddab4  mov     r9d, eax; char *
0x1800ddab7  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800ddabe  mov     edx, 18Dh; void *
0x1800ddac3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800ddac9  mov     [rsp+590h+var_54F], r12b
0x1800ddace  xor     edx, edx; length
0x1800ddad0  mov     rcx, [rsp+590h+string]; string
0x1800ddad5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ddadb  mov     rdx, rax
0x1800ddade  lea     rcx, [rbp+490h+var_438]
0x1800ddae2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ddae7  nop
0x1800ddae8  lea     rbx, [rsi+308h]
0x1800ddaef  lea     rdx, [rbp+490h+var_438]
0x1800ddaf3  mov     rcx, rbx
0x1800ddaf6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ddafb  mov     rcx, [r14]
0x1800ddafe  mov     [rsp+590h+var_548], rcx
0x1800ddb03  test    rcx, rcx
0x1800ddb06  jz      short loc_1800DDB15
0x1800ddb08  mov     rax, [rcx]
0x1800ddb0b  mov     rax, [rax+8]
0x1800ddb0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddb14  nop
0x1800ddb15  lea     rcx, [rsp+590h+var_548]
0x1800ddb1a  call    ?GetStoreAppLanguageSr@StoreApplication@@SAKAEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; StoreApplication::GetStoreAppLanguageSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)
0x1800ddb1f  mov     edi, eax
0x1800ddb21  lea     rcx, [rsp+590h+var_548]
0x1800ddb26  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ddb2b  mov     [rsp+590h+var_570], edi
0x1800ddb2f  lea     r9, [rbp+490h+Buffer]
0x1800ddb36  lea     r8, [rbp+490h+var_3D8]
0x1800ddb3d  lea     rdx, [rbp+490h+var_418]
0x1800ddb41  lea     rcx, [rbp+490h+var_458]
0x1800ddb45  call    ?ComputeProgramId@Application@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00K@Z; Application::ComputeProgramId(std::wstring const &,std::wstring const &,std::wstring const &,ulong)
0x1800ddb4a  nop
0x1800ddb4b  lea     rcx, [rbp+490h+var_458]
0x1800ddb4f  cmp     [rbp+490h+var_440], 7
0x1800ddb54  cmova   rcx, [rbp+490h+var_458]
0x1800ddb59  lea     rax, [rbp+490h+var_438]
0x1800ddb5d  cmp     [rbp+490h+var_420], 7
0x1800ddb62  cmova   rax, qword ptr [rbp+490h+var_438]
0x1800ddb67  mov     [rsp+590h+var_568], rcx
0x1800ddb6c  mov     qword ptr [rsp+590h+var_570], rax; int
0x1800ddb71  lea     r9, aWsWs; "%ws | %ws"
0x1800ddb78  mov     r8d, 199h
0x1800ddb7e  lea     rdx, aStoreapplicati_0; "StoreApplication::GetStoreApplicationSr"
0x1800ddb85  mov     ecx, 3
0x1800ddb8a  call    AslLogCallPrintf
0x1800ddb8f  mov     r12d, [r13+0E0h]
0x1800ddb96  mov     r15d, 1
0x1800ddb9c  cmp     cs:?ForceFullAppScan@Application@@1_NA, 0; bool Application::ForceFullAppScan
0x1800ddba3  jnz     short loc_1800DDBB9
0x1800ddba5  cmp     r12d, r15d
0x1800ddba8  jbe     short loc_1800DDBB9
0x1800ddbaa  lea     r8, [rbp+490h+var_458]
0x1800ddbae  mov     rdx, r13
0x1800ddbb1  mov     rcx, rsi; struct IAmiInventoryItem *
0x1800ddbb4  call    ?GetApplicationFromCache@Application@@QEAAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::GetApplicationFromCache(ConfigSettings const &,std::wstring const &)
0x1800ddbb9  mov     rcx, rsi; this
0x1800ddbbc  call    ?IsValid@Application@@QEAA_NAEBVConfigSettings@@@Z; Application::IsValid(ConfigSettings const &)
0x1800ddbc1  test    al, al
0x1800ddbc3  jnz     loc_1800DE0C2
0x1800ddbc9  lea     rdx, [rbp+490h+var_418]
0x1800ddbcd  mov     rcx, rsi
0x1800ddbd0  call    ?SetName@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetName(std::wstring const &)
0x1800ddbd5  lea     rdx, [rbp+490h+var_3D8]
0x1800ddbdc  mov     rcx, rsi
0x1800ddbdf  call    ?SetPublisher@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetPublisher(std::wstring const &)
0x1800ddbe4  lea     rdx, [rbp+490h+Buffer]
0x1800ddbeb  mov     rcx, rsi
0x1800ddbee  call    ?SetVersion@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetVersion(std::wstring const &)
0x1800ddbf3  mov     [rsi+1D0h], edi
0x1800ddbf9  lea     rcx, [rsi+38h]
0x1800ddbfd  lea     rdx, [rbp+490h+var_458]
0x1800ddc01  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ddc06  lea     rdx, [rbp+490h+var_438]
0x1800ddc0a  mov     rcx, rbx
0x1800ddc0d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ddc12  lea     rcx, [rsi+150h]
0x1800ddc19  lea     rdx, ?ApplicationSourceAppxPackage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationSourceAppxPackage
0x1800ddc20  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ddc25  lea     rcx, [rsi+170h]
0x1800ddc2c  lea     rdx, ?ApplicationTypeApplication@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationTypeApplication
0x1800ddc33  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ddc38  mov     [rsp+590h+var_548], 0
0x1800ddc41  mov     rdi, [r14]
0x1800ddc44  mov     rax, [rdi]
0x1800ddc47  mov     rbx, [rax+70h]
0x1800ddc4b  xor     edx, edx
0x1800ddc4d  lea     rcx, [rsp+590h+var_548]
0x1800ddc52  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800ddc57  lea     rdx, [rsp+590h+var_548]
0x1800ddc5c  mov     rcx, rdi
0x1800ddc5f  mov     rax, rbx
0x1800ddc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddc67  mov     rcx, [rbp+498h]; this
0x1800ddc6e  test    eax, eax
0x1800ddc70  jns     short loc_1800DDC87
0x1800ddc72  mov     r9d, eax; char *
0x1800ddc75  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800ddc7c  mov     edx, 1B8h; void *
0x1800ddc81  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800ddc87  xor     edx, edx; length
0x1800ddc89  mov     rcx, [rsp+590h+var_548]; string
0x1800ddc8e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ddc94  mov     rdx, rax
0x1800ddc97  lea     rcx, [rbp+490h+var_4D8]
0x1800ddc9b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ddca0  nop
0x1800ddca1  lea     rcx, [rsi+2E8h]
0x1800ddca8  lea     rdx, [rbp+490h+var_4D8]
0x1800ddcac  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ddcb1  test    r12d, r12d
0x1800ddcb4  jnz     loc_1800DDD68
0x1800ddcba  lea     rdx, [rbp+490h+var_4B8]
0x1800ddcbe  mov     rcx, r13
0x1800ddcc1  call    ?GetExtractedAppxPackagePath@ConfigSettings@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigSettings::GetExtractedAppxPackagePath(void)
0x1800ddcc6  nop
0x1800ddcc7  mov     rdx, rax
0x1800ddcca  mov     rcx, rsi
0x1800ddccd  call    ?SetInstallLocation@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetInstallLocation(std::wstring const &)
0x1800ddcd2  nop
0x1800ddcd3  lea     rcx, [rbp+490h+var_4B8]
0x1800ddcd7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ddcdc  lea     rdx, [rbp+490h+var_4B8]
0x1800ddce0  mov     rcx, r13
0x1800ddce3  call    ?GetExtractedAppxManifestPath@ConfigSettings@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigSettings::GetExtractedAppxManifestPath(void)
0x1800ddce8  nop
0x1800ddce9  lea     rcx, [rsi+388h]
0x1800ddcf0  mov     rdx, rax
0x1800ddcf3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ddcf8  nop
0x1800ddcf9  lea     rcx, [rbp+490h+var_4B8]
0x1800ddcfd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ddd02  lea     rdx, [rbp+490h+var_478]
0x1800ddd06  mov     rcx, r13
0x1800ddd09  call    ?GetExtractedAppxManifestPath@ConfigSettings@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigSettings::GetExtractedAppxManifestPath(void)
0x1800ddd0e  nop
0x1800ddd0f  xor     r8d, r8d
0x1800ddd12  mov     rdx, rax
0x1800ddd15  lea     rcx, [rbp+490h+var_4B8]
0x1800ddd19  call    ?GetStoreAppType@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@E@Z; StoreApplication::GetStoreAppType(std::wstring const &,uchar)
0x1800ddd1e  nop
0x1800ddd1f  lea     rcx, [rsi+328h]
0x1800ddd26  mov     rdx, rax
0x1800ddd29  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ddd2e  nop
0x1800ddd2f  lea     rcx, [rbp+490h+var_4B8]
0x1800ddd33  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ddd38  nop
0x1800ddd39  lea     rcx, [rbp+490h+var_478]
0x1800ddd3d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ddd42  lea     rdx, [rbp+490h+var_4B8]
0x1800ddd46  mov     rcx, r13
0x1800ddd49  call    ?GetExtractedAppxBundlePath@ConfigSettings@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigSettings::GetExtractedAppxBundlePath(void)
0x1800ddd4e  nop
0x1800ddd4f  lea     rcx, [rsi+3A8h]
0x1800ddd56  mov     rdx, rax
0x1800ddd59  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800ddd5e  nop
0x1800ddd5f  lea     rcx, [rbp+490h+var_4B8]
0x1800ddd63  jmp     loc_1800DE0A3
0x1800ddd68  mov     rcx, [r14]
  ... truncated ...
```
