# Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::DownloadProfile(ModernDeployment::Autopilot::Core::AutopilotProfileDownloadOption)

- ea: `0x1801ae8e0`
- end: `0x1801af349`
- name: `?DownloadProfile@DirectDdsDownloadManagerBase@Autopilot@Windows@Microsoft@@AEAAJW4AutopilotProfileDownloadOption@Core@2ModernDeployment@@@Z`
- size: `2665`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801af350`

## callees

- `0x18000b820`
- `0x180067008`
- `0x180067a54`
- `0x18006b708`
- `0x18006c628`
- `0x18006c694`
- `0x18006df70`
- `0x18007755c`
- `0x18008019c`
- `0x1800806b0`
- `0x18008084c`
- `0x18008122c`
- `0x1800839bc`
- `0x180083a0c`
- `0x180084238`
- `0x1800860c4`
- `0x1800889a0`
- `0x18008a014`
- `0x18008ac1c`
- `0x18008afec`
- `0x18008d484`
- `0x18008ecf8`
- `0x18008f068`
- `0x1800da000`
- `0x1800da400`
- `0x180146418`
- `0x18017d75c`
- `0x18018027c`
- `0x180197ac0`
- `0x180199d50`
- `0x180199ddc`
- `0x1801a9ef4`
- `0x1801aa48c`
- `0x1801acc7c`
- `0x1801ad474`
- `0x1801ae690`
- `0x1801ae8e0`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801af154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801af154`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801ae90d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801aef8c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801ae90d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801aef8c`

## string_xrefs

- `0x1801ae981`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`
- `0x1801ae9ec`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`
- `0x1801aed23`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`
- `0x1801aedd7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`
- `0x1801aefd5`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`
- `0x1801af0a2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`
- `0x1801af18a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\directddsdownloadmanagerbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  _QWORD v63[2]; // [rsp+390h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+0h]

  QueryPerformanceCounter(&PerformanceCount);
  v49 = a2;
  v63[0] = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 104))(*(_QWORD *)(a1 + 104));
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
  v11 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(v57);
  v12 = v11;
  if ( v11 >= 0 )
  {
    std::wstring::wstring(v60, L"X-Autopilot-Marker");
    std::wstring::wstring(v61, v57);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<std::pair<std::wstring,std::wstring>>(
      v47,
      v63,
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
      McGenEventWrite_EventWriteTransfer(v24, AutopilotDownloadEmptyProfileNotPersisted, v26, 1, v63);
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
0x1801ae8e0  mov     [rsp+arg_10], rbx
0x1801ae8e5  push    rsi
0x1801ae8e6  push    rdi
0x1801ae8e7  push    r14
0x1801ae8e9  sub     rsp, 3B0h
0x1801ae8f0  mov     rax, cs:__security_cookie
0x1801ae8f7  xor     rax, rsp
0x1801ae8fa  mov     [rsp+3C8h+var_28], rax
0x1801ae902  mov     r14d, edx
0x1801ae905  mov     rdi, rcx
0x1801ae908  lea     rcx, [rsp+3C8h+PerformanceCount]; lpPerformanceCount
0x1801ae90d  call    cs:__imp_QueryPerformanceCounter
0x1801ae913  mov     [rsp+3C8h+var_368], r14d
0x1801ae918  mov     rcx, [rdi+68h]
0x1801ae91c  mov     rax, [rcx]
0x1801ae91f  mov     rax, [rax]
0x1801ae922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ae927  mov     [rsp+3C8h+var_38], rax
0x1801ae92f  lea     r8, [rsp+3C8h+var_368]
0x1801ae934  lea     rdx, [rsp+3C8h+var_38]
0x1801ae93c  lea     rcx, [rsp+3C8h+var_188]
0x1801ae944  call    ??$Start@PEBGK@AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@SA?AV01@$$QEAPEBG$$QEAK@Z; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::Start<ushort const *,ulong>(ushort const * &&,ulong &&)
0x1801ae949  nop
0x1801ae94a  lea     rcx, [rsp+3C8h+var_348]
0x1801ae952  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801ae957  nop
0x1801ae958  mov     rcx, [rdi+68h]
0x1801ae95c  mov     rax, [rcx]
0x1801ae95f  lea     rdx, [rsp+3C8h+var_348]
0x1801ae967  mov     rax, [rax+10h]
0x1801ae96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ae970  mov     ebx, eax
0x1801ae972  test    eax, eax
0x1801ae974  jns     short loc_1801AE9B5
0x1801ae976  mov     rcx, [rsp+3C8h]; this
0x1801ae97e  mov     r9d, eax; char *
0x1801ae981  lea     r8, aOnecoreuapAdmi_162; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801ae988  mov     edx, 9Eh; void *
0x1801ae98d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ae992  nop
0x1801ae993  lea     rcx, [rsp+3C8h+var_348]
0x1801ae99b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801ae9a0  nop
0x1801ae9a1  lea     rcx, [rsp+3C8h+var_188]; this
0x1801ae9a9  call    ??1AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry(void)
0x1801ae9ae  mov     eax, ebx
0x1801ae9b0  jmp     loc_1801AF324
0x1801ae9b5  lea     rcx, [rsp+3C8h+var_328]
0x1801ae9bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801ae9c2  nop
0x1801ae9c3  mov     rcx, [rdi+68h]
0x1801ae9c7  mov     rax, [rcx]
0x1801ae9ca  lea     rdx, [rsp+3C8h+var_328]
0x1801ae9d2  mov     rax, [rax+18h]
0x1801ae9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ae9db  mov     ebx, eax
0x1801ae9dd  test    eax, eax
0x1801ae9df  jns     short loc_1801AEA2E
0x1801ae9e1  mov     rcx, [rsp+3C8h]; this
0x1801ae9e9  mov     r9d, eax; char *
0x1801ae9ec  lea     r8, aOnecoreuapAdmi_162; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801ae9f3  mov     edx, 0A1h; void *
0x1801ae9f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ae9fd  nop
0x1801ae9fe  lea     rcx, [rsp+3C8h+var_328]
0x1801aea06  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aea0b  nop
0x1801aea0c  lea     rcx, [rsp+3C8h+var_348]
0x1801aea14  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aea19  nop
0x1801aea1a  lea     rcx, [rsp+3C8h+var_188]; this
0x1801aea22  call    ??1AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry(void)
0x1801aea27  mov     eax, ebx
0x1801aea29  jmp     loc_1801AF324
0x1801aea2e  lea     rcx, [rsp+3C8h+var_248]
0x1801aea36  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1801aea3b  nop
0x1801aea3c  lea     rcx, [rsp+3C8h+var_2C8]
0x1801aea44  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x1801aea49  nop
0x1801aea4a  mov     r8, rax
0x1801aea4d  lea     rdx, [rsp+3C8h+var_308]
0x1801aea55  lea     rcx, [rsp+3C8h+var_248]
0x1801aea5d  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(std::string const &)
0x1801aea62  nop
0x1801aea63  lea     rcx, [rsp+3C8h+var_2C8]
0x1801aea6b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801aea70  lea     rcx, [rsp+3C8h+var_380]
0x1801aea75  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x1801aea7a  nop
0x1801aea7b  mov     dl, 1
0x1801aea7d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotRestoration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotRestoration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration> `wil::Feature<__WilFeatureTraits_Feature_AutopilotRestoration>::GetImpl(void)'::`2'::impl
0x1801aea84  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotRestoration@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotRestoration>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801aea89  lea     rcx, [rsp+3C8h+var_2C8]
0x1801aea91  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801aea96  nop
0x1801aea97  lea     rcx, [rsp+3C8h+var_2C8]
0x1801aea9f  call    ?GetOrSetAutopilotMarker@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(std::wstring &)
0x1801aeaa4  mov     ebx, eax
0x1801aeaa6  test    eax, eax
0x1801aeaa8  jns     short loc_1801AEB1F
0x1801aeaaa  cmp     eax, 80070001h
0x1801aeaaf  jz      loc_1801AEB73
0x1801aeab5  lea     rcx, [rsp+3C8h+var_2C8]
0x1801aeabd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aeac2  nop
0x1801aeac3  lea     rdx, [rsp+3C8h+var_380]
0x1801aeac8  lea     rcx, [rsp+3C8h+var_380]
0x1801aeacd  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1801aead2  nop
0x1801aead3  lea     rcx, [rsp+3C8h+var_308]
0x1801aeadb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aeae0  nop
0x1801aeae1  lea     rcx, [rsp+3C8h+var_248]
0x1801aeae9  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1801aeaee  nop
0x1801aeaef  lea     rcx, [rsp+3C8h+var_328]
0x1801aeaf7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aeafc  nop
0x1801aeafd  lea     rcx, [rsp+3C8h+var_348]
0x1801aeb05  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aeb0a  nop
0x1801aeb0b  lea     rcx, [rsp+3C8h+var_188]; this
0x1801aeb13  call    ??1AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry(void)
0x1801aeb18  mov     eax, ebx
0x1801aeb1a  jmp     loc_1801AF324
0x1801aeb1f  mov     rdx, cs:off_1802168F0; "X-Autopilot-Marker"
0x1801aeb26  lea     rcx, [rsp+3C8h+var_1C8]
0x1801aeb2e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801aeb33  nop
0x1801aeb34  lea     rdx, [rsp+3C8h+var_2C8]
0x1801aeb3c  lea     rcx, [rsp+3C8h+var_1A8]
0x1801aeb44  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801aeb49  nop
0x1801aeb4a  lea     r8, [rsp+3C8h+var_1C8]
0x1801aeb52  lea     rdx, [rsp+3C8h+var_38]
0x1801aeb5a  lea     rcx, [rsp+3C8h+var_380]
0x1801aeb5f  call    ??$_Emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<std::pair<std::wstring,std::wstring>>(std::pair<std::wstring,std::wstring> &&)
0x1801aeb64  nop
0x1801aeb65  lea     rcx, [rsp+3C8h+var_1C8]; void *
0x1801aeb6d  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x1801aeb72  nop
0x1801aeb73  lea     rcx, [rsp+3C8h+var_2C8]
0x1801aeb7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aeb80  lea     rcx, [rsp+3C8h+var_2A8]; this
0x1801aeb88  call    ??0DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::DdsNetworkWrapper(void)
0x1801aeb8d  nop
0x1801aeb8e  mov     [rsp+3C8h+var_388], 0
0x1801aeb97  lea     rax, [rsp+3C8h+var_388]
0x1801aeb9c  mov     [rsp+3C8h+var_398], rax; __int64
0x1801aeba1  mov     qword ptr [rsp+3C8h+var_3A0], 0; int
0x1801aebaa  lea     rax, [rsp+3C8h+var_380]
0x1801aebaf  mov     [rsp+3C8h+var_3A8], rax; int
0x1801aebb4  lea     r9, [rsp+3C8h+var_308]
0x1801aebbc  lea     r8, [rsp+3C8h+var_328]
0x1801aebc4  lea     rdx, [rsp+3C8h+var_348]
0x1801aebcc  lea     rcx, [rsp+3C8h+var_2A8]; this
0x1801aebd4  call    ?RequestProfileJson@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@QEBUTimeoutOverride@1234@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::RequestProfileJson(std::wstring const &,std::wstring const &,std::wstring const &,std::map<std::wstring,std::wstring> const *,Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride const * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)
0x1801aebd9  mov     ebx, eax
0x1801aebdb  lea     rcx, [rsp+3C8h+PerformanceCount]; this
0x1801aebe0  call    ?GetElapsedMicroseconds@AutoPilotPerformanceTimer@Autopilot@Windows@Microsoft@@QEAA_KXZ; Microsoft::Windows::Autopilot::AutoPilotPerformanceTimer::GetElapsedMicroseconds(void)
0x1801aebe5  mov     rsi, rax
0x1801aebe8  mov     rcx, [rdi+68h]
0x1801aebec  mov     rdx, [rcx]
0x1801aebef  mov     rax, [rdx]
0x1801aebf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aebf7  mov     r9d, ebx; unsigned int
0x1801aebfa  mov     r8, rsi; __int64
0x1801aebfd  mov     rdx, rax; unsigned __int16 *
0x1801aec00  lea     rcx, [rsp+3C8h+var_188]; this
0x1801aec08  call    ?Stop@AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@QEAAXPEBG_JK@Z; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::Stop(ushort const *,__int64,ulong)
0x1801aec0d  test    ebx, ebx
0x1801aec0f  jns     loc_1801AEDAA
0x1801aec15  mov     ecx, ebx; int
0x1801aec17  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x1801aec1c  test    al, al
0x1801aec1e  jz      loc_1801AECD9
0x1801aec24  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 1
0x1801aec2b  jz      short loc_1801AEC64
0x1801aec2d  lea     rcx, [rsp+3C8h+var_2A8]
0x1801aec35  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801aec3a  mov     rsi, rax
0x1801aec3d  mov     rcx, [rdi+68h]
0x1801aec41  mov     rdx, [rcx]
0x1801aec44  mov     rax, [rdx]
0x1801aec47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aec4c  mov     [rsp+3C8h+var_3A8], rsi
0x1801aec51  mov     r9, rax
0x1801aec54  mov     r8d, ebx
0x1801aec57  lea     rdx, AutopilotDownloadFailedExpected
0x1801aec5e  call    McTemplateU0dzz_EventWriteTransfer
0x1801aec63  nop
0x1801aec64  lea     rcx, [rsp+3C8h+var_388]; this
0x1801aec69  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801aec6e  nop
0x1801aec6f  lea     rcx, [rsp+3C8h+var_2A8]; this
0x1801aec77  call    ??1DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper(void)
0x1801aec7c  nop
0x1801aec7d  lea     rdx, [rsp+3C8h+var_380]
0x1801aec82  lea     rcx, [rsp+3C8h+var_380]
0x1801aec87  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1801aec8c  nop
0x1801aec8d  lea     rcx, [rsp+3C8h+var_308]
0x1801aec95  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aec9a  nop
0x1801aec9b  lea     rcx, [rsp+3C8h+var_248]
0x1801aeca3  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1801aeca8  nop
0x1801aeca9  lea     rcx, [rsp+3C8h+var_328]
0x1801aecb1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aecb6  nop
0x1801aecb7  lea     rcx, [rsp+3C8h+var_348]
0x1801aecbf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aecc4  nop
0x1801aecc5  lea     rcx, [rsp+3C8h+var_188]; this
0x1801aeccd  call    ??1AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry(void)
0x1801aecd2  mov     eax, ebx
0x1801aecd4  jmp     loc_1801AF324
0x1801aecd9  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x1801aece0  jz      short loc_1801AED18
0x1801aece2  lea     rcx, [rsp+3C8h+var_2A8]
0x1801aecea  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801aecef  mov     rsi, rax
0x1801aecf2  mov     rcx, [rdi+68h]
0x1801aecf6  mov     rdx, [rcx]
0x1801aecf9  mov     rax, [rdx]
0x1801aecfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aed01  mov     [rsp+3C8h+var_3A8], rsi; int
0x1801aed06  mov     r9, rax
0x1801aed09  mov     r8d, ebx
0x1801aed0c  lea     rdx, AutopilotDownloadFailedUnexpected
0x1801aed13  call    McTemplateU0dzz_EventWriteTransfer
0x1801aed18  mov     rcx, [rsp+3C8h]; this
0x1801aed20  mov     r9d, ebx; char *
0x1801aed23  lea     r8, aOnecoreuapAdmi_162; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801aed2a  mov     edx, 0CBh; void *
0x1801aed2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aed34  nop
0x1801aed35  lea     rcx, [rsp+3C8h+var_388]; this
0x1801aed3a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801aed3f  nop
0x1801aed40  lea     rcx, [rsp+3C8h+var_2A8]; this
0x1801aed48  call    ??1DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper(void)
0x1801aed4d  nop
0x1801aed4e  lea     rdx, [rsp+3C8h+var_380]
0x1801aed53  lea     rcx, [rsp+3C8h+var_380]
0x1801aed58  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1801aed5d  nop
0x1801aed5e  lea     rcx, [rsp+3C8h+var_308]
0x1801aed66  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aed6b  nop
0x1801aed6c  lea     rcx, [rsp+3C8h+var_248]
0x1801aed74  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1801aed79  nop
0x1801aed7a  lea     rcx, [rsp+3C8h+var_328]
0x1801aed82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aed87  nop
0x1801aed88  lea     rcx, [rsp+3C8h+var_348]
0x1801aed90  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aed95  nop
0x1801aed96  lea     rcx, [rsp+3C8h+var_188]; this
0x1801aed9e  call    ??1AutopilotPolicyDownloadTelemetry@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotPolicyDownloadTelemetry::~AutopilotPolicyDownloadTelemetry(void)
0x1801aeda3  mov     eax, ebx
0x1801aeda5  jmp     loc_1801AF324
0x1801aedaa  mov     [rsp+3C8h+var_370], 0
0x1801aedb3  lea     rdx, [rsp+3C8h+var_370]
0x1801aedb8  lea     rcx, [rsp+3C8h+var_388]
0x1801aedbd  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1801aedc2  mov     ebx, eax
0x1801aedc4  test    eax, eax
0x1801aedc6  jns     loc_1801AEE69
0x1801aedcc  mov     rcx, [rsp+3C8h]; this
0x1801aedd4  mov     r9d, eax; char *
0x1801aedd7  lea     r8, aOnecoreuapAdmi_162; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801aedde  mov     edx, 0D1h; void *
0x1801aede3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801aede8  nop
0x1801aede9  lea     rcx, [rsp+3C8h+var_370]
0x1801aedee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801aedf3  nop
0x1801aedf4  lea     rcx, [rsp+3C8h+var_388]; this
0x1801aedf9  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1801aedfe  nop
0x1801aedff  lea     rcx, [rsp+3C8h+var_2A8]; this
0x1801aee07  call    ??1DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::~DdsNetworkWrapper(void)
0x1801aee0c  nop
0x1801aee0d  lea     rdx, [rsp+3C8h+var_380]
0x1801aee12  lea     rcx, [rsp+3C8h+var_380]
0x1801aee17  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1801aee1c  nop
0x1801aee1d  lea     rcx, [rsp+3C8h+var_308]
0x1801aee25  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aee2a  nop
0x1801aee2b  lea     rcx, [rsp+3C8h+var_248]
0x1801aee33  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1801aee38  nop
0x1801aee39  lea     rcx, [rsp+3C8h+var_328]
0x1801aee41  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801aee46  nop
0x1801aee47  lea     rcx, [rsp+3C8h+var_348]
  ... truncated ...
```
