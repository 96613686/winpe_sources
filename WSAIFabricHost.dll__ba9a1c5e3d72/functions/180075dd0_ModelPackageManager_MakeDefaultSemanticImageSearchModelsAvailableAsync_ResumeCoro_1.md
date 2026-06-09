# ModelPackageManager::MakeDefaultSemanticImageSearchModelsAvailableAsync$_ResumeCoro$1

- ea: `0x180075dd0`
- end: `0x1800765b0`
- name: `ModelPackageManager::MakeDefaultSemanticImageSearchModelsAvailableAsync$_ResumeCoro$1`
- size: `2016`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001b430`
- `0x180075dc0`

## callees

- `0x180005140`
- `0x180007f72`
- `0x180008f84`
- `0x18000c478`
- `0x180014688`
- `0x180018fa0`
- `0x180019c3c`
- `0x18001a420`
- `0x18001de54`
- `0x18002d62c`
- `0x18002f8ec`
- `0x1800318c4`
- `0x180031bac`
- `0x18004ba10`
- `0x18004dd6c`
- `0x18004dea8`
- `0x18004eb70`
- `0x18005266c`
- `0x180073ce8`
- `0x1800748bc`
- `0x180075748`
- `0x1800758e4`
- `0x180075dd0`
- `0x1800783b8`
- `0x1800785a8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007614b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800764aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007614b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800764aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075e7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007611f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800761e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007647e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075e7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007611f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800761e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007647e`
- `msvcp_win!_Thrd_yield` at `0x180075fd6`
- `msvcp_win!_Thrd_yield` at `0x180076071`
- `msvcp_win!_Thrd_yield` at `0x18007633c`
- `msvcp_win!_Thrd_yield` at `0x1800763d0`
- `msvcp_win!_Thrd_yield` at `0x180075fd6`
- `msvcp_win!_Thrd_yield` at `0x180076071`
- `msvcp_win!_Thrd_yield` at `0x18007633c`
- `msvcp_win!_Thrd_yield` at `0x1800763d0`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180076553`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180076553`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007619c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076396`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800764f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007619c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180076396`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800764f6`

## string_xrefs

- `0x1800760f0`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\modelpackagemanager.cpp`
- `0x18007644f`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\modelpackagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall ModelPackageManager::MakeDefaultSemanticImageSearchModelsAvailableAsync__ResumeCoro_1(__int64 a1)
{
  _WORD *v2; // r13
  __int64 *v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rbx
  const struct winrt::impl::slim_source_location *v8; // rax
  volatile __int64 *v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  volatile __int64 *v11; // rbx
  const char *v12; // rdx
  const char *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned __int16 v16; // ax
  __int64 v17; // r8
  unsigned int v18; // eax
  __int64 v19; // rbx
  struct _RTL_CRITICAL_SECTION *v20; // rbx
  __int64 *v21; // rax
  __int64 v22; // rbx
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rbx
  const struct winrt::impl::slim_source_location *v26; // rax
  volatile __int64 *v27; // rbx
  struct _RTL_CRITICAL_SECTION *v28; // rbx
  volatile __int64 *v29; // rbx
  const char *v30; // rdx
  const char *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  unsigned __int16 v34; // ax
  __int64 v35; // r8
  unsigned int v36; // eax
  __int64 v37; // rbx
  struct _RTL_CRITICAL_SECTION *v38; // rbx
  const char *v39; // [rsp+28h] [rbp-150h]
  _BYTE pExceptionObject[24]; // [rsp+70h] [rbp-108h] BYREF
  _BYTE v41[24]; // [rsp+88h] [rbp-F0h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-D8h]
  __int64 v43; // [rsp+C0h] [rbp-B8h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v2 = (_WORD *)(a1 + 124);
  switch ( *(_WORD *)(a1 + 124) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_83;
    case 2:
      if ( ModelPackageManager::IsDefaultImageEmbeddingsGeneratorAvailable() )
        goto LABEL_42;
      tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(a1 + 128);
      v3 = (__int64 *)tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(a1 + 128);
      v4 = *v3;
      *(_QWORD *)(a1 + 136) = *v3;
      if ( v4 )
        _InterlockedAdd((volatile signed __int32 *)(v4 + 288), 1u);
      EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 200));
      ++*(_DWORD *)(v4 + 240);
      *(_DWORD *)(v4 + 272) = 38;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(a1 + 136);
      *(_QWORD *)(a1 + 392) = &qword_1800AF658;
      _InterlockedAdd64(&qword_1800AF658, 1u);
      v5 = winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> )
      {
        *(_QWORD *)(a1 + 408) = 0;
        *(_DWORD *)(a1 + 416) = 0;
        *(_QWORD *)(a1 + 424) = 0;
        *(_QWORD *)(a1 + 432) = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 80LL))(v5, a1 + 408);
        if ( v6 < 0 )
          winrt::throw_hresult((unsigned int)v6, a1 + 416);
        v7 = a1 + 144;
        *(_QWORD *)(a1 + 144) = *(_QWORD *)(a1 + 408);
        _InterlockedDecrement64(&qword_1800AF658);
      }
      else
      {
        _InterlockedDecrement64(&qword_1800AF658);
        *(_QWORD *)(a1 + 400) = _lambda_42c5ad22edcc3d8e44a36b4fb3cdc9f0_::_lambda_invoker_cdecl_;
        v7 = a1 + 144;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::call<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::ImageEmbeddingsGenerator> (*)(winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics const &)>(
          0,
          a1 + 144,
          (void (__fastcall **)(__int64, __int64 *))(a1 + 400));
      }
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        v8 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 440);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v8);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 152) = 0;
      *(_QWORD *)(a1 + 160) = v7;
      *(_QWORD *)(a1 + 168) = 0;
      *(_BYTE *)(a1 + 176) = 1;
      *v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>(
                              a1 + 152,
                              a1) )
        return;
LABEL_24:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(
        a1 + 152,
        a1 + 184);
      v11 = *(volatile __int64 **)(a1 + 152);
      if ( v11 )
      {
        v42 = *(_QWORD *)(a1 + 152);
        while ( _InterlockedExchange64(v11, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 144) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 144);
      if ( !ModelPackageManager::IsDefaultImageEmbeddingsGeneratorAvailable() )
      {
        ModelPackageManager::ThrowIfPackageDeploymentFailed((const struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *)(a1 + 184));
        v13 = tip2::details::reason_string(
                (tip2::details *)"AIFabricAPIsPerfTest::reason::ImageSearchModelNotAvailable",
                v12);
        v16 = tip2::details::validate_reason<enum _tip_AIFabricAPIsPerfTest::reason,4>(v15, v14, v13);
        tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(
          a1 + 128,
          v16,
          v17);
        v18 = wil::verify_hresult(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0xAD,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
          (const char *)v18,
          (int)"MakeAvailableAsync succeeded but models are still not available",
          v39);
      }
      v19 = *(_QWORD *)(a1 + 128);
      if ( v19 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 200));
        *(_DWORD *)(v19 + 72) |= 0x300u;
        if ( *(_QWORD *)(v19 + 248) )
          tip2::details::shared_data<0,0,0>::complete_helper(v19 + 8, 2);
        if ( v19 != -200 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 200));
      }
      if ( *(_QWORD *)(a1 + 184) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 184);
      v20 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 128);
      if ( v20 && _InterlockedExchangeAdd(&v20[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v20);
        CoTaskMemFree(v20);
      }
LABEL_42:
      if ( ModelPackageManager::IsDefaultImageTextQueryGeneratorAvailable() )
        goto LABEL_82;
      tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(a1 + 256);
      v21 = (__int64 *)tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(a1 + 256);
      v22 = *v21;
      *(_QWORD *)(a1 + 264) = *v21;
      if ( v22 )
        _InterlockedAdd((volatile signed __int32 *)(v22 + 288), 1u);
      EnterCriticalSection((LPCRITICAL_SECTION)(v22 + 200));
      ++*(_DWORD *)(v22 + 240);
      *(_DWORD *)(v22 + 272) = 39;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(a1 + 264);
      *(_QWORD *)(a1 + 464) = &qword_1800AF658;
      _InterlockedAdd64(&qword_1800AF658, 1u);
      v23 = winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>;
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> )
      {
        *(_QWORD *)(a1 + 480) = 0;
        *(_DWORD *)(a1 + 488) = 0;
        *(_QWORD *)(a1 + 496) = 0;
        *(_QWORD *)(a1 + 504) = 0;
        v24 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 128LL))(v23, a1 + 480);
        if ( v24 < 0 )
          winrt::throw_hresult((unsigned int)v24, a1 + 488);
        v25 = a1 + 272;
        *(_QWORD *)(a1 + 272) = *(_QWORD *)(a1 + 480);
        _InterlockedDecrement64(&qword_1800AF658);
      }
      else
      {
        _InterlockedDecrement64(&qword_1800AF658);
        *(_QWORD *)(a1 + 472) = _lambda_43da5b421c0f3789bb44d96d5d5c90f3_::_lambda_invoker_cdecl_;
        v25 = a1 + 272;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::call<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::ImageEmbeddingsGenerator> (*)(winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics const &)>(
          0,
          a1 + 272,
          (void (__fastcall **)(__int64, __int64 *))(a1 + 472));
      }
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        v26 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 512);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v41, v26);
        throw (winrt::hresult_canceled *)v41;
      }
      *(_QWORD *)(a1 + 280) = 0;
      *(_QWORD *)(a1 + 288) = v25;
      *(_QWORD *)(a1 + 296) = 0;
      *(_BYTE *)(a1 + 304) = 1;
      *v2 = 6;
      if ( !(unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>(
                               a1 + 280,
                               a1) )
      {
LABEL_64:
        winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(
          a1 + 280,
          a1 + 312);
        v29 = *(volatile __int64 **)(a1 + 280);
        if ( v29 )
        {
          v43 = *(_QWORD *)(a1 + 280);
          while ( _InterlockedExchange64(v29, 0) == 1 )
            _Thrd_yield();
        }
        if ( *(_QWORD *)(a1 + 272) )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 272);
        if ( !ModelPackageManager::IsDefaultImageTextQueryGeneratorAvailable() )
        {
          ModelPackageManager::ThrowIfPackageDeploymentFailed((const struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *)(a1 + 312));
          v31 = tip2::details::reason_string(
                  (tip2::details *)"AIFabricAPIsPerfTest::reason::ImageSearchModelNotAvailable",
                  v30);
          v34 = tip2::details::validate_reason<enum _tip_AIFabricAPIsPerfTest::reason,4>(v33, v32, v31);
          tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(
            a1 + 256,
            v34,
            v35);
          v36 = wil::verify_hresult(2147549183LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0xC6,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
            (const char *)v36,
            (int)"MakeAvailableAsync succeeded but models are still not available",
            v39);
        }
        v37 = *(_QWORD *)(a1 + 256);
        if ( v37 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)(v37 + 200));
          *(_DWORD *)(v37 + 72) |= 0x300u;
          if ( *(_QWORD *)(v37 + 248) )
            tip2::details::shared_data<0,0,0>::complete_helper(v37 + 8, 2);
          if ( v37 != -200 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(v37 + 200));
        }
        if ( *(_QWORD *)(a1 + 312) )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 312);
        v38 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 256);
        if ( v38 && _InterlockedExchangeAdd(&v38[7].LockCount, 0xFFFFFFFF) == 1 )
        {
          tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v38);
          CoTaskMemFree(v38);
        }
LABEL_82:
        *(_QWORD *)(a1 + 384) = a1 + 16;
        *v2 = 0;
        *(_QWORD *)a1 = 0;
        if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,enum winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
        {
LABEL_83:
          if ( *(_QWORD *)(a1 + 104) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 104);
          if ( *(_QWORD *)(a1 + 96) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 96);
          __ExceptionPtrDestroy((void *)(a1 + 72));
          winrt::impl::root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>::~root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>(a1 + 16);
          if ( *(_WORD *)(a1 + 126) )
            operator delete((void *)a1, 0x220u);
        }
      }
      return;
    case 4:
      goto LABEL_24;
    case 5:
      v9 = *(volatile __int64 **)(a1 + 152);
      if ( v9 )
      {
        v42 = *(_QWORD *)(a1 + 152);
        while ( _InterlockedExchange64(v9, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 144) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 144);
      v10 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 128);
      if ( v10 && _InterlockedExchangeAdd(&v10[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v10);
        CoTaskMemFree(v10);
      }
      goto LABEL_83;
    case 6:
      goto LABEL_64;
    case 7:
      v27 = *(volatile __int64 **)(a1 + 280);
      if ( v27 )
      {
        v43 = *(_QWORD *)(a1 + 280);
        while ( _InterlockedExchange64(v27, 0) == 1 )
          _Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 272) )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 272);
      v28 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 256);
      if ( v28 && _InterlockedExchangeAdd(&v28[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v28);
        CoTaskMemFree(v28);
      }
      goto LABEL_83;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180075dd0  mov     [rsp+arg_0], rcx
0x180075dd5  push    rbx
0x180075dd6  push    rsi
0x180075dd7  push    rdi
0x180075dd8  push    r12
0x180075dda  push    r13
0x180075ddc  push    r14
0x180075dde  push    r15
0x180075de0  sub     rsp, 140h
0x180075de7  mov     rsi, [rsp+178h+arg_0]
0x180075def  lea     r13, [rsi+7Ch]
0x180075df3  movzx   eax, word ptr [r13+0]
0x180075df8  mov     [rsp+178h+var_148], ax
0x180075dfd  mov     r15d, 1
0x180075e03  add     ax, r15w
0x180075e07  cmp     ax, 8; switch 9 cases
0x180075e0b  ja      def_180075E2B; jumptable 0000000180075E2B default case, case 1
0x180075e11  mov     [rsp+178h+var_130], r13
0x180075e16  movsx   rax, ax
0x180075e1a  lea     rdx, __ImageBase
0x180075e21  mov     ecx, ds:(jpt_180075E2B - 180000000h)[rdx+rax*4]
0x180075e28  add     rcx, rdx
0x180075e2b  jmp     rcx; switch jump
0x180075e2d  xor     edi, edi; jumptable 0000000180075E2B case 4
0x180075e2f  jmp     loc_180076533
0x180075e34  xor     edi, edi; jumptable 0000000180075E2B case 3
0x180075e36  call    ?IsDefaultImageEmbeddingsGeneratorAvailable@ModelPackageManager@@CA_NXZ; ModelPackageManager::IsDefaultImageEmbeddingsGeneratorAvailable(void)
0x180075e3b  test    al, al
0x180075e3d  jnz     loc_180075FB2
0x180075e43  lea     rbx, [rsi+80h]
0x180075e4a  mov     rcx, rbx
0x180075e4d  call    ??$start@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(void)
0x180075e52  nop
0x180075e53  mov     rcx, rbx
0x180075e56  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(void)
0x180075e5b  mov     rbx, [rax]
0x180075e5e  lea     r14, [rsi+88h]
0x180075e65  mov     [r14], rbx
0x180075e68  test    rbx, rbx
0x180075e6b  jz      short loc_180075E75
0x180075e6d  lock add [rbx+120h], r15d
0x180075e75  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180075e7c  call    cs:__imp_EnterCriticalSection
0x180075e82  add     [rbx+0F0h], r15d
0x180075e89  mov     dword ptr [rbx+110h], 26h ; '&'
0x180075e93  mov     rcx, r14
0x180075e96  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180075e9b  nop
0x180075e9c  lea     r12, qword_1800AF658
0x180075ea3  mov     [rsi+188h], r12
0x180075eaa  lock add cs:qword_1800AF658, r15
0x180075eb2  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>
0x180075eb9  test    rcx, rcx
0x180075ebc  jz      short loc_180075F18
0x180075ebe  lea     r14, [rsi+198h]
0x180075ec5  mov     [r14], rdi
0x180075ec8  lea     rbx, [rsi+1A0h]
0x180075ecf  mov     [rbx], edi
0x180075ed1  mov     [rsi+1A8h], rdi
0x180075ed8  mov     [rsi+1B0h], rdi
0x180075edf  mov     rax, [rcx]
0x180075ee2  mov     rdx, r14
0x180075ee5  mov     rax, [rax+50h]
0x180075ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075eee  test    eax, eax
0x180075ef0  jns     short loc_180075EFC
0x180075ef2  mov     rdx, rbx
0x180075ef5  mov     ecx, eax
0x180075ef7  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180075efc  lea     rbx, [rsi+90h]
0x180075f03  mov     rax, [r14]
0x180075f06  mov     [rsp+178h+var_128], rax
0x180075f0b  mov     [rbx], rax
0x180075f0e  lock dec cs:qword_1800AF658
0x180075f16  jmp     short loc_180075F41
0x180075f18  lock dec cs:qword_1800AF658
0x180075f20  lea     r8, [rsi+190h]
0x180075f27  lea     rax, ?_lambda_invoker_cdecl_@_lambda_42c5ad22edcc3d8e44a36b4fb3cdc9f0_@@CA@AEBUISemanticImageIndexStoreStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z; _lambda_42c5ad22edcc3d8e44a36b4fb3cdc9f0_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics const &)
0x180075f2e  mov     [r8], rax
0x180075f31  lea     rbx, [rsi+90h]
0x180075f38  mov     rdx, rbx
0x180075f3b  call    ??$call@P6A?AU?$IAsyncOperation@UImageEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEBUISemanticImageIndexStoreStatics@SemanticSearch@3Microsoft@4@@Z@?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperation@UImageEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@2@AEBUISemanticImageIndexStoreStatics@SemanticSearch@5Microsoft@2@@Z@Z
0x180075f40  nop
0x180075f41  mov     eax, [rsi+70h]
0x180075f44  nop
0x180075f45  cmp     eax, 2
0x180075f48  jnz     short loc_180075F74
0x180075f4a  lea     rcx, [rsi+1B8h]
0x180075f51  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180075f56  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x180075f59  lea     rcx, [rsp+178h+pExceptionObject]; this
0x180075f5e  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180075f63  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180075f6a  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x180075f6f  call    _CxxThrowException_0
0x180075f74  lea     rcx, [rsi+98h]
0x180075f7b  mov     [rcx], rdi
0x180075f7e  mov     [rsi+0A0h], rbx
0x180075f85  mov     [rsi+0A8h], rdi
0x180075f8c  mov     [rsi+0B0h], r15b
0x180075f93  mov     eax, 4
0x180075f98  mov     [r13+0], ax
0x180075f9d  mov     rdx, rsi
0x180075fa0  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>)
0x180075fa5  test    al, al
0x180075fa7  jz      loc_180076045
0x180075fad  jmp     loc_180076578
0x180075fb2  lea     r12, qword_1800AF658
0x180075fb9  jmp     loc_1800761A2
0x180075fbe  mov     rbx, [rsi+98h]; jumptable 0000000180075E2B case 6
0x180075fc5  xor     edi, edi
0x180075fc7  test    rbx, rbx
0x180075fca  jz      short loc_180075FE7
0x180075fcc  mov     [rsp+178h+var_D8], rbx
0x180075fd4  jmp     short loc_180075FDC
0x180075fd6  call    cs:__imp__Thrd_yield
0x180075fdc  mov     rax, rdi
0x180075fdf  xchg    rax, [rbx]
0x180075fe2  cmp     rax, r15
0x180075fe5  jz      short loc_180075FD6
0x180075fe7  lea     rcx, [rsi+90h]
0x180075fee  mov     rax, [rcx]
0x180075ff1  mov     [rsp+178h+var_140], rax
0x180075ff6  test    rax, rax
0x180075ff9  jz      short loc_180076001
0x180075ffb  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180076000  nop
0x180076001  mov     rbx, [rsi+80h]
0x180076008  mov     [rsp+178h+arg_10], rbx
0x180076010  test    rbx, rbx
0x180076013  jz      short loc_180076037
0x180076015  or      eax, 0FFFFFFFFh
0x180076018  lock xadd [rbx+120h], eax
0x180076020  cmp     eax, 1
0x180076023  jnz     short loc_180076037
0x180076025  mov     rcx, rbx
0x180076028  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x18007602d  mov     rcx, rbx; pv
0x180076030  call    cs:__imp_CoTaskMemFree
0x180076036  nop
0x180076037  jmp     loc_180076533
0x18007603c  xor     edi, edi; jumptable 0000000180075E2B case 5
0x18007603e  lea     r12, qword_1800AF658
0x180076045  lea     r14, [rsi+0B8h]
0x18007604c  lea     rbx, [rsi+98h]
0x180076053  mov     rdx, r14
0x180076056  mov     rcx, rbx
0x180076059  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(void)
0x18007605e  nop
0x18007605f  mov     rbx, [rbx]
0x180076062  test    rbx, rbx
0x180076065  jz      short loc_180076082
0x180076067  mov     [rsp+178h+var_D8], rbx
0x18007606f  jmp     short loc_180076077
0x180076071  call    cs:__imp__Thrd_yield
0x180076077  mov     rax, rdi
0x18007607a  xchg    rax, [rbx]
0x18007607d  cmp     rax, r15
0x180076080  jz      short loc_180076071
0x180076082  lea     rcx, [rsi+90h]
0x180076089  mov     rax, [rcx]
0x18007608c  mov     [rsp+178h+var_140], rax
0x180076091  test    rax, rax
0x180076094  jz      short loc_18007609B
0x180076096  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18007609b  call    ?IsDefaultImageEmbeddingsGeneratorAvailable@ModelPackageManager@@CA_NXZ; ModelPackageManager::IsDefaultImageEmbeddingsGeneratorAvailable(void)
0x1800760a0  test    al, al
0x1800760a2  jnz     short loc_180076101
0x1800760a4  mov     rcx, r14; struct winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult *
0x1800760a7  call    ?ThrowIfPackageDeploymentFailed@ModelPackageManager@@CAXAEBUPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@Z; ModelPackageManager::ThrowIfPackageDeploymentFailed(winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult const &)
0x1800760ac  lea     rcx, aAifabricapispe_0; "AIFabricAPIsPerfTest::reason::ImageSear"...
0x1800760b3  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800760b8  mov     r8, rax
0x1800760bb  call    ??$validate_reason@W4reason@_tip_AIFabricAPIsPerfTest@@$03@details@tip2@@YAGXZ; tip2::details::validate_reason<_tip_AIFabricAPIsPerfTest::reason,4>(void)
0x1800760c0  movzx   edx, ax
0x1800760c3  lea     rcx, [rsi+80h]
0x1800760ca  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::complete_and_fail(ushort,char const *)
0x1800760cf  mov     ecx, 8000FFFFh
0x1800760d4  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x1800760d9  mov     r9d, eax; char *
0x1800760dc  mov     rcx, [rsp+178h]; this
0x1800760e4  lea     rax, aMakeavailablea_1; "MakeAvailableAsync succeeded but models"...
0x1800760eb  mov     qword ptr [rsp+178h+var_158], rax; int
0x1800760f0  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800760f7  mov     edx, 0ADh; void *
0x1800760fc  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180076101  mov     rbx, [rsi+80h]
0x180076108  test    rbx, rbx
0x18007610b  jz      short loc_180076157
0x18007610d  mov     [rsp+178h+arg_10], rbx
0x180076115  lea     r15, [rbx+0C8h]
0x18007611c  mov     rcx, r15; lpCriticalSection
0x18007611f  call    cs:__imp_EnterCriticalSection
0x180076125  or      dword ptr [rbx+48h], 300h
0x18007612c  cmp     [rbx+0F8h], rdi
0x180076133  jz      short loc_180076143
0x180076135  mov     edx, 2
0x18007613a  lea     rcx, [rbx+8]
0x18007613e  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180076143  test    r15, r15
0x180076146  jz      short loc_180076151
0x180076148  mov     rcx, r15; lpCriticalSection
0x18007614b  call    cs:__imp_LeaveCriticalSection
0x180076151  mov     r15d, 1
0x180076157  mov     rax, [r14]
0x18007615a  mov     [rsp+178h+var_120], rax
0x18007615f  test    rax, rax
0x180076162  jz      short loc_18007616D
0x180076164  mov     rcx, r14
0x180076167  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18007616c  nop
0x18007616d  mov     rbx, [rsi+80h]
0x180076174  mov     [rsp+178h+arg_10], rbx
0x18007617c  test    rbx, rbx
0x18007617f  jz      short loc_1800761A2
0x180076181  or      eax, 0FFFFFFFFh
0x180076184  lock xadd [rbx+120h], eax
0x18007618c  cmp     eax, 1
0x18007618f  jnz     short loc_1800761A2
0x180076191  mov     rcx, rbx
0x180076194  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180076199  mov     rcx, rbx; pv
0x18007619c  call    cs:__imp_CoTaskMemFree
0x1800761a2  call    ?IsDefaultImageTextQueryGeneratorAvailable@ModelPackageManager@@CA_NXZ; ModelPackageManager::IsDefaultImageTextQueryGeneratorAvailable(void)
0x1800761a7  test    al, al
0x1800761a9  jnz     loc_1800764FD
0x1800761af  lea     rbx, [rsi+100h]
0x1800761b6  mov     rcx, rbx
0x1800761b9  call    ??$start@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(void)
0x1800761be  nop
0x1800761bf  mov     rcx, rbx
0x1800761c2  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::ensure_data(void)
0x1800761c7  mov     rbx, [rax]
0x1800761ca  lea     r14, [rsi+108h]
0x1800761d1  mov     [r14], rbx
0x1800761d4  test    rbx, rbx
0x1800761d7  jz      short loc_1800761E1
0x1800761d9  lock add [rbx+120h], r15d
0x1800761e1  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800761e8  call    cs:__imp_EnterCriticalSection
0x1800761ee  add     [rbx+0F0h], r15d
0x1800761f5  mov     dword ptr [rbx+110h], 27h ; '''
0x1800761ff  mov     rcx, r14
0x180076202  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180076207  nop
0x180076208  mov     [rsi+1D0h], r12
0x18007620f  lock add cs:qword_1800AF658, r15
0x180076217  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>
0x18007621e  test    rcx, rcx
0x180076221  jz      short loc_180076280
0x180076223  lea     r14, [rsi+1E0h]
0x18007622a  mov     [r14], rdi
0x18007622d  lea     rbx, [rsi+1E8h]
0x180076234  mov     [rbx], edi
0x180076236  mov     [rsi+1F0h], rdi
0x18007623d  mov     [rsi+1F8h], rdi
0x180076244  mov     rax, [rcx]
0x180076247  mov     rdx, r14
0x18007624a  mov     rax, [rax+80h]
0x180076251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076256  test    eax, eax
0x180076258  jns     short loc_180076264
0x18007625a  mov     rdx, rbx
0x18007625d  mov     ecx, eax
0x18007625f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180076264  lea     rbx, [rsi+110h]
0x18007626b  mov     rax, [r14]
0x18007626e  mov     [rsp+178h+var_118], rax
0x180076273  mov     [rbx], rax
0x180076276  lock dec cs:qword_1800AF658
0x18007627e  jmp     short loc_1800762A9
0x180076280  lock dec cs:qword_1800AF658
0x180076288  lea     r8, [rsi+1D8h]
0x18007628f  lea     rax, ?_lambda_invoker_cdecl_@_lambda_43da5b421c0f3789bb44d96d5d5c90f3_@@CA@AEBUISemanticImageIndexStoreStatics@SemanticSearch@Windows@Microsoft@winrt@@@Z; _lambda_43da5b421c0f3789bb44d96d5d5c90f3_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics const &)
0x180076296  mov     [r8], rax
0x180076299  lea     rbx, [rsi+110h]
0x1800762a0  mov     rdx, rbx
0x1800762a3  call    ??$call@P6A?AU?$IAsyncOperation@UImageEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEBUISemanticImageIndexStoreStatics@SemanticSearch@3Microsoft@4@@Z@?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6A?AU?$IAsyncOperation@UImageEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@2@AEBUISemanticImageIndexStoreStatics@SemanticSearch@5Microsoft@2@@Z@Z
0x1800762a8  nop
0x1800762a9  mov     eax, [rsi+70h]
0x1800762ac  nop
0x1800762ad  cmp     eax, 2
0x1800762b0  jnz     short loc_1800762E2
0x1800762b2  lea     rcx, [rsi+200h]
0x1800762b9  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800762be  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x1800762c1  lea     rcx, [rsp+178h+var_F0]; this
0x1800762c9  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1800762ce  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1800762d5  lea     rcx, [rsp+178h+var_F0]; pExceptionObject
0x1800762dd  call    _CxxThrowException_0
0x1800762e2  lea     rcx, [rsi+118h]
0x1800762e9  mov     [rcx], rdi
0x1800762ec  mov     [rsi+120h], rbx
0x1800762f3  mov     qword ptr [rsi+128h], 0
0x1800762fe  mov     [rsi+130h], r15b
0x180076305  mov     eax, 6
0x18007630a  mov     [r13+0], ax
0x18007630f  mov     rdx, rsi
0x180076312  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@$$V@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,>::promise_type>)
  ... truncated ...
```
