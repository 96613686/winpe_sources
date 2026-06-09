# IndexerSemanticStoreManagerImpl::OpenImageStore(wchar_t *,IIndexerSemanticStore * *,tagIndexCreationDisposition)

- ea: `0x180044780`
- end: `0x180044f76`
- name: `?OpenImageStore@IndexerSemanticStoreManagerImpl@@UEAAJPEA_WPEAPEAUIIndexerSemanticStore@@W4tagIndexCreationDisposition@@@Z`
- size: `2038`
- prototype: `__int64 __fastcall(_QWORD *, const wchar_t *, __int64 **, int)`
- caller_count: `0`
- callee_count: `36`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800058cb`
- `0x18000591f`
- `0x180007f72`
- `0x180008f84`
- `0x18000b064`
- `0x18000c350`
- `0x18000c478`
- `0x18000c634`
- `0x180013d94`
- `0x180015f90`
- `0x1800187b0`
- `0x1800189b8`
- `0x180018fa0`
- `0x180019c3c`
- `0x180019f14`
- `0x18001a464`
- `0x18001fd14`
- `0x180021290`
- `0x18002cb78`
- `0x18002e86c`
- `0x18002f924`
- `0x180030600`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x180032c94`
- `0x180032ca0`
- `0x18003cf0c`
- `0x180044780`
- `0x18004b60c`
- `0x18004ba10`
- `0x18004d7e4`
- `0x18004dea8`
- `0x18004ff60`
- `0x18005040c`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800449d0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800449db`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044e75`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800449d0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800449db`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044e75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044caa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044caa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044a7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044c7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044a7e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180044c7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044de1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044de1`

## string_xrefs

- `0x180044e9d`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`
- `0x1800447be`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18004489d`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180044d8a`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180044e40`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180044e17`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180044f63`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x1800447b2`: `OpenImageStore : basePath: %s, idxCreationDisposition: %lu`
- `0x180044891`: `OpenImageStore: Models are available`
- `0x180044e34`: `OpenImageStore : Invalid arguments basePath: %p, store: %p`
- `0x180044d7e`: `OpenImageStore : Successfully completed`
- `0x180044f08`: `SemanticImageIndexStore::CreateAsync timed out`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall IndexerSemanticStoreManagerImpl::OpenImageStore(_QWORD *a1, const wchar_t *a2, __int64 **a3, int a4)
{
  struct winrt::impl::shared_hstring_header *v8; // r14
  unsigned int v9; // edx
  __int64 v10; // rcx
  unsigned int v11; // esi
  __int64 *v12; // r15
  __int64 v13; // r12
  __int64 v14; // rdi
  __int64 v15; // rax
  const wchar_t *v16; // r9
  volatile signed __int32 *v17; // rsi
  unsigned int v18; // edx
  unsigned int v19; // r15d
  __int64 v20; // rbx
  struct winrt::impl::shared_hstring_header *v21; // rdi
  unsigned int v22; // r14d
  const void *v23; // rbx
  int v24; // eax
  HANDLE ProcessHeap; // rax
  int v26; // eax
  HANDLE v27; // rax
  int v28; // eax
  __int64 (__fastcall ****v29)(_QWORD, __int64 *, LPVOID *); // rcx
  int v30; // eax
  struct _RTL_CRITICAL_SECTION *v31; // rbx
  int v32; // eax
  __int64 (__fastcall ****v33)(_QWORD, __int64 *, LPVOID *); // rbx
  __int64 v34; // rax
  __int64 *v35; // rdi
  __int64 **v36; // r14
  IndexerSemanticSearchServicesImpl *v37; // rsi
  __int64 *v38; // rdi
  __int64 *v39; // rax
  _DWORD *v40; // rdi
  struct _RTL_CRITICAL_SECTION *v41; // rsi
  unsigned int v42; // edx
  IndexerSemanticSearchServicesImpl *v43; // r12
  __int64 v44; // rdi
  struct winrt::impl::shared_hstring_header *v45; // rsi
  struct winrt::impl::shared_hstring_header *v46; // r14
  __int64 v47; // r15
  const void *v48; // rdi
  const wchar_t *v49; // r9
  int v50; // eax
  HANDLE v51; // rax
  void *v52; // rbx
  const char *v53; // r9
  __int64 result; // rax
  const char *v55; // r9
  __int64 v56; // rax
  __int64 v57; // rbx
  unsigned int *v58; // rax
  const char *v60; // [rsp+28h] [rbp-100h]
  __int64 *v61; // [rsp+30h] [rbp-F8h] BYREF
  __int64 (__fastcall ****v62)(_QWORD, __int64 *, LPVOID *); // [rsp+38h] [rbp-F0h] BYREF
  __int64 *v63; // [rsp+40h] [rbp-E8h] BYREF
  __int64 (__fastcall ***v64)(_QWORD, __int64 *, LPVOID *); // [rsp+48h] [rbp-E0h] BYREF
  int v65; // [rsp+50h] [rbp-D8h] BYREF
  __int128 v66; // [rsp+58h] [rbp-D0h]
  char v67[8]; // [rsp+70h] [rbp-B8h] BYREF
  char v68[48]; // [rsp+78h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-80h]
  _BYTE pExceptionObject[24]; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v71[96]; // [rsp+C8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]
  __int64 (__fastcall ****v74)(_QWORD, __int64 *, LPVOID *); // [rsp+138h] [rbp+10h] BYREF
  __int64 **v75; // [rsp+140h] [rbp+18h]

  v75 = a3;
  v8 = 0;
  SearchIndexerTrace::Information(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
    (const wchar_t *)0xB7C,
    (unsigned int)L"OpenImageStore : basePath: %s, idxCreationDisposition: %lu",
    a2);
  try
  {
    if ( !a2 || !a3 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const wchar_t *)0xB80,
        (unsigned int)L"OpenImageStore : Invalid arguments basePath: %p, store: %p",
        a2,
        a3);
      return 2147500035LL;
    }
    v10 = a1[6];
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 64LL))(v10);
    switch ( a4 )
    {
      case 1:
        v11 = 0;
        break;
      case 2:
        v11 = 1;
        break;
      case 4:
        v11 = 2;
        break;
      default:
        v55 = (const char *)(unsigned int)wil::verify_hresult(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x33,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\Utils.h",
          v55,
          (int)"Unexpected disposition.",
          v60);
    }
    v12 = (__int64 *)a1[3];
    v13 = *v12;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    if ( (_DWORD)v14 )
    {
      v8 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v14, v9);
      memcpy_s((char *)v8 + 28, 2LL * (unsigned int)v14, a2, 2LL * (unsigned int)v14);
    }
    v74 = (__int64 (__fastcall ****)(_QWORD, __int64 *, LPVOID *))v8;
    v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall *****)(_QWORD, __int64 *, LPVOID *), __int64 (__fastcall *****)(_QWORD, __int64 *, LPVOID *), _QWORD))(v13 + 16))(
            v12,
            &v62,
            &v74,
            v11);
    winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(v15);
    v17 = 0;
    if ( v62 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v62);
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0xB8B,
      (unsigned int)L"OpenImageStore: Models are available",
      v16);
    if ( a4 == 4 )
      v19 = 2;
    else
      v19 = a4 != 1;
    v20 = -1;
    do
      ++v20;
    while ( a2[v20] );
    if ( (_DWORD)v20 )
    {
      v21 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v20, v18);
      memcpy_s((char *)v21 + 28, 2LL * (unsigned int)v20, a2, 2LL * (unsigned int)v20);
    }
    else
    {
      v21 = 0;
    }
    v61 = (__int64 *)v21;
    if ( v21 )
    {
      if ( (*(_BYTE *)v21 & 1) != 0 )
      {
        v22 = *((_DWORD *)v21 + 1);
        if ( v22 )
        {
          v23 = (const void *)*((_QWORD *)v21 + 2);
          v17 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)v22, v18);
          memcpy_s((void *const)(v17 + 7), 2LL * v22, v23, 2LL * v22);
        }
      }
      else
      {
        _InterlockedIncrement((volatile signed __int32 *)v21 + 6);
        v17 = (volatile signed __int32 *)v21;
      }
    }
    v74 = (__int64 (__fastcall ****)(_QWORD, __int64 *, LPVOID *))v17;
    Utils::GetSemanticImageIndexStoreOptions(&v64, &v74, v19);
    if ( v17 )
    {
      v24 = _InterlockedDecrement(v17 + 6);
      if ( v24 )
      {
        if ( v24 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v17);
      }
    }
    if ( v21 )
    {
      v26 = _InterlockedDecrement((volatile signed __int32 *)v21 + 6);
      if ( v26 )
      {
        if ( v26 < 0 )
          abort();
      }
      else
      {
        v27 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v27, 0, v21);
      }
    }
    v74 = 0;
    if ( v64 )
    {
      v28 = (**v64)(
              v64,
              winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreOptions3>,
              (LPVOID *)&v74);
      v29 = v74;
    }
    else
    {
      v28 = 0;
      v29 = 0;
    }
    v65 = 0;
    v66 = 0;
    if ( v28 < 0 )
      winrt::throw_hresult((unsigned int)v28, &v65);
    v65 = 0;
    v66 = 0;
    v30 = ((__int64 (__fastcall *)(__int64 (__fastcall ****)(_QWORD, __int64 *, LPVOID *), _QWORD))(*v29)[7])(v29, 0);
    if ( v30 < 0 )
      winrt::throw_hresult((unsigned int)v30, &v65);
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v74);
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(v67);
    v31 = (struct _RTL_CRITICAL_SECTION *)pv;
    v74 = (__int64 (__fastcall ****)(_QWORD, __int64 *, LPVOID *))pv;
    if ( pv )
      _InterlockedIncrement((volatile signed __int32 *)pv + 72);
    EnterCriticalSection(v31 + 5);
    ++LODWORD(v31[6].DebugInfo);
    LODWORD(v31[6].SpinCount) = 5;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v74);
    v74 = &v64;
    v61 = &qword_1800AF658;
    _InterlockedIncrement64(&qword_1800AF658);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> )
    {
      v74 = 0;
      v65 = 0;
      v66 = 0;
      v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>
                                                                 + 64LL))(
              winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>,
              v64,
              (LPVOID *)&v74);
      if ( v32 < 0 )
        winrt::throw_hresult((unsigned int)v32, &v65);
      v33 = v74;
      v62 = v74;
      _InterlockedDecrement64(&qword_1800AF658);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800AF658);
      winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::call<_lambda_9293e9b3e542a45805ed53334864e622_ &>(
        0,
        &v62,
        &v74);
      v33 = v62;
    }
    if ( !(unsigned int)winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>>(
                          &v62,
                          120000) )
    {
      v56 = tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(
              v67,
              &v74);
      *(_BYTE *)(std::unique_ptr<wil::srwlock>::operator->(v56) + 276) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v74);
      v57 = winrt::impl::slim_source_location::current(&v65);
      winrt::param::hstring::hstring((winrt::param::hstring *)v71, L"SemanticImageIndexStore::CreateAsync timed out");
      v58 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v74, -2147023436);
      winrt::hresult_error::hresult_error(pExceptionObject, *v58, v71, v57);
      throw (winrt::hresult_error *)pExceptionObject;
    }
    v34 = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>,winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>::get(
            &v62,
            &v74);
    winrt::make<IndexerSemanticStore,IEnclaveInterface &,winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>(
      &v63,
      a1[4],
      v34);
    if ( v74 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v74);
    v35 = v63;
    if ( !v63 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB9E,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const char *)0x8007000ELL,
        a4);
    v36 = (__int64 **)(a1 + 6);
    if ( (__int64 *)a1[6] != v63 )
    {
      if ( *v36 )
        winrt::com_ptr<IAIFabricResourceManagerClient>::unconditional_release_ref(a1 + 6);
      *v36 = v35;
      if ( v35 )
        (*(void (__fastcall **)(__int64 *))(*v35 + 8))(v35);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58816171>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58816171>::GetImpl'::`2'::impl) )
    {
      v37 = g_singletonIndexerSemanticSearchServices;
      v38 = *v36;
      v61 = v38;
      if ( v38 )
        (*(void (__fastcall **)(__int64 *))(*v38 + 8))(v38);
      if ( *((__int64 **)v37 + 21) != v38 )
      {
        if ( *((_QWORD *)v37 + 21) )
          winrt::com_ptr<IAIFabricResourceManagerClient>::unconditional_release_ref((char *)v37 + 168);
        *((_QWORD *)v37 + 21) = v38;
        if ( v38 )
          (*(void (__fastcall **)(__int64 *))(*v38 + 8))(v38);
      }
      if ( v38 )
        winrt::com_ptr<IAIFabricResourceManagerClient>::unconditional_release_ref(&v61);
    }
    v39 = v63;
    v63 = 0;
    *v75 = v39;
    v40 = pv;
    v41 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    v40[18] |= 0x300u;
    if ( *((_QWORD *)v40 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper(v40 + 2, 2);
    if ( v41 )
      LeaveCriticalSection(v41);
    v43 = g_singletonIndexerSemanticSearchServices;
    v44 = -1;
    do
      ++v44;
    while ( a2[v44] );
    if ( (_DWORD)v44 )
    {
      v45 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v44, v42);
      memcpy_s((char *)v45 + 28, 2LL * (unsigned int)v44, a2, 2LL * (unsigned int)v44);
    }
    else
    {
      v45 = 0;
    }
    v74 = (__int64 (__fastcall ****)(_QWORD, __int64 *, LPVOID *))v45;
    if ( v45 )
    {
      if ( (*(_BYTE *)v45 & 1) == 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v45 + 6);
        v46 = v45;
        goto LABEL_86;
      }
      v47 = *((unsigned int *)v45 + 1);
      if ( (_DWORD)v47 )
      {
        v48 = (const void *)*((_QWORD *)v45 + 2);
        v46 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v47, v42);
        memcpy_s((char *)v46 + 28, 2 * v47, v48, 2 * v47);
        goto LABEL_86;
      }
    }
    v46 = 0;
LABEL_86:
    v61 = (__int64 *)v46;
    IndexerSemanticSearchServicesImpl::SetImageIndexStorePath(v43, &v61);
    if ( v45 )
    {
      v50 = _InterlockedDecrement((volatile signed __int32 *)v45 + 6);
      if ( v50 )
      {
        if ( v50 < 0 )
          abort();
      }
      else
      {
        v51 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v51, 0, v45);
      }
    }
    SearchIndexerTrace::Information(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0xBAC,
      (unsigned int)L"OpenImageStore : Successfully completed",
      v49);
    if ( v63 )
      winrt::com_ptr<IAIFabricResourceManagerClient>::unconditional_release_ref(&v63);
    if ( v33 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v62);
    v52 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v52);
      CoTaskMemFree(v52);
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v68);
    if ( v64 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v64);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v74) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xBB5,
                     (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
                     v53);
    return (unsigned int)v74;
  }
  return result;
}

```

## disassembly

```asm
0x180044780  mov     [rsp+arg_10], r8
0x180044785  mov     [rsp+arg_0], rcx
0x18004478a  push    rbx
0x18004478b  push    rsi
0x18004478c  push    rdi
0x18004478d  push    r12
0x18004478f  push    r13
0x180044791  push    r14
0x180044793  push    r15
0x180044795  sub     rsp, 0F0h
0x18004479c  mov     ebx, r9d
0x18004479f  mov     rsi, r8
0x1800447a2  mov     r13, rdx
0x1800447a5  mov     rdi, rcx
0x1800447a8  xor     r14d, r14d
0x1800447ab  mov     [rsp+128h+var_108], ebx; int
0x1800447af  mov     r9, rdx; wchar_t *
0x1800447b2  lea     r8, aOpenimagestore; "OpenImageStore : basePath: %s, idxCreat"...
0x1800447b9  mov     edx, 0B7Ch; wchar_t *
0x1800447be  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800447c5  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x1800447ca  test    r13, r13
0x1800447cd  jz      loc_180044E2C
0x1800447d3  test    rsi, rsi
0x1800447d6  jz      loc_180044E2C
0x1800447dc  mov     rcx, [rdi+30h]
0x1800447e0  test    rcx, rcx
0x1800447e3  jz      short loc_1800447F1
0x1800447e5  mov     rax, [rcx]
0x1800447e8  mov     rax, [rax+40h]
0x1800447ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447f1  mov     ecx, ebx
0x1800447f3  sub     ecx, 1
0x1800447f6  jz      short loc_180044814
0x1800447f8  sub     ecx, 1
0x1800447fb  jz      short loc_18004480D
0x1800447fd  cmp     ecx, 2
0x180044800  jnz     loc_180044E7C
0x180044806  mov     esi, 2
0x18004480b  jmp     short loc_180044817
0x18004480d  mov     esi, 1
0x180044812  jmp     short loc_180044817
0x180044814  mov     esi, r14d
0x180044817  mov     r15, [rdi+18h]
0x18004481b  mov     r12, [r15]
0x18004481e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180044822  inc     rdi
0x180044825  cmp     [r13+rdi*2+0], r14w
0x18004482b  jnz     short loc_180044822
0x18004482d  test    edi, edi
0x18004482f  jz      short loc_18004484F
0x180044831  mov     ecx, edi; this
0x180044833  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180044838  mov     r14, rax
0x18004483b  mov     edx, edi
0x18004483d  add     rdx, rdx; DestinationSize
0x180044840  lea     rcx, [rax+1Ch]; Destination
0x180044844  mov     r9, rdx; SourceSize
0x180044847  mov     r8, r13; Source
0x18004484a  call    memcpy_s
0x18004484f  mov     [rsp+128h+arg_8], r14
0x180044857  mov     r9d, esi
0x18004485a  lea     r8, [rsp+128h+arg_8]
0x180044862  lea     rdx, [rsp+128h+var_F0]
0x180044867  mov     rcx, r15
0x18004486a  mov     rax, [r12+10h]
0x18004486f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044874  nop
0x180044875  mov     rcx, rax
0x180044878  call    ?get@?$consume_Windows_Foundation_IAsyncAction@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(void)
0x18004487d  nop
0x18004487e  xor     esi, esi
0x180044880  cmp     [rsp+128h+var_F0], rsi
0x180044885  jz      short loc_180044891
0x180044887  lea     rcx, [rsp+128h+var_F0]
0x18004488c  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180044891  lea     r8, aOpenimagestore_0; "OpenImageStore: Models are available"
0x180044898  mov     edx, 0B8Bh; wchar_t *
0x18004489d  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800448a4  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1800448a9  cmp     ebx, 4
0x1800448ac  jnz     short loc_1800448B4
0x1800448ae  lea     r15d, [rbx-2]
0x1800448b2  jmp     short loc_1800448CB
0x1800448b4  cmp     ebx, 1
0x1800448b7  jnz     short loc_1800448BE
0x1800448b9  mov     r15d, esi
0x1800448bc  jmp     short loc_1800448CB
0x1800448be  cmp     ebx, 2
0x1800448c1  jnz     loc_180044E07
0x1800448c7  lea     r15d, [rbx-1]
0x1800448cb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800448cf  inc     rbx
0x1800448d2  cmp     [r13+rbx*2+0], si
0x1800448d8  jnz     short loc_1800448CF
0x1800448da  test    ebx, ebx
0x1800448dc  jnz     short loc_1800448E3
0x1800448de  mov     rdi, rsi
0x1800448e1  jmp     short loc_180044901
0x1800448e3  mov     ecx, ebx; this
0x1800448e5  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800448ea  mov     rdi, rax
0x1800448ed  mov     edx, ebx
0x1800448ef  add     rdx, rdx; DestinationSize
0x1800448f2  lea     rcx, [rax+1Ch]; Destination
0x1800448f6  mov     r9, rdx; SourceSize
0x1800448f9  mov     r8, r13; Source
0x1800448fc  call    memcpy_s
0x180044901  mov     [rsp+128h+var_F8], rdi
0x180044906  test    rdi, rdi
0x180044909  jz      short loc_180044946
0x18004490b  test    byte ptr [rdi], 1
0x18004490e  jnz     short loc_180044919
0x180044910  lock inc dword ptr [rdi+18h]
0x180044914  mov     rsi, rdi
0x180044917  jmp     short loc_180044946
0x180044919  mov     r14d, [rdi+4]
0x18004491d  test    r14d, r14d
0x180044920  jz      short loc_180044946
0x180044922  mov     rbx, [rdi+10h]
0x180044926  mov     ecx, r14d; this
0x180044929  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18004492e  mov     rsi, rax
0x180044931  mov     edx, r14d
0x180044934  add     rdx, rdx; DestinationSize
0x180044937  lea     rcx, [rax+1Ch]; Destination
0x18004493b  mov     r9, rdx; SourceSize
0x18004493e  mov     r8, rbx; Source
0x180044941  call    memcpy_s
0x180044946  mov     [rsp+128h+arg_8], rsi
0x18004494e  mov     r8d, r15d
0x180044951  lea     rdx, [rsp+128h+arg_8]
0x180044959  lea     rcx, [rsp+128h+var_E0]
0x18004495e  call    ?GetSemanticImageIndexStoreOptions@Utils@@YA?AUSemanticImageIndexStoreOptions@SemanticSearch@Windows@Microsoft@winrt@@AEBUhstring@6@W4IndexCreationDisposition@3456@@Z; Utils::GetSemanticImageIndexStoreOptions(winrt::hstring const &,winrt::Microsoft::Windows::SemanticSearch::IndexCreationDisposition)
0x180044963  nop
0x180044964  xor     r15d, r15d
0x180044967  test    rsi, rsi
0x18004496a  jz      short loc_18004498D
0x18004496c  or      eax, 0FFFFFFFFh
0x18004496f  lock xadd [rsi+18h], eax
0x180044974  sub     eax, 1
0x180044977  jnz     short loc_1800449CC
0x180044979  nop
0x18004497a  call    WINRT_IMPL_GetProcessHeap
0x18004497f  mov     rcx, rax; hHeap
0x180044982  mov     r8, rsi; lpMem
0x180044985  xor     edx, edx; dwFlags
0x180044987  call    WINRT_IMPL_HeapFree
0x18004498c  nop
0x18004498d  test    rdi, rdi
0x180044990  jz      short loc_1800449B2
0x180044992  or      eax, 0FFFFFFFFh
0x180044995  lock xadd [rdi+18h], eax
0x18004499a  sub     eax, 1
0x18004499d  jnz     short loc_1800449D7
0x18004499f  nop
0x1800449a0  call    WINRT_IMPL_GetProcessHeap
0x1800449a5  mov     rcx, rax; hHeap
0x1800449a8  mov     r8, rdi; lpMem
0x1800449ab  xor     edx, edx; dwFlags
0x1800449ad  call    WINRT_IMPL_HeapFree
0x1800449b2  mov     rcx, [rsp+128h+var_E0]
0x1800449b7  mov     [rsp+128h+arg_8], r15
0x1800449bf  test    rcx, rcx
0x1800449c2  jnz     short loc_1800449E2
0x1800449c4  mov     eax, r15d
0x1800449c7  mov     rcx, r15
0x1800449ca  jmp     short loc_180044A0C
0x1800449cc  test    eax, eax
0x1800449ce  jns     short loc_18004498D
0x1800449d0  call    cs:__imp_abort
0x1800449d7  test    eax, eax
0x1800449d9  jns     short loc_1800449B2
0x1800449db  call    cs:__imp_abort
0x1800449e2  mov     rax, [rcx]
0x1800449e5  lea     r8, [rsp+128h+arg_8]
0x1800449ed  lea     rdx, ??$guid_v@UISemanticImageIndexStoreOptions3@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreOptions3>
0x1800449f4  mov     rax, [rax]
0x1800449f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800449fc  mov     rcx, [rsp+128h+arg_8]
0x180044a04  mov     [rsp+128h+arg_8], rcx
0x180044a0c  mov     [rsp+128h+var_D8], r15d
0x180044a11  xorps   xmm0, xmm0
0x180044a14  movdqu  [rsp+128h+var_D0], xmm0
0x180044a1a  test    eax, eax
0x180044a1c  js      loc_180044EAF
0x180044a22  mov     [rsp+128h+var_D8], r15d
0x180044a27  movdqu  [rsp+128h+var_D0], xmm0
0x180044a2d  mov     rax, [rcx]
0x180044a30  xor     edx, edx
0x180044a32  mov     rax, [rax+38h]
0x180044a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a3b  test    eax, eax
0x180044a3d  js      loc_180044EBB
0x180044a43  lea     rcx, [rsp+128h+arg_8]
0x180044a4b  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180044a50  lea     rcx, [rsp+128h+var_B8]
0x180044a55  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180044a5a  nop
0x180044a5b  mov     rbx, [rsp+128h+pv]
0x180044a63  mov     [rsp+128h+arg_8], rbx
0x180044a6b  test    rbx, rbx
0x180044a6e  jz      short loc_180044A77
0x180044a70  lock inc dword ptr [rbx+120h]
0x180044a77  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180044a7e  call    cs:__imp_EnterCriticalSection
0x180044a84  inc     dword ptr [rbx+0F0h]
0x180044a8a  mov     dword ptr [rbx+110h], 5
0x180044a94  lea     rcx, [rsp+128h+arg_8]
0x180044a9c  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180044aa1  lea     rax, [rsp+128h+var_E0]
0x180044aa6  mov     [rsp+128h+arg_8], rax
0x180044aae  lea     rax, qword_1800AF658
0x180044ab5  mov     [rsp+128h+var_F8], rax
0x180044aba  lock inc cs:qword_1800AF658
0x180044ac2  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>
0x180044ac9  test    rcx, rcx
0x180044acc  jz      short loc_180044B1C
0x180044ace  mov     [rsp+128h+arg_8], r15
0x180044ad6  mov     [rsp+128h+var_D8], r15d
0x180044adb  xorps   xmm0, xmm0
0x180044ade  movdqu  [rsp+128h+var_D0], xmm0
0x180044ae4  mov     rax, [rcx]
0x180044ae7  lea     r8, [rsp+128h+arg_8]
0x180044aef  mov     rdx, [rsp+128h+var_E0]
0x180044af4  mov     rax, [rax+40h]
0x180044af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044afd  test    eax, eax
0x180044aff  js      loc_180044EC8
0x180044b05  mov     rbx, [rsp+128h+arg_8]
0x180044b0d  mov     [rsp+128h+var_F0], rbx
0x180044b12  lock dec cs:qword_1800AF658
0x180044b1a  jmp     short loc_180044B3B
0x180044b1c  lock dec cs:qword_1800AF658
0x180044b24  lea     r8, [rsp+128h+arg_8]
0x180044b2c  lea     rdx, [rsp+128h+var_F0]
0x180044b31  call    ??$call@AEAV_lambda_9293e9b3e542a45805ed53334864e622_@@@?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_9293e9b3e542a45805ed53334864e622_@@@Z
0x180044b36  mov     rbx, [rsp+128h+var_F0]
0x180044b3b  mov     edx, 1D4C0h
0x180044b40  lea     rcx, [rsp+128h+var_F0]
0x180044b45  call    ??$wait_for_completed@U?$IAsyncOperation@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@1@I@Z
0x180044b4a  lea     rdx, [rsp+128h+arg_8]
0x180044b52  test    eax, eax
0x180044b54  jz      loc_180044ED5
0x180044b5a  lea     rcx, [rsp+128h+var_F0]
0x180044b5f  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@USemanticImageIndexStore@SemanticSearch@3Microsoft@4@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>,winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>::get(void)
0x180044b64  nop
0x180044b65  mov     r8, rax
0x180044b68  mov     rsi, [rsp+128h+arg_0]
0x180044b70  mov     rdx, [rsi+20h]
0x180044b74  lea     rcx, [rsp+128h+var_E8]
0x180044b79  call    ??$make@UIndexerSemanticStore@@AEAUIEnclaveInterface@@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@winrt@@YA?A_PAEAUIEnclaveInterface@@$$QEAUSemanticImageIndexStore@SemanticSearch@Windows@Microsoft@0@@Z
0x180044b7e  nop
0x180044b7f  cmp     [rsp+128h+arg_8], r15
0x180044b87  jz      short loc_180044B96
0x180044b89  lea     rcx, [rsp+128h+arg_8]
0x180044b91  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180044b96  mov     rcx, [rsp+128h]; this
0x180044b9e  mov     rdi, [rsp+128h+var_E8]
0x180044ba3  test    rdi, rdi
0x180044ba6  jz      loc_180044F5D
0x180044bac  lea     r14, [rsi+30h]
0x180044bb0  cmp     [r14], rdi
0x180044bb3  jz      short loc_180044BDA
0x180044bb5  cmp     [r14], r15
0x180044bb8  jz      short loc_180044BC2
0x180044bba  mov     rcx, r14
0x180044bbd  call    ?unconditional_release_ref@?$com_ptr@UIAIFabricResourceManagerClient@@@winrt@@AEAAXXZ; winrt::com_ptr<IAIFabricResourceManagerClient>::unconditional_release_ref(void)
0x180044bc2  mov     [r14], rdi
0x180044bc5  test    rdi, rdi
0x180044bc8  jz      short loc_180044BDA
0x180044bca  mov     rax, [rdi]
0x180044bcd  mov     rcx, rdi
0x180044bd0  mov     rax, [rax+8]
0x180044bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044bd9  nop
0x180044bda  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58816171@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58816171@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58816171> `wil::Feature<__WilFeatureTraits_Feature_58816171>::GetImpl(void)'::`2'::impl
0x180044be1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58816171@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58816171>::__private_IsEnabled(void)
0x180044be6  test    al, al
0x180044be8  jz      short loc_180044C57
0x180044bea  mov     rsi, cs:?g_singletonIndexerSemanticSearchServices@@3U?$com_ptr@UIndexerSemanticSearchServicesImpl@@@winrt@@A; winrt::com_ptr<IndexerSemanticSearchServicesImpl> g_singletonIndexerSemanticSearchServices
0x180044bf1  mov     rdi, [r14]
0x180044bf4  mov     [rsp+128h+var_F8], rdi
0x180044bf9  test    rdi, rdi
0x180044bfc  jz      short loc_180044C0E
0x180044bfe  mov     rax, [rdi]
0x180044c01  mov     rcx, rdi
0x180044c04  mov     rax, [rax+8]
0x180044c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c0d  nop
0x180044c0e  cmp     [rsi+0A8h], rdi
0x180044c15  jz      short loc_180044C48
0x180044c17  cmp     [rsi+0A8h], r15
0x180044c1e  jz      short loc_180044C2C
0x180044c20  lea     rcx, [rsi+0A8h]
0x180044c27  call    ?unconditional_release_ref@?$com_ptr@UIAIFabricResourceManagerClient@@@winrt@@AEAAXXZ; winrt::com_ptr<IAIFabricResourceManagerClient>::unconditional_release_ref(void)
0x180044c2c  mov     [rsi+0A8h], rdi
0x180044c33  test    rdi, rdi
0x180044c36  jz      short loc_180044C48
0x180044c38  mov     rax, [rdi]
  ... truncated ...
```
