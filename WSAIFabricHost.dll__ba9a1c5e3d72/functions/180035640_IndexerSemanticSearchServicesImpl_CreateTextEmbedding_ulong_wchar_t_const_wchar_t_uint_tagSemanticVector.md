# IndexerSemanticSearchServicesImpl::CreateTextEmbedding(ulong,wchar_t const *,wchar_t *,uint *,tagSemanticVector * *)

- ea: `0x180035640`
- end: `0x180035ca6`
- name: `?CreateTextEmbedding@IndexerSemanticSearchServicesImpl@@UEAAJKPEB_WPEA_WPEAIPEAPEAUtagSemanticVector@@@Z`
- size: `1638`
- prototype: `__int64 __fastcall(IndexerSemanticSearchServicesImpl *this, unsigned int, const wchar_t *, wchar_t *, unsigned int *, struct tagSemanticVector **)`
- caller_count: `0`
- callee_count: `27`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800058cb`
- `0x18000591f`
- `0x180007fae`
- `0x18000c350`
- `0x18000c478`
- `0x18000c634`
- `0x180015f90`
- `0x1800187b0`
- `0x180019c3c`
- `0x180022760`
- `0x180028c20`
- `0x18002df50`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x180032f28`
- `0x180035640`
- `0x180036954`
- `0x180036d18`
- `0x1800373cc`
- `0x18003d104`
- `0x180049a80`
- `0x18004cb7c`
- `0x18004d9c4`
- `0x18004dea8`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180035a94`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180035a94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035a51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035a51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003571e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035935`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035a25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003571e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035935`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035a25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035a73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035a73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800359de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800359de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035b27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035c0c`

## string_xrefs

- `0x180035696`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180035b44`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180035b5e`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180035980`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180035c93`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18003568a`: `CreateTextEmbedding : Started`
- `0x180035971`: `Failed to create text embeddings`
- `0x180035b52`: `CreateTextEmbedding : Failed to generate vector using AIFabric`
- `0x180035b38`: `CreateTextEmbedding : Successfully generated vector using AIFabric. EmbeddingCount: %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall IndexerSemanticSearchServicesImpl::CreateTextEmbedding(
        IndexerSemanticSearchServicesImpl *this,
        unsigned int a2,
        const wchar_t *a3,
        wchar_t *a4,
        unsigned int *a5,
        struct tagSemanticVector **a6)
{
  wchar_t *v6; // r14
  const wchar_t *v7; // r13
  unsigned int v8; // r12d
  IndexerSemanticSearchServicesImpl *v9; // rbx
  int v10; // esi
  unsigned __int8 v11; // al
  const wchar_t *v12; // r9
  __int64 v13; // r15
  __int64 *TextEmbeddingGenerator; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  __int64 v16; // rcx
  __int64 *v17; // rbx
  unsigned int v18; // edx
  int v19; // esi
  volatile signed __int32 *v20; // r14
  int v21; // eax
  __int64 (__fastcall *v22)(const struct winrt::Windows::Foundation::IActivationFactory *); // rbx
  int v23; // eax
  HANDLE ProcessHeap; // rax
  int matched; // esi
  struct _RTL_CRITICAL_SECTION *v26; // rbx
  int v27; // esi
  void *v28; // rbx
  __int64 result; // rax
  _DWORD *v30; // rsi
  struct _RTL_CRITICAL_SECTION *v31; // r14
  const wchar_t *v32; // r9
  unsigned int v33; // esi
  struct tagSemanticVector *v34; // rax
  const char *v35; // r9
  unsigned int i; // r14d
  __int128 *v37; // rax
  __int128 v38; // xmm1
  __int128 v39; // xmm2
  __int64 v40; // r12
  __int64 v41; // rax
  char *v42; // rsi
  char *v43; // r14
  void *v44; // rbx
  int v45; // eax
  const char *v46; // [rsp+20h] [rbp-128h]
  const char *v47; // [rsp+28h] [rbp-120h]
  unsigned __int8 v48; // [rsp+30h] [rbp-118h]
  __int64 (__fastcall *v49)(const struct winrt::Windows::Foundation::IActivationFactory *); // [rsp+38h] [rbp-110h] BYREF
  int v50; // [rsp+40h] [rbp-108h]
  __int64 v51; // [rsp+48h] [rbp-100h] BYREF
  __int64 (__fastcall *v52)(const struct winrt::Windows::Foundation::IActivationFactory *); // [rsp+50h] [rbp-F8h] BYREF
  __int64 v53; // [rsp+58h] [rbp-F0h] BYREF
  __int64 *v54; // [rsp+60h] [rbp-E8h] BYREF
  LPVOID v55; // [rsp+68h] [rbp-E0h] BYREF
  wchar_t *v56; // [rsp+70h] [rbp-D8h]
  __int64 v57; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v58; // [rsp+80h] [rbp-C8h] BYREF
  LPVOID *v59; // [rsp+88h] [rbp-C0h] BYREF
  LPVOID v60[2]; // [rsp+90h] [rbp-B8h] BYREF
  LPVOID v61; // [rsp+A0h] [rbp-A8h]
  _BYTE v62[8]; // [rsp+A8h] [rbp-A0h] BYREF
  int v63; // [rsp+B0h] [rbp-98h] BYREF
  __int128 v64; // [rsp+B8h] [rbp-90h]
  _BYTE v65[8]; // [rsp+D0h] [rbp-78h] BYREF
  _BYTE v66[48]; // [rsp+D8h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+108h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v6 = a4;
  v7 = a3;
  v8 = a2;
  v9 = this;
  v10 = 0;
  v50 = 0;
  v11 = 0;
  v48 = 0;
  v12 = 0;
  while ( 2 )
  {
    if ( v11 >= 3u )
      return (unsigned int)v12;
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0x37A,
      (unsigned int)L"CreateTextEmbedding : Started",
      v12);
    try
    {
      v13 = 0;
      v51 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
      {
        TextEmbeddingGenerator = (__int64 *)IndexerSemanticSearchServicesImpl::GetTextEmbeddingGenerator(v9, &v57, v6);
        if ( &v51 != TextEmbeddingGenerator )
        {
          v13 = *TextEmbeddingGenerator;
          *TextEmbeddingGenerator = 0;
          v51 = v13;
        }
        if ( v57 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v57);
      }
      tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(v65);
      v15 = (struct _RTL_CRITICAL_SECTION *)pv;
      v52 = (__int64 (__fastcall *)(const struct winrt::Windows::Foundation::IActivationFactory *))pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 72);
      EnterCriticalSection(v15 + 5);
      ++LODWORD(v15[6].DebugInfo);
      LODWORD(v15[6].SpinCount) = 8;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v52);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
      {
        v17 = (__int64 *)IndexerSemanticSearchServicesImpl::GetTextEmbeddingGenerator(this, &v58, v6);
        if ( &v51 != v17 )
        {
          if ( v13 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
          v13 = *v17;
          *v17 = 0;
          v51 = v13;
        }
        if ( v58 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v58);
      }
      v54 = &qword_1800AF738;
      _InterlockedIncrement64(&qword_1800AF738);
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory> )
      {
        _lambda_1f675fac5d8dafc75d3c42376965940e_::operator()(
          v16,
          &v53,
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory>);
        v19 = v10 | 1;
        v50 = v19;
        _InterlockedDecrement64(&qword_1800AF738);
      }
      else
      {
        _InterlockedDecrement64(&qword_1800AF738);
        v52 = _lambda_1f675fac5d8dafc75d3c42376965940e_::_lambda_invoker_cdecl_;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
          v16,
          &v53,
          &v52);
        v19 = v10 | 1;
        v50 = v19;
      }
      if ( v8 )
      {
        v20 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)v8, v18);
        memcpy_s((void *const)(v20 + 7), 2LL * v8, v7, 2LL * v8);
      }
      else
      {
        v20 = 0;
      }
      v54 = (__int64 *)v20;
      v60[0] = (LPVOID)0x100000001LL;
      v61 = L"0";
      v59 = v60;
      v52 = 0;
      v63 = 0;
      v64 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64, LPVOID *, volatile signed __int32 *, __int64, __int64 (__fastcall **)(const struct winrt::Windows::Foundation::IActivationFactory *)))(*(_QWORD *)v13 + 64LL))(
              v13,
              v60,
              v20,
              v53,
              &v52);
      if ( v21 < 0 )
        winrt::throw_hresult((unsigned int)v21, &v63);
      v22 = v52;
      v49 = v52;
      if ( v20 )
      {
        v23 = _InterlockedDecrement(v20 + 6);
        if ( v23 )
        {
          if ( v23 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v20);
        }
      }
      v50 = v19 | 2;
      if ( (unsigned __int8)winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(&v49) )
      {
        winrt::impl::consume_Microsoft_Windows_SemanticSearch_IMultipleEmbeddingsResult<winrt::Microsoft::Windows::SemanticSearch::IMultipleEmbeddingsResult>::Embeddings(
          &v49,
          &v55);
        v30 = pv;
        v31 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
        EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
        v30[18] |= 0x300u;
        if ( *((_QWORD *)v30 + 31) )
          tip2::details::shared_data<0,0,0>::complete_helper(v30 + 2, 2);
        if ( v31 )
          LeaveCriticalSection(v31);
        v33 = (unsigned int)v56;
        if ( (_DWORD)v56 )
        {
          *a5 = (unsigned int)v56;
          v34 = (struct tagSemanticVector *)CoTaskMemAlloc(32LL * v33);
          if ( !v34 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x39B,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
              v35);
          *a6 = v34;
          for ( i = 0; i < v33; ++i )
          {
            v37 = (__int128 *)anonymous_namespace_::EmbeddingToSemanticVector(
                                &v59,
                                *((_QWORD *)this + 20),
                                (char *)v55 + 8 * i);
            v38 = *v37;
            v39 = v37[1];
            *v37 = 0;
            v37[1] = 0;
            v40 = 32LL * i;
            v41 = (__int64)*a6;
            *(_OWORD *)(v40 + v41) = v38;
            *(_OWORD *)(v40 + v41 + 16) = v39;
            if ( v60[0] )
            {
              CoTaskMemFree(v60[0]);
              v60[0] = 0;
            }
            if ( v61 )
              CoTaskMemFree(v61);
          }
          SearchIndexerTrace::Verbose(
            (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
            (const wchar_t *)0x3A0,
            (unsigned int)L"CreateTextEmbedding : Successfully generated vector using AIFabric. EmbeddingCount: %u",
            (const wchar_t *)v33);
        }
        else
        {
          SearchIndexerTrace::Error(
            (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
            (const wchar_t *)0x3A4,
            (unsigned int)L"CreateTextEmbedding : Failed to generate vector using AIFabric",
            v32);
          *a5 = 0;
          *a6 = 0;
        }
        v42 = (char *)v55;
        if ( v55 )
        {
          v43 = (char *)v55 + 8 * (unsigned int)v56;
          if ( v55 != v43 )
          {
            do
            {
              if ( *(_QWORD *)v42 )
                winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v42);
              v42 += 8;
            }
            while ( v42 != v43 );
            v42 = (char *)v55;
          }
          CoTaskMemFree_0(v42);
          v55 = 0;
          LODWORD(v56) = 0;
        }
        if ( v22 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v49);
        if ( v53 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v53);
        v44 = pv;
        if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
        {
          tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v44);
          CoTaskMemFree(v44);
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v66);
        if ( v13 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
        result = 0;
      }
      else
      {
        matched = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v49);
        v26 = (struct _RTL_CRITICAL_SECTION *)pv;
        v54 = (__int64 *)pv;
        if ( pv )
          _InterlockedIncrement((volatile signed __int32 *)pv + 72);
        EnterCriticalSection(v26 + 5);
        ++LODWORD(v26[6].DebugInfo);
        LODWORD(v26[7].DebugInfo) = matched;
        tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v54);
        v27 = *(_DWORD *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(
                           &v49,
                           v62);
        if ( v27 < 0 )
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x391,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
            (const char *)(unsigned int)v27,
            (int)"Failed to create text embeddings",
            v47);
        if ( v52 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v49);
        if ( v53 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v53);
        v28 = pv;
        if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
        {
          tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v28);
          CoTaskMemFree(v28);
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v66);
        if ( v13 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
        result = (unsigned int)v27;
      }
    }
    catch ( ... )
    {
      IndexerSemanticSearchServicesImpl::ResetTextEmbeddingGenerator(this, a4);
      v45 = wil::details::in1diag3::Log_CaughtExceptionMsg(
              retaddr,
              (void *)0x3AE,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
              "CreateTextEmbedding : Exception occurred while creating text embedding",
              v46);
      LODWORD(v49) = v45;
      if ( v45 < 0
        && ((v45 & 0x1FFF0000) == 0x10000
         || (v45 & 0x1FFF0000) == 0x70000 && (unsigned int)(unsigned __int16)v45 - 1700 <= 0x12B) )
      {
        ++v48;
        v6 = a4;
        v7 = a3;
        v8 = a2;
        v11 = v48;
        v12 = (const wchar_t *)(unsigned int)v49;
        v10 = v50;
        v9 = this;
        continue;
      }
      return (unsigned int)v49;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x180035640  mov     rax, rsp
0x180035643  mov     [rax+20h], r9
0x180035647  mov     [rax+18h], r8
0x18003564b  mov     [rax+10h], edx
0x18003564e  mov     [rax+8], rcx
0x180035652  push    rbx
0x180035653  push    rsi
0x180035654  push    rdi
0x180035655  push    r12
0x180035657  push    r13
0x180035659  push    r14
0x18003565b  push    r15
0x18003565d  sub     rsp, 110h
0x180035664  mov     r14, r9
0x180035667  mov     r13, r8
0x18003566a  mov     r12d, edx
0x18003566d  mov     rbx, rcx
0x180035670  xor     edi, edi
0x180035672  mov     esi, edi
0x180035674  mov     [rsp+148h+var_108], edi
0x180035678  mov     al, dil
0x18003567b  mov     [rsp+148h+var_118], al
0x18003567f  mov     r9d, edi; wchar_t *
0x180035682  cmp     al, 3
0x180035684  jnb     loc_180035C6D
0x18003568a  lea     r8, aCreatetextembe; "CreateTextEmbedding : Started"
0x180035691  mov     edx, 37Ah; wchar_t *
0x180035696  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x18003569d  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1800356a2  mov     r15, rdi
0x1800356a5  mov     [rsp+148h+var_100], rdi
0x1800356aa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x1800356b1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x1800356b6  test    al, al
0x1800356b8  jz      short loc_1800356F0
0x1800356ba  mov     r8, r14
0x1800356bd  lea     rdx, [rsp+148h+var_D0]
0x1800356c2  mov     rcx, rbx
0x1800356c5  call    ?GetTextEmbeddingGenerator@IndexerSemanticSearchServicesImpl@@AEAA?AUTextEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@PEA_W@Z; IndexerSemanticSearchServicesImpl::GetTextEmbeddingGenerator(wchar_t *)
0x1800356ca  lea     rcx, [rsp+148h+var_100]
0x1800356cf  cmp     rcx, rax
0x1800356d2  jz      short loc_1800356DF
0x1800356d4  mov     r15, [rax]
0x1800356d7  mov     [rax], rdi
0x1800356da  mov     [rsp+148h+var_100], r15
0x1800356df  cmp     [rsp+148h+var_D0], rdi
0x1800356e4  jz      short loc_1800356F0
0x1800356e6  lea     rcx, [rsp+148h+var_D0]
0x1800356eb  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800356f0  lea     rcx, [rsp+148h+var_78]
0x1800356f8  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1800356fd  nop
0x1800356fe  mov     rbx, [rsp+148h+pv]
0x180035706  mov     [rsp+148h+var_F8], rbx
0x18003570b  test    rbx, rbx
0x18003570e  jz      short loc_180035717
0x180035710  lock inc dword ptr [rbx+120h]
0x180035717  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18003571e  call    cs:__imp_EnterCriticalSection
0x180035724  inc     dword ptr [rbx+0F0h]
0x18003572a  mov     dword ptr [rbx+110h], 8
0x180035734  lea     rcx, [rsp+148h+var_F8]
0x180035739  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003573e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x180035745  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x18003574a  test    al, al
0x18003574c  jnz     short loc_1800357A4
0x18003574e  mov     r8, r14
0x180035751  lea     rdx, [rsp+148h+var_C8]
0x180035759  mov     rcx, [rsp+148h+arg_0]
0x180035761  call    ?GetTextEmbeddingGenerator@IndexerSemanticSearchServicesImpl@@AEAA?AUTextEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@PEA_W@Z; IndexerSemanticSearchServicesImpl::GetTextEmbeddingGenerator(wchar_t *)
0x180035766  mov     rbx, rax
0x180035769  lea     rax, [rsp+148h+var_100]
0x18003576e  cmp     rax, rbx
0x180035771  jz      short loc_18003578D
0x180035773  test    r15, r15
0x180035776  jz      short loc_180035782
0x180035778  lea     rcx, [rsp+148h+var_100]
0x18003577d  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180035782  mov     r15, [rbx]
0x180035785  mov     [rbx], rdi
0x180035788  mov     [rsp+148h+var_100], r15
0x18003578d  cmp     [rsp+148h+var_C8], rdi
0x180035795  jz      short loc_1800357A4
0x180035797  lea     rcx, [rsp+148h+var_C8]
0x18003579f  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800357a4  lea     rax, qword_1800AF738
0x1800357ab  mov     [rsp+148h+var_E8], rax
0x1800357b0  lock inc cs:qword_1800AF738
0x1800357b8  cmp     cs:??$factory_cache_entry_v@UTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@impl@winrt@@3U?$factory_cache_entry@UTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@12@A, rdi; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory>
0x1800357bf  jz      short loc_1800357E3
0x1800357c1  lea     r8, ??$factory_cache_entry_v@UTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@impl@winrt@@3U?$factory_cache_entry@UTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory>
0x1800357c8  lea     rdx, [rsp+148h+var_F0]
0x1800357cd  call    ??R_lambda_1f675fac5d8dafc75d3c42376965940e_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_1f675fac5d8dafc75d3c42376965940e_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x1800357d2  or      esi, 1
0x1800357d5  mov     [rsp+148h+var_108], esi
0x1800357d9  lock dec cs:qword_1800AF738
0x1800357e1  jmp     short loc_18003580D
0x1800357e3  lock dec cs:qword_1800AF738
0x1800357eb  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1f675fac5d8dafc75d3c42376965940e_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_1f675fac5d8dafc75d3c42376965940e_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x1800357f2  mov     [rsp+148h+var_F8], rax
0x1800357f7  lea     r8, [rsp+148h+var_F8]
0x1800357fc  lea     rdx, [rsp+148h+var_F0]
0x180035801  call    ??$call@P6A?AUTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@35@@Z@?$factory_cache_entry@UTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@impl@winrt@@QEAA?A_P$$QEAP6A?AUTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@52@@Z@Z
0x180035806  or      esi, 1
0x180035809  mov     [rsp+148h+var_108], esi
0x18003580d  mov     ebx, r12d
0x180035810  test    r12d, r12d
0x180035813  jnz     short loc_18003581A
0x180035815  mov     r14, rdi
0x180035818  jmp     short loc_180035839
0x18003581a  mov     ecx, ebx; this
0x18003581c  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180035821  mov     r14, rax
0x180035824  mov     rdx, rbx
0x180035827  add     rdx, rdx; DestinationSize
0x18003582a  lea     rcx, [rax+1Ch]; Destination
0x18003582e  mov     r9, rdx; SourceSize
0x180035831  mov     r8, r13; Source
0x180035834  call    memcpy_s
0x180035839  mov     [rsp+148h+var_E8], r14
0x18003583e  mov     dword ptr [rsp+148h+var_B8], 1
0x180035849  mov     dword ptr [rsp+148h+var_B8+4], 1
0x180035854  lea     rax, a0; "0"
0x18003585b  mov     [rsp+148h+var_A8], rax
0x180035863  lea     rax, [rsp+148h+var_B8]
0x18003586b  mov     [rsp+148h+var_C0], rax
0x180035873  mov     [rsp+148h+var_F8], rdi
0x180035878  mov     [rsp+148h+var_98], edi
0x18003587f  xorps   xmm0, xmm0
0x180035882  movdqu  [rsp+148h+var_90], xmm0
0x18003588b  mov     rax, [r15]
0x18003588e  lea     rcx, [rsp+148h+var_F8]
0x180035893  mov     qword ptr [rsp+148h+var_128], rcx
0x180035898  mov     r9, [rsp+148h+var_F0]
0x18003589d  mov     r8, r14
0x1800358a0  lea     rdx, [rsp+148h+var_B8]
0x1800358a8  mov     rcx, r15
0x1800358ab  mov     rax, [rax+40h]
0x1800358af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358b4  test    eax, eax
0x1800358b6  js      loc_180035C83
0x1800358bc  mov     rbx, [rsp+148h+var_F8]
0x1800358c1  mov     [rsp+148h+var_110], rbx
0x1800358c6  test    r14, r14
0x1800358c9  jz      short loc_1800358F0
0x1800358cb  or      eax, 0FFFFFFFFh
0x1800358ce  lock xadd [r14+18h], eax
0x1800358d4  sub     eax, 1
0x1800358d7  jnz     loc_180035A8C
0x1800358dd  nop
0x1800358de  call    WINRT_IMPL_GetProcessHeap
0x1800358e3  mov     rcx, rax; hHeap
0x1800358e6  mov     r8, r14; lpMem
0x1800358e9  xor     edx, edx; dwFlags
0x1800358eb  call    WINRT_IMPL_HeapFree
0x1800358f0  or      esi, 2
0x1800358f3  mov     [rsp+148h+var_108], esi
0x1800358f7  lea     rcx, [rsp+148h+var_110]
0x1800358fc  call    ?VerifyIsOK@?$consume_Windows_ApplicationModel_IPackageStatus@UIPackageStatus@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(void)
0x180035901  lea     rcx, [rsp+148h+var_110]
0x180035906  test    al, al
0x180035908  jnz     loc_180035A08
0x18003590e  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x180035913  mov     esi, eax
0x180035915  mov     rbx, [rsp+148h+pv]
0x18003591d  mov     [rsp+148h+var_E8], rbx
0x180035922  test    rbx, rbx
0x180035925  jz      short loc_18003592E
0x180035927  lock inc dword ptr [rbx+120h]
0x18003592e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180035935  call    cs:__imp_EnterCriticalSection
0x18003593b  inc     dword ptr [rbx+0F0h]
0x180035941  mov     [rbx+118h], esi
0x180035947  lea     rcx, [rsp+148h+var_E8]
0x18003594c  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180035951  lea     rdx, [rsp+148h+var_A0]
0x180035959  lea     rcx, [rsp+148h+var_110]
0x18003595e  call    ?ExtendedError@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(void)
0x180035963  mov     esi, [rax]
0x180035965  test    esi, esi
0x180035967  jns     short loc_180035992
0x180035969  mov     rcx, [rsp+148h]; this
0x180035971  lea     rax, aFailedToCreate_0; "Failed to create text embeddings"
0x180035978  mov     qword ptr [rsp+148h+var_128], rax; int
0x18003597d  mov     r9d, esi; char *
0x180035980  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180035987  mov     edx, 391h; void *
0x18003598c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180035991  nop
0x180035992  cmp     [rsp+148h+var_F8], rdi
0x180035997  jz      short loc_1800359A4
0x180035999  lea     rcx, [rsp+148h+var_110]
0x18003599e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800359a3  nop
0x1800359a4  cmp     [rsp+148h+var_F0], rdi
0x1800359a9  jz      short loc_1800359B6
0x1800359ab  lea     rcx, [rsp+148h+var_F0]
0x1800359b0  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800359b5  nop
0x1800359b6  mov     rbx, [rsp+148h+pv]
0x1800359be  test    rbx, rbx
0x1800359c1  jz      short loc_1800359E4
0x1800359c3  or      eax, 0FFFFFFFFh
0x1800359c6  lock xadd [rbx+120h], eax
0x1800359ce  cmp     eax, 1
0x1800359d1  jnz     short loc_1800359E4
0x1800359d3  mov     rcx, rbx
0x1800359d6  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x1800359db  mov     rcx, rbx; pv
0x1800359de  call    cs:__imp_CoTaskMemFree
0x1800359e4  lea     rcx, [rsp+148h+var_70]; this
0x1800359ec  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800359f1  nop
0x1800359f2  test    r15, r15
0x1800359f5  jz      short loc_180035A01
0x1800359f7  lea     rcx, [rsp+148h+var_100]
0x1800359fc  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180035a01  mov     eax, esi
0x180035a03  jmp     loc_180035C70
0x180035a08  lea     rdx, [rsp+148h+var_E0]
0x180035a0d  call    ?Embeddings@?$consume_Microsoft_Windows_SemanticSearch_IMultipleEmbeddingsResult@UIMultipleEmbeddingsResult@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_SemanticSearch_IMultipleEmbeddingsResult<winrt::Microsoft::Windows::SemanticSearch::IMultipleEmbeddingsResult>::Embeddings(void)
0x180035a12  nop
0x180035a13  mov     rsi, [rsp+148h+pv]
0x180035a1b  lea     r14, [rsi+0C8h]
0x180035a22  mov     rcx, r14; lpCriticalSection
0x180035a25  call    cs:__imp_EnterCriticalSection
0x180035a2b  or      dword ptr [rsi+48h], 300h
0x180035a32  cmp     [rsi+0F8h], rdi
0x180035a39  jz      short loc_180035A49
0x180035a3b  mov     edx, 2
0x180035a40  lea     rcx, [rsi+8]
0x180035a44  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180035a49  test    r14, r14
0x180035a4c  jz      short loc_180035A57
0x180035a4e  mov     rcx, r14; lpCriticalSection
0x180035a51  call    cs:__imp_LeaveCriticalSection
0x180035a57  mov     esi, dword ptr [rsp+148h+var_D8]
0x180035a5b  test    esi, esi
0x180035a5d  jz      loc_180035B52
0x180035a63  mov     rax, [rsp+148h+arg_20]
0x180035a6b  mov     [rax], esi
0x180035a6d  mov     ecx, esi
0x180035a6f  shl     rcx, 5; cb
0x180035a73  call    cs:__imp_CoTaskMemAlloc
0x180035a79  mov     rcx, [rsp+148h]; this
0x180035a81  test    rax, rax
0x180035a84  jz      loc_180035C93
0x180035a8a  jmp     short loc_180035A9B
0x180035a8c  test    eax, eax
0x180035a8e  jns     loc_1800358F0
0x180035a94  call    cs:__imp_abort
0x180035a9b  mov     r13, [rsp+148h+arg_28]
0x180035aa3  mov     [r13+0], rax
0x180035aa7  mov     r14d, edi
0x180035aaa  cmp     r14d, esi
0x180035aad  jnb     loc_180035B35
0x180035ab3  mov     r12d, r14d
0x180035ab6  mov     rax, [rsp+148h+var_E0]
0x180035abb  lea     r8, [rax+r12*8]
0x180035abf  mov     rax, [rsp+148h+arg_0]
0x180035ac7  mov     rdx, [rax+0A0h]
0x180035ace  lea     rcx, [rsp+148h+var_C0]
0x180035ad6  call    _anonymous_namespace___EmbeddingToSemanticVector
0x180035adb  movups  xmm1, xmmword ptr [rax]
0x180035ade  movups  xmm2, xmmword ptr [rax+10h]
0x180035ae2  xorps   xmm0, xmm0
0x180035ae5  movups  xmmword ptr [rax], xmm0
0x180035ae8  movups  xmmword ptr [rax+10h], xmm0
0x180035aec  shl     r12, 5
0x180035af0  mov     rax, [r13+0]
0x180035af4  movups  xmmword ptr [r12+rax], xmm1
0x180035af9  movups  xmmword ptr [r12+rax+10h], xmm2
0x180035aff  mov     rcx, [rsp+148h+var_B8]; pv
0x180035b07  test    rcx, rcx
0x180035b0a  jz      short loc_180035B1A
0x180035b0c  call    cs:__imp_CoTaskMemFree
0x180035b12  mov     [rsp+148h+var_B8], rdi
0x180035b1a  mov     rcx, [rsp+148h+var_A8]; pv
0x180035b22  test    rcx, rcx
0x180035b25  jz      short loc_180035B2D
0x180035b27  call    cs:__imp_CoTaskMemFree
0x180035b2d  inc     r14d
0x180035b30  jmp     loc_180035AAA
0x180035b35  mov     r9d, esi; wchar_t *
0x180035b38  lea     r8, aCreatetextembe_1; "CreateTextEmbedding : Successfully gene"...
0x180035b3f  mov     edx, 3A0h; wchar_t *
0x180035b44  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180035b4b  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180035b50  jmp     short loc_180035B7F
0x180035b52  lea     r8, aCreatetextembe_0; "CreateTextEmbedding : Failed to generat"...
0x180035b59  mov     edx, 3A4h; wchar_t *
0x180035b5e  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180035b65  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180035b6a  mov     rax, [rsp+148h+arg_20]
0x180035b72  mov     [rax], edi
0x180035b74  mov     rax, [rsp+148h+arg_28]
0x180035b7c  mov     [rax], rdi
0x180035b7f  mov     rsi, [rsp+148h+var_E0]
0x180035b84  test    rsi, rsi
  ... truncated ...
```
