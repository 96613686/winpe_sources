# IndexerSemanticStore::SearchText(winrt::hstring,winrt::Windows::Indexer::SemanticSearch::SemanticQueryParameters const &)

- ea: `0x180049b80`
- end: `0x18004a36d`
- name: `?SearchText@IndexerSemanticStore@@QEBA?AU?$IVector@USemanticQueryResult@SemanticSearch@Indexer@Windows@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@6@AEBUSemanticQueryParameters@SemanticSearch@Indexer@56@@Z`
- size: `2029`
- prototype: ``
- caller_count: `1`
- callee_count: `47`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180049ac0`

## callees

- `0x180004ca0`
- `0x1800058cb`
- `0x18000591f`
- `0x180007f72`
- `0x180009574`
- `0x18000c478`
- `0x1800142ac`
- `0x180015f90`
- `0x180018fa0`
- `0x180019c3c`
- `0x18001a464`
- `0x18001fcc0`
- `0x180021290`
- `0x180022760`
- `0x180028898`
- `0x180028c20`
- `0x18002e928`
- `0x18002f824`
- `0x18002f924`
- `0x18002fcf0`
- `0x180030e10`
- `0x1800313fc`
- `0x1800318c4`
- `0x180031bac`
- `0x180032254`
- `0x180032300`
- `0x1800326e8`
- `0x180032c94`
- `0x180032ca0`
- `0x180034dd8`
- `0x180034e2c`
- `0x1800373cc`
- `0x18003a7c4`
- `0x18003ef20`
- `0x1800402dc`
- `0x180040328`
- `0x180048248`
- `0x180048310`
- `0x1800486c0`
- `0x180048f24`
- `0x180049574`
- `0x180049b80`
- `0x18004b9bc`
- `0x18004d9c4`
- `0x18004dea8`
- `0x18004e888`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004a0f1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004a1ca`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004a0f1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004a1ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049f46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049f46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049dc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049e15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049e8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049f17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049dc2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049e15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049e8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049f17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a12f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a12f`

## string_xrefs

- `0x180049bd5`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180049d27`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18004a262`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18004a291`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
_QWORD *__fastcall IndexerSemanticStore::SearchText(
        __int64 a1,
        _QWORD *a2,
        volatile signed __int32 **a3,
        const wchar_t *a4)
{
  double v8; // xmm0_8
  unsigned int matched; // ebx
  char v10; // di
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int Ids; // eax
  unsigned int v18; // edi
  __int64 v19; // rbx
  struct _RTL_CRITICAL_SECTION *v20; // rdi
  struct _RTL_CRITICAL_SECTION *v21; // rdi
  __int64 *v22; // rax
  struct _RTL_CRITICAL_SECTION *v23; // rdi
  _DWORD *v24; // rdi
  struct _RTL_CRITICAL_SECTION *v25; // rsi
  struct _RTL_CRITICAL_SECTION *v26; // rdi
  unsigned int v27; // r14d
  unsigned int v28; // r15d
  int v29; // r14d
  int v30; // eax
  __int64 v31; // rax
  __int64 v32; // rdi
  __int64 v33; // rax
  __int64 v34; // rax
  int v35; // eax
  HANDLE ProcessHeap; // rax
  __int64 v37; // rcx
  int v38; // eax
  struct _RTL_CRITICAL_SECTION *v39; // rdi
  volatile signed __int32 *v40; // rbx
  int v41; // esi
  HANDLE v42; // rax
  int v44; // ebx
  __int64 v45; // rax
  int v46; // ebx
  unsigned int v47; // eax
  __int64 v48; // rax
  int v49; // r14d
  int v50; // esi
  int v51; // edi
  double v52; // xmm0_8
  unsigned int v53; // ebx
  unsigned int v54; // eax
  __int64 v55; // rbx
  __int64 v56; // [rsp+28h] [rbp-E0h]
  wchar_t *v57; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v58; // [rsp+50h] [rbp-B8h] BYREF
  struct _RTL_CRITICAL_SECTION *v59; // [rsp+58h] [rbp-B0h] BYREF
  int v60; // [rsp+60h] [rbp-A8h]
  int v61; // [rsp+64h] [rbp-A4h]
  __int64 v62; // [rsp+68h] [rbp-A0h]
  struct _RTL_CRITICAL_SECTION *v63; // [rsp+70h] [rbp-98h] BYREF
  __int64 v64; // [rsp+78h] [rbp-90h] BYREF
  struct _RTL_CRITICAL_SECTION *v65; // [rsp+80h] [rbp-88h] BYREF
  struct _RTL_CRITICAL_SECTION *v66; // [rsp+88h] [rbp-80h] BYREF
  __int64 v67; // [rsp+90h] [rbp-78h] BYREF
  __int64 v68; // [rsp+98h] [rbp-70h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp-68h] BYREF
  volatile signed __int32 *pExceptionObject; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v71; // [rsp+B0h] [rbp-58h]
  _QWORD *v72; // [rsp+C8h] [rbp-40h]
  volatile signed __int32 **v73; // [rsp+D0h] [rbp-38h]
  _BYTE v74[8]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v75[48]; // [rsp+E0h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+110h] [rbp+8h]
  _BYTE v77[32]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v78[24]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v79[8]; // [rsp+150h] [rbp+48h] BYREF
  int v80; // [rsp+158h] [rbp+50h]
  int v81; // [rsp+15Ch] [rbp+54h]

  v72 = a2;
  v73 = a3;
  LODWORD(v62) = 0;
  SearchIndexerTrace::Information(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
    (const wchar_t *)0x94C,
    (unsigned int)L"SearchText : Started",
    a4);
  winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions::SemanticQueryOptions((winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions *)&v64);
  v8 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::Threshold(a4);
  matched = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(a4);
  v10 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::ImageIndexCreationDisposition(a4);
  winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(
    a4,
    &v67);
  if ( *(float *)&v8 != -1.0 )
  {
    *(_DWORD *)v78 = 0;
    *(_OWORD *)&v78[8] = 0;
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 96LL))(v64);
    if ( v11 < 0 )
      winrt::throw_hresult((unsigned int)v11, v78);
  }
  if ( matched )
  {
    *(_DWORD *)v78 = 0;
    *(_OWORD *)&v78[8] = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v64 + 72LL))(v64, matched);
    if ( v12 < 0 )
      winrt::throw_hresult((unsigned int)v12, v78);
  }
  v13 = v10 & 2;
  if ( (v10 & 1) != 0 )
    v13 = (unsigned int)v13 | 1;
  *(_DWORD *)v78 = 0;
  *(_OWORD *)&v78[8] = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v64 + 56LL))(v64, v13);
  if ( v14 < 0 )
    winrt::throw_hresult((unsigned int)v14, v78);
  v15 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(&v67);
  v16 = v15;
  if ( v15 && v15 <= 0x7530 )
  {
    std::vector<winrt::guid>::vector<winrt::guid>(v78, v15);
    winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSet<winrt::Microsoft::Windows::Management::Deployment::IPackageSet>::Items(
      &v64,
      &v65);
    v59 = *(struct _RTL_CRITICAL_SECTION **)v78;
    v60 = (__int64)(*(_QWORD *)&v78[8] - *(_QWORD *)v78) >> 4;
    v61 = v81;
    Ids = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::GetIds(&v67);
    v18 = Ids;
    if ( Ids != v16 )
      SearchIndexerTrace::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const wchar_t *)0x979,
        (unsigned int)L"GetIds returned %lu items but expected %lu",
        (const wchar_t *)Ids,
        v16);
    v59 = *(struct _RTL_CRITICAL_SECTION **)v78;
    v60 = (__int64)(*(_QWORD *)&v78[8] - *(_QWORD *)v78) >> 4;
    v61 = v81;
    winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::guid>,winrt::guid>::ReplaceAll(&v65);
    SemanticSearchTelemetryAggregated::ReportSemanticSearchWorkIdsCount(v18);
    if ( v65 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v65);
    std::vector<winrt::guid>::~vector<winrt::guid>(v78);
  }
  v19 = 0;
  v58 = 0;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v74);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
  {
    v20 = (struct _RTL_CRITICAL_SECTION *)pv;
    v59 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv )
      _InterlockedIncrement((volatile signed __int32 *)pv + 72);
    EnterCriticalSection(v20 + 5);
    ++LODWORD(v20[6].DebugInfo);
    LODWORD(v20[6].SpinCount) = 17;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v59);
  }
  if ( *(_QWORD *)(a1 + 40) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
    {
      v21 = (struct _RTL_CRITICAL_SECTION *)pv;
      v59 = (struct _RTL_CRITICAL_SECTION *)pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 72);
      EnterCriticalSection(v21 + 5);
      ++LODWORD(v21[6].DebugInfo);
      LODWORD(v21[6].SpinCount) = 42;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v59);
    }
    pExceptionObject = *a3;
    v22 = (__int64 *)winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndex<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>::QueryText(
                       a1 + 40,
                       &v63,
                       &pExceptionObject,
                       &v64);
  }
  else
  {
    if ( !*(_QWORD *)(a1 + 48) )
      goto LABEL_35;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
    {
      v23 = (struct _RTL_CRITICAL_SECTION *)pv;
      v59 = (struct _RTL_CRITICAL_SECTION *)pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 72);
      EnterCriticalSection(v23 + 5);
      ++LODWORD(v23[6].DebugInfo);
      LODWORD(v23[6].SpinCount) = 43;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v59);
    }
    pExceptionObject = *a3;
    v22 = (__int64 *)winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticImageIndex<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>::QueryText(
                       a1 + 48,
                       &v63,
                       &pExceptionObject,
                       &v64);
  }
  if ( &v58 != v22 )
  {
    v19 = *v22;
    *v22 = 0;
    v58 = v19;
  }
  if ( v63 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v63);
LABEL_35:
  if ( !(unsigned __int8)winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(&v58) )
  {
    winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(
      &v58,
      &v57);
    v44 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v58);
    v45 = tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(
            v74,
            &v59);
    *(_DWORD *)(std::unique_ptr<wil::srwlock>::operator->(v45) + 280) = v44;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v59);
    if ( (unsigned int)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v58) == 110 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const wchar_t *)0x9A4,
        (unsigned int)L"SearchText : Query failed because models are not loaded hr(0x%08x)",
        (const wchar_t *)(unsigned int)v57);
    }
    else
    {
      v46 = (int)v57;
      v47 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v58);
      LODWORD(v56) = v46;
      SearchIndexerTrace::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const wchar_t *)0x9AB,
        (unsigned int)L"SearchText : Query failed with status %lu and hr(0x%08x)",
        (const wchar_t *)v47,
        v56);
    }
    v48 = winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(
            a4,
            &v59);
    v49 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(v48);
    v50 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::ImageIndexCreationDisposition(a4);
    v51 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(a4);
    v52 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::Threshold(a4);
    v53 = winrt::hresult::operator int(&v57);
    v54 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v58);
    wil::str_printf<std::wstring>(
      (__int64)v79,
      L"SearchText : Query failed with status %u and hr(0x%08X) [threshold=%.3f, maxMatchCount=%u, queryFlags=%u, itemIdQuerySetSize=%u]",
      v54,
      v53,
      *(float *)&v52,
      v51,
      v50,
      v49);
    winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::Private::Workloads::SessionManager::SessionManager>::~IAsyncOperation<winrt::Microsoft::Windows::Private::Workloads::SessionManager::SessionManager>(&v59);
    v55 = winrt::impl::slim_source_location::current(v78);
    winrt::param::hstring::hstring(v77, v79);
    winrt::hresult_error::hresult_error(&pExceptionObject, (unsigned int)v57, v77, v55);
    throw (winrt::hresult_error *)&pExceptionObject;
  }
  v24 = pv;
  v25 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
  v24[18] |= 0x300u;
  if ( *((_QWORD *)v24 + 31) )
    tip2::details::shared_data<0,0,0>::complete_helper(v24 + 2, 2);
  v26 = 0;
  if ( v25 )
    LeaveCriticalSection(v25);
  memset(v78, 0, sizeof(v78));
  winrt::single_threaded_vector<winrt::Windows::Indexer::SemanticSearch::SemanticQueryResult,std::allocator<winrt::Windows::Indexer::SemanticSearch::SemanticQueryResult>>(
    a2,
    (__int64 *)v78);
  v27 = 1;
  LODWORD(v62) = 1;
  std::vector<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtension>::_Tidy(v78);
  winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(
    &v58,
    &v65);
  v28 = 0;
  winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>,winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>::end(
    &v65,
    v79);
  while ( v28 != v80 )
  {
    v66 = v26;
    v29 = v27 | 4;
    LODWORD(v62) = v29;
    LODWORD(pExceptionObject) = (_DWORD)v26;
    v71 = 0;
    v30 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *, _QWORD, struct _RTL_CRITICAL_SECTION **))&v65->DebugInfo[1].Type)(
            v65,
            v28,
            &v66);
    if ( v30 < 0 )
      winrt::throw_hresult((unsigned int)v30, &pExceptionObject);
    v27 = v29 & 0xFFFFFFF9 | 2;
    LODWORD(v62) = v27;
    LODWORD(v57) = winrt::impl::consume_Microsoft_Windows_SemanticSearch_IItemQueryMatch<winrt::Microsoft::Windows::SemanticSearch::IItemQueryMatch>::ConfidenceScore(&v66);
    v31 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(
            &v66,
            &v59);
    v32 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(
            v31,
            &lpMem);
    v33 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(
            &v66,
            &v68);
    v34 = winrt::impl::consume_Microsoft_Windows_SemanticSearch_IItemRegion<winrt::Microsoft::Windows::SemanticSearch::IItemRegion>::ItemId(
            v33,
            v78);
    winrt::make<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticQueryResult,winrt::guid,winrt::hstring,float>(
      &v63,
      v34,
      v32,
      &v57);
    if ( v68 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v68);
    v26 = (struct _RTL_CRITICAL_SECTION *)lpMem;
    if ( lpMem )
    {
      v35 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v35 )
      {
        v26 = 0;
        if ( v35 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v26);
        v26 = 0;
      }
      lpMem = 0;
    }
    if ( v59 != v26 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v59);
    v37 = *a2;
    LODWORD(pExceptionObject) = (_DWORD)v26;
    v71 = 0;
    v38 = (*(__int64 (__fastcall **)(__int64, struct _RTL_CRITICAL_SECTION *))(*(_QWORD *)v37 + 104LL))(v37, v63);
    if ( v38 < 0 )
      winrt::throw_hresult((unsigned int)v38, &pExceptionObject);
    if ( v63 != v26 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v63);
    if ( v66 != v26 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v66);
    ++v28;
  }
  if ( v65 != v26 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v65);
  v39 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v39);
    CoTaskMemFree(v39);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v75);
  if ( v19 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v58);
  if ( v67 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v67);
  if ( v64 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v64);
  v40 = *a3;
  if ( *a3 )
  {
    v41 = _InterlockedDecrement(v40 + 6);
    if ( v41 )
    {
      if ( v41 < 0 )
        abort();
    }
    else
    {
      v42 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v42, 0, (LPVOID)v40);
    }
    *a3 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180049b80  mov     rax, rsp
0x180049b83  push    rbp
0x180049b84  push    rbx
0x180049b85  push    rsi
0x180049b86  push    rdi
0x180049b87  push    r12
0x180049b89  push    r13
0x180049b8b  push    r14
0x180049b8d  push    r15
0x180049b8f  lea     rbp, [rax-0C8h]
0x180049b96  sub     rsp, 188h
0x180049b9d  movaps  xmmword ptr [rax-58h], xmm6
0x180049ba1  mov     rax, cs:__security_cookie
0x180049ba8  xor     rax, rsp
0x180049bab  mov     qword ptr [rbp+0C0h+var_58], rax
0x180049baf  mov     r15, r9
0x180049bb2  mov     r12, r8
0x180049bb5  mov     r13, rdx
0x180049bb8  mov     r14, rcx
0x180049bbb  mov     [rbp+0C0h+var_100], rdx
0x180049bbf  mov     [rbp+0C0h+var_F8], r8
0x180049bc3  xor     esi, esi
0x180049bc5  mov     dword ptr [rsp+1C0h+var_160], esi
0x180049bc9  lea     r8, aSearchtextStar; "SearchText : Started"
0x180049bd0  mov     edx, 94Ch; wchar_t *
0x180049bd5  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180049bdc  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180049be1  lea     rcx, [rsp+1C0h+var_150]; this
0x180049be6  call    ??0SemanticQueryOptions@SemanticSearch@Windows@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions::SemanticQueryOptions(void)
0x180049beb  nop
0x180049bec  mov     rcx, r15
0x180049bef  call    ?Threshold@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::Threshold(void)
0x180049bf4  movaps  xmm6, xmm0
0x180049bf7  mov     rcx, r15
0x180049bfa  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x180049bff  mov     ebx, eax
0x180049c01  mov     rcx, r15
0x180049c04  call    ?ImageIndexCreationDisposition@?$consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions@UISemanticIndexStoreOptions@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::ImageIndexCreationDisposition(void)
0x180049c09  mov     edi, eax
0x180049c0b  lea     rdx, [rbp+0C0h+var_138]
0x180049c0f  mov     rcx, r15
0x180049c12  call    ?ErrorText@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(void)
0x180049c17  nop
0x180049c18  ucomiss xmm6, cs:__real@bf800000
0x180049c1f  jp      short loc_180049C23
0x180049c21  jz      short loc_180049C4A
0x180049c23  mov     rcx, [rsp+1C0h+var_150]
0x180049c28  mov     dword ptr [rbp+0C0h+var_90], esi
0x180049c2b  xorps   xmm0, xmm0
0x180049c2e  movdqu  [rbp+0C0h+var_90+8], xmm0
0x180049c33  mov     rax, [rcx]
0x180049c36  movaps  xmm1, xmm6
0x180049c39  mov     rax, [rax+60h]
0x180049c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c42  test    eax, eax
0x180049c44  js      loc_18004A1DD
0x180049c4a  test    ebx, ebx
0x180049c4c  jz      short loc_180049C74
0x180049c4e  mov     rcx, [rsp+1C0h+var_150]
0x180049c53  mov     dword ptr [rbp+0C0h+var_90], esi
0x180049c56  xorps   xmm0, xmm0
0x180049c59  movdqu  [rbp+0C0h+var_90+8], xmm0
0x180049c5e  mov     rax, [rcx]
0x180049c61  mov     edx, ebx
0x180049c63  mov     rax, [rax+48h]
0x180049c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c6c  test    eax, eax
0x180049c6e  js      loc_18004A1E9
0x180049c74  mov     edx, edi
0x180049c76  and     edx, 2
0x180049c79  test    dil, 1
0x180049c7d  jz      short loc_180049C82
0x180049c7f  or      edx, 1
0x180049c82  mov     rcx, [rsp+1C0h+var_150]
0x180049c87  mov     dword ptr [rbp+0C0h+var_90], esi
0x180049c8a  xorps   xmm0, xmm0
0x180049c8d  movdqu  [rbp+0C0h+var_90+8], xmm0
0x180049c92  mov     rax, [rcx]
0x180049c95  mov     rax, [rax+38h]
0x180049c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c9e  test    eax, eax
0x180049ca0  js      loc_18004A1F5
0x180049ca6  lea     rcx, [rbp+0C0h+var_138]
0x180049caa  call    ?Size@?$consume_Windows_Indexer_SemanticSearch_ISparseBitIds@UISparseBitIds@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(void)
0x180049caf  mov     ebx, eax
0x180049cb1  test    eax, eax
0x180049cb3  jz      loc_180049D84
0x180049cb9  cmp     ebx, 7530h
0x180049cbf  ja      loc_180049D84
0x180049cc5  mov     edx, ebx
0x180049cc7  lea     rcx, [rbp+0C0h+var_90]
0x180049ccb  call    ??0?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@QEAA@_KAEBV?$allocator@Uguid@winrt@@@1@@Z; std::vector<winrt::guid>::vector<winrt::guid>(unsigned __int64,std::allocator<winrt::guid> const &)
0x180049cd0  nop
0x180049cd1  lea     rdx, [rsp+1C0h+var_148]
0x180049cd6  lea     rcx, [rsp+1C0h+var_150]
0x180049cdb  call    ?Items@?$consume_Microsoft_Windows_Management_Deployment_IPackageSet@UIPackageSet@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSet<winrt::Microsoft::Windows::Management::Deployment::IPackageSet>::Items(void)
0x180049ce0  nop
0x180049ce1  mov     rax, qword ptr [rbp+0C0h+var_90]
0x180049ce5  mov     qword ptr [rsp+1C0h+var_170], rax
0x180049cea  mov     rcx, qword ptr [rbp+0C0h+var_90+8]
0x180049cee  sub     rcx, rax
0x180049cf1  sar     rcx, 4
0x180049cf5  mov     [rsp+1C0h+var_168], ecx
0x180049cf9  mov     eax, [rbp+0C0h+var_6C]
0x180049cfc  mov     [rsp+1C0h+var_164], eax
0x180049d00  lea     rdx, [rsp+1C0h+var_170]
0x180049d05  lea     rcx, [rbp+0C0h+var_138]
0x180049d09  call    ?GetIds@?$consume_Windows_Indexer_SemanticSearch_ISparseBitIds@UISparseBitIds@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@U?$array_view@Uguid@winrt@@@3@@Z; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::GetIds(winrt::array_view<winrt::guid>)
0x180049d0e  mov     edi, eax
0x180049d10  cmp     eax, ebx
0x180049d12  jz      short loc_180049D33
0x180049d14  mov     dword ptr [rsp+1C0h+var_1A0], ebx
0x180049d18  mov     r9d, eax; wchar_t *
0x180049d1b  lea     r8, aGetidsReturned; "GetIds returned %lu items but expected "...
0x180049d22  mov     edx, 979h; wchar_t *
0x180049d27  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180049d2e  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180049d33  mov     rax, qword ptr [rbp+0C0h+var_90]
0x180049d37  mov     qword ptr [rsp+1C0h+var_170], rax
0x180049d3c  mov     rcx, qword ptr [rbp+0C0h+var_90+8]
0x180049d40  sub     rcx, rax
0x180049d43  sar     rcx, 4
0x180049d47  mov     [rsp+1C0h+var_168], ecx
0x180049d4b  mov     eax, [rbp+0C0h+var_6C]
0x180049d4e  mov     [rsp+1C0h+var_164], eax
0x180049d52  lea     rdx, [rsp+1C0h+var_170]
0x180049d57  lea     rcx, [rsp+1C0h+var_148]
0x180049d5c  call    ?ReplaceAll@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uguid@winrt@@@Collections@Foundation@Windows@winrt@@Uguid@5@@impl@winrt@@QEBA@U?$array_view@$$CBUguid@winrt@@@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::guid>,winrt::guid>::ReplaceAll(winrt::array_view<winrt::guid const>)
0x180049d61  mov     ecx, edi; unsigned int
0x180049d63  call    ?ReportSemanticSearchWorkIdsCount@SemanticSearchTelemetryAggregated@@SAXI@Z; SemanticSearchTelemetryAggregated::ReportSemanticSearchWorkIdsCount(uint)
0x180049d68  nop
0x180049d69  cmp     [rsp+1C0h+var_148], rsi
0x180049d6e  jz      short loc_180049D7B
0x180049d70  lea     rcx, [rsp+1C0h+var_148]
0x180049d75  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180049d7a  nop
0x180049d7b  lea     rcx, [rbp+0C0h+var_90]
0x180049d7f  call    ??1?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::guid>::~vector<winrt::guid>(void)
0x180049d84  mov     rbx, rsi
0x180049d87  mov     [rsp+1C0h+var_178], rbx
0x180049d8c  lea     rcx, [rbp+0C0h+var_F0]
0x180049d90  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180049d95  nop
0x180049d96  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x180049d9d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x180049da2  test    al, al
0x180049da4  jnz     short loc_180049DE2
0x180049da6  mov     rdi, [rbp+0C0h+pv]
0x180049daa  mov     qword ptr [rsp+1C0h+var_170], rdi
0x180049daf  test    rdi, rdi
0x180049db2  jz      short loc_180049DBB
0x180049db4  lock inc dword ptr [rdi+120h]
0x180049dbb  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180049dc2  call    cs:__imp_EnterCriticalSection
0x180049dc8  inc     dword ptr [rdi+0F0h]
0x180049dce  mov     dword ptr [rdi+110h], 11h
0x180049dd8  lea     rcx, [rsp+1C0h+var_170]
0x180049ddd  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180049de2  cmp     qword ptr [r14+28h], 0
0x180049de7  jz      short loc_180049E56
0x180049de9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x180049df0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x180049df5  test    al, al
0x180049df7  jz      short loc_180049E35
0x180049df9  mov     rdi, [rbp+0C0h+pv]
0x180049dfd  mov     qword ptr [rsp+1C0h+var_170], rdi
0x180049e02  test    rdi, rdi
0x180049e05  jz      short loc_180049E0E
0x180049e07  lock inc dword ptr [rdi+120h]
0x180049e0e  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180049e15  call    cs:__imp_EnterCriticalSection
0x180049e1b  inc     dword ptr [rdi+0F0h]
0x180049e21  mov     dword ptr [rdi+110h], 2Ah ; '*'
0x180049e2b  lea     rcx, [rsp+1C0h+var_170]
0x180049e30  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180049e35  mov     rax, [r12]
0x180049e39  mov     [rbp+0C0h+pExceptionObject], rax
0x180049e3d  lea     r9, [rsp+1C0h+var_150]
0x180049e42  lea     r8, [rbp+0C0h+pExceptionObject]
0x180049e46  lea     rdx, [rsp+1C0h+var_158]
0x180049e4b  lea     rcx, [r14+28h]
0x180049e4f  call    ?QueryText@?$consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndex@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUSemanticQueryOptions@SemanticSearch@Windows@Microsoft@3@@Z; winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndex<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>::QueryText(winrt::param::hstring const &,winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions const &)
0x180049e54  jmp     short loc_180049ECC
0x180049e56  cmp     qword ptr [r14+30h], 0
0x180049e5b  jz      loc_180049EF7
0x180049e61  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x180049e68  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x180049e6d  test    al, al
0x180049e6f  jz      short loc_180049EAD
0x180049e71  mov     rdi, [rbp+0C0h+pv]
0x180049e75  mov     qword ptr [rsp+1C0h+var_170], rdi
0x180049e7a  test    rdi, rdi
0x180049e7d  jz      short loc_180049E86
0x180049e7f  lock inc dword ptr [rdi+120h]
0x180049e86  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180049e8d  call    cs:__imp_EnterCriticalSection
0x180049e93  inc     dword ptr [rdi+0F0h]
0x180049e99  mov     dword ptr [rdi+110h], 2Bh ; '+'
0x180049ea3  lea     rcx, [rsp+1C0h+var_170]
0x180049ea8  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180049ead  mov     rax, [r12]
0x180049eb1  mov     [rbp+0C0h+pExceptionObject], rax
0x180049eb5  lea     r9, [rsp+1C0h+var_150]
0x180049eba  lea     r8, [rbp+0C0h+pExceptionObject]
0x180049ebe  lea     rdx, [rsp+1C0h+var_158]
0x180049ec3  lea     rcx, [r14+30h]
0x180049ec7  call    ?QueryText@?$consume_Microsoft_Windows_SemanticSearch_ISemanticImageIndex@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUSemanticQueryOptions@SemanticSearch@Windows@Microsoft@3@@Z; winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticImageIndex<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>::QueryText(winrt::param::hstring const &,winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions const &)
0x180049ecc  lea     rcx, [rsp+1C0h+var_178]
0x180049ed1  cmp     rcx, rax
0x180049ed4  jz      short loc_180049EE5
0x180049ed6  mov     rbx, [rax]
0x180049ed9  mov     qword ptr [rax], 0
0x180049ee0  mov     [rsp+1C0h+var_178], rbx
0x180049ee5  cmp     [rsp+1C0h+var_158], 0
0x180049eeb  jz      short loc_180049EF7
0x180049eed  lea     rcx, [rsp+1C0h+var_158]
0x180049ef2  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180049ef7  lea     rcx, [rsp+1C0h+var_178]
0x180049efc  call    ?VerifyIsOK@?$consume_Windows_ApplicationModel_IPackageStatus@UIPackageStatus@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(void)
0x180049f01  test    al, al
0x180049f03  jz      loc_18004A201
0x180049f09  mov     rdi, [rbp+0C0h+pv]
0x180049f0d  lea     rsi, [rdi+0C8h]
0x180049f14  mov     rcx, rsi; lpCriticalSection
0x180049f17  call    cs:__imp_EnterCriticalSection
0x180049f1d  or      dword ptr [rdi+48h], 300h
0x180049f24  cmp     qword ptr [rdi+0F8h], 0
0x180049f2c  jz      short loc_180049F3C
0x180049f2e  mov     edx, 2
0x180049f33  lea     rcx, [rdi+8]
0x180049f37  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180049f3c  xor     edi, edi
0x180049f3e  test    rsi, rsi
0x180049f41  jz      short loc_180049F4C
0x180049f43  mov     rcx, rsi; lpCriticalSection
0x180049f46  call    cs:__imp_LeaveCriticalSection
0x180049f4c  xorps   xmm0, xmm0
0x180049f4f  movdqu  [rbp+0C0h+var_90], xmm0
0x180049f54  mov     [rbp+0C0h+var_80], rdi
0x180049f58  lea     rdx, [rbp+0C0h+var_90]
0x180049f5c  mov     rcx, r13
0x180049f5f  call    ??$single_threaded_vector@USemanticQueryResult@SemanticSearch@Indexer@Windows@winrt@@V?$allocator@USemanticQueryResult@SemanticSearch@Indexer@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@USemanticQueryResult@SemanticSearch@Indexer@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@USemanticQueryResult@SemanticSearch@Indexer@Windows@winrt@@V?$allocator@USemanticQueryResult@SemanticSearch@Indexer@Windows@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::Windows::Indexer::SemanticSearch::SemanticQueryResult,std::allocator<winrt::Windows::Indexer::SemanticSearch::SemanticQueryResult>>(std::vector<winrt::Windows::Indexer::SemanticSearch::SemanticQueryResult> &&)
0x180049f64  mov     r14d, 1
0x180049f6a  mov     dword ptr [rsp+1C0h+var_160], r14d
0x180049f6f  lea     rcx, [rbp+0C0h+var_90]
0x180049f73  call    ?_Tidy@?$vector@UPackageExtension@PackageExtensions@ApplicationModel@Windows@winrt@@V?$allocator@UPackageExtension@PackageExtensions@ApplicationModel@Windows@winrt@@@std@@@std@@AEAAXXZ; std::vector<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtension>::_Tidy(void)
0x180049f78  lea     rdx, [rsp+1C0h+var_148]
0x180049f7d  lea     rcx, [rsp+1C0h+var_178]
0x180049f82  call    ?ErrorText@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(void)
0x180049f87  nop
0x180049f88  mov     r15d, edi
0x180049f8b  lea     rdx, [rbp+0C0h+var_78]
0x180049f8f  lea     rcx, [rsp+1C0h+var_148]
0x180049f94  call    ?end@?$consume_Windows_Foundation_Collections_IIterable@U?$IVectorView@UItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@winrt@@UItemQueryMatch@SemanticSearch@4Microsoft@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>,winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>::end(void)
0x180049f99  or      esi, 0FFFFFFFFh
0x180049f9c  cmp     r15d, [rbp+0C0h+var_70]
0x180049fa0  jz      loc_18004A0F8
0x180049fa6  mov     [rbp+0C0h+var_140], rdi
0x180049faa  or      r14d, 4
0x180049fae  mov     dword ptr [rsp+1C0h+var_160], r14d
0x180049fb3  mov     rcx, [rsp+1C0h+var_148]
0x180049fb8  mov     dword ptr [rbp+0C0h+pExceptionObject], edi
0x180049fbb  xorps   xmm0, xmm0
0x180049fbe  movdqu  [rbp+0C0h+var_118], xmm0
0x180049fc3  mov     rax, [rcx]
0x180049fc6  lea     r8, [rbp+0C0h+var_140]
0x180049fca  mov     edx, r15d
0x180049fcd  mov     rax, [rax+30h]
0x180049fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049fd6  test    eax, eax
0x180049fd8  js      loc_18004A1D1
0x180049fde  and     r14d, 0FFFFFFFBh
0x180049fe2  or      r14d, 2
0x180049fe6  mov     dword ptr [rsp+1C0h+var_160], r14d
0x180049feb  lea     rcx, [rbp+0C0h+var_140]
0x180049fef  call    ?ConfidenceScore@?$consume_Microsoft_Windows_SemanticSearch_IItemQueryMatch@UIItemQueryMatch@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_SemanticSearch_IItemQueryMatch<winrt::Microsoft::Windows::SemanticSearch::IItemQueryMatch>::ConfidenceScore(void)
0x180049ff4  movss   dword ptr [rsp+1C0h+var_180], xmm0
0x180049ffa  lea     rdx, [rsp+1C0h+var_170]
0x180049fff  lea     rcx, [rbp+0C0h+var_140]
0x18004a003  call    ?TextIndexBasePath@?$consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions@UISemanticIndexStoreOptions@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(void)
0x18004a008  nop
0x18004a009  lea     rdx, [rbp+0C0h+lpMem]
0x18004a00d  mov     rcx, rax
0x18004a010  call    ?TextIndexBasePath@?$consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions@UISemanticIndexStoreOptions@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(void)
0x18004a015  mov     rdi, rax
0x18004a018  lea     rdx, [rbp+0C0h+var_130]
0x18004a01c  lea     rcx, [rbp+0C0h+var_140]
0x18004a020  call    ?TextIndexBasePath@?$consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions@UISemanticIndexStoreOptions@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(void)
0x18004a025  nop
0x18004a026  lea     rdx, [rbp+0C0h+var_90]
0x18004a02a  mov     rcx, rax
0x18004a02d  call    ?ItemId@?$consume_Microsoft_Windows_SemanticSearch_IItemRegion@UIItemRegion@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_SemanticSearch_IItemRegion<winrt::Microsoft::Windows::SemanticSearch::IItemRegion>::ItemId(void)
0x18004a032  lea     r9, [rsp+1C0h+var_180]
0x18004a037  mov     r8, rdi
0x18004a03a  mov     rdx, rax
0x18004a03d  lea     rcx, [rsp+1C0h+var_158]
0x18004a042  call    ??$make@USemanticQueryResult@implementation@SemanticSearch@Indexer@Windows@winrt@@Uguid@6@Uhstring@6@M@winrt@@YA?A_P$$QEAUguid@0@$$QEAUhstring@0@$$QEAM@Z
0x18004a047  nop
0x18004a048  cmp     [rbp+0C0h+var_130], 0
0x18004a04d  jz      short loc_18004A059
  ... truncated ...
```
