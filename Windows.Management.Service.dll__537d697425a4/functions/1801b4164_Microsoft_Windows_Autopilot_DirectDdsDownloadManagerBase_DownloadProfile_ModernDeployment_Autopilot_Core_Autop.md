# Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::DownloadProfile(ModernDeployment::Autopilot::Core::AutopilotProfileDownloadOption)

- ea: `0x1801b4164`
- end: `0x1801b4bdf`
- name: `?DownloadProfile@DirectDdsDownloadManagerBase@Autopilot@Windows@Microsoft@@AEAAJW4AutopilotProfileDownloadOption@Core@2ModernDeployment@@@Z`
- size: `2683`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801b4bf0`

## callees

- `0x18000b8f0`
- `0x180067398`
- `0x180067e54`
- `0x18006bbf0`
- `0x18006cb28`
- `0x18006cb94`
- `0x18006e4c0`
- `0x180077de0`
- `0x180080bac`
- `0x1800810f0`
- `0x180081294`
- `0x180081cac`
- `0x180084574`
- `0x1800845c8`
- `0x180084db8`
- `0x180086dd0`
- `0x180089850`
- `0x18008aecc`
- `0x18008bb18`
- `0x18008bf28`
- `0x18008e570`
- `0x18008fe3c`
- `0x1800901c0`
- `0x1800dc7a0`
- `0x1800dcbb8`
- `0x18014a31c`
- `0x18018206c`
- `0x180184d44`
- `0x18019ccb0`
- `0x18019f0e0`
- `0x18019f170`
- `0x1801af94c`
- `0x1801afe84`
- `0x1801b243c`
- `0x1801b2c5c`
- `0x1801b3f04`
- `0x1801b4164`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b49e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801b49e4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b4191`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b4816`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b4191`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801b4816`

## string_xrefs

- `0x1801b420b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`
- `0x1801b4276`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`
- `0x1801b45ad`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`
- `0x1801b4661`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`
- `0x1801b4865`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`
- `0x1801b4932`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`
- `0x1801b4a20`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::DownloadProfile(__int64 a1, int a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 AutopilotCorrelationVector; // rax
  __int64 v10; // rdx
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  __int64 ElapsedMicroseconds; // rsi
  const unsigned __int16 *v15; // rax
  __int64 v16; // rsi
  int v17; // eax
  int v18; // ecx
  __int64 v19; // rsi
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  unsigned int v23; // ebx
  __int64 v24; // rcx
  char v25; // bl
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 *v29; // rdx
  __int64 v30; // rax
  int StateSeparationAwareExpandedFilePath; // eax
  unsigned int v32; // ebx
  int v33; // eax
  unsigned int v34; // ebx
  WCHAR *StringRawBuffer; // rbx
  const WCHAR *v36; // rax
  DWORD v37; // r8d
  int v38; // eax
  unsigned int v39; // ebx
  __int64 v40; // rbx
  const unsigned __int16 *v41; // rax
  __int64 v42; // rax
  __int64 v43; // rcx
  int v44; // [rsp+20h] [rbp-3A8h]
  int v45; // [rsp+20h] [rbp-3A8h]
  __int64 v46; // [rsp+40h] [rbp-388h] BYREF
  __int64 v47[2]; // [rsp+48h] [rbp-380h] BYREF
  __int64 v48; // [rsp+58h] [rbp-370h] BYREF
  int v49; // [rsp+60h] [rbp-368h]
  HSTRING string; // [rsp+68h] [rbp-360h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp-358h] BYREF
  LARGE_INTEGER v52; // [rsp+78h] [rbp-350h] BYREF
  _BYTE v53[32]; // [rsp+80h] [rbp-348h] BYREF
  _BYTE v54[32]; // [rsp+A0h] [rbp-328h] BYREF
  _BYTE v55[32]; // [rsp+C0h] [rbp-308h] BYREF
  _BYTE v56[32]; // [rsp+E0h] [rbp-2E8h] BYREF
  _BYTE v57[32]; // [rsp+100h] [rbp-2C8h] BYREF
  _BYTE v58[96]; // [rsp+120h] [rbp-2A8h] BYREF
  _BYTE v59[128]; // [rsp+180h] [rbp-248h] BYREF
  _BYTE v60[32]; // [rsp+200h] [rbp-1C8h] BYREF
  _BYTE v61[32]; // [rsp+220h] [rbp-1A8h] BYREF
  _BYTE v62[336]; // [rsp+240h] [rbp-188h] BYREF
  __int64 v63; // [rsp+390h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+0h]

  QueryPerformanceCounter(&PerformanceCount);
  v49 = a2;
  v63 = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 104))(*(_QWORD *)(a1 + 104));
  ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::Start<unsigned short const *,unsigned long>((ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62);
  std::wstring::wstring(v53);
  v4 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 104) + 16LL))(*(_QWORD *)(a1 + 104), v53);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\directddsdownloadmanagerbase.cpp",
      (const char *)(unsigned int)v4,
      v44);
    std::wstring::_Tidy_deallocate(v53);
    ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry((ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62);
    return v5;
  }
  std::wstring::wstring(v54);
  v7 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 104) + 24LL))(*(_QWORD *)(a1 + 104), v54);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\directddsdownloadmanagerbase.cpp",
      (const char *)(unsigned int)v7,
      v44);
    std::wstring::_Tidy_deallocate(v54);
    std::wstring::_Tidy_deallocate(v53);
    ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry((ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62);
    return v8;
  }
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v59);
  AutopilotCorrelationVector = ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(v57);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
    v59,
    v55,
    AutopilotCorrelationVector);
  std::string::_Tidy_deallocate(v57);
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v47);
  LOBYTE(v10) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_AutopilotRestoration>::GetImpl'::`2'::impl,
    v10);
  std::wstring::wstring(v57);
  v11 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker((__int64)v57);
  v12 = v11;
  if ( v11 >= 0 )
  {
    std::wstring::wstring(v60, L"X-Autopilot-Marker");
    std::wstring::wstring(v61, v57);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<std::pair<std::wstring,std::wstring>>(
      v47,
      &v63,
      v60);
    std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v60);
  }
  else if ( v11 != -2147024895 )
  {
    std::wstring::_Tidy_deallocate(v57);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      v47,
      v47);
    std::wstring::_Tidy_deallocate(v55);
    std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v59);
    std::wstring::_Tidy_deallocate(v54);
    std::wstring::_Tidy_deallocate(v53);
    ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry((ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62);
    return v12;
  }
  std::wstring::_Tidy_deallocate(v57);
  Microsoft::Windows::Autopilot::DdsNetworkWrapper::DdsNetworkWrapper((Microsoft::Windows::Autopilot::DdsNetworkWrapper *)v58);
  v46 = 0;
  v13 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::RequestProfileJson(
          (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)v58,
          (__int64)v53,
          (__int64)v54,
          (__int64)v55,
          (__int64)v47,
          0,
          (__int64)&v46);
  ElapsedMicroseconds = Microsoft::Windows::Autopilot::AutoPilotPerformanceTimer::GetElapsedMicroseconds((Microsoft::Windows::Autopilot::AutoPilotPerformanceTimer *)&PerformanceCount);
  v15 = (const unsigned __int16 *)(***(__int64 (__fastcall ****)(_QWORD))(a1 + 104))(*(_QWORD *)(a1 + 104));
  ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::Stop(
    (ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62,
    v15,
    ElapsedMicroseconds,
    v13);
  if ( (v13 & 0x80000000) != 0 )
  {
    if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(v13) )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
        v17 = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 104))(*(_QWORD *)(a1 + 104));
        McTemplateU0dzz_EventWriteTransfer(v18, (unsigned int)AutopilotDownloadFailedExpected, v13, v17, v16);
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&v46);
      Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper((Microsoft::Windows::Autopilot::DdsNetworkWrapper *)v58);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v47,
        v47);
      std::wstring::_Tidy_deallocate(v55);
      std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v59);
      std::wstring::_Tidy_deallocate(v54);
      std::wstring::_Tidy_deallocate(v53);
      ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry((ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62);
      return v13;
    }
    else
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v58);
        v20 = (***(__int64 (__fastcall ****)(_QWORD, _QWORD))(a1 + 104))(*(_QWORD *)(a1 + 104), **(_QWORD **)(a1 + 104));
        McTemplateU0dzz_EventWriteTransfer(v21, (unsigned int)AutopilotDownloadFailedUnexpected, v13, v20, v19);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\directddsdownloadmanagerbase.cpp",
        (const char *)v13,
        v45);
      Windows::Internal::String::~String((Windows::Internal::String *)&v46);
      Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper((Microsoft::Windows::Autopilot::DdsNetworkWrapper *)v58);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v47,
        v47);
      std::wstring::_Tidy_deallocate(v55);
      std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v59);
      std::wstring::_Tidy_deallocate(v54);
      std::wstring::_Tidy_deallocate(v53);
      ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry((ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62);
      return v13;
    }
  }
  v48 = 0;
  v22 = Microsoft::Windows::Autopilot::JsonHelpers::FromString(&v46, &v48);
  v23 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\directddsdownloadmanagerbase.cpp",
      (const char *)(unsigned int)v22,
      v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    Windows::Internal::String::~String((Windows::Internal::String *)&v46);
    Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper((Microsoft::Windows::Autopilot::DdsNetworkWrapper *)v58);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      v47,
      v47);
    std::wstring::_Tidy_deallocate(v55);
    std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v59);
    std::wstring::_Tidy_deallocate(v54);
    std::wstring::_Tidy_deallocate(v53);
    ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry((ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62);
    return v23;
  }
  v25 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 104) + 32LL))(*(_QWORD *)(a1 + 104), v48);
  if ( v25 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      v27 = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 104))(*(_QWORD *)(a1 + 104));
      v29 = AutopilotDownloadNewProfileAvailable;
LABEL_24:
      McTemplateU0z_EventWriteTransfer(v28, v29, v27);
    }
  }
  else if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
  {
    v27 = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 104))(*(_QWORD *)(a1 + 104));
    v29 = AutopilotDownloadNewProfileEmpty;
    goto LABEL_24;
  }
  if ( (a2 & 8) == 0 || v25 )
  {
    QueryPerformanceCounter(&v52);
    std::wstring::wstring(v56);
    v30 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 104) + 8LL))(*(_QWORD *)(a1 + 104));
    StateSeparationAwareExpandedFilePath = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::GetStateSeparationAwareExpandedFilePath(
                                             v30,
                                             v56);
    v32 = StateSeparationAwareExpandedFilePath;
    if ( StateSeparationAwareExpandedFilePath >= 0 )
    {
      string = 0;
      v33 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v48, &string);
      v34 = v33;
      if ( v33 >= 0 )
      {
        StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
        v36 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56);
        v38 = Microsoft::Windows::Autopilot::AutoPilotStringFile::WriteToFileWithEncoding(v36, StringRawBuffer, v37);
        v39 = v38;
        if ( v38 >= 0 )
        {
          v40 = Microsoft::Windows::Autopilot::AutoPilotPerformanceTimer::GetElapsedMicroseconds((Microsoft::Windows::Autopilot::AutoPilotPerformanceTimer *)&v52);
          v41 = (const unsigned __int16 *)(***(__int64 (__fastcall ****)(_QWORD, _QWORD))(a1 + 104))(
                                            *(_QWORD *)(a1 + 104),
                                            **(_QWORD **)(a1 + 104));
          ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::LogProfileJsonConversion(
            (ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62,
            v41,
            v40);
          if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
          {
            v42 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56);
            McTemplateU0z_EventWriteTransfer(v43, AutopilotDownloadNewProfileSaved, v42);
          }
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          std::wstring::_Tidy_deallocate(v56);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
          Windows::Internal::String::~String((Windows::Internal::String *)&v46);
          Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper((Microsoft::Windows::Autopilot::DdsNetworkWrapper *)v58);
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
            v47,
            v47);
          std::wstring::_Tidy_deallocate(v55);
          std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v59);
          std::wstring::_Tidy_deallocate(v54);
          std::wstring::_Tidy_deallocate(v53);
          ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry((ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xEF,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\directddsdownloadmanagerbase.cpp",
            (const char *)(unsigned int)v38,
            v45);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
          std::wstring::_Tidy_deallocate(v56);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
          Windows::Internal::String::~String((Windows::Internal::String *)&v46);
          Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper((Microsoft::Windows::Autopilot::DdsNetworkWrapper *)v58);
          std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
            v47,
            v47);
          std::wstring::_Tidy_deallocate(v55);
          std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v59);
          std::wstring::_Tidy_deallocate(v54);
          std::wstring::_Tidy_deallocate(v53);
          ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry((ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62);
          return v39;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEE,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\directddsdownloadmanagerbase.cpp",
          (const char *)(unsigned int)v33,
          v45);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        std::wstring::_Tidy_deallocate(v56);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        Windows::Internal::String::~String((Windows::Internal::String *)&v46);
        Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper((Microsoft::Windows::Autopilot::DdsNetworkWrapper *)v58);
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
          v47,
          v47);
        std::wstring::_Tidy_deallocate(v55);
        std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v59);
        std::wstring::_Tidy_deallocate(v54);
        std::wstring::_Tidy_deallocate(v53);
        ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry((ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62);
        return v34;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\directddsdownloadmanagerbase.cpp",
        (const char *)(unsigned int)StateSeparationAwareExpandedFilePath,
        v45);
      std::wstring::_Tidy_deallocate(v56);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      Windows::Internal::String::~String((Windows::Internal::String *)&v46);
      Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper((Microsoft::Windows::Autopilot::DdsNetworkWrapper *)v58);
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v47,
        v47);
      std::wstring::_Tidy_deallocate(v55);
      std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v59);
      std::wstring::_Tidy_deallocate(v54);
      std::wstring::_Tidy_deallocate(v53);
      ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry((ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62);
      return v32;
    }
  }
  else
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v24, AutopilotDownloadEmptyProfileNotPersisted, v26, 1);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    Windows::Internal::String::~String((Windows::Internal::String *)&v46);
    Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper((Microsoft::Windows::Autopilot::DdsNetworkWrapper *)v58);
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
      v47,
      v47);
    std::wstring::_Tidy_deallocate(v55);
    std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v59);
    std::wstring::_Tidy_deallocate(v54);
    std::wstring::_Tidy_deallocate(v53);
    ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry((ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry *)v62);
    return 0;
  }
}

```

## disassembly

```asm
0x1801b4164  mov     [rsp+arg_10], rbx
0x1801b4169  push    rsi
0x1801b416a  push    rdi
0x1801b416b  push    r14
0x1801b416d  sub     rsp, 3B0h
0x1801b4174  mov     rax, cs:__security_cookie
0x1801b417b  xor     rax, rsp
0x1801b417e  mov     [rsp+3C8h+var_28], rax
0x1801b4186  mov     r14d, edx
0x1801b4189  mov     rdi, rcx
0x1801b418c  lea     rcx, [rsp+3C8h+PerformanceCount]; lpPerformanceCount
0x1801b4191  call    cs:__imp_QueryPerformanceCounter
0x1801b4198  nop     dword ptr [rax+rax+00h]
0x1801b419d  mov     [rsp+3C8h+var_368], r14d
0x1801b41a2  mov     rcx, [rdi+68h]
0x1801b41a6  mov     rax, [rcx]
0x1801b41a9  mov     rax, [rax]
0x1801b41ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b41b1  mov     [rsp+3C8h+var_38], rax
0x1801b41b9  lea     r8, [rsp+3C8h+var_368]
0x1801b41be  lea     rdx, [rsp+3C8h+var_38]
0x1801b41c6  lea     rcx, [rsp+3C8h+var_188]
0x1801b41ce  call    ??$Start@PEBGK@AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@SA?AV01@$$QEAPEBG$$QEAK@Z; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::Start<ushort const *,ulong>(ushort const * &&,ulong &&)
0x1801b41d3  nop
0x1801b41d4  lea     rcx, [rsp+3C8h+var_348]
0x1801b41dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801b41e1  nop
0x1801b41e2  mov     rcx, [rdi+68h]
0x1801b41e6  mov     rax, [rcx]
0x1801b41e9  lea     rdx, [rsp+3C8h+var_348]
0x1801b41f1  mov     rax, [rax+10h]
0x1801b41f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b41fa  mov     ebx, eax
0x1801b41fc  test    eax, eax
0x1801b41fe  jns     short loc_1801B423F
0x1801b4200  mov     rcx, [rsp+3C8h]; this
0x1801b4208  mov     r9d, eax; char *
0x1801b420b  lea     r8, aOnecoreuapAdmi_162; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b4212  mov     edx, 9Eh; void *
0x1801b4217  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b421c  nop
0x1801b421d  lea     rcx, [rsp+3C8h+var_348]
0x1801b4225  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b422a  nop
0x1801b422b  lea     rcx, [rsp+3C8h+var_188]; this
0x1801b4233  call    ??1AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry(void)
0x1801b4238  mov     eax, ebx
0x1801b423a  jmp     loc_1801B4BBA
0x1801b423f  lea     rcx, [rsp+3C8h+var_328]
0x1801b4247  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801b424c  nop
0x1801b424d  mov     rcx, [rdi+68h]
0x1801b4251  mov     rax, [rcx]
0x1801b4254  lea     rdx, [rsp+3C8h+var_328]
0x1801b425c  mov     rax, [rax+18h]
0x1801b4260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b4265  mov     ebx, eax
0x1801b4267  test    eax, eax
0x1801b4269  jns     short loc_1801B42B8
0x1801b426b  mov     rcx, [rsp+3C8h]; this
0x1801b4273  mov     r9d, eax; char *
0x1801b4276  lea     r8, aOnecoreuapAdmi_162; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b427d  mov     edx, 0A1h; void *
0x1801b4282  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b4287  nop
0x1801b4288  lea     rcx, [rsp+3C8h+var_328]
0x1801b4290  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b4295  nop
0x1801b4296  lea     rcx, [rsp+3C8h+var_348]
0x1801b429e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b42a3  nop
0x1801b42a4  lea     rcx, [rsp+3C8h+var_188]; this
0x1801b42ac  call    ??1AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry(void)
0x1801b42b1  mov     eax, ebx
0x1801b42b3  jmp     loc_1801B4BBA
0x1801b42b8  lea     rcx, [rsp+3C8h+var_248]
0x1801b42c0  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1801b42c5  nop
0x1801b42c6  lea     rcx, [rsp+3C8h+var_2C8]
0x1801b42ce  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x1801b42d3  nop
0x1801b42d4  mov     r8, rax
0x1801b42d7  lea     rdx, [rsp+3C8h+var_308]
0x1801b42df  lea     rcx, [rsp+3C8h+var_248]
0x1801b42e7  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(std::string const &)
0x1801b42ec  nop
0x1801b42ed  lea     rcx, [rsp+3C8h+var_2C8]
0x1801b42f5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801b42fa  lea     rcx, [rsp+3C8h+var_380]
0x1801b42ff  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x1801b4304  nop
0x1801b4305  mov     dl, 1
0x1801b4307  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotRestoration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotRestoration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration> `wil::Feature<__WilFeatureTraits_Feature_AutopilotRestoration>::GetImpl(void)'::`2'::impl
0x1801b430e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotRestoration@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801b4313  lea     rcx, [rsp+3C8h+var_2C8]
0x1801b431b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801b4320  nop
0x1801b4321  lea     rcx, [rsp+3C8h+var_2C8]
0x1801b4329  call    ?GetOrSetAutopilotMarker@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(std::wstring &)
0x1801b432e  mov     ebx, eax
0x1801b4330  test    eax, eax
0x1801b4332  jns     short loc_1801B43A9
0x1801b4334  cmp     eax, 80070001h
0x1801b4339  jz      loc_1801B43FD
0x1801b433f  lea     rcx, [rsp+3C8h+var_2C8]
0x1801b4347  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b434c  nop
0x1801b434d  lea     rdx, [rsp+3C8h+var_380]
0x1801b4352  lea     rcx, [rsp+3C8h+var_380]
0x1801b4357  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1801b435c  nop
0x1801b435d  lea     rcx, [rsp+3C8h+var_308]
0x1801b4365  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b436a  nop
0x1801b436b  lea     rcx, [rsp+3C8h+var_248]
0x1801b4373  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1801b4378  nop
0x1801b4379  lea     rcx, [rsp+3C8h+var_328]
0x1801b4381  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b4386  nop
0x1801b4387  lea     rcx, [rsp+3C8h+var_348]
0x1801b438f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b4394  nop
0x1801b4395  lea     rcx, [rsp+3C8h+var_188]; this
0x1801b439d  call    ??1AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry(void)
0x1801b43a2  mov     eax, ebx
0x1801b43a4  jmp     loc_1801B4BBA
0x1801b43a9  mov     rdx, cs:off_18021C8E8; "X-Autopilot-Marker"
0x1801b43b0  lea     rcx, [rsp+3C8h+var_1C8]
0x1801b43b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801b43bd  nop
0x1801b43be  lea     rdx, [rsp+3C8h+var_2C8]
0x1801b43c6  lea     rcx, [rsp+3C8h+var_1A8]
0x1801b43ce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801b43d3  nop
0x1801b43d4  lea     r8, [rsp+3C8h+var_1C8]
0x1801b43dc  lea     rdx, [rsp+3C8h+var_38]
0x1801b43e4  lea     rcx, [rsp+3C8h+var_380]
0x1801b43e9  call    ??$_Emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<std::pair<std::wstring,std::wstring>>(std::pair<std::wstring,std::wstring> &&)
0x1801b43ee  nop
0x1801b43ef  lea     rcx, [rsp+3C8h+var_1C8]; void *
0x1801b43f7  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1801b43fc  nop
0x1801b43fd  lea     rcx, [rsp+3C8h+var_2C8]
0x1801b4405  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b440a  lea     rcx, [rsp+3C8h+var_2A8]; this
0x1801b4412  call    ??0DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::DdsNetworkWrapper(void)
0x1801b4417  nop
0x1801b4418  mov     [rsp+3C8h+var_388], 0
0x1801b4421  lea     rax, [rsp+3C8h+var_388]
0x1801b4426  mov     [rsp+3C8h+var_398], rax; __int64
0x1801b442b  mov     qword ptr [rsp+3C8h+var_3A0], 0; int
0x1801b4434  lea     rax, [rsp+3C8h+var_380]
0x1801b4439  mov     [rsp+3C8h+var_3A8], rax; int
0x1801b443e  lea     r9, [rsp+3C8h+var_308]
0x1801b4446  lea     r8, [rsp+3C8h+var_328]
0x1801b444e  lea     rdx, [rsp+3C8h+var_348]
0x1801b4456  lea     rcx, [rsp+3C8h+var_2A8]; this
0x1801b445e  call    ?RequestProfileJson@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@QEBUTimeoutOverride@1234@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::RequestProfileJson(std::wstring const &,std::wstring const &,std::wstring const &,std::map<std::wstring,std::wstring> const *,Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride const * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x1801b4463  mov     ebx, eax
0x1801b4465  lea     rcx, [rsp+3C8h+PerformanceCount]; this
0x1801b446a  call    ?GetElapsedMicroseconds@AutoPilotPerformanceTimer@Autopilot@Windows@Microsoft@@QEAA_KXZ; Microsoft::Windows::Autopilot::AutoPilotPerformanceTimer::GetElapsedMicroseconds(void)
0x1801b446f  mov     rsi, rax
0x1801b4472  mov     rcx, [rdi+68h]
0x1801b4476  mov     rdx, [rcx]
0x1801b4479  mov     rax, [rdx]
0x1801b447c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b4481  mov     r9d, ebx; unsigned int
0x1801b4484  mov     r8, rsi; __int64
0x1801b4487  mov     rdx, rax; unsigned __int16 *
0x1801b448a  lea     rcx, [rsp+3C8h+var_188]; this
0x1801b4492  call    ?Stop@AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@QEAAXPEBG_JK@Z; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::Stop(ushort const *,__int64,ulong)
0x1801b4497  test    ebx, ebx
0x1801b4499  jns     loc_1801B4634
0x1801b449f  mov     ecx, ebx; int
0x1801b44a1  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x1801b44a6  test    al, al
0x1801b44a8  jz      loc_1801B4563
0x1801b44ae  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 1
0x1801b44b5  jz      short loc_1801B44EE
0x1801b44b7  lea     rcx, [rsp+3C8h+var_2A8]
0x1801b44bf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801b44c4  mov     rsi, rax
0x1801b44c7  mov     rcx, [rdi+68h]
0x1801b44cb  mov     rdx, [rcx]
0x1801b44ce  mov     rax, [rdx]
0x1801b44d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b44d6  mov     [rsp+3C8h+var_3A8], rsi
0x1801b44db  mov     r9, rax
0x1801b44de  mov     r8d, ebx
0x1801b44e1  lea     rdx, AutopilotDownloadFailedExpected
0x1801b44e8  call    McTemplateU0dzz_EventWriteTransfer
0x1801b44ed  nop
0x1801b44ee  lea     rcx, [rsp+3C8h+var_388]; this
0x1801b44f3  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801b44f8  nop
0x1801b44f9  lea     rcx, [rsp+3C8h+var_2A8]; this
0x1801b4501  call    ??1DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper(void)
0x1801b4506  nop
0x1801b4507  lea     rdx, [rsp+3C8h+var_380]
0x1801b450c  lea     rcx, [rsp+3C8h+var_380]
0x1801b4511  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1801b4516  nop
0x1801b4517  lea     rcx, [rsp+3C8h+var_308]
0x1801b451f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b4524  nop
0x1801b4525  lea     rcx, [rsp+3C8h+var_248]
0x1801b452d  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1801b4532  nop
0x1801b4533  lea     rcx, [rsp+3C8h+var_328]
0x1801b453b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b4540  nop
0x1801b4541  lea     rcx, [rsp+3C8h+var_348]
0x1801b4549  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b454e  nop
0x1801b454f  lea     rcx, [rsp+3C8h+var_188]; this
0x1801b4557  call    ??1AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry(void)
0x1801b455c  mov     eax, ebx
0x1801b455e  jmp     loc_1801B4BBA
0x1801b4563  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x1801b456a  jz      short loc_1801B45A2
0x1801b456c  lea     rcx, [rsp+3C8h+var_2A8]
0x1801b4574  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801b4579  mov     rsi, rax
0x1801b457c  mov     rcx, [rdi+68h]
0x1801b4580  mov     rdx, [rcx]
0x1801b4583  mov     rax, [rdx]
0x1801b4586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b458b  mov     [rsp+3C8h+var_3A8], rsi; int
0x1801b4590  mov     r9, rax
0x1801b4593  mov     r8d, ebx
0x1801b4596  lea     rdx, AutopilotDownloadFailedUnexpected
0x1801b459d  call    McTemplateU0dzz_EventWriteTransfer
0x1801b45a2  mov     rcx, [rsp+3C8h]; this
0x1801b45aa  mov     r9d, ebx; char *
0x1801b45ad  lea     r8, aOnecoreuapAdmi_162; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b45b4  mov     edx, 0CBh; void *
0x1801b45b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b45be  nop
0x1801b45bf  lea     rcx, [rsp+3C8h+var_388]; this
0x1801b45c4  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801b45c9  nop
0x1801b45ca  lea     rcx, [rsp+3C8h+var_2A8]; this
0x1801b45d2  call    ??1DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper(void)
0x1801b45d7  nop
0x1801b45d8  lea     rdx, [rsp+3C8h+var_380]
0x1801b45dd  lea     rcx, [rsp+3C8h+var_380]
0x1801b45e2  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1801b45e7  nop
0x1801b45e8  lea     rcx, [rsp+3C8h+var_308]
0x1801b45f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b45f5  nop
0x1801b45f6  lea     rcx, [rsp+3C8h+var_248]
0x1801b45fe  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1801b4603  nop
0x1801b4604  lea     rcx, [rsp+3C8h+var_328]
0x1801b460c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b4611  nop
0x1801b4612  lea     rcx, [rsp+3C8h+var_348]
0x1801b461a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b461f  nop
0x1801b4620  lea     rcx, [rsp+3C8h+var_188]; this
0x1801b4628  call    ??1AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry(void)
0x1801b462d  mov     eax, ebx
0x1801b462f  jmp     loc_1801B4BBA
0x1801b4634  mov     [rsp+3C8h+var_370], 0
0x1801b463d  lea     rdx, [rsp+3C8h+var_370]
0x1801b4642  lea     rcx, [rsp+3C8h+var_388]
0x1801b4647  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1801b464c  mov     ebx, eax
0x1801b464e  test    eax, eax
0x1801b4650  jns     loc_1801B46F3
0x1801b4656  mov     rcx, [rsp+3C8h]; this
0x1801b465e  mov     r9d, eax; char *
0x1801b4661  lea     r8, aOnecoreuapAdmi_162; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801b4668  mov     edx, 0D1h; void *
0x1801b466d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b4672  nop
0x1801b4673  lea     rcx, [rsp+3C8h+var_370]
0x1801b4678  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801b467d  nop
0x1801b467e  lea     rcx, [rsp+3C8h+var_388]; this
0x1801b4683  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801b4688  nop
0x1801b4689  lea     rcx, [rsp+3C8h+var_2A8]; this
0x1801b4691  call    ??1DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper(void)
0x1801b4696  nop
0x1801b4697  lea     rdx, [rsp+3C8h+var_380]
0x1801b469c  lea     rcx, [rsp+3C8h+var_380]
0x1801b46a1  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1801b46a6  nop
0x1801b46a7  lea     rcx, [rsp+3C8h+var_308]
0x1801b46af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b46b4  nop
0x1801b46b5  lea     rcx, [rsp+3C8h+var_248]
0x1801b46bd  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1801b46c2  nop
0x1801b46c3  lea     rcx, [rsp+3C8h+var_328]
0x1801b46cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801b46d0  nop
  ... truncated ...
```
