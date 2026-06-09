# Microsoft::Diagnostics::AsimovHttpClient::UploadEventBuffer(Microsoft::Diagnostics::AsimovHttpClient::UploadEventBufferHeaders const &,Microsoft::Diagnostics::NetworkCost,std::vector<gsl::byte,std::allocator<gsl::byte>> const &,ulong,Concurrency::cancellation_token,std::shared_ptr<Microsoft::Diagnostics::HttpResponse> &)

- ea: `0x18014a484`
- end: `0x18014b225`
- name: `?UploadEventBuffer@AsimovHttpClient@Diagnostics@Microsoft@@QEAAJAEBUUploadEventBufferHeaders@123@VNetworkCost@23@AEBV?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@KVcancellation_token@Concurrency@@AEAV?$shared_ptr@UHttpResponse@Diagnostics@Microsoft@@@7@@Z`
- size: `3489`
- prototype: `__int64 __fastcall(int, int, int, int, int, Concurrency::cancellation_token *, __int64)`
- caller_count: `1`
- callee_count: `41`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801498e8`

## callees

- `0x1800041a0`
- `0x18002cb04`
- `0x18002df00`
- `0x180031168`
- `0x180039e6c`
- `0x180052240`
- `0x180053ff4`
- `0x1800552d8`
- `0x180055730`
- `0x1800561a4`
- `0x180064e8c`
- `0x18006835c`
- `0x180068c58`
- `0x18008035c`
- `0x18009c8c0`
- `0x1800b5cb4`
- `0x1800ba07c`
- `0x1800ba498`
- `0x1800ba854`
- `0x1800bac64`
- `0x1800bc658`
- `0x1800cf7d8`
- `0x1800d11c0`
- `0x1800d35b4`
- `0x1800d39fc`
- `0x1800e8f80`
- `0x1800e9018`
- `0x1800f4930`
- `0x180102bbc`
- `0x180111bd4`
- `0x1801285dc`
- `0x18012d7b0`
- `0x180135914`
- `0x180142fcc`
- `0x18014a20c`
- `0x18014a484`
- `0x18014c064`
- `0x1801b2084`
- `0x18020aac0`
- `0x18024eea0`
- `0x1802fcb94`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18014ac98`
- `msvcp_win!_Mtx_unlock` at `0x18014ac98`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18014ad04`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18014ad04`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18014ad53`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18014ad53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18014a52f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18014a52f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x18014ac3b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x18014ac3b`

## string_xrefs

- `0x18014b214`: `onecore\base\telemetry\utc\include\TimedCancellationTokenSource.h`
- `0x18014a54a`: `onecore\base\telemetry\utc\service\asimov\asimovhttpclient.cpp`
- `0x18014a8a0`: `Aad-Token`
- `0x18014a7e4`: `AuthXToken`
- `0x18014a901`: `AadDeviceToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=17 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::AsimovHttpClient::UploadEventBuffer(
        __int64 a1,
        _QWORD *a2,
        char a3,
        __int64 a4,
        DWORD a5,
        Concurrency::cancellation_token *a6,
        __int64 a7)
{
  __int64 v10; // rdi
  ULONGLONG v11; // rdi
  unsigned __int64 FileTimeAsULL; // rax
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 ClientVersionString; // rax
  __int64 v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // rax
  Microsoft::Diagnostics::SystemStateManager *SystemStateManager; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  struct _Mtx_internal_imp_t *v29; // rcx
  CONTEXT *v30; // rdi
  __int64 v31; // r8
  __int64 v32; // rdi
  PTP_TIMER v33; // rax
  const char *v34; // r9
  __int64 v35; // r8
  __int128 v36; // xmm6
  __int64 v37; // rcx
  __int64 v38; // r8
  __int128 v39; // xmm7
  __int64 v40; // r8
  __int128 v41; // xmm8
  __int64 v42; // r8
  __int128 v43; // xmm9
  __int64 v44; // r8
  __int128 *v45; // rax
  __int64 v46; // r8
  char v47; // r8
  int v48; // r9d
  int v49; // edi
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  struct Microsoft::Diagnostics::SystemStateManager *v53; // rax
  __int64 v54; // r8
  const wchar_t *v55; // rcx
  const WCHAR *v56; // rcx
  int v57; // ecx
  _QWORD *v58; // rax
  __int64 v59; // rdx
  int v60; // [rsp+20h] [rbp-3A8h]
  __int128 pv; // [rsp+90h] [rbp-338h] BYREF
  int v62; // [rsp+A0h] [rbp-328h] BYREF
  bool v63; // [rsp+A4h] [rbp-324h]
  __int128 v64; // [rsp+B0h] [rbp-318h] BYREF
  _QWORD v65[2]; // [rsp+C0h] [rbp-308h] BYREF
  __int128 v66; // [rsp+D0h] [rbp-2F8h] BYREF
  int v67; // [rsp+E0h] [rbp-2E8h]
  int v68; // [rsp+E4h] [rbp-2E4h]
  int v69; // [rsp+E8h] [rbp-2E0h]
  int v70; // [rsp+ECh] [rbp-2DCh]
  __int64 v71; // [rsp+F0h] [rbp-2D8h] BYREF
  __int64 v72; // [rsp+F8h] [rbp-2D0h] BYREF
  std::_Ref_count_base *v73[2]; // [rsp+100h] [rbp-2C8h]
  struct _FILETIME pftDueTime[2]; // [rsp+110h] [rbp-2B8h] BYREF
  __int64 v75; // [rsp+120h] [rbp-2A8h]
  Concurrency::cancellation_token *v76; // [rsp+128h] [rbp-2A0h]
  __int128 v77; // [rsp+130h] [rbp-298h] BYREF
  _BYTE v78[8]; // [rsp+140h] [rbp-288h] BYREF
  char v79; // [rsp+148h] [rbp-280h] BYREF
  __int128 v80; // [rsp+160h] [rbp-268h] BYREF
  __int128 v81; // [rsp+170h] [rbp-258h] BYREF
  __int128 v82; // [rsp+180h] [rbp-248h] BYREF
  _BYTE v83[16]; // [rsp+190h] [rbp-238h] BYREF
  _BYTE v84[16]; // [rsp+1A0h] [rbp-228h] BYREF
  _BYTE v85[16]; // [rsp+1B0h] [rbp-218h] BYREF
  _BYTE v86[16]; // [rsp+1C0h] [rbp-208h] BYREF
  _BYTE v87[16]; // [rsp+1D0h] [rbp-1F8h] BYREF
  _QWORD Src[4]; // [rsp+1E0h] [rbp-1E8h] BYREF
  _OWORD v89[2]; // [rsp+200h] [rbp-1C8h] BYREF
  _BYTE v90[32]; // [rsp+220h] [rbp-1A8h] BYREF
  _BYTE v91[224]; // [rsp+240h] [rbp-188h] BYREF
  wchar_t pszDest[21]; // [rsp+320h] [rbp-A8h] BYREF
  _BYTE v93[6]; // [rsp+34Ah] [rbp-7Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+0h]

  v72 = a4;
  v76 = a6;
  v75 = a7;
  if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4096) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1804543B0,
      &byte_1803E4C27);
  v10 = 136;
  if ( a3 == 1 )
    v10 = 144;
  v11 = *(_QWORD *)(v10 + a1);
  if ( v11 <= GetTickCount64() )
  {
    std::wstring::wstring(Src, a1 + 104);
    FileTimeAsULL = Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
    v14 = std::_UIntegral_to_buff<wchar_t,unsigned __int64>(v93, FileTimeAsULL);
    std::wstring::wstring(v90, v14, v93);
    pv = *(_OWORD *)std::wstring::operator std::wstring_view(v90, &v66, v15);
    v16 = Microsoft::Diagnostics::Utils::Time::FileTimeToMillisecond8601(pszDest);
    v64 = *(_OWORD *)std::wstring::operator std::wstring_view(v16, &v77, v17);
    *(_QWORD *)&pv = L"Upload-Time";
    *((_QWORD *)&pv + 1) = 11;
    Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(Src);
    std::wstring::_Tidy_deallocate(pszDest);
    v64 = *(_OWORD *)std::wstring::operator std::wstring_view(a2 + 4, &v66, v18);
    *(_QWORD *)&pv = L"Reliability-Mode";
    *((_QWORD *)&pv + 1) = 16;
    Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(Src);
    ClientVersionString = Microsoft::Diagnostics::AsimovHttpClient::GenerateClientVersionString(pszDest);
    v64 = *(_OWORD *)std::wstring::operator std::wstring_view(ClientVersionString, &v66, v20);
    *(_QWORD *)&pv = L"Client-Version";
    *((_QWORD *)&pv + 1) = 14;
    Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(Src);
    std::wstring::_Tidy_deallocate(pszDest);
    v64 = *(_OWORD *)std::wstring::operator std::wstring_view(a2 + 8, &v66, v21);
    *(_QWORD *)&pv = L"ApiKey";
    *((_QWORD *)&pv + 1) = 6;
    Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(Src);
    if ( a2[2] )
    {
      v64 = *(_OWORD *)std::wstring::operator std::wstring_view(a2, &v66, v22);
      *(_QWORD *)&pv = L"AuthMsaDeviceTicket";
      *((_QWORD *)&pv + 1) = 19;
      Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(Src);
    }
    if ( a2[18] )
    {
      v64 = *(_OWORD *)std::wstring::operator std::wstring_view(a2 + 16, &v66, v22);
      *(_QWORD *)&pv = L"AuthXToken";
      *((_QWORD *)&pv + 1) = 10;
      Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(Src);
    }
    if ( a2[14] )
    {
      v64 = *(_OWORD *)std::wstring::operator std::wstring_view(a2 + 12, &v66, v22);
      *(_QWORD *)&pv = L"Tickets";
      *((_QWORD *)&pv + 1) = 7;
      Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(Src);
    }
    if ( a2[22] )
    {
      v64 = *(_OWORD *)std::wstring::operator std::wstring_view(a2 + 20, &v66, v22);
      *(_QWORD *)&pv = L"Aad-Token";
      *((_QWORD *)&pv + 1) = 9;
      Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(Src);
    }
    if ( a2[26] )
    {
      v64 = *(_OWORD *)std::wstring::operator std::wstring_view(a2 + 24, &v66, v22);
      *(_QWORD *)&pv = L"AadDeviceToken";
      *((_QWORD *)&pv + 1) = 14;
      Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(Src);
    }
    if ( a2[30] )
    {
      v64 = *(_OWORD *)std::wstring::operator std::wstring_view(a2 + 28, &v66, v22);
      *(_QWORD *)&pv = L"Custom-Request-Field";
      *((_QWORD *)&pv + 1) = 20;
      Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(Src);
    }
    v23 = *(_QWORD *)a6;
    if ( *(_QWORD *)a6 )
      _InterlockedAdd((volatile signed __int32 *)(v23 + 8), 1u);
    v65[0] = v23;
    Microsoft::Diagnostics::TimedCancellationTokenSource::TimedCancellationTokenSource(v78, v65);
    SystemStateManager = Microsoft::Diagnostics::LifetimeManager::GetSystemStateManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    v63 = Microsoft::Diagnostics::SystemStateManager::FreeNetworkAvailable(SystemStateManager);
    *(_OWORD *)v73 = 0;
    v67 = 60000;
    v68 = 60000;
    v69 = 30000;
    v70 = 30000;
    v62 = 60000;
    *(_QWORD *)&pv = L"UploadResolveTimeout";
    *((_QWORD *)&pv + 1) = 20;
    v25 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateOneSettingsConfig(v91, &v62, &pv, 0);
    v67 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v25);
    Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v91);
    v62 = 60000;
    *(_QWORD *)&pv = L"UploadConnectTimeout";
    *((_QWORD *)&pv + 1) = 20;
    v26 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateOneSettingsConfig(v91, &v62, &pv, 0);
    v68 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v26);
    Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v91);
    v62 = 30000;
    *(_QWORD *)&pv = L"UploadSendTimeout";
    *((_QWORD *)&pv + 1) = 17;
    v27 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateOneSettingsConfig(v91, &v62, &pv, 0);
    v69 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v27);
    Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v91);
    v62 = 30000;
    *(_QWORD *)&pv = L"UploadReceiveTimeout";
    *((_QWORD *)&pv + 1) = 20;
    v28 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::CreateOneSettingsConfig(v91, &v62, &pv, 0);
    v70 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get(v28);
    Microsoft::Diagnostics::DynamicConfig<unsigned long>::~DynamicConfig<unsigned long>((struct Microsoft::Diagnostics::ISettingReceiver *)v91);
    v89[0] = 0;
    v89[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v89[0]) = 0;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_1804631F0, 0, 0) )
    {
      v29 = (struct Microsoft::Diagnostics::SystemStateManager *)((char *)Microsoft::Diagnostics::LifetimeManager::GetSystemStateManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager)
                                                                + 696);
      Microsoft::Diagnostics::ProxyConfig::GetProxyOverrideServer(v29);
      std::wstring::operator=(v89, pszDest);
      std::wstring::_Tidy_deallocate(pszDest);
    }
    Microsoft::Diagnostics::UserManager::GetNetworkImpersonationToken(&v71);
    v30 = (CONTEXT *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 64LL);
    RtlCaptureContext(v30);
    LOBYTE(v31) = 4;
    Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(&v66, 600000, v31, v30);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_TelibTrustAnchors>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_TelibTrustAnchors>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int16)(qword_1804632CA - 3) <= 1u )
      {
        std::_Mutex_base::lock((std::_Mutex_base *)qword_180463078);
        v32 = qword_1804630C8;
        _Mtx_unlock((_Mtx_t)qword_180463078);
        if ( v32 )
        {
          if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4096) )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_1804543B0,
              &byte_1803E4B5F);
        }
      }
    }
    pv = (unsigned __int64)&v79;
    v33 = CreateThreadpoolTimer(
            Microsoft::Diagnostics::Utils::Os::MethodToTpTimerCallbackAdapter<Microsoft::Diagnostics::TimedCancellationTokenSource::TimedCancellationTokenUsage,&private: void Microsoft::Diagnostics::TimedCancellationTokenSource::TimedCancellationTokenUsage::OnTimerExpire(void)>,
            &pv,
            0);
    if ( !v33 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\TimedCancellationTokenSource.h",
        v34);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      (char *)&pv + 8,
      v33);
    pftDueTime[0] = (struct _FILETIME)-3000000000LL;
    SetThreadpoolTimer(*((PTP_TIMER *)&pv + 1), pftDueTime, 0, 0);
    Concurrency::cancellation_token_source::get_token(pv, v65);
    v36 = *(_OWORD *)std::wstring::operator std::wstring_view(&qword_180462610, v83, v35);
    v39 = *(_OWORD *)std::wstring::operator std::wstring_view(v37, v84, v38);
    v41 = *(_OWORD *)std::wstring::operator std::wstring_view(v89, v85, v40);
    v43 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v86, v42);
    v64 = *(_OWORD *)&off_180383FE0;
    LOBYTE(v44) = Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(&v64);
    v45 = (__int128 *)std::wstring::operator std::wstring_view(a1 + 40, v87, v44);
    v64 = v36;
    *(_OWORD *)&pftDueTime[0].dwLowDateTime = v39;
    v80 = v41;
    v81 = v43;
    v82 = *v45;
    v77 = *(_OWORD *)std::wstring::operator std::wstring_view(a1 + 72, pszDest, v46);
    LOBYTE(v48) = a3;
    v49 = Microsoft::Diagnostics::HttpSessionManager::DoSynchronousHttpRequest(
            (int)a1 + 1976,
            (unsigned int)&v77,
            (unsigned int)&v82,
            v48,
            v47 ^ 1u,
            1,
            (__int64)&v81,
            v72,
            (__int64)&v80);
    Concurrency::cancellation_token::_Clear((Concurrency::cancellation_token *)v65);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>((char *)&pv + 8);
    Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)&v66);
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_1804631F0, 0, 0) )
    {
      v53 = Microsoft::Diagnostics::LifetimeManager::GetSystemStateManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      v66 = *(_OWORD *)std::wstring::operator std::wstring_view(v89, pszDest, v53);
      Microsoft::Diagnostics::ProxyConfig::Update(v54 + 696, &v66, (unsigned int)v49);
    }
    if ( (unsigned int)dword_1804543B0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 4096) )
    {
      v62 = v49;
      pftDueTime[0].dwLowDateTime = a5;
      if ( v73[0] )
      {
        v55 = (const wchar_t *)((char *)v73[0] + 32);
        if ( *((_QWORD *)v73[0] + 7) > 0xFu )
          v55 = *(const wchar_t **)v55;
      }
      else
      {
        v55 = &byte_180398459;
      }
      v72 = (__int64)v55;
      if ( v73[0] )
      {
        if ( *((_QWORD *)v73[0] + 3) <= 7u )
          v56 = (const WCHAR *)v73[0];
        else
          v56 = *(const WCHAR **)v73[0];
      }
      else
      {
        v56 = &::Src;
      }
      *(_QWORD *)&v64 = v56;
      if ( v73[0] )
        v57 = *((_DWORD *)v73[0] + 16);
      else
        v57 = 0;
      LODWORD(v65[0]) = v57;
      v58 = Src;
      if ( Src[3] > 7u )
        v58 = (_QWORD *)Src[0];
      *(_QWORD *)&pv = v58;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v57,
        (unsigned int)&word_1803E4AE6,
        v51,
        v52,
        (__int64)&pv,
        (__int64)v65,
        (__int64)&v64,
        (__int64)&v72,
        (__int64)pftDueTime,
        (__int64)&v62);
    }
    if ( v49 >= 0 )
    {
      v59 = *((unsigned int *)v73[0] + 26);
      if ( (_DWORD)v59 )
      {
        LOBYTE(v52) = 1;
        LOBYTE(v59) = 1;
        Microsoft::Diagnostics::AsimovHttpClient::Backoff(a1, v59, 0, v52, *((_DWORD *)v73[0] + 26));
      }
      std::shared_ptr<Microsoft::Diagnostics::ITriggerInst>::operator=(v75);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v71);
      std::wstring::_Tidy_deallocate(v89);
      if ( v73[1] )
        std::_Ref_count_base::_Decref(v73[1]);
      Microsoft::Diagnostics::TimedCancellationTokenSource::~TimedCancellationTokenSource((Microsoft::Diagnostics::TimedCancellationTokenSource *)v78);
      std::wstring::_Tidy_deallocate(v90);
      std::wstring::_Tidy_deallocate(Src);
      Concurrency::cancellation_token::_Clear(a6);
      return 0;
    }
    else
    {
      LOBYTE(v52) = v63;
      LOBYTE(v51) = 1;
      LOBYTE(v50) = a3;
      Microsoft::Diagnostics::AsimovHttpClient::Backoff(a1, v50, v51, v52, 0);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v71);
      std::wstring::_Tidy_deallocate(v89);
      if ( v73[1] )
        std::_Ref_count_base::_Decref(v73[1]);
      Microsoft::Diagnostics::TimedCancellationTokenSource::~TimedCancellationTokenSource((Microsoft::Diagnostics::TimedCancellationTokenSource *)v78);
      std::wstring::_Tidy_deallocate(v90);
      std::wstring::_Tidy_deallocate(Src);
      Concurrency::cancellation_token::_Clear(a6);
      return (unsigned int)v49;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\asimov\\asimovhttpclient.cpp",
      (const char *)0x80070770LL,
      v60);
    Concurrency::cancellation_token::_Clear(a6);
    return 2147944304LL;
  }
}

```

## disassembly

```asm
0x18014a484  mov     rax, rsp
0x18014a487  push    rbx
0x18014a488  push    rsi
0x18014a489  push    rdi
0x18014a48a  push    r13
0x18014a48c  push    r15
0x18014a48e  sub     rsp, 3A0h
0x18014a495  movaps  xmmword ptr [rax-38h], xmm6
0x18014a499  movaps  xmmword ptr [rax-48h], xmm7
0x18014a49d  movaps  xmmword ptr [rax-58h], xmm8
0x18014a4a2  movaps  xmmword ptr [rax-68h], xmm9
0x18014a4a7  mov     rax, cs:__security_cookie
0x18014a4ae  xor     rax, rsp
0x18014a4b1  mov     [rsp+3C8h+var_78], rax
0x18014a4b9  mov     [rsp+3C8h+var_2D0], r9
0x18014a4c1  mov     bl, r8b
0x18014a4c4  mov     rsi, rdx
0x18014a4c7  mov     r13, rcx
0x18014a4ca  mov     r15, [rsp+3C8h+arg_28]
0x18014a4d2  mov     [rsp+3C8h+var_2A0], r15
0x18014a4da  mov     rax, [rsp+3C8h+arg_30]
0x18014a4e2  mov     [rsp+3C8h+var_2A8], rax
0x18014a4ea  mov     eax, cs:dword_1804543B0
0x18014a4f0  cmp     eax, 5
0x18014a4f3  jbe     short loc_18014A51D
0x18014a4f5  mov     edx, 1000h
0x18014a4fa  lea     rcx, dword_1804543B0
0x18014a501  call    _tlgKeywordOn
0x18014a506  test    al, al
0x18014a508  jz      short loc_18014A51D
0x18014a50a  lea     rdx, byte_1803E4C27
0x18014a511  lea     rcx, dword_1804543B0
0x18014a518  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18014a51d  mov     edi, 88h
0x18014a522  lea     eax, [rdi+8]
0x18014a525  cmp     bl, 1
0x18014a528  cmovz   edi, eax
0x18014a52b  mov     rdi, [rdi+r13]
0x18014a52f  call    cs:__imp_GetTickCount64
0x18014a535  cmp     rdi, rax
0x18014a538  jbe     short loc_18014A56C
0x18014a53a  mov     rcx, [rsp+3C8h]; this
0x18014a542  mov     ebx, 80070770h
0x18014a547  mov     r9d, ebx; char *
0x18014a54a  lea     r8, aOnecoreBaseTel_245; "onecore\\base\\telemetry\\utc\\service"...
0x18014a551  mov     edx, 5Eh ; '^'; void *
0x18014a556  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014a55b  nop
0x18014a55c  mov     rcx, r15; this
0x18014a55f  call    ?_Clear@cancellation_token@Concurrency@@AEAAXXZ; Concurrency::cancellation_token::_Clear(void)
0x18014a564  nop
0x18014a565  mov     eax, ebx
0x18014a567  jmp     loc_18014B1DD
0x18014a56c  lea     rdx, [r13+68h]
0x18014a570  lea     rcx, [rsp+3C8h+Src]
0x18014a578  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18014a57d  nop
0x18014a57e  call    ?GetFileTimeAsULL@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL(void)
0x18014a583  mov     rdx, rax
0x18014a586  lea     rcx, [rsp+3C8h+var_7E]
0x18014a58e  call    ??$_UIntegral_to_buff@_W_K@std@@YAPEA_WPEA_W_K@Z; std::_UIntegral_to_buff<wchar_t,unsigned __int64>(wchar_t *,unsigned __int64)
0x18014a593  lea     r8, [rsp+3C8h+var_7E]
0x18014a59b  mov     rdx, rax
0x18014a59e  lea     rcx, [rsp+3C8h+var_1A8]
0x18014a5a6  call    ??$?0PEB_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t const *,wchar_t const *,std::allocator<wchar_t> const &)
0x18014a5ab  nop
0x18014a5ac  lea     rdx, [rsp+3C8h+var_2F8]
0x18014a5b4  lea     rcx, [rsp+3C8h+var_1A8]
0x18014a5bc  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18014a5c1  movups  xmm0, xmmword ptr [rax]
0x18014a5c4  movdqu  [rsp+3C8h+pv], xmm0
0x18014a5cd  lea     rdx, [rsp+3C8h+pv]
0x18014a5d5  lea     rcx, [rsp+3C8h+pszDest]; pszDest
0x18014a5dd  call    ?FileTimeToMillisecond8601@Time@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::Time::FileTimeToMillisecond8601(std::wstring_view)
0x18014a5e2  nop
0x18014a5e3  lea     rdx, [rsp+3C8h+var_298]
0x18014a5eb  mov     rcx, rax
0x18014a5ee  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18014a5f3  movups  xmm0, xmmword ptr [rax]
0x18014a5f6  movdqu  [rsp+3C8h+var_318], xmm0
0x18014a5ff  lea     rax, aUploadTime; "Upload-Time"
0x18014a606  mov     qword ptr [rsp+3C8h+pv], rax
0x18014a60e  mov     qword ptr [rsp+3C8h+pv+8], 0Bh
0x18014a61a  lea     r8, [rsp+3C8h+var_318]
0x18014a622  lea     rdx, [rsp+3C8h+pv]
0x18014a62a  lea     rcx, [rsp+3C8h+Src]; Src
0x18014a632  call    ?AddRequestHeader@AsimovHttpClient@Diagnostics@Microsoft@@CAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z; Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(std::wstring &,std::wstring_view,std::wstring_view)
0x18014a637  nop
0x18014a638  lea     rcx, [rsp+3C8h+pszDest]
0x18014a640  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014a645  lea     rcx, [rsi+20h]
0x18014a649  lea     rdx, [rsp+3C8h+var_2F8]
0x18014a651  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18014a656  movups  xmm0, xmmword ptr [rax]
0x18014a659  movdqu  [rsp+3C8h+var_318], xmm0
0x18014a662  lea     rax, aReliabilityMod; "Reliability-Mode"
0x18014a669  mov     qword ptr [rsp+3C8h+pv], rax
0x18014a671  mov     qword ptr [rsp+3C8h+pv+8], 10h
0x18014a67d  lea     r8, [rsp+3C8h+var_318]
0x18014a685  lea     rdx, [rsp+3C8h+pv]
0x18014a68d  lea     rcx, [rsp+3C8h+Src]; Src
0x18014a695  call    ?AddRequestHeader@AsimovHttpClient@Diagnostics@Microsoft@@CAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z; Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(std::wstring &,std::wstring_view,std::wstring_view)
0x18014a69a  lea     rcx, [rsp+3C8h+pszDest]
0x18014a6a2  call    ?GenerateClientVersionString@AsimovHttpClient@Diagnostics@Microsoft@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::AsimovHttpClient::GenerateClientVersionString(void)
0x18014a6a7  nop
0x18014a6a8  lea     rdx, [rsp+3C8h+var_2F8]
0x18014a6b0  mov     rcx, rax
0x18014a6b3  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18014a6b8  movups  xmm0, xmmword ptr [rax]
0x18014a6bb  movdqu  [rsp+3C8h+var_318], xmm0
0x18014a6c4  lea     rax, aClientVersion; "Client-Version"
0x18014a6cb  mov     qword ptr [rsp+3C8h+pv], rax
0x18014a6d3  mov     qword ptr [rsp+3C8h+pv+8], 0Eh
0x18014a6df  lea     r8, [rsp+3C8h+var_318]
0x18014a6e7  lea     rdx, [rsp+3C8h+pv]
0x18014a6ef  lea     rcx, [rsp+3C8h+Src]; Src
0x18014a6f7  call    ?AddRequestHeader@AsimovHttpClient@Diagnostics@Microsoft@@CAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z; Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(std::wstring &,std::wstring_view,std::wstring_view)
0x18014a6fc  nop
0x18014a6fd  lea     rcx, [rsp+3C8h+pszDest]
0x18014a705  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014a70a  lea     rcx, [rsi+40h]
0x18014a70e  lea     rdx, [rsp+3C8h+var_2F8]
0x18014a716  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18014a71b  movups  xmm0, xmmword ptr [rax]
0x18014a71e  movdqu  [rsp+3C8h+var_318], xmm0
0x18014a727  lea     rax, aApikey; "ApiKey"
0x18014a72e  mov     qword ptr [rsp+3C8h+pv], rax
0x18014a736  mov     qword ptr [rsp+3C8h+pv+8], 6
0x18014a742  lea     r8, [rsp+3C8h+var_318]
0x18014a74a  lea     rdx, [rsp+3C8h+pv]
0x18014a752  lea     rcx, [rsp+3C8h+Src]; Src
0x18014a75a  call    ?AddRequestHeader@AsimovHttpClient@Diagnostics@Microsoft@@CAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z; Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(std::wstring &,std::wstring_view,std::wstring_view)
0x18014a75f  xor     edi, edi
0x18014a761  cmp     [rsi+10h], rdi
0x18014a765  jz      short loc_18014A7BB
0x18014a767  lea     rdx, [rsp+3C8h+var_2F8]
0x18014a76f  mov     rcx, rsi
0x18014a772  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18014a777  movups  xmm0, xmmword ptr [rax]
0x18014a77a  movdqu  [rsp+3C8h+var_318], xmm0
0x18014a783  lea     rax, aAuthmsadevicet; "AuthMsaDeviceTicket"
0x18014a78a  mov     qword ptr [rsp+3C8h+pv], rax
0x18014a792  mov     qword ptr [rsp+3C8h+pv+8], 13h
0x18014a79e  lea     r8, [rsp+3C8h+var_318]
0x18014a7a6  lea     rdx, [rsp+3C8h+pv]
0x18014a7ae  lea     rcx, [rsp+3C8h+Src]; Src
0x18014a7b6  call    ?AddRequestHeader@AsimovHttpClient@Diagnostics@Microsoft@@CAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z; Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(std::wstring &,std::wstring_view,std::wstring_view)
0x18014a7bb  cmp     [rsi+90h], rdi
0x18014a7c2  jz      short loc_18014A81C
0x18014a7c4  lea     rcx, [rsi+80h]
0x18014a7cb  lea     rdx, [rsp+3C8h+var_2F8]
0x18014a7d3  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18014a7d8  movups  xmm0, xmmword ptr [rax]
0x18014a7db  movdqu  [rsp+3C8h+var_318], xmm0
0x18014a7e4  lea     rax, aAuthxtoken; "AuthXToken"
0x18014a7eb  mov     qword ptr [rsp+3C8h+pv], rax
0x18014a7f3  mov     qword ptr [rsp+3C8h+pv+8], 0Ah
0x18014a7ff  lea     r8, [rsp+3C8h+var_318]
0x18014a807  lea     rdx, [rsp+3C8h+pv]
0x18014a80f  lea     rcx, [rsp+3C8h+Src]; Src
0x18014a817  call    ?AddRequestHeader@AsimovHttpClient@Diagnostics@Microsoft@@CAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z; Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(std::wstring &,std::wstring_view,std::wstring_view)
0x18014a81c  cmp     [rsi+70h], rdi
0x18014a820  jz      short loc_18014A877
0x18014a822  lea     rcx, [rsi+60h]
0x18014a826  lea     rdx, [rsp+3C8h+var_2F8]
0x18014a82e  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18014a833  movups  xmm0, xmmword ptr [rax]
0x18014a836  movdqu  [rsp+3C8h+var_318], xmm0
0x18014a83f  lea     rax, aTickets; "Tickets"
0x18014a846  mov     qword ptr [rsp+3C8h+pv], rax
0x18014a84e  mov     qword ptr [rsp+3C8h+pv+8], 7
0x18014a85a  lea     r8, [rsp+3C8h+var_318]
0x18014a862  lea     rdx, [rsp+3C8h+pv]
0x18014a86a  lea     rcx, [rsp+3C8h+Src]; Src
0x18014a872  call    ?AddRequestHeader@AsimovHttpClient@Diagnostics@Microsoft@@CAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z; Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(std::wstring &,std::wstring_view,std::wstring_view)
0x18014a877  cmp     [rsi+0B0h], rdi
0x18014a87e  jz      short loc_18014A8D8
0x18014a880  lea     rcx, [rsi+0A0h]
0x18014a887  lea     rdx, [rsp+3C8h+var_2F8]
0x18014a88f  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18014a894  movups  xmm0, xmmword ptr [rax]
0x18014a897  movdqu  [rsp+3C8h+var_318], xmm0
0x18014a8a0  lea     rax, aAadToken; "Aad-Token"
0x18014a8a7  mov     qword ptr [rsp+3C8h+pv], rax
0x18014a8af  mov     qword ptr [rsp+3C8h+pv+8], 9
0x18014a8bb  lea     r8, [rsp+3C8h+var_318]
0x18014a8c3  lea     rdx, [rsp+3C8h+pv]
0x18014a8cb  lea     rcx, [rsp+3C8h+Src]; Src
0x18014a8d3  call    ?AddRequestHeader@AsimovHttpClient@Diagnostics@Microsoft@@CAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z; Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(std::wstring &,std::wstring_view,std::wstring_view)
0x18014a8d8  cmp     [rsi+0D0h], rdi
0x18014a8df  jz      short loc_18014A939
0x18014a8e1  lea     rcx, [rsi+0C0h]
0x18014a8e8  lea     rdx, [rsp+3C8h+var_2F8]
0x18014a8f0  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18014a8f5  movups  xmm0, xmmword ptr [rax]
0x18014a8f8  movdqu  [rsp+3C8h+var_318], xmm0
0x18014a901  lea     rax, aAaddevicetoken; "AadDeviceToken"
0x18014a908  mov     qword ptr [rsp+3C8h+pv], rax
0x18014a910  mov     qword ptr [rsp+3C8h+pv+8], 0Eh
0x18014a91c  lea     r8, [rsp+3C8h+var_318]
0x18014a924  lea     rdx, [rsp+3C8h+pv]
0x18014a92c  lea     rcx, [rsp+3C8h+Src]; Src
0x18014a934  call    ?AddRequestHeader@AsimovHttpClient@Diagnostics@Microsoft@@CAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z; Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(std::wstring &,std::wstring_view,std::wstring_view)
0x18014a939  cmp     [rsi+0F0h], rdi
0x18014a940  jz      short loc_18014A99D
0x18014a942  lea     rcx, [rsi+0E0h]
0x18014a949  lea     rdx, [rsp+3C8h+var_2F8]
0x18014a951  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18014a956  movups  xmm0, xmmword ptr [rax]
0x18014a959  movdqu  [rsp+3C8h+var_318], xmm0
0x18014a962  lea     rax, aCustomRequestF; "Custom-Request-Field"
0x18014a969  mov     qword ptr [rsp+3C8h+pv], rax
0x18014a971  mov     edi, 14h
0x18014a976  mov     qword ptr [rsp+3C8h+pv+8], rdi
0x18014a97e  lea     r8, [rsp+3C8h+var_318]
0x18014a986  lea     rdx, [rsp+3C8h+pv]
0x18014a98e  lea     rcx, [rsp+3C8h+Src]; Src
0x18014a996  call    ?AddRequestHeader@AsimovHttpClient@Diagnostics@Microsoft@@CAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z; Microsoft::Diagnostics::AsimovHttpClient::AddRequestHeader(std::wstring &,std::wstring_view,std::wstring_view)
0x18014a99b  jmp     short loc_18014A9A2
0x18014a99d  mov     edi, 14h
0x18014a9a2  mov     rax, [r15]
0x18014a9a5  mov     esi, 1
0x18014a9aa  test    rax, rax
0x18014a9ad  jz      short loc_18014A9B3
0x18014a9af  lock add [rax+8], esi
0x18014a9b3  mov     [rsp+3C8h+var_308], rax
0x18014a9bb  lea     rdx, [rsp+3C8h+var_308]
0x18014a9c3  lea     rcx, [rsp+3C8h+var_288]
0x18014a9cb  call    ??0TimedCancellationTokenSource@Diagnostics@Microsoft@@QEAA@Vcancellation_token@Concurrency@@@Z; Microsoft::Diagnostics::TimedCancellationTokenSource::TimedCancellationTokenSource(Concurrency::cancellation_token)
0x18014a9d0  nop
0x18014a9d1  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18014a9d8  call    ?GetSystemStateManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVSystemStateManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetSystemStateManager(void)
0x18014a9dd  mov     rcx, rax; this
0x18014a9e0  call    ?FreeNetworkAvailable@SystemStateManager@Diagnostics@Microsoft@@QEBA_NXZ; Microsoft::Diagnostics::SystemStateManager::FreeNetworkAvailable(void)
0x18014a9e5  mov     [rsp+3C8h+var_324], al
0x18014a9ec  xorps   xmm0, xmm0
0x18014a9ef  movdqu  xmmword ptr [rsp+3C8h+var_2C8], xmm0
0x18014a9f8  mov     eax, 0EA60h
0x18014a9fd  mov     [rsp+3C8h+var_2E8], eax
0x18014aa04  mov     [rsp+3C8h+var_2E4], eax
0x18014aa0b  mov     ecx, 7530h
0x18014aa10  mov     [rsp+3C8h+var_2E0], ecx
0x18014aa17  mov     [rsp+3C8h+var_2DC], ecx
0x18014aa1e  mov     [rsp+3C8h+var_328], eax
0x18014aa25  lea     rax, aUploadresolvet; "UploadResolveTimeout"
0x18014aa2c  mov     qword ptr [rsp+3C8h+pv], rax
0x18014aa34  mov     qword ptr [rsp+3C8h+pv+8], rdi
0x18014aa3c  xor     r9d, r9d
0x18014aa3f  lea     r8, [rsp+3C8h+pv]
0x18014aa47  lea     rdx, [rsp+3C8h+var_328]
0x18014aa4f  lea     rcx, [rsp+3C8h+var_188]
0x18014aa57  call    ?CreateOneSettingsConfig@?$DynamicConfig@K@Diagnostics@Microsoft@@SA?AV123@AEBKV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N@Z; Microsoft::Diagnostics::DynamicConfig<ulong>::CreateOneSettingsConfig(ulong const &,std::wstring_view,bool)
0x18014aa5c  nop
0x18014aa5d  mov     rcx, rax
0x18014aa60  call    ?Get@?$DynamicConfig@K@Diagnostics@Microsoft@@QEBAKXZ; Microsoft::Diagnostics::DynamicConfig<ulong>::Get(void)
0x18014aa65  mov     [rsp+3C8h+var_2E8], eax
0x18014aa6c  lea     rcx, [rsp+3C8h+var_188]
0x18014aa74  call    ??1?$DynamicConfig@K@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::DynamicConfig<ulong>::~DynamicConfig<ulong>(void)
0x18014aa79  mov     [rsp+3C8h+var_328], 0EA60h
0x18014aa84  lea     rax, aUploadconnectt; "UploadConnectTimeout"
0x18014aa8b  mov     qword ptr [rsp+3C8h+pv], rax
0x18014aa93  mov     qword ptr [rsp+3C8h+pv+8], rdi
0x18014aa9b  xor     r9d, r9d
0x18014aa9e  lea     r8, [rsp+3C8h+pv]
0x18014aaa6  lea     rdx, [rsp+3C8h+var_328]
0x18014aaae  lea     rcx, [rsp+3C8h+var_188]
0x18014aab6  call    ?CreateOneSettingsConfig@?$DynamicConfig@K@Diagnostics@Microsoft@@SA?AV123@AEBKV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N@Z; Microsoft::Diagnostics::DynamicConfig<ulong>::CreateOneSettingsConfig(ulong const &,std::wstring_view,bool)
0x18014aabb  nop
0x18014aabc  mov     rcx, rax
0x18014aabf  call    ?Get@?$DynamicConfig@K@Diagnostics@Microsoft@@QEBAKXZ; Microsoft::Diagnostics::DynamicConfig<ulong>::Get(void)
0x18014aac4  mov     [rsp+3C8h+var_2E4], eax
0x18014aacb  lea     rcx, [rsp+3C8h+var_188]
0x18014aad3  call    ??1?$DynamicConfig@K@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::DynamicConfig<ulong>::~DynamicConfig<ulong>(void)
0x18014aad8  mov     [rsp+3C8h+var_328], 7530h
0x18014aae3  lea     rax, aUploadsendtime; "UploadSendTimeout"
0x18014aaea  mov     qword ptr [rsp+3C8h+pv], rax
0x18014aaf2  mov     qword ptr [rsp+3C8h+pv+8], 11h
0x18014aafe  xor     r9d, r9d
0x18014ab01  lea     r8, [rsp+3C8h+pv]
0x18014ab09  lea     rdx, [rsp+3C8h+var_328]
0x18014ab11  lea     rcx, [rsp+3C8h+var_188]
0x18014ab19  call    ?CreateOneSettingsConfig@?$DynamicConfig@K@Diagnostics@Microsoft@@SA?AV123@AEBKV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N@Z; Microsoft::Diagnostics::DynamicConfig<ulong>::CreateOneSettingsConfig(ulong const &,std::wstring_view,bool)
0x18014ab1e  nop
0x18014ab1f  mov     rcx, rax
0x18014ab22  call    ?Get@?$DynamicConfig@K@Diagnostics@Microsoft@@QEBAKXZ; Microsoft::Diagnostics::DynamicConfig<ulong>::Get(void)
0x18014ab27  mov     [rsp+3C8h+var_2E0], eax
0x18014ab2e  lea     rcx, [rsp+3C8h+var_188]
0x18014ab36  call    ??1?$DynamicConfig@K@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::DynamicConfig<ulong>::~DynamicConfig<ulong>(void)
0x18014ab3b  mov     [rsp+3C8h+var_328], 7530h
0x18014ab46  lea     rax, aUploadreceivet; "UploadReceiveTimeout"
0x18014ab4d  mov     qword ptr [rsp+3C8h+pv], rax
0x18014ab55  mov     qword ptr [rsp+3C8h+pv+8], rdi
0x18014ab5d  xor     r9d, r9d
0x18014ab60  lea     r8, [rsp+3C8h+pv]
0x18014ab68  lea     rdx, [rsp+3C8h+var_328]
0x18014ab70  lea     rcx, [rsp+3C8h+var_188]
0x18014ab78  call    ?CreateOneSettingsConfig@?$DynamicConfig@K@Diagnostics@Microsoft@@SA?AV123@AEBKV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N@Z; Microsoft::Diagnostics::DynamicConfig<ulong>::CreateOneSettingsConfig(ulong const &,std::wstring_view,bool)
0x18014ab7d  nop
0x18014ab7e  mov     rcx, rax
0x18014ab81  call    ?Get@?$DynamicConfig@K@Diagnostics@Microsoft@@QEBAKXZ; Microsoft::Diagnostics::DynamicConfig<ulong>::Get(void)
  ... truncated ...
```
