# _lambda_c6f1c6a9ddf4305a8f4b0f277ad85766_::operator()

- ea: `0x1800a1398`
- end: `0x1800a1953`
- name: `_lambda_c6f1c6a9ddf4305a8f4b0f277ad85766_::operator()`
- size: `1467`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800be900`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001c414`
- `0x180036e6c`
- `0x180037200`
- `0x180042b9c`
- `0x1800453bc`
- `0x180045588`
- `0x18006cc00`
- `0x18006d484`
- `0x1800724a4`
- `0x180082af0`
- `0x180084d64`
- `0x18008c1e0`
- `0x18008fc28`
- `0x1800a1398`
- `0x1800a7390`
- `0x1800a7afc`
- `0x1800a86bc`
- `0x1800ac030`
- `0x1800accbc`
- `0x1800ad5e8`
- `0x1800c13a0`
- `0x1800c893c`
- `0x1800cd008`
- `0x1800d2100`
- `0x18012e1f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1405`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a143e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1723`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1405`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a143e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1723`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a14b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a18a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a14b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a18a6`

## string_xrefs

- `0x1800a1904`: `onecoreuap\enduser\winstore\installservice\lib\appinstallcontrol.cpp`
- `0x1800a18f7`: `Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallAsync::<lambda_c6f1c6a9ddf4305a8f4b0f277ad85766>::operator ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall lambda_c6f1c6a9ddf4305a8f4b0f277ad85766_::operator()(_QWORD *a1, __int64 a2)
{
  int AppData; // r15d
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v5; // rcx
  _QWORD *v6; // r12
  AppId *v7; // rbx
  unsigned int ExtendedStoreId; // eax
  int InstallControl2; // ebx
  const unsigned __int16 *StringRawBuffer; // rax
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v11; // rbx
  struct WindowsUpdate::Internal::IInstallItem **v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // eax
  Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *v15; // rbx
  TraceLoggingCorrelationVector **v16; // rsi
  struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *v17; // rdx
  unsigned __int8 v18; // r9
  unsigned int InstallFlags; // r15d
  HSTRING v20; // rbx
  const char *v21; // r9
  PCWSTR v22; // rsi
  PCWSTR v23; // rdi
  PCWSTR v24; // rbx
  __int64 v25; // rax
  char v27; // [rsp+38h] [rbp-250h]
  bool v28; // [rsp+70h] [rbp-218h] BYREF
  bool v29; // [rsp+71h] [rbp-217h] BYREF
  HSTRING string; // [rsp+78h] [rbp-210h] BYREF
  int v31; // [rsp+80h] [rbp-208h] BYREF
  struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *v32; // [rsp+88h] [rbp-200h] BYREF
  char v33[8]; // [rsp+90h] [rbp-1F8h] BYREF
  TraceLoggingCorrelationVector **v34; // [rsp+98h] [rbp-1F0h]
  _QWORD *v35; // [rsp+A0h] [rbp-1E8h]
  char v36[8]; // [rsp+A8h] [rbp-1E0h] BYREF
  char v37[8]; // [rsp+B0h] [rbp-1D8h] BYREF
  __int64 v38; // [rsp+B8h] [rbp-1D0h] BYREF
  __int128 v39; // [rsp+C0h] [rbp-1C8h]
  HSTRING v40; // [rsp+D8h] [rbp-1B0h] BYREF
  char v41[8]; // [rsp+E0h] [rbp-1A8h] BYREF
  char v42[8]; // [rsp+E8h] [rbp-1A0h] BYREF
  char v43[8]; // [rsp+F0h] [rbp-198h] BYREF
  char v44[8]; // [rsp+F8h] [rbp-190h] BYREF
  HSTRING v45; // [rsp+100h] [rbp-188h]
  char v46[8]; // [rsp+108h] [rbp-180h] BYREF
  HSTRING v47; // [rsp+110h] [rbp-178h]
  const winrt::hresult_error *v48; // [rsp+118h] [rbp-170h] BYREF
  __int64 v49[4]; // [rsp+120h] [rbp-168h] BYREF
  __int64 v50[4]; // [rsp+140h] [rbp-148h] BYREF
  _BYTE v51[32]; // [rsp+160h] [rbp-128h] BYREF
  __int64 v52; // [rsp+180h] [rbp-108h] BYREF
  __int64 v53; // [rsp+1A0h] [rbp-E8h] BYREF
  char v54[144]; // [rsp+1C0h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  v34 = (TraceLoggingCorrelationVector **)a1;
  wil::impersonate_token(v46, a1[4]);
  AppData = 0;
  if ( Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(v5) )
  {
    v45 = (HSTRING)a1[6];
    WindowsDeleteString(0);
    v47 = v45;
    string = 0;
    LODWORD(v38) = 0;
    v39 = 0;
    v6 = a1 + 2;
    v35 = a1 + 2;
    v7 = (AppId *)a1[2];
    WindowsDeleteString(0);
    string = 0;
    ExtendedStoreId = AppId::get_ExtendedStoreId(v7, &string);
    try
    {
      winrt::check_hresult(&v31, ExtendedStoreId, &v38);
      InstallControl2 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(
                          *a1,
                          v33);
      v38 = *(_QWORD *)PluginHelpers::EmptyPropertiesJson(v44);
      ToWinRTType<HSTRING__ *>(v36, a1 + 6);
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(*v6 + 80LL), 0);
      winrt::hstring::hstring((winrt::hstring *)&v31, StringRawBuffer);
      v28 = *((_BYTE *)a1 + 26) != 0;
      v29 = *((_BYTE *)a1 + 25) != 0;
      v49[0] = *(_QWORD *)PluginHelpers::CreatePropertiesJson<PluginHelpers::WorkProperty::IsInteractive,PluginHelpers::WorkProperty::AllowDownloadOnAnyNetwork,PluginHelpers::WorkProperty::CatalogId,PluginHelpers::WorkProperty::CallerApplicationId>(
                            (unsigned int)v43,
                            (unsigned int)&v29,
                            (unsigned int)&v28,
                            (unsigned int)&v31,
                            (__int64)v36);
      v40 = string;
      v50[0] = *(_QWORD *)ToWinRTType<HSTRING__ *>(v42, &v40);
      winrt::param::hstring::hstring((winrt::param::hstring *)v51, L"StoreId");
      v52 = 0;
      v16 = (TraceLoggingCorrelationVector **)(a1 + 5);
      v53 = *(_QWORD *)GetCvString(v41, a1[5]);
      winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::CreateInstallServiceWork(
        InstallControl2,
        (unsigned int)v37,
        (unsigned int)&v53,
        (unsigned int)&v52,
        (__int64)v51,
        (__int64)v50,
        (__int64)v49,
        (__int64)&v38);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v41);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v42);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v43);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v31);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v36);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v44);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v33);
      v32 = 0;
      LODWORD(v38) = 0;
      v39 = 0;
      v11 = (Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *)*a1;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
      v12 = (struct WindowsUpdate::Internal::IInstallItem **)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUpdate::Internal::InstallItem>,winrt::WindowsUpdate::Internal::InstallItem>::GetAt(
                                                               v37,
                                                               v33,
                                                               0);
      v13 = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::FindOrCreateInstallItem(
              v11,
              *v12,
              &v32);
      winrt::check_hresult(&v31, v13, &v38);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v33);
      LODWORD(v38) = 0;
      v39 = 0;
      v14 = Windows::Internal::CMarshaledInterfaceResult<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::Set(
              a2,
              v32);
      winrt::check_hresult(&v31, v14, &v38);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v37);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v45);
    }
    catch ( const winrt::hresult_error *v48 )
    {
      v31 = *((_DWORD *)v48 + 3);
      v16 = v34 + 5;
      AppData = v31;
      v6 = v35;
    }
  }
  else
  {
    string = 0;
    v15 = (Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl *)*a1;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
    v16 = (TraceLoggingCorrelationVector **)(a1 + 5);
    v34 = (TraceLoggingCorrelationVector **)(a1 + 5);
    v6 = a1 + 2;
    v35 = a1 + 2;
    AppData = Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::GetAppData(
                v15,
                0,
                (struct AppId *)a1[2],
                (struct TraceLoggingCorrelationVector *)a1[5],
                (struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData **)&string);
    if ( AppData >= 0 )
    {
      try
      {
        LOBYTE(v17) = *((_BYTE *)a1 + 25);
        InstallFlags = Utils::GetInstallFlags(0, v17, *((_BYTE *)a1 + 26), v18);
        v32 = 0;
        v20 = string;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
        v27 = 1;
        AppData = Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::_StartInstallForUser(
                    v20,
                    0,
                    *((_BYTE *)a1 + 24) != 0 ? 2 : 0,
                    InstallFlags,
                    0,
                    0,
                    *v16,
                    v27,
                    &v32);
        if ( AppData >= 0 )
          AppData = Windows::Internal::CMarshaledInterfaceResult<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::Set(
                      a2,
                      v32);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
      }
      catch ( ... )
      {
        v31 = wil::details::in1diag3::Log_CaughtException(
                retaddr,
                (void *)0x64E,
                (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
                v21);
        AppData = v31;
        v6 = v35;
        v16 = v34;
      }
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
  }
  TraceLoggingCorrelationVector::ToStringImpl(
    *v16,
    _InterlockedExchangeAdd64((volatile signed __int64 *)*v16 + 17, 0),
    v54);
  v22 = WindowsGetStringRawBuffer(*(HSTRING *)(*v6 + 88LL), 0);
  v23 = WindowsGetStringRawBuffer(*(HSTRING *)(*v6 + 80LL), 0);
  v24 = WindowsGetStringRawBuffer(*(HSTRING *)(*v6 + 64LL), 0);
  v25 = AppId::IdTypeName(*(unsigned int *)(*v6 + 56LL));
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\appinstallcontrol.cpp",
    0x65Au,
    "Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::StartAppInstallAsync::<lambda_c6f1"
    "c6a9ddf4305a8f4b0f277ad85766>::operator ()",
    AppData,
    L"%s = %s, catalogId = %s, flightId  = %s, CV = %hs",
    0,
    0,
    v25,
    v24,
    v23,
    v22,
    v54);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v46);
  return (unsigned int)AppData;
}

```

## disassembly

```asm
0x1800a1398  mov     [rsp+arg_10], rbx
0x1800a139d  mov     [rsp+arg_18], rsi
0x1800a13a2  push    rdi
0x1800a13a3  push    r12
0x1800a13a5  push    r13
0x1800a13a7  push    r14
0x1800a13a9  push    r15
0x1800a13ab  sub     rsp, 260h
0x1800a13b2  mov     rax, cs:__security_cookie
0x1800a13b9  xor     rax, rsp
0x1800a13bc  mov     [rsp+288h+var_38], rax
0x1800a13c4  mov     r13, rdx
0x1800a13c7  mov     rdi, rcx
0x1800a13ca  mov     [rsp+288h+var_1F0], rcx
0x1800a13d2  mov     rdx, [rcx+20h]
0x1800a13d6  lea     rcx, [rsp+288h+var_180]
0x1800a13de  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x1800a13e3  nop
0x1800a13e4  xor     r14d, r14d
0x1800a13e7  mov     r15d, r14d
0x1800a13ea  call    ?_ShouldUseInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA_NXZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_ShouldUseInstallControl2(void)
0x1800a13ef  test    al, al
0x1800a13f1  jz      loc_1800A1753
0x1800a13f7  mov     rbx, [rdi+30h]
0x1800a13fb  mov     [rsp+288h+var_188], rbx
0x1800a1403  xor     ecx, ecx; string
0x1800a1405  call    cs:__imp_WindowsDeleteString
0x1800a140b  mov     [rsp+288h+var_178], rbx
0x1800a1413  mov     [rsp+288h+string], r14
0x1800a1418  mov     dword ptr [rsp+288h+var_1D0], r14d
0x1800a1420  xorps   xmm0, xmm0
0x1800a1423  movdqu  [rsp+288h+var_1C8], xmm0
0x1800a142c  lea     r12, [rdi+10h]
0x1800a1430  mov     [rsp+288h+var_1E8], r12
0x1800a1438  mov     rbx, [r12]
0x1800a143c  xor     ecx, ecx; string
0x1800a143e  call    cs:__imp_WindowsDeleteString
0x1800a1444  mov     [rsp+288h+string], r14
0x1800a1449  lea     rdx, [rsp+288h+string]; HSTRING *
0x1800a144e  mov     rcx, rbx; this
0x1800a1451  call    ?get_ExtendedStoreId@AppId@@QEBAJPEAPEAUHSTRING__@@@Z; AppId::get_ExtendedStoreId(HSTRING__ * *)
0x1800a1456  lea     r8, [rsp+288h+var_1D0]
0x1800a145e  mov     edx, eax
0x1800a1460  lea     rcx, [rsp+288h+var_208]
0x1800a1468  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800a146d  lea     rdx, [rsp+288h+var_1F8]
0x1800a1475  mov     rcx, [rdi]
0x1800a1478  call    ?_GetInstallControl2@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAA?AUInstallServiceControl@Control@InstallService@Internal@6winrt@@XZ; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::_GetInstallControl2(void)
0x1800a147d  mov     rbx, rax
0x1800a1480  lea     rcx, [rsp+288h+var_190]
0x1800a1488  call    ?EmptyPropertiesJson@PluginHelpers@@YA?AUhstring@winrt@@XZ; PluginHelpers::EmptyPropertiesJson(void)
0x1800a148d  nop
0x1800a148e  mov     rcx, [rax]
0x1800a1491  mov     [rsp+288h+var_1D0], rcx
0x1800a1499  lea     rdx, [rdi+30h]
0x1800a149d  lea     rcx, [rsp+288h+var_1E0]
0x1800a14a5  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800a14aa  nop
0x1800a14ab  mov     rcx, [r12]
0x1800a14af  xor     edx, edx; length
0x1800a14b1  mov     rcx, [rcx+50h]; string
0x1800a14b5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a14bb  mov     rdx, rax; unsigned __int16 *
0x1800a14be  lea     rcx, [rsp+288h+var_208]; this
0x1800a14c6  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800a14cb  nop
0x1800a14cc  cmp     [rdi+1Ah], r14b
0x1800a14d0  setnz   [rsp+288h+var_218]
0x1800a14d5  cmp     [rdi+19h], r14b
0x1800a14d9  setnz   [rsp+288h+var_217]
0x1800a14de  lea     rax, [rsp+288h+var_1E0]
0x1800a14e6  mov     [rsp+288h+var_268], rax
0x1800a14eb  lea     r9, [rsp+288h+var_208]
0x1800a14f3  lea     r8, [rsp+288h+var_218]
0x1800a14f8  lea     rdx, [rsp+288h+var_217]
0x1800a14fd  lea     rcx, [rsp+288h+var_198]
0x1800a1505  call    ??$CreatePropertiesJson@UIsInteractive@WorkProperty@PluginHelpers@@UAllowDownloadOnAnyNetwork@23@UCatalogId@23@UCallerApplicationId@23@@PluginHelpers@@YA?AUhstring@winrt@@$$QEAUIsInteractive@WorkProperty@0@$$QEAUAllowDownloadOnAnyNetwork@40@$$QEAUCatalogId@40@$$QEAUCallerApplicationId@40@@Z; PluginHelpers::CreatePropertiesJson<PluginHelpers::WorkProperty::IsInteractive,PluginHelpers::WorkProperty::AllowDownloadOnAnyNetwork,PluginHelpers::WorkProperty::CatalogId,PluginHelpers::WorkProperty::CallerApplicationId>(PluginHelpers::WorkProperty::IsInteractive &&,PluginHelpers::WorkProperty::AllowDownloadOnAnyNetwork &&,PluginHelpers::WorkProperty::CatalogId &&,PluginHelpers::WorkProperty::CallerApplicationId &&)
0x1800a150a  nop
0x1800a150b  mov     rax, [rax]
0x1800a150e  mov     [rsp+288h+var_168], rax
0x1800a1516  mov     rax, [rsp+288h+string]
0x1800a151b  mov     [rsp+288h+var_1B0], rax
0x1800a1523  lea     rdx, [rsp+288h+var_1B0]
0x1800a152b  lea     rcx, [rsp+288h+var_1A0]
0x1800a1533  call    ??$ToWinRTType@PEAUHSTRING__@@@@YA?A_PAEBQEAUHSTRING__@@@Z
0x1800a1538  nop
0x1800a1539  mov     rax, [rax]
0x1800a153c  mov     [rsp+288h+var_148], rax
0x1800a1544  lea     rdx, aStoreid_0; "StoreId"
0x1800a154b  lea     rcx, [rsp+288h+var_128]; this
0x1800a1553  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800a1558  mov     [rsp+288h+var_108], r14
0x1800a1560  lea     rsi, [rdi+28h]
0x1800a1564  mov     rdx, [rsi]
0x1800a1567  lea     rcx, [rsp+288h+var_1A8]
0x1800a156f  call    ?GetCvString@@YA?AUhstring@winrt@@PEAVTraceLoggingCorrelationVector@@@Z; GetCvString(TraceLoggingCorrelationVector *)
0x1800a1574  nop
0x1800a1575  mov     rax, [rax]
0x1800a1578  mov     [rsp+288h+var_E8], rax
0x1800a1580  lea     rax, [rsp+288h+var_1D0]
0x1800a1588  mov     [rsp+288h+var_250], rax
0x1800a158d  lea     rax, [rsp+288h+var_168]
0x1800a1595  mov     [rsp+288h+var_258], rax
0x1800a159a  lea     rax, [rsp+288h+var_148]
0x1800a15a2  mov     [rsp+288h+var_260], rax
0x1800a15a7  lea     rax, [rsp+288h+var_128]
0x1800a15af  mov     [rsp+288h+var_268], rax
0x1800a15b4  lea     r9, [rsp+288h+var_108]
0x1800a15bc  lea     r8, [rsp+288h+var_E8]
0x1800a15c4  lea     rdx, [rsp+288h+var_1D8]
0x1800a15cc  mov     rcx, rbx
0x1800a15cf  call    ?CreateInstallServiceWork@?$consume_Windows_Internal_InstallService_Control_IInstallServiceControl@UIInstallServiceControl@Control@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@00000@Z; winrt::impl::consume_Windows_Internal_InstallService_Control_IInstallServiceControl<winrt::Windows::Internal::InstallService::Control::IInstallServiceControl>::CreateInstallServiceWork(winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x1800a15d4  nop
0x1800a15d5  lea     rcx, [rsp+288h+var_1A8]
0x1800a15dd  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a15e2  nop
0x1800a15e3  lea     rcx, [rsp+288h+var_1A0]
0x1800a15eb  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a15f0  nop
0x1800a15f1  lea     rcx, [rsp+288h+var_198]
0x1800a15f9  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a15fe  nop
0x1800a15ff  lea     rcx, [rsp+288h+var_208]
0x1800a1607  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a160c  nop
0x1800a160d  lea     rcx, [rsp+288h+var_1E0]
0x1800a1615  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a161a  nop
0x1800a161b  lea     rcx, [rsp+288h+var_190]
0x1800a1623  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800a1628  nop
0x1800a1629  lea     rcx, [rsp+288h+var_1F8]; void *
0x1800a1631  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800a1636  mov     [rsp+288h+var_200], r14
0x1800a163e  mov     dword ptr [rsp+288h+var_1D0], r14d
0x1800a1646  xorps   xmm0, xmm0
0x1800a1649  movdqu  [rsp+288h+var_1C8], xmm0
0x1800a1652  mov     rbx, [rdi]
0x1800a1655  lea     rcx, [rsp+288h+var_200]
0x1800a165d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800a1662  xor     r8d, r8d
0x1800a1665  lea     rdx, [rsp+288h+var_1F8]
0x1800a166d  lea     rcx, [rsp+288h+var_1D8]
0x1800a1675  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UInstallItem@Internal@WindowsUpdate@winrt@@@Collections@Foundation@Windows@winrt@@UInstallItem@Internal@WindowsUpdate@5@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::WindowsUpdate::Internal::InstallItem>,winrt::WindowsUpdate::Internal::InstallItem>::GetAt(uint)
0x1800a167a  nop
0x1800a167b  lea     r8, [rsp+288h+var_200]; struct Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem **
0x1800a1683  mov     rdx, [rax]; struct WindowsUpdate::Internal::IInstallItem *
0x1800a1686  mov     rcx, rbx; this
0x1800a1689  call    ?FindOrCreateInstallItem@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@QEAAJPEAUIInstallItem@Internal@WindowsUpdate@@PEAPEAVAppInstallItem@23456@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::FindOrCreateInstallItem(WindowsUpdate::Internal::IInstallItem *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem * *)
0x1800a168e  lea     r8, [rsp+288h+var_1D0]
0x1800a1696  mov     edx, eax
0x1800a1698  lea     rcx, [rsp+288h+var_208]
0x1800a16a0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800a16a5  nop
0x1800a16a6  lea     rcx, [rsp+288h+var_1F8]; void *
0x1800a16ae  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800a16b3  mov     dword ptr [rsp+288h+var_1D0], r14d
0x1800a16bb  xorps   xmm0, xmm0
0x1800a16be  movdqu  [rsp+288h+var_1C8], xmm0
0x1800a16c7  mov     rdx, [rsp+288h+var_200]
0x1800a16cf  mov     rcx, r13
0x1800a16d2  call    ?Set@?$CMarshaledInterfaceResult@UIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Internal@Windows@@QEAAJPEAUIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@3@@Z; Windows::Internal::CMarshaledInterfaceResult<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::Set(Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *)
0x1800a16d7  lea     r8, [rsp+288h+var_1D0]
0x1800a16df  mov     edx, eax
0x1800a16e1  lea     rcx, [rsp+288h+var_208]
0x1800a16e9  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800a16ee  nop
0x1800a16ef  lea     rcx, [rsp+288h+var_200]
0x1800a16f7  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800a16fc  nop
0x1800a16fd  lea     rcx, [rsp+288h+var_1D8]; void *
0x1800a1705  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800a170a  nop
0x1800a170b  mov     rcx, [rsp+288h+string]; string
0x1800a1710  call    cs:__imp_WindowsDeleteString
0x1800a1716  mov     [rsp+288h+string], r14
0x1800a171b  mov     rcx, [rsp+288h+var_188]; string
0x1800a1723  call    cs:__imp_WindowsDeleteString
0x1800a1729  nop
0x1800a172a  jmp     loc_1800A185A
0x1800a172f  mov     rsi, [rsp+288h+var_1F0]
0x1800a1737  add     rsi, 28h ; '('
0x1800a173b  xor     r14d, r14d
0x1800a173e  mov     r15d, [rsp+288h+var_208]
0x1800a1746  mov     r12, [rsp+288h+var_1E8]
0x1800a174e  jmp     loc_1800A185A
0x1800a1753  mov     [rsp+288h+string], r14
0x1800a1758  mov     rbx, [rdi]
0x1800a175b  lea     rcx, [rsp+288h+string]
0x1800a1760  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800a1765  lea     rsi, [rdi+28h]
0x1800a1769  mov     [rsp+288h+var_1F0], rsi
0x1800a1771  lea     r12, [rdi+10h]
0x1800a1775  mov     [rsp+288h+var_1E8], r12
0x1800a177d  lea     rax, [rsp+288h+string]
0x1800a1782  mov     [rsp+288h+var_268], rax; struct Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData **
0x1800a1787  mov     r9, [rsi]; struct TraceLoggingCorrelationVector *
0x1800a178a  mov     r8, [r12]; struct AppId *
0x1800a178e  xor     edx, edx; struct Windows::System::IUser *
0x1800a1790  mov     rcx, rbx; this
0x1800a1793  call    ?GetAppData@AppInstallManagerImpl@InstallControl@Preview@Store@ApplicationModel@Windows@@QEAAJPEAUIUser@System@6@PEAVAppId@@PEAVTraceLoggingCorrelationVector@@PEAPEAVAppData@Internal@23456@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl::GetAppData(Windows::System::IUser *,AppId *,TraceLoggingCorrelationVector *,Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData * *)
0x1800a1798  mov     r15d, eax
0x1800a179b  test    eax, eax
0x1800a179d  js      loc_1800A1850
0x1800a17a3  mov     r8b, [rdi+1Ah]; unsigned __int8
0x1800a17a7  mov     dl, [rdi+19h]; struct Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *
0x1800a17aa  xor     ecx, ecx; this
0x1800a17ac  call    ?GetInstallFlags@Utils@@YAKPEAUIAppInstallOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@EE@Z; Utils::GetInstallFlags(Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallOptions *,uchar,uchar)
0x1800a17b1  mov     r15d, eax
0x1800a17b4  mov     [rsp+288h+var_200], r14
0x1800a17bc  mov     rbx, [rsp+288h+string]
0x1800a17c1  lea     rcx, [rsp+288h+var_200]
0x1800a17c9  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800a17ce  mov     dl, [rdi+18h]
0x1800a17d1  neg     dl
0x1800a17d3  sbb     r8d, r8d
0x1800a17d6  and     r8d, 2
0x1800a17da  lea     rax, [rsp+288h+var_200]
0x1800a17e2  mov     [rsp+288h+var_248], rax
0x1800a17e7  mov     byte ptr [rsp+288h+var_250], 1
0x1800a17ec  mov     rax, [rsi]
0x1800a17ef  mov     [rsp+288h+var_258], rax
0x1800a17f4  mov     [rsp+288h+var_260], r14
0x1800a17f9  mov     [rsp+288h+var_268], r14
0x1800a17fe  mov     r9d, r15d
0x1800a1801  xor     edx, edx
0x1800a1803  mov     rcx, rbx
0x1800a1806  call    ?_StartInstallForUser@AppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@AEAAJPEAUIUser@System@7@W4AppInstallType@34567@KPEAUHSTRING__@@2PEAVTraceLoggingCorrelationVector@@_NPEAPEAVAppInstallItem@34567@@Z; Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData::_StartInstallForUser(Windows::System::IUser *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallType,ulong,HSTRING__ *,HSTRING__ *,TraceLoggingCorrelationVector *,bool,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem * *)
0x1800a180b  mov     r15d, eax
0x1800a180e  test    eax, eax
0x1800a1810  js      short loc_1800A1825
0x1800a1812  mov     rdx, [rsp+288h+var_200]
0x1800a181a  mov     rcx, r13
0x1800a181d  call    ?Set@?$CMarshaledInterfaceResult@UIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@Internal@Windows@@QEAAJPEAUIAppInstallItem@InstallControl@Preview@Store@ApplicationModel@3@@Z; Windows::Internal::CMarshaledInterfaceResult<Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem>::Set(Windows::ApplicationModel::Store::Preview::InstallControl::IAppInstallItem *)
0x1800a1822  mov     r15d, eax
0x1800a1825  lea     rcx, [rsp+288h+var_200]
0x1800a182d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800a1832  nop
0x1800a1833  jmp     short loc_1800A1850
0x1800a1835  xor     r14d, r14d
0x1800a1838  mov     r15d, [rsp+288h+var_208]
0x1800a1840  mov     r12, [rsp+288h+var_1E8]
0x1800a1848  mov     rsi, [rsp+288h+var_1F0]
0x1800a1850  lea     rcx, [rsp+288h+string]
0x1800a1855  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800a185a  mov     rcx, [rsi]; this
0x1800a185d  mov     rdx, r14
0x1800a1860  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800a1869  lea     r8, [rsp+288h+var_C8]; char *
0x1800a1871  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800a1876  mov     rcx, [r12]
0x1800a187a  xor     edx, edx; length
0x1800a187c  mov     rcx, [rcx+58h]; string
0x1800a1880  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a1886  mov     rsi, rax
0x1800a1889  mov     rcx, [r12]
0x1800a188d  xor     edx, edx; length
0x1800a188f  mov     rcx, [rcx+50h]; string
0x1800a1893  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a1899  mov     rdi, rax
0x1800a189c  mov     rcx, [r12]
0x1800a18a0  xor     edx, edx; length
0x1800a18a2  mov     rcx, [rcx+40h]; string
0x1800a18a6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a18ac  mov     rbx, rax
0x1800a18af  mov     rcx, [r12]
0x1800a18b3  mov     ecx, [rcx+38h]
0x1800a18b6  call    ?IdTypeName@AppId@@SAPEBGW4Type@1@@Z; AppId::IdTypeName(AppId::Type)
0x1800a18bb  lea     rcx, [rsp+288h+var_C8]
0x1800a18c3  mov     [rsp+288h+var_228], rcx
0x1800a18c8  mov     [rsp+288h+var_230], rsi
0x1800a18cd  mov     [rsp+288h+var_238], rdi
0x1800a18d2  mov     [rsp+288h+var_240], rbx
0x1800a18d7  mov     [rsp+288h+var_248], rax
0x1800a18dc  mov     [rsp+288h+var_250], r14; unsigned __int16 *
0x1800a18e1  mov     [rsp+288h+var_258], r14; char *
0x1800a18e6  lea     rax, aSSCatalogidSFl; "%s = %s, catalogId = %s, flightId  = %s"...
0x1800a18ed  mov     [rsp+288h+var_260], rax; unsigned __int16 *
0x1800a18f2  mov     dword ptr [rsp+288h+var_268], r15d; int
0x1800a18f7  lea     r9, aWindowsApplica_97; "Windows::ApplicationModel::Store::Previ"...
0x1800a18fe  mov     r8d, 65Ah; unsigned int
0x1800a1904  lea     rdx, aOnecoreuapEndu_39; "onecoreuap\\enduser\\winstore\\installs"...
0x1800a190b  mov     ecx, 3; unsigned int
0x1800a1910  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800a1915  nop
0x1800a1916  lea     rcx, [rsp+288h+var_180]
0x1800a191e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1800a1923  mov     eax, r15d
0x1800a1926  mov     rcx, [rsp+288h+var_38]
0x1800a192e  xor     rcx, rsp; StackCookie
0x1800a1931  call    __security_check_cookie
0x1800a1936  lea     r11, [rsp+288h+var_28]
0x1800a193e  mov     rbx, [r11+40h]
0x1800a1942  mov     rsi, [r11+48h]
0x1800a1946  mov     rsp, r11
0x1800a1949  pop     r15
0x1800a194b  pop     r14
0x1800a194d  pop     r13
0x1800a194f  pop     r12
0x1800a1951  pop     rdi
  ... truncated ...
```
