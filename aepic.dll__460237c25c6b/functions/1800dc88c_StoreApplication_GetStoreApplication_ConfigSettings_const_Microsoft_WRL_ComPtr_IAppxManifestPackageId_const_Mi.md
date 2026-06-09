# StoreApplication::GetStoreApplication(ConfigSettings const &,Microsoft::WRL::ComPtr<IAppxManifestPackageId> const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)

- ea: `0x1800dc88c`
- end: `0x1800dd874`
- name: `?GetStoreApplication@StoreApplication@@QEAAXAEBVConfigSettings@@AEBV?$ComPtr@UIAppxManifestPackageId@@@WRL@Microsoft@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@45@@Z`
- size: `4072`
- prototype: `__int64 __fastcall(Application *this, struct ConfigSettings *)`
- caller_count: `1`
- callee_count: `54`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d93a4`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18000ea34`
- `0x18000ec84`
- `0x18000f0bc`
- `0x18000faac`
- `0x18000faf0`
- `0x18001082c`
- `0x1800108a8`
- `0x18001c5f0`
- `0x18001c6d8`
- `0x18001de0c`
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
- `0x1800caa40`
- `0x1800cea08`
- `0x1800d05d0`
- `0x1800d0c84`
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
- `0x1800d59dc`
- `0x1800d8684`
- `0x1800d9dcc`
- `0x1800daabc`
- `0x1800dac8c`
- `0x1800dafb8`
- `0x1800db734`
- `0x1800dbc34`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dd031`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dd1dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dd031`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dd1dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800dcd29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800dcd29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd346`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd7e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd80c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd824`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd346`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd7e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd80c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dd824`

## string_xrefs

- `0x1800dc8fc`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dc942`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dc98a`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dc9fe`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dcba1`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dcc0b`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dcd3d`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dcd93`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dcdbc`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dcede`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dcfc8`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dd010`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dd0c2`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dd10f`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dd160`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dd354`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dd369`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800dd37e`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=46
void __fastcall StoreApplication::GetStoreApplication(
        Application *this,
        struct ConfigSettings *a2,
        _QWORD *a3,
        __int64 *a4)
{
  struct ConfigSettings *v6; // r15
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int StoreAppLanguage; // r14d
  _QWORD *v13; // rcx
  int *v14; // rax
  const struct ConfigSettings *v15; // rdx
  unsigned int v16; // r13d
  __int64 v17; // r8
  int v18; // eax
  const unsigned __int16 (*v19)[45]; // rdx
  int v20; // eax
  __int64 ExtractedAppxPackagePath; // rax
  __int64 ExtractedAppxManifestPath; // rax
  char *v23; // r14
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 ExtractedAppxBundlePath; // rax
  const WCHAR *v27; // rcx
  HRESULT v28; // eax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING, __int64 *); // rbx
  int v31; // eax
  __int64 v32; // rcx
  __int64 StoreAppInstallLocationFromPackage; // rax
  __int64 StoreAppInstallDateFromPackage; // rax
  __int64 v35; // rax
  int v36; // eax
  __int64 StoreAppType; // rax
  __int64 v38; // rax
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, __int64 **); // rbx
  int v41; // eax
  __int64 v42; // rax
  int v43; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v45; // rax
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, HSTRING, __int64 *); // rbx
  int v48; // eax
  __int64 v49; // rdi
  __int64 (__fastcall *v50)(__int64, __int64 *); // rbx
  int v51; // eax
  __int64 AllUserSids; // rax
  int v53; // eax
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, __int64 *); // rbx
  int v56; // eax
  int v57; // eax
  PCWSTR v58; // rdi
  struct File *v59; // rbx
  struct File *v60; // r12
  __int64 v61; // r9
  __int128 *v62; // rcx
  int v63; // eax
  __int64 StoreAppManifestPathFromPackage; // rax
  __int64 v65; // rax
  int v66; // ebx
  int v67; // eax
  struct File *v68; // rdi
  _QWORD *v69; // rax
  __int64 i; // rbx
  __int64 v71; // r12
  int v72; // [rsp+20h] [rbp-E0h]
  int v73; // [rsp+20h] [rbp-E0h]
  int v74; // [rsp+20h] [rbp-E0h]
  char v75; // [rsp+40h] [rbp-C0h] BYREF
  char v76; // [rsp+41h] [rbp-BFh] BYREF
  char v77; // [rsp+42h] [rbp-BEh]
  __int64 v78; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v79; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v81; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v82; // [rsp+68h] [rbp-98h] BYREF
  __int64 v83; // [rsp+70h] [rbp-90h] BYREF
  __int64 v84; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v85; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v86; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v87; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v88; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v89; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v90; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID pv[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v92; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v93; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v94; // [rsp+D8h] [rbp-28h]
  struct File *v95; // [rsp+E0h] [rbp-20h] BYREF
  struct File *v96; // [rsp+E8h] [rbp-18h]
  struct ConfigSettings *v97; // [rsp+F8h] [rbp-8h]
  _BYTE v98[32]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v99; // [rsp+120h] [rbp+20h] BYREF
  __int64 v100; // [rsp+130h] [rbp+30h]
  unsigned __int64 v101; // [rsp+138h] [rbp+38h]
  __int128 v102; // [rsp+140h] [rbp+40h] BYREF
  __m128i si128; // [rsp+150h] [rbp+50h]
  PCNZWCH sourceString[2]; // [rsp+160h] [rbp+60h] BYREF
  UINT32 length[4]; // [rsp+170h] [rbp+70h]
  _OWORD v106[2]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v107[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v108[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int64 v109; // [rsp+1D8h] [rbp+D8h]
  HSTRING v110[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v111[32]; // [rsp+200h] [rbp+100h] BYREF
  _OWORD v112[2]; // [rsp+220h] [rbp+120h] BYREF
  wchar_t Buffer[16]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v114[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v115[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v116[24]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _QWORD v117[80]; // [rsp+2B8h] [rbp+1B8h] BYREF
  _BYTE v118[32]; // [rsp+538h] [rbp+438h] BYREF
  _BYTE v119[120]; // [rsp+558h] [rbp+458h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+628h] [rbp+528h]

  v6 = a2;
  v97 = a2;
  v93 = 0;
  v94 = 0;
  v88 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 24LL))(*a3, &v88);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v8,
      v72);
  std::wstring::wstring(v115, v88);
  v90 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 40LL))(*a3, &v90);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v9,
      v72);
  std::wstring::wstring(v114, v90);
  v92 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 48LL))(*a3, &v92);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v10,
      v72);
  v73 = WORD1(v92);
  Utility::FormatWstring(Buffer, (wchar_t *)L"%hu.%hu.%hu.%hu");
  v89 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 80LL))(*a3, &v89);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v11,
      v73);
  v77 = 0;
  std::wstring::wstring(v108, v89);
  std::wstring::operator=((char *)this + 776, v108);
  StoreAppLanguage = StoreApplication::GetStoreAppLanguage(v108, *a3);
  Application::ComputeProgramId(
    (unsigned int)v107,
    (unsigned int)v115,
    (unsigned int)v114,
    (unsigned int)Buffer,
    StoreAppLanguage);
  v13 = v107;
  if ( v107[3] > 7u )
    v13 = (_QWORD *)v107[0];
  v14 = v108;
  if ( v109 > 7 )
    v14 = *(int **)v108;
  AslLogCallPrintf(3, "StoreApplication::GetStoreApplication", 104, "%ws | %ws", v14, v13);
  v16 = *((_DWORD *)v6 + 56);
  if ( !Application::ForceFullAppScan && v16 > 1 )
    Application::GetApplicationFromCache(this);
  if ( Application::IsValid(this, v15) )
  {
    v23 = (char *)this + 904;
    if ( !*((_QWORD *)this + 115) )
    {
      *(_OWORD *)sourceString = 0;
      *(__m128i *)length = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(sourceString[0]) = 0;
      StoreAppManifestPathFromPackage = StoreApplication::GetStoreAppManifestPathFromPackage(v110, a4, 1);
      std::wstring::operator=(sourceString, StoreAppManifestPathFromPackage);
      std::wstring::_Tidy_deallocate(v110);
      std::wstring::operator=((char *)this + 904, sourceString);
      v102 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v102) = 0;
      v65 = StoreApplication::GetStoreAppManifestPathFromPackage(v110, a4, 2);
      std::wstring::operator=(&v102, v65);
      std::wstring::_Tidy_deallocate(v110);
      std::wstring::operator=((char *)this + 936, &v102);
      std::wstring::_Tidy_deallocate(&v102);
      std::wstring::_Tidy_deallocate(sourceString);
    }
  }
  else
  {
    Application::SetName(this, v115);
    Application::SetPublisher(this, v114);
    Application::SetVersion(this, Buffer);
    *((_DWORD *)this + 116) = StoreAppLanguage;
    std::wstring::operator=((char *)this + 56, v107);
    std::wstring::operator=((char *)this + 776, v108);
    std::wstring::operator=((char *)this + 336, &Application::ApplicationSourceAppxPackage);
    std::wstring::operator=((char *)this + 368, Application::ApplicationTypeApplication);
    pv[0] = 0;
    v18 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 72LL))(*a3, pv);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v18,
        v74);
    std::wstring::wstring(sourceString, pv[0]);
    std::wstring::operator=((char *)this + 744, sourceString);
    v82 = 0;
    Windows::Internal::StringReference::StringReference(v110, v19);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
    v20 = Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager>(v110[0], &v82);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v20,
        v74);
    v112[0] = 0;
    v112[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v112[0]) = 0;
    if ( v16 )
    {
      v81 = 0;
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v27 = (const WCHAR *)sourceString;
      if ( *(_QWORD *)&length[2] > 7u )
        v27 = sourceString[0];
      v28 = WindowsCreateString(v27, length[0], &string);
      if ( v28 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xA6,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v28,
          v74);
      if ( *a4 )
      {
        v32 = v81;
      }
      else
      {
        v29 = v82;
        v30 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v82 + 136LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
        v31 = v30(v29, string, &v81);
        if ( v31 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xAB,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)(unsigned int)v31,
            v74);
        v32 = v81;
        if ( !v81 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xAC,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)0x80070490LL,
            v74);
      }
      if ( *a4 )
        v32 = *a4;
      v78 = v32;
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
      StoreAppInstallLocationFromPackage = StoreApplication::GetStoreAppInstallLocationFromPackage(v98, &v78);
      Application::SetInstallLocation(this, StoreAppInstallLocationFromPackage);
      std::wstring::_Tidy_deallocate(v98);
      StoreAppInstallDateFromPackage = StoreApplication::GetStoreAppInstallDateFromPackage(v98, &v78);
      std::wstring::operator=((char *)this + 256, StoreAppInstallDateFromPackage);
      std::wstring::_Tidy_deallocate(v98);
      v106[0] = 0;
      v106[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v106[0]) = 0;
      v35 = StoreApplication::GetStoreAppManifestPathFromPackage(v98, &v78, 1);
      std::wstring::operator=(v106, v35);
      std::wstring::_Tidy_deallocate(v98);
      v23 = (char *)this + 904;
      std::wstring::operator=((char *)this + 904, v106);
      StoreApplication::GetPackageRelativeAppIDs(v106, &v93);
      v76 = 0;
      v36 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v78 + 64LL))(v78, &v76);
      if ( v36 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xC1,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v36,
          v74);
      *((_BYTE *)this + 969) = v76 != 0;
      StoreAppType = StoreApplication::GetStoreAppType(v98, v106);
      std::wstring::operator=((char *)this + 808, StoreAppType);
      std::wstring::_Tidy_deallocate(v98);
      v102 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v102) = 0;
      v38 = StoreApplication::GetStoreAppManifestPathFromPackage(v98, &v78, 2);
      std::wstring::operator=(&v102, v38);
      std::wstring::_Tidy_deallocate(v98);
      std::wstring::operator=((char *)this + 936, &v102);
      *((_BYTE *)this + 968) = StoreApplication::IsInboxStoreApp(v6, &v78);
      v85 = 0;
      v39 = v78;
      v40 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v78 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
      v41 = v40(v39, &v85);
      if ( v41 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xDA,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v41,
          v74);
      v87 = 0;
      v42 = *v85;
      *(_QWORD *)&v99 = &v87;
      *((_QWORD *)&v99 + 1) = 0;
      LOBYTE(v100) = 1;
      v43 = (*(__int64 (__fastcall **)(__int64 *, char *))(v42 + 48))(v85, (char *)&v99 + 8);
      if ( v43 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v43,
          v74);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&v99);
      StringRawBuffer = WindowsGetStringRawBuffer(v87, 0);
      std::wstring::wstring(&v99, StringRawBuffer);
      std::wstring::operator=((char *)this + 712, &v99);
      std::wstring::_Tidy_deallocate(&v99);
      v45 = Application::ComputeProgramInstanceId(this, v98);
      std::wstring::operator=((char *)this + 400, v45);
      std::wstring::_Tidy_deallocate(v98);
      v84 = 0;
      v46 = v82;
      v47 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v82 + 120LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
      v48 = v47(v46, string, &v84);
      if ( v48 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v48,
          v74);
      v79 = 0;
      v49 = v84;
      v50 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v84 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
      v51 = v50(v49, &v79);
      if ( v51 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v51,
          v74);
      AllUserSids = Utility::GetAllUserSids(retaddr);
      std::vector<std::wstring>::vector<std::wstring>(&v95, AllUserSids);
      v75 = 0;
      v53 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v79 + 56LL))(v79, &v75);
      if ( v53 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v53,
          v74);
      while ( v75 )
      {
        v83 = 0;
        v54 = v79;
        v55 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v79 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
        v56 = v55(v54, &v83);
        if ( v56 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xF2,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)(unsigned int)v56,
            v74);
        v86 = 0;
        v57 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v83 + 48LL))(v83, &v86);
        if ( v57 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xF4,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)(unsigned int)v57,
            v74);
        v58 = WindowsGetStringRawBuffer(v86, 0);
        v59 = v95;
        v60 = v96;
        while ( v59 != v60 )
        {
          std::wstring::wstring(&v99, v59);
          v61 = -1;
          do
            ++v61;
          while ( v58[v61] );
          v62 = &v99;
          if ( v101 > 7 )
            v62 = (__int128 *)v99;
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v62, v100, v58, v61) )
          {
            std::wstring::wstring(v98, v58);
            Application::AddUserSid(this, v98);
            std::wstring::_Tidy_deallocate(v98);
            std::wstring::_Tidy_deallocate(&v99);
            break;
          }
          std::wstring::_Tidy_deallocate(&v99);
          v59 = (struct File *)((char *)v59 + 32);
        }
        v63 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v79 + 64LL))(v79, &v75);
        if ( v63 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xFF,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)(unsigned int)v63,
            v74);
        Windows::Internal::String::~String((Windows::Internal::String *)&v86);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v83);
      }
      v77 = 1;
      std::vector<std::wstring>::_Tidy(&v95);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v84);
      Windows::Internal::String::~String((Windows::Internal::String *)&v87);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v85);
      std::wstring::_Tidy_deallocate(&v102);
      std::wstring::_Tidy_deallocate(v106);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v81);
    }
    else
    {
      ExtractedAppxPackagePath = ConfigSettings::GetExtractedAppxPackagePath(v6, v98);
      Application::SetInstallLocation(this, ExtractedAppxPackagePath);
      std::wstring::_Tidy_deallocate(v98);
      ExtractedAppxManifestPath = ConfigSettings::GetExtractedAppxManifestPath(v6, v98);
      v23 = (char *)this + 904;
      std::wstring::operator=((char *)this + 904, ExtractedAppxManifestPath);
      std::wstring::_Tidy_deallocate(v98);
      v24 = ConfigSettings::GetExtractedAppxManifestPath(v6, &v102);
      v25 = StoreApplication::GetStoreAppType(v98, v24);
      std::wstring::operator=((char *)this + 808, v25);
      std::wstring::_Tidy_deallocate(v98);
      std::wstring::_Tidy_deallocate(&v102);
      ExtractedAppxBundlePath = ConfigSettings::GetExtractedAppxBundlePath(v6, v98);
      std::wstring::operator=((char *)this + 936, ExtractedAppxBundlePath);
      std::wstring::_Tidy_deallocate(v98);
    }
    std::wstring::_Tidy_deallocate(v112);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v82);
    std::wstring::_Tidy_deallocate(sourceString);
    CoTaskMemFree(pv[0]);
  }
  if ( *((_DWORD *)v6 + 2) != 5 && v16 != 2 )
  {
    v99 = 0;
    v100 = 0;
    std::wstring::wstring(v98, L".exe");
    std::vector<std::wstring>::push_back(&v99, v98);
    std::wstring::_Tidy_deallocate(v98);
    if ( *((_DWORD *)v6 + 2) == 1 )
    {
      std::wstring::wstring(v98, L".dll");
      std::vector<std::wstring>::push_back(&v99, v98);
      std::wstring::_Tidy_deallocate(v98);
      std::wstring::wstring(v98, L".js");
      std::vector<std::wstring>::push_back(&v99, v98);
      std::wstring::_Tidy_deallocate(v98);
      std::wstring::wstring(v98, L".pri");
      std::vector<std::wstring>::push_back(&v99, v98);
      std::wstring::_Tidy_deallocate(v98);
      std::wstring::wstring(v98, L".htm");
      std::vector<std::wstring>::push_back(&v99, v98);
      std::wstring::_Tidy_deallocate(v98);
      std::wstring::wstring(v98, L".html");
      std::vector<std::wstring>::push_back(&v99, v98);
      std::wstring::_Tidy_deallocate(v98);
      std::wstring::wstring(v98, L".xhtml");
      std::vector<std::wstring>::push_back(&v99, v98);
      std::wstring::_Tidy_deallocate(v98);
      std::wstring::wstring(v98, L".winmd");
      std::vector<std::wstring>::push_back(&v99, v98);
      std::wstring::_Tidy_deallocate(v98);
    }
    pv[0] = v106;
    v66 = std::vector<std::wstring>::vector<std::wstring>(v106, &v99);
    v67 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 2) + 40LL))((char *)this + 16);
    File::SearchForPeFiles((unsigned int)&v95, (_DWORD)v6, v67, v66, v74, (__int64)v107);
    v68 = v95;
    if ( v95 != v96 )
    {
      do
      {
        File::File((File *)v116, v68);
        v69 = v117;
        if ( v117[3] > 7u )
          v69 = (_QWORD *)v117[0];
        AslLogCallPrintf(3, "StoreApplication::GetStoreApplication", 300, "%ws", v69);
        Utility::ToLower(v98, v117);
        v71 = *((_QWORD *)&v93 + 1);
        for ( i = v93; i != v71; i += 64 )
        {
          std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(v110, i);
          if ( std::wstring::find(v98, v111) != -1 )
          {
            std::wstring::operator=(v119, v110);
            std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v110);
            break;
          }
          std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v110);
        }
        std::wstring::operator=(v118, (char *)this + 744);
        std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::emplace<File &>(
          (char *)this + 24,
          pv,
          v116);
        std::wstring::_Tidy_deallocate(v98);
        File::~File((File *)v116);
        v68 = (struct File *)((char *)v68 + 816);
      }
      while ( v68 != v96 );
      v6 = v97;
    }
    std::vector<File>::_Tidy(&v95);
    std::vector<std::wstring>::_Tidy(&v99);
  }
  if ( v77 )
    Application::SaveApplicationToCache(this, v6);
  if ( *((_BYTE *)v6 + 220) )
  {
    if ( *((_QWORD *)v23 + 2) )
    {
      LOBYTE(v17) = 1;
      StoreApplication::GetStoreAppManifestXml(v98, v23, v17);
      std::wstring::operator=((char *)this + 840, v98);
      std::wstring::_Tidy_deallocate(v98);
    }
    if ( *((_QWORD *)this + 119) )
    {
      StoreApplication::GetStoreAppManifestXml(v98, (char *)this + 936, 0);
      std::wstring::operator=((char *)this + 872, v98);
      std::wstring::_Tidy_deallocate(v98);
    }
  }
  std::wstring::_Tidy_deallocate(v107);
  std::wstring::_Tidy_deallocate(v108);
  CoTaskMemFree(v89);
  std::wstring::_Tidy_deallocate(Buffer);
  std::wstring::_Tidy_deallocate(v114);
  CoTaskMemFree(v90);
  std::wstring::_Tidy_deallocate(v115);
  CoTaskMemFree(v88);
  if ( (_QWORD)v93 )
  {
    std::_Destroy_range<std::allocator<std::pair<std::wstring,std::wstring>>>(v93, *((_QWORD *)&v93 + 1));
    std::_Deallocate<16>(v93, (v94 - v93) & 0xFFFFFFFFFFFFFFC0uLL);
  }
}

```

## disassembly

```asm
0x1800dc88c  push    rbp
0x1800dc88e  push    rbx
0x1800dc88f  push    rsi
0x1800dc890  push    rdi
0x1800dc891  push    r12
0x1800dc893  push    r13
0x1800dc895  push    r14
0x1800dc897  push    r15
0x1800dc899  lea     rbp, [rsp-4E8h]
0x1800dc8a1  sub     rsp, 5E8h
0x1800dc8a8  mov     rax, cs:__security_cookie
0x1800dc8af  xor     rax, rsp
0x1800dc8b2  mov     [rbp+520h+var_50], rax
0x1800dc8b9  mov     r12, r9
0x1800dc8bc  mov     rbx, r8
0x1800dc8bf  mov     r15, rdx
0x1800dc8c2  mov     [rbp+520h+var_528], rdx
0x1800dc8c6  mov     rsi, rcx
0x1800dc8c9  xorps   xmm0, xmm0
0x1800dc8cc  movdqu  [rbp+520h+var_558], xmm0
0x1800dc8d1  xor     edi, edi
0x1800dc8d3  mov     [rbp+520h+var_548], rdi
0x1800dc8d7  mov     [rbp+520h+var_588], rdi
0x1800dc8db  mov     rcx, [r8]
0x1800dc8de  mov     rax, [rcx]
0x1800dc8e1  lea     rdx, [rbp+520h+var_588]
0x1800dc8e5  mov     rax, [rax+18h]
0x1800dc8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc8ee  mov     rcx, [rbp+528h]; this
0x1800dc8f5  test    eax, eax
0x1800dc8f7  jns     short loc_1800DC90C
0x1800dc8f9  mov     r9d, eax; char *
0x1800dc8fc  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dc903  lea     edx, [rdi+4Bh]; void *
0x1800dc906  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dc90c  mov     rdx, [rbp+520h+var_588]
0x1800dc910  lea     rcx, [rbp+520h+var_3A0]
0x1800dc917  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dc91c  nop
0x1800dc91d  mov     [rbp+520h+var_578], rdi
0x1800dc921  mov     rcx, [rbx]
0x1800dc924  mov     rax, [rcx]
0x1800dc927  lea     rdx, [rbp+520h+var_578]
0x1800dc92b  mov     rax, [rax+28h]
0x1800dc92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc934  mov     rcx, [rbp+528h]; this
0x1800dc93b  test    eax, eax
0x1800dc93d  jns     short loc_1800DC954
0x1800dc93f  mov     r9d, eax; char *
0x1800dc942  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dc949  mov     edx, 50h ; 'P'; void *
0x1800dc94e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dc954  mov     rdx, [rbp+520h+var_578]
0x1800dc958  lea     rcx, [rbp+520h+var_3C0]
0x1800dc95f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dc964  nop
0x1800dc965  mov     [rbp+520h+var_560], rdi
0x1800dc969  mov     rcx, [rbx]
0x1800dc96c  mov     rax, [rcx]
0x1800dc96f  lea     rdx, [rbp+520h+var_560]
0x1800dc973  mov     rax, [rax+30h]
0x1800dc977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc97c  mov     rcx, [rbp+528h]; this
0x1800dc983  test    eax, eax
0x1800dc985  jns     short loc_1800DC99C
0x1800dc987  mov     r9d, eax; char *
0x1800dc98a  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dc991  mov     edx, 55h ; 'U'; void *
0x1800dc996  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dc99c  mov     r8, [rbp+520h+var_560]
0x1800dc9a0  movzx   edx, r8w
0x1800dc9a4  mov     rax, r8
0x1800dc9a7  shr     rax, 10h
0x1800dc9ab  movzx   ecx, ax
0x1800dc9ae  mov     rax, r8
0x1800dc9b1  shr     rax, 20h
0x1800dc9b5  movzx   r9d, ax
0x1800dc9b9  shr     r8, 30h
0x1800dc9bd  mov     dword ptr [rsp+620h+var_5F8], edx
0x1800dc9c1  mov     [rsp+620h+var_600], ecx; int
0x1800dc9c5  lea     rdx, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x1800dc9cc  lea     rcx, [rbp+520h+Buffer]; Buffer
0x1800dc9d3  call    ?FormatWstring@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Utility::FormatWstring(ushort const *,...)
0x1800dc9d8  nop
0x1800dc9d9  mov     [rbp+520h+var_580], rdi
0x1800dc9dd  mov     rcx, [rbx]
0x1800dc9e0  mov     rax, [rcx]
0x1800dc9e3  lea     rdx, [rbp+520h+var_580]
0x1800dc9e7  mov     rax, [rax+50h]
0x1800dc9eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc9f0  mov     rcx, [rbp+528h]; this
0x1800dc9f7  test    eax, eax
0x1800dc9f9  jns     short loc_1800DCA10
0x1800dc9fb  mov     r9d, eax; char *
0x1800dc9fe  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dca05  mov     edx, 5Eh ; '^'; void *
0x1800dca0a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dca10  mov     [rsp+620h+var_5DE], dil
0x1800dca15  mov     rdx, [rbp+520h+var_580]
0x1800dca19  lea     rcx, [rbp+520h+var_460]
0x1800dca20  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dca25  nop
0x1800dca26  lea     rdi, [rsi+308h]
0x1800dca2d  lea     rdx, [rbp+520h+var_460]
0x1800dca34  mov     rcx, rdi
0x1800dca37  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800dca3c  mov     rdx, [rbx]
0x1800dca3f  lea     rcx, [rbp+520h+var_460]
0x1800dca46  call    ?GetStoreAppLanguage@StoreApplication@@SAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIAppxManifestPackageId@@@Z; StoreApplication::GetStoreAppLanguage(std::wstring const &,IAppxManifestPackageId *)
0x1800dca4b  mov     r14d, eax
0x1800dca4e  mov     [rsp+620h+var_600], eax
0x1800dca52  lea     r9, [rbp+520h+Buffer]
0x1800dca59  lea     r8, [rbp+520h+var_3C0]
0x1800dca60  lea     rdx, [rbp+520h+var_3A0]
0x1800dca67  lea     rcx, [rbp+520h+var_480]
0x1800dca6e  call    ?ComputeProgramId@Application@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00K@Z; Application::ComputeProgramId(std::wstring const &,std::wstring const &,std::wstring const &,ulong)
0x1800dca73  nop
0x1800dca74  lea     rcx, [rbp+520h+var_480]
0x1800dca7b  cmp     [rbp+520h+var_468], 7
0x1800dca83  cmova   rcx, [rbp+520h+var_480]
0x1800dca8b  lea     rax, [rbp+520h+var_460]
0x1800dca92  cmp     [rbp+520h+var_448], 7
0x1800dca9a  cmova   rax, qword ptr [rbp+520h+var_460]
0x1800dcaa2  mov     [rsp+620h+var_5F8], rcx
0x1800dcaa7  mov     qword ptr [rsp+620h+var_600], rax; int
0x1800dcaac  lea     r9, aWsWs; "%ws | %ws"
0x1800dcab3  mov     r8d, 68h ; 'h'
0x1800dcab9  lea     rdx, aStoreapplicati_4; "StoreApplication::GetStoreApplication"
0x1800dcac0  lea     ecx, [r8-65h]
0x1800dcac4  call    AslLogCallPrintf
0x1800dcac9  mov     r13d, [r15+0E0h]
0x1800dcad0  cmp     cs:?ForceFullAppScan@Application@@1_NA, 0; bool Application::ForceFullAppScan
0x1800dcad7  jnz     short loc_1800DCAF1
0x1800dcad9  cmp     r13d, 1
0x1800dcadd  jbe     short loc_1800DCAF1
0x1800dcadf  lea     r8, [rbp+520h+var_480]
0x1800dcae6  mov     rdx, r15
0x1800dcae9  mov     rcx, rsi; struct IAmiInventoryItem *
0x1800dcaec  call    ?GetApplicationFromCache@Application@@QEAAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::GetApplicationFromCache(ConfigSettings const &,std::wstring const &)
0x1800dcaf1  mov     rcx, rsi; this
0x1800dcaf4  call    ?IsValid@Application@@QEAA_NAEBVConfigSettings@@@Z; Application::IsValid(ConfigSettings const &)
0x1800dcaf9  test    al, al
0x1800dcafb  jnz     loc_1800DD390
0x1800dcb01  lea     rdx, [rbp+520h+var_3A0]
0x1800dcb08  mov     rcx, rsi
0x1800dcb0b  call    ?SetName@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetName(std::wstring const &)
0x1800dcb10  lea     rdx, [rbp+520h+var_3C0]
0x1800dcb17  mov     rcx, rsi
0x1800dcb1a  call    ?SetPublisher@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetPublisher(std::wstring const &)
0x1800dcb1f  lea     rdx, [rbp+520h+Buffer]
0x1800dcb26  mov     rcx, rsi
0x1800dcb29  call    ?SetVersion@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetVersion(std::wstring const &)
0x1800dcb2e  mov     [rsi+1D0h], r14d
0x1800dcb35  lea     rcx, [rsi+38h]
0x1800dcb39  lea     rdx, [rbp+520h+var_480]
0x1800dcb40  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800dcb45  lea     rdx, [rbp+520h+var_460]
0x1800dcb4c  mov     rcx, rdi
0x1800dcb4f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800dcb54  lea     rcx, [rsi+150h]
0x1800dcb5b  lea     rdx, ?ApplicationSourceAppxPackage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationSourceAppxPackage
0x1800dcb62  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800dcb67  lea     rcx, [rsi+170h]
0x1800dcb6e  lea     rdx, ?ApplicationTypeApplication@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationTypeApplication
0x1800dcb75  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800dcb7a  xor     edi, edi
0x1800dcb7c  mov     [rbp+520h+pv], rdi
0x1800dcb80  mov     rcx, [rbx]
0x1800dcb83  mov     rax, [rcx]
0x1800dcb86  lea     rdx, [rbp+520h+pv]
0x1800dcb8a  mov     rax, [rax+48h]
0x1800dcb8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcb93  mov     rcx, [rbp+528h]; this
0x1800dcb9a  test    eax, eax
0x1800dcb9c  jns     short loc_1800DCBB3
0x1800dcb9e  mov     r9d, eax; char *
0x1800dcba1  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dcba8  mov     edx, 87h; void *
0x1800dcbad  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dcbb3  mov     rdx, [rbp+520h+pv]
0x1800dcbb7  lea     rcx, [rbp+520h+sourceString]
0x1800dcbbb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dcbc0  nop
0x1800dcbc1  lea     rcx, [rsi+2E8h]
0x1800dcbc8  lea     rdx, [rbp+520h+sourceString]
0x1800dcbcc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800dcbd1  mov     [rsp+620h+var_5B8], rdi
0x1800dcbd6  lea     rcx, [rbp+520h+var_440]; string
0x1800dcbdd  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800dcbe2  lea     rcx, [rsp+620h+var_5B8]
0x1800dcbe7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dcbec  lea     rdx, [rsp+620h+var_5B8]
0x1800dcbf1  mov     rcx, [rbp+520h+var_440]
0x1800dcbf8  call    ??$ActivateInstance@UIPackageManager@Deployment@Management@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIPackageManager@Deployment@Management@1@@Z; Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager>(HSTRING__ *,Windows::Management::Deployment::IPackageManager * *)
0x1800dcbfd  mov     rcx, [rbp+528h]; this
0x1800dcc04  test    eax, eax
0x1800dcc06  jns     short loc_1800DCC1D
0x1800dcc08  mov     r9d, eax; char *
0x1800dcc0b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dcc12  mov     edx, 8Eh; void *
0x1800dcc17  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dcc1d  xorps   xmm0, xmm0
0x1800dcc20  movups  [rbp+520h+var_400], xmm0
0x1800dcc27  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800dcc2f  movdqu  [rbp+520h+var_3F0], xmm1
0x1800dcc37  mov     word ptr [rbp+520h+var_400], di
0x1800dcc3e  test    r13d, r13d
0x1800dcc41  jnz     loc_1800DCCFD
0x1800dcc47  lea     rdx, [rbp+520h+var_520]
0x1800dcc4b  mov     rcx, r15
0x1800dcc4e  call    ?GetExtractedAppxPackagePath@ConfigSettings@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigSettings::GetExtractedAppxPackagePath(void)
0x1800dcc53  nop
0x1800dcc54  mov     rdx, rax
0x1800dcc57  mov     rcx, rsi
0x1800dcc5a  call    ?SetInstallLocation@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetInstallLocation(std::wstring const &)
0x1800dcc5f  nop
0x1800dcc60  lea     rcx, [rbp+520h+var_520]
0x1800dcc64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dcc69  lea     rdx, [rbp+520h+var_520]
0x1800dcc6d  mov     rcx, r15
0x1800dcc70  call    ?GetExtractedAppxManifestPath@ConfigSettings@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigSettings::GetExtractedAppxManifestPath(void)
0x1800dcc75  nop
0x1800dcc76  lea     r14, [rsi+388h]
0x1800dcc7d  mov     rdx, rax
0x1800dcc80  mov     rcx, r14
0x1800dcc83  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800dcc88  nop
0x1800dcc89  lea     rcx, [rbp+520h+var_520]
0x1800dcc8d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dcc92  lea     rdx, [rbp+520h+var_4E0]
0x1800dcc96  mov     rcx, r15
0x1800dcc99  call    ?GetExtractedAppxManifestPath@ConfigSettings@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigSettings::GetExtractedAppxManifestPath(void)
0x1800dcc9e  nop
0x1800dcc9f  xor     r8d, r8d
0x1800dcca2  mov     rdx, rax
0x1800dcca5  lea     rcx, [rbp+520h+var_520]
0x1800dcca9  call    ?GetStoreAppType@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@E@Z; StoreApplication::GetStoreAppType(std::wstring const &,uchar)
0x1800dccae  nop
0x1800dccaf  lea     rcx, [rsi+328h]
0x1800dccb6  mov     rdx, rax
0x1800dccb9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800dccbe  nop
0x1800dccbf  lea     rcx, [rbp+520h+var_520]
0x1800dccc3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dccc8  nop
0x1800dccc9  lea     rcx, [rbp+520h+var_4E0]
0x1800dcccd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dccd2  lea     rdx, [rbp+520h+var_520]
0x1800dccd6  mov     rcx, r15
0x1800dccd9  call    ?GetExtractedAppxBundlePath@ConfigSettings@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigSettings::GetExtractedAppxBundlePath(void)
0x1800dccde  nop
0x1800dccdf  lea     rcx, [rsi+3A8h]
0x1800dcce6  mov     rdx, rax
0x1800dcce9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800dccee  nop
0x1800dccef  lea     rcx, [rbp+520h+var_520]
0x1800dccf3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800dccf8  jmp     loc_1800DD320
0x1800dccfd  mov     [rsp+620h+var_5C0], rdi
0x1800dcd02  mov     [rsp+620h+string], rdi
0x1800dcd07  xor     edx, edx
0x1800dcd09  lea     rcx, [rsp+620h+string]
0x1800dcd0e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800dcd13  lea     rcx, [rbp+520h+sourceString]
0x1800dcd17  cmp     qword ptr [rbp+520h+length+8], 7
0x1800dcd1c  cmova   rcx, [rbp+520h+sourceString]; sourceString
0x1800dcd21  lea     r8, [rsp+620h+string]; string
0x1800dcd26  mov     edx, [rbp+520h+length]; length
0x1800dcd29  call    cs:__imp_WindowsCreateString
0x1800dcd2f  mov     rcx, [rbp+528h]; this
0x1800dcd36  test    eax, eax
0x1800dcd38  jns     short loc_1800DCD4F
0x1800dcd3a  mov     r9d, eax; char *
0x1800dcd3d  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dcd44  mov     edx, 0A6h; void *
0x1800dcd49  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dcd4f  cmp     [r12], rdi
0x1800dcd53  jnz     short loc_1800DCDD1
0x1800dcd55  mov     rdi, [rsp+620h+var_5B8]
0x1800dcd5a  mov     rax, [rdi]
0x1800dcd5d  mov     rbx, [rax+88h]
0x1800dcd64  lea     rcx, [rsp+620h+var_5C0]
0x1800dcd69  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dcd6e  lea     r8, [rsp+620h+var_5C0]
0x1800dcd73  mov     rdx, [rsp+620h+string]
0x1800dcd78  mov     rcx, rdi
0x1800dcd7b  mov     rax, rbx
0x1800dcd7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dcd83  mov     rcx, [rbp+528h]; this
0x1800dcd8a  xor     edi, edi
0x1800dcd8c  test    eax, eax
0x1800dcd8e  jns     short loc_1800DCDA5
0x1800dcd90  mov     r9d, eax; char *
0x1800dcd93  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800dcd9a  mov     edx, 0ABh; void *
0x1800dcd9f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800dcda5  mov     rax, [rbp+528h]
0x1800dcdac  mov     rcx, [rsp+620h+var_5C0]
0x1800dcdb1  test    rcx, rcx
0x1800dcdb4  jnz     short loc_1800DCDD6
  ... truncated ...
```
