# StoreApplication::GetStoreApplication(ConfigSettings const &,Microsoft::WRL::ComPtr<IAppxManifestPackageId> const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)

- ea: `0x1800dc88c`
- end: `0x1800dd874`
- name: `?GetStoreApplication@StoreApplication@@QEAAXAEBVConfigSettings@@AEBV?$ComPtr@UIAppxManifestPackageId@@@WRL@Microsoft@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@45@@Z`
- size: `4072`
- prototype: `void __fastcall(Application *this, struct ConfigSettings *, _QWORD *, __int64 *)`
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
  char *v22; // r14
  __int64 ExtractedAppxManifestPath; // rax
  const WCHAR *v24; // rcx
  HRESULT v25; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, HSTRING, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rcx
  __int64 StoreAppInstallLocationFromPackage; // rax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64 **); // rbx
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, HSTRING, __int64 *); // rbx
  int v42; // eax
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, __int64 *); // rbx
  int v45; // eax
  __int64 AllUserSids; // rax
  int v47; // eax
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, __int64 *); // rbx
  int v50; // eax
  int v51; // eax
  PCWSTR v52; // rdi
  struct File *v53; // rbx
  struct File *v54; // r12
  __int64 v55; // r9
  __int128 *v56; // rcx
  int v57; // eax
  __int64 StoreAppManifestPathFromPackage; // rax
  __int64 v59; // rax
  int v60; // ebx
  int v61; // eax
  struct File *v62; // rdi
  _QWORD *v63; // rax
  __int64 i; // rbx
  __int64 v65; // r12
  int v66; // [rsp+20h] [rbp-E0h]
  int v67; // [rsp+20h] [rbp-E0h]
  int v68; // [rsp+20h] [rbp-E0h]
  char v69; // [rsp+40h] [rbp-C0h] BYREF
  char v70; // [rsp+41h] [rbp-BFh] BYREF
  char v71; // [rsp+42h] [rbp-BEh]
  __int64 v72; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v73; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v75; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v76; // [rsp+68h] [rbp-98h] BYREF
  __int64 v77; // [rsp+70h] [rbp-90h] BYREF
  __int64 v78; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v79; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v80; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v81; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v82; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v83; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v84; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID pv[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v86; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v87; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v88; // [rsp+D8h] [rbp-28h]
  struct File *v89; // [rsp+E0h] [rbp-20h] BYREF
  struct File *v90; // [rsp+E8h] [rbp-18h]
  struct ConfigSettings *v91; // [rsp+F8h] [rbp-8h]
  _BYTE v92[32]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v93; // [rsp+120h] [rbp+20h] BYREF
  __int64 v94; // [rsp+130h] [rbp+30h]
  unsigned __int64 v95; // [rsp+138h] [rbp+38h]
  __int128 v96; // [rsp+140h] [rbp+40h] BYREF
  __m128i si128; // [rsp+150h] [rbp+50h]
  PCNZWCH sourceString[2]; // [rsp+160h] [rbp+60h] BYREF
  UINT32 length[4]; // [rsp+170h] [rbp+70h]
  _OWORD v100[2]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v101[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v102[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int64 v103; // [rsp+1D8h] [rbp+D8h]
  HSTRING v104[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v105[32]; // [rsp+200h] [rbp+100h] BYREF
  _OWORD v106[2]; // [rsp+220h] [rbp+120h] BYREF
  wchar_t Buffer[16]; // [rsp+240h] [rbp+140h] BYREF
  _QWORD v108[4]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v109[16]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v110[24]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _QWORD v111[80]; // [rsp+2B8h] [rbp+1B8h] BYREF
  _BYTE v112[32]; // [rsp+538h] [rbp+438h] BYREF
  _BYTE v113[120]; // [rsp+558h] [rbp+458h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+628h] [rbp+528h]

  v6 = a2;
  v91 = a2;
  v87 = 0;
  v88 = 0;
  v82 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 24LL))(*a3, &v82);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v8,
      v66);
  std::wstring::wstring(v109, v82);
  v84 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 40LL))(*a3, &v84);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v9,
      v66);
  std::wstring::wstring(v108, v84);
  v86 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a3 + 48LL))(*a3, &v86);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v10,
      v66);
  v67 = WORD1(v86);
  Utility::FormatWstring(Buffer, (wchar_t *)L"%hu.%hu.%hu.%hu");
  v83 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 80LL))(*a3, &v83);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v11,
      v67);
  v71 = 0;
  std::wstring::wstring(v102, v83);
  std::wstring::operator=((char *)this + 776);
  StoreAppLanguage = StoreApplication::GetStoreAppLanguage(v102, *a3);
  Application::ComputeProgramId((__int64)v101, v109, v108, Buffer);
  v13 = v101;
  if ( v101[3] > 7u )
    v13 = (_QWORD *)v101[0];
  v14 = v102;
  if ( v103 > 7 )
    v14 = *(int **)v102;
  AslLogCallPrintf(3, "StoreApplication::GetStoreApplication", 104, "%ws | %ws", v14, v13);
  v16 = *((_DWORD *)v6 + 56);
  if ( !Application::ForceFullAppScan && v16 > 1 )
    Application::GetApplicationFromCache(this);
  if ( Application::IsValid(this, v15) )
  {
    v22 = (char *)this + 904;
    if ( !*((_QWORD *)this + 115) )
    {
      *(_OWORD *)sourceString = 0;
      *(__m128i *)length = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(sourceString[0]) = 0;
      StoreAppManifestPathFromPackage = StoreApplication::GetStoreAppManifestPathFromPackage(v104, a4, 1);
      std::wstring::operator=(sourceString, StoreAppManifestPathFromPackage);
      std::wstring::_Tidy_deallocate(v104);
      std::wstring::operator=((char *)this + 904);
      v96 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v96) = 0;
      v59 = StoreApplication::GetStoreAppManifestPathFromPackage(v104, a4, 2);
      std::wstring::operator=(&v96, v59);
      std::wstring::_Tidy_deallocate(v104);
      std::wstring::operator=((char *)this + 936);
      std::wstring::_Tidy_deallocate(&v96);
      std::wstring::_Tidy_deallocate(sourceString);
    }
  }
  else
  {
    Application::SetName(this, v109);
    Application::SetPublisher(this, v108);
    Application::SetVersion(this, Buffer);
    *((_DWORD *)this + 116) = StoreAppLanguage;
    std::wstring::operator=((char *)this + 56);
    std::wstring::operator=((char *)this + 776);
    std::wstring::operator=((char *)this + 336);
    std::wstring::operator=((char *)this + 368);
    pv[0] = 0;
    v18 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 72LL))(*a3, pv);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v18,
        v68);
    std::wstring::wstring(sourceString, pv[0]);
    std::wstring::operator=((char *)this + 744);
    v76 = 0;
    Windows::Internal::StringReference::StringReference(v104, v19);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
    v20 = Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager>(v104[0], &v76);
    if ( v20 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v20,
        v68);
    v106[0] = 0;
    v106[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v106[0]) = 0;
    if ( v16 )
    {
      v75 = 0;
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v24 = (const WCHAR *)sourceString;
      if ( *(_QWORD *)&length[2] > 7u )
        v24 = sourceString[0];
      v25 = WindowsCreateString(v24, length[0], &string);
      if ( v25 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xA6,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v25,
          v68);
      if ( *a4 )
      {
        v29 = v75;
      }
      else
      {
        v26 = v76;
        v27 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v76 + 136LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
        v28 = v27(v26, string, &v75);
        if ( v28 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xAB,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)(unsigned int)v28,
            v68);
        v29 = v75;
        if ( !v75 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xAC,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)0x80070490LL,
            v68);
      }
      if ( *a4 )
        v29 = *a4;
      v72 = v29;
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
      StoreAppInstallLocationFromPackage = StoreApplication::GetStoreAppInstallLocationFromPackage(v92, &v72);
      Application::SetInstallLocation(this, StoreAppInstallLocationFromPackage);
      std::wstring::_Tidy_deallocate(v92);
      StoreApplication::GetStoreAppInstallDateFromPackage(v92, &v72);
      std::wstring::operator=((char *)this + 256);
      std::wstring::_Tidy_deallocate(v92);
      v100[0] = 0;
      v100[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v100[0]) = 0;
      v31 = StoreApplication::GetStoreAppManifestPathFromPackage(v92, &v72, 1);
      std::wstring::operator=(v100, v31);
      std::wstring::_Tidy_deallocate(v92);
      v22 = (char *)this + 904;
      std::wstring::operator=((char *)this + 904);
      StoreApplication::GetPackageRelativeAppIDs(v100, &v87);
      v70 = 0;
      v32 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v72 + 64LL))(v72, &v70);
      if ( v32 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xC1,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v32,
          v68);
      *((_BYTE *)this + 969) = v70 != 0;
      StoreApplication::GetStoreAppType(v92, v100);
      std::wstring::operator=((char *)this + 808);
      std::wstring::_Tidy_deallocate(v92);
      v96 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v96) = 0;
      v33 = StoreApplication::GetStoreAppManifestPathFromPackage(v92, &v72, 2);
      std::wstring::operator=(&v96, v33);
      std::wstring::_Tidy_deallocate(v92);
      std::wstring::operator=((char *)this + 936);
      *((_BYTE *)this + 968) = StoreApplication::IsInboxStoreApp(v6, &v72);
      v79 = 0;
      v34 = v72;
      v35 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v72 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
      v36 = v35(v34, &v79);
      if ( v36 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xDA,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v36,
          v68);
      v81 = 0;
      v37 = *v79;
      *(_QWORD *)&v93 = &v81;
      *((_QWORD *)&v93 + 1) = 0;
      LOBYTE(v94) = 1;
      v38 = (*(__int64 (__fastcall **)(__int64 *, char *))(v37 + 48))(v79, (char *)&v93 + 8);
      if ( v38 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v38,
          v68);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&v93);
      StringRawBuffer = WindowsGetStringRawBuffer(v81, 0);
      std::wstring::wstring(&v93, StringRawBuffer);
      std::wstring::operator=((char *)this + 712);
      std::wstring::_Tidy_deallocate(&v93);
      Application::ComputeProgramInstanceId(this, v92);
      std::wstring::operator=((char *)this + 400);
      std::wstring::_Tidy_deallocate(v92);
      v78 = 0;
      v40 = v76;
      v41 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v76 + 120LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
      v42 = v41(v40, string, &v78);
      if ( v42 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v42,
          v68);
      v73 = 0;
      v43 = v78;
      v44 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v78 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
      v45 = v44(v43, &v73);
      if ( v45 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v45,
          v68);
      AllUserSids = Utility::GetAllUserSids(retaddr);
      std::vector<std::wstring>::vector<std::wstring>(&v89, AllUserSids);
      v69 = 0;
      v47 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v73 + 56LL))(v73, &v69);
      if ( v47 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v47,
          v68);
      while ( v69 )
      {
        v77 = 0;
        v48 = v73;
        v49 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v73 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
        v50 = v49(v48, &v77);
        if ( v50 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xF2,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)(unsigned int)v50,
            v68);
        v80 = 0;
        v51 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v77 + 48LL))(v77, &v80);
        if ( v51 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xF4,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)(unsigned int)v51,
            v68);
        v52 = WindowsGetStringRawBuffer(v80, 0);
        v53 = v89;
        v54 = v90;
        while ( v53 != v54 )
        {
          std::wstring::wstring(&v93, v53);
          v55 = -1;
          do
            ++v55;
          while ( v52[v55] );
          v56 = &v93;
          if ( v95 > 7 )
            v56 = (__int128 *)v93;
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v56, v94, v52) )
          {
            std::wstring::wstring(v92, v52);
            Application::AddUserSid(this, v92);
            std::wstring::_Tidy_deallocate(v92);
            std::wstring::_Tidy_deallocate(&v93);
            break;
          }
          std::wstring::_Tidy_deallocate(&v93);
          v53 = (struct File *)((char *)v53 + 32);
        }
        v57 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v73 + 64LL))(v73, &v69);
        if ( v57 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xFF,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)(unsigned int)v57,
            v68);
        Windows::Internal::String::~String((Windows::Internal::String *)&v80);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v77);
      }
      v71 = 1;
      std::vector<std::wstring>::_Tidy(&v89);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
      Windows::Internal::String::~String((Windows::Internal::String *)&v81);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
      std::wstring::_Tidy_deallocate(&v96);
      std::wstring::_Tidy_deallocate(v100);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
    }
    else
    {
      ExtractedAppxPackagePath = ConfigSettings::GetExtractedAppxPackagePath(v6, v92);
      Application::SetInstallLocation(this, ExtractedAppxPackagePath);
      std::wstring::_Tidy_deallocate(v92);
      ConfigSettings::GetExtractedAppxManifestPath(v6, v92);
      v22 = (char *)this + 904;
      std::wstring::operator=((char *)this + 904);
      std::wstring::_Tidy_deallocate(v92);
      ExtractedAppxManifestPath = ConfigSettings::GetExtractedAppxManifestPath(v6, &v96);
      StoreApplication::GetStoreAppType(v92, ExtractedAppxManifestPath);
      std::wstring::operator=((char *)this + 808);
      std::wstring::_Tidy_deallocate(v92);
      std::wstring::_Tidy_deallocate(&v96);
      ConfigSettings::GetExtractedAppxBundlePath(v6, v92);
      std::wstring::operator=((char *)this + 936);
      std::wstring::_Tidy_deallocate(v92);
    }
    std::wstring::_Tidy_deallocate(v106);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
    std::wstring::_Tidy_deallocate(sourceString);
    CoTaskMemFree(pv[0]);
  }
  if ( *((_DWORD *)v6 + 2) != 5 && v16 != 2 )
  {
    v93 = 0;
    v94 = 0;
    std::wstring::wstring(v92, L".exe");
    std::vector<std::wstring>::push_back(&v93, v92);
    std::wstring::_Tidy_deallocate(v92);
    if ( *((_DWORD *)v6 + 2) == 1 )
    {
      std::wstring::wstring(v92, L".dll");
      std::vector<std::wstring>::push_back(&v93, v92);
      std::wstring::_Tidy_deallocate(v92);
      std::wstring::wstring(v92, L".js");
      std::vector<std::wstring>::push_back(&v93, v92);
      std::wstring::_Tidy_deallocate(v92);
      std::wstring::wstring(v92, L".pri");
      std::vector<std::wstring>::push_back(&v93, v92);
      std::wstring::_Tidy_deallocate(v92);
      std::wstring::wstring(v92, L".htm");
      std::vector<std::wstring>::push_back(&v93, v92);
      std::wstring::_Tidy_deallocate(v92);
      std::wstring::wstring(v92, L".html");
      std::vector<std::wstring>::push_back(&v93, v92);
      std::wstring::_Tidy_deallocate(v92);
      std::wstring::wstring(v92, L".xhtml");
      std::vector<std::wstring>::push_back(&v93, v92);
      std::wstring::_Tidy_deallocate(v92);
      std::wstring::wstring(v92, L".winmd");
      std::vector<std::wstring>::push_back(&v93, v92);
      std::wstring::_Tidy_deallocate(v92);
    }
    pv[0] = v100;
    v60 = std::vector<std::wstring>::vector<std::wstring>(v100, &v93);
    v61 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 2) + 40LL))((char *)this + 16);
    File::SearchForPeFiles((unsigned int)&v89, (_DWORD)v6, v61, v60, v68, (__int64)v101);
    v62 = v89;
    if ( v89 != v90 )
    {
      do
      {
        File::File((File *)v110, v62);
        v63 = v111;
        if ( v111[3] > 7u )
          v63 = (_QWORD *)v111[0];
        AslLogCallPrintf(3, "StoreApplication::GetStoreApplication", 300, "%ws", v63);
        Utility::ToLower(v92, v111);
        v65 = *((_QWORD *)&v87 + 1);
        for ( i = v87; i != v65; i += 64 )
        {
          std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(v104, i);
          if ( std::wstring::find(v92, v105) != -1 )
          {
            std::wstring::operator=(v113);
            std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v104);
            break;
          }
          std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v104);
        }
        std::wstring::operator=(v112);
        std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::emplace<File &>(
          (char *)this + 24,
          pv,
          v110);
        std::wstring::_Tidy_deallocate(v92);
        File::~File((File *)v110);
        v62 = (struct File *)((char *)v62 + 816);
      }
      while ( v62 != v90 );
      v6 = v91;
    }
    std::vector<File>::_Tidy(&v89);
    std::vector<std::wstring>::_Tidy(&v93);
  }
  if ( v71 )
    Application::SaveApplicationToCache(this, v6);
  if ( *((_BYTE *)v6 + 220) )
  {
    if ( *((_QWORD *)v22 + 2) )
    {
      LOBYTE(v17) = 1;
      StoreApplication::GetStoreAppManifestXml(v92, v22, v17);
      std::wstring::operator=((char *)this + 840);
      std::wstring::_Tidy_deallocate(v92);
    }
    if ( *((_QWORD *)this + 119) )
    {
      StoreApplication::GetStoreAppManifestXml(v92, (char *)this + 936, 0);
      std::wstring::operator=((char *)this + 872);
      std::wstring::_Tidy_deallocate(v92);
    }
  }
  std::wstring::_Tidy_deallocate(v101);
  std::wstring::_Tidy_deallocate(v102);
  CoTaskMemFree(v83);
  std::wstring::_Tidy_deallocate(Buffer);
  std::wstring::_Tidy_deallocate(v108);
  CoTaskMemFree(v84);
  std::wstring::_Tidy_deallocate(v109);
  CoTaskMemFree(v82);
  if ( (_QWORD)v87 )
  {
    std::_Destroy_range<std::allocator<std::pair<std::wstring,std::wstring>>>(v87, *((_QWORD *)&v87 + 1));
    std::_Deallocate<16>(v87, (v88 - v87) & 0xFFFFFFFFFFFFFFC0uLL);
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
