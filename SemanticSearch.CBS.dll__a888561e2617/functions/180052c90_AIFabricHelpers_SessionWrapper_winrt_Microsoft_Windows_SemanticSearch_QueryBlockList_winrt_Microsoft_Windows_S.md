# AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::QueryBlockList_winrt::Microsoft::Windows::SemanticSearch::implementation::QueryBlockList_winrt::Microsoft::Windows::SemanticSearchInternal::IQueryBlockListSession_0_::CreateAsync$_ResumeCoro$1_winrt::Microsoft::Windows::SemanticSearch::QueryBlockList_

- ea: `0x180052c90`
- end: `0x1800535f4`
- name: `AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::QueryBlockList_winrt::Microsoft::Windows::SemanticSearch::implementation::QueryBlockList_winrt::Microsoft::Windows::SemanticSearchInternal::IQueryBlockListSession_0_::CreateAsync$_ResumeCoro$1_winrt::Microsoft::Windows::SemanticSearch::QueryBlockList_`
- size: `2404`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180017960`
- `0x180052c80`

## callees

- `0x1800018b0`
- `0x180002bb0`
- `0x180008520`
- `0x180008600`
- `0x180009ac0`
- `0x180009fa0`
- `0x18000d050`
- `0x180010050`
- `0x180010230`
- `0x1800103e0`
- `0x180010910`
- `0x180014100`
- `0x180014540`
- `0x180014840`
- `0x180015090`
- `0x1800151a0`
- `0x180015a70`
- `0x180015bd0`
- `0x1800161b0`
- `0x180018760`
- `0x180019c90`
- `0x180019e50`
- `0x18001a180`
- `0x18001a570`
- `0x18001a640`
- `0x18001a730`
- `0x18001b0b0`
- `0x18004c070`
- `0x18004c090`
- `0x18004ecf0`
- `0x180052c90`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180052ffc`
- `KERNEL32!GetCurrentThreadId` at `0x180053291`
- `KERNEL32!GetCurrentThreadId` at `0x180052ffc`
- `KERNEL32!GetCurrentThreadId` at `0x180053291`
- `KERNEL32!CloseHandle` at `0x180053181`
- `KERNEL32!CloseHandle` at `0x180053409`
- `KERNEL32!CloseHandle` at `0x180053427`
- `KERNEL32!CloseHandle` at `0x1800534ed`
- `KERNEL32!CloseHandle` at `0x180053181`
- `KERNEL32!CloseHandle` at `0x180053409`
- `KERNEL32!CloseHandle` at `0x180053427`
- `KERNEL32!CloseHandle` at `0x1800534ed`
- `KERNEL32!LeaveCriticalSection` at `0x180053483`
- `KERNEL32!LeaveCriticalSection` at `0x180053483`
- `KERNEL32!EnterCriticalSection` at `0x180052ee0`
- `KERNEL32!EnterCriticalSection` at `0x180053456`
- `KERNEL32!EnterCriticalSection` at `0x180052ee0`
- `KERNEL32!EnterCriticalSection` at `0x180053456`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800533f1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800533f1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800533bd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800533bd`

## string_xrefs

- `0x180052daf`: `CreateAsync`
- `0x180052e27`: `CreateAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::QueryBlockList_winrt::Microsoft::Windows::SemanticSearch::implementation::QueryBlockList_winrt::Microsoft::Windows::SemanticSearchInternal::IQueryBlockListSession_0_::CreateAsync__ResumeCoro_1_winrt::Microsoft::Windows::SemanticSearch::QueryBlockList_(
        _QWORD *a1)
{
  _WORD *v1; // rbx
  unsigned __int64 v2; // rdx
  const wchar_t *v3; // r14
  _DWORD *v4; // rcx
  TelemetryLogger *v5; // rax
  __int64 v6; // rcx
  const wchar_t *v7; // rcx
  __int64 *Async; // rax
  __int64 v9; // rsi
  __int64 v10; // r12
  __int64 *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 *v14; // rax
  _QWORD *v15; // rsi
  _QWORD *Local; // rax
  volatile signed __int32 *v17; // rax
  void *v18; // rcx
  __int64 v19; // rax
  void *v20; // rcx
  _QWORD *v21; // rax
  _QWORD *v22; // rsi
  _QWORD *v23; // rax
  __int64 v24; // rax
  void *v25; // rcx
  __int64 v26; // rax
  const struct _tlgProvider_t *v27; // rax
  void *v28; // r15
  __int64 v29; // rcx
  LPVOID *v30; // rsi
  void *v31; // r14
  unsigned int v32; // r8d
  const char *v33; // r9
  wil::details::in1diag3 *v34; // rcx
  __int64 v35; // rsi
  _QWORD *v36; // rsi
  _QWORD *v37; // r14
  _WORD *v38; // [rsp+30h] [rbp-138h]
  _BYTE pExceptionObject[24]; // [rsp+80h] [rbp-E8h] BYREF
  volatile signed __int32 *v40; // [rsp+98h] [rbp-D0h]
  HANDLE v41; // [rsp+A0h] [rbp-C8h]
  LPVOID v42; // [rsp+A8h] [rbp-C0h]
  int v43; // [rsp+D0h] [rbp-98h]
  LPVOID v44; // [rsp+E0h] [rbp-88h]
  const wchar_t *v45; // [rsp+E8h] [rbp-80h]
  unsigned __int64 v46; // [rsp+100h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v1 = a1;
  v38 = (_WORD *)a1 + 74;
  v2 = 0x180000000uLL;
  switch ( *((_WORD *)a1 + 74) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_116;
    case 2:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
      {
        if ( _InterlockedIncrement(&`AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::implementation::QueryBlockList,winrt::Microsoft::Windows::SemanticSearchInternal::IQueryBlockListSession,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList>'::`7'::__apiCallCounter) != 1 )
          goto LABEL_14;
        *(_OWORD *)(v1 + 76) = 0;
        *((_QWORD *)v1 + 21) = 0;
        *((_QWORD *)v1 + 22) = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (_QWORD *)v1 + 19,
          L"Microsoft.Windows.SemanticSearch.QueryBlockList",
          0x2Fu);
        v3 = v1 + 76;
        v46 = *((_QWORD *)v1 + 22);
        if ( v46 > 7 )
        {
          v3 = (const wchar_t *)*((_QWORD *)v1 + 19);
          v45 = v3;
        }
        v4 = (_DWORD *)*((_QWORD *)TelemetryLogger::Instance() + 1);
        if ( v4 && *v4 )
        {
          v5 = TelemetryLogger::Instance();
          TelemetryLogger::InitApiData_(
            v5,
            v3,
            L"CreateAsync",
            &`AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::implementation::QueryBlockList,winrt::Microsoft::Windows::SemanticSearchInternal::IQueryBlockListSession,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList>'::`7'::__apiCallCounter);
        }
        v6 = (__int64)(v1 + 76);
      }
      else
      {
        *((_OWORD *)v1 + 26) = 0;
        *((_QWORD *)v1 + 54) = 0;
        *((_QWORD *)v1 + 55) = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (_QWORD *)v1 + 52,
          L"Microsoft.Windows.SemanticSearch.QueryBlockList",
          0x2Fu);
        v7 = v1 + 208;
        v46 = *((_QWORD *)v1 + 55);
        if ( v46 > 7 )
        {
          v7 = (const wchar_t *)*((_QWORD *)v1 + 52);
          v45 = v7;
        }
        TelemetryLogger::LogWclApiUsage(v7, L"CreateAsync");
        v6 = (__int64)(v1 + 208);
      }
      std::wstring::_Tidy_deallocate(v6);
LABEL_14:
      Async = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>((_QWORD *)v1 + 56);
      v9 = *Async;
      *Async = 0;
      *((_QWORD *)v1 + 23) = v9;
      if ( *((_QWORD *)v1 + 56) )
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(*((LPVOID *)v1 + 56));
      tip2::details::shared_data<0,0,0>::start(v9 + 8, v1 + 96);
      v10 = v9;
      if ( !v9 )
      {
        v11 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>((_QWORD *)v1 + 57);
        v9 = *v11;
        *v11 = 0;
        *((_QWORD *)v1 + 23) = v9;
        v10 = v9;
        if ( *((_QWORD *)v1 + 57) )
        {
          v42 = (LPVOID)*((_QWORD *)v1 + 57);
          tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(v42);
        }
      }
      *((_QWORD *)v1 + 26) = v9;
      if ( v9 )
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 296));
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
      std::wstring::assign((void *)(v9 + 264), L"Microsoft.Windows.SemanticSearch.QueryBlockList");
      if ( v9 )
      {
        tip2::details::shared_data<0,0,0>::end_update(v9 + 8);
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release((LPVOID)v9);
      }
      *((_QWORD *)v1 + 28) = 0;
      *((_QWORD *)v1 + 29) = 0;
      *((_QWORD *)v1 + 30) = 0;
      *((_QWORD *)v1 + 31) = 0;
      *((_QWORD *)v1 + 32) = 0;
      *((_QWORD *)v1 + 33) = 0;
      *((_QWORD *)v1 + 27) = &tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>>::`vftable';
      *((_QWORD *)v1 + 28) = 0;
      *((_QWORD *)v1 + 29) = v1 + 108;
      *((_QWORD *)v1 + 30) = 0;
      *((_DWORD *)v1 + 62) = 0;
      *((_QWORD *)v1 + 32) = 0;
      tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>((_QWORD *)v1 + 33);
      if ( !v10 )
      {
        v14 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>((_QWORD *)v1 + 58);
        v13 = *v14;
        *v14 = 0;
        *((_QWORD *)v1 + 23) = v13;
        if ( *((_QWORD *)v1 + 58) )
          tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(*((LPVOID *)v1 + 58));
      }
      *((_QWORD *)v1 + 34) = &tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>>::`vftable';
      v15 = v1 + 140;
      *((_QWORD *)v1 + 35) = 0;
      *((_QWORD *)v1 + 36) = v1 + 136;
      *((_QWORD *)v1 + 37) = 0;
      *((_DWORD *)v1 + 76) = 0;
      *((_QWORD *)v1 + 39) = 0;
      if ( wil::details::g_pThreadFailureCallbacks )
      {
        LOBYTE(v12) = 1;
        Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                            v13,
                            v12);
        *v15 = Local;
        if ( Local )
        {
          *((_QWORD *)v1 + 37) = *Local;
          *Local = v15;
          *((_DWORD *)v1 + 76) = GetCurrentThreadId();
        }
      }
      v17 = (volatile signed __int32 *)*((_QWORD *)v1 + 23);
      *((_QWORD *)v1 + 40) = v17;
      if ( v17 )
      {
        v40 = v17;
        _InterlockedIncrement(v17 + 74);
      }
      v18 = (void *)*((_QWORD *)v1 + 33);
      v44 = v18;
      v19 = *((_QWORD *)v1 + 40);
      *((_QWORD *)v1 + 33) = v19;
      if ( v19 )
        _InterlockedIncrement((volatile signed __int32 *)(v19 + 296));
      if ( v18 )
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(v18);
      if ( *((_DWORD *)v1 + 76) )
      {
        if ( !*((_DWORD *)v1 + 62) )
          wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(v1 + 112));
      }
      else if ( *((_DWORD *)v1 + 62) )
      {
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v1 + 112));
      }
      if ( *((_QWORD *)v1 + 40) )
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(*((LPVOID *)v1 + 40));
      if ( *((_DWORD *)v1 + 76) )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v1 + 140));
      *((_QWORD *)v1 + 41) = 0;
      ImpersonationHelper::GetThreadImpersonationToken(v1 + 164);
      v43 = *((_DWORD *)v1 + 62);
      if ( v43 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v1 + 112));
      *((_BYTE *)v1 + 336) = 0;
      if ( *((_DWORD *)v1 + 28) == 2 )
      {
        *((_DWORD *)v1 + 118) = 3980;
        *((_QWORD *)v1 + 60) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(v1 + 236));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v38 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(4, v1);
      return;
    case 4:
      if ( !a1[23] )
      {
        v21 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(a1 + 61);
        a1 = (_QWORD *)*v21;
        *v21 = 0;
        *((_QWORD *)v1 + 23) = a1;
        if ( *((_QWORD *)v1 + 61) )
          tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(*((LPVOID *)v1 + 61));
      }
      *((_QWORD *)v1 + 43) = &tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>>::`vftable';
      v22 = v1 + 176;
      *((_QWORD *)v1 + 44) = 0;
      *((_QWORD *)v1 + 45) = v1 + 172;
      *((_QWORD *)v1 + 46) = 0;
      *((_DWORD *)v1 + 94) = 0;
      *((_QWORD *)v1 + 48) = 0;
      if ( wil::details::g_pThreadFailureCallbacks )
      {
        LOBYTE(v2) = 1;
        v23 = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          a1,
                          v2);
        *v22 = v23;
        if ( v23 )
        {
          *((_QWORD *)v1 + 46) = *v23;
          *v23 = v22;
          *((_DWORD *)v1 + 94) = GetCurrentThreadId();
        }
      }
      v24 = *((_QWORD *)v1 + 23);
      *((_QWORD *)v1 + 49) = v24;
      if ( v24 )
        _InterlockedIncrement((volatile signed __int32 *)(v24 + 296));
      v25 = (void *)*((_QWORD *)v1 + 33);
      v26 = *((_QWORD *)v1 + 49);
      *((_QWORD *)v1 + 33) = v26;
      if ( v26 )
        _InterlockedIncrement((volatile signed __int32 *)(v26 + 296));
      if ( v25 )
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(v25);
      if ( *((_DWORD *)v1 + 94) )
      {
        if ( !*((_DWORD *)v1 + 62) )
          wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(v1 + 112));
      }
      else if ( *((_DWORD *)v1 + 62) )
      {
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v1 + 112));
      }
      if ( *((_QWORD *)v1 + 49) )
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(*((LPVOID *)v1 + 49));
      if ( *((_DWORD *)v1 + 94) )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v1 + 176));
      v27 = TraceLogger::Provider();
      if ( *(_DWORD *)v27 > 5u )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (__int64)v27,
          (unsigned __int8 *)byte_1800797ED);
      v28 = (void *)*((_QWORD *)v1 + 41);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_LocalService_Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIFabric_LocalService_Support>::GetImpl'::`2'::impl)
        && v28 )
      {
        v30 = (LPVOID *)(v1 + 248);
        *((_QWORD *)v1 + 62) = 0;
        ImpersonationHelper::GetThreadImpersonationToken(v1 + 248);
        v31 = (void *)*((_QWORD *)v1 + 62);
        *((_QWORD *)v1 + 62) = 0;
        *((_QWORD *)v1 + 63) = v31;
        if ( !ImpersonateLoggedOnUser(v28) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x23, v32, v33);
        `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::implementation::QueryBlockList,winrt::Microsoft::Windows::SemanticSearchInternal::IQueryBlockListSession,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList>'::`2'::_lambda_1_::operator()(
          (__int64)retaddr,
          (_QWORD *)v1 + 50);
        if ( v31 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v31) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v34);
          if ( v31 )
            CloseHandle(v31);
        }
        if ( *v30 && *v30 != (LPVOID)-1LL )
        {
          v42 = *v30;
          CloseHandle(v42);
        }
      }
      else
      {
        `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::implementation::QueryBlockList,winrt::Microsoft::Windows::SemanticSearchInternal::IQueryBlockListSession,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList>'::`2'::_lambda_1_::operator()(
          v29,
          (_QWORD *)v1 + 50);
      }
      if ( *((_QWORD *)v1 + 23) )
      {
        v35 = *((_QWORD *)v1 + 23);
        EnterCriticalSection((LPCRITICAL_SECTION)(v35 + 200));
        *(_DWORD *)(v35 + 72) |= 0x300u;
        if ( *(_QWORD *)(v35 + 240) )
          tip2::details::shared_data<0,0,0>::complete_helper(v35 + 8, 2u);
        if ( v35 != -200 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v35 + 200));
      }
      v36 = v1 + 60;
      v37 = v1 + 200;
      if ( v1 + 60 == v1 + 200 )
      {
        if ( *v37 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v1 + 200);
      }
      else
      {
        if ( *v36 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v1 + 60);
        *v36 = *v37;
      }
      if ( *((_QWORD *)v1 + 41) && *((_QWORD *)v1 + 41) != -1 )
      {
        v41 = (HANDLE)*((_QWORD *)v1 + 41);
        CloseHandle(v41);
      }
      v44 = (LPVOID)*((_QWORD *)v1 + 33);
      if ( v44 )
      {
        v44 = (LPVOID)*((_QWORD *)v1 + 33);
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(v44);
      }
      v43 = *((_DWORD *)v1 + 62);
      if ( v43 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v1 + 112));
      if ( *((_QWORD *)v1 + 23) )
      {
        v40 = (volatile signed __int32 *)*((_QWORD *)v1 + 23);
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release((LPVOID)v40);
      }
      *((_QWORD *)v1 + 51) = v1 + 8;
      *v38 = 0;
      *(_QWORD *)v1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)v1 + 51) )
        goto LABEL_116;
      return;
    case 5:
      if ( a1[41] && a1[41] != -1 )
      {
        v20 = (void *)a1[41];
        v41 = (HANDLE)*((_QWORD *)v1 + 41);
        CloseHandle(v20);
      }
      v44 = (LPVOID)*((_QWORD *)v1 + 33);
      if ( v44 )
      {
        v44 = (LPVOID)*((_QWORD *)v1 + 33);
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(v44);
      }
      v43 = *((_DWORD *)v1 + 62);
      if ( v43 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v1 + 112));
      if ( *((_QWORD *)v1 + 23) )
      {
        v40 = (volatile signed __int32 *)*((_QWORD *)v1 + 23);
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release((LPVOID)v40);
      }
LABEL_116:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)v1 + 2);
      if ( v1[75] )
        operator delete(v1);
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180052c90  mov     r11, rsp
0x180052c93  mov     [r11+10h], rbx
0x180052c97  mov     [r11+18h], rsi
0x180052c9b  mov     [r11+8], rcx
0x180052c9f  push    rdi
0x180052ca0  push    r12
0x180052ca2  push    r13
0x180052ca4  push    r14
0x180052ca6  push    r15
0x180052ca8  sub     rsp, 140h
0x180052caf  mov     rax, cs:__security_cookie
0x180052cb6  xor     rax, rsp
0x180052cb9  mov     [rsp+168h+var_30], rax
0x180052cc1  mov     rbx, rcx
0x180052cc4  mov     [rsp+168h+var_140], rcx
0x180052cc9  lea     rax, [rbx+94h]
0x180052cd0  mov     [rsp+168h+var_138], rax
0x180052cd5  movzx   eax, word ptr [rax]
0x180052cd8  mov     [rsp+168h+var_148], ax
0x180052cdd  inc     ax; switch 7 cases
0x180052ce0  cmp     ax, 6
0x180052ce4  ja      def_180052CFF; jumptable 0000000180052CFF default case, case 0
0x180052cea  movsx   rax, ax
0x180052cee  lea     rdx, cs:180000000h
0x180052cf5  mov     ecx, ds:(jpt_180052CFF - 180000000h)[rdx+rax*4]
0x180052cfc  add     rcx, rdx
0x180052cff  jmp     rcx; switch jump
0x180052d01  jmp     loc_180053586; jumptable 0000000180052CFF case 3
0x180052d06  xor     edi, edi; jumptable 0000000180052CFF case 2
0x180052d08  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x180052d0f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x180052d14  test    al, al
0x180052d16  jz      loc_180052DCB
0x180052d1c  mov     eax, 1
0x180052d21  lock xadd cs:?__apiCallCounter@?6???$CreateAsync@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@@?$SessionWrapper@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UIQueryBlockListSession@SemanticSearchInternal@345@$0A@@AIFabricHelpers@@SA?AU?$IAsyncOperation@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@6@@Z@4JC, eax; long volatile `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList,winrt::Microsoft::Windows::SemanticSearch::implementation::QueryBlockList,winrt::Microsoft::Windows::SemanticSearchInternal::IQueryBlockListSession,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::QueryBlockList>(winrt::guid)'::`7'::__apiCallCounter
0x180052d29  inc     eax
0x180052d2b  cmp     eax, 1
0x180052d2e  jnz     loc_180052E40
0x180052d34  xorps   xmm0, xmm0
0x180052d37  movups  xmmword ptr [rbx+98h], xmm0
0x180052d3e  mov     [rbx+0A8h], rdi
0x180052d45  mov     [rbx+0B0h], rdi
0x180052d4c  mov     r8d, 2Fh ; '/'
0x180052d52  lea     rdx, aMicrosoftWindo_29; "Microsoft.Windows.SemanticSearch.QueryB"...
0x180052d59  lea     rcx, [rbx+98h]
0x180052d60  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180052d65  lea     r14, [rbx+98h]
0x180052d6c  mov     rax, [rbx+0B0h]
0x180052d73  mov     [rsp+168h+var_68], rax
0x180052d7b  cmp     rax, 7
0x180052d7f  jbe     short loc_180052D90
0x180052d81  mov     r14, [rbx+98h]
0x180052d88  mov     [rsp+168h+var_80], r14
0x180052d90  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180052d95  mov     rcx, [rax+8]
0x180052d99  test    rcx, rcx
0x180052d9c  jz      short loc_180052DC2
0x180052d9e  cmp     dword ptr [rcx], 0
0x180052da1  jbe     short loc_180052DC2
0x180052da3  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180052da8  lea     r9, ?__apiCallCounter@?6???$CreateAsync@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@@?$SessionWrapper@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UIQueryBlockListSession@SemanticSearchInternal@345@$0A@@AIFabricHelpers@@SA?AU?$IAsyncOperation@UQueryBlockList@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@6@@Z@4JC; volatile int *
0x180052daf  lea     r8, aCreateasync; "CreateAsync"
0x180052db6  mov     rdx, r14; wchar_t *
0x180052db9  mov     rcx, rax; this
0x180052dbc  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x180052dc1  nop
0x180052dc2  lea     rcx, [rbx+98h]
0x180052dc9  jmp     short loc_180052E3A
0x180052dcb  xorps   xmm0, xmm0
0x180052dce  movups  xmmword ptr [rbx+1A0h], xmm0
0x180052dd5  mov     [rbx+1B0h], rdi
0x180052ddc  mov     [rbx+1B8h], rdi
0x180052de3  mov     r8d, 2Fh ; '/'
0x180052de9  lea     rdx, aMicrosoftWindo_29; "Microsoft.Windows.SemanticSearch.QueryB"...
0x180052df0  lea     rcx, [rbx+1A0h]
0x180052df7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180052dfc  lea     rcx, [rbx+1A0h]
0x180052e03  mov     rax, [rbx+1B8h]
0x180052e0a  mov     [rsp+168h+var_68], rax
0x180052e12  cmp     rax, 7
0x180052e16  jbe     short loc_180052E27
0x180052e18  mov     rcx, [rbx+1A0h]; wchar_t *
0x180052e1f  mov     [rsp+168h+var_80], rcx
0x180052e27  lea     rdx, aCreateasync; "CreateAsync"
0x180052e2e  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x180052e33  lea     rcx, [rbx+1A0h]
0x180052e3a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180052e3f  nop
0x180052e40  lea     rcx, [rbx+1C0h]
0x180052e47  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x180052e4c  mov     rsi, [rax]
0x180052e4f  mov     [rax], rdi
0x180052e52  mov     [rbx+0B8h], rsi
0x180052e59  cmp     qword ptr [rbx+1C0h], 0
0x180052e61  jz      short loc_180052E74
0x180052e63  mov     rcx, [rbx+1C0h]; pv
0x180052e6a  mov     [rsp+168h+var_130], rcx
0x180052e6f  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180052e74  lea     rdx, [rbx+0C0h]
0x180052e7b  lea     rcx, [rsi+8]
0x180052e7f  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180052e84  mov     r12, rsi
0x180052e87  test    rsi, rsi
0x180052e8a  jnz     short loc_180052EC6
0x180052e8c  lea     rcx, [rbx+1C8h]
0x180052e93  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x180052e98  mov     rsi, [rax]
0x180052e9b  mov     [rax], rdi
0x180052e9e  mov     [rbx+0B8h], rsi
0x180052ea5  mov     r12, rsi
0x180052ea8  cmp     qword ptr [rbx+1C8h], 0
0x180052eb0  jz      short loc_180052EC6
0x180052eb2  mov     rcx, [rbx+1C8h]; pv
0x180052eb9  mov     [rsp+168h+var_C0], rcx
0x180052ec1  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180052ec6  mov     [rbx+0D0h], rsi
0x180052ecd  test    rsi, rsi
0x180052ed0  jz      short loc_180052ED9
0x180052ed2  lock inc dword ptr [rsi+128h]
0x180052ed9  lea     rcx, [rsi+0C8h]; lpCriticalSection
0x180052ee0  call    cs:__imp_EnterCriticalSection
0x180052ee6  nop
0x180052ee7  lea     rcx, [rsi+108h]; void *
0x180052eee  mov     r8d, 2Fh ; '/'
0x180052ef4  lea     rdx, aMicrosoftWindo_29; "Microsoft.Windows.SemanticSearch.QueryB"...
0x180052efb  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180052f00  nop
0x180052f01  test    rsi, rsi
0x180052f04  jz      short loc_180052F17
0x180052f06  lea     rcx, [rsi+8]
0x180052f0a  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180052f0f  mov     rcx, rsi; pv
0x180052f12  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180052f17  lea     rax, [rbx+0D8h]
0x180052f1e  mov     [rax+8], rdi
0x180052f22  mov     [rax+10h], rdi
0x180052f26  mov     [rax+18h], rdi
0x180052f2a  mov     [rax+20h], rdi
0x180052f2e  mov     [rax+28h], rdi
0x180052f32  mov     [rax+30h], rdi
0x180052f36  lea     rsi, ??_7?$test_watcher@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>>::`vftable'
0x180052f3d  mov     [rax], rsi
0x180052f40  mov     [rbx+0E0h], rdi
0x180052f47  mov     [rbx+0E8h], rax
0x180052f4e  mov     [rbx+0F0h], rdi
0x180052f55  mov     [rbx+0F8h], edi
0x180052f5b  mov     [rbx+100h], rdi
0x180052f62  lea     rcx, [rbx+108h]
0x180052f69  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x180052f6e  nop
0x180052f6f  test    r12, r12
0x180052f72  jnz     short loc_180052FA7
0x180052f74  lea     rcx, [rbx+1D0h]
0x180052f7b  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x180052f80  mov     rcx, [rax]
0x180052f83  mov     [rax], rdi
0x180052f86  mov     [rbx+0B8h], rcx
0x180052f8d  cmp     [rbx+1D0h], r12
0x180052f94  jz      short loc_180052FA7
0x180052f96  mov     rcx, [rbx+1D0h]; pv
0x180052f9d  mov     [rsp+168h+var_128], rcx
0x180052fa2  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180052fa7  lea     rax, [rbx+110h]
0x180052fae  mov     [rax], rsi
0x180052fb1  lea     rsi, [rbx+118h]
0x180052fb8  mov     [rsi], rdi
0x180052fbb  mov     [rbx+120h], rax
0x180052fc2  mov     [rbx+128h], rdi
0x180052fc9  mov     [rbx+130h], edi
0x180052fcf  mov     [rbx+138h], rdi
0x180052fd6  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180052fde  jz      short loc_180053008
0x180052fe0  mov     dl, 1
0x180052fe2  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180052fe7  mov     [rsi], rax
0x180052fea  test    rax, rax
0x180052fed  jz      short loc_180053008
0x180052fef  mov     rcx, [rax]
0x180052ff2  mov     [rbx+128h], rcx
0x180052ff9  mov     [rax], rsi
0x180052ffc  call    cs:__imp_GetCurrentThreadId
0x180053002  mov     [rbx+130h], eax
0x180053008  mov     rax, [rbx+0B8h]
0x18005300f  mov     [rbx+140h], rax
0x180053016  test    rax, rax
0x180053019  jz      short loc_18005302A
0x18005301b  mov     [rsp+168h+var_D0], rax
0x180053023  lock inc dword ptr [rax+128h]
0x18005302a  mov     rcx, [rbx+108h]; pv
0x180053031  mov     [rsp+168h+var_88], rcx
0x180053039  mov     rax, [rbx+140h]
0x180053040  mov     [rbx+108h], rax
0x180053047  test    rax, rax
0x18005304a  jz      short loc_180053053
0x18005304c  lock inc dword ptr [rax+128h]
0x180053053  test    rcx, rcx
0x180053056  jz      short loc_18005305D
0x180053058  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x18005305d  cmp     dword ptr [rbx+130h], 0
0x180053064  jz      short loc_18005307D
0x180053066  cmp     dword ptr [rbx+0F8h], 0
0x18005306d  jnz     short loc_180053093
0x18005306f  lea     rcx, [rbx+0E0h]; this
0x180053076  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18005307b  jmp     short loc_180053093
0x18005307d  cmp     dword ptr [rbx+0F8h], 0
0x180053084  jz      short loc_180053093
0x180053086  lea     rcx, [rbx+0E0h]; this
0x18005308d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180053092  nop
0x180053093  mov     rax, [rbx+140h]
0x18005309a  mov     [rsp+168h+var_F0], rax
0x18005309f  test    rax, rax
0x1800530a2  jz      short loc_1800530B5
0x1800530a4  mov     rcx, [rbx+140h]; pv
0x1800530ab  mov     [rsp+168h+var_F0], rcx
0x1800530b0  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x1800530b5  mov     eax, [rbx+130h]
0x1800530bb  mov     [rsp+168h+var_100], eax
0x1800530bf  test    eax, eax
0x1800530c1  jz      short loc_1800530CB
0x1800530c3  mov     rcx, rsi; this
0x1800530c6  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800530cb  lea     rcx, [rbx+148h]
0x1800530d2  mov     [rcx], rdi
0x1800530d5  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x1800530da  nop
0x1800530db  mov     eax, [rbx+0F8h]
0x1800530e1  mov     [rsp+168h+var_98], eax
0x1800530e8  test    eax, eax
0x1800530ea  jz      short loc_1800530F9
0x1800530ec  lea     rcx, [rbx+0E0h]; this
0x1800530f3  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800530f8  nop
0x1800530f9  mov     byte ptr [rbx+150h], 0
0x180053100  mov     eax, [rbx+70h]
0x180053103  cmp     eax, 2
0x180053106  jnz     short loc_180053144
0x180053108  lea     rdx, [rbx+1D8h]; struct winrt::impl::slim_source_location *
0x18005310f  mov     dword ptr [rdx], 0F8Ch
0x180053115  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005311c  mov     [rbx+1E0h], rax
0x180053123  lea     rcx, [rsp+168h+pExceptionObject]; this
0x18005312b  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180053130  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180053137  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18005313f  call    _CxxThrowException
0x180053144  mov     ecx, 4
0x180053149  mov     rax, [rsp+168h+var_138]
0x18005314e  mov     [rax], cx
0x180053151  mov     rdx, rbx
0x180053154  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180053159  jmp     loc_1800535A9
0x18005315e  cmp     qword ptr [rbx+148h], 0; jumptable 0000000180052CFF case 5
0x180053166  jz      short loc_180053188
0x180053168  cmp     qword ptr [rbx+148h], 0FFFFFFFFFFFFFFFFh
0x180053170  jz      short loc_180053188
0x180053172  mov     rcx, [rbx+148h]; hObject
0x180053179  mov     [rsp+168h+var_C8], rcx
0x180053181  call    cs:__imp_CloseHandle
0x180053187  nop
0x180053188  mov     rax, [rbx+108h]
0x18005318f  mov     [rsp+168h+var_88], rax
0x180053197  test    rax, rax
0x18005319a  jz      short loc_1800531B0
0x18005319c  mov     rcx, [rbx+108h]; pv
0x1800531a3  mov     [rsp+168h+var_88], rcx
0x1800531ab  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x1800531b0  mov     eax, [rbx+0F8h]
0x1800531b6  mov     [rsp+168h+var_98], eax
0x1800531bd  test    eax, eax
0x1800531bf  jz      short loc_1800531CE
0x1800531c1  lea     rcx, [rbx+0E0h]; this
0x1800531c8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800531cd  nop
0x1800531ce  cmp     qword ptr [rbx+0B8h], 0
0x1800531d6  jz      short loc_1800531ED
0x1800531d8  mov     rcx, [rbx+0B8h]; pv
0x1800531df  mov     [rsp+168h+var_D0], rcx
0x1800531e7  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x1800531ec  nop
0x1800531ed  jmp     loc_180053586; jumptable 0000000180052CFF cases -1,1
0x1800531f2  cmp     qword ptr [rbx+0B8h], 0; jumptable 0000000180052CFF case 4
0x1800531fa  jnz     short loc_180053233
0x1800531fc  lea     rcx, [rbx+1E8h]
0x180053203  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x180053208  mov     rcx, [rax]
0x18005320b  xor     edi, edi
0x18005320d  mov     [rax], rdi
0x180053210  mov     [rbx+0B8h], rcx
0x180053217  cmp     [rbx+1E8h], rdi
0x18005321e  jz      short loc_180053235
0x180053220  mov     rcx, [rbx+1E8h]; pv
0x180053227  mov     [rsp+168h+var_128], rcx
0x18005322c  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180053231  jmp     short loc_180053235
0x180053233  xor     edi, edi
0x180053235  lea     rax, [rbx+158h]
0x18005323c  lea     rsi, ??_7?$test_watcher@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>>::`vftable'
0x180053243  mov     [rax], rsi
  ... truncated ...
```
