# Microsoft::Windows::Autopilot::DdsNetworkWrapper::MarkDeviceAsRemediationRequired(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> const *,Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride const * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180023cb0`
- end: `0x1800247aa`
- name: `?MarkDeviceAsRemediationRequired@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@QEBUTimeoutOverride@1234@AEAV56@@Z`
- size: `2810`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Autopilot::DdsNetworkWrapper *this@<rcx>, LPCWSTR pwszUrl@<rdx>, int, int, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800193e4`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x18000ec40`
- `0x1800105d4`
- `0x1800105f4`
- `0x180013370`
- `0x180013a40`
- `0x180013be0`
- `0x180017488`
- `0x1800174f0`
- `0x180018120`
- `0x18001ada0`
- `0x18001f0ec`
- `0x18001f440`
- `0x18001f638`
- `0x180020bd0`
- `0x18002230c`
- `0x18002264c`
- `0x180023cb0`
- `0x1800248b0`
- `0x180024c34`
- `0x1800253d4`
- `0x18002e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180023d8c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180023db5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180023d8c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180023db5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800241e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002424d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024431`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800244f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800245cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800246da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800241e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002424d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024431`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800244f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800245cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800246da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023f60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024047`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800240a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024121`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002417b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024202`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002426d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024387`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024451`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024513`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800245eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800246fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023f60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024047`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800240a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024121`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002417b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024202`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002426d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024387`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024451`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024513`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800245eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800246fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023f6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023fba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024055`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800240af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002412f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024189`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024210`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002427b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024395`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002445f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024521`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800245f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024708`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023f6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023fba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024055`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800240af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002412f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024189`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024210`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002427b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024395`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002445f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024521`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800245f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024708`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800242df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800242df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024636`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024636`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800244c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800245a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800246af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024406`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800244c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024556`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800245a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800246af`
- `WINHTTP!WinHttpCrackUrl` at `0x180023d54`
- `WINHTTP!WinHttpCrackUrl` at `0x180023d54`
- `DMCmnUtils!MBToUnicode` at `0x180023f3d`
- `DMCmnUtils!MBToUnicode` at `0x180023f3d`

## string_xrefs

- `0x1800242d8`: `Windows.Data.Json.JsonObject`
- `0x180023d65`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180023e2a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180023e63`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180023ecc`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180023f87`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024076`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024150`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024231`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024331`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1800243eb`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1800244ad`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180024584`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18002476c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::MarkDeviceAsRemediationRequired(
        Microsoft::Windows::Autopilot::DdsNetworkWrapper *this,
        const WCHAR *pwszUrl,
        __int64 a3,
        HSTRING a4,
        int a5,
        int a6,
        __int128 *a7)
{
  unsigned __int16 *v7; // rsi
  const WCHAR *v10; // rcx
  const char *v11; // r9
  unsigned __int16 v13; // r15
  DWORD v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  unsigned int v18; // ebx
  int RemediationData; // eax
  __int64 v20; // rbx
  int v21; // eax
  int Data; // edi
  const char *v23; // rcx
  void *v24; // rsi
  HANDLE ProcessHeap; // rax
  void *v26; // rsi
  HANDLE v27; // rax
  const struct Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride *v28; // r9
  void *v29; // rsi
  HANDLE v30; // rax
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
  void *v41; // rdi
  HRESULT v42; // eax
  int v43; // edx
  unsigned int v44; // r8d
  HSTRING v45; // rsi
  __int64 v46; // rcx
  int v47; // eax
  unsigned int v48; // esi
  __int64 v49; // rcx
  void *v50; // rdi
  HANDLE v51; // rax
  int v52; // eax
  __int64 v53; // rcx
  void *v54; // rdi
  HANDLE v55; // rax
  int v56; // eax
  __int64 v57; // rcx
  void *v58; // rdi
  HANDLE v59; // rax
  int v60; // eax
  __int64 v61; // rcx
  void *v62; // rdi
  HANDLE v63; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v65; // r8
  __int64 v66; // rcx
  void *v67; // rdi
  HANDLE v68; // rax
  int v69; // [rsp+20h] [rbp-E0h]
  int v70; // [rsp+20h] [rbp-E0h]
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v72; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v73; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v74; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v75; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v76; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v78; // [rsp+80h] [rbp-80h]
  __int64 v79; // [rsp+88h] [rbp-78h]
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+90h] [rbp-70h] BYREF
  __int128 v81; // [rsp+100h] [rbp+0h] BYREF
  __m128i v82; // [rsp+110h] [rbp+10h]
  unsigned __int16 v83[8]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v84; // [rsp+130h] [rbp+30h]
  __int128 v85; // [rsp+140h] [rbp+40h] BYREF
  __m128i v86; // [rsp+150h] [rbp+50h]
  unsigned __int16 v87[8]; // [rsp+160h] [rbp+60h] BYREF
  __m128i si128; // [rsp+170h] [rbp+70h]
  HSTRING_HEADER hstringHeader; // [rsp+180h] [rbp+80h] BYREF
  HSTRING string; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int16 v91[256]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+2F8h]

  v7 = (unsigned __int16 *)a4;
  v73 = a4;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.dwSchemeLength = -1;
  UrlComponents.dwUrlPathLength = -1;
  memset_0(v91, 0, sizeof(v91));
  UrlComponents.lpszHostName = (LPSTR)v91;
  UrlComponents.dwHostNameLength = 256;
  if ( *((_QWORD *)pwszUrl + 3) <= 7u )
    v10 = pwszUrl;
  else
    v10 = *(const WCHAR **)pwszUrl;
  if ( !WinHttpCrackUrl(v10, 0, 0, &UrlComponents) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x135,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
             v11);
  if ( (unsigned int)_o__wcsnicmp(L"https", UrlComponents.lpszScheme, 5) )
  {
    if ( (unsigned int)_o__wcsnicmp(L"http", UrlComponents.lpszScheme, 4) )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      {
        if ( *((_QWORD *)pwszUrl + 3) > 7u )
          pwszUrl = *(const WCHAR **)pwszUrl;
        McTemplateU0z_EventWriteTransfer(v15, AutopilotDownloadBadTargetUrl, pwszUrl);
      }
      v18 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)0x8000FFFFLL,
        v69);
      return v18;
    }
    v13 = 80;
    v14 = 0;
  }
  else
  {
    v13 = 443;
    v14 = 0x800000;
  }
  *(_OWORD *)v87 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v87[0] = 0;
  *(_OWORD *)pv = 0;
  v78 = 0;
  v79 = 0;
  std::wstring::_Construct<2,unsigned short const *>(pv);
  v17 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::AcquireMsaTicketWithRetry(v16, pv, v87);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v17,
      v69);
LABEL_118:
    std::wstring::_Tidy_deallocate(v87);
    return v18;
  }
  v76 = 0;
  RemediationData = Microsoft::Windows::Autopilot::HardwareInfo::GetRemediationData(&v76);
  v18 = RemediationData;
  if ( RemediationData < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)RemediationData,
      v69);
    if ( v76 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    goto LABEL_118;
  }
  v81 = 0;
  v82 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v81) = 0;
  v20 = v76;
  v21 = Microsoft::Windows::Autopilot::JsonHelpers::ToMbcsB64String(v76, &v81);
  Data = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v21,
      v69);
    std::string::_Tidy_deallocate(&v81);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
LABEL_19:
    v18 = Data;
    goto LABEL_118;
  }
  v74 = 0;
  lpMem = 0;
  pv[0] = &lpMem;
  pv[1] = 0;
  LOBYTE(v78) = 1;
  v23 = (const char *)&v81;
  if ( v82.m128i_i64[1] > 0xFuLL )
    v23 = (const char *)v81;
  Data = MBToUnicode(v23, 0xFDE9u, (unsigned __int16 **)&pv[1], &v74);
  if ( (_BYTE)v78 )
  {
    v24 = *(void **)pv[0];
    *(_QWORD *)pv[0] = pv[1];
    if ( v24 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v24);
    }
    v7 = (unsigned __int16 *)v73;
  }
  if ( Data < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)Data,
      v69);
    v26 = lpMem;
    lpMem = 0;
    if ( v26 )
    {
      v27 = GetProcessHeap();
      HeapFree(v27, 0, v26);
    }
    std::string::_Tidy_deallocate(&v81);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_19;
  }
  *(_OWORD *)v83 = 0;
  v84 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v83, lpMem, v74 - 1);
  Data = Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer(this, v91, v13, v28);
  if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(Data) )
  {
    std::wstring::_Tidy_deallocate(v83);
    v29 = lpMem;
    lpMem = 0;
    if ( v29 )
    {
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v29);
    }
LABEL_39:
    std::string::_Tidy_deallocate(&v81);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_19;
  }
  if ( Data < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)Data,
      v69);
    std::wstring::_Tidy_deallocate(v83);
    v31 = lpMem;
    lpMem = 0;
    if ( v31 )
    {
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v31);
    }
    goto LABEL_39;
  }
  Data = Microsoft::Windows::Autopilot::DdsNetworkWrapper::SendRemediationRequest(
           this,
           (LPCWSTR)UrlComponents.lpszUrlPath,
           v14,
           v87,
           v7,
           v83);
  if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(Data) )
  {
    std::wstring::_Tidy_deallocate(v83);
    v33 = lpMem;
    lpMem = 0;
    if ( v33 )
    {
      v34 = GetProcessHeap();
      HeapFree(v34, 0, v33);
    }
LABEL_49:
    std::string::_Tidy_deallocate(&v81);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_19;
  }
  if ( Data < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)Data,
      v70);
    std::wstring::_Tidy_deallocate(v83);
    v35 = lpMem;
    lpMem = 0;
    if ( v35 )
    {
      v36 = GetProcessHeap();
      HeapFree(v36, 0, v35);
    }
    goto LABEL_49;
  }
  pv[0] = 0;
  pv[1] = 0;
  Data = Microsoft::Windows::Autopilot::DdsNetworkWrapper::RetrieveData(this, pv);
  if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(Data) )
  {
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    std::wstring::_Tidy_deallocate(v83);
    v37 = lpMem;
    lpMem = 0;
    if ( v37 )
    {
      v38 = GetProcessHeap();
      HeapFree(v38, 0, v37);
    }
LABEL_63:
    std::string::_Tidy_deallocate(&v81);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_19;
  }
  if ( Data < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x168,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)Data,
      v70);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    std::wstring::_Tidy_deallocate(v83);
    v39 = lpMem;
    lpMem = 0;
    if ( v39 )
    {
      v40 = GetProcessHeap();
      HeapFree(v40, 0, v39);
    }
    goto LABEL_63;
  }
  v72 = 0;
  v41 = pv[0];
  if ( pv[1] )
  {
    v73 = 0;
    v52 = Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(
            0xFDE9u,
            (LPCCH)pv[0],
            (int)pv[1],
            &v73);
    v48 = v52;
    if ( v52 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x173,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)v52,
        v70);
      if ( v73 )
        WindowsDeleteString(v73);
      v53 = v72;
      if ( v72 )
      {
        v72 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
      }
      if ( v41 )
        CoTaskMemFree(v41);
      std::wstring::_Tidy_deallocate(v83);
      v54 = lpMem;
      lpMem = 0;
      if ( v54 )
      {
        v55 = GetProcessHeap();
        HeapFree(v55, 0, v54);
      }
      std::string::_Tidy_deallocate(&v81);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      goto LABEL_117;
    }
    v56 = Microsoft::Windows::Autopilot::JsonHelpers::FromString(&v73, &v72);
    v48 = v56;
    if ( v56 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x175,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)v56,
        v70);
      if ( v73 )
        WindowsDeleteString(v73);
      v57 = v72;
      if ( v72 )
      {
        v72 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
      }
      if ( v41 )
        CoTaskMemFree(v41);
      std::wstring::_Tidy_deallocate(v83);
      v58 = lpMem;
      lpMem = 0;
      if ( v58 )
      {
        v59 = GetProcessHeap();
        HeapFree(v59, 0, v58);
      }
      std::string::_Tidy_deallocate(&v81);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      goto LABEL_117;
    }
    if ( v73 )
      WindowsDeleteString(v73);
  }
  else
  {
    string = 0;
    v42 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
    if ( v42 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v42, v43, v44);
      JUMPOUT(0x1800247A9LL);
    }
    v45 = string;
    v46 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    v47 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v45, &v72);
    v48 = v47;
    if ( v47 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16D,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)v47,
        v70);
      v49 = v72;
      if ( v72 )
      {
        v72 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
      if ( v41 )
        CoTaskMemFree(v41);
      std::wstring::_Tidy_deallocate(v83);
      v50 = lpMem;
      lpMem = 0;
      if ( v50 )
      {
        v51 = GetProcessHeap();
        HeapFree(v51, 0, v50);
      }
      std::string::_Tidy_deallocate(&v81);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
LABEL_117:
      v18 = v48;
      goto LABEL_118;
    }
  }
  v75 = 0;
  v60 = Microsoft::Windows::Autopilot::JsonHelpers::ToString(v72, &v75);
  v48 = v60;
  if ( v60 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x178,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v60,
      v70);
    if ( v75 )
      WindowsDeleteString(v75);
    v61 = v72;
    if ( v72 )
    {
      v72 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
    }
    if ( v41 )
      CoTaskMemFree(v41);
    std::wstring::_Tidy_deallocate(v83);
    v62 = lpMem;
    lpMem = 0;
    if ( v62 )
    {
      v63 = GetProcessHeap();
      HeapFree(v63, 0, v62);
    }
    std::string::_Tidy_deallocate(&v81);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    goto LABEL_117;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v75, 0);
  v85 = 0;
  v86 = 0;
  v65 = -1;
  do
    ++v65;
  while ( StringRawBuffer[v65] );
  std::wstring::_Construct<1,unsigned short const *>(&v85, StringRawBuffer, v65);
  if ( a7 != &v85 )
  {
    std::wstring::_Tidy_deallocate(a7);
    *a7 = v85;
    a7[1] = (__int128)v86;
    v86 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v85) = 0;
  }
  std::wstring::_Tidy_deallocate(&v85);
  if ( v75 )
    WindowsDeleteString(v75);
  v66 = v72;
  if ( v72 )
  {
    v72 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
  }
  if ( v41 )
    CoTaskMemFree(v41);
  std::wstring::_Tidy_deallocate(v83);
  v67 = lpMem;
  lpMem = 0;
  if ( v67 )
  {
    v68 = GetProcessHeap();
    HeapFree(v68, 0, v67);
  }
  std::string::_Tidy_deallocate(&v81);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  std::wstring::_Tidy_deallocate(v87);
  return 0;
}

```

## disassembly

```asm
0x180023cb0  push    rbp
0x180023cb2  push    rbx
0x180023cb3  push    rsi
0x180023cb4  push    rdi
0x180023cb5  push    r12
0x180023cb7  push    r13
0x180023cb9  push    r14
0x180023cbb  push    r15
0x180023cbd  lea     rbp, [rsp-2B8h]
0x180023cc5  sub     rsp, 3B8h
0x180023ccc  mov     rax, cs:__security_cookie
0x180023cd3  xor     rax, rsp
0x180023cd6  mov     [rbp+2F0h+var_50], rax
0x180023cdd  mov     rsi, r9
0x180023ce0  mov     [rsp+3F0h+var_3A0], r9
0x180023ce5  mov     rdi, r8
0x180023ce8  mov     rbx, rdx
0x180023ceb  mov     r13, rcx
0x180023cee  mov     r12, [rbp+2F0h+arg_30]
0x180023cf5  mov     r14d, 68h ; 'h'
0x180023cfb  mov     r8d, r14d; Size
0x180023cfe  xor     edx, edx; Val
0x180023d00  lea     rcx, [rbp+2F0h+UrlComponents]; void *
0x180023d04  call    memset_0
0x180023d09  mov     [rbp+2F0h+UrlComponents.dwStructSize], r14d
0x180023d0d  or      eax, 0FFFFFFFFh
0x180023d10  mov     [rbp+2F0h+UrlComponents.dwSchemeLength], eax
0x180023d13  mov     [rbp+2F0h+UrlComponents.dwUrlPathLength], eax
0x180023d16  xor     edx, edx; Val
0x180023d18  mov     r8d, 200h; Size
0x180023d1e  lea     rcx, [rbp+2F0h+var_250]; void *
0x180023d25  call    memset_0
0x180023d2a  lea     rax, [rbp+2F0h+var_250]
0x180023d31  mov     [rbp+2F0h+UrlComponents.lpszHostName], rax
0x180023d35  mov     [rbp+2F0h+UrlComponents.dwHostNameLength], 100h
0x180023d3c  cmp     qword ptr [rbx+18h], 7
0x180023d41  jbe     short loc_180023D48
0x180023d43  mov     rcx, [rbx]
0x180023d46  jmp     short loc_180023D4B
0x180023d48  mov     rcx, rbx; pwszUrl
0x180023d4b  lea     r9, [rbp+2F0h+UrlComponents]; lpUrlComponents
0x180023d4f  xor     r8d, r8d; dwFlags
0x180023d52  xor     edx, edx; dwUrlLength
0x180023d54  call    cs:__imp_WinHttpCrackUrl
0x180023d5a  test    eax, eax
0x180023d5c  jnz     short loc_180023D7B
0x180023d5e  mov     rcx, [rbp+2F8h]; this
0x180023d65  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180023d6c  mov     edx, 135h; void *
0x180023d71  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023d76  jmp     loc_18002477F
0x180023d7b  mov     r8d, 5
0x180023d81  mov     rdx, [rbp+2F0h+UrlComponents.lpszScheme]
0x180023d85  lea     rcx, aHttps; "https"
0x180023d8c  call    cs:__imp__o__wcsnicmp
0x180023d92  test    eax, eax
0x180023d94  jnz     short loc_180023DA4
0x180023d96  mov     r15d, 1BBh
0x180023d9c  mov     r14d, 800000h
0x180023da2  jmp     short loc_180023DCA
0x180023da4  mov     r8d, 4
0x180023daa  mov     rdx, [rbp+2F0h+UrlComponents.lpszScheme]
0x180023dae  lea     rcx, aHttp; "http"
0x180023db5  call    cs:__imp__o__wcsnicmp
0x180023dbb  test    eax, eax
0x180023dbd  jnz     loc_18002473B
0x180023dc3  lea     r15d, [rax+50h]
0x180023dc7  xor     r14d, r14d
0x180023dca  xorps   xmm0, xmm0
0x180023dcd  movups  xmmword ptr [rbp+2F0h+var_290], xmm0
0x180023dd1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180023dd9  movdqu  [rbp+2F0h+var_280], xmm1
0x180023dde  xor     eax, eax
0x180023de0  mov     [rbp+2F0h+var_290], ax
0x180023de4  movups  xmmword ptr [rsp+3F0h+pv], xmm0
0x180023de9  mov     [rbp+2F0h+var_370], rax
0x180023ded  mov     [rbp+2F0h+var_368], rax
0x180023df1  mov     r8, [rdi+10h]
0x180023df5  cmp     qword ptr [rdi+18h], 7
0x180023dfa  jbe     short loc_180023DFF
0x180023dfc  mov     rdi, [rdi]
0x180023dff  mov     rdx, rdi
0x180023e02  lea     rcx, [rsp+3F0h+pv]
0x180023e07  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180023e0c  lea     r8, [rbp+2F0h+var_290]
0x180023e10  lea     rdx, [rsp+3F0h+pv]
0x180023e15  call    ?AcquireMsaTicketWithRetry@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::AcquireMsaTicketWithRetry(std::wstring,std::wstring &)
0x180023e1a  mov     ebx, eax
0x180023e1c  test    eax, eax
0x180023e1e  jns     short loc_180023E40
0x180023e20  mov     rcx, [rbp+2F8h]; this
0x180023e27  mov     r9d, eax; char *
0x180023e2a  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180023e31  mov     edx, 14Bh; void *
0x180023e36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023e3b  jmp     loc_180024621
0x180023e40  mov     [rsp+3F0h+var_388], 0
0x180023e49  lea     rcx, [rsp+3F0h+var_388]
0x180023e4e  call    ?GetRemediationData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@W4HardwareComponentsCacheType@234@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetRemediationData(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::Windows::Autopilot::HardwareComponentsCacheType)
0x180023e53  mov     ebx, eax
0x180023e55  test    eax, eax
0x180023e57  jns     short loc_180023E91
0x180023e59  mov     rcx, [rbp+2F8h]; this
0x180023e60  mov     r9d, eax; char *
0x180023e63  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180023e6a  mov     edx, 14Fh; void *
0x180023e6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023e74  nop
0x180023e75  mov     rcx, [rsp+3F0h+var_388]
0x180023e7a  test    rcx, rcx
0x180023e7d  jz      short loc_180023E8C
0x180023e7f  mov     rax, [rcx]
0x180023e82  mov     rax, [rax+10h]
0x180023e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e8b  nop
0x180023e8c  jmp     loc_180024621
0x180023e91  xorps   xmm0, xmm0
0x180023e94  movups  [rbp+2F0h+var_2F0], xmm0
0x180023e98  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180023ea0  movdqu  [rbp+2F0h+var_2E0], xmm1
0x180023ea5  mov     byte ptr [rbp+2F0h+var_2F0], 0
0x180023ea9  lea     rdx, [rbp+2F0h+var_2F0]
0x180023ead  mov     rbx, [rsp+3F0h+var_388]
0x180023eb2  mov     rcx, rbx
0x180023eb5  call    ?ToMbcsB64String@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Windows::Autopilot::JsonHelpers::ToMbcsB64String(Windows::Data::Json::IJsonObject *,std::string &)
0x180023eba  mov     edi, eax
0x180023ebc  xor     ecx, ecx
0x180023ebe  test    eax, eax
0x180023ec0  jns     short loc_180023F04
0x180023ec2  mov     rcx, [rbp+2F8h]; this
0x180023ec9  mov     r9d, eax; char *
0x180023ecc  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180023ed3  mov     edx, 153h; void *
0x180023ed8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023edd  nop
0x180023ede  lea     rcx, [rbp+2F0h+var_2F0]
0x180023ee2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180023ee7  nop
0x180023ee8  test    rbx, rbx
0x180023eeb  jz      short loc_180023EFD
0x180023eed  mov     rax, [rbx]
0x180023ef0  mov     rcx, rbx
0x180023ef3  mov     rax, [rax+10h]
0x180023ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023efc  nop
0x180023efd  mov     ebx, edi
0x180023eff  jmp     loc_180024621
0x180023f04  mov     [rsp+3F0h+var_398], ecx
0x180023f08  mov     [rsp+3F0h+lpMem], rcx
0x180023f0d  lea     rax, [rsp+3F0h+lpMem]
0x180023f12  mov     [rsp+3F0h+pv], rax
0x180023f17  mov     [rsp+3F0h+pv+8], rcx
0x180023f1c  mov     byte ptr [rbp+2F0h+var_370], 1
0x180023f20  lea     rcx, [rbp+2F0h+var_2F0]
0x180023f24  cmp     qword ptr [rbp+2F0h+var_2E0+8], 0Fh
0x180023f29  cmova   rcx, qword ptr [rbp+2F0h+var_2F0]
0x180023f2e  lea     r9, [rsp+3F0h+var_398]
0x180023f33  lea     r8, [rsp+3F0h+pv+8]
0x180023f38  mov     edx, 0FDE9h
0x180023f3d  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x180023f43  mov     edi, eax
0x180023f45  cmp     byte ptr [rbp+2F0h+var_370], 0
0x180023f49  jz      short loc_180023F79
0x180023f4b  mov     rdx, [rsp+3F0h+pv]
0x180023f50  mov     rsi, [rdx]
0x180023f53  mov     rcx, [rsp+3F0h+pv+8]
0x180023f58  mov     [rdx], rcx
0x180023f5b  test    rsi, rsi
0x180023f5e  jz      short loc_180023F74
0x180023f60  call    cs:__imp_GetProcessHeap
0x180023f66  mov     rcx, rax; hHeap
0x180023f69  mov     r8, rsi; lpMem
0x180023f6c  xor     edx, edx; dwFlags
0x180023f6e  call    cs:__imp_HeapFree
0x180023f74  mov     rsi, [rsp+3F0h+var_3A0]
0x180023f79  test    edi, edi
0x180023f7b  jns     short loc_180023FE5
0x180023f7d  mov     rcx, [rbp+2F8h]; this
0x180023f84  mov     r9d, edi; char *
0x180023f87  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x180023f8e  mov     edx, 158h; void *
0x180023f93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023f98  nop
0x180023f99  mov     rsi, [rsp+3F0h+lpMem]
0x180023f9e  mov     [rsp+3F0h+lpMem], 0
0x180023fa7  test    rsi, rsi
0x180023faa  jz      short loc_180023FC1
0x180023fac  call    cs:__imp_GetProcessHeap
0x180023fb2  mov     rcx, rax; hHeap
0x180023fb5  mov     r8, rsi; lpMem
0x180023fb8  xor     edx, edx; dwFlags
0x180023fba  call    cs:__imp_HeapFree
0x180023fc0  nop
0x180023fc1  lea     rcx, [rbp+2F0h+var_2F0]
0x180023fc5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180023fca  nop
0x180023fcb  test    rbx, rbx
0x180023fce  jz      short loc_180023FE0
0x180023fd0  mov     rax, [rbx]
0x180023fd3  mov     rcx, rbx
0x180023fd6  mov     rax, [rax+10h]
0x180023fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fdf  nop
0x180023fe0  jmp     loc_180023EFD
0x180023fe5  xorps   xmm0, xmm0
0x180023fe8  movups  xmmword ptr [rbp+2F0h+var_2D0], xmm0
0x180023fec  xorps   xmm1, xmm1
0x180023fef  movdqu  [rbp+2F0h+var_2C0], xmm1
0x180023ff4  mov     r8d, [rsp+3F0h+var_398]
0x180023ff9  dec     r8d
0x180023ffc  mov     rdx, [rsp+3F0h+lpMem]
0x180024001  lea     rcx, [rbp+2F0h+var_2D0]
0x180024005  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002400a  nop
0x18002400b  movzx   r8d, r15w; unsigned __int16
0x18002400f  lea     rdx, [rbp+2F0h+var_250]; unsigned __int16 *
0x180024016  mov     rcx, r13; this
0x180024019  call    ?ConnectToServer@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGGQEBUTimeoutOverride@1234@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::ConnectToServer(ushort const *,ushort,Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride const * const)
0x18002401e  mov     edi, eax
0x180024020  mov     ecx, eax; int
0x180024022  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x180024027  xor     r15d, r15d
0x18002402a  test    al, al
0x18002402c  jz      short loc_180024068
0x18002402e  lea     rcx, [rbp+2F0h+var_2D0]
0x180024032  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024037  nop
0x180024038  mov     rsi, [rsp+3F0h+lpMem]
0x18002403d  mov     [rsp+3F0h+lpMem], r15
0x180024042  test    rsi, rsi
0x180024045  jz      short loc_18002405C
0x180024047  call    cs:__imp_GetProcessHeap
0x18002404d  mov     rcx, rax; hHeap
0x180024050  mov     r8, rsi; lpMem
0x180024053  xor     edx, edx; dwFlags
0x180024055  call    cs:__imp_HeapFree
0x18002405b  nop
0x18002405c  lea     rcx, [rbp+2F0h+var_2F0]
0x180024060  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180024065  nop
0x180024066  jmp     short loc_1800240C0
0x180024068  test    edi, edi
0x18002406a  jns     short loc_1800240DA
0x18002406c  mov     rcx, [rbp+2F8h]; this
0x180024073  mov     r9d, edi; char *
0x180024076  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002407d  mov     edx, 15Eh; void *
0x180024082  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024087  nop
0x180024088  lea     rcx, [rbp+2F0h+var_2D0]
0x18002408c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024091  nop
0x180024092  mov     rsi, [rsp+3F0h+lpMem]
0x180024097  mov     [rsp+3F0h+lpMem], r15
0x18002409c  test    rsi, rsi
0x18002409f  jz      short loc_1800240B6
0x1800240a1  call    cs:__imp_GetProcessHeap
0x1800240a7  mov     rcx, rax; hHeap
0x1800240aa  mov     r8, rsi; lpMem
0x1800240ad  xor     edx, edx; dwFlags
0x1800240af  call    cs:__imp_HeapFree
0x1800240b5  nop
0x1800240b6  lea     rcx, [rbp+2F0h+var_2F0]
0x1800240ba  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800240bf  nop
0x1800240c0  test    rbx, rbx
0x1800240c3  jz      short loc_1800240D5
0x1800240c5  mov     rax, [rbx]
0x1800240c8  mov     rcx, rbx
0x1800240cb  mov     rax, [rax+10h]
0x1800240cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240d4  nop
0x1800240d5  jmp     loc_180023EFD
0x1800240da  lea     rax, [rbp+2F0h+var_2D0]
0x1800240de  mov     [rsp+3F0h+var_3C8], rax; unsigned __int16 *
0x1800240e3  mov     [rsp+3F0h+var_3D0], rsi; int
0x1800240e8  lea     r9, [rbp+2F0h+var_290]; unsigned __int16 *
0x1800240ec  mov     r8d, r14d; dwFlags
0x1800240ef  mov     rdx, [rbp+2F0h+UrlComponents.lpszUrlPath]; pwszObjectName
0x1800240f3  mov     rcx, r13; this
0x1800240f6  call    ?SendRemediationRequest@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAJPEBGKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::SendRemediationRequest(ushort const *,ulong,std::wstring const &,std::wstring const &,std::wstring const &,std::map<std::wstring,std::wstring> const *)
0x1800240fb  mov     edi, eax
0x1800240fd  mov     ecx, eax; int
0x1800240ff  call    ?IsExpectedAcquireError@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SA_NJ@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(long)
0x180024104  test    al, al
0x180024106  jz      short loc_180024142
0x180024108  lea     rcx, [rbp+2F0h+var_2D0]
0x18002410c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024111  nop
0x180024112  mov     rsi, [rsp+3F0h+lpMem]
0x180024117  mov     [rsp+3F0h+lpMem], r15
0x18002411c  test    rsi, rsi
0x18002411f  jz      short loc_180024136
0x180024121  call    cs:__imp_GetProcessHeap
0x180024127  mov     rcx, rax; hHeap
0x18002412a  mov     r8, rsi; lpMem
0x18002412d  xor     edx, edx; dwFlags
0x18002412f  call    cs:__imp_HeapFree
0x180024135  nop
0x180024136  lea     rcx, [rbp+2F0h+var_2F0]
  ... truncated ...
```
