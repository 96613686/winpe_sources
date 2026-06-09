# UWAInstallServiceWorkItem::UWAInstallServiceWorkItem(winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,int)

- ea: `0x1801c9c60`
- end: `0x1801cab7f`
- name: `??0UWAInstallServiceWorkItem@@QEAA@AEBUhstring@winrt@@00000_N11111111111H@Z`
- size: `3871`
- prototype: `UWAInstallServiceWorkItem *(UWAInstallServiceWorkItem *__hidden this, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *, bool, bool, bool, bool, bool, bool, bool, bool, bool, bool, bool, bool, int)`
- caller_count: `1`
- callee_count: `61`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801c8bdc`

## callees

- `0x180009ea0`
- `0x18000a850`
- `0x18000ad3c`
- `0x1800101f4`
- `0x18001ddb0`
- `0x180020868`
- `0x180022298`
- `0x1800222d8`
- `0x1800225e4`
- `0x18002ec2c`
- `0x1800322f8`
- `0x180036618`
- `0x180036bd8`
- `0x180036e6c`
- `0x180037200`
- `0x1800378d0`
- `0x18003ecf8`
- `0x180044fc4`
- `0x180045338`
- `0x1800453a0`
- `0x1800453bc`
- `0x180045588`
- `0x18004579c`
- `0x180069a84`
- `0x18006cc00`
- `0x180075fc0`
- `0x180095814`
- `0x18009588c`
- `0x180095b2c`
- `0x180095b68`
- `0x180099350`
- `0x1800a5498`
- `0x1800a74fc`
- `0x1800b063c`
- `0x1800b356c`
- `0x1800b7b08`
- `0x1800c18bc`
- `0x1800d326c`
- `0x1800e4c70`
- `0x180138ec8`
- `0x180154c34`
- `0x180158b54`
- `0x18016a3cc`
- `0x18016ff78`
- `0x18017b834`
- `0x1801b43dc`
- `0x1801b54bc`
- `0x1801c79ac`
- `0x1801c920c`
- `0x1801c92d8`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801ca33a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1801ca33a`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x1801ca2ef`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x1801ca2ef`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801ca321`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801ca321`
- `msvcp_win!_Xtime_get_ticks` at `0x1801ca41e`
- `msvcp_win!_Xtime_get_ticks` at `0x1801ca41e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ca3f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ca448`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ca3f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ca448`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ca42e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ca42e`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801ca2a7`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1801ca2a7`

## string_xrefs

- `0x1801c9e67`: `Install`
- `0x1801ca796`: `Install`
- `0x1801c9dee`: `onecoreuap\enduser\winstore\installservice\libqueue2\uwainstallworkbridge.cpp`
- `0x1801caa4b`: `onecoreuap\enduser\winstore\installservice\libqueue2\uwainstallworkbridge.cpp`
- `0x1801caa5f`: `onecoreuap\enduser\winstore\installservice\libqueue2\uwainstallworkbridge.cpp`
- `0x1801caa73`: `onecoreuap\enduser\winstore\installservice\libqueue2\uwainstallworkbridge.cpp`
- `0x1801caa87`: `onecoreuap\enduser\winstore\installservice\libqueue2\uwainstallworkbridge.cpp`
- `0x1801caa9c`: `onecoreuap\enduser\winstore\installservice\libqueue2\uwainstallworkbridge.cpp`
- `0x1801caadd`: `onecoreuap\enduser\winstore\installservice\libqueue2\uwainstallworkbridge.cpp`
- `0x1801ca7c2`: `InstallType`
- `0x1801c9dd9`: `UWAInstallServiceWorkItem::UWAInstallServiceWorkItem`
- `0x1801caac8`: `UWAInstallServiceWorkItem::UWAInstallServiceWorkItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
UWAInstallServiceWorkItem *__fastcall UWAInstallServiceWorkItem::UWAInstallServiceWorkItem(
        UWAInstallServiceWorkItem *this,
        const struct winrt::hstring *a2,
        const struct winrt::hstring *a3,
        const struct winrt::hstring *a4,
        const struct winrt::hstring *a5,
        const struct winrt::hstring *a6,
        const struct winrt::hstring *a7,
        bool a8,
        bool a9,
        bool a10,
        bool a11,
        bool a12,
        bool a13,
        bool a14,
        bool a15,
        bool a16,
        bool a17,
        bool a18,
        bool a19,
        int a20)
{
  __int64 v23; // r10
  winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes **v24; // r14
  __int64 v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rax
  char IsEnabled; // al
  winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes *v29; // rcx
  __int64 v30; // rcx
  int v31; // eax
  const unsigned __int16 *v32; // rax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, struct winrt::hstring **); // rbx
  int v37; // eax
  __int64 *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rdx
  winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes *v41; // rbx
  const struct winrt::hstring *NamedString; // rax
  __int64 *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdx
  winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes *v46; // rbx
  const struct winrt::hstring *v47; // rax
  unsigned int v48; // eax
  __int64 v49; // rax
  unsigned int v50; // eax
  size_t v51; // rax
  unsigned __int64 v52; // rcx
  HSTRING v53; // rdx
  struct WindowsUpdate::Internal::IFulfillmentDataInfo *v54; // rdi
  __int64 (__fastcall *v55)(struct WindowsUpdate::Internal::IFulfillmentDataInfo *, HSTRING *); // rbx
  int v56; // eax
  __int64 ticks; // rbx
  PCWSTR StringRawBuffer; // rax
  struct winrt::hstring *v59; // rbx
  int v60; // eax
  __int64 v61; // rax
  char *v62; // r15
  struct winrt::hstring *v63; // rbx
  int v64; // eax
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 StringValue; // rbx
  void (__fastcall ***v68)(_QWORD, __int64 *, struct winrt::hstring **); // rcx
  __int64 v69; // rdi
  winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes *v70; // rbx
  __int64 *v71; // rcx
  __int64 v72; // rax
  __int64 v73; // rdx
  _QWORD *v74; // rdx
  __int64 v75; // rcx
  UWAInstallServiceWorkItem *result; // rax
  unsigned int *v77; // rax
  __int64 v78; // r8
  wil::ResultException *v79; // rdi
  int v80; // r9d
  __int64 v81; // rbx
  __int64 v82; // rax
  int ErrorCode; // eax
  unsigned int *v84; // rax
  _BYTE v85[32]; // [rsp+0h] [rbp-388h] BYREF
  bool v86[8]; // [rsp+20h] [rbp-368h]
  char v87[8]; // [rsp+70h] [rbp-318h] BYREF
  HSTRING string; // [rsp+78h] [rbp-310h] BYREF
  PWSTR ppszPath; // [rsp+80h] [rbp-308h] BYREF
  __int64 v90; // [rsp+88h] [rbp-300h] BYREF
  int v91; // [rsp+90h] [rbp-2F8h] BYREF
  __int64 v92; // [rsp+98h] [rbp-2F0h] BYREF
  struct winrt::hstring *v93; // [rsp+A0h] [rbp-2E8h] BYREF
  const wchar_t *v94; // [rsp+A8h] [rbp-2E0h] BYREF
  __int128 v95; // [rsp+B0h] [rbp-2D8h]
  _BYTE v96[8]; // [rsp+C0h] [rbp-2C8h] BYREF
  _BYTE v97[8]; // [rsp+C8h] [rbp-2C0h] BYREF
  const struct winrt::hstring *v98; // [rsp+D0h] [rbp-2B8h] BYREF
  const struct winrt::hstring *v99; // [rsp+D8h] [rbp-2B0h] BYREF
  const struct winrt::hstring *v100; // [rsp+E0h] [rbp-2A8h] BYREF
  struct winrt::hstring *v101; // [rsp+E8h] [rbp-2A0h] BYREF
  __int64 v102; // [rsp+F0h] [rbp-298h] BYREF
  struct WindowsUpdate::Internal::IFulfillmentDataInfo *v103; // [rsp+F8h] [rbp-290h] BYREF
  WCHAR *v104; // [rsp+100h] [rbp-288h] BYREF
  __int64 v105; // [rsp+108h] [rbp-280h] BYREF
  _BYTE v106[16]; // [rsp+110h] [rbp-278h] BYREF
  _QWORD v107[2]; // [rsp+120h] [rbp-268h] BYREF
  const wil::ResultException *v108; // [rsp+130h] [rbp-258h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+138h] [rbp-250h] BYREF
  _BYTE v110[24]; // [rsp+150h] [rbp-238h] BYREF
  _BYTE v111[32]; // [rsp+168h] [rbp-220h] BYREF
  _QWORD v112[5]; // [rsp+188h] [rbp-200h] BYREF
  _BYTE v113[256]; // [rsp+1B0h] [rbp-1D8h] BYREF
  WCHAR szVolumeName[72]; // [rsp+2B0h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  v93 = a3;
  v98 = a2;
  v107[0] = this;
  v100 = a5;
  string = (HSTRING)a6;
  v99 = a7;
  winrt::implements<UWAInstallServiceWorkItem,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem2,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemWithSubTasks>::implements<UWAInstallServiceWorkItem,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem2,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemWithSubTasks>();
  try
  {
    *(_QWORD *)this = &winrt::impl::heap_implements<UWAInstallServiceWorkItem>::`vftable';
    *((_QWORD *)this + 5) = 2;
    *((_OWORD *)this + 4) = 0;
    *((_OWORD *)this + 5) = 0;
    *((_OWORD *)this + 6) = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
    *((_DWORD *)this + 28) = -1;
    *(_QWORD *)((char *)this + 116) = 0;
    *((_QWORD *)this + 17) = 0;
    *((_QWORD *)this + 18) = 0;
    *((_QWORD *)this + 19) = 0;
    *((_QWORD *)this + 20) = 0;
    CorrelationVector::ValidateAndCreate((char *)this + 168, v23);
    winrt::hstring::hstring((UWAInstallServiceWorkItem *)((char *)this + 320), a3);
    winrt::hstring::hstring((UWAInstallServiceWorkItem *)((char *)this + 328), a4);
    *((_QWORD *)this + 42) = 0;
    *((_QWORD *)this + 43) = 0;
    *((_QWORD *)this + 44) = 0;
    *((_QWORD *)this + 45) = 0;
    v24 = (winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes **)((char *)this + 368);
    *((_QWORD *)this + 46) = 0;
    *((_QWORD *)this + 47) = 0;
    *((_BYTE *)this + 384) = 0;
    *((_BYTE *)this + 392) = 0;
    *((_QWORD *)this + 50) = 0;
    *((_DWORD *)this + 102) = 0;
    v25 = std::make_pair<unsigned short const (&)[16],winrt::hstring const &>(&v105, 0, a4);
    v94 = L"Creating UWA Work";
    *(_QWORD *)&v95 = 17;
    std::string::string(v112, "UWAInstallServiceWorkItem::UWAInstallServiceWorkItem");
    std::string::string(v111, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\uwainstallworkbridge.cpp");
    Logging::TraceActivity_CorrelationVector___std::pair_unsigned_short_const___winrt::hstring___(
      (unsigned int)v113,
      (unsigned int)v111,
      312,
      (unsigned int)v112,
      *(_DWORD *)v86,
      (__int64)&v94,
      (__int64)this + 168,
      v25);
    std::string::~string(v111);
    std::string::~string(v112);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v106);
    winrt::hstring::hstring((winrt::hstring *)v97, L"Install");
    v91 = 0;
    if ( a9 )
    {
      winrt::hstring::operator=(v97, L"Disc");
      v91 = 5;
    }
    if ( a10 )
    {
      winrt::hstring::operator=(v97, L"Remediation");
      v91 = 3;
    }
    if ( a11 )
    {
      winrt::hstring::operator=(v97, L"Restore");
      v91 = 4;
    }
    v26 = winrt::make_self<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkProgressStatus,>(&ppszPath);
    winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes>::operator=(
      (char *)this + 360,
      v26);
    if ( ppszPath )
      winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkProgressStatus>::unconditional_release_ref(&ppszPath);
    v27 = winrt::make_self<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes,>(&ppszPath);
    winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes>::operator=(
      (char *)this + 368,
      v27);
    if ( ppszPath )
      winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkProgressStatus>::unconditional_release_ref(&ppszPath);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncWorkAttributeAccess>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SyncWorkAttributeAccess>::GetImpl'::`2'::impl);
    v29 = *v24;
    if ( IsEnabled )
      winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes::SetWorkType(
        v29,
        (const struct winrt::hstring *)v97);
    else
      winrt::hstring::operator=((char *)v29 + 136, v97);
    v103 = 0;
    v102 = 0;
    v101 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v102);
    v31 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IFulfillmentDataInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>(
            v30,
            &v102);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x159,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\uwainstallworkbridge.cpp",
        (const char *)(unsigned int)v31,
        *(int *)v86);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v103);
    v32 = winrt::hstring::c_str(a4);
    v33 = WindowsUpdate::Internal::FulfillmentDataInfo::Deserialize(v32, &v103);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\uwainstallworkbridge.cpp",
        (const char *)(unsigned int)v33,
        *(int *)v86);
    v34 = (*(__int64 (__fastcall **)(__int64, struct WindowsUpdate::Internal::IFulfillmentDataInfo *))(*(_QWORD *)v102 + 104LL))(
            v102,
            v103);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\uwainstallworkbridge.cpp",
        (const char *)(unsigned int)v34,
        *(int *)v86);
    v35 = v102;
    v36 = *(__int64 (__fastcall **)(__int64, struct winrt::hstring **))(*(_QWORD *)v102 + 64LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v101);
    v37 = v36(v35, &v101);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\uwainstallworkbridge.cpp",
        (const char *)(unsigned int)v37,
        *(int *)v86);
    v112[0] = *(_QWORD *)a4;
    winrt::Windows::Data::Json::JsonObject::Parse((const struct winrt::param::hstring *)v96);
    winrt::param::hstring::hstring((winrt::param::hstring *)v111, L"PackageFamilyName");
    if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                            v96,
                            v111) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncWorkAttributeAccess>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SyncWorkAttributeAccess>::GetImpl'::`2'::impl) )
      {
        v41 = *v24;
        winrt::param::hstring::hstring((winrt::param::hstring *)v111, L"PackageFamilyName");
        NamedString = (const struct winrt::hstring *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                                                       v96,
                                                       &v90,
                                                       v111);
        winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes::SetPackageFamilyName(
          v41,
          NamedString);
      }
      else
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v111, L"PackageFamilyName");
        v38 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                           v96,
                           &v90,
                           v111);
        v39 = (__int64)*v24 + 120;
        if ( (__int64 *)v39 != v38 )
        {
          v40 = *v38;
          *v38 = 0;
          winrt::handle_type<winrt::impl::hstring_traits>::attach(v39, v40);
        }
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v90);
    }
    winrt::param::hstring::hstring((winrt::param::hstring *)v111, L"MainPackageFamilyNameForDlc");
    if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                            v96,
                            v111) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncWorkAttributeAccess>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SyncWorkAttributeAccess>::GetImpl'::`2'::impl) )
      {
        v46 = *v24;
        winrt::param::hstring::hstring((winrt::param::hstring *)v111, L"MainPackageFamilyNameForDlc");
        v47 = (const struct winrt::hstring *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                                               v96,
                                               &v90,
                                               v111);
        winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes::SetParentPackageFamilyName(
          v46,
          v47);
      }
      else
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v111, L"MainPackageFamilyNameForDlc");
        v43 = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                           v96,
                           &v90,
                           v111);
        v44 = (__int64)*v24 + 128;
        if ( (__int64 *)v44 != v43 )
        {
          v45 = *v43;
          *v43 = 0;
          winrt::handle_type<winrt::impl::hstring_traits>::attach(v44, v45);
        }
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v90);
    }
    if ( a8 )
    {
      *((_DWORD *)this + 102) = 2;
    }
    else if ( a11 )
    {
      *((_DWORD *)this + 102) = 1;
    }
    winrt::hstring::hstring((winrt::hstring *)&v104, (const struct winrt::hstring *)string);
    if ( a19 )
    {
      ppszPath = 0;
      LODWORD(v94) = 0;
      v95 = 0;
      v48 = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath);
      winrt::check_hresult(&string, v48, &v94);
      LODWORD(v94) = 0;
      v95 = 0;
      v49 = -1;
      do
        ++v49;
      while ( ppszPath[v49] );
      v50 = PathCchStripToRoot(ppszPath, v49 + 1);
      winrt::check_hresult(&string, v50, &v94);
      if ( !GetVolumeNameForVolumeMountPointW(ppszPath, szVolumeName, 0x32u) )
      {
        std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
          &v94,
          L"Unexpected error. Failed to get system volume GUID.");
        std::string::string(v111, "UWAInstallServiceWorkItem::UWAInstallServiceWorkItem");
        std::string::string(v112, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\uwainstallworkbridge.cpp");
        Logging::Log<>((unsigned int)v112, 405, (unsigned int)v111, 2, (__int64)&v94);
        std::string::~string(v112);
        std::string::~string(v111);
        winrt::impl::slim_source_location::current(&v94);
        v77 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&string, 3);
        winrt::hresult_error::hresult_error(pExceptionObject, *v77, v78);
        throw (winrt::hresult_error *)pExceptionObject;
      }
      v51 = wcsnlen(szVolumeName, 0x32u);
      if ( v51 > 1 )
      {
        v52 = 2 * v51 - 2;
        if ( v52 >= 0x64 )
          _report_rangecheckfailure();
        *(WCHAR *)((char *)szVolumeName + v52) = 0;
        winrt::hstring::hstring((winrt::hstring *)&v90, szVolumeName);
        winrt::hstring::hstring((winrt::hstring *)&string, (const struct winrt::hstring *)&v90);
        v53 = string;
        string = 0;
        winrt::handle_type<winrt::impl::hstring_traits>::attach(&v104, v53);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&string);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v90);
      }
    }
    v87[0] = 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PreSearchForPackages>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PreSearchForPackages>::GetImpl'::`2'::impl) )
    {
      if ( GetPreSearchUpdatePackageEnabledFromOneSettings() )
      {
        string = 0;
        v54 = v103;
        v55 = *(__int64 (__fastcall **)(struct WindowsUpdate::Internal::IFulfillmentDataInfo *, HSTRING *))(*(_QWORD *)v103 + 168LL);
        WindowsDeleteString(0);
        string = 0;
        v56 = v55(v54, &string);
        if ( v56 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1A0,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\uwainstallworkbridge.cpp",
            (const char *)(unsigned int)v56,
            *(int *)v86);
        ticks = _Xtime_get_ticks();
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v87[0] = IsOnlinePreSearchForPackageAllowed(StringRawBuffer, ticks);
        WindowsDeleteString(string);
      }
      v98 = *(const struct winrt::hstring **)v98;
      v90 = 0;
      v99 = *(const struct winrt::hstring **)v99;
      ppszPath = v104;
      v100 = *(const struct winrt::hstring **)v100;
      v105 = 0;
      v59 = v93;
      LODWORD(string) = GetInstallFlags(a8, a12, a13, a14, a15, a16, a17, a18, v93);
      v93 = v101;
      v60 = CallerContext::Create(szVolumeName, *(_QWORD *)v59);
      v61 = make_com_ptr<UWAInstallWork,CallerContext,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::IFulfillmentDataInfo *> *,enum WindowsUpdate::Internal::InstallType &,unsigned long,std::nullptr_t,HSTRING__ *,HSTRING__ *,HSTRING__ *,std::nullptr_t,HSTRING__ *,bool &,int const &>(
              (unsigned int)&v94,
              v60,
              (unsigned int)&v93,
              (unsigned int)&v91,
              (__int64)&string,
              (__int64)&v105,
              (__int64)&v100,
              (__int64)&ppszPath,
              (__int64)&v99,
              (__int64)&v90,
              (__int64)&v98,
              (__int64)v87,
              (__int64)&a20);
      v62 = (char *)this + 160;
      wil::com_ptr_t<IUpdateCollection,wil::err_exception_policy>::operator=((char *)this + 160, v61);
      wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(&v94);
    }
    else
    {
      v94 = *(const wchar_t **)v98;
      v105 = 0;
      v99 = *(const struct winrt::hstring **)v99;
      v98 = (const struct winrt::hstring *)v104;
      v100 = *(const struct winrt::hstring **)v100;
      v90 = 0;
      v63 = v93;
      LODWORD(string) = GetInstallFlags(a8, a12, a13, a14, a15, a16, a17, a18, v93);
      v93 = v101;
      v64 = CallerContext::Create(szVolumeName, *(_QWORD *)v63);
      v65 = make_com_ptr<UWAInstallWork,CallerContext,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::IFulfillmentDataInfo *> *,enum WindowsUpdate::Internal::InstallType &,unsigned long,std::nullptr_t,HSTRING__ *,HSTRING__ *,HSTRING__ *,std::nullptr_t,HSTRING__ *,bool &,int const &>(
              (unsigned int)&ppszPath,
              v64,
              (unsigned int)&v93,
              (unsigned int)&v91,
              (__int64)&string,
              (__int64)&v90,
              (__int64)&v100,
              (__int64)&v98,
              (__int64)&v99,
              (__int64)&v105,
              (__int64)&v94,
              (__int64)v87,
              (__int64)&a20);
      v62 = (char *)this + 160;
      wil::com_ptr_t<IUpdateCollection,wil::err_exception_policy>::operator=((char *)this + 160, v65);
      wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(&ppszPath);
    }
    CallerContext::~CallerContext((CallerContext *)szVolumeName);
    v66 = winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)&v94);
    winrt::Windows::Foundation::IUnknown::operator=((char *)this + 400, v66);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v94);
    winrt::param::hstring::hstring((winrt::param::hstring *)v112, L"Install");
    StringValue = winrt::Windows::Data::Json::JsonValue::CreateStringValue((const struct winrt::param::hstring *)&v94);
    winrt::param::hstring::hstring((winrt::param::hstring *)v111, L"InstallType");
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      (char *)this + 400,
      v111,
      StringValue);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v94);
    v68 = *(void (__fastcall ****)(_QWORD, __int64 *, struct winrt::hstring **))winrt::Windows::Data::Json::JsonArray::JsonArray((winrt::Windows::Data::Json::JsonArray *)&v94);
    if ( v68 )
    {
      v93 = 0;
      (**v68)(v68, winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>, &v93);
      ppszPath = (PWSTR)v93;
    }
    else
    {
      ppszPath = 0;
    }
    winrt::param::hstring::hstring((winrt::param::hstring *)v112, L"FulfillmentData");
    winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::SetNamedValue(
      (char *)this + 400,
      v112,
      &ppszPath);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&ppszPath);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v94);
    winrt::make_self<UWAWorkSubTask,>(&v92);
    v69 = v92;
    v70 = *v24;
    if ( *(winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes **)(v92 + 40) != *v24 )
    {
      if ( *(_QWORD *)(v92 + 40) )
        winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkProgressStatus>::unconditional_release_ref(v92 + 40);
      *(_QWORD *)(v69 + 40) = v70;
      if ( v70 )
        winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::AddRef(v70);
    }
    wil::com_ptr_t<UWAInstallWork,wil::err_exception_policy>::operator=(v92 + 48, v62);
    *(_DWORD *)(v92 + 56) = 0;
    winrt::hstring::operator=(v92 + 24, L"PackageFamilyName");
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncWorkAttributeAccess>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SyncWorkAttributeAccess>::GetImpl'::`2'::impl) )
    {
      v71 = (__int64 *)winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes::PackageFamilyName(
                         *v24,
                         &v94);
      v72 = v92 + 32;
      if ( (__int64 *)(v92 + 32) != v71 )
      {
        v73 = *v71;
        *v71 = 0;
        winrt::handle_type<winrt::impl::hstring_traits>::attach(v72, v73);
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v94);
    }
    else
    {
      winrt::hstring::operator=(v92 + 32, (char *)*v24 + 120);
    }
    v74 = (_QWORD *)*((_QWORD *)this + 18);
    if ( v74 == *((_QWORD **)this + 19) )
    {
      std::vector<winrt::com_ptr<UWAWorkSubTask>>::_Emplace_reallocate<winrt::com_ptr<UWAWorkSubTask> const &>(
        (char *)this + 136,
        v74,
        &v92);
    }
    else
    {
      v75 = v92;
      *v74 = v92;
      if ( v75 )
        winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::AddRef(v75);
      *((_QWORD *)this + 18) += 8LL;
    }
    if ( v92 )
      winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkProgressStatus>::unconditional_release_ref(&v92);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v104);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v96);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v101);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v102);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v103);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v97);
    Logging::ActivityScope<CorrelationVector &,std::pair<unsigned short const *,winrt::hstring>>::~ActivityScope<CorrelationVector &,std::pair<unsigned short const *,winrt::hstring>>((Logging::Context *)v113);
    result = this;
  }
  catch ( const wil::ResultException *v108 )
  {
    v79 = v108;
    LODWORD(string) = wil::ResultException::GetErrorCode(v108);
    std::basic_string_view<unsigned short>::basic_string_view<unsigned short,std::char_traits<unsigned short>>(
      v107,
      L"Error creating work item");
    std::string::string(v111, "UWAInstallServiceWorkItem::UWAInstallServiceWorkItem");
    std::string::string(v112, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\uwainstallworkbridge.cpp");
    Logging::Log<long>((unsigned int)v85 + 392, 474, (unsigned int)v85 + 360, v80, (__int64)v107, (__int64)&string);
    std::string::~string(v112);
    std::string::~string(v111);
    v81 = winrt::impl::slim_source_location::current(&v105);
    v94 = (const wchar_t *)(*(__int64 (__fastcall **)(wil::ResultException *))(*(_QWORD *)v79 + 8LL))(v79);
    v82 = winrt::to_hstring<char const *,0>(v107, &v94);
    wistd::__compressed_pair<ProductDocument::AlternateId *,wistd::default_delete<ProductDocument::AlternateId>>::__compressed_pair<ProductDocument::AlternateId *,wistd::default_delete<ProductDocument::AlternateId>>(
      v112,
      v82);
    ErrorCode = wil::ResultException::GetErrorCode(v79);
    v84 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&string, ErrorCode);
    winrt::hresult_error::hresult_error(v110, *v84, v112, v81);
    throw (winrt::hresult_error *)v110;
  }
  return result;
}

```

## disassembly

```asm
0x1801c9c60  push    rbx
0x1801c9c62  push    rsi
0x1801c9c63  push    rdi
0x1801c9c64  push    r12
0x1801c9c66  push    r13
0x1801c9c68  push    r14
0x1801c9c6a  push    r15
0x1801c9c6c  sub     rsp, 350h
0x1801c9c73  mov     rax, cs:__security_cookie
0x1801c9c7a  xor     rax, rsp
0x1801c9c7d  mov     [rsp+388h+var_48], rax
0x1801c9c85  mov     r12, r9
0x1801c9c88  mov     rdi, r8
0x1801c9c8b  mov     [rsp+388h+var_2E8], r8
0x1801c9c93  mov     r10, rdx
0x1801c9c96  mov     [rsp+388h+var_2B8], rdx
0x1801c9c9e  mov     rsi, rcx
0x1801c9ca1  mov     [rsp+388h+var_268], rcx
0x1801c9ca9  mov     rax, [rsp+388h+arg_20]
0x1801c9cb1  mov     [rsp+388h+var_2A8], rax
0x1801c9cb9  mov     rax, [rsp+388h+arg_28]
0x1801c9cc1  mov     [rsp+388h+string], rax
0x1801c9cc6  mov     rax, [rsp+388h+arg_30]
0x1801c9cce  mov     [rsp+388h+var_2B0], rax
0x1801c9cd6  call    ??0?$implements@UUWAInstallServiceWorkItem@@UIInstallServiceWorkItem@Plugin@InstallService@Internal@Windows@winrt@@UIInstallServiceWorkItem2@34567@UIInstallServiceWorkItemWithSubTasks@34567@@winrt@@QEAA@XZ; winrt::implements<UWAInstallServiceWorkItem,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem2,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemWithSubTasks>::implements<UWAInstallServiceWorkItem,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItem2,winrt::Windows::Internal::InstallService::Plugin::IInstallServiceWorkItemWithSubTasks>(void)
0x1801c9cdb  nop
0x1801c9cdc  lea     rax, ??_7?$heap_implements@UUWAInstallServiceWorkItem@@@impl@winrt@@6B@; const winrt::impl::heap_implements<UWAInstallServiceWorkItem>::`vftable'
0x1801c9ce3  mov     [rsi], rax
0x1801c9ce6  mov     qword ptr [rsi+28h], 2
0x1801c9cee  xorps   xmm0, xmm0
0x1801c9cf1  movups  xmmword ptr [rsi+40h], xmm0
0x1801c9cf5  movups  xmmword ptr [rsi+50h], xmm0
0x1801c9cf9  movups  xmmword ptr [rsi+60h], xmm0
0x1801c9cfd  xor     r14d, r14d
0x1801c9d00  mov     [rsi+30h], r14
0x1801c9d04  mov     [rsi+38h], r14
0x1801c9d08  mov     dword ptr [rsi+70h], 0FFFFFFFFh
0x1801c9d0f  mov     [rsi+74h], r14
0x1801c9d13  lea     r13, [rsi+88h]
0x1801c9d1a  mov     [r13+0], r14
0x1801c9d1e  mov     [r13+8], r14
0x1801c9d22  mov     [r13+10h], r14
0x1801c9d26  mov     [rsi+0A0h], r14
0x1801c9d2d  lea     rbx, [rsi+0A8h]
0x1801c9d34  mov     rdx, r10
0x1801c9d37  mov     rcx, rbx
0x1801c9d3a  call    ?ValidateAndCreate@CorrelationVector@@SA?AV1@AEBUhstring@winrt@@@Z; CorrelationVector::ValidateAndCreate(winrt::hstring const &)
0x1801c9d3f  nop
0x1801c9d40  lea     rcx, [rsi+140h]; this
0x1801c9d47  mov     rdx, rdi; struct winrt::hstring *
0x1801c9d4a  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1801c9d4f  nop
0x1801c9d50  lea     rcx, [rsi+148h]; this
0x1801c9d57  mov     rdx, r12; struct winrt::hstring *
0x1801c9d5a  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1801c9d5f  nop
0x1801c9d60  mov     [rsi+150h], r14
0x1801c9d67  mov     [rsi+158h], r14
0x1801c9d6e  mov     [rsi+160h], r14
0x1801c9d75  lea     r15, [rsi+168h]
0x1801c9d7c  mov     [r15], r14
0x1801c9d7f  lea     r14, [rsi+170h]
0x1801c9d86  xor     edx, edx
0x1801c9d88  mov     [r14], rdx
0x1801c9d8b  mov     [rsi+178h], rdx
0x1801c9d92  mov     [rsi+180h], dl
0x1801c9d98  mov     [rsi+188h], dl
0x1801c9d9e  mov     [rsi+190h], rdx
0x1801c9da5  mov     [rsi+198h], edx
0x1801c9dab  mov     r8, r12
0x1801c9dae  lea     rcx, [rsp+388h+var_280]
0x1801c9db6  call    ??$make_pair@AEAY0BA@$$CBGAEBUhstring@winrt@@@std@@YA?AU?$pair@PEBGUhstring@winrt@@@0@AEAY0BA@$$CBGAEBUhstring@winrt@@@Z; std::make_pair<ushort const (&)[16],winrt::hstring const &>(ushort const (&)[16],winrt::hstring const &)
0x1801c9dbb  mov     rdi, rax
0x1801c9dbe  lea     rax, aCreatingUwaWor; "Creating UWA Work"
0x1801c9dc5  mov     [rsp+388h+var_2E0], rax
0x1801c9dcd  mov     qword ptr [rsp+388h+var_2D8], 11h
0x1801c9dd9  lea     rdx, aUwainstallserv_3; "UWAInstallServiceWorkItem::UWAInstallSe"...
0x1801c9de0  lea     rcx, [rsp+388h+var_200]
0x1801c9de8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801c9ded  nop
0x1801c9dee  lea     rdx, aOnecoreuapEndu_81; "onecoreuap\\enduser\\winstore\\installs"...
0x1801c9df5  lea     rcx, [rsp+388h+var_220]
0x1801c9dfd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801c9e02  nop
0x1801c9e03  mov     qword ptr [rsp+388h+var_350], rdi
0x1801c9e08  mov     qword ptr [rsp+388h+var_358], rbx
0x1801c9e0d  lea     rax, [rsp+388h+var_2E0]
0x1801c9e15  mov     qword ptr [rsp+388h+var_360], rax
0x1801c9e1a  lea     r9, [rsp+388h+var_200]
0x1801c9e22  mov     r8d, 138h
0x1801c9e28  lea     rdx, [rsp+388h+var_220]
0x1801c9e30  lea     rcx, [rsp+388h+var_1D8]
0x1801c9e38  call    Logging__TraceActivity_CorrelationVector___std__pair_unsigned_short_const___winrt__hstring___
0x1801c9e3d  nop
0x1801c9e3e  lea     rcx, [rsp+388h+var_220]
0x1801c9e46  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1801c9e4b  nop
0x1801c9e4c  lea     rcx, [rsp+388h+var_200]
0x1801c9e54  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1801c9e59  nop
0x1801c9e5a  lea     rcx, [rsp+388h+var_278]
0x1801c9e62  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801c9e67  lea     rdx, aInstall; "Install"
0x1801c9e6e  lea     rcx, [rsp+388h+var_2C0]; this
0x1801c9e76  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1801c9e7b  nop
0x1801c9e7c  xor     ebx, ebx
0x1801c9e7e  mov     [rsp+388h+var_2F8], ebx
0x1801c9e85  cmp     [rsp+388h+arg_40], bl
0x1801c9e8c  jz      short loc_1801C9EAD
0x1801c9e8e  lea     rdx, aDisc; "Disc"
0x1801c9e95  lea     rcx, [rsp+388h+var_2C0]
0x1801c9e9d  call    ??4hstring@winrt@@QEAAAEAU01@QEBG@Z; winrt::hstring::operator=(ushort const * const)
0x1801c9ea2  mov     [rsp+388h+var_2F8], 5
0x1801c9ead  cmp     [rsp+388h+arg_48], bl
0x1801c9eb4  jz      short loc_1801C9ED5
0x1801c9eb6  lea     rdx, aRemediation; "Remediation"
0x1801c9ebd  lea     rcx, [rsp+388h+var_2C0]
0x1801c9ec5  call    ??4hstring@winrt@@QEAAAEAU01@QEBG@Z; winrt::hstring::operator=(ushort const * const)
0x1801c9eca  mov     [rsp+388h+var_2F8], 3
0x1801c9ed5  cmp     [rsp+388h+arg_50], bl
0x1801c9edc  jz      short loc_1801C9EFD
0x1801c9ede  lea     rdx, aRestore; "Restore"
0x1801c9ee5  lea     rcx, [rsp+388h+var_2C0]
0x1801c9eed  call    ??4hstring@winrt@@QEAAAEAU01@QEBG@Z; winrt::hstring::operator=(ushort const * const)
0x1801c9ef2  mov     [rsp+388h+var_2F8], 4
0x1801c9efd  lea     rcx, [rsp+388h+ppszPath]
0x1801c9f05  call    ??$make_self@UInstallServiceWorkProgressStatus@implementation@Plugin@InstallService@Internal@Windows@winrt@@$$V@winrt@@YA?AU?$com_ptr@UInstallServiceWorkProgressStatus@implementation@Plugin@InstallService@Internal@Windows@winrt@@@0@XZ; winrt::make_self<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkProgressStatus,>(void)
0x1801c9f0a  mov     rdx, rax
0x1801c9f0d  mov     rcx, r15
0x1801c9f10  call    ??4?$com_ptr@UInstallServiceWorkAttributes@implementation@Plugin@InstallService@Internal@Windows@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes>::operator=(winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes> &&)
0x1801c9f15  cmp     [rsp+388h+ppszPath], rbx
0x1801c9f1d  jz      short loc_1801C9F2C
0x1801c9f1f  lea     rcx, [rsp+388h+ppszPath]
0x1801c9f27  call    ?unconditional_release_ref@?$com_ptr@UInstallServiceWorkProgressStatus@implementation@Plugin@InstallService@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkProgressStatus>::unconditional_release_ref(void)
0x1801c9f2c  lea     rcx, [rsp+388h+ppszPath]
0x1801c9f34  call    ??$make_self@UInstallServiceWorkAttributes@implementation@Plugin@InstallService@Internal@Windows@winrt@@$$V@winrt@@YA?AU?$com_ptr@UInstallServiceWorkAttributes@implementation@Plugin@InstallService@Internal@Windows@winrt@@@0@XZ; winrt::make_self<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes,>(void)
0x1801c9f39  mov     rdx, rax
0x1801c9f3c  mov     rcx, r14
0x1801c9f3f  call    ??4?$com_ptr@UInstallServiceWorkAttributes@implementation@Plugin@InstallService@Internal@Windows@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes>::operator=(winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes> &&)
0x1801c9f44  cmp     [rsp+388h+ppszPath], rbx
0x1801c9f4c  jz      short loc_1801C9F5B
0x1801c9f4e  lea     rcx, [rsp+388h+ppszPath]
0x1801c9f56  call    ?unconditional_release_ref@?$com_ptr@UInstallServiceWorkProgressStatus@implementation@Plugin@InstallService@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkProgressStatus>::unconditional_release_ref(void)
0x1801c9f5b  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SyncWorkAttributeAccess@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SyncWorkAttributeAccess@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncWorkAttributeAccess> `wil::Feature<__WilFeatureTraits_Feature_SyncWorkAttributeAccess>::GetImpl(void)'::`2'::impl
0x1801c9f62  mov     rcx, r15
0x1801c9f65  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SyncWorkAttributeAccess@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncWorkAttributeAccess>::__private_IsEnabled(void)
0x1801c9f6a  lea     rdx, [rsp+388h+var_2C0]; struct winrt::hstring *
0x1801c9f72  mov     rcx, [r14]; this
0x1801c9f75  test    al, al
0x1801c9f77  jz      short loc_1801C9F80
0x1801c9f79  call    ?SetWorkType@InstallServiceWorkAttributes@implementation@Plugin@InstallService@Internal@Windows@winrt@@QEAAXAEBUhstring@7@@Z; winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes::SetWorkType(winrt::hstring const &)
0x1801c9f7e  jmp     short loc_1801C9F8C
0x1801c9f80  add     rcx, 88h
0x1801c9f87  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x1801c9f8c  mov     [rsp+388h+var_290], rbx
0x1801c9f94  mov     [rsp+388h+var_298], rbx
0x1801c9f9c  mov     [rsp+388h+var_2A0], rbx
0x1801c9fa4  lea     rcx, [rsp+388h+var_298]
0x1801c9fac  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801c9fb1  lea     rdx, [rsp+388h+var_298]
0x1801c9fb9  call    ??$CreateExternalObjectVector@UIFulfillmentDataInfo@Internal@WindowsUpdate@@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@2Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IFulfillmentDataInfo,Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0> * *)
0x1801c9fbe  mov     rcx, [rsp+388h]; this
0x1801c9fc6  test    eax, eax
0x1801c9fc8  js      loc_1801CAA48
0x1801c9fce  lea     rcx, [rsp+388h+var_290]
0x1801c9fd6  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801c9fdb  mov     rcx, r12; this
0x1801c9fde  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1801c9fe3  lea     rdx, [rsp+388h+var_290]; struct WindowsUpdate::Internal::IFulfillmentDataInfo **
0x1801c9feb  mov     rcx, rax; unsigned __int16 *
0x1801c9fee  call    ?Deserialize@FulfillmentDataInfo@Internal@WindowsUpdate@@SAJPEBGPEAPEAUIFulfillmentDataInfo@23@@Z; WindowsUpdate::Internal::FulfillmentDataInfo::Deserialize(ushort const *,WindowsUpdate::Internal::IFulfillmentDataInfo * *)
0x1801c9ff3  mov     rcx, [rsp+388h]; this
0x1801c9ffb  test    eax, eax
0x1801c9ffd  js      loc_1801CAA5C
0x1801ca003  mov     rcx, [rsp+388h+var_298]
0x1801ca00b  mov     rax, [rcx]
0x1801ca00e  mov     rdx, [rsp+388h+var_290]
0x1801ca016  mov     rax, [rax+68h]
0x1801ca01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ca01f  mov     rcx, [rsp+388h]; this
0x1801ca027  test    eax, eax
0x1801ca029  js      loc_1801CAA70
0x1801ca02f  mov     rdi, [rsp+388h+var_298]
0x1801ca037  mov     rax, [rdi]
0x1801ca03a  mov     rbx, [rax+40h]
0x1801ca03e  lea     rcx, [rsp+388h+var_2A0]
0x1801ca046  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801ca04b  lea     rdx, [rsp+388h+var_2A0]
0x1801ca053  mov     rcx, rdi
0x1801ca056  mov     rax, rbx
0x1801ca059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ca05e  mov     rcx, [rsp+388h]; this
0x1801ca066  test    eax, eax
0x1801ca068  js      loc_1801CAA84
0x1801ca06e  mov     rax, [r12]
0x1801ca072  mov     [rsp+388h+var_200], rax
0x1801ca07a  lea     rdx, [rsp+388h+var_200]
0x1801ca082  lea     rcx, [rsp+388h+var_2C8]; struct winrt::param::hstring *
0x1801ca08a  call    ?Parse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonObject::Parse(winrt::param::hstring const &)
0x1801ca08f  nop
0x1801ca090  lea     rdi, aPackagefamilyn_3; "PackageFamilyName"
0x1801ca097  mov     rdx, rdi; unsigned __int16 *
0x1801ca09a  lea     rcx, [rsp+388h+var_220]; this
0x1801ca0a2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801ca0a7  lea     rdx, [rsp+388h+var_220]
0x1801ca0af  lea     rcx, [rsp+388h+var_2C8]
0x1801ca0b7  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x1801ca0bc  xor     r12d, r12d
0x1801ca0bf  test    al, al
0x1801ca0c1  jz      loc_1801CA15E
0x1801ca0c7  mov     rcx, r15
0x1801ca0ca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SyncWorkAttributeAccess@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncWorkAttributeAccess>::__private_IsEnabled(void)
0x1801ca0cf  mov     rdx, rdi; unsigned __int16 *
0x1801ca0d2  lea     rcx, [rsp+388h+var_220]; this
0x1801ca0da  test    al, al
0x1801ca0dc  jnz     short loc_1801CA11F
0x1801ca0de  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801ca0e3  lea     r8, [rsp+388h+var_220]
0x1801ca0eb  lea     rdx, [rsp+388h+var_300]
0x1801ca0f3  lea     rcx, [rsp+388h+var_2C8]
0x1801ca0fb  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x1801ca100  mov     rcx, rax
0x1801ca103  mov     rax, [r14]
0x1801ca106  add     rax, 78h ; 'x'
0x1801ca10a  cmp     rax, rcx
0x1801ca10d  jz      short loc_1801CA151
0x1801ca10f  mov     rdx, [rcx]
0x1801ca112  mov     [rcx], r12
0x1801ca115  mov     rcx, rax
0x1801ca118  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1801ca11d  jmp     short loc_1801CA151
0x1801ca11f  mov     rbx, [r14]
0x1801ca122  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801ca127  lea     r8, [rsp+388h+var_220]
0x1801ca12f  lea     rdx, [rsp+388h+var_300]
0x1801ca137  lea     rcx, [rsp+388h+var_2C8]
0x1801ca13f  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x1801ca144  nop
0x1801ca145  mov     rdx, rax; struct winrt::hstring *
0x1801ca148  mov     rcx, rbx; this
0x1801ca14b  call    ?SetPackageFamilyName@InstallServiceWorkAttributes@implementation@Plugin@InstallService@Internal@Windows@winrt@@QEAAXAEBUhstring@7@@Z; winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes::SetPackageFamilyName(winrt::hstring const &)
0x1801ca150  nop
0x1801ca151  lea     rcx, [rsp+388h+var_300]
0x1801ca159  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801ca15e  lea     rdi, aMainpackagefam; "MainPackageFamilyNameForDlc"
0x1801ca165  mov     rdx, rdi; unsigned __int16 *
0x1801ca168  lea     rcx, [rsp+388h+var_220]; this
0x1801ca170  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801ca175  lea     rdx, [rsp+388h+var_220]
0x1801ca17d  lea     rcx, [rsp+388h+var_2C8]
0x1801ca185  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x1801ca18a  test    al, al
0x1801ca18c  jz      loc_1801CA229
0x1801ca192  mov     rcx, r15
0x1801ca195  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SyncWorkAttributeAccess@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncWorkAttributeAccess>::__private_IsEnabled(void)
0x1801ca19a  mov     rdx, rdi; unsigned __int16 *
0x1801ca19d  lea     rcx, [rsp+388h+var_220]; this
0x1801ca1a5  test    al, al
0x1801ca1a7  jnz     short loc_1801CA1EA
0x1801ca1a9  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801ca1ae  lea     r8, [rsp+388h+var_220]
0x1801ca1b6  lea     rdx, [rsp+388h+var_300]
0x1801ca1be  lea     rcx, [rsp+388h+var_2C8]
0x1801ca1c6  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x1801ca1cb  mov     rcx, rax
0x1801ca1ce  mov     rax, [r14]
0x1801ca1d1  sub     rax, 0FFFFFFFFFFFFFF80h
0x1801ca1d5  cmp     rax, rcx
0x1801ca1d8  jz      short loc_1801CA21C
0x1801ca1da  mov     rdx, [rcx]
0x1801ca1dd  mov     [rcx], r12
0x1801ca1e0  mov     rcx, rax
0x1801ca1e3  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x1801ca1e8  jmp     short loc_1801CA21C
0x1801ca1ea  mov     rbx, [r14]
0x1801ca1ed  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801ca1f2  lea     r8, [rsp+388h+var_220]
0x1801ca1fa  lea     rdx, [rsp+388h+var_300]
0x1801ca202  lea     rcx, [rsp+388h+var_2C8]
0x1801ca20a  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x1801ca20f  nop
0x1801ca210  mov     rdx, rax; struct winrt::hstring *
0x1801ca213  mov     rcx, rbx; this
0x1801ca216  call    ?SetParentPackageFamilyName@InstallServiceWorkAttributes@implementation@Plugin@InstallService@Internal@Windows@winrt@@QEAAXAEBUhstring@7@@Z; winrt::Windows::Internal::InstallService::Plugin::implementation::InstallServiceWorkAttributes::SetParentPackageFamilyName(winrt::hstring const &)
0x1801ca21b  nop
0x1801ca21c  lea     rcx, [rsp+388h+var_300]
0x1801ca224  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801ca229  mov     r15b, [rsp+388h+arg_38]
0x1801ca231  test    r15b, r15b
0x1801ca234  jz      short loc_1801CA242
0x1801ca236  mov     dword ptr [rsi+198h], 2
0x1801ca240  jmp     short loc_1801CA256
0x1801ca242  cmp     [rsp+388h+arg_50], r12b
0x1801ca24a  jz      short loc_1801CA256
0x1801ca24c  mov     dword ptr [rsi+198h], 1
0x1801ca256  mov     rdx, [rsp+388h+string]; struct winrt::hstring *
0x1801ca25b  lea     rcx, [rsp+388h+var_288]; this
0x1801ca263  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1801ca268  nop
  ... truncated ...
```
