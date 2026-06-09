# AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::QueryProcessor_winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor_winrt::Microsoft::Windows::SemanticSearchInternal::IQueryProcessorSession3_0_::CreateAsync$_ResumeCoro$1_winrt::Microsoft::Windows::SemanticSearch::QueryProcessor_

- ea: `0x180053610`
- end: `0x180053f74`
- name: `AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::QueryProcessor_winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor_winrt::Microsoft::Windows::SemanticSearchInternal::IQueryProcessorSession3_0_::CreateAsync$_ResumeCoro$1_winrt::Microsoft::Windows::SemanticSearch::QueryProcessor_`
- size: `2404`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c320`
- `0x180053600`

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
- `0x180019c90`
- `0x180019e50`
- `0x18001a180`
- `0x18001a570`
- `0x18001a640`
- `0x18001a730`
- `0x18001b0b0`
- `0x18001ce90`
- `0x18004c070`
- `0x18004c090`
- `0x18004ecf0`
- `0x180053610`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005397c`
- `KERNEL32!GetCurrentThreadId` at `0x180053c11`
- `KERNEL32!GetCurrentThreadId` at `0x18005397c`
- `KERNEL32!GetCurrentThreadId` at `0x180053c11`
- `KERNEL32!CloseHandle` at `0x180053b01`
- `KERNEL32!CloseHandle` at `0x180053d89`
- `KERNEL32!CloseHandle` at `0x180053da7`
- `KERNEL32!CloseHandle` at `0x180053e6d`
- `KERNEL32!CloseHandle` at `0x180053b01`
- `KERNEL32!CloseHandle` at `0x180053d89`
- `KERNEL32!CloseHandle` at `0x180053da7`
- `KERNEL32!CloseHandle` at `0x180053e6d`
- `KERNEL32!LeaveCriticalSection` at `0x180053e03`
- `KERNEL32!LeaveCriticalSection` at `0x180053e03`
- `KERNEL32!EnterCriticalSection` at `0x180053860`
- `KERNEL32!EnterCriticalSection` at `0x180053dd6`
- `KERNEL32!EnterCriticalSection` at `0x180053860`
- `KERNEL32!EnterCriticalSection` at `0x180053dd6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180053d71`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180053d71`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180053d3d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180053d3d`

## string_xrefs

- `0x18005372f`: `CreateAsync`
- `0x1800537a7`: `CreateAsync`

## pseudocode

```c
void __fastcall AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::QueryProcessor_winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor_winrt::Microsoft::Windows::SemanticSearchInternal::IQueryProcessorSession3_0_::CreateAsync__ResumeCoro_1_winrt::Microsoft::Windows::SemanticSearch::QueryProcessor_(
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
        if ( _InterlockedIncrement(&`AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor,winrt::Microsoft::Windows::SemanticSearchInternal::IQueryProcessorSession3,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor>'::`7'::__apiCallCounter) != 1 )
          goto LABEL_14;
        *(_OWORD *)(v1 + 76) = 0;
        *((_QWORD *)v1 + 21) = 0;
        *((_QWORD *)v1 + 22) = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (_QWORD *)v1 + 19,
          L"Microsoft.Windows.SemanticSearch.QueryProcessor",
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
            &`AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor,winrt::Microsoft::Windows::SemanticSearchInternal::IQueryProcessorSession3,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor>'::`7'::__apiCallCounter);
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
          L"Microsoft.Windows.SemanticSearch.QueryProcessor",
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
      std::wstring::assign((void *)(v9 + 264), L"Microsoft.Windows.SemanticSearch.QueryProcessor");
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
        `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor,winrt::Microsoft::Windows::SemanticSearchInternal::IQueryProcessorSession3,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor>'::`2'::_lambda_1_::operator()(
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
        `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor,winrt::Microsoft::Windows::SemanticSearchInternal::IQueryProcessorSession3,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor>'::`2'::_lambda_1_::operator()(
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
0x180053610  mov     r11, rsp
0x180053613  mov     [r11+10h], rbx
0x180053617  mov     [r11+18h], rsi
0x18005361b  mov     [r11+8], rcx
0x18005361f  push    rdi
0x180053620  push    r12
0x180053622  push    r13
0x180053624  push    r14
0x180053626  push    r15
0x180053628  sub     rsp, 140h
0x18005362f  mov     rax, cs:__security_cookie
0x180053636  xor     rax, rsp
0x180053639  mov     [rsp+168h+var_30], rax
0x180053641  mov     rbx, rcx
0x180053644  mov     [rsp+168h+var_140], rcx
0x180053649  lea     rax, [rbx+94h]
0x180053650  mov     [rsp+168h+var_138], rax
0x180053655  movzx   eax, word ptr [rax]
0x180053658  mov     [rsp+168h+var_148], ax
0x18005365d  inc     ax; switch 7 cases
0x180053660  cmp     ax, 6
0x180053664  ja      def_18005367F; jumptable 000000018005367F default case, case 0
0x18005366a  movsx   rax, ax
0x18005366e  lea     rdx, cs:180000000h
0x180053675  mov     ecx, ds:(jpt_18005367F - 180000000h)[rdx+rax*4]
0x18005367c  add     rcx, rdx
0x18005367f  jmp     rcx; switch jump
0x180053681  jmp     loc_180053F06; jumptable 000000018005367F case 3
0x180053686  xor     edi, edi; jumptable 000000018005367F case 2
0x180053688  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x18005368f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x180053694  test    al, al
0x180053696  jz      loc_18005374B
0x18005369c  mov     eax, 1
0x1800536a1  lock xadd cs:?__apiCallCounter@?6???$CreateAsync@UQueryProcessor@SemanticSearch@Windows@Microsoft@winrt@@@?$SessionWrapper@UQueryProcessor@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UIQueryProcessorSession3@SemanticSearchInternal@345@$0A@@AIFabricHelpers@@SA?AU?$IAsyncOperation@UQueryProcessor@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@6@@Z@4JC, eax; long volatile `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor,winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor,winrt::Microsoft::Windows::SemanticSearchInternal::IQueryProcessorSession3,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::QueryProcessor>(winrt::guid)'::`7'::__apiCallCounter
0x1800536a9  inc     eax
0x1800536ab  cmp     eax, 1
0x1800536ae  jnz     loc_1800537C0
0x1800536b4  xorps   xmm0, xmm0
0x1800536b7  movups  xmmword ptr [rbx+98h], xmm0
0x1800536be  mov     [rbx+0A8h], rdi
0x1800536c5  mov     [rbx+0B0h], rdi
0x1800536cc  mov     r8d, 2Fh ; '/'
0x1800536d2  lea     rdx, aMicrosoftWindo_3; "Microsoft.Windows.SemanticSearch.QueryP"...
0x1800536d9  lea     rcx, [rbx+98h]
0x1800536e0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800536e5  lea     r14, [rbx+98h]
0x1800536ec  mov     rax, [rbx+0B0h]
0x1800536f3  mov     [rsp+168h+var_68], rax
0x1800536fb  cmp     rax, 7
0x1800536ff  jbe     short loc_180053710
0x180053701  mov     r14, [rbx+98h]
0x180053708  mov     [rsp+168h+var_80], r14
0x180053710  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180053715  mov     rcx, [rax+8]
0x180053719  test    rcx, rcx
0x18005371c  jz      short loc_180053742
0x18005371e  cmp     dword ptr [rcx], 0
0x180053721  jbe     short loc_180053742
0x180053723  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180053728  lea     r9, ?__apiCallCounter@?6???$CreateAsync@UQueryProcessor@SemanticSearch@Windows@Microsoft@winrt@@@?$SessionWrapper@UQueryProcessor@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UIQueryProcessorSession3@SemanticSearchInternal@345@$0A@@AIFabricHelpers@@SA?AU?$IAsyncOperation@UQueryProcessor@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@6@@Z@4JC; volatile int *
0x18005372f  lea     r8, aCreateasync; "CreateAsync"
0x180053736  mov     rdx, r14; wchar_t *
0x180053739  mov     rcx, rax; this
0x18005373c  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x180053741  nop
0x180053742  lea     rcx, [rbx+98h]
0x180053749  jmp     short loc_1800537BA
0x18005374b  xorps   xmm0, xmm0
0x18005374e  movups  xmmword ptr [rbx+1A0h], xmm0
0x180053755  mov     [rbx+1B0h], rdi
0x18005375c  mov     [rbx+1B8h], rdi
0x180053763  mov     r8d, 2Fh ; '/'
0x180053769  lea     rdx, aMicrosoftWindo_3; "Microsoft.Windows.SemanticSearch.QueryP"...
0x180053770  lea     rcx, [rbx+1A0h]
0x180053777  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18005377c  lea     rcx, [rbx+1A0h]
0x180053783  mov     rax, [rbx+1B8h]
0x18005378a  mov     [rsp+168h+var_68], rax
0x180053792  cmp     rax, 7
0x180053796  jbe     short loc_1800537A7
0x180053798  mov     rcx, [rbx+1A0h]; wchar_t *
0x18005379f  mov     [rsp+168h+var_80], rcx
0x1800537a7  lea     rdx, aCreateasync; "CreateAsync"
0x1800537ae  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x1800537b3  lea     rcx, [rbx+1A0h]
0x1800537ba  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800537bf  nop
0x1800537c0  lea     rcx, [rbx+1C0h]
0x1800537c7  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x1800537cc  mov     rsi, [rax]
0x1800537cf  mov     [rax], rdi
0x1800537d2  mov     [rbx+0B8h], rsi
0x1800537d9  cmp     qword ptr [rbx+1C0h], 0
0x1800537e1  jz      short loc_1800537F4
0x1800537e3  mov     rcx, [rbx+1C0h]; pv
0x1800537ea  mov     [rsp+168h+var_130], rcx
0x1800537ef  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x1800537f4  lea     rdx, [rbx+0C0h]
0x1800537fb  lea     rcx, [rsi+8]
0x1800537ff  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180053804  mov     r12, rsi
0x180053807  test    rsi, rsi
0x18005380a  jnz     short loc_180053846
0x18005380c  lea     rcx, [rbx+1C8h]
0x180053813  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x180053818  mov     rsi, [rax]
0x18005381b  mov     [rax], rdi
0x18005381e  mov     [rbx+0B8h], rsi
0x180053825  mov     r12, rsi
0x180053828  cmp     qword ptr [rbx+1C8h], 0
0x180053830  jz      short loc_180053846
0x180053832  mov     rcx, [rbx+1C8h]; pv
0x180053839  mov     [rsp+168h+var_C0], rcx
0x180053841  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180053846  mov     [rbx+0D0h], rsi
0x18005384d  test    rsi, rsi
0x180053850  jz      short loc_180053859
0x180053852  lock inc dword ptr [rsi+128h]
0x180053859  lea     rcx, [rsi+0C8h]; lpCriticalSection
0x180053860  call    cs:__imp_EnterCriticalSection
0x180053866  nop
0x180053867  lea     rcx, [rsi+108h]; void *
0x18005386e  mov     r8d, 2Fh ; '/'
0x180053874  lea     rdx, aMicrosoftWindo_3; "Microsoft.Windows.SemanticSearch.QueryP"...
0x18005387b  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180053880  nop
0x180053881  test    rsi, rsi
0x180053884  jz      short loc_180053897
0x180053886  lea     rcx, [rsi+8]
0x18005388a  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18005388f  mov     rcx, rsi; pv
0x180053892  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180053897  lea     rax, [rbx+0D8h]
0x18005389e  mov     [rax+8], rdi
0x1800538a2  mov     [rax+10h], rdi
0x1800538a6  mov     [rax+18h], rdi
0x1800538aa  mov     [rax+20h], rdi
0x1800538ae  mov     [rax+28h], rdi
0x1800538b2  mov     [rax+30h], rdi
0x1800538b6  lea     rsi, ??_7?$test_watcher@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>>::`vftable'
0x1800538bd  mov     [rax], rsi
0x1800538c0  mov     [rbx+0E0h], rdi
0x1800538c7  mov     [rbx+0E8h], rax
0x1800538ce  mov     [rbx+0F0h], rdi
0x1800538d5  mov     [rbx+0F8h], edi
0x1800538db  mov     [rbx+100h], rdi
0x1800538e2  lea     rcx, [rbx+108h]
0x1800538e9  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x1800538ee  nop
0x1800538ef  test    r12, r12
0x1800538f2  jnz     short loc_180053927
0x1800538f4  lea     rcx, [rbx+1D0h]
0x1800538fb  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x180053900  mov     rcx, [rax]
0x180053903  mov     [rax], rdi
0x180053906  mov     [rbx+0B8h], rcx
0x18005390d  cmp     [rbx+1D0h], r12
0x180053914  jz      short loc_180053927
0x180053916  mov     rcx, [rbx+1D0h]; pv
0x18005391d  mov     [rsp+168h+var_128], rcx
0x180053922  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180053927  lea     rax, [rbx+110h]
0x18005392e  mov     [rax], rsi
0x180053931  lea     rsi, [rbx+118h]
0x180053938  mov     [rsi], rdi
0x18005393b  mov     [rbx+120h], rax
0x180053942  mov     [rbx+128h], rdi
0x180053949  mov     [rbx+130h], edi
0x18005394f  mov     [rbx+138h], rdi
0x180053956  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18005395e  jz      short loc_180053988
0x180053960  mov     dl, 1
0x180053962  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180053967  mov     [rsi], rax
0x18005396a  test    rax, rax
0x18005396d  jz      short loc_180053988
0x18005396f  mov     rcx, [rax]
0x180053972  mov     [rbx+128h], rcx
0x180053979  mov     [rax], rsi
0x18005397c  call    cs:__imp_GetCurrentThreadId
0x180053982  mov     [rbx+130h], eax
0x180053988  mov     rax, [rbx+0B8h]
0x18005398f  mov     [rbx+140h], rax
0x180053996  test    rax, rax
0x180053999  jz      short loc_1800539AA
0x18005399b  mov     [rsp+168h+var_D0], rax
0x1800539a3  lock inc dword ptr [rax+128h]
0x1800539aa  mov     rcx, [rbx+108h]; pv
0x1800539b1  mov     [rsp+168h+var_88], rcx
0x1800539b9  mov     rax, [rbx+140h]
0x1800539c0  mov     [rbx+108h], rax
0x1800539c7  test    rax, rax
0x1800539ca  jz      short loc_1800539D3
0x1800539cc  lock inc dword ptr [rax+128h]
0x1800539d3  test    rcx, rcx
0x1800539d6  jz      short loc_1800539DD
0x1800539d8  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x1800539dd  cmp     dword ptr [rbx+130h], 0
0x1800539e4  jz      short loc_1800539FD
0x1800539e6  cmp     dword ptr [rbx+0F8h], 0
0x1800539ed  jnz     short loc_180053A13
0x1800539ef  lea     rcx, [rbx+0E0h]; this
0x1800539f6  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800539fb  jmp     short loc_180053A13
0x1800539fd  cmp     dword ptr [rbx+0F8h], 0
0x180053a04  jz      short loc_180053A13
0x180053a06  lea     rcx, [rbx+0E0h]; this
0x180053a0d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180053a12  nop
0x180053a13  mov     rax, [rbx+140h]
0x180053a1a  mov     [rsp+168h+var_F0], rax
0x180053a1f  test    rax, rax
0x180053a22  jz      short loc_180053A35
0x180053a24  mov     rcx, [rbx+140h]; pv
0x180053a2b  mov     [rsp+168h+var_F0], rcx
0x180053a30  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180053a35  mov     eax, [rbx+130h]
0x180053a3b  mov     [rsp+168h+var_100], eax
0x180053a3f  test    eax, eax
0x180053a41  jz      short loc_180053A4B
0x180053a43  mov     rcx, rsi; this
0x180053a46  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180053a4b  lea     rcx, [rbx+148h]
0x180053a52  mov     [rcx], rdi
0x180053a55  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x180053a5a  nop
0x180053a5b  mov     eax, [rbx+0F8h]
0x180053a61  mov     [rsp+168h+var_98], eax
0x180053a68  test    eax, eax
0x180053a6a  jz      short loc_180053A79
0x180053a6c  lea     rcx, [rbx+0E0h]; this
0x180053a73  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180053a78  nop
0x180053a79  mov     byte ptr [rbx+150h], 0
0x180053a80  mov     eax, [rbx+70h]
0x180053a83  cmp     eax, 2
0x180053a86  jnz     short loc_180053AC4
0x180053a88  lea     rdx, [rbx+1D8h]; struct winrt::impl::slim_source_location *
0x180053a8f  mov     dword ptr [rdx], 0F8Ch
0x180053a95  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180053a9c  mov     [rbx+1E0h], rax
0x180053aa3  lea     rcx, [rsp+168h+pExceptionObject]; this
0x180053aab  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180053ab0  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180053ab7  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x180053abf  call    _CxxThrowException
0x180053ac4  mov     ecx, 4
0x180053ac9  mov     rax, [rsp+168h+var_138]
0x180053ace  mov     [rax], cx
0x180053ad1  mov     rdx, rbx
0x180053ad4  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180053ad9  jmp     loc_180053F29
0x180053ade  cmp     qword ptr [rbx+148h], 0; jumptable 000000018005367F case 5
0x180053ae6  jz      short loc_180053B08
0x180053ae8  cmp     qword ptr [rbx+148h], 0FFFFFFFFFFFFFFFFh
0x180053af0  jz      short loc_180053B08
0x180053af2  mov     rcx, [rbx+148h]; hObject
0x180053af9  mov     [rsp+168h+var_C8], rcx
0x180053b01  call    cs:__imp_CloseHandle
0x180053b07  nop
0x180053b08  mov     rax, [rbx+108h]
0x180053b0f  mov     [rsp+168h+var_88], rax
0x180053b17  test    rax, rax
0x180053b1a  jz      short loc_180053B30
0x180053b1c  mov     rcx, [rbx+108h]; pv
0x180053b23  mov     [rsp+168h+var_88], rcx
0x180053b2b  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180053b30  mov     eax, [rbx+0F8h]
0x180053b36  mov     [rsp+168h+var_98], eax
0x180053b3d  test    eax, eax
0x180053b3f  jz      short loc_180053B4E
0x180053b41  lea     rcx, [rbx+0E0h]; this
0x180053b48  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180053b4d  nop
0x180053b4e  cmp     qword ptr [rbx+0B8h], 0
0x180053b56  jz      short loc_180053B6D
0x180053b58  mov     rcx, [rbx+0B8h]; pv
0x180053b5f  mov     [rsp+168h+var_D0], rcx
0x180053b67  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180053b6c  nop
0x180053b6d  jmp     loc_180053F06; jumptable 000000018005367F cases -1,1
0x180053b72  cmp     qword ptr [rbx+0B8h], 0; jumptable 000000018005367F case 4
0x180053b7a  jnz     short loc_180053BB3
0x180053b7c  lea     rcx, [rbx+1E8h]
0x180053b83  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x180053b88  mov     rcx, [rax]
0x180053b8b  xor     edi, edi
0x180053b8d  mov     [rax], rdi
0x180053b90  mov     [rbx+0B8h], rcx
0x180053b97  cmp     [rbx+1E8h], rdi
0x180053b9e  jz      short loc_180053BB5
0x180053ba0  mov     rcx, [rbx+1E8h]; pv
0x180053ba7  mov     [rsp+168h+var_128], rcx
0x180053bac  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180053bb1  jmp     short loc_180053BB5
0x180053bb3  xor     edi, edi
0x180053bb5  lea     rax, [rbx+158h]
0x180053bbc  lea     rsi, ??_7?$test_watcher@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>>::`vftable'
0x180053bc3  mov     [rax], rsi
  ... truncated ...
```
