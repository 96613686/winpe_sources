# AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::Tokenizer_winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer_winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2_0_::CreateAsync$_ResumeCoro$1_winrt::Microsoft::Windows::SemanticSearch::Tokenizer_

- ea: `0x18005bc90`
- end: `0x18005c5f4`
- name: `AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::Tokenizer_winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer_winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2_0_::CreateAsync$_ResumeCoro$1_winrt::Microsoft::Windows::SemanticSearch::Tokenizer_`
- size: `2404`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18003fd50`
- `0x18005bc80`

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
- `0x1800408b0`
- `0x18004c070`
- `0x18004c090`
- `0x18004ecf0`
- `0x18005bc90`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005bffc`
- `KERNEL32!GetCurrentThreadId` at `0x18005c291`
- `KERNEL32!GetCurrentThreadId` at `0x18005bffc`
- `KERNEL32!GetCurrentThreadId` at `0x18005c291`
- `KERNEL32!CloseHandle` at `0x18005c181`
- `KERNEL32!CloseHandle` at `0x18005c409`
- `KERNEL32!CloseHandle` at `0x18005c427`
- `KERNEL32!CloseHandle` at `0x18005c4ed`
- `KERNEL32!CloseHandle` at `0x18005c181`
- `KERNEL32!CloseHandle` at `0x18005c409`
- `KERNEL32!CloseHandle` at `0x18005c427`
- `KERNEL32!CloseHandle` at `0x18005c4ed`
- `KERNEL32!LeaveCriticalSection` at `0x18005c483`
- `KERNEL32!LeaveCriticalSection` at `0x18005c483`
- `KERNEL32!EnterCriticalSection` at `0x18005bee0`
- `KERNEL32!EnterCriticalSection` at `0x18005c456`
- `KERNEL32!EnterCriticalSection` at `0x18005bee0`
- `KERNEL32!EnterCriticalSection` at `0x18005c456`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005c3f1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005c3f1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005c3bd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005c3bd`

## string_xrefs

- `0x18005bd52`: `Microsoft.Windows.SemanticSearch.Tokenizer`
- `0x18005bde9`: `Microsoft.Windows.SemanticSearch.Tokenizer`
- `0x18005bef4`: `Microsoft.Windows.SemanticSearch.Tokenizer`
- `0x18005bdaf`: `CreateAsync`
- `0x18005be27`: `CreateAsync`

## pseudocode

```c
void __fastcall AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::Tokenizer_winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer_winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2_0_::CreateAsync__ResumeCoro_1_winrt::Microsoft::Windows::SemanticSearch::Tokenizer_(
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
        if ( _InterlockedIncrement(&`AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>'::`7'::__apiCallCounter) != 1 )
          goto LABEL_14;
        *(_OWORD *)(v1 + 76) = 0;
        *((_QWORD *)v1 + 21) = 0;
        *((_QWORD *)v1 + 22) = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (_QWORD *)v1 + 19,
          L"Microsoft.Windows.SemanticSearch.Tokenizer",
          0x2Au);
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
            &`AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>'::`7'::__apiCallCounter);
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
          L"Microsoft.Windows.SemanticSearch.Tokenizer",
          0x2Au);
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
      std::wstring::assign((void *)(v9 + 264), L"Microsoft.Windows.SemanticSearch.Tokenizer");
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
        `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>'::`2'::_lambda_1_::operator()(
          (__int64)retaddr,
          v1 + 200);
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
        `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>'::`2'::_lambda_1_::operator()(
          v29,
          v1 + 200);
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
0x18005bc90  mov     r11, rsp
0x18005bc93  mov     [r11+10h], rbx
0x18005bc97  mov     [r11+18h], rsi
0x18005bc9b  mov     [r11+8], rcx
0x18005bc9f  push    rdi
0x18005bca0  push    r12
0x18005bca2  push    r13
0x18005bca4  push    r14
0x18005bca6  push    r15
0x18005bca8  sub     rsp, 140h
0x18005bcaf  mov     rax, cs:__security_cookie
0x18005bcb6  xor     rax, rsp
0x18005bcb9  mov     [rsp+168h+var_30], rax
0x18005bcc1  mov     rbx, rcx
0x18005bcc4  mov     [rsp+168h+var_140], rcx
0x18005bcc9  lea     rax, [rbx+94h]
0x18005bcd0  mov     [rsp+168h+var_138], rax
0x18005bcd5  movzx   eax, word ptr [rax]
0x18005bcd8  mov     [rsp+168h+var_148], ax
0x18005bcdd  inc     ax; switch 7 cases
0x18005bce0  cmp     ax, 6
0x18005bce4  ja      def_18005BCFF; jumptable 000000018005BCFF default case, case 0
0x18005bcea  movsx   rax, ax
0x18005bcee  lea     rdx, cs:180000000h
0x18005bcf5  mov     ecx, ds:(jpt_18005BCFF - 180000000h)[rdx+rax*4]
0x18005bcfc  add     rcx, rdx
0x18005bcff  jmp     rcx; switch jump
0x18005bd01  jmp     loc_18005C586; jumptable 000000018005BCFF case 3
0x18005bd06  xor     edi, edi; jumptable 000000018005BCFF case 2
0x18005bd08  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x18005bd0f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x18005bd14  test    al, al
0x18005bd16  jz      loc_18005BDCB
0x18005bd1c  mov     eax, 1
0x18005bd21  lock xadd cs:?__apiCallCounter@?6???$CreateAsync@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@?$SessionWrapper@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UITokenizerSession2@SemanticSearchInternal@345@$0A@@AIFabricHelpers@@SA?AU?$IAsyncOperation@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@6@@Z@4JC, eax; long volatile `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>(winrt::guid)'::`7'::__apiCallCounter
0x18005bd29  inc     eax
0x18005bd2b  cmp     eax, 1
0x18005bd2e  jnz     loc_18005BE40
0x18005bd34  xorps   xmm0, xmm0
0x18005bd37  movups  xmmword ptr [rbx+98h], xmm0
0x18005bd3e  mov     [rbx+0A8h], rdi
0x18005bd45  mov     [rbx+0B0h], rdi
0x18005bd4c  mov     r8d, 2Ah ; '*'
0x18005bd52  lea     rdx, aMicrosoftWindo_8; "Microsoft.Windows.SemanticSearch.Tokeni"...
0x18005bd59  lea     rcx, [rbx+98h]
0x18005bd60  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18005bd65  lea     r14, [rbx+98h]
0x18005bd6c  mov     rax, [rbx+0B0h]
0x18005bd73  mov     [rsp+168h+var_68], rax
0x18005bd7b  cmp     rax, 7
0x18005bd7f  jbe     short loc_18005BD90
0x18005bd81  mov     r14, [rbx+98h]
0x18005bd88  mov     [rsp+168h+var_80], r14
0x18005bd90  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18005bd95  mov     rcx, [rax+8]
0x18005bd99  test    rcx, rcx
0x18005bd9c  jz      short loc_18005BDC2
0x18005bd9e  cmp     dword ptr [rcx], 0
0x18005bda1  jbe     short loc_18005BDC2
0x18005bda3  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18005bda8  lea     r9, ?__apiCallCounter@?6???$CreateAsync@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@?$SessionWrapper@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UITokenizerSession2@SemanticSearchInternal@345@$0A@@AIFabricHelpers@@SA?AU?$IAsyncOperation@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@6@@Z@4JC; volatile int *
0x18005bdaf  lea     r8, aCreateasync; "CreateAsync"
0x18005bdb6  mov     rdx, r14; wchar_t *
0x18005bdb9  mov     rcx, rax; this
0x18005bdbc  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x18005bdc1  nop
0x18005bdc2  lea     rcx, [rbx+98h]
0x18005bdc9  jmp     short loc_18005BE3A
0x18005bdcb  xorps   xmm0, xmm0
0x18005bdce  movups  xmmword ptr [rbx+1A0h], xmm0
0x18005bdd5  mov     [rbx+1B0h], rdi
0x18005bddc  mov     [rbx+1B8h], rdi
0x18005bde3  mov     r8d, 2Ah ; '*'
0x18005bde9  lea     rdx, aMicrosoftWindo_8; "Microsoft.Windows.SemanticSearch.Tokeni"...
0x18005bdf0  lea     rcx, [rbx+1A0h]
0x18005bdf7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18005bdfc  lea     rcx, [rbx+1A0h]
0x18005be03  mov     rax, [rbx+1B8h]
0x18005be0a  mov     [rsp+168h+var_68], rax
0x18005be12  cmp     rax, 7
0x18005be16  jbe     short loc_18005BE27
0x18005be18  mov     rcx, [rbx+1A0h]; wchar_t *
0x18005be1f  mov     [rsp+168h+var_80], rcx
0x18005be27  lea     rdx, aCreateasync; "CreateAsync"
0x18005be2e  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x18005be33  lea     rcx, [rbx+1A0h]
0x18005be3a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005be3f  nop
0x18005be40  lea     rcx, [rbx+1C0h]
0x18005be47  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x18005be4c  mov     rsi, [rax]
0x18005be4f  mov     [rax], rdi
0x18005be52  mov     [rbx+0B8h], rsi
0x18005be59  cmp     qword ptr [rbx+1C0h], 0
0x18005be61  jz      short loc_18005BE74
0x18005be63  mov     rcx, [rbx+1C0h]; pv
0x18005be6a  mov     [rsp+168h+var_130], rcx
0x18005be6f  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x18005be74  lea     rdx, [rbx+0C0h]
0x18005be7b  lea     rcx, [rsi+8]
0x18005be7f  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18005be84  mov     r12, rsi
0x18005be87  test    rsi, rsi
0x18005be8a  jnz     short loc_18005BEC6
0x18005be8c  lea     rcx, [rbx+1C8h]
0x18005be93  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x18005be98  mov     rsi, [rax]
0x18005be9b  mov     [rax], rdi
0x18005be9e  mov     [rbx+0B8h], rsi
0x18005bea5  mov     r12, rsi
0x18005bea8  cmp     qword ptr [rbx+1C8h], 0
0x18005beb0  jz      short loc_18005BEC6
0x18005beb2  mov     rcx, [rbx+1C8h]; pv
0x18005beb9  mov     [rsp+168h+var_C0], rcx
0x18005bec1  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x18005bec6  mov     [rbx+0D0h], rsi
0x18005becd  test    rsi, rsi
0x18005bed0  jz      short loc_18005BED9
0x18005bed2  lock inc dword ptr [rsi+128h]
0x18005bed9  lea     rcx, [rsi+0C8h]; lpCriticalSection
0x18005bee0  call    cs:__imp_EnterCriticalSection
0x18005bee6  nop
0x18005bee7  lea     rcx, [rsi+108h]; void *
0x18005beee  mov     r8d, 2Ah ; '*'
0x18005bef4  lea     rdx, aMicrosoftWindo_8; "Microsoft.Windows.SemanticSearch.Tokeni"...
0x18005befb  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x18005bf00  nop
0x18005bf01  test    rsi, rsi
0x18005bf04  jz      short loc_18005BF17
0x18005bf06  lea     rcx, [rsi+8]
0x18005bf0a  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18005bf0f  mov     rcx, rsi; pv
0x18005bf12  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x18005bf17  lea     rax, [rbx+0D8h]
0x18005bf1e  mov     [rax+8], rdi
0x18005bf22  mov     [rax+10h], rdi
0x18005bf26  mov     [rax+18h], rdi
0x18005bf2a  mov     [rax+20h], rdi
0x18005bf2e  mov     [rax+28h], rdi
0x18005bf32  mov     [rax+30h], rdi
0x18005bf36  lea     rsi, ??_7?$test_watcher@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>>::`vftable'
0x18005bf3d  mov     [rax], rsi
0x18005bf40  mov     [rbx+0E0h], rdi
0x18005bf47  mov     [rbx+0E8h], rax
0x18005bf4e  mov     [rbx+0F0h], rdi
0x18005bf55  mov     [rbx+0F8h], edi
0x18005bf5b  mov     [rbx+100h], rdi
0x18005bf62  lea     rcx, [rbx+108h]
0x18005bf69  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x18005bf6e  nop
0x18005bf6f  test    r12, r12
0x18005bf72  jnz     short loc_18005BFA7
0x18005bf74  lea     rcx, [rbx+1D0h]
0x18005bf7b  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x18005bf80  mov     rcx, [rax]
0x18005bf83  mov     [rax], rdi
0x18005bf86  mov     [rbx+0B8h], rcx
0x18005bf8d  cmp     [rbx+1D0h], r12
0x18005bf94  jz      short loc_18005BFA7
0x18005bf96  mov     rcx, [rbx+1D0h]; pv
0x18005bf9d  mov     [rsp+168h+var_128], rcx
0x18005bfa2  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x18005bfa7  lea     rax, [rbx+110h]
0x18005bfae  mov     [rax], rsi
0x18005bfb1  lea     rsi, [rbx+118h]
0x18005bfb8  mov     [rsi], rdi
0x18005bfbb  mov     [rbx+120h], rax
0x18005bfc2  mov     [rbx+128h], rdi
0x18005bfc9  mov     [rbx+130h], edi
0x18005bfcf  mov     [rbx+138h], rdi
0x18005bfd6  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18005bfde  jz      short loc_18005C008
0x18005bfe0  mov     dl, 1
0x18005bfe2  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18005bfe7  mov     [rsi], rax
0x18005bfea  test    rax, rax
0x18005bfed  jz      short loc_18005C008
0x18005bfef  mov     rcx, [rax]
0x18005bff2  mov     [rbx+128h], rcx
0x18005bff9  mov     [rax], rsi
0x18005bffc  call    cs:__imp_GetCurrentThreadId
0x18005c002  mov     [rbx+130h], eax
0x18005c008  mov     rax, [rbx+0B8h]
0x18005c00f  mov     [rbx+140h], rax
0x18005c016  test    rax, rax
0x18005c019  jz      short loc_18005C02A
0x18005c01b  mov     [rsp+168h+var_D0], rax
0x18005c023  lock inc dword ptr [rax+128h]
0x18005c02a  mov     rcx, [rbx+108h]; pv
0x18005c031  mov     [rsp+168h+var_88], rcx
0x18005c039  mov     rax, [rbx+140h]
0x18005c040  mov     [rbx+108h], rax
0x18005c047  test    rax, rax
0x18005c04a  jz      short loc_18005C053
0x18005c04c  lock inc dword ptr [rax+128h]
0x18005c053  test    rcx, rcx
0x18005c056  jz      short loc_18005C05D
0x18005c058  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x18005c05d  cmp     dword ptr [rbx+130h], 0
0x18005c064  jz      short loc_18005C07D
0x18005c066  cmp     dword ptr [rbx+0F8h], 0
0x18005c06d  jnz     short loc_18005C093
0x18005c06f  lea     rcx, [rbx+0E0h]; this
0x18005c076  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18005c07b  jmp     short loc_18005C093
0x18005c07d  cmp     dword ptr [rbx+0F8h], 0
0x18005c084  jz      short loc_18005C093
0x18005c086  lea     rcx, [rbx+0E0h]; this
0x18005c08d  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005c092  nop
0x18005c093  mov     rax, [rbx+140h]
0x18005c09a  mov     [rsp+168h+var_F0], rax
0x18005c09f  test    rax, rax
0x18005c0a2  jz      short loc_18005C0B5
0x18005c0a4  mov     rcx, [rbx+140h]; pv
0x18005c0ab  mov     [rsp+168h+var_F0], rcx
0x18005c0b0  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x18005c0b5  mov     eax, [rbx+130h]
0x18005c0bb  mov     [rsp+168h+var_100], eax
0x18005c0bf  test    eax, eax
0x18005c0c1  jz      short loc_18005C0CB
0x18005c0c3  mov     rcx, rsi; this
0x18005c0c6  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005c0cb  lea     rcx, [rbx+148h]
0x18005c0d2  mov     [rcx], rdi
0x18005c0d5  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18005c0da  nop
0x18005c0db  mov     eax, [rbx+0F8h]
0x18005c0e1  mov     [rsp+168h+var_98], eax
0x18005c0e8  test    eax, eax
0x18005c0ea  jz      short loc_18005C0F9
0x18005c0ec  lea     rcx, [rbx+0E0h]; this
0x18005c0f3  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005c0f8  nop
0x18005c0f9  mov     byte ptr [rbx+150h], 0
0x18005c100  mov     eax, [rbx+70h]
0x18005c103  cmp     eax, 2
0x18005c106  jnz     short loc_18005C144
0x18005c108  lea     rdx, [rbx+1D8h]; struct winrt::impl::slim_source_location *
0x18005c10f  mov     dword ptr [rdx], 0F8Ch
0x18005c115  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005c11c  mov     [rbx+1E0h], rax
0x18005c123  lea     rcx, [rsp+168h+pExceptionObject]; this
0x18005c12b  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18005c130  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18005c137  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18005c13f  call    _CxxThrowException
0x18005c144  mov     ecx, 4
0x18005c149  mov     rax, [rsp+168h+var_138]
0x18005c14e  mov     [rax], cx
0x18005c151  mov     rdx, rbx
0x18005c154  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18005c159  jmp     loc_18005C5A9
0x18005c15e  cmp     qword ptr [rbx+148h], 0; jumptable 000000018005BCFF case 5
0x18005c166  jz      short loc_18005C188
0x18005c168  cmp     qword ptr [rbx+148h], 0FFFFFFFFFFFFFFFFh
0x18005c170  jz      short loc_18005C188
0x18005c172  mov     rcx, [rbx+148h]; hObject
0x18005c179  mov     [rsp+168h+var_C8], rcx
0x18005c181  call    cs:__imp_CloseHandle
0x18005c187  nop
0x18005c188  mov     rax, [rbx+108h]
0x18005c18f  mov     [rsp+168h+var_88], rax
0x18005c197  test    rax, rax
0x18005c19a  jz      short loc_18005C1B0
0x18005c19c  mov     rcx, [rbx+108h]; pv
0x18005c1a3  mov     [rsp+168h+var_88], rcx
0x18005c1ab  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x18005c1b0  mov     eax, [rbx+0F8h]
0x18005c1b6  mov     [rsp+168h+var_98], eax
0x18005c1bd  test    eax, eax
0x18005c1bf  jz      short loc_18005C1CE
0x18005c1c1  lea     rcx, [rbx+0E0h]; this
0x18005c1c8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18005c1cd  nop
0x18005c1ce  cmp     qword ptr [rbx+0B8h], 0
0x18005c1d6  jz      short loc_18005C1ED
0x18005c1d8  mov     rcx, [rbx+0B8h]; pv
0x18005c1df  mov     [rsp+168h+var_D0], rcx
0x18005c1e7  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x18005c1ec  nop
0x18005c1ed  jmp     loc_18005C586; jumptable 000000018005BCFF cases -1,1
0x18005c1f2  cmp     qword ptr [rbx+0B8h], 0; jumptable 000000018005BCFF case 4
0x18005c1fa  jnz     short loc_18005C233
0x18005c1fc  lea     rcx, [rbx+1E8h]
0x18005c203  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x18005c208  mov     rcx, [rax]
0x18005c20b  xor     edi, edi
0x18005c20d  mov     [rax], rdi
0x18005c210  mov     [rbx+0B8h], rcx
0x18005c217  cmp     [rbx+1E8h], rdi
0x18005c21e  jz      short loc_18005C235
0x18005c220  mov     rcx, [rbx+1E8h]; pv
0x18005c227  mov     [rsp+168h+var_128], rcx
0x18005c22c  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x18005c231  jmp     short loc_18005C235
0x18005c233  xor     edi, edi
0x18005c235  lea     rax, [rbx+158h]
0x18005c23c  lea     rsi, ??_7?$test_watcher@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>>::`vftable'
0x18005c243  mov     [rax], rsi
  ... truncated ...
```
