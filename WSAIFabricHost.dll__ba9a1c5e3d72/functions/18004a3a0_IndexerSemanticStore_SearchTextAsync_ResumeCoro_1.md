# IndexerSemanticStore::SearchTextAsync$_ResumeCoro$1

- ea: `0x18004a3a0`
- end: `0x18004b230`
- name: `IndexerSemanticStore::SearchTextAsync$_ResumeCoro$1`
- size: `3728`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `56`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004a380`
- `0x18004b240`

## callees

- `0x180004ca0`
- `0x180005140`
- `0x1800058cb`
- `0x18000591f`
- `0x18000592b`
- `0x180005937`
- `0x180007ad0`
- `0x180007f72`
- `0x180009574`
- `0x18000c478`
- `0x180013930`
- `0x1800142ac`
- `0x180014688`
- `0x180015f90`
- `0x180018fa0`
- `0x180019c3c`
- `0x18001a464`
- `0x18001de54`
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
- `0x1800483d8`
- `0x1800484a0`
- `0x1800486c0`
- `0x180048f24`
- `0x180049574`
- `0x18004a3a0`
- `0x18004b9bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004af5b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b1c1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004af5b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b1c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ada6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ada6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a71b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a796`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a9c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ad7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a71b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a796`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004a9c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ad7b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18004b182`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18004b182`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b0b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b0b1`

## string_xrefs

- `0x18004a43d`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18004a636`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18004ac30`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18004ac5f`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=30 #try_helpers=1
void __fastcall IndexerSemanticStore::SearchTextAsync__ResumeCoro_1(
        char *a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4)
{
  __int64 *v5; // r13
  double v6; // xmm0_8
  unsigned int matched; // r14d
  char v8; // r15
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // esi
  __int64 *v18; // r14
  __int64 v19; // r8
  __int64 v20; // rax
  unsigned int Ids; // eax
  unsigned int v22; // r12d
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 *v25; // r14
  __int64 v26; // rsi
  __int64 v27; // rax
  __int64 v28; // r12
  __int64 v29; // rsi
  char *v30; // r13
  __int64 *v31; // r15
  __int64 v32; // rcx
  __int64 v33; // rax
  _DWORD *v34; // rsi
  __int64 v35; // rcx
  _QWORD *v36; // r15
  _QWORD *v37; // r12
  __int64 *v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // r12
  __int64 v42; // rsi
  __int64 *v43; // r15
  __int64 v44; // rcx
  __int64 v45; // rax
  _DWORD *v46; // rsi
  __int64 v47; // rcx
  _QWORD *v48; // r15
  _QWORD *v49; // r12
  __int64 *v50; // rax
  __int64 v51; // rcx
  unsigned int *v52; // rsi
  int v53; // r15d
  __int64 v54; // rax
  unsigned int v55; // eax
  __int64 v56; // rax
  int v57; // r13d
  int v58; // r12d
  int v59; // r15d
  double v60; // xmm0_8
  unsigned int v61; // eax
  __int64 v62; // rbx
  __int64 *v63; // r12
  unsigned int v64; // r13d
  int v65; // r14d
  __int64 v66; // rcx
  int v67; // eax
  __int64 v68; // rax
  char *v69; // r12
  __int64 v70; // rax
  __int64 v71; // rax
  _QWORD *v72; // r14
  void *v73; // r14
  int v74; // eax
  HANDLE ProcessHeap; // rax
  __int64 v76; // rcx
  int v77; // eax
  _QWORD *v78; // r15
  __int64 *v79; // r14
  __int64 v80; // rax
  struct _RTL_CRITICAL_SECTION *v81; // r14
  volatile signed __int32 *v82; // r14
  int v83; // esi
  HANDLE v84; // rax
  __int64 v85; // [rsp+20h] [rbp-2B8h]
  int v86; // [rsp+48h] [rbp-290h]
  unsigned int v87; // [rsp+50h] [rbp-288h]
  __int64 v88; // [rsp+50h] [rbp-288h]
  __int64 v89; // [rsp+148h] [rbp-190h]
  _BYTE pExceptionObject[64]; // [rsp+150h] [rbp-188h] BYREF
  int v91; // [rsp+190h] [rbp-148h]

  if ( (unsigned __int16)(*((_WORD *)a1 + 80) + 1) > 4u )
  {
LABEL_140:
    __debugbreak();
  }
  else
  {
    switch ( *((_WORD *)a1 + 80) )
    {
      case 0xFFFF:
      case 1:
      case 3:
        goto LABEL_126;
      case 0:
        goto LABEL_140;
      case 2:
        *((_DWORD *)a1 + 214) = 0;
        a1[64] = 1;
        SearchIndexerTrace::Information(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
          (const wchar_t *)0x9D3,
          (unsigned int)L"SearchTextAsync : Started",
          a4);
        v5 = (__int64 *)(a1 + 168);
        winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions::SemanticQueryOptions((winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions *)(a1 + 168));
        v6 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::Threshold(*((_QWORD *)a1 + 19));
        matched = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(*((_QWORD *)a1 + 19));
        v8 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::ImageIndexCreationDisposition(*((_QWORD *)a1 + 19));
        winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(
          *((_QWORD *)a1 + 19),
          a1 + 176);
        if ( *(float *)&v6 != -1.0 )
        {
          v9 = *v5;
          *((_DWORD *)a1 + 188) = 0;
          *((_QWORD *)a1 + 95) = 0;
          *((_QWORD *)a1 + 96) = 0;
          v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 96LL))(v9);
          if ( v10 < 0 )
            winrt::throw_hresult((unsigned int)v10, a1 + 752);
        }
        if ( matched )
        {
          v11 = *v5;
          *((_DWORD *)a1 + 198) = 0;
          *((_QWORD *)a1 + 100) = 0;
          *((_QWORD *)a1 + 101) = 0;
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v11 + 72LL))(v11, matched);
          if ( v12 < 0 )
            winrt::throw_hresult((unsigned int)v12, a1 + 792);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57174852>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57174852>::GetImpl'::`2'::impl) )
        {
          v13 = v8 & 2 | 1u;
          if ( (v8 & 1) == 0 )
            v13 = v8 & 2;
          v14 = *v5;
          *((_DWORD *)a1 + 204) = 0;
          *((_QWORD *)a1 + 103) = 0;
          *((_QWORD *)a1 + 104) = 0;
          v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 56LL))(v14, v13);
          if ( v15 < 0 )
            winrt::throw_hresult((unsigned int)v15, a1 + 816);
          v16 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(a1 + 176);
          v17 = v16;
          if ( v16 && v16 <= 0x7530 )
          {
            v18 = (__int64 *)(a1 + 184);
            std::vector<winrt::guid>::vector<winrt::guid>(a1 + 184, v16);
            winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSet<winrt::Microsoft::Windows::Management::Deployment::IPackageSet>::Items(
              a1 + 168,
              a1 + 208);
            v19 = *((_QWORD *)a1 + 24);
            v20 = *((_QWORD *)a1 + 23);
            *((_QWORD *)a1 + 90) = v20;
            *((_DWORD *)a1 + 182) = (v19 - v20) >> 4;
            *((_DWORD *)a1 + 183) = *((_DWORD *)a1 + 57);
            Ids = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::GetIds(a1 + 176);
            v22 = Ids;
            if ( Ids != v17 )
              SearchIndexerTrace::Error(
                (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
                (const wchar_t *)0xA02,
                (unsigned int)L"GetIds returned %lu items but expected %lu",
                (const wchar_t *)Ids,
                v17);
            v23 = *((_QWORD *)a1 + 24);
            v24 = *v18;
            *((_QWORD *)a1 + 92) = *v18;
            *((_DWORD *)a1 + 186) = (v23 - v24) >> 4;
            *((_DWORD *)a1 + 187) = *((_DWORD *)a1 + 61);
            winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::guid>,winrt::guid>::ReplaceAll(a1 + 208);
            SemanticSearchTelemetryAggregated::ReportSemanticSearchWorkIdsCount(v22);
            if ( *((_QWORD *)a1 + 26) )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 208);
            std::vector<winrt::guid>::~vector<winrt::guid>(a1 + 184);
          }
        }
        v25 = (__int64 *)(a1 + 248);
        *((_QWORD *)a1 + 31) = 0;
        tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)(a1 + 256));
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
        {
          v26 = *((_QWORD *)a1 + 39);
          *((_QWORD *)a1 + 40) = v26;
          if ( v26 )
            _InterlockedIncrement((volatile signed __int32 *)(v26 + 288));
          EnterCriticalSection((LPCRITICAL_SECTION)(v26 + 200));
          ++*(_DWORD *)(v26 + 240);
          *(_DWORD *)(*((_QWORD *)a1 + 40) + 272LL) = 45;
          tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>((struct _RTL_CRITICAL_SECTION **)a1 + 40);
        }
        v27 = *((_QWORD *)a1 + 17);
        v28 = v27 + 40;
        if ( *(_QWORD *)(v27 + 40) )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
          {
            v29 = *((_QWORD *)a1 + 39);
            *((_QWORD *)a1 + 41) = v29;
            if ( v29 )
              _InterlockedIncrement((volatile signed __int32 *)(v29 + 288));
            EnterCriticalSection((LPCRITICAL_SECTION)(v29 + 200));
            ++*(_DWORD *)(v29 + 240);
            *(_DWORD *)(*((_QWORD *)a1 + 41) + 272LL) = 46;
            tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>((struct _RTL_CRITICAL_SECTION **)a1 + 41);
          }
          *((_QWORD *)a1 + 42) = *((_QWORD *)a1 + 18);
          v30 = a1 + 368;
          winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndex4<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>::QueryTextAsync(
            v28,
            a1 + 368,
            a1 + 336,
            a1 + 168);
          v31 = (__int64 *)(a1 + 384);
          v32 = *((_QWORD *)a1 + 46);
          *((_QWORD *)a1 + 48) = v32;
          if ( v32 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
          *((_QWORD *)a1 + 97) = v31;
          v33 = *v31;
          *v31 = 0;
          *((_QWORD *)a1 + 105) = v33;
          *((_QWORD *)a1 + 106) = a1 + 840;
          v34 = operator new(0x18u);
          v34[2] = 1;
          v35 = *((_QWORD *)a1 + 105);
          *((_QWORD *)a1 + 105) = 0;
          *((_QWORD *)v34 + 2) = v35;
          winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v34 + 6));
          *(_QWORD *)v34 = off_18008AE50;
          *((_QWORD *)a1 + 47) = v34;
          *((_DWORD *)a1 + 214) = 1;
          if ( *((_QWORD *)a1 + 105) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 840);
          if ( *v31 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 384);
          WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)a1 + 11);
          if ( *((_DWORD *)a1 + 28) == 2 )
          {
            ReleaseSRWLockExclusive_0((PSRWLOCK)a1 + 11);
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v34 + 24LL))(v34);
            v37 = a1 + 376;
          }
          else
          {
            v36 = a1 + 104;
            v37 = a1 + 376;
            if ( a1 + 104 != a1 + 376 )
            {
              if ( *v36 )
                winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 104);
              *v37 = 0;
              *v36 = v34;
              v34 = 0;
            }
            ReleaseSRWLockExclusive_0((PSRWLOCK)a1 + 11);
          }
          if ( v34 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v37);
          v38 = (__int64 *)winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::QueryResult>::get(
                             a1 + 368,
                             a1 + 392);
          if ( v25 != v38 )
          {
            v39 = *v38;
            *v38 = 0;
            *v25 = v39;
          }
          if ( *((_QWORD *)a1 + 49) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 392);
          v40 = *(_QWORD *)v30;
        }
        else
        {
          v41 = v27 + 48;
          if ( !*(_QWORD *)(v27 + 48) )
            goto LABEL_83;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
          {
            v42 = *((_QWORD *)a1 + 39);
            *((_QWORD *)a1 + 50) = v42;
            if ( v42 )
              _InterlockedIncrement((volatile signed __int32 *)(v42 + 288));
            EnterCriticalSection((LPCRITICAL_SECTION)(v42 + 200));
            ++*(_DWORD *)(v42 + 240);
            *(_DWORD *)(*((_QWORD *)a1 + 50) + 272LL) = 47;
            tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>((struct _RTL_CRITICAL_SECTION **)a1 + 50);
          }
          *((_QWORD *)a1 + 51) = *((_QWORD *)a1 + 18);
          v30 = a1 + 440;
          winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticImageIndex4<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>::QueryTextAsync(
            v41,
            a1 + 440,
            a1 + 408,
            a1 + 168);
          v43 = (__int64 *)(a1 + 456);
          v44 = *((_QWORD *)a1 + 55);
          *((_QWORD *)a1 + 57) = v44;
          if ( v44 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
          *((_QWORD *)a1 + 98) = v43;
          v45 = *v43;
          *v43 = 0;
          *((_QWORD *)a1 + 108) = v45;
          *((_QWORD *)a1 + 109) = a1 + 864;
          v46 = operator new(0x18u);
          v46[2] = 1;
          v47 = *((_QWORD *)a1 + 108);
          *((_QWORD *)a1 + 108) = 0;
          *((_QWORD *)v46 + 2) = v47;
          winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v46 + 6));
          *(_QWORD *)v46 = off_18008AE50;
          *((_QWORD *)a1 + 56) = v46;
          *((_DWORD *)a1 + 214) = 2;
          if ( *((_QWORD *)a1 + 108) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 864);
          if ( *v43 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 456);
          WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)a1 + 11);
          if ( *((_DWORD *)a1 + 28) == 2 )
          {
            ReleaseSRWLockExclusive_0((PSRWLOCK)a1 + 11);
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v46 + 24LL))(v46);
            v49 = a1 + 448;
          }
          else
          {
            v48 = a1 + 104;
            v49 = a1 + 448;
            if ( a1 + 104 != a1 + 448 )
            {
              if ( *v48 )
                winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 104);
              *v49 = 0;
              *v48 = v46;
              v46 = 0;
            }
            ReleaseSRWLockExclusive_0((PSRWLOCK)a1 + 11);
          }
          if ( v46 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v49);
          v50 = (__int64 *)winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::QueryResult>,winrt::Microsoft::Windows::SemanticSearch::QueryResult>::get(
                             a1 + 440,
                             a1 + 464);
          if ( v25 != v50 )
          {
            v51 = *v50;
            *v50 = 0;
            *v25 = v51;
          }
          if ( *((_QWORD *)a1 + 58) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 464);
          v40 = *(_QWORD *)v30;
        }
        if ( v40 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v30);
        if ( *v25
          && !(unsigned __int8)winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(a1 + 248) )
        {
          v52 = (unsigned int *)(a1 + 472);
          winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(
            a1 + 248,
            a1 + 472);
          v53 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(a1 + 248);
          v54 = tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(
                  a1 + 256,
                  a1 + 480);
          *(_DWORD *)(std::unique_ptr<wil::srwlock>::operator->(v54) + 280) = v53;
          tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>((struct _RTL_CRITICAL_SECTION **)a1 + 60);
          if ( (unsigned int)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(a1 + 248) == 110 )
          {
            SearchIndexerTrace::Error(
              (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
              (const wchar_t *)0xA41,
              (unsigned int)L"SearchTextAsync : Query failed because models are not loaded hr(0x%08x)",
              (const wchar_t *)*v52);
          }
          else
          {
            v86 = *v52;
            v55 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(a1 + 248);
            LODWORD(v85) = v86;
            SearchIndexerTrace::Error(
              (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
              (const wchar_t *)0xA48,
              (unsigned int)L"SearchTextAsync : Query failed with status %lu and hr(0x%08x)",
              (const wchar_t *)v55,
              v85);
          }
          v56 = winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(
                  *((_QWORD *)a1 + 19),
                  a1 + 488);
          v57 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(v56);
          v58 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::ImageIndexCreationDisposition(*((_QWORD *)a1 + 19));
          v59 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(*((_QWORD *)a1 + 19));
          v60 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::Threshold(*((_QWORD *)a1 + 19));
          v87 = winrt::hresult::operator int(a1 + 472);
          v61 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(a1 + 248);
          wil::str_printf<std::wstring>(
            (__int64)(a1 + 496),
            L"SearchTextAsync : Query failed with status %u and hr(0x%08X) [threshold=%.3f, maxMatchCount=%u, queryFlags=%"
             "u, itemIdQuerySetSize=%u]",
            v61,
            v87,
            *(float *)&v60,
            v59,
            v58,
            v57);
          winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::Private::Workloads::SessionManager::SessionManager>::~IAsyncOperation<winrt::Microsoft::Windows::Private::Workloads::SessionManager::SessionManager>((_QWORD *)a1 + 61);
          v62 = winrt::impl::slim_source_location::current(a1 + 528);
          winrt::param::hstring::hstring(a1 + 552, a1 + 496);
          winrt::hresult_error::hresult_error(pExceptionObject, *v52, a1 + 552, v62);
          throw (winrt::hresult_error *)pExceptionObject;
        }
LABEL_83:
        v89 = *((_QWORD *)a1 + 39);
        EnterCriticalSection((LPCRITICAL_SECTION)(v89 + 200));
        *(_DWORD *)(v89 + 72) |= 0x300u;
        if ( *(_QWORD *)(v89 + 248) )
          tip2::details::shared_data<0,0,0>::complete_helper(v89 + 8, 2);
        if ( v89 != -200 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v89 + 200));
        *((_QWORD *)a1 + 73) = 0;
        *((_QWORD *)a1 + 74) = 0;
        *((_QWORD *)a1 + 75) = 0;
        winrt::single_threaded_vector<winrt::Windows::Indexer::SemanticSearch::SemanticQueryResult,std::allocator<winrt::Windows::Indexer::SemanticSearch::SemanticQueryResult>>(
          (_QWORD *)a1 + 76,
          (__int64 *)a1 + 73);
        std::vector<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtension>::_Tidy(a1 + 584);
        v63 = (__int64 *)(a1 + 616);
        winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(
          a1 + 248,
          a1 + 616);
        v64 = 0;
        winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>,winrt::Microsoft::Windows::SemanticSearch::ItemQueryMatch>::end(
          a1 + 616,
          a1 + 624);
        while ( 1 )
        {
          v91 = *((_DWORD *)a1 + 158);
          if ( v64 == v91 )
            break;
          *((_QWORD *)a1 + 80) = 0;
          v65 = *((_DWORD *)a1 + 214) | 8;
          *((_DWORD *)a1 + 214) = v65;
          v66 = *v63;
          *((_DWORD *)a1 + 220) = 0;
          *((_QWORD *)a1 + 111) = 0;
          *((_QWORD *)a1 + 112) = 0;
          v67 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v66 + 48LL))(v66, v64, a1 + 640);
          if ( v67 < 0 )
            winrt::throw_hresult((unsigned int)v67, a1 + 880);
          *((_DWORD *)a1 + 214) = v65 & 0xFFFFFFF3 | 4;
          *((float *)a1 + 162) = winrt::impl::consume_Microsoft_Windows_SemanticSearch_IItemQueryMatch<winrt::Microsoft::Windows::SemanticSearch::IItemQueryMatch>::ConfidenceScore(a1 + 640);
          v68 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(
                  a1 + 640,
                  a1 + 656);
          v69 = a1 + 664;
          v88 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(
                  v68,
                  a1 + 664);
          v70 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::TextIndexBasePath(
                  a1 + 640,
                  a1 + 672);
          v71 = winrt::impl::consume_Microsoft_Windows_SemanticSearch_IItemRegion<winrt::Microsoft::Windows::SemanticSearch::IItemRegion>::ItemId(
                  v70,
                  a1 + 680);
          v72 = a1 + 696;
          winrt::make<winrt::Windows::Indexer::SemanticSearch::implementation::SemanticQueryResult,winrt::guid,winrt::hstring,float>(
            a1 + 696,
            v71,
            v88,
            a1 + 648);
          if ( *((_QWORD *)a1 + 84) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 672);
          if ( *(_QWORD *)v69 )
          {
            v73 = *(void **)v69;
            v74 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v69 + 24LL));
            if ( v74 )
            {
              if ( v74 < 0 )
                abort();
            }
            else
            {
              ProcessHeap = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(ProcessHeap, 0, v73);
            }
            *(_QWORD *)v69 = 0;
            v72 = a1 + 696;
          }
          if ( *((_QWORD *)a1 + 82) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 656);
          v76 = *((_QWORD *)a1 + 76);
          *((_DWORD *)a1 + 226) = 0;
          *((_QWORD *)a1 + 114) = 0;
          *((_QWORD *)a1 + 115) = 0;
          v77 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v76 + 104LL))(v76);
          if ( v77 < 0 )
            winrt::throw_hresult((unsigned int)v77, a1 + 904);
          if ( *v72 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v72);
          if ( *((_QWORD *)a1 + 80) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 640);
          ++v64;
          v63 = (__int64 *)(a1 + 616);
        }
        if ( *((_QWORD *)a1 + 77) )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 616);
        v78 = a1 + 120;
        v79 = (__int64 *)(a1 + 608);
        if ( a1 + 120 != a1 + 608 )
        {
          if ( *v78 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 120);
          v80 = *v79;
          *v79 = 0;
          *v78 = v80;
        }
        if ( *v79 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 608);
        if ( *((_QWORD *)a1 + 39) )
        {
          v81 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 39);
          if ( _InterlockedExchangeAdd(&v81[7].LockCount, 0xFFFFFFFF) == 1 )
          {
            tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v81);
            CoTaskMemFree(v81);
          }
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 264));
        if ( *((_QWORD *)a1 + 31) )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 248);
        if ( *((_QWORD *)a1 + 22) )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 176);
        if ( *((_QWORD *)a1 + 21) )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 168);
        *((_QWORD *)a1 + 88) = a1 + 16;
        *((_WORD *)a1 + 80) = 0;
        *(_QWORD *)a1 = 0;
        if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,enum winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
        {
LABEL_126:
          if ( *((_QWORD *)a1 + 15) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 120);
          if ( *((_QWORD *)a1 + 13) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 104);
          if ( *((_QWORD *)a1 + 12) )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 96);
          __ExceptionPtrDestroy(a1 + 72);
          winrt::impl::root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>::~root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>(a1 + 16);
          v82 = (volatile signed __int32 *)*((_QWORD *)a1 + 18);
          if ( v82 )
          {
            v83 = _InterlockedDecrement(v82 + 6);
            if ( v83 )
            {
              if ( v83 < 0 )
                abort();
            }
            else
            {
              v84 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v84, 0, (LPVOID)v82);
            }
            *((_QWORD *)a1 + 18) = 0;
          }
          if ( *((_WORD *)a1 + 81) )
            operator delete(a1, 0x3A0u);
        }
        break;
    }
  }
}

```

## disassembly

```asm
0x18004a3a0  mov     r11, rsp
0x18004a3a3  mov     [r11+10h], rbx
0x18004a3a7  mov     [r11+18h], rsi
0x18004a3ab  mov     [r11+8], rcx
0x18004a3af  push    rdi
0x18004a3b0  push    r12
0x18004a3b2  push    r13
0x18004a3b4  push    r14
0x18004a3b6  push    r15
0x18004a3b8  sub     rsp, 2B0h
0x18004a3bf  movaps  xmmword ptr [r11-38h], xmm6
0x18004a3c4  mov     rax, cs:__security_cookie
0x18004a3cb  xor     rax, rsp
0x18004a3ce  mov     [rsp+2D8h+var_48], rax
0x18004a3d6  mov     rdi, rcx
0x18004a3d9  mov     [rsp+2D8h+var_238], rcx
0x18004a3e1  movzx   eax, word ptr [rdi+0A0h]
0x18004a3e8  mov     [rsp+2D8h+var_270], ax
0x18004a3ed  mov     r8d, 1
0x18004a3f3  add     ax, r8w
0x18004a3f7  lea     ecx, [r8+3]
0x18004a3fb  cmp     ax, cx
0x18004a3fe  ja      loc_18004B1E7; jumptable 000000018004A419 case 1
0x18004a404  movsx   rax, ax
0x18004a408  lea     rdx, __ImageBase
0x18004a40f  mov     ecx, ds:(jpt_18004A419 - 180000000h)[rdx+rax*4]; switch 5 cases
0x18004a416  add     rcx, rdx
0x18004a419  jmp     rcx; switch jump
0x18004a41b  xor     ebx, ebx; jumptable 000000018004A419 case 4
0x18004a41d  or      esi, 0FFFFFFFFh
0x18004a420  jmp     loc_18004B154
0x18004a425  xor     ebx, ebx; jumptable 000000018004A419 case 3
0x18004a427  mov     [rdi+358h], ebx
0x18004a42d  mov     [rdi+40h], r8b
0x18004a431  lea     r8, aSearchtextasyn_2; "SearchTextAsync : Started"
0x18004a438  mov     edx, 9D3h; wchar_t *
0x18004a43d  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x18004a444  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18004a449  lea     r13, [rdi+0A8h]
0x18004a450  mov     rcx, r13; this
0x18004a453  call    ??0SemanticQueryOptions@SemanticSearch@Windows@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions::SemanticQueryOptions(void)
0x18004a458  nop
0x18004a459  mov     rcx, [rdi+98h]
0x18004a460  call    ?Threshold@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::Threshold(void)
0x18004a465  movaps  xmm6, xmm0
0x18004a468  mov     rcx, [rdi+98h]
0x18004a46f  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x18004a474  mov     r14d, eax
0x18004a477  mov     rcx, [rdi+98h]
0x18004a47e  call    ?ImageIndexCreationDisposition@?$consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions@UISemanticIndexStoreOptions@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticIndexStoreOptions<winrt::Windows::Indexer::SemanticSearch::ISemanticIndexStoreOptions>::ImageIndexCreationDisposition(void)
0x18004a483  mov     r15d, eax
0x18004a486  lea     r12, [rdi+0B0h]
0x18004a48d  mov     rdx, r12
0x18004a490  mov     rcx, [rdi+98h]
0x18004a497  call    ?ErrorText@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(void)
0x18004a49c  nop
0x18004a49d  ucomiss xmm6, cs:__real@bf800000
0x18004a4a4  jp      short loc_18004A4A8
0x18004a4a6  jz      short loc_18004A4E5
0x18004a4a8  mov     rcx, [r13+0]
0x18004a4ac  mov     [rsp+2D8h+var_268], rcx
0x18004a4b1  lea     rsi, [rdi+2F0h]
0x18004a4b8  mov     [rsi], ebx
0x18004a4ba  mov     [rdi+2F8h], rbx
0x18004a4c1  mov     [rdi+300h], rbx
0x18004a4c8  mov     rax, [rcx]
0x18004a4cb  movaps  xmm1, xmm6
0x18004a4ce  mov     rax, [rax+60h]
0x18004a4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4d7  test    eax, eax
0x18004a4d9  jns     short loc_18004A4E5
0x18004a4db  mov     rdx, rsi
0x18004a4de  mov     ecx, eax
0x18004a4e0  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18004a4e5  test    r14d, r14d
0x18004a4e8  jz      short loc_18004A527
0x18004a4ea  mov     rcx, [r13+0]
0x18004a4ee  mov     [rsp+2D8h+var_268], rcx
0x18004a4f3  lea     rsi, [rdi+318h]
0x18004a4fa  mov     [rsi], ebx
0x18004a4fc  mov     [rdi+320h], rbx
0x18004a503  mov     [rdi+328h], rbx
0x18004a50a  mov     rax, [rcx]
0x18004a50d  mov     edx, r14d
0x18004a510  mov     rax, [rax+48h]
0x18004a514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a519  test    eax, eax
0x18004a51b  jns     short loc_18004A527
0x18004a51d  mov     rdx, rsi
0x18004a520  mov     ecx, eax
0x18004a522  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18004a527  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57174852@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57174852@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57174852> `wil::Feature<__WilFeatureTraits_Feature_57174852>::GetImpl(void)'::`2'::impl
0x18004a52e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57174852@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57174852>::__private_IsEnabled(void)
0x18004a533  test    al, al
0x18004a535  jz      loc_18004A6BD
0x18004a53b  mov     eax, r15d
0x18004a53e  and     eax, 2
0x18004a541  mov     edx, eax
0x18004a543  or      edx, 1
0x18004a546  bt      r15d, 0
0x18004a54b  cmovnb  edx, eax
0x18004a54e  mov     rcx, [r13+0]
0x18004a552  mov     [rsp+2D8h+var_268], rcx
0x18004a557  lea     rsi, [rdi+330h]
0x18004a55e  mov     [rsi], ebx
0x18004a560  mov     [rdi+338h], rbx
0x18004a567  mov     [rdi+340h], rbx
0x18004a56e  mov     rax, [rcx]
0x18004a571  mov     rax, [rax+38h]
0x18004a575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a57a  test    eax, eax
0x18004a57c  jns     short loc_18004A588
0x18004a57e  mov     rdx, rsi
0x18004a581  mov     ecx, eax
0x18004a583  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18004a588  mov     rcx, r12
0x18004a58b  call    ?Size@?$consume_Windows_Indexer_SemanticSearch_ISparseBitIds@UISparseBitIds@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(void)
0x18004a590  mov     esi, eax
0x18004a592  test    eax, eax
0x18004a594  jz      loc_18004A6BD
0x18004a59a  cmp     esi, 7530h
0x18004a5a0  ja      loc_18004A6BD
0x18004a5a6  lea     r14, [rdi+0B8h]
0x18004a5ad  mov     edx, esi
0x18004a5af  mov     rcx, r14
0x18004a5b2  call    ??0?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@QEAA@_KAEBV?$allocator@Uguid@winrt@@@1@@Z; std::vector<winrt::guid>::vector<winrt::guid>(unsigned __int64,std::allocator<winrt::guid> const &)
0x18004a5b7  nop
0x18004a5b8  lea     r15, [rdi+0D0h]
0x18004a5bf  mov     rdx, r15
0x18004a5c2  mov     rcx, r13
0x18004a5c5  call    ?Items@?$consume_Microsoft_Windows_Management_Deployment_IPackageSet@UIPackageSet@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSet<winrt::Microsoft::Windows::Management::Deployment::IPackageSet>::Items(void)
0x18004a5ca  nop
0x18004a5cb  mov     rcx, [r14]
0x18004a5ce  mov     [rsp+2D8h+var_218], rcx
0x18004a5d6  mov     r8, [rdi+0C0h]
0x18004a5dd  mov     [rsp+2D8h+var_210], r8
0x18004a5e5  mov     rax, [r14]
0x18004a5e8  mov     [rsp+2D8h+var_218], rax
0x18004a5f0  lea     rdx, [rdi+2D0h]
0x18004a5f7  mov     [rdx], rcx
0x18004a5fa  sub     r8, rax
0x18004a5fd  sar     r8, 4
0x18004a601  mov     [rdi+2D8h], r8d
0x18004a608  mov     eax, [rdi+0E4h]
0x18004a60e  mov     [rdi+2DCh], eax
0x18004a614  mov     rcx, r12
0x18004a617  call    ?GetIds@?$consume_Windows_Indexer_SemanticSearch_ISparseBitIds@UISparseBitIds@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@U?$array_view@Uguid@winrt@@@3@@Z; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::GetIds(winrt::array_view<winrt::guid>)
0x18004a61c  mov     r12d, eax
0x18004a61f  cmp     eax, esi
0x18004a621  jz      short loc_18004A642
0x18004a623  mov     dword ptr [rsp+2D8h+var_2B8], esi
0x18004a627  mov     r9d, eax; wchar_t *
0x18004a62a  lea     r8, aGetidsReturned; "GetIds returned %lu items but expected "...
0x18004a631  mov     edx, 0A02h; wchar_t *
0x18004a636  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x18004a63d  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18004a642  mov     rcx, [r14]
0x18004a645  mov     [rsp+2D8h+var_218], rcx
0x18004a64d  mov     r8, [rdi+0C0h]
0x18004a654  mov     [rsp+2D8h+var_210], r8
0x18004a65c  mov     rax, [r14]
0x18004a65f  mov     [rsp+2D8h+var_218], rax
0x18004a667  lea     rdx, [rdi+2E0h]
0x18004a66e  mov     [rdx], rcx
0x18004a671  sub     r8, rax
0x18004a674  sar     r8, 4
0x18004a678  mov     [rdi+2E8h], r8d
0x18004a67f  mov     eax, [rdi+0F4h]
0x18004a685  mov     [rdi+2ECh], eax
0x18004a68b  mov     rcx, r15
0x18004a68e  call    ?ReplaceAll@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@Uguid@winrt@@@Collections@Foundation@Windows@winrt@@Uguid@5@@impl@winrt@@QEBA@U?$array_view@$$CBUguid@winrt@@@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::guid>,winrt::guid>::ReplaceAll(winrt::array_view<winrt::guid const>)
0x18004a693  mov     ecx, r12d; unsigned int
0x18004a696  call    ?ReportSemanticSearchWorkIdsCount@SemanticSearchTelemetryAggregated@@SAXI@Z; SemanticSearchTelemetryAggregated::ReportSemanticSearchWorkIdsCount(uint)
0x18004a69b  nop
0x18004a69c  mov     rax, [r15]
0x18004a69f  mov     [rsp+2D8h+var_200], rax
0x18004a6a7  test    rax, rax
0x18004a6aa  jz      short loc_18004A6B5
0x18004a6ac  mov     rcx, r15
0x18004a6af  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18004a6b4  nop
0x18004a6b5  mov     rcx, r14
0x18004a6b8  call    ??1?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::guid>::~vector<winrt::guid>(void)
0x18004a6bd  lea     r14, [rdi+0F8h]
0x18004a6c4  mov     [r14], rbx
0x18004a6c7  lea     rcx, [rdi+100h]
0x18004a6ce  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18004a6d3  nop
0x18004a6d4  lea     r13, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x18004a6db  mov     rcx, r13
0x18004a6de  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x18004a6e3  test    al, al
0x18004a6e5  jnz     short loc_18004A744
0x18004a6e7  mov     rsi, [rdi+138h]
0x18004a6ee  mov     [rsp+2D8h+var_190], rsi
0x18004a6f6  lea     r15, [rdi+140h]
0x18004a6fd  mov     [r15], rsi
0x18004a700  test    rsi, rsi
0x18004a703  jz      short loc_18004A70C
0x18004a705  lock inc dword ptr [rsi+120h]
0x18004a70c  mov     [rsp+2D8h+var_230], rsi
0x18004a714  lea     rcx, [rsi+0C8h]; lpCriticalSection
0x18004a71b  call    cs:__imp_EnterCriticalSection
0x18004a721  inc     dword ptr [rsi+0F0h]
0x18004a727  mov     rax, [r15]
0x18004a72a  mov     [rsp+2D8h+var_230], rax
0x18004a732  mov     dword ptr [rax+110h], 2Dh ; '-'
0x18004a73c  mov     rcx, r15
0x18004a73f  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18004a744  mov     rax, [rdi+88h]
0x18004a74b  lea     r12, [rax+28h]
0x18004a74f  cmp     [r12], rbx
0x18004a753  jz      loc_18004A972
0x18004a759  mov     rcx, r13
0x18004a75c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x18004a761  test    al, al
0x18004a763  jz      short loc_18004A7BC
0x18004a765  mov     rsi, [rdi+138h]
0x18004a76c  mov     [rsp+2D8h+var_190], rsi
0x18004a774  lea     r15, [rdi+148h]
0x18004a77b  mov     [r15], rsi
0x18004a77e  test    rsi, rsi
0x18004a781  jz      short loc_18004A78A
0x18004a783  lock inc dword ptr [rsi+120h]
0x18004a78a  mov     [rsp+2D8h+var_260], rsi
0x18004a78f  lea     rcx, [rsi+0C8h]; lpCriticalSection
0x18004a796  call    cs:__imp_EnterCriticalSection
0x18004a79c  inc     dword ptr [rsi+0F0h]
0x18004a7a2  mov     rax, [r15]
0x18004a7a5  mov     [rsp+2D8h+var_260], rax
0x18004a7aa  mov     dword ptr [rax+110h], 2Eh ; '.'
0x18004a7b4  mov     rcx, r15
0x18004a7b7  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18004a7bc  lea     r8, [rdi+150h]
0x18004a7c3  mov     rax, [rdi+90h]
0x18004a7ca  mov     [r8], rax
0x18004a7cd  lea     r13, [rdi+170h]
0x18004a7d4  lea     r9, [rdi+0A8h]
0x18004a7db  mov     rdx, r13
0x18004a7de  mov     rcx, r12
0x18004a7e1  call    ?QueryTextAsync@?$consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndex4@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUSemanticQueryOptions@SemanticSearch@Windows@Microsoft@3@@Z; winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndex4<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>::QueryTextAsync(winrt::param::hstring const &,winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions const &)
0x18004a7e6  nop
0x18004a7e7  lea     r15, [rdi+180h]
0x18004a7ee  mov     rcx, [r13+0]
0x18004a7f2  mov     [rsp+2D8h+var_248], rcx
0x18004a7fa  mov     [r15], rcx
0x18004a7fd  test    rcx, rcx
0x18004a800  jz      short loc_18004A80E
0x18004a802  mov     rax, [rcx]
0x18004a805  mov     rax, [rax+8]
0x18004a809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a80e  mov     [rdi+308h], r15
0x18004a815  lea     r12, [rdi+348h]
0x18004a81c  mov     rax, [r15]
0x18004a81f  mov     [rsp+2D8h+var_250], rax
0x18004a827  mov     [r15], rbx
0x18004a82a  mov     [r12], rax
0x18004a82e  mov     [rdi+350h], r12
0x18004a835  mov     ecx, 18h; Size
0x18004a83a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004a83f  mov     rsi, rax
0x18004a842  mov     dword ptr [rax+8], 1
0x18004a849  mov     rcx, [r12]
0x18004a84d  mov     [rsp+2D8h+var_258], rcx
0x18004a855  mov     [r12], rbx
0x18004a859  mov     [rax+10h], rcx
0x18004a85d  lea     rcx, [rax+18h]
0x18004a861  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x18004a866  lea     rax, off_18008AE50
0x18004a86d  mov     [rsi], rax
0x18004a870  mov     [rdi+178h], rsi
0x18004a877  mov     dword ptr [rdi+358h], 1
0x18004a881  mov     rax, [r12]
0x18004a885  mov     [rsp+2D8h+var_258], rax
0x18004a88d  test    rax, rax
0x18004a890  jz      short loc_18004A89B
0x18004a892  mov     rcx, r12
0x18004a895  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18004a89a  nop
0x18004a89b  mov     rax, [r15]
0x18004a89e  mov     [rsp+2D8h+var_250], rax
0x18004a8a6  test    rax, rax
0x18004a8a9  jz      short loc_18004A8B4
0x18004a8ab  mov     rcx, r15
0x18004a8ae  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18004a8b3  nop
0x18004a8b4  lea     rcx, [rdi+58h]; SRWLock
0x18004a8b8  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18004a8bd  mov     eax, [rdi+70h]
0x18004a8c0  cmp     eax, 2
0x18004a8c3  jz      short loc_18004A8F7
0x18004a8c5  lea     r15, [rdi+68h]
0x18004a8c9  lea     r12, [rdi+178h]
0x18004a8d0  cmp     r15, r12
0x18004a8d3  jz      short loc_18004A8EC
0x18004a8d5  cmp     [r15], rbx
0x18004a8d8  jz      short loc_18004A8E2
0x18004a8da  mov     rcx, r15
0x18004a8dd  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18004a8e2  mov     [r12], rbx
  ... truncated ...
```
