# AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::CreateAsync$_ResumeCoro$1_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_

- ea: `0x1800583b0`
- end: `0x180058d40`
- name: `AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::CreateAsync$_ResumeCoro$1_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_`
- size: `2448`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180035180`
- `0x1800583a0`

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
- `0x1800352d0`
- `0x18004c070`
- `0x18004c090`
- `0x18004ecf0`
- `0x1800583b0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18005871c`
- `KERNEL32!GetCurrentThreadId` at `0x1800589b1`
- `KERNEL32!GetCurrentThreadId` at `0x18005871c`
- `KERNEL32!GetCurrentThreadId` at `0x1800589b1`
- `KERNEL32!CloseHandle` at `0x1800588a1`
- `KERNEL32!CloseHandle` at `0x180058b45`
- `KERNEL32!CloseHandle` at `0x180058b63`
- `KERNEL32!CloseHandle` at `0x180058c30`
- `KERNEL32!CloseHandle` at `0x1800588a1`
- `KERNEL32!CloseHandle` at `0x180058b45`
- `KERNEL32!CloseHandle` at `0x180058b63`
- `KERNEL32!CloseHandle` at `0x180058c30`
- `KERNEL32!LeaveCriticalSection` at `0x180058bc6`
- `KERNEL32!LeaveCriticalSection` at `0x180058bc6`
- `KERNEL32!EnterCriticalSection` at `0x180058600`
- `KERNEL32!EnterCriticalSection` at `0x180058b99`
- `KERNEL32!EnterCriticalSection` at `0x180058600`
- `KERNEL32!EnterCriticalSection` at `0x180058b99`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180058b2d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180058b2d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180058af2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180058af2`

## string_xrefs

- `0x1800584cf`: `CreateAsync`
- `0x180058547`: `CreateAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator_winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2_2_::CreateAsync__ResumeCoro_1_winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator_(
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
  void *v28; // r12
  LPVOID *v29; // rsi
  void *v30; // r14
  unsigned int v31; // r8d
  const char *v32; // r9
  wil::details::in1diag3 *v33; // rcx
  __int64 v34; // rsi
  _QWORD *v35; // rsi
  _QWORD *v36; // r14
  _WORD *v37; // [rsp+30h] [rbp-138h]
  _BYTE pExceptionObject[24]; // [rsp+80h] [rbp-E8h] BYREF
  volatile signed __int32 *v39; // [rsp+98h] [rbp-D0h]
  HANDLE v40; // [rsp+A0h] [rbp-C8h]
  LPVOID v41; // [rsp+A8h] [rbp-C0h]
  int v42; // [rsp+D0h] [rbp-98h]
  LPVOID v43; // [rsp+E0h] [rbp-88h]
  const wchar_t *v44; // [rsp+E8h] [rbp-80h]
  unsigned __int64 v45; // [rsp+100h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v1 = a1;
  v37 = (_WORD *)a1 + 74;
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
        if ( _InterlockedIncrement(&`AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2,2>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator>'::`7'::__apiCallCounter) != 1 )
          goto LABEL_14;
        *(_OWORD *)(v1 + 76) = 0;
        *((_QWORD *)v1 + 21) = 0;
        *((_QWORD *)v1 + 22) = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (_QWORD *)v1 + 19,
          L"Microsoft.Windows.SemanticSearch.SemanticTextEmbeddingsCreator",
          0x3Eu);
        v3 = v1 + 76;
        v45 = *((_QWORD *)v1 + 22);
        if ( v45 > 7 )
        {
          v3 = (const wchar_t *)*((_QWORD *)v1 + 19);
          v44 = v3;
        }
        v4 = (_DWORD *)*((_QWORD *)TelemetryLogger::Instance() + 1);
        if ( v4 && *v4 )
        {
          v5 = TelemetryLogger::Instance();
          TelemetryLogger::InitApiData_(
            v5,
            v3,
            L"CreateAsync",
            &`AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2,2>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator>'::`7'::__apiCallCounter);
        }
        v6 = (__int64)(v1 + 76);
      }
      else
      {
        *(_OWORD *)(v1 + 212) = 0;
        *((_QWORD *)v1 + 55) = 0;
        *((_QWORD *)v1 + 56) = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (_QWORD *)v1 + 53,
          L"Microsoft.Windows.SemanticSearch.SemanticTextEmbeddingsCreator",
          0x3Eu);
        v7 = v1 + 212;
        v45 = *((_QWORD *)v1 + 56);
        if ( v45 > 7 )
        {
          v7 = (const wchar_t *)*((_QWORD *)v1 + 53);
          v44 = v7;
        }
        TelemetryLogger::LogWclApiUsage(v7, L"CreateAsync");
        v6 = (__int64)(v1 + 212);
      }
      std::wstring::_Tidy_deallocate(v6);
LABEL_14:
      Async = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>((_QWORD *)v1 + 57);
      v9 = *Async;
      *Async = 0;
      *((_QWORD *)v1 + 23) = v9;
      if ( *((_QWORD *)v1 + 57) )
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(*((LPVOID *)v1 + 57));
      tip2::details::shared_data<0,0,0>::start(v9 + 8, v1 + 96);
      v10 = v9;
      if ( !v9 )
      {
        v11 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>((_QWORD *)v1 + 58);
        v9 = *v11;
        *v11 = 0;
        *((_QWORD *)v1 + 23) = v9;
        v10 = v9;
        if ( *((_QWORD *)v1 + 58) )
        {
          v41 = (LPVOID)*((_QWORD *)v1 + 58);
          tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(v41);
        }
      }
      *((_QWORD *)v1 + 26) = v9;
      if ( v9 )
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 296));
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
      std::wstring::assign((void *)(v9 + 264), L"Microsoft.Windows.SemanticSearch.SemanticTextEmbeddingsCreator");
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
        v14 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>((_QWORD *)v1 + 59);
        v13 = *v14;
        *v14 = 0;
        *((_QWORD *)v1 + 23) = v13;
        if ( *((_QWORD *)v1 + 59) )
          tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(*((LPVOID *)v1 + 59));
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
        v39 = v17;
        _InterlockedIncrement(v17 + 74);
      }
      v18 = (void *)*((_QWORD *)v1 + 33);
      v43 = v18;
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
      v42 = *((_DWORD *)v1 + 62);
      if ( v42 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v1 + 112));
      *((_BYTE *)v1 + 336) = 0;
      if ( *((_DWORD *)v1 + 28) == 2 )
      {
        *((_DWORD *)v1 + 120) = 3980;
        *((_QWORD *)v1 + 61) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(v1 + 240));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v37 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(4, v1);
      return;
    case 4:
      if ( !a1[23] )
      {
        v21 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(a1 + 62);
        a1 = (_QWORD *)*v21;
        *v21 = 0;
        *((_QWORD *)v1 + 23) = a1;
        if ( *((_QWORD *)v1 + 62) )
          tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(*((LPVOID *)v1 + 62));
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
      *((_QWORD *)v1 + 50) = v1 + 66;
      v28 = (void *)*((_QWORD *)v1 + 41);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_LocalService_Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIFabric_LocalService_Support>::GetImpl'::`2'::impl)
        && v28 )
      {
        v29 = (LPVOID *)(v1 + 252);
        *((_QWORD *)v1 + 63) = 0;
        ImpersonationHelper::GetThreadImpersonationToken(v1 + 252);
        v30 = (void *)*((_QWORD *)v1 + 63);
        *((_QWORD *)v1 + 63) = 0;
        *((_QWORD *)v1 + 64) = v30;
        if ( !ImpersonateLoggedOnUser(v28) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x23, v31, v32);
        `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2,2>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator>'::`2'::_lambda_1_::operator()(
          (__int128 **)v1 + 50,
          (_QWORD *)v1 + 51);
        if ( v30 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v30) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v33);
          if ( v30 )
            CloseHandle(v30);
        }
        if ( *v29 && *v29 != (LPVOID)-1LL )
        {
          v41 = *v29;
          CloseHandle(v41);
        }
      }
      else
      {
        `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2,2>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator>'::`2'::_lambda_1_::operator()(
          (__int128 **)v1 + 50,
          (_QWORD *)v1 + 51);
      }
      if ( *((_QWORD *)v1 + 23) )
      {
        v34 = *((_QWORD *)v1 + 23);
        EnterCriticalSection((LPCRITICAL_SECTION)(v34 + 200));
        *(_DWORD *)(v34 + 72) |= 0x300u;
        if ( *(_QWORD *)(v34 + 240) )
          tip2::details::shared_data<0,0,0>::complete_helper(v34 + 8, 2u);
        if ( v34 != -200 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v34 + 200));
      }
      v35 = v1 + 60;
      v36 = v1 + 204;
      if ( v1 + 60 == v1 + 204 )
      {
        if ( *v36 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v1 + 204);
      }
      else
      {
        if ( *v35 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v1 + 60);
        *v35 = *v36;
      }
      if ( *((_QWORD *)v1 + 41) && *((_QWORD *)v1 + 41) != -1 )
      {
        v40 = (HANDLE)*((_QWORD *)v1 + 41);
        CloseHandle(v40);
      }
      v43 = (LPVOID)*((_QWORD *)v1 + 33);
      if ( v43 )
      {
        v43 = (LPVOID)*((_QWORD *)v1 + 33);
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(v43);
      }
      v42 = *((_DWORD *)v1 + 62);
      if ( v42 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v1 + 112));
      if ( *((_QWORD *)v1 + 23) )
      {
        v39 = (volatile signed __int32 *)*((_QWORD *)v1 + 23);
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release((LPVOID)v39);
      }
      *((_QWORD *)v1 + 52) = v1 + 8;
      *v37 = 0;
      *(_QWORD *)v1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)v1 + 52) )
        goto LABEL_116;
      return;
    case 5:
      if ( a1[41] && a1[41] != -1 )
      {
        v20 = (void *)a1[41];
        v40 = (HANDLE)*((_QWORD *)v1 + 41);
        CloseHandle(v20);
      }
      v43 = (LPVOID)*((_QWORD *)v1 + 33);
      if ( v43 )
      {
        v43 = (LPVOID)*((_QWORD *)v1 + 33);
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(v43);
      }
      v42 = *((_DWORD *)v1 + 62);
      if ( v42 )
        wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v1 + 112));
      if ( *((_QWORD *)v1 + 23) )
      {
        v39 = (volatile signed __int32 *)*((_QWORD *)v1 + 23);
        tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release((LPVOID)v39);
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
0x1800583b0  mov     r11, rsp
0x1800583b3  mov     [r11+10h], rbx
0x1800583b7  mov     [r11+18h], rsi
0x1800583bb  mov     [r11+8], rcx
0x1800583bf  push    rdi
0x1800583c0  push    r12
0x1800583c2  push    r13
0x1800583c4  push    r14
0x1800583c6  push    r15
0x1800583c8  sub     rsp, 140h
0x1800583cf  mov     rax, cs:__security_cookie
0x1800583d6  xor     rax, rsp
0x1800583d9  mov     [rsp+168h+var_30], rax
0x1800583e1  mov     rbx, rcx
0x1800583e4  mov     [rsp+168h+var_140], rcx
0x1800583e9  lea     rax, [rbx+94h]
0x1800583f0  mov     [rsp+168h+var_138], rax
0x1800583f5  movzx   eax, word ptr [rax]
0x1800583f8  mov     [rsp+168h+var_148], ax
0x1800583fd  inc     ax; switch 7 cases
0x180058400  cmp     ax, 6
0x180058404  ja      def_18005841F; jumptable 000000018005841F default case, case 0
0x18005840a  movsx   rax, ax
0x18005840e  lea     rdx, cs:180000000h
0x180058415  mov     ecx, ds:(jpt_18005841F - 180000000h)[rdx+rax*4]
0x18005841c  add     rcx, rdx
0x18005841f  jmp     rcx; switch jump
0x180058421  jmp     loc_180058CD0; jumptable 000000018005841F case 3
0x180058426  xor     edi, edi; jumptable 000000018005841F case 2
0x180058428  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x18005842f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x180058434  test    al, al
0x180058436  jz      loc_1800584EB
0x18005843c  mov     eax, 1
0x180058441  lock xadd cs:?__apiCallCounter@?6???$CreateAsync@USemanticTextEmbeddingsCreator@SemanticSearch@Windows@Microsoft@winrt@@@?$SessionWrapper@USemanticTextEmbeddingsCreator@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UISemanticTextSession2@SemanticSearchInternal@345@$01@AIFabricHelpers@@SA?AU?$IAsyncOperation@USemanticTextEmbeddingsCreator@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@6@@Z@4JC, eax; long volatile `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator,winrt::Microsoft::Windows::SemanticSearchInternal::ISemanticTextSession2,2>::CreateAsync<winrt::Microsoft::Windows::SemanticSearch::SemanticTextEmbeddingsCreator>(winrt::guid)'::`7'::__apiCallCounter
0x180058449  inc     eax
0x18005844b  cmp     eax, 1
0x18005844e  jnz     loc_180058560
0x180058454  xorps   xmm0, xmm0
0x180058457  movups  xmmword ptr [rbx+98h], xmm0
0x18005845e  mov     [rbx+0A8h], rdi
0x180058465  mov     [rbx+0B0h], rdi
0x18005846c  mov     r8d, 3Eh ; '>'
0x180058472  lea     rdx, aMicrosoftWindo_27; "Microsoft.Windows.SemanticSearch.Semant"...
0x180058479  lea     rcx, [rbx+98h]
0x180058480  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180058485  lea     r14, [rbx+98h]
0x18005848c  mov     rax, [rbx+0B0h]
0x180058493  mov     [rsp+168h+var_68], rax
0x18005849b  cmp     rax, 7
0x18005849f  jbe     short loc_1800584B0
0x1800584a1  mov     r14, [rbx+98h]
0x1800584a8  mov     [rsp+168h+var_80], r14
0x1800584b0  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800584b5  mov     rcx, [rax+8]
0x1800584b9  test    rcx, rcx
0x1800584bc  jz      short loc_1800584E2
0x1800584be  cmp     dword ptr [rcx], 0
0x1800584c1  jbe     short loc_1800584E2
0x1800584c3  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800584c8  lea     r9, ?__apiCallCounter@?6???$CreateAsync@USemanticTextEmbeddingsCreator@SemanticSearch@Windows@Microsoft@winrt@@@?$SessionWrapper@USemanticTextEmbeddingsCreator@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UISemanticTextSession2@SemanticSearchInternal@345@$01@AIFabricHelpers@@SA?AU?$IAsyncOperation@USemanticTextEmbeddingsCreator@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@6@@Z@4JC; volatile int *
0x1800584cf  lea     r8, aCreateasync; "CreateAsync"
0x1800584d6  mov     rdx, r14; wchar_t *
0x1800584d9  mov     rcx, rax; this
0x1800584dc  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x1800584e1  nop
0x1800584e2  lea     rcx, [rbx+98h]
0x1800584e9  jmp     short loc_18005855A
0x1800584eb  xorps   xmm0, xmm0
0x1800584ee  movups  xmmword ptr [rbx+1A8h], xmm0
0x1800584f5  mov     [rbx+1B8h], rdi
0x1800584fc  mov     [rbx+1C0h], rdi
0x180058503  mov     r8d, 3Eh ; '>'
0x180058509  lea     rdx, aMicrosoftWindo_27; "Microsoft.Windows.SemanticSearch.Semant"...
0x180058510  lea     rcx, [rbx+1A8h]
0x180058517  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18005851c  lea     rcx, [rbx+1A8h]
0x180058523  mov     rax, [rbx+1C0h]
0x18005852a  mov     [rsp+168h+var_68], rax
0x180058532  cmp     rax, 7
0x180058536  jbe     short loc_180058547
0x180058538  mov     rcx, [rbx+1A8h]; wchar_t *
0x18005853f  mov     [rsp+168h+var_80], rcx
0x180058547  lea     rdx, aCreateasync; "CreateAsync"
0x18005854e  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x180058553  lea     rcx, [rbx+1A8h]
0x18005855a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005855f  nop
0x180058560  lea     rcx, [rbx+1C8h]
0x180058567  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x18005856c  mov     rsi, [rax]
0x18005856f  mov     [rax], rdi
0x180058572  mov     [rbx+0B8h], rsi
0x180058579  cmp     qword ptr [rbx+1C8h], 0
0x180058581  jz      short loc_180058594
0x180058583  mov     rcx, [rbx+1C8h]; pv
0x18005858a  mov     [rsp+168h+var_130], rcx
0x18005858f  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180058594  lea     rdx, [rbx+0C0h]
0x18005859b  lea     rcx, [rsi+8]
0x18005859f  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x1800585a4  mov     r12, rsi
0x1800585a7  test    rsi, rsi
0x1800585aa  jnz     short loc_1800585E6
0x1800585ac  lea     rcx, [rbx+1D0h]
0x1800585b3  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x1800585b8  mov     rsi, [rax]
0x1800585bb  mov     [rax], rdi
0x1800585be  mov     [rbx+0B8h], rsi
0x1800585c5  mov     r12, rsi
0x1800585c8  cmp     qword ptr [rbx+1D0h], 0
0x1800585d0  jz      short loc_1800585E6
0x1800585d2  mov     rcx, [rbx+1D0h]; pv
0x1800585d9  mov     [rsp+168h+var_C0], rcx
0x1800585e1  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x1800585e6  mov     [rbx+0D0h], rsi
0x1800585ed  test    rsi, rsi
0x1800585f0  jz      short loc_1800585F9
0x1800585f2  lock inc dword ptr [rsi+128h]
0x1800585f9  lea     rcx, [rsi+0C8h]; lpCriticalSection
0x180058600  call    cs:__imp_EnterCriticalSection
0x180058606  nop
0x180058607  lea     rcx, [rsi+108h]; void *
0x18005860e  mov     r8d, 3Eh ; '>'
0x180058614  lea     rdx, aMicrosoftWindo_27; "Microsoft.Windows.SemanticSearch.Semant"...
0x18005861b  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::assign(wchar_t const * const,unsigned __int64)
0x180058620  nop
0x180058621  test    rsi, rsi
0x180058624  jz      short loc_180058637
0x180058626  lea     rcx, [rsi+8]
0x18005862a  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18005862f  mov     rcx, rsi; pv
0x180058632  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180058637  lea     rax, [rbx+0D8h]
0x18005863e  mov     [rax+8], rdi
0x180058642  mov     [rax+10h], rdi
0x180058646  mov     [rax+18h], rdi
0x18005864a  mov     [rax+20h], rdi
0x18005864e  mov     [rax+28h], rdi
0x180058652  mov     [rax+30h], rdi
0x180058656  lea     rsi, ??_7?$test_watcher@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>>::`vftable'
0x18005865d  mov     [rax], rsi
0x180058660  mov     [rbx+0E0h], rdi
0x180058667  mov     [rbx+0E8h], rax
0x18005866e  mov     [rbx+0F0h], rdi
0x180058675  mov     [rbx+0F8h], edi
0x18005867b  mov     [rbx+100h], rdi
0x180058682  lea     rcx, [rbx+108h]
0x180058689  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x18005868e  nop
0x18005868f  test    r12, r12
0x180058692  jnz     short loc_1800586C7
0x180058694  lea     rcx, [rbx+1D8h]
0x18005869b  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x1800586a0  mov     rcx, [rax]
0x1800586a3  mov     [rax], rdi
0x1800586a6  mov     [rbx+0B8h], rcx
0x1800586ad  cmp     [rbx+1D8h], r12
0x1800586b4  jz      short loc_1800586C7
0x1800586b6  mov     rcx, [rbx+1D8h]; pv
0x1800586bd  mov     [rsp+168h+var_128], rcx
0x1800586c2  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x1800586c7  lea     rax, [rbx+110h]
0x1800586ce  mov     [rax], rsi
0x1800586d1  lea     rsi, [rbx+118h]
0x1800586d8  mov     [rsi], rdi
0x1800586db  mov     [rbx+120h], rax
0x1800586e2  mov     [rbx+128h], rdi
0x1800586e9  mov     [rbx+130h], edi
0x1800586ef  mov     [rbx+138h], rdi
0x1800586f6  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800586fe  jz      short loc_180058728
0x180058700  mov     dl, 1
0x180058702  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180058707  mov     [rsi], rax
0x18005870a  test    rax, rax
0x18005870d  jz      short loc_180058728
0x18005870f  mov     rcx, [rax]
0x180058712  mov     [rbx+128h], rcx
0x180058719  mov     [rax], rsi
0x18005871c  call    cs:__imp_GetCurrentThreadId
0x180058722  mov     [rbx+130h], eax
0x180058728  mov     rax, [rbx+0B8h]
0x18005872f  mov     [rbx+140h], rax
0x180058736  test    rax, rax
0x180058739  jz      short loc_18005874A
0x18005873b  mov     [rsp+168h+var_D0], rax
0x180058743  lock inc dword ptr [rax+128h]
0x18005874a  mov     rcx, [rbx+108h]; pv
0x180058751  mov     [rsp+168h+var_88], rcx
0x180058759  mov     rax, [rbx+140h]
0x180058760  mov     [rbx+108h], rax
0x180058767  test    rax, rax
0x18005876a  jz      short loc_180058773
0x18005876c  lock inc dword ptr [rax+128h]
0x180058773  test    rcx, rcx
0x180058776  jz      short loc_18005877D
0x180058778  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x18005877d  cmp     dword ptr [rbx+130h], 0
0x180058784  jz      short loc_18005879D
0x180058786  cmp     dword ptr [rbx+0F8h], 0
0x18005878d  jnz     short loc_1800587B3
0x18005878f  lea     rcx, [rbx+0E0h]; this
0x180058796  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18005879b  jmp     short loc_1800587B3
0x18005879d  cmp     dword ptr [rbx+0F8h], 0
0x1800587a4  jz      short loc_1800587B3
0x1800587a6  lea     rcx, [rbx+0E0h]; this
0x1800587ad  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800587b2  nop
0x1800587b3  mov     rax, [rbx+140h]
0x1800587ba  mov     [rsp+168h+var_F0], rax
0x1800587bf  test    rax, rax
0x1800587c2  jz      short loc_1800587D5
0x1800587c4  mov     rcx, [rbx+140h]; pv
0x1800587cb  mov     [rsp+168h+var_F0], rcx
0x1800587d0  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x1800587d5  mov     eax, [rbx+130h]
0x1800587db  mov     [rsp+168h+var_100], eax
0x1800587df  test    eax, eax
0x1800587e1  jz      short loc_1800587EB
0x1800587e3  mov     rcx, rsi; this
0x1800587e6  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800587eb  lea     rcx, [rbx+148h]
0x1800587f2  mov     [rcx], rdi
0x1800587f5  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x1800587fa  nop
0x1800587fb  mov     eax, [rbx+0F8h]
0x180058801  mov     [rsp+168h+var_98], eax
0x180058808  test    eax, eax
0x18005880a  jz      short loc_180058819
0x18005880c  lea     rcx, [rbx+0E0h]; this
0x180058813  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180058818  nop
0x180058819  mov     byte ptr [rbx+150h], 0
0x180058820  mov     eax, [rbx+70h]
0x180058823  cmp     eax, 2
0x180058826  jnz     short loc_180058864
0x180058828  lea     rdx, [rbx+1E0h]; struct winrt::impl::slim_source_location *
0x18005882f  mov     dword ptr [rdx], 0F8Ch
0x180058835  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005883c  mov     [rbx+1E8h], rax
0x180058843  lea     rcx, [rsp+168h+pExceptionObject]; this
0x18005884b  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180058850  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180058857  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18005885f  call    _CxxThrowException
0x180058864  mov     ecx, 4
0x180058869  mov     rax, [rsp+168h+var_138]
0x18005886e  mov     [rax], cx
0x180058871  mov     rdx, rbx
0x180058874  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180058879  jmp     loc_180058CF3
0x18005887e  cmp     qword ptr [rbx+148h], 0; jumptable 000000018005841F case 5
0x180058886  jz      short loc_1800588A8
0x180058888  cmp     qword ptr [rbx+148h], 0FFFFFFFFFFFFFFFFh
0x180058890  jz      short loc_1800588A8
0x180058892  mov     rcx, [rbx+148h]; hObject
0x180058899  mov     [rsp+168h+var_C8], rcx
0x1800588a1  call    cs:__imp_CloseHandle
0x1800588a7  nop
0x1800588a8  mov     rax, [rbx+108h]
0x1800588af  mov     [rsp+168h+var_88], rax
0x1800588b7  test    rax, rax
0x1800588ba  jz      short loc_1800588D0
0x1800588bc  mov     rcx, [rbx+108h]; pv
0x1800588c3  mov     [rsp+168h+var_88], rcx
0x1800588cb  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x1800588d0  mov     eax, [rbx+0F8h]
0x1800588d6  mov     [rsp+168h+var_98], eax
0x1800588dd  test    eax, eax
0x1800588df  jz      short loc_1800588EE
0x1800588e1  lea     rcx, [rbx+0E0h]; this
0x1800588e8  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800588ed  nop
0x1800588ee  cmp     qword ptr [rbx+0B8h], 0
0x1800588f6  jz      short loc_18005890D
0x1800588f8  mov     rcx, [rbx+0B8h]; pv
0x1800588ff  mov     [rsp+168h+var_D0], rcx
0x180058907  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x18005890c  nop
0x18005890d  jmp     loc_180058CD0; jumptable 000000018005841F cases -1,1
0x180058912  cmp     qword ptr [rbx+0B8h], 0; jumptable 000000018005841F case 4
0x18005891a  jnz     short loc_180058953
0x18005891c  lea     rcx, [rbx+1F0h]
0x180058923  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>,>(void)
0x180058928  mov     rcx, [rax]
0x18005892b  xor     edi, edi
0x18005892d  mov     [rax], rdi
0x180058930  mov     [rbx+0B8h], rcx
0x180058937  cmp     [rbx+1F0h], rdi
0x18005893e  jz      short loc_180058955
0x180058940  mov     rcx, [rbx+1F0h]; pv
0x180058947  mov     [rsp+168h+var_128], rcx
0x18005894c  call    ?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)
0x180058951  jmp     short loc_180058955
0x180058953  xor     edi, edi
0x180058955  lea     rax, [rbx+158h]
0x18005895c  lea     rsi, ??_7?$test_watcher@V?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>>::`vftable'
0x180058963  mov     [rax], rsi
  ... truncated ...
```
