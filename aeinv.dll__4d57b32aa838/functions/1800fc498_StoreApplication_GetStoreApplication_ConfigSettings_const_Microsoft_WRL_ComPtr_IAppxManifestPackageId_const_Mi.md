# StoreApplication::GetStoreApplication(ConfigSettings const &,Microsoft::WRL::ComPtr<IAppxManifestPackageId> const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)

- ea: `0x1800fc498`
- end: `0x1800fd47c`
- name: `?GetStoreApplication@StoreApplication@@QEAAXAEBVConfigSettings@@AEBV?$ComPtr@UIAppxManifestPackageId@@@WRL@Microsoft@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@45@@Z`
- size: `4068`
- prototype: `__int64 __fastcall(struct IAmiInventoryItem *, struct ConfigSettings *)`
- caller_count: `1`
- callee_count: `58`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003dc7c`

## callees

- `0x18000a39c`
- `0x18000dfc4`
- `0x18000eb5c`
- `0x18000ecac`
- `0x1800118d0`
- `0x1800150ac`
- `0x180015f74`
- `0x18001716c`
- `0x180018300`
- `0x180018450`
- `0x1800188f4`
- `0x180018a60`
- `0x1800197d4`
- `0x18001d31c`
- `0x18001e0d0`
- `0x18001f27c`
- `0x180022500`
- `0x180029388`
- `0x18002a36c`
- `0x18002b55c`
- `0x180034908`
- `0x180034ff0`
- `0x18003dcec`
- `0x18003dd14`
- `0x18003ed14`
- `0x1800403ac`
- `0x180040414`
- `0x1800404c4`
- `0x180041f68`
- `0x18004225c`
- `0x180042280`
- `0x180042d0c`
- `0x1800461c4`
- `0x180046510`
- `0x1800493b8`
- `0x18004f010`
- `0x18004f820`
- `0x180051834`
- `0x180052f28`
- `0x180054154`
- `0x180054f2c`
- `0x180057e28`
- `0x180059920`
- `0x1800679f8`
- `0x180070d28`
- `0x1800f6efc`
- `0x1800f7398`
- `0x1800f8528`
- `0x1800f92d0`
- `0x1800fbd04`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800fce28`
- `ole32!CoTaskMemFree` at `0x1800fd26f`
- `ole32!CoTaskMemFree` at `0x1800fd294`
- `ole32!CoTaskMemFree` at `0x1800fd2ac`
- `ole32!CoTaskMemFree` at `0x1800fce28`
- `ole32!CoTaskMemFree` at `0x1800fd26f`
- `ole32!CoTaskMemFree` at `0x1800fd294`
- `ole32!CoTaskMemFree` at `0x1800fd2ac`

## string_xrefs

- `0x1800fd2ff`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd317`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd32f`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd344`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd359`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd36e`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd383`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd398`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd3ad`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd3c2`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd3d7`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd3ec`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd401`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd416`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd42b`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd440`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd455`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x1800fd46a`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
void __fastcall StoreApplication::GetStoreApplication(
        struct IAmiInventoryItem *a1,
        struct ConfigSettings *a2,
        _QWORD *a3,
        __int64 *a4)
{
  struct ConfigSettings *v6; // r15
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int StoreAppLanguage; // r14d
  int *v13; // rax
  const struct ConfigSettings *v14; // rdx
  unsigned int v15; // r13d
  int v16; // eax
  const unsigned __int16 (*v17)[45]; // rdx
  int v18; // eax
  __int64 ExtractedAppxPackagePath; // rax
  __int64 ExtractedAppxManifestPath; // rax
  _QWORD *v21; // r14
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 ExtractedAppxBundlePath; // rax
  const WCHAR *v25; // rcx
  HRESULT v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING, __int64 *); // rbx
  int v29; // eax
  __int64 v30; // rcx
  __int64 StoreAppInstallLocationFromPackage; // rdx
  __int64 StoreAppInstallDateFromPackage; // rax
  __int64 v33; // rax
  int v34; // eax
  __int64 StoreAppType; // rax
  __int64 v36; // rax
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, __int64 **); // rbx
  int v39; // eax
  __int64 v40; // rax
  int v41; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v43; // rax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, HSTRING, __int64 *); // rbx
  int v46; // eax
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, __int64 *); // rbx
  int v49; // eax
  __int64 AllUserSids; // rax
  int v51; // eax
  __int64 v52; // rdi
  __int64 (__fastcall *v53)(__int64, __int64 *); // rbx
  int v54; // eax
  int v55; // eax
  PCWSTR v56; // rdi
  struct File *v57; // rbx
  struct File *v58; // r12
  __int64 v59; // r9
  _QWORD *v60; // rcx
  int v61; // eax
  __int64 StoreAppManifestPathFromPackage; // rax
  __int64 v63; // rax
  __int64 v64; // rbx
  __int64 v65; // rax
  struct File *v66; // rdi
  __int64 i; // rbx
  __int64 v68; // r12
  int v69; // [rsp+20h] [rbp-E0h]
  int v70; // [rsp+20h] [rbp-E0h]
  __int64 v71; // [rsp+20h] [rbp-E0h]
  char v72; // [rsp+40h] [rbp-C0h] BYREF
  char v73; // [rsp+41h] [rbp-BFh] BYREF
  char v74; // [rsp+42h] [rbp-BEh]
  __int64 v75; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v76; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v78; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v79; // [rsp+68h] [rbp-98h] BYREF
  __int64 v80; // [rsp+70h] [rbp-90h] BYREF
  __int64 v81; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v82; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v83; // [rsp+88h] [rbp-78h] BYREF
  HSTRING v84; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v85; // [rsp+98h] [rbp-68h] BYREF
  LPVOID v86; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v87; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID pv[2]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v89; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v90; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v91; // [rsp+D8h] [rbp-28h]
  struct File *v92; // [rsp+E0h] [rbp-20h] BYREF
  struct File *v93; // [rsp+E8h] [rbp-18h]
  struct ConfigSettings *v94; // [rsp+F8h] [rbp-8h]
  __int64 v95; // [rsp+100h] [rbp+0h]
  _BYTE v96[32]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v97; // [rsp+128h] [rbp+28h] BYREF
  __int64 v98; // [rsp+138h] [rbp+38h]
  _QWORD v99[4]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v100[32]; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v101[3]; // [rsp+188h] [rbp+88h] BYREF
  int v102[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  unsigned __int64 v103; // [rsp+1C0h] [rbp+C0h]
  PCNZWCH sourceString[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  UINT32 length; // [rsp+1D8h] [rbp+D8h]
  unsigned __int64 v106; // [rsp+1E0h] [rbp+E0h]
  _BYTE v107[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v108[32]; // [rsp+210h] [rbp+110h] BYREF
  wchar_t v109[16]; // [rsp+230h] [rbp+130h] BYREF
  _QWORD v110[4]; // [rsp+250h] [rbp+150h] BYREF
  _QWORD v111[4]; // [rsp+270h] [rbp+170h] BYREF
  HSTRING v112; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v113[24]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v114[3]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v115[32]; // [rsp+548h] [rbp+448h] BYREF
  _BYTE v116[120]; // [rsp+568h] [rbp+468h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+638h] [rbp+538h]

  v95 = -2;
  v6 = a2;
  v94 = a2;
  v90 = 0;
  v91 = 0;
  v85 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 24LL))(*a3, &v85);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v8,
      v69);
  std::wstring::wstring(v111, v85);
  v87 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 40LL))(*a3, &v87);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v9,
      v69);
  std::wstring::wstring(v110, v87);
  v89 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(*(_QWORD *)*a3 + 48LL))(*a3, &v89);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v10,
      v69);
  v70 = WORD1(v89);
  Utility::FormatWstring(v109, L"%hu.%hu.%hu.%hu", HIWORD(v89), WORD2(v89));
  v86 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 80LL))(*a3, &v86);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v11,
      v70);
  v74 = 0;
  std::wstring::wstring(v102, v86);
  std::wstring::operator=((char *)a1 + 776, v102);
  StoreAppLanguage = StoreApplication::GetStoreAppLanguage(v102, *a3);
  Application::ComputeProgramId((__int64)v101, v111, v110, v109, StoreAppLanguage);
  v13 = v102;
  if ( v103 > 7 )
    v13 = *(int **)v102;
  v71 = (__int64)v13;
  AslLogCallPrintf(3, (unsigned int)"StoreApplication::GetStoreApplication", 104, (unsigned int)"%ws | %ws");
  v15 = *((_DWORD *)v6 + 56);
  if ( !Application::ForceFullAppScan && v15 > 1 )
    Application::GetApplicationFromCache(a1);
  if ( Application::IsValid(a1, v14) )
  {
    v21 = (_QWORD *)((char *)a1 + 904);
    if ( !*((_QWORD *)a1 + 115) )
    {
      std::wstring::wstring(v100);
      StoreAppManifestPathFromPackage = StoreApplication::GetStoreAppManifestPathFromPackage(v107, a4, 1);
      std::wstring::operator=(v100, StoreAppManifestPathFromPackage);
      std::wstring::~wstring(v107);
      std::wstring::operator=((char *)a1 + 904, v100);
      std::wstring::wstring(v96);
      v63 = StoreApplication::GetStoreAppManifestPathFromPackage(v107, a4, 2);
      std::wstring::operator=(v96, v63);
      std::wstring::~wstring(v107);
      std::wstring::operator=((char *)a1 + 936, v96);
      std::wstring::~wstring(v96);
      std::wstring::~wstring(v100);
    }
  }
  else
  {
    Application::SetName(a1, v111);
    Application::SetPublisher(a1, v110);
    Application::SetVersion(a1, v109);
    *((_DWORD *)a1 + 116) = StoreAppLanguage;
    std::wstring::operator=((char *)a1 + 56, v101);
    std::wstring::operator=((char *)a1 + 776, v102);
    std::wstring::operator=((char *)a1 + 336, &Application::ApplicationSourceAppxPackage);
    std::wstring::operator=((char *)a1 + 368, Application::ApplicationTypeApplication);
    pv[0] = 0;
    v16 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 72LL))(*a3, pv);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v16,
        v71);
    std::wstring::wstring(sourceString, pv[0]);
    std::wstring::operator=((char *)a1 + 744, sourceString);
    v79 = 0;
    Windows::Internal::StringReference::StringReference(&v112, v17);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v79);
    v18 = Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager>(v112, &v79);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v18,
        v71);
    std::wstring::wstring(v107);
    if ( v15 )
    {
      v78 = 0;
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v25 = (const WCHAR *)sourceString;
      if ( v106 > 7 )
        v25 = sourceString[0];
      v26 = WindowsCreateString(v25, length, &string);
      if ( v26 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xA6,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
          (const char *)(unsigned int)v26,
          v71);
      if ( *a4 )
      {
        v30 = v78;
      }
      else
      {
        v27 = v79;
        v28 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v79 + 136LL);
        Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v78);
        v29 = v28(v27, string, &v78);
        if ( v29 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xAB,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
            (const char *)(unsigned int)v29,
            v71);
        v30 = v78;
        if ( !v78 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xAC,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
            (const char *)0x80070490LL,
            v71);
      }
      if ( *a4 )
        v30 = *a4;
      v75 = v30;
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
      StoreAppInstallLocationFromPackage = StoreApplication::GetStoreAppInstallLocationFromPackage(v96, &v75);
      Application::SetInstallLocation(a1, StoreAppInstallLocationFromPackage);
      std::wstring::~wstring(v96);
      StoreAppInstallDateFromPackage = StoreApplication::GetStoreAppInstallDateFromPackage(v96, &v75);
      std::wstring::operator=((char *)a1 + 256, StoreAppInstallDateFromPackage);
      std::wstring::~wstring(v96);
      std::wstring::wstring(v100);
      v33 = StoreApplication::GetStoreAppManifestPathFromPackage(v96, &v75, 1);
      std::wstring::operator=(v100, v33);
      std::wstring::~wstring(v96);
      v21 = (_QWORD *)((char *)a1 + 904);
      std::wstring::operator=((char *)a1 + 904, v100);
      StoreApplication::GetPackageRelativeAppIDs(v100, &v90);
      v73 = 0;
      v34 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v75 + 64LL))(v75, &v73);
      if ( v34 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xC1,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
          (const char *)(unsigned int)v34,
          v71);
      *((_BYTE *)a1 + 969) = v73 != 0;
      StoreAppType = StoreApplication::GetStoreAppType(v96, v100);
      std::wstring::operator=((char *)a1 + 808, StoreAppType);
      std::wstring::~wstring(v96);
      std::wstring::wstring(v96);
      v36 = StoreApplication::GetStoreAppManifestPathFromPackage(v99, &v75, 2);
      std::wstring::operator=(v96, v36);
      std::wstring::~wstring(v99);
      std::wstring::operator=((char *)a1 + 936, v96);
      *((_BYTE *)a1 + 968) = StoreApplication::IsInboxStoreApp(v6, &v75);
      v82 = 0;
      v37 = v75;
      v38 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v75 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v82);
      v39 = v38(v37, &v82);
      if ( v39 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xDA,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
          (const char *)(unsigned int)v39,
          v71);
      v84 = 0;
      v40 = *v82;
      *(_QWORD *)&v97 = &v84;
      *((_QWORD *)&v97 + 1) = 0;
      LOBYTE(v98) = 1;
      v41 = (*(__int64 (__fastcall **)(__int64 *, char *))(v40 + 48))(v82, (char *)&v97 + 8);
      if ( v41 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
          (const char *)(unsigned int)v41,
          v71);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&v97);
      StringRawBuffer = WindowsGetStringRawBuffer(v84, 0);
      std::wstring::wstring(v99, StringRawBuffer);
      std::wstring::operator=((char *)a1 + 712, v99);
      std::wstring::~wstring(v99);
      v43 = Application::ComputeProgramInstanceId((__int64)a1, (__int64)v99);
      std::wstring::operator=((char *)a1 + 400, v43);
      std::wstring::~wstring(v99);
      v81 = 0;
      v44 = v79;
      v45 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v79 + 120LL);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v81);
      v46 = v45(v44, string, &v81);
      if ( v46 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
          (const char *)(unsigned int)v46,
          v71);
      v76 = 0;
      v47 = v81;
      v48 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v81 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v76);
      v49 = v48(v47, &v76);
      if ( v49 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
          (const char *)(unsigned int)v49,
          v71);
      AllUserSids = Utility::GetAllUserSids(0);
      std::vector<std::wstring>::vector<std::wstring>(&v92, AllUserSids);
      v72 = 0;
      v51 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v76 + 56LL))(v76, &v72);
      if ( v51 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
          (const char *)(unsigned int)v51,
          v71);
      while ( v72 )
      {
        v80 = 0;
        v52 = v76;
        v53 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v76 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v80);
        v54 = v53(v52, &v80);
        if ( v54 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xF2,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
            (const char *)(unsigned int)v54,
            v71);
        v83 = 0;
        v55 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v80 + 48LL))(v80, &v83);
        if ( v55 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xF4,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
            (const char *)(unsigned int)v55,
            v71);
        v56 = WindowsGetStringRawBuffer(v83, 0);
        v57 = v92;
        v58 = v93;
        while ( v57 != v58 )
        {
          std::wstring::wstring(v99, v57);
          v59 = -1;
          do
            ++v59;
          while ( v56[v59] );
          v60 = v99;
          if ( v99[3] > 7u )
            v60 = (_QWORD *)v99[0];
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v60, v99[2], v56, v59, v71) )
          {
            std::wstring::wstring(&v97, v56);
            Application::AddUserSid(a1, &v97);
            std::wstring::~wstring(&v97);
            std::wstring::~wstring(v99);
            break;
          }
          std::wstring::~wstring(v99);
          v57 = (struct File *)((char *)v57 + 32);
        }
        v61 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v76 + 64LL))(v76, &v72);
        if ( v61 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xFF,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
            (const char *)(unsigned int)v61,
            v71);
        Windows::Internal::String::~String((Windows::Internal::String *)&v83);
        Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v80);
      }
      v74 = 1;
      std::vector<std::wstring>::_Tidy(&v92);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v76);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v81);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v84);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v82);
      std::wstring::~wstring(v96);
      std::wstring::~wstring(v100);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v75);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v78);
    }
    else
    {
      ExtractedAppxPackagePath = ConfigSettings::GetExtractedAppxPackagePath(v6, v96);
      Application::SetInstallLocation(a1, ExtractedAppxPackagePath);
      std::wstring::~wstring(v96);
      ExtractedAppxManifestPath = ConfigSettings::GetExtractedAppxManifestPath(v6, v96);
      v21 = (_QWORD *)((char *)a1 + 904);
      std::wstring::operator=((char *)a1 + 904, ExtractedAppxManifestPath);
      std::wstring::~wstring(v96);
      v22 = ConfigSettings::GetExtractedAppxManifestPath(v6, v100);
      v23 = StoreApplication::GetStoreAppType(v96, v22);
      std::wstring::operator=((char *)a1 + 808, v23);
      std::wstring::~wstring(v96);
      std::wstring::~wstring(v100);
      ExtractedAppxBundlePath = ConfigSettings::GetExtractedAppxBundlePath(v6, v96);
      std::wstring::operator=((char *)a1 + 936, ExtractedAppxBundlePath);
      std::wstring::~wstring(v96);
    }
    std::wstring::~wstring(v107);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v79);
    std::wstring::~wstring(sourceString);
    CoTaskMemFree(pv[0]);
  }
  if ( *((_DWORD *)v6 + 2) != 5 && v15 != 2 )
  {
    v97 = 0;
    v98 = 0;
    std::wstring::wstring(v96, L".exe");
    std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v97, v96);
    std::wstring::~wstring(v96);
    if ( *((_DWORD *)v6 + 2) == 1 )
    {
      std::wstring::wstring(v96, L".dll");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v97, v96);
      std::wstring::~wstring(v96);
      std::wstring::wstring(v96, L".js");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v97, v96);
      std::wstring::~wstring(v96);
      std::wstring::wstring(v96, L".pri");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v97, v96);
      std::wstring::~wstring(v96);
      std::wstring::wstring(v96, L".htm");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v97, v96);
      std::wstring::~wstring(v96);
      std::wstring::wstring(v96, L".html");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v97, v96);
      std::wstring::~wstring(v96);
      std::wstring::wstring(v96, L".xhtml");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v97, v96);
      std::wstring::~wstring(v96);
      std::wstring::wstring(v96, L".winmd");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v97, v96);
      std::wstring::~wstring(v96);
    }
    pv[0] = v99;
    v64 = std::vector<std::wstring>::vector<std::wstring>(v99, &v97);
    v65 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)a1 + 2) + 40LL))((char *)a1 + 16, *((_QWORD *)a1 + 2));
    File::SearchForPeFiles((__int64)&v92, v6, v65, v64, v71, (int)v101, 0);
    v66 = v92;
    if ( v92 != v93 )
    {
      do
      {
        File::File((File *)v113, v66);
        AslLogCallPrintf(3, (unsigned int)"StoreApplication::GetStoreApplication", 300, (unsigned int)"%ws");
        Utility::ToLower((__int64)v96, v114);
        v68 = *((_QWORD *)&v90 + 1);
        for ( i = v90; i != v68; i += 64 )
        {
          std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(v107, i);
          if ( std::wstring::find(v96, v108) != -1 )
          {
            std::wstring::operator=(v116, v107);
            std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v107);
            break;
          }
          std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v107);
        }
        std::wstring::operator=(v115, (char *)a1 + 744);
        std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::emplace<File &>(
          (char *)a1 + 24,
          pv,
          v113);
        std::wstring::~wstring(v96);
        File::~File((File *)v113);
        v66 = (struct File *)((char *)v66 + 816);
      }
      while ( v66 != v93 );
      v6 = v94;
    }
    std::vector<File>::_Tidy(&v92);
    std::vector<std::wstring>::_Tidy(&v97);
  }
  if ( v74 )
    Application::SaveApplicationToCache(a1, v6);
  if ( *((_BYTE *)v6 + 220) )
  {
    if ( v21[2] )
    {
      StoreApplication::GetStoreAppManifestXml((__int64)v96, v21, 1);
      std::wstring::operator=((char *)a1 + 840, v96);
      std::wstring::~wstring(v96);
    }
    if ( *((_QWORD *)a1 + 119) )
    {
      StoreApplication::GetStoreAppManifestXml((__int64)v96, (_QWORD *)a1 + 117, 0);
      std::wstring::operator=((char *)a1 + 872, v96);
      std::wstring::~wstring(v96);
    }
  }
  std::wstring::~wstring(v101);
  std::wstring::~wstring(v102);
  CoTaskMemFree(v86);
  std::wstring::~wstring(v109);
  std::wstring::~wstring(v110);
  CoTaskMemFree(v87);
  std::wstring::~wstring(v111);
  CoTaskMemFree(v85);
  if ( (_QWORD)v90 )
  {
    std::_Destroy_range<std::allocator<std::pair<std::wstring,std::wstring>>>(v90, *((_QWORD *)&v90 + 1));
    std::_Deallocate<16>(v90, (v91 - v90) & 0xFFFFFFFFFFFFFFC0uLL);
  }
}

```

## disassembly

```asm
0x1800fc498  push    rbp
0x1800fc49a  push    rbx
0x1800fc49b  push    rsi
0x1800fc49c  push    rdi
0x1800fc49d  push    r12
0x1800fc49f  push    r13
0x1800fc4a1  push    r14
0x1800fc4a3  push    r15
0x1800fc4a5  lea     rbp, [rsp-4F8h]
0x1800fc4ad  sub     rsp, 5F8h
0x1800fc4b4  mov     [rbp+530h+var_530], 0FFFFFFFFFFFFFFFEh
0x1800fc4bc  mov     rax, cs:__security_cookie
0x1800fc4c3  xor     rax, rsp
0x1800fc4c6  mov     [rbp+530h+var_50], rax
0x1800fc4cd  mov     r12, r9
0x1800fc4d0  mov     rbx, r8
0x1800fc4d3  mov     r15, rdx
0x1800fc4d6  mov     [rbp+530h+var_538], rdx
0x1800fc4da  mov     rsi, rcx
0x1800fc4dd  xorps   xmm0, xmm0
0x1800fc4e0  movdqu  [rbp+530h+var_568], xmm0
0x1800fc4e5  xor     edi, edi
0x1800fc4e7  mov     [rbp+530h+var_558], rdi
0x1800fc4eb  mov     [rbp+530h+var_598], rdi
0x1800fc4ef  mov     rcx, [r8]
0x1800fc4f2  mov     rax, [rcx]
0x1800fc4f5  lea     rdx, [rbp+530h+var_598]
0x1800fc4f9  mov     rax, [rax+18h]
0x1800fc4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc502  mov     rcx, [rbp+538h]; this
0x1800fc509  test    eax, eax
0x1800fc50b  js      loc_1800FD341
0x1800fc511  mov     rdx, [rbp+530h+var_598]
0x1800fc515  lea     rcx, [rbp+530h+var_3C0]
0x1800fc51c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800fc521  nop
0x1800fc522  mov     [rbp+530h+var_588], rdi
0x1800fc526  mov     rcx, [rbx]
0x1800fc529  mov     rax, [rcx]
0x1800fc52c  lea     rdx, [rbp+530h+var_588]
0x1800fc530  mov     rax, [rax+28h]
0x1800fc534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc539  mov     rcx, [rbp+538h]; this
0x1800fc540  test    eax, eax
0x1800fc542  js      loc_1800FD356
0x1800fc548  mov     rdx, [rbp+530h+var_588]
0x1800fc54c  lea     rcx, [rbp+530h+var_3E0]
0x1800fc553  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800fc558  nop
0x1800fc559  mov     [rbp+530h+var_570], rdi
0x1800fc55d  mov     rcx, [rbx]
0x1800fc560  mov     rax, [rcx]
0x1800fc563  lea     rdx, [rbp+530h+var_570]
0x1800fc567  mov     rax, [rax+30h]
0x1800fc56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc570  mov     rcx, [rbp+538h]; this
0x1800fc577  test    eax, eax
0x1800fc579  js      loc_1800FD36B
0x1800fc57f  mov     r8, [rbp+530h+var_570]
0x1800fc583  movzx   edx, r8w
0x1800fc587  mov     rax, r8
0x1800fc58a  shr     rax, 10h
0x1800fc58e  movzx   ecx, ax
0x1800fc591  mov     rax, r8
0x1800fc594  shr     rax, 20h
0x1800fc598  movzx   r9d, ax
0x1800fc59c  shr     r8, 30h
0x1800fc5a0  mov     dword ptr [rsp+630h+var_608], edx
0x1800fc5a4  mov     [rsp+630h+var_610], ecx; int
0x1800fc5a8  lea     rdx, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x1800fc5af  lea     rcx, [rbp+530h+var_400]
0x1800fc5b6  call    ?FormatWstring@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Utility::FormatWstring(ushort const *,...)
0x1800fc5bb  nop
0x1800fc5bc  mov     [rbp+530h+var_590], rdi
0x1800fc5c0  mov     rcx, [rbx]
0x1800fc5c3  mov     rax, [rcx]
0x1800fc5c6  lea     rdx, [rbp+530h+var_590]
0x1800fc5ca  mov     rax, [rax+50h]
0x1800fc5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc5d3  mov     rcx, [rbp+538h]; this
0x1800fc5da  test    eax, eax
0x1800fc5dc  js      loc_1800FD380
0x1800fc5e2  mov     [rsp+630h+var_5EE], dil
0x1800fc5e7  mov     rdx, [rbp+530h+var_590]
0x1800fc5eb  lea     rcx, [rbp+530h+var_488]
0x1800fc5f2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800fc5f7  nop
0x1800fc5f8  lea     rdi, [rsi+308h]
0x1800fc5ff  lea     rdx, [rbp+530h+var_488]
0x1800fc606  mov     rcx, rdi
0x1800fc609  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800fc60e  mov     rdx, [rbx]
0x1800fc611  lea     rcx, [rbp+530h+var_488]
0x1800fc618  call    ?GetStoreAppLanguage@StoreApplication@@SAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIAppxManifestPackageId@@@Z; StoreApplication::GetStoreAppLanguage(std::wstring const &,IAppxManifestPackageId *)
0x1800fc61d  mov     r14d, eax
0x1800fc620  mov     [rsp+630h+var_610], eax
0x1800fc624  lea     r9, [rbp+530h+var_400]
0x1800fc62b  lea     r8, [rbp+530h+var_3E0]
0x1800fc632  lea     rdx, [rbp+530h+var_3C0]
0x1800fc639  lea     rcx, [rbp+530h+var_4A8]
0x1800fc640  call    ?ComputeProgramId@Application@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00K@Z; Application::ComputeProgramId(std::wstring const &,std::wstring const &,std::wstring const &,ulong)
0x1800fc645  nop
0x1800fc646  lea     rcx, [rbp+530h+var_4A8]
0x1800fc64d  cmp     [rbp+530h+var_490], 7
0x1800fc655  cmova   rcx, [rbp+530h+var_4A8]
0x1800fc65d  lea     rax, [rbp+530h+var_488]
0x1800fc664  cmp     [rbp+530h+var_470], 7
0x1800fc66c  cmova   rax, qword ptr [rbp+530h+var_488]
0x1800fc674  mov     [rsp+630h+var_608], rcx
0x1800fc679  mov     qword ptr [rsp+630h+var_610], rax; int
0x1800fc67e  lea     r9, aWsWs; "%ws | %ws"
0x1800fc685  mov     r8d, 68h ; 'h'
0x1800fc68b  lea     rdx, aStoreapplicati_4; "StoreApplication::GetStoreApplication"
0x1800fc692  lea     ecx, [r8-65h]
0x1800fc696  call    AslLogCallPrintf
0x1800fc69b  mov     r13d, [r15+0E0h]
0x1800fc6a2  cmp     cs:?ForceFullAppScan@Application@@1_NA, 0; bool Application::ForceFullAppScan
0x1800fc6a9  jnz     short loc_1800FC6C3
0x1800fc6ab  cmp     r13d, 1
0x1800fc6af  jbe     short loc_1800FC6C3
0x1800fc6b1  lea     r8, [rbp+530h+var_4A8]
0x1800fc6b8  mov     rdx, r15
0x1800fc6bb  mov     rcx, rsi; struct IAmiInventoryItem *
0x1800fc6be  call    ?GetApplicationFromCache@Application@@QEAAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::GetApplicationFromCache(ConfigSettings const &,std::wstring const &)
0x1800fc6c3  mov     rcx, rsi; this
0x1800fc6c6  call    ?IsValid@Application@@QEAA_NAEBVConfigSettings@@@Z; Application::IsValid(ConfigSettings const &)
0x1800fc6cb  test    al, al
0x1800fc6cd  jnz     loc_1800FCE33
0x1800fc6d3  lea     rdx, [rbp+530h+var_3C0]
0x1800fc6da  mov     rcx, rsi
0x1800fc6dd  call    ?SetName@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetName(std::wstring const &)
0x1800fc6e2  lea     rdx, [rbp+530h+var_3E0]
0x1800fc6e9  mov     rcx, rsi
0x1800fc6ec  call    ?SetPublisher@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetPublisher(std::wstring const &)
0x1800fc6f1  lea     rdx, [rbp+530h+var_400]
0x1800fc6f8  mov     rcx, rsi
0x1800fc6fb  call    ?SetVersion@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetVersion(std::wstring const &)
0x1800fc700  mov     [rsi+1D0h], r14d
0x1800fc707  lea     rcx, [rsi+38h]
0x1800fc70b  lea     rdx, [rbp+530h+var_4A8]
0x1800fc712  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800fc717  lea     rdx, [rbp+530h+var_488]
0x1800fc71e  mov     rcx, rdi
0x1800fc721  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800fc726  lea     rcx, [rsi+150h]
0x1800fc72d  lea     rdx, ?ApplicationSourceAppxPackage@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationSourceAppxPackage
0x1800fc734  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800fc739  lea     rcx, [rsi+170h]
0x1800fc740  lea     rdx, ?ApplicationTypeApplication@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationTypeApplication
0x1800fc747  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800fc74c  xor     edi, edi
0x1800fc74e  mov     [rbp+530h+pv], rdi
0x1800fc752  mov     rcx, [rbx]
0x1800fc755  mov     rax, [rcx]
0x1800fc758  lea     rdx, [rbp+530h+pv]
0x1800fc75c  mov     rax, [rax+48h]
0x1800fc760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc765  mov     rcx, [rbp+538h]; this
0x1800fc76c  test    eax, eax
0x1800fc76e  js      loc_1800FD395
0x1800fc774  mov     rdx, [rbp+530h+pv]
0x1800fc778  lea     rcx, [rbp+530h+sourceString]
0x1800fc77f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800fc784  nop
0x1800fc785  lea     rcx, [rsi+2E8h]
0x1800fc78c  lea     rdx, [rbp+530h+sourceString]
0x1800fc793  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800fc798  mov     [rsp+630h+var_5C8], rdi
0x1800fc79d  lea     rcx, [rbp+530h+var_3A0]; string
0x1800fc7a4  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800fc7a9  lea     rcx, [rsp+630h+var_5C8]
0x1800fc7ae  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800fc7b3  lea     rdx, [rsp+630h+var_5C8]
0x1800fc7b8  mov     rcx, [rbp+530h+var_3A0]
0x1800fc7bf  call    ??$ActivateInstance@UIPackageManager@Deployment@Management@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIPackageManager@Deployment@Management@1@@Z; Windows::Foundation::ActivateInstance<Windows::Management::Deployment::IPackageManager>(HSTRING__ *,Windows::Management::Deployment::IPackageManager * *)
0x1800fc7c4  mov     rcx, [rbp+538h]; this
0x1800fc7cb  test    eax, eax
0x1800fc7cd  js      loc_1800FD3AA
0x1800fc7d3  lea     rcx, [rbp+530h+var_440]
0x1800fc7da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800fc7df  nop
0x1800fc7e0  test    r13d, r13d
0x1800fc7e3  jnz     loc_1800FC89F
0x1800fc7e9  lea     rdx, [rbp+530h+var_528]
0x1800fc7ed  mov     rcx, r15
0x1800fc7f0  call    ?GetExtractedAppxPackagePath@ConfigSettings@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigSettings::GetExtractedAppxPackagePath(void)
0x1800fc7f5  nop
0x1800fc7f6  mov     rdx, rax
0x1800fc7f9  mov     rcx, rsi
0x1800fc7fc  call    ?SetInstallLocation@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetInstallLocation(std::wstring const &)
0x1800fc801  nop
0x1800fc802  lea     rcx, [rbp+530h+var_528]
0x1800fc806  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fc80b  lea     rdx, [rbp+530h+var_528]
0x1800fc80f  mov     rcx, r15
0x1800fc812  call    ?GetExtractedAppxManifestPath@ConfigSettings@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigSettings::GetExtractedAppxManifestPath(void)
0x1800fc817  nop
0x1800fc818  lea     r14, [rsi+388h]
0x1800fc81f  mov     rdx, rax
0x1800fc822  mov     rcx, r14
0x1800fc825  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800fc82a  nop
0x1800fc82b  lea     rcx, [rbp+530h+var_528]
0x1800fc82f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fc834  lea     rdx, [rbp+530h+var_4C8]
0x1800fc838  mov     rcx, r15
0x1800fc83b  call    ?GetExtractedAppxManifestPath@ConfigSettings@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigSettings::GetExtractedAppxManifestPath(void)
0x1800fc840  nop
0x1800fc841  xor     r8d, r8d
0x1800fc844  mov     rdx, rax
0x1800fc847  lea     rcx, [rbp+530h+var_528]
0x1800fc84b  call    ?GetStoreAppType@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@E@Z; StoreApplication::GetStoreAppType(std::wstring const &,uchar)
0x1800fc850  nop
0x1800fc851  lea     rcx, [rsi+328h]
0x1800fc858  mov     rdx, rax
0x1800fc85b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800fc860  nop
0x1800fc861  lea     rcx, [rbp+530h+var_528]
0x1800fc865  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fc86a  nop
0x1800fc86b  lea     rcx, [rbp+530h+var_4C8]
0x1800fc86f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fc874  lea     rdx, [rbp+530h+var_528]
0x1800fc878  mov     rcx, r15
0x1800fc87b  call    ?GetExtractedAppxBundlePath@ConfigSettings@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ConfigSettings::GetExtractedAppxBundlePath(void)
0x1800fc880  nop
0x1800fc881  lea     rcx, [rsi+3A8h]
0x1800fc888  mov     rdx, rax
0x1800fc88b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800fc890  nop
0x1800fc891  lea     rcx, [rbp+530h+var_528]
0x1800fc895  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fc89a  jmp     loc_1800FCDFF
0x1800fc89f  mov     [rsp+630h+var_5D0], rdi
0x1800fc8a4  mov     [rsp+630h+string], rdi
0x1800fc8a9  xor     edx, edx
0x1800fc8ab  lea     rcx, [rsp+630h+string]
0x1800fc8b0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800fc8b5  lea     rcx, [rbp+530h+sourceString]
0x1800fc8bc  cmp     [rbp+530h+var_450], 7
0x1800fc8c4  cmova   rcx, [rbp+530h+sourceString]; sourceString
0x1800fc8cc  lea     r8, [rsp+630h+string]; string
0x1800fc8d1  mov     edx, [rbp+530h+length]; length
0x1800fc8d7  call    WindowsCreateString
0x1800fc8dc  mov     rcx, [rbp+538h]; this
0x1800fc8e3  test    eax, eax
0x1800fc8e5  js      loc_1800FD3BF
0x1800fc8eb  cmp     [r12], rdi
0x1800fc8ef  jnz     short loc_1800FC947
0x1800fc8f1  mov     rdi, [rsp+630h+var_5C8]
0x1800fc8f6  mov     rax, [rdi]
0x1800fc8f9  mov     rbx, [rax+88h]
0x1800fc900  lea     rcx, [rsp+630h+var_5D0]
0x1800fc905  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800fc90a  lea     r8, [rsp+630h+var_5D0]
0x1800fc90f  mov     rdx, [rsp+630h+string]
0x1800fc914  mov     rcx, rdi
0x1800fc917  mov     rax, rbx
0x1800fc91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc91f  mov     rcx, [rbp+538h]; this
0x1800fc926  xor     edi, edi
0x1800fc928  test    eax, eax
0x1800fc92a  js      loc_1800FD3D4
0x1800fc930  mov     rax, [rbp+538h]
0x1800fc937  mov     rcx, [rsp+630h+var_5D0]
0x1800fc93c  test    rcx, rcx
0x1800fc93f  jz      loc_1800FD311
0x1800fc945  jmp     short loc_1800FC94C
0x1800fc947  mov     rcx, [rsp+630h+var_5D0]
0x1800fc94c  cmp     [r12], rdi
0x1800fc950  cmovnz  rcx, [r12]
0x1800fc955  mov     [rsp+630h+var_5E8], rcx
0x1800fc95a  test    rcx, rcx
0x1800fc95d  jz      short loc_1800FC96C
0x1800fc95f  mov     rax, [rcx]
0x1800fc962  mov     rax, [rax+8]
0x1800fc966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc96b  nop
0x1800fc96c  lea     rdx, [rsp+630h+var_5E8]
0x1800fc971  lea     rcx, [rbp+530h+var_528]
0x1800fc975  call    ?GetStoreAppInstallLocationFromPackage@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@Z; StoreApplication::GetStoreAppInstallLocationFromPackage(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)
0x1800fc97a  nop
0x1800fc97b  mov     rdx, rax
0x1800fc97e  mov     rcx, rsi
0x1800fc981  call    ?SetInstallLocation@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetInstallLocation(std::wstring const &)
0x1800fc986  nop
0x1800fc987  lea     rcx, [rbp+530h+var_528]
0x1800fc98b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fc990  lea     rdx, [rsp+630h+var_5E8]
0x1800fc995  lea     rcx, [rbp+530h+var_528]
0x1800fc999  call    ?GetStoreAppInstallDateFromPackage@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@Z; StoreApplication::GetStoreAppInstallDateFromPackage(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)
0x1800fc99e  nop
0x1800fc99f  lea     rcx, [rsi+100h]
0x1800fc9a6  mov     rdx, rax
0x1800fc9a9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800fc9ae  nop
0x1800fc9af  lea     rcx, [rbp+530h+var_528]
0x1800fc9b3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fc9b8  lea     rcx, [rbp+530h+var_4C8]
0x1800fc9bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
  ... truncated ...
```
