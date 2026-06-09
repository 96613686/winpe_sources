# Microsoft::Windows::Autopilot::DdsNetworkWrapper::MarkDeviceAsRemediationRequired(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const *,Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride const * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180024878`
- end: `0x18002547f`
- name: `?MarkDeviceAsRemediationRequired@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@QEBUTimeoutOverride@1234@AEAV56@@Z`
- size: `3079`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::DdsNetworkWrapper *this, const WCHAR *pwszUrl, __int64 **, HSTRING, int, int, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800199e4`

## callees

- `0x1800045d0`
- `0x1800053c4`
- `0x18000ed44`
- `0x180010744`
- `0x180010764`
- `0x180013618`
- `0x180013de4`
- `0x180013f88`
- `0x1800179b8`
- `0x180017a20`
- `0x180018678`
- `0x18001b430`
- `0x18001f98c`
- `0x18001fcec`
- `0x18001ff1c`
- `0x1800215e4`
- `0x180022dd4`
- `0x18002311c`
- `0x180024878`
- `0x180025590`
- `0x180025958`
- `0x1800261a8`
- `0x18002f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002495a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180024989`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002495a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180024989`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024e0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024e8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024fbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002509f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025179`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002526f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002539c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024e0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024e8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024fbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002509f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025179`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002526f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002539c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024b40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024b98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024ca5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024e30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024eb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024fe3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800250c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002519f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025295`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800253c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024b40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024b98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c3f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024ca5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024d97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024e30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024eb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024fe3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800250c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002519f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025295`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800253c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024b54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024bac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024c53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024cb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024d45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024dab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024e44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024ec5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024ff7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800250d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800251b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800252a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800253d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024b54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024bac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024c53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024cb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024d45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024dab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024e44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024ec5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024ff7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800250d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800251b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800252a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800253d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024f2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024f2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800252ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800252ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002506e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025148`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800251ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002523e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002536b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002506e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025148`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800251ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002523e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002536b`
- `WINHTTP!WinHttpCrackUrl` at `0x18002491c`
- `WINHTTP!WinHttpCrackUrl` at `0x18002491c`
- `DMCmnUtils!MBToUnicode` at `0x180024b17`
- `DMCmnUtils!MBToUnicode` at `0x180024b17`

## string_xrefs

- `0x180024f28`: `Windows.Data.Json.JsonObject`
- `0x180024933`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024a04`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024a3d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024aa6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024b73`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024c7a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024d6c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024e6f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024f87`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025053`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18002512d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025222`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180025440`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::MarkDeviceAsRemediationRequired(
        Microsoft::Windows::Autopilot::DdsNetworkWrapper *this,
        const WCHAR *pwszUrl,
        __int64 **a3,
        HSTRING a4,
        int a5,
        int a6,
        __int64 a7)
{
  unsigned __int16 *v7; // rsi
  const WCHAR *v11; // rcx
  const char *v12; // r9
  INTERNET_PORT v14; // r15
  DWORD v15; // r14d
  __int64 v16; // rcx
  unsigned __int64 v17; // r8
  __int64 v18; // rcx
  int v19; // eax
  unsigned int v20; // ebx
  int RemediationData; // eax
  struct Windows::Data::Json::IJsonObject *v22; // rbx
  int v23; // eax
  int Data; // edi
  const char *v25; // rcx
  void *v26; // rsi
  HANDLE ProcessHeap; // rax
  void *v28; // rsi
  HANDLE v29; // rax
  const struct Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride *v30; // r9
  void *v31; // rsi
  HANDLE v32; // rax
  void *v33; // rsi
  HANDLE v34; // rax
  void *v35; // rsi
  HANDLE v36; // rax
  void *v37; // rsi
  HANDLE v38; // rax
  void *v39; // rsi
  HANDLE v40; // rax
  void *v41; // rsi
  HANDLE v42; // rax
  void *v43; // rdi
  HRESULT v44; // eax
  int v45; // edx
  unsigned int v46; // r8d
  HSTRING v47; // rsi
  __int64 v48; // rcx
  int v49; // eax
  unsigned int v50; // esi
  __int64 v51; // rcx
  void *v52; // rdi
  HANDLE v53; // rax
  int v54; // eax
  __int64 v55; // rcx
  void *v56; // rdi
  HANDLE v57; // rax
  int v58; // eax
  __int64 v59; // rcx
  void *v60; // rdi
  HANDLE v61; // rax
  int v62; // eax
  __int64 v63; // rcx
  void *v64; // rdi
  HANDLE v65; // rax
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v67; // r8
  __int64 v68; // rcx
  void *v69; // rdi
  HANDLE v70; // rax
  int v71; // [rsp+20h] [rbp-E0h]
  int v72; // [rsp+20h] [rbp-E0h]
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v74; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v75; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v76; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v77; // [rsp+60h] [rbp-A0h] BYREF
  struct Windows::Data::Json::IJsonObject *v78; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v80; // [rsp+80h] [rbp-80h]
  __int64 v81; // [rsp+88h] [rbp-78h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+90h] [rbp-70h] BYREF
  __int128 v83; // [rsp+100h] [rbp+0h] BYREF
  __m128i v84; // [rsp+110h] [rbp+10h]
  unsigned __int16 v85[8]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v86; // [rsp+130h] [rbp+30h]
  __int128 v87; // [rsp+140h] [rbp+40h] BYREF
  __m128i v88; // [rsp+150h] [rbp+50h]
  unsigned __int16 v89[8]; // [rsp+160h] [rbp+60h] BYREF
  __m128i si128; // [rsp+170h] [rbp+70h]
  HSTRING_HEADER hstringHeader; // [rsp+180h] [rbp+80h] BYREF
  HSTRING string; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int16 v93[256]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+2F8h]

  v7 = (unsigned __int16 *)a4;
  v75 = a4;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwSchemeLength = -1;
  UrlComponents.dwUrlPathLength = -1;
  memset_0(v93, 0, sizeof(v93));
  UrlComponents.lpszHostName = (LPSTR)v93;
  UrlComponents.dwHostNameLength = 256;
  if ( *((_QWORD *)pwszUrl + 3) <= 7u )
    v11 = pwszUrl;
  else
    v11 = *(const WCHAR **)pwszUrl;
  if ( !WinHttpCrackUrl(v11, 0, 0, &UrlComponents) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x135,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
             v12);
  if ( (unsigned int)_o__wcsnicmp(L"https", UrlComponents.lpszScheme, 5) )
  {
    if ( (unsigned int)_o__wcsnicmp(L"http", UrlComponents.lpszScheme, 4) )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        if ( *((_QWORD *)pwszUrl + 3) > 7u )
          pwszUrl = *(const WCHAR **)pwszUrl;
        McTemplateU0z_EventWriteTransfer(v16, AutopilotDownloadBadTargetUrl, pwszUrl);
      }
      v20 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)0x8000FFFFLL,
        v71);
      return v20;
    }
    v14 = 80;
    v15 = 0;
  }
  else
  {
    v14 = 443;
    v15 = 0x800000;
  }
  *(_OWORD *)v89 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v89[0] = 0;
  *(_OWORD *)pv = 0;
  v80 = 0;
  v81 = 0;
  v17 = (unsigned __int64)a3[2];
  if ( (unsigned __int64)a3[3] > 7 )
    a3 = (__int64 **)*a3;
  std::wstring::_Construct<2,unsigned short const *>((__int64)pv, a3, v17);
  v19 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AcquireMsaTicketWithRetry(v18, (__int64)pv, (__int64)v89);
  v20 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v19,
      v71);
LABEL_120:
    std::wstring::_Tidy_deallocate((char **)v89);
    return v20;
  }
  v78 = 0;
  RemediationData = Microsoft::Windows::Autopilot::HardwareInfo::GetRemediationData(&v78);
  v20 = RemediationData;
  if ( RemediationData < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)RemediationData,
      v71);
    if ( v78 )
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v78 + 16LL))(v78);
    goto LABEL_120;
  }
  v83 = 0;
  v84 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v83) = 0;
  v22 = v78;
  v23 = Microsoft::Windows::Autopilot::JsonHelpers::ToMbcsB64String(v78, &v83);
  Data = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v23,
      v71);
    std::string::_Tidy_deallocate((char **)&v83);
    if ( v22 )
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v22 + 16LL))(v22);
LABEL_21:
    v20 = Data;
    goto LABEL_120;
  }
  v76 = 0;
  lpMem = 0;
  pv[0] = &lpMem;
  pv[1] = 0;
  LOBYTE(v80) = 1;
  v25 = (const char *)&v83;
  if ( v84.m128i_i64[1] > 0xFuLL )
    v25 = (const char *)v83;
  Data = MBToUnicode(v25, 0xFDE9u, (unsigned __int16 **)&pv[1], &v76);
  if ( (_BYTE)v80 )
  {
    v26 = *(void **)pv[0];
    *(_QWORD *)pv[0] = pv[1];
    if ( v26 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v26);
    }
    v7 = (unsigned __int16 *)v75;
  }
  if ( Data < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)Data,
      v71);
    v28 = lpMem;
    lpMem = 0;
    if ( v28 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v28);
    }
    std::string::_Tidy_deallocate((char **)&v83);
    if ( v22 )
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v22 + 16LL))(v22);
    goto LABEL_21;
  }
  *(_OWORD *)v85 = 0;
  v86 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v85, lpMem, v76 - 1);
  Data = Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer(this, v93, v14, v30);
  if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(Data) )
  {
    std::wstring::_Tidy_deallocate((char **)v85);
    v31 = lpMem;
    lpMem = 0;
    if ( v31 )
    {
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v31);
    }
LABEL_41:
    std::string::_Tidy_deallocate((char **)&v83);
    if ( v22 )
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v22 + 16LL))(v22);
    goto LABEL_21;
  }
  if ( Data < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)Data,
      v71);
    std::wstring::_Tidy_deallocate((char **)v85);
    v33 = lpMem;
    lpMem = 0;
    if ( v33 )
    {
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v33);
    }
    goto LABEL_41;
  }
  Data = Microsoft::Windows::Autopilot::DdsNetworkWrapper::SendRemediationRequest(
           this,
           (LPCWSTR)UrlComponents.lpszUrlPath,
           v15,
           v89,
           v7,
           v85);
  if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(Data) )
  {
    std::wstring::_Tidy_deallocate((char **)v85);
    v35 = lpMem;
    lpMem = 0;
    if ( v35 )
    {
      v36 = GetProcessHeap();
      HeapFree(v36, 0, v35);
    }
LABEL_51:
    std::string::_Tidy_deallocate((char **)&v83);
    if ( v22 )
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v22 + 16LL))(v22);
    goto LABEL_21;
  }
  if ( Data < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)Data,
      v72);
    std::wstring::_Tidy_deallocate((char **)v85);
    v37 = lpMem;
    lpMem = 0;
    if ( v37 )
    {
      v38 = GetProcessHeap();
      HeapFree(v38, 0, v37);
    }
    goto LABEL_51;
  }
  pv[0] = 0;
  pv[1] = 0;
  Data = Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData(this, pv);
  if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(Data) )
  {
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    std::wstring::_Tidy_deallocate((char **)v85);
    v39 = lpMem;
    lpMem = 0;
    if ( v39 )
    {
      v40 = GetProcessHeap();
      HeapFree(v40, 0, v39);
    }
LABEL_65:
    std::string::_Tidy_deallocate((char **)&v83);
    if ( v22 )
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v22 + 16LL))(v22);
    goto LABEL_21;
  }
  if ( Data < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x168,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)Data,
      v72);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    std::wstring::_Tidy_deallocate((char **)v85);
    v41 = lpMem;
    lpMem = 0;
    if ( v41 )
    {
      v42 = GetProcessHeap();
      HeapFree(v42, 0, v41);
    }
    goto LABEL_65;
  }
  v74 = 0;
  v43 = pv[0];
  if ( pv[1] )
  {
    v75 = 0;
    v54 = Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(
            0xFDE9u,
            (LPCCH)pv[0],
            (int)pv[1],
            &v75);
    v50 = v54;
    if ( v54 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x173,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)v54,
        v72);
      if ( v75 )
        WindowsDeleteString(v75);
      v55 = v74;
      if ( v74 )
      {
        v74 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
      }
      if ( v43 )
        CoTaskMemFree(v43);
      std::wstring::_Tidy_deallocate((char **)v85);
      v56 = lpMem;
      lpMem = 0;
      if ( v56 )
      {
        v57 = GetProcessHeap();
        HeapFree(v57, 0, v56);
      }
      std::string::_Tidy_deallocate((char **)&v83);
      if ( v22 )
        (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v22 + 16LL))(v22);
      goto LABEL_119;
    }
    v58 = Microsoft::Windows::Autopilot::JsonHelpers::FromString(&v75, &v74);
    v50 = v58;
    if ( v58 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x175,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)v58,
        v72);
      if ( v75 )
        WindowsDeleteString(v75);
      v59 = v74;
      if ( v74 )
      {
        v74 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      }
      if ( v43 )
        CoTaskMemFree(v43);
      std::wstring::_Tidy_deallocate((char **)v85);
      v60 = lpMem;
      lpMem = 0;
      if ( v60 )
      {
        v61 = GetProcessHeap();
        HeapFree(v61, 0, v60);
      }
      std::string::_Tidy_deallocate((char **)&v83);
      if ( v22 )
        (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v22 + 16LL))(v22);
      goto LABEL_119;
    }
    if ( v75 )
      WindowsDeleteString(v75);
  }
  else
  {
    string = 0;
    v44 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
    if ( v44 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v44, v45, v46);
      JUMPOUT(0x18002547ELL);
    }
    v47 = string;
    v48 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    }
    v49 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>((__int64)v47, &v74);
    v50 = v49;
    if ( v49 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)v49,
        v72);
      v51 = v74;
      if ( v74 )
      {
        v74 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      }
      if ( v43 )
        CoTaskMemFree(v43);
      std::wstring::_Tidy_deallocate((char **)v85);
      v52 = lpMem;
      lpMem = 0;
      if ( v52 )
      {
        v53 = GetProcessHeap();
        HeapFree(v53, 0, v52);
      }
      std::string::_Tidy_deallocate((char **)&v83);
      if ( v22 )
        (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v22 + 16LL))(v22);
LABEL_119:
      v20 = v50;
      goto LABEL_120;
    }
  }
  v77 = 0;
  v62 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v74, &v77);
  v50 = v62;
  if ( v62 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x178,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v62,
      v72);
    if ( v77 )
      WindowsDeleteString(v77);
    v63 = v74;
    if ( v74 )
    {
      v74 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
    }
    if ( v43 )
      CoTaskMemFree(v43);
    std::wstring::_Tidy_deallocate((char **)v85);
    v64 = lpMem;
    lpMem = 0;
    if ( v64 )
    {
      v65 = GetProcessHeap();
      HeapFree(v65, 0, v64);
    }
    std::string::_Tidy_deallocate((char **)&v83);
    if ( v22 )
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v22 + 16LL))(v22);
    goto LABEL_119;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v77, 0);
  v87 = 0;
  v88 = 0;
  v67 = -1;
  do
    ++v67;
  while ( StringRawBuffer[v67] );
  std::wstring::_Construct<1,unsigned short const *>(&v87, StringRawBuffer, v67);
  if ( (__int128 *)a7 != &v87 )
  {
    std::wstring::_Tidy_deallocate((char **)a7);
    *(_OWORD *)a7 = v87;
    *(__m128i *)(a7 + 16) = v88;
    v88 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v87) = 0;
  }
  std::wstring::_Tidy_deallocate((char **)&v87);
  if ( v77 )
    WindowsDeleteString(v77);
  v68 = v74;
  if ( v74 )
  {
    v74 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
  }
  if ( v43 )
    CoTaskMemFree(v43);
  std::wstring::_Tidy_deallocate((char **)v85);
  v69 = lpMem;
  lpMem = 0;
  if ( v69 )
  {
    v70 = GetProcessHeap();
    HeapFree(v70, 0, v69);
  }
  std::string::_Tidy_deallocate((char **)&v83);
  if ( v22 )
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v22 + 16LL))(v22);
  std::wstring::_Tidy_deallocate((char **)v89);
  return 0;
}

```

## disassembly

```asm
0x180024878  push    rbp
0x18002487a  push    rbx
0x18002487b  push    rsi
0x18002487c  push    rdi
0x18002487d  push    r12
0x18002487f  push    r13
0x180024881  push    r14
0x180024883  push    r15
0x180024885  lea     rbp, [rsp-2B8h]
0x18002488d  sub     rsp, 3B8h
0x180024894  mov     rax, cs:__security_cookie
0x18002489b  xor     rax, rsp
0x18002489e  mov     [rbp+2F0h+var_50], rax
0x1800248a5  mov     rsi, r9
0x1800248a8  mov     [rsp+3F0h+var_3A0], r9
0x1800248ad  mov     rdi, r8
0x1800248b0  mov     rbx, rdx
0x1800248b3  mov     r13, rcx
0x1800248b6  mov     r12, [rbp+2F0h+arg_30]
0x1800248bd  mov     r14d, 68h ; 'h'
0x1800248c3  mov     r8d, r14d; Size
0x1800248c6  xor     edx, edx; Val
0x1800248c8  lea     rcx, [rbp+2F0h+UrlComponents]; void *
0x1800248cc  call    memset_0
0x1800248d1  mov     [rbp+2F0h+UrlComponents.dwStructSize], r14d
0x1800248d5  or      eax, 0FFFFFFFFh
0x1800248d8  mov     [rbp+2F0h+UrlComponents.dwSchemeLength], eax
0x1800248db  mov     [rbp+2F0h+UrlComponents.dwUrlPathLength], eax
0x1800248de  xor     edx, edx; Val
0x1800248e0  mov     r8d, 200h; Size
0x1800248e6  lea     rcx, [rbp+2F0h+var_250]; void *
0x1800248ed  call    memset_0
0x1800248f2  lea     rax, [rbp+2F0h+var_250]
0x1800248f9  mov     [rbp+2F0h+UrlComponents.lpszHostName], rax
0x1800248fd  mov     [rbp+2F0h+UrlComponents.dwHostNameLength], 100h
0x180024904  cmp     qword ptr [rbx+18h], 7
0x180024909  jbe     short loc_180024910
0x18002490b  mov     rcx, [rbx]
0x18002490e  jmp     short loc_180024913
0x180024910  mov     rcx, rbx; pwszUrl
0x180024913  lea     r9, [rbp+2F0h+UrlComponents]; lpUrlComponents
0x180024917  xor     r8d, r8d; dwFlags
0x18002491a  xor     edx, edx; dwUrlLength
0x18002491c  call    cs:__imp_WinHttpCrackUrl
0x180024923  nop     dword ptr [rax+rax+00h]
0x180024928  test    eax, eax
0x18002492a  jnz     short loc_180024949
0x18002492c  mov     rcx, [rbp+2F8h]; this
0x180024933  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002493a  mov     edx, 135h; void *
0x18002493f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024944  jmp     loc_180025453
0x180024949  mov     r8d, 5
0x18002494f  mov     rdx, [rbp+2F0h+UrlComponents.lpszScheme]
0x180024953  lea     rcx, aHttps; "https"
0x18002495a  call    cs:__imp__o__wcsnicmp
0x180024961  nop     dword ptr [rax+rax+00h]
0x180024966  test    eax, eax
0x180024968  jnz     short loc_180024978
0x18002496a  mov     r15d, 1BBh
0x180024970  mov     r14d, 800000h
0x180024976  jmp     short loc_1800249A4
0x180024978  mov     r8d, 4
0x18002497e  mov     rdx, [rbp+2F0h+UrlComponents.lpszScheme]
0x180024982  lea     rcx, aHttp; "http"
0x180024989  call    cs:__imp__o__wcsnicmp
0x180024990  nop     dword ptr [rax+rax+00h]
0x180024995  test    eax, eax
0x180024997  jnz     loc_18002540F
0x18002499d  lea     r15d, [rax+50h]
0x1800249a1  xor     r14d, r14d
0x1800249a4  xorps   xmm0, xmm0
0x1800249a7  movups  xmmword ptr [rbp+2F0h+var_290], xmm0
0x1800249ab  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800249b3  movdqu  [rbp+2F0h+var_280], xmm1
0x1800249b8  xor     eax, eax
0x1800249ba  mov     [rbp+2F0h+var_290], ax
0x1800249be  movups  xmmword ptr [rsp+3F0h+pv], xmm0
0x1800249c3  mov     [rbp+2F0h+var_370], rax
0x1800249c7  mov     [rbp+2F0h+var_368], rax
0x1800249cb  mov     r8, [rdi+10h]
0x1800249cf  cmp     qword ptr [rdi+18h], 7
0x1800249d4  jbe     short loc_1800249D9
0x1800249d6  mov     rdi, [rdi]
0x1800249d9  mov     rdx, rdi
0x1800249dc  lea     rcx, [rsp+3F0h+pv]
0x1800249e1  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800249e6  lea     r8, [rbp+2F0h+var_290]
0x1800249ea  lea     rdx, [rsp+3F0h+pv]
0x1800249ef  call    ?AcquireMsaTicketWithRetry@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AcquireMsaTicketWithRetry(std::wstring,std::wstring &)
0x1800249f4  mov     ebx, eax
0x1800249f6  test    eax, eax
0x1800249f8  jns     short loc_180024A1A
0x1800249fa  mov     rcx, [rbp+2F8h]; this
0x180024a01  mov     r9d, eax; char *
0x180024a04  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024a0b  mov     edx, 14Bh; void *
0x180024a10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024a15  jmp     loc_1800252D7
0x180024a1a  mov     [rsp+3F0h+var_388], 0
0x180024a23  lea     rcx, [rsp+3F0h+var_388]
0x180024a28  call    ?GetRemediationData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@W4HardwareComponentsCacheType@234@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetRemediationData(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::Windows::Autopilot::HardwareComponentsCacheType)
0x180024a2d  mov     ebx, eax
0x180024a2f  test    eax, eax
0x180024a31  jns     short loc_180024A6B
0x180024a33  mov     rcx, [rbp+2F8h]; this
0x180024a3a  mov     r9d, eax; char *
0x180024a3d  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024a44  mov     edx, 14Fh; void *
0x180024a49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024a4e  nop
0x180024a4f  mov     rcx, [rsp+3F0h+var_388]
0x180024a54  test    rcx, rcx
0x180024a57  jz      short loc_180024A66
0x180024a59  mov     rax, [rcx]
0x180024a5c  mov     rax, [rax+10h]
0x180024a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a65  nop
0x180024a66  jmp     loc_1800252D7
0x180024a6b  xorps   xmm0, xmm0
0x180024a6e  movups  [rbp+2F0h+var_2F0], xmm0
0x180024a72  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180024a7a  movdqu  [rbp+2F0h+var_2E0], xmm1
0x180024a7f  mov     byte ptr [rbp+2F0h+var_2F0], 0
0x180024a83  lea     rdx, [rbp+2F0h+var_2F0]
0x180024a87  mov     rbx, [rsp+3F0h+var_388]
0x180024a8c  mov     rcx, rbx
0x180024a8f  call    ?ToMbcsB64String@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToMbcsB64String(Windows::Data::Json::IJsonObject *,std::string &)
0x180024a94  mov     edi, eax
0x180024a96  xor     ecx, ecx
0x180024a98  test    eax, eax
0x180024a9a  jns     short loc_180024ADE
0x180024a9c  mov     rcx, [rbp+2F8h]; this
0x180024aa3  mov     r9d, eax; char *
0x180024aa6  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024aad  mov     edx, 153h; void *
0x180024ab2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024ab7  nop
0x180024ab8  lea     rcx, [rbp+2F0h+var_2F0]
0x180024abc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180024ac1  nop
0x180024ac2  test    rbx, rbx
0x180024ac5  jz      short loc_180024AD7
0x180024ac7  mov     rax, [rbx]
0x180024aca  mov     rcx, rbx
0x180024acd  mov     rax, [rax+10h]
0x180024ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ad6  nop
0x180024ad7  mov     ebx, edi
0x180024ad9  jmp     loc_1800252D7
0x180024ade  mov     [rsp+3F0h+var_398], ecx
0x180024ae2  mov     [rsp+3F0h+lpMem], rcx
0x180024ae7  lea     rax, [rsp+3F0h+lpMem]
0x180024aec  mov     [rsp+3F0h+pv], rax
0x180024af1  mov     [rsp+3F0h+pv+8], rcx
0x180024af6  mov     byte ptr [rbp+2F0h+var_370], 1
0x180024afa  lea     rcx, [rbp+2F0h+var_2F0]
0x180024afe  cmp     qword ptr [rbp+2F0h+var_2E0+8], 0Fh
0x180024b03  cmova   rcx, qword ptr [rbp+2F0h+var_2F0]
0x180024b08  lea     r9, [rsp+3F0h+var_398]
0x180024b0d  lea     r8, [rsp+3F0h+pv+8]
0x180024b12  mov     edx, 0FDE9h
0x180024b17  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x180024b1e  nop     dword ptr [rax+rax+00h]
0x180024b23  mov     edi, eax
0x180024b25  cmp     byte ptr [rbp+2F0h+var_370], 0
0x180024b29  jz      short loc_180024B65
0x180024b2b  mov     rdx, [rsp+3F0h+pv]
0x180024b30  mov     rsi, [rdx]
0x180024b33  mov     rcx, [rsp+3F0h+pv+8]
0x180024b38  mov     [rdx], rcx
0x180024b3b  test    rsi, rsi
0x180024b3e  jz      short loc_180024B60
0x180024b40  call    cs:__imp_GetProcessHeap
0x180024b47  nop     dword ptr [rax+rax+00h]
0x180024b4c  mov     rcx, rax; hHeap
0x180024b4f  mov     r8, rsi; lpMem
0x180024b52  xor     edx, edx; dwFlags
0x180024b54  call    cs:__imp_HeapFree
0x180024b5b  nop     dword ptr [rax+rax+00h]
0x180024b60  mov     rsi, [rsp+3F0h+var_3A0]
0x180024b65  test    edi, edi
0x180024b67  jns     short loc_180024BDD
0x180024b69  mov     rcx, [rbp+2F8h]; this
0x180024b70  mov     r9d, edi; char *
0x180024b73  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024b7a  mov     edx, 158h; void *
0x180024b7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024b84  nop
0x180024b85  mov     rsi, [rsp+3F0h+lpMem]
0x180024b8a  mov     [rsp+3F0h+lpMem], 0
0x180024b93  test    rsi, rsi
0x180024b96  jz      short loc_180024BB9
0x180024b98  call    cs:__imp_GetProcessHeap
0x180024b9f  nop     dword ptr [rax+rax+00h]
0x180024ba4  mov     rcx, rax; hHeap
0x180024ba7  mov     r8, rsi; lpMem
0x180024baa  xor     edx, edx; dwFlags
0x180024bac  call    cs:__imp_HeapFree
0x180024bb3  nop     dword ptr [rax+rax+00h]
0x180024bb8  nop
0x180024bb9  lea     rcx, [rbp+2F0h+var_2F0]
0x180024bbd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180024bc2  nop
0x180024bc3  test    rbx, rbx
0x180024bc6  jz      short loc_180024BD8
0x180024bc8  mov     rax, [rbx]
0x180024bcb  mov     rcx, rbx
0x180024bce  mov     rax, [rax+10h]
0x180024bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bd7  nop
0x180024bd8  jmp     loc_180024AD7
0x180024bdd  xorps   xmm0, xmm0
0x180024be0  movups  xmmword ptr [rbp+2F0h+var_2D0], xmm0
0x180024be4  xorps   xmm1, xmm1
0x180024be7  movdqu  [rbp+2F0h+var_2C0], xmm1
0x180024bec  mov     r8d, [rsp+3F0h+var_398]
0x180024bf1  dec     r8d
0x180024bf4  mov     rdx, [rsp+3F0h+lpMem]
0x180024bf9  lea     rcx, [rbp+2F0h+var_2D0]
0x180024bfd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180024c02  nop
0x180024c03  movzx   r8d, r15w; unsigned __int16
0x180024c07  lea     rdx, [rbp+2F0h+var_250]; unsigned __int16 *
0x180024c0e  mov     rcx, r13; this
0x180024c11  call    ?ConnectToServer@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGGQEBUTimeoutOverride@1234@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer(ushort const *,ushort,Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride const * const)
0x180024c16  mov     edi, eax
0x180024c18  mov     ecx, eax; int
0x180024c1a  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x180024c1f  xor     r15d, r15d
0x180024c22  test    al, al
0x180024c24  jz      short loc_180024C6C
0x180024c26  lea     rcx, [rbp+2F0h+var_2D0]
0x180024c2a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024c2f  nop
0x180024c30  mov     rsi, [rsp+3F0h+lpMem]
0x180024c35  mov     [rsp+3F0h+lpMem], r15
0x180024c3a  test    rsi, rsi
0x180024c3d  jz      short loc_180024C60
0x180024c3f  call    cs:__imp_GetProcessHeap
0x180024c46  nop     dword ptr [rax+rax+00h]
0x180024c4b  mov     rcx, rax; hHeap
0x180024c4e  mov     r8, rsi; lpMem
0x180024c51  xor     edx, edx; dwFlags
0x180024c53  call    cs:__imp_HeapFree
0x180024c5a  nop     dword ptr [rax+rax+00h]
0x180024c5f  nop
0x180024c60  lea     rcx, [rbp+2F0h+var_2F0]
0x180024c64  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180024c69  nop
0x180024c6a  jmp     short loc_180024CD0
0x180024c6c  test    edi, edi
0x180024c6e  jns     short loc_180024CEA
0x180024c70  mov     rcx, [rbp+2F8h]; this
0x180024c77  mov     r9d, edi; char *
0x180024c7a  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180024c81  mov     edx, 15Eh; void *
0x180024c86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024c8b  nop
0x180024c8c  lea     rcx, [rbp+2F0h+var_2D0]
0x180024c90  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024c95  nop
0x180024c96  mov     rsi, [rsp+3F0h+lpMem]
0x180024c9b  mov     [rsp+3F0h+lpMem], r15
0x180024ca0  test    rsi, rsi
0x180024ca3  jz      short loc_180024CC6
0x180024ca5  call    cs:__imp_GetProcessHeap
0x180024cac  nop     dword ptr [rax+rax+00h]
0x180024cb1  mov     rcx, rax; hHeap
0x180024cb4  mov     r8, rsi; lpMem
0x180024cb7  xor     edx, edx; dwFlags
0x180024cb9  call    cs:__imp_HeapFree
0x180024cc0  nop     dword ptr [rax+rax+00h]
0x180024cc5  nop
0x180024cc6  lea     rcx, [rbp+2F0h+var_2F0]
0x180024cca  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180024ccf  nop
0x180024cd0  test    rbx, rbx
0x180024cd3  jz      short loc_180024CE5
0x180024cd5  mov     rax, [rbx]
0x180024cd8  mov     rcx, rbx
0x180024cdb  mov     rax, [rax+10h]
0x180024cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ce4  nop
0x180024ce5  jmp     loc_180024AD7
0x180024cea  lea     rax, [rbp+2F0h+var_2D0]
0x180024cee  mov     [rsp+3F0h+var_3C8], rax; unsigned __int16 *
0x180024cf3  mov     [rsp+3F0h+var_3D0], rsi; int
0x180024cf8  lea     r9, [rbp+2F0h+var_290]; unsigned __int16 *
0x180024cfc  mov     r8d, r14d; dwFlags
0x180024cff  mov     rdx, [rbp+2F0h+UrlComponents.lpszUrlPath]; pwszObjectName
0x180024d03  mov     rcx, r13; this
0x180024d06  call    ?SendRemediationRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::SendRemediationRequest(ushort const *,ulong,std::wstring const &,std::wstring const &,std::wstring const &,std::map<std::wstring,std::wstring> const *)
0x180024d0b  mov     edi, eax
0x180024d0d  mov     ecx, eax; int
0x180024d0f  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x180024d14  test    al, al
0x180024d16  jz      short loc_180024D5E
0x180024d18  lea     rcx, [rbp+2F0h+var_2D0]
0x180024d1c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
  ... truncated ...
```
