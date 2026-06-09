# IndexerSemanticStoreManagerImpl::OpenTextStore(wchar_t *,IIndexerSemanticStore * *,tagIndexCreationDisposition)

- ea: `0x180044f80`
- end: `0x1800456fc`
- name: `?OpenTextStore@IndexerSemanticStoreManagerImpl@@UEAAJPEA_WPEAPEAUIIndexerSemanticStore@@W4tagIndexCreationDisposition@@@Z`
- size: `1916`
- prototype: `__int64 __fastcall(_QWORD *, const wchar_t *, _QWORD *, int)`
- caller_count: `0`
- callee_count: `35`
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
- `0x18002c874`
- `0x18002e86c`
- `0x18002f924`
- `0x180030700`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x180032c94`
- `0x180032ca0`
- `0x18003d008`
- `0x180044f80`
- `0x18004b710`
- `0x18004ba10`
- `0x18004dea8`
- `0x18004ff60`
- `0x18005054c`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800451cd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800451d8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800455fb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800451cd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800451d8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800455fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045431`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045431`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004527b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045405`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004527b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045405`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045567`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045567`

## string_xrefs

- `0x180045623`: `onecoreuap\base\appmodel\Search\common\AIFabricHostHelper\include\Utils.h`
- `0x180044fbe`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18004509b`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180045510`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x1800455c6`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18004559d`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x1800456e9`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x1800455ba`: `OpenTextStore : Invalid arguments basePath: %s, store: %p`
- `0x180044fb2`: `OpenTextStore : basePath: %s, idxCreationDisposition: %lu`
- `0x18004568e`: `SemanticTextIndexStore::CreateAsync timed out`
- `0x18004508f`: `OpenTextStore: Models are available`
- `0x180045504`: `OpenTextStore : Successfully completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall IndexerSemanticStoreManagerImpl::OpenTextStore(_QWORD *a1, const wchar_t *a2, _QWORD *a3, int a4)
{
  struct winrt::impl::shared_hstring_header *v8; // r14
  unsigned int v9; // edx
  __int64 v10; // rcx
  unsigned int v11; // esi
  __int64 *v12; // r15
  __int64 v13; // r13
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
  __int64 v35; // rax
  __int64 v36; // rdi
  _QWORD *v37; // rsi
  _DWORD *v38; // rdi
  struct _RTL_CRITICAL_SECTION *v39; // rsi
  unsigned int v40; // edx
  IndexerSemanticSearchServicesImpl *v41; // r13
  __int64 v42; // rdi
  struct winrt::impl::shared_hstring_header *v43; // rsi
  volatile signed __int32 *v44; // r14
  __int64 v45; // r15
  const void *v46; // rdi
  const wchar_t *v47; // r9
  int v48; // eax
  HANDLE v49; // rax
  void *v50; // rbx
  const char *v51; // r9
  __int64 result; // rax
  const char *v53; // r9
  __int64 v54; // rax
  __int64 v55; // rbx
  unsigned int *v56; // rax
  const char *v58; // [rsp+28h] [rbp-100h]
  __int64 (__fastcall ****v59)(_QWORD, __int64 *, LPVOID *); // [rsp+30h] [rbp-F8h] BYREF
  __int64 v60; // [rsp+38h] [rbp-F0h] BYREF
  __int64 (__fastcall ***v61)(_QWORD, __int64 *, LPVOID *); // [rsp+40h] [rbp-E8h] BYREF
  volatile signed __int32 *v62; // [rsp+48h] [rbp-E0h] BYREF
  int v63; // [rsp+50h] [rbp-D8h] BYREF
  __int128 v64; // [rsp+58h] [rbp-D0h]
  char v65[8]; // [rsp+70h] [rbp-B8h] BYREF
  char v66[48]; // [rsp+78h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-80h]
  _BYTE pExceptionObject[24]; // [rsp+B0h] [rbp-78h] BYREF
  _BYTE v69[96]; // [rsp+C8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]
  __int64 (__fastcall ****v72)(_QWORD, __int64 *, LPVOID *); // [rsp+138h] [rbp+10h] BYREF
  _QWORD *v73; // [rsp+140h] [rbp+18h]

  v73 = a3;
  v8 = 0;
  SearchIndexerTrace::Information(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
    (const wchar_t *)0xB3D,
    (unsigned int)L"OpenTextStore : basePath: %s, idxCreationDisposition: %lu",
    a2);
  try
  {
    if ( !a2 || !a3 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const wchar_t *)0xB41,
        (unsigned int)L"OpenTextStore : Invalid arguments basePath: %s, store: %p",
        a2,
        a3);
      return 2147500035LL;
    }
    v10 = a1[5];
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
        v53 = (const char *)(unsigned int)wil::verify_hresult(2147549183LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x33,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\AIFabricHostHelper\\include\\Utils.h",
          v53,
          (int)"Unexpected disposition.",
          v58);
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
    v72 = (__int64 (__fastcall ****)(_QWORD, __int64 *, LPVOID *))v8;
    v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 (__fastcall *****)(_QWORD, __int64 *, LPVOID *), __int64 (__fastcall *****)(_QWORD, __int64 *, LPVOID *), _QWORD))(v13 + 8))(
            v12,
            &v59,
            &v72,
            v11);
    winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(v15);
    v17 = 0;
    if ( v59 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v59);
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0xB4C,
      (unsigned int)L"OpenTextStore: Models are available",
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
    v62 = (volatile signed __int32 *)v21;
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
    v72 = (__int64 (__fastcall ****)(_QWORD, __int64 *, LPVOID *))v17;
    Utils::GetSemanticTextIndexStoreOptions(&v61, &v72, v19);
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
    v72 = 0;
    if ( v61 )
    {
      v28 = (**v61)(
              v61,
              winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreOptions3>,
              (LPVOID *)&v72);
      v29 = v72;
    }
    else
    {
      v28 = 0;
      v29 = 0;
    }
    v63 = 0;
    v64 = 0;
    if ( v28 < 0 )
      winrt::throw_hresult((unsigned int)v28, &v63);
    v63 = 0;
    v64 = 0;
    v30 = ((__int64 (__fastcall *)(__int64 (__fastcall ****)(_QWORD, __int64 *, LPVOID *), _QWORD))(*v29)[7])(v29, 0);
    if ( v30 < 0 )
      winrt::throw_hresult((unsigned int)v30, &v63);
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v72);
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(v65);
    v31 = (struct _RTL_CRITICAL_SECTION *)pv;
    v72 = (__int64 (__fastcall ****)(_QWORD, __int64 *, LPVOID *))pv;
    if ( pv )
      _InterlockedIncrement((volatile signed __int32 *)pv + 72);
    EnterCriticalSection(v31 + 5);
    ++LODWORD(v31[6].DebugInfo);
    LODWORD(v31[6].SpinCount) = 4;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v72);
    v72 = &v61;
    v62 = (volatile signed __int32 *)&qword_1800AF6D8;
    _InterlockedIncrement64(&qword_1800AF6D8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> )
    {
      v72 = 0;
      v63 = 0;
      v64 = 0;
      v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>
                                                                 + 64LL))(
              winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>,
              v61,
              (LPVOID *)&v72);
      if ( v32 < 0 )
        winrt::throw_hresult((unsigned int)v32, &v63);
      v33 = v72;
      v59 = v72;
      _InterlockedDecrement64(&qword_1800AF6D8);
    }
    else
    {
      _InterlockedDecrement64(&qword_1800AF6D8);
      winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>::call<_lambda_35390557c02a2fbcb54347936c615a82_ &>(
        0,
        &v59,
        &v72);
      v33 = v59;
    }
    if ( !(unsigned int)winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>>(
                          &v59,
                          120000) )
    {
      v54 = tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(
              v65,
              &v72);
      *(_BYTE *)(std::unique_ptr<wil::srwlock>::operator->(v54) + 276) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v72);
      v55 = winrt::impl::slim_source_location::current(&v63);
      winrt::param::hstring::hstring((winrt::param::hstring *)v69, L"SemanticTextIndexStore::CreateAsync timed out");
      v56 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v72, -2147023436);
      winrt::hresult_error::hresult_error(pExceptionObject, *v56, v69, v55);
      throw (winrt::hresult_error *)pExceptionObject;
    }
    v34 = winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>::get(
            &v59,
            &v72);
    winrt::make<IndexerSemanticStore,IEnclaveInterface &,winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>(
      &v60,
      a1[4],
      v34);
    if ( v72 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v72);
    v35 = v60;
    if ( !v60 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB5F,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const char *)0x8007000ELL,
        a4);
    v36 = v60;
    v37 = a1 + 5;
    if ( a1[5] != v60 )
    {
      if ( *v37 )
        winrt::com_ptr<IAIFabricResourceManagerClient>::unconditional_release_ref(a1 + 5);
      *v37 = v36;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
      v35 = v60;
    }
    v60 = 0;
    *v73 = v35;
    v38 = pv;
    v39 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    v38[18] |= 0x300u;
    if ( *((_QWORD *)v38 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper(v38 + 2, 2);
    if ( v39 )
      LeaveCriticalSection(v39);
    v41 = g_singletonIndexerSemanticSearchServices;
    v42 = -1;
    do
      ++v42;
    while ( a2[v42] );
    if ( (_DWORD)v42 )
    {
      v43 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v42, v40);
      memcpy_s((char *)v43 + 28, 2LL * (unsigned int)v42, a2, 2LL * (unsigned int)v42);
    }
    else
    {
      v43 = 0;
    }
    v72 = (__int64 (__fastcall ****)(_QWORD, __int64 *, LPVOID *))v43;
    if ( v43 )
    {
      if ( (*(_BYTE *)v43 & 1) == 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v43 + 6);
        v44 = (volatile signed __int32 *)v43;
        goto LABEL_75;
      }
      v45 = *((unsigned int *)v43 + 1);
      if ( (_DWORD)v45 )
      {
        v46 = (const void *)*((_QWORD *)v43 + 2);
        v44 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v45, v40);
        memcpy_s((void *const)(v44 + 7), 2 * v45, v46, 2 * v45);
        goto LABEL_75;
      }
    }
    v44 = 0;
LABEL_75:
    v62 = v44;
    IndexerSemanticSearchServicesImpl::SetTextIndexStorePath((__int64)v41, &v62);
    if ( v43 )
    {
      v48 = _InterlockedDecrement((volatile signed __int32 *)v43 + 6);
      if ( v48 )
      {
        if ( v48 < 0 )
          abort();
      }
      else
      {
        v49 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v49, 0, v43);
      }
    }
    SearchIndexerTrace::Information(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0xB68,
      (unsigned int)L"OpenTextStore : Successfully completed",
      v47);
    if ( v60 )
      winrt::com_ptr<IAIFabricResourceManagerClient>::unconditional_release_ref(&v60);
    if ( v33 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v59);
    v50 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v50);
      CoTaskMemFree(v50);
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v66);
    if ( v61 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v61);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v72) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xB71,
                     (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
                     v51);
    return (unsigned int)v72;
  }
  return result;
}

```

## disassembly

```asm
0x180044f80  mov     [rsp+arg_10], r8
0x180044f85  mov     [rsp+arg_0], rcx
0x180044f8a  push    rbx
0x180044f8b  push    rsi
0x180044f8c  push    rdi
0x180044f8d  push    r12
0x180044f8f  push    r13
0x180044f91  push    r14
0x180044f93  push    r15
0x180044f95  sub     rsp, 0F0h
0x180044f9c  mov     ebx, r9d
0x180044f9f  mov     rsi, r8
0x180044fa2  mov     r12, rdx
0x180044fa5  mov     rdi, rcx
0x180044fa8  xor     r14d, r14d
0x180044fab  mov     [rsp+128h+var_108], ebx; int
0x180044faf  mov     r9, rdx; wchar_t *
0x180044fb2  lea     r8, aOpentextstoreB; "OpenTextStore : basePath: %s, idxCreati"...
0x180044fb9  mov     edx, 0B3Dh; wchar_t *
0x180044fbe  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180044fc5  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180044fca  test    r12, r12
0x180044fcd  jz      loc_1800455B2
0x180044fd3  test    rsi, rsi
0x180044fd6  jz      loc_1800455B2
0x180044fdc  mov     rcx, [rdi+28h]
0x180044fe0  test    rcx, rcx
0x180044fe3  jz      short loc_180044FF1
0x180044fe5  mov     rax, [rcx]
0x180044fe8  mov     rax, [rax+40h]
0x180044fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ff1  mov     ecx, ebx
0x180044ff3  sub     ecx, 1
0x180044ff6  jz      short loc_180045014
0x180044ff8  sub     ecx, 1
0x180044ffb  jz      short loc_18004500D
0x180044ffd  cmp     ecx, 2
0x180045000  jnz     loc_180045602
0x180045006  mov     esi, 2
0x18004500b  jmp     short loc_180045017
0x18004500d  mov     esi, 1
0x180045012  jmp     short loc_180045017
0x180045014  mov     esi, r14d
0x180045017  mov     r15, [rdi+18h]
0x18004501b  mov     r13, [r15]
0x18004501e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180045022  inc     rdi
0x180045025  cmp     [r12+rdi*2], r14w
0x18004502a  jnz     short loc_180045022
0x18004502c  test    edi, edi
0x18004502e  jz      short loc_18004504E
0x180045030  mov     ecx, edi; this
0x180045032  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180045037  mov     r14, rax
0x18004503a  mov     edx, edi
0x18004503c  add     rdx, rdx; DestinationSize
0x18004503f  lea     rcx, [rax+1Ch]; Destination
0x180045043  mov     r9, rdx; SourceSize
0x180045046  mov     r8, r12; Source
0x180045049  call    memcpy_s
0x18004504e  mov     [rsp+128h+arg_8], r14
0x180045056  mov     r9d, esi
0x180045059  lea     r8, [rsp+128h+arg_8]
0x180045061  lea     rdx, [rsp+128h+var_F8]
0x180045066  mov     rcx, r15
0x180045069  mov     rax, [r13+8]
0x18004506d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045072  nop
0x180045073  mov     rcx, rax
0x180045076  call    ?get@?$consume_Windows_Foundation_IAsyncAction@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncAction<winrt::Windows::Foundation::IAsyncAction>::get(void)
0x18004507b  nop
0x18004507c  xor     esi, esi
0x18004507e  cmp     [rsp+128h+var_F8], rsi
0x180045083  jz      short loc_18004508F
0x180045085  lea     rcx, [rsp+128h+var_F8]
0x18004508a  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18004508f  lea     r8, aOpentextstoreM; "OpenTextStore: Models are available"
0x180045096  mov     edx, 0B4Ch; wchar_t *
0x18004509b  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800450a2  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1800450a7  cmp     ebx, 4
0x1800450aa  jnz     short loc_1800450B2
0x1800450ac  lea     r15d, [rbx-2]
0x1800450b0  jmp     short loc_1800450C9
0x1800450b2  cmp     ebx, 1
0x1800450b5  jnz     short loc_1800450BC
0x1800450b7  mov     r15d, esi
0x1800450ba  jmp     short loc_1800450C9
0x1800450bc  cmp     ebx, 2
0x1800450bf  jnz     loc_18004558D
0x1800450c5  lea     r15d, [rbx-1]
0x1800450c9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800450cd  inc     rbx
0x1800450d0  cmp     [r12+rbx*2], si
0x1800450d5  jnz     short loc_1800450CD
0x1800450d7  test    ebx, ebx
0x1800450d9  jnz     short loc_1800450E0
0x1800450db  mov     rdi, rsi
0x1800450de  jmp     short loc_1800450FE
0x1800450e0  mov     ecx, ebx; this
0x1800450e2  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800450e7  mov     rdi, rax
0x1800450ea  mov     edx, ebx
0x1800450ec  add     rdx, rdx; DestinationSize
0x1800450ef  lea     rcx, [rax+1Ch]; Destination
0x1800450f3  mov     r9, rdx; SourceSize
0x1800450f6  mov     r8, r12; Source
0x1800450f9  call    memcpy_s
0x1800450fe  mov     [rsp+128h+var_E0], rdi
0x180045103  test    rdi, rdi
0x180045106  jz      short loc_180045143
0x180045108  test    byte ptr [rdi], 1
0x18004510b  jnz     short loc_180045116
0x18004510d  lock inc dword ptr [rdi+18h]
0x180045111  mov     rsi, rdi
0x180045114  jmp     short loc_180045143
0x180045116  mov     r14d, [rdi+4]
0x18004511a  test    r14d, r14d
0x18004511d  jz      short loc_180045143
0x18004511f  mov     rbx, [rdi+10h]
0x180045123  mov     ecx, r14d; this
0x180045126  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18004512b  mov     rsi, rax
0x18004512e  mov     edx, r14d
0x180045131  add     rdx, rdx; DestinationSize
0x180045134  lea     rcx, [rax+1Ch]; Destination
0x180045138  mov     r9, rdx; SourceSize
0x18004513b  mov     r8, rbx; Source
0x18004513e  call    memcpy_s
0x180045143  mov     [rsp+128h+arg_8], rsi
0x18004514b  mov     r8d, r15d
0x18004514e  lea     rdx, [rsp+128h+arg_8]
0x180045156  lea     rcx, [rsp+128h+var_E8]
0x18004515b  call    ?GetSemanticTextIndexStoreOptions@Utils@@YA?AUSemanticTextIndexStoreOptions@SemanticSearch@Windows@Microsoft@winrt@@AEBUhstring@6@W4IndexCreationDisposition@3456@@Z; Utils::GetSemanticTextIndexStoreOptions(winrt::hstring const &,winrt::Microsoft::Windows::SemanticSearch::IndexCreationDisposition)
0x180045160  nop
0x180045161  xor     r15d, r15d
0x180045164  test    rsi, rsi
0x180045167  jz      short loc_18004518A
0x180045169  or      eax, 0FFFFFFFFh
0x18004516c  lock xadd [rsi+18h], eax
0x180045171  sub     eax, 1
0x180045174  jnz     short loc_1800451C9
0x180045176  nop
0x180045177  call    WINRT_IMPL_GetProcessHeap
0x18004517c  mov     rcx, rax; hHeap
0x18004517f  mov     r8, rsi; lpMem
0x180045182  xor     edx, edx; dwFlags
0x180045184  call    WINRT_IMPL_HeapFree
0x180045189  nop
0x18004518a  test    rdi, rdi
0x18004518d  jz      short loc_1800451AF
0x18004518f  or      eax, 0FFFFFFFFh
0x180045192  lock xadd [rdi+18h], eax
0x180045197  sub     eax, 1
0x18004519a  jnz     short loc_1800451D4
0x18004519c  nop
0x18004519d  call    WINRT_IMPL_GetProcessHeap
0x1800451a2  mov     rcx, rax; hHeap
0x1800451a5  mov     r8, rdi; lpMem
0x1800451a8  xor     edx, edx; dwFlags
0x1800451aa  call    WINRT_IMPL_HeapFree
0x1800451af  mov     rcx, [rsp+128h+var_E8]
0x1800451b4  mov     [rsp+128h+arg_8], r15
0x1800451bc  test    rcx, rcx
0x1800451bf  jnz     short loc_1800451DF
0x1800451c1  mov     eax, r15d
0x1800451c4  mov     rcx, r15
0x1800451c7  jmp     short loc_180045209
0x1800451c9  test    eax, eax
0x1800451cb  jns     short loc_18004518A
0x1800451cd  call    cs:__imp_abort
0x1800451d4  test    eax, eax
0x1800451d6  jns     short loc_1800451AF
0x1800451d8  call    cs:__imp_abort
0x1800451df  mov     rax, [rcx]
0x1800451e2  lea     r8, [rsp+128h+arg_8]
0x1800451ea  lea     rdx, ??$guid_v@UISemanticTextIndexStoreOptions3@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreOptions3>
0x1800451f1  mov     rax, [rax]
0x1800451f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451f9  mov     rcx, [rsp+128h+arg_8]
0x180045201  mov     [rsp+128h+arg_8], rcx
0x180045209  mov     [rsp+128h+var_D8], r15d
0x18004520e  xorps   xmm0, xmm0
0x180045211  movdqu  [rsp+128h+var_D0], xmm0
0x180045217  test    eax, eax
0x180045219  js      loc_180045635
0x18004521f  mov     [rsp+128h+var_D8], r15d
0x180045224  movdqu  [rsp+128h+var_D0], xmm0
0x18004522a  mov     rax, [rcx]
0x18004522d  xor     edx, edx
0x18004522f  mov     rax, [rax+38h]
0x180045233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045238  test    eax, eax
0x18004523a  js      loc_180045641
0x180045240  lea     rcx, [rsp+128h+arg_8]
0x180045248  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18004524d  lea     rcx, [rsp+128h+var_B8]
0x180045252  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180045257  nop
0x180045258  mov     rbx, [rsp+128h+pv]
0x180045260  mov     [rsp+128h+arg_8], rbx
0x180045268  test    rbx, rbx
0x18004526b  jz      short loc_180045274
0x18004526d  lock inc dword ptr [rbx+120h]
0x180045274  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18004527b  call    cs:__imp_EnterCriticalSection
0x180045281  inc     dword ptr [rbx+0F0h]
0x180045287  mov     dword ptr [rbx+110h], 4
0x180045291  lea     rcx, [rsp+128h+arg_8]
0x180045299  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18004529e  lea     rax, [rsp+128h+var_E8]
0x1800452a3  mov     [rsp+128h+arg_8], rax
0x1800452ab  lea     rax, qword_1800AF6D8
0x1800452b2  mov     [rsp+128h+var_E0], rax
0x1800452b7  lock inc cs:qword_1800AF6D8
0x1800452bf  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>
0x1800452c6  test    rcx, rcx
0x1800452c9  jz      short loc_180045319
0x1800452cb  mov     [rsp+128h+arg_8], r15
0x1800452d3  mov     [rsp+128h+var_D8], r15d
0x1800452d8  xorps   xmm0, xmm0
0x1800452db  movdqu  [rsp+128h+var_D0], xmm0
0x1800452e1  mov     rax, [rcx]
0x1800452e4  lea     r8, [rsp+128h+arg_8]
0x1800452ec  mov     rdx, [rsp+128h+var_E8]
0x1800452f1  mov     rax, [rax+40h]
0x1800452f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452fa  test    eax, eax
0x1800452fc  js      loc_18004564E
0x180045302  mov     rbx, [rsp+128h+arg_8]
0x18004530a  mov     [rsp+128h+var_F8], rbx
0x18004530f  lock dec cs:qword_1800AF6D8
0x180045317  jmp     short loc_180045338
0x180045319  lock dec cs:qword_1800AF6D8
0x180045321  lea     r8, [rsp+128h+arg_8]
0x180045329  lea     rdx, [rsp+128h+var_F8]
0x18004532e  call    ??$call@AEAV_lambda_35390557c02a2fbcb54347936c615a82_@@@?$factory_cache_entry@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_35390557c02a2fbcb54347936c615a82_@@@Z
0x180045333  mov     rbx, [rsp+128h+var_F8]
0x180045338  mov     edx, 1D4C0h
0x18004533d  lea     rcx, [rsp+128h+var_F8]
0x180045342  call    ??$wait_for_completed@U?$IAsyncOperation@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@1@I@Z
0x180045347  lea     rdx, [rsp+128h+arg_8]
0x18004534f  test    eax, eax
0x180045351  jz      loc_18004565B
0x180045357  lea     rcx, [rsp+128h+var_F8]
0x18004535c  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@USemanticTextIndexStore@SemanticSearch@3Microsoft@4@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>::get(void)
0x180045361  nop
0x180045362  mov     r8, rax
0x180045365  mov     r14, [rsp+128h+arg_0]
0x18004536d  mov     rdx, [r14+20h]
0x180045371  lea     rcx, [rsp+128h+var_F0]
0x180045376  call    ??$make@UIndexerSemanticStore@@AEAUIEnclaveInterface@@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@winrt@@YA?A_PAEAUIEnclaveInterface@@$$QEAUSemanticImageIndexStore@SemanticSearch@Windows@Microsoft@0@@Z
0x18004537b  nop
0x18004537c  cmp     [rsp+128h+arg_8], r15
0x180045384  jz      short loc_180045393
0x180045386  lea     rcx, [rsp+128h+arg_8]
0x18004538e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180045393  mov     rcx, [rsp+128h]; this
0x18004539b  mov     rax, [rsp+128h+var_F0]
0x1800453a0  test    rax, rax
0x1800453a3  jz      loc_1800456E3
0x1800453a9  mov     rdi, rax
0x1800453ac  lea     rsi, [r14+28h]
0x1800453b0  cmp     [rsi], rax
0x1800453b3  jz      short loc_1800453E3
0x1800453b5  cmp     [rsi], r15
0x1800453b8  jz      short loc_1800453C7
0x1800453ba  mov     rcx, rsi
0x1800453bd  call    ?unconditional_release_ref@?$com_ptr@UIAIFabricResourceManagerClient@@@winrt@@AEAAXXZ; winrt::com_ptr<IAIFabricResourceManagerClient>::unconditional_release_ref(void)
0x1800453c2  mov     rax, [rsp+128h+var_F0]
0x1800453c7  mov     [rsi], rdi
0x1800453ca  test    rdi, rdi
0x1800453cd  jz      short loc_1800453E3
0x1800453cf  mov     rax, [rdi]
0x1800453d2  mov     rcx, rdi
0x1800453d5  mov     rax, [rax+8]
0x1800453d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453de  mov     rax, [rsp+128h+var_F0]
0x1800453e3  mov     [rsp+128h+var_F0], r15
0x1800453e8  mov     rcx, [rsp+128h+arg_10]
0x1800453f0  mov     [rcx], rax
0x1800453f3  mov     rdi, [rsp+128h+pv]
0x1800453fb  lea     rsi, [rdi+0C8h]
0x180045402  mov     rcx, rsi; lpCriticalSection
0x180045405  call    cs:__imp_EnterCriticalSection
0x18004540b  or      dword ptr [rdi+48h], 300h
0x180045412  cmp     [rdi+0F8h], r15
0x180045419  jz      short loc_180045429
0x18004541b  mov     edx, 2
0x180045420  lea     rcx, [rdi+8]
0x180045424  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180045429  test    rsi, rsi
0x18004542c  jz      short loc_180045437
0x18004542e  mov     rcx, rsi; lpCriticalSection
0x180045431  call    cs:__imp_LeaveCriticalSection
0x180045437  mov     r13, cs:?g_singletonIndexerSemanticSearchServices@@3U?$com_ptr@UIndexerSemanticSearchServicesImpl@@@winrt@@A; winrt::com_ptr<IndexerSemanticSearchServicesImpl> g_singletonIndexerSemanticSearchServices
0x18004543e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180045442  inc     rdi
0x180045445  cmp     [r12+rdi*2], r15w
0x18004544a  jnz     short loc_180045442
  ... truncated ...
```
