# IndexerSemanticSearchServicesImpl::ImageEmbeddingGenerationCommon(winrt::Windows::Graphics::Imaging::SoftwareBitmap const &)

- ea: `0x18003eb7c`
- end: `0x18003ef18`
- name: `?ImageEmbeddingGenerationCommon@IndexerSemanticSearchServicesImpl@@AEAA?AUtagSemanticVector@@AEBUSoftwareBitmap@Imaging@Graphics@Windows@winrt@@@Z`
- size: `924`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `23`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035230`
- `0x180046140`

## callees

- `0x180008f84`
- `0x18000c478`
- `0x180015f90`
- `0x1800187b0`
- `0x180022760`
- `0x180028898`
- `0x180028c20`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x180032c94`
- `0x180032ca0`
- `0x18003534c`
- `0x180036954`
- `0x1800373cc`
- `0x18003acac`
- `0x18003e914`
- `0x18003eb7c`
- `0x18004ba10`
- `0x18004d708`
- `0x18004d9c4`
- `0x18004dea8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ed9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ed9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ec6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ed6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ec6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ed6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003edd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ee49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ee5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003edd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ee49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ee5c`

## string_xrefs

- `0x18003edf4`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18003ef06`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18003ee01`: `ImageEmbeddingGenerationCommon : Successfully generated vector using AIFabric`
- `0x18003eefa`: `ImageEmbeddingGenerationCommon: Failed to create image embedding!`
- `0x18003ee68`: `ImageEmbeddingGenerationCommon : Failed to generate vector using AIFabric`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_OWORD *__fastcall IndexerSemanticSearchServicesImpl::ImageEmbeddingGenerationCommon(
        __int64 a1,
        _OWORD *a2,
        __int64 a3)
{
  __int64 *v6; // rbx
  const wchar_t *v7; // r9
  __int64 v8; // rcx
  LPVOID *v9; // rcx
  __int64 v10; // rbx
  __int64 *ImageEmbeddingGenerator; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  __int64 *v13; // rdi
  __int64 *v14; // rdi
  __int64 v15; // rcx
  _DWORD *v16; // rdi
  struct _RTL_CRITICAL_SECTION *v17; // rsi
  struct _RTL_CRITICAL_SECTION *v18; // rdi
  _OWORD *v19; // rax
  int matched; // ebx
  __int64 v22; // rax
  unsigned int *v23; // rax
  unsigned int v24; // eax
  const char *v25; // [rsp+28h] [rbp-51h]
  __int64 v26; // [rsp+30h] [rbp-49h] BYREF
  __int64 v27; // [rsp+38h] [rbp-41h] BYREF
  __int64 v28; // [rsp+40h] [rbp-39h] BYREF
  LPVOID *v29; // [rsp+48h] [rbp-31h] BYREF
  LPVOID v30; // [rsp+50h] [rbp-29h] BYREF
  LPVOID v31; // [rsp+60h] [rbp-19h]
  char v32[8]; // [rsp+70h] [rbp-9h] BYREF
  char v33[48]; // [rsp+78h] [rbp-1h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  LPVOID v36; // [rsp+F8h] [rbp+7Fh] BYREF

  v26 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl'::`2'::impl) )
  {
    v6 = (__int64 *)IndexerSemanticSearchServicesImpl::ImageEmbedding(a1, &v36, a3);
    if ( &v26 != v6 )
    {
      v8 = *v6;
      *v6 = 0;
      v26 = v8;
    }
    if ( v36 )
    {
      v9 = &v36;
LABEL_38:
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v9);
    }
  }
  else
  {
    v10 = 0;
    v27 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
    {
      ImageEmbeddingGenerator = IndexerSemanticSearchServicesImpl::GetImageEmbeddingGenerator(
                                  (void (__fastcall *)(__int64, __int64 *))a1,
                                  (__int64 *)&v36);
      if ( &v27 != ImageEmbeddingGenerator )
      {
        v10 = *ImageEmbeddingGenerator;
        *ImageEmbeddingGenerator = 0;
        v27 = v10;
      }
      if ( v36 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v36);
    }
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v32);
    v12 = (struct _RTL_CRITICAL_SECTION *)pv;
    v36 = pv;
    if ( pv )
      _InterlockedIncrement((volatile signed __int32 *)pv + 72);
    EnterCriticalSection(v12 + 5);
    ++LODWORD(v12[6].DebugInfo);
    LODWORD(v12[6].SpinCount) = 10;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v36);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
    {
      v13 = IndexerSemanticSearchServicesImpl::GetImageEmbeddingGenerator(
              (void (__fastcall *)(__int64, __int64 *))a1,
              (__int64 *)&v36);
      if ( &v27 != v13 )
      {
        if ( v10 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v27);
        v10 = *v13;
        *v13 = 0;
        v27 = v10;
      }
      if ( v36 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v36);
    }
    v30 = (LPVOID)0x100000001LL;
    v31 = L"0";
    v29 = &v30;
    winrt::impl::consume_Microsoft_Windows_SemanticSearch_IImageEmbeddingsGenerator<winrt::Microsoft::Windows::SemanticSearch::IImageEmbeddingsGenerator>::CreateItemEmbedding(
      &v27,
      &v28,
      &v29,
      a3);
    if ( !(unsigned __int8)winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(&v28) )
    {
      matched = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v28);
      v22 = tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(
              v32,
              &v36);
      *(_DWORD *)(std::unique_ptr<wil::srwlock>::operator->(v22) + 280) = matched;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v36);
      v23 = (unsigned int *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(
                              &v28,
                              &v36);
      v24 = wil::verify_hresult(*v23);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x480,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const char *)v24,
        (int)"ImageEmbeddingGenerationCommon: Failed to create image embedding!",
        v25);
    }
    v14 = (__int64 *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(
                       &v28,
                       &v36);
    if ( &v26 != v14 )
    {
      if ( v26 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v26);
      v15 = *v14;
      *v14 = 0;
      v26 = v15;
    }
    if ( v36 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v36);
    v16 = pv;
    v17 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    v16[18] |= 0x300u;
    if ( *((_QWORD *)v16 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper(v16 + 2, 2);
    if ( v17 )
      LeaveCriticalSection(v17);
    if ( v28 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v28);
    v18 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v18);
      CoTaskMemFree(v18);
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v33);
    if ( v10 )
    {
      v9 = (LPVOID *)&v27;
      goto LABEL_38;
    }
  }
  if ( v26 )
  {
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0x488,
      (unsigned int)L"ImageEmbeddingGenerationCommon : Successfully generated vector using AIFabric",
      v7);
    v19 = (_OWORD *)anonymous_namespace_::EmbeddingToSemanticVector(&v29, *(_QWORD *)(a1 + 160), &v26);
    *a2 = *v19;
    a2[1] = v19[1];
    *v19 = 0;
    v19[1] = 0;
    if ( v30 )
    {
      CoTaskMemFree(v30);
      v30 = 0;
    }
    if ( v31 )
    {
      CoTaskMemFree(v31);
      v31 = 0;
    }
  }
  else
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0x48D,
      (unsigned int)L"ImageEmbeddingGenerationCommon : Failed to generate vector using AIFabric",
      v7);
    *a2 = 0;
    a2[1] = 0;
  }
  if ( v26 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v26);
  return a2;
}

```

## disassembly

```asm
0x18003eb7c  mov     [rsp-8+arg_0], rbx
0x18003eb81  mov     [rsp-8+arg_8], rsi
0x18003eb86  push    rbp
0x18003eb87  push    rdi
0x18003eb88  push    r12
0x18003eb8a  push    r14
0x18003eb8c  push    r15
0x18003eb8e  lea     rbp, [rsp-37h]
0x18003eb93  sub     rsp, 0B0h
0x18003eb9a  mov     rsi, r8
0x18003eb9d  mov     r14, rdx
0x18003eba0  mov     r15, rcx
0x18003eba3  xor     r12d, r12d
0x18003eba6  mov     [rbp+57h+var_A0], r12
0x18003ebaa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57180361@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361> `wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl(void)'::`2'::impl
0x18003ebb1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(void)
0x18003ebb6  test    al, al
0x18003ebb8  jz      short loc_18003EC01
0x18003ebba  mov     r8, rsi
0x18003ebbd  lea     rdx, [rbp+57h+arg_18]
0x18003ebc1  mov     rcx, r15
0x18003ebc4  call    ?ImageEmbedding@IndexerSemanticSearchServicesImpl@@AEAA?AUEmbedding@SemanticSearch@Windows@Microsoft@winrt@@AEBUSoftwareBitmap@Imaging@Graphics@46@@Z; IndexerSemanticSearchServicesImpl::ImageEmbedding(winrt::Windows::Graphics::Imaging::SoftwareBitmap const &)
0x18003ebc9  mov     rbx, rax
0x18003ebcc  lea     rax, [rbp+57h+var_A0]
0x18003ebd0  cmp     rax, rbx
0x18003ebd3  jz      short loc_18003EBEE
0x18003ebd5  cmp     [rbp+57h+var_A0], r12
0x18003ebd9  jz      short loc_18003EBE4
0x18003ebdb  lea     rcx, [rbp+57h+var_A0]
0x18003ebdf  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003ebe4  mov     rcx, [rbx]
0x18003ebe7  mov     [rbx], r12
0x18003ebea  mov     [rbp+57h+var_A0], rcx
0x18003ebee  cmp     [rbp+57h+arg_18], r12
0x18003ebf2  jz      loc_18003EDF4
0x18003ebf8  lea     rcx, [rbp+57h+arg_18]
0x18003ebfc  jmp     loc_18003EDEF
0x18003ec01  mov     rbx, r12
0x18003ec04  mov     [rbp+57h+var_98], rbx
0x18003ec08  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x18003ec0f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x18003ec14  test    al, al
0x18003ec16  jz      short loc_18003EC46
0x18003ec18  lea     rdx, [rbp+57h+arg_18]
0x18003ec1c  mov     rcx, r15
0x18003ec1f  call    ?GetImageEmbeddingGenerator@IndexerSemanticSearchServicesImpl@@AEAA?AUImageEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@XZ; IndexerSemanticSearchServicesImpl::GetImageEmbeddingGenerator(void)
0x18003ec24  lea     rcx, [rbp+57h+var_98]
0x18003ec28  cmp     rcx, rax
0x18003ec2b  jz      short loc_18003EC37
0x18003ec2d  mov     rbx, [rax]
0x18003ec30  mov     [rax], r12
0x18003ec33  mov     [rbp+57h+var_98], rbx
0x18003ec37  cmp     [rbp+57h+arg_18], r12
0x18003ec3b  jz      short loc_18003EC46
0x18003ec3d  lea     rcx, [rbp+57h+arg_18]
0x18003ec41  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003ec46  lea     rcx, [rbp+57h+var_60]
0x18003ec4a  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18003ec4f  nop
0x18003ec50  mov     rdi, [rbp+57h+pv]
0x18003ec54  mov     [rbp+57h+arg_18], rdi
0x18003ec58  test    rdi, rdi
0x18003ec5b  jz      short loc_18003EC64
0x18003ec5d  lock inc dword ptr [rdi+120h]
0x18003ec64  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18003ec6b  call    cs:__imp_EnterCriticalSection
0x18003ec71  inc     dword ptr [rdi+0F0h]
0x18003ec77  mov     dword ptr [rdi+110h], 0Ah
0x18003ec81  lea     rcx, [rbp+57h+arg_18]
0x18003ec85  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003ec8a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x18003ec91  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x18003ec96  test    al, al
0x18003ec98  jnz     short loc_18003ECD9
0x18003ec9a  lea     rdx, [rbp+57h+arg_18]
0x18003ec9e  mov     rcx, r15
0x18003eca1  call    ?GetImageEmbeddingGenerator@IndexerSemanticSearchServicesImpl@@AEAA?AUImageEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@XZ; IndexerSemanticSearchServicesImpl::GetImageEmbeddingGenerator(void)
0x18003eca6  mov     rdi, rax
0x18003eca9  lea     rax, [rbp+57h+var_98]
0x18003ecad  cmp     rax, rdi
0x18003ecb0  jz      short loc_18003ECCA
0x18003ecb2  test    rbx, rbx
0x18003ecb5  jz      short loc_18003ECC0
0x18003ecb7  lea     rcx, [rbp+57h+var_98]
0x18003ecbb  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003ecc0  mov     rbx, [rdi]
0x18003ecc3  mov     [rdi], r12
0x18003ecc6  mov     [rbp+57h+var_98], rbx
0x18003ecca  cmp     [rbp+57h+arg_18], r12
0x18003ecce  jz      short loc_18003ECD9
0x18003ecd0  lea     rcx, [rbp+57h+arg_18]
0x18003ecd4  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003ecd9  mov     dword ptr [rbp+57h+var_80], 1
0x18003ece0  mov     dword ptr [rbp+57h+var_80+4], 1
0x18003ece7  lea     rax, a0; "0"
0x18003ecee  mov     [rbp+57h+var_70], rax
0x18003ecf2  lea     rax, [rbp+57h+var_80]
0x18003ecf6  mov     [rbp+57h+var_88], rax
0x18003ecfa  mov     r9, rsi
0x18003ecfd  lea     r8, [rbp+57h+var_88]
0x18003ed01  lea     rdx, [rbp+57h+var_90]
0x18003ed05  lea     rcx, [rbp+57h+var_98]
0x18003ed09  call    ?CreateItemEmbedding@?$consume_Microsoft_Windows_SemanticSearch_IImageEmbeddingsGenerator@UIImageEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUSoftwareBitmap@Imaging@Graphics@Windows@3@@Z; winrt::impl::consume_Microsoft_Windows_SemanticSearch_IImageEmbeddingsGenerator<winrt::Microsoft::Windows::SemanticSearch::IImageEmbeddingsGenerator>::CreateItemEmbedding(winrt::param::hstring const &,winrt::Windows::Graphics::Imaging::SoftwareBitmap const &)
0x18003ed0e  nop
0x18003ed0f  lea     rcx, [rbp+57h+var_90]
0x18003ed13  call    ?VerifyIsOK@?$consume_Windows_ApplicationModel_IPackageStatus@UIPackageStatus@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(void)
0x18003ed18  lea     rcx, [rbp+57h+var_90]
0x18003ed1c  test    al, al
0x18003ed1e  jz      loc_18003EEB3
0x18003ed24  lea     rdx, [rbp+57h+arg_18]
0x18003ed28  call    ?ErrorText@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(void)
0x18003ed2d  mov     rdi, rax
0x18003ed30  lea     rax, [rbp+57h+var_A0]
0x18003ed34  cmp     rax, rdi
0x18003ed37  jz      short loc_18003ED52
0x18003ed39  cmp     [rbp+57h+var_A0], r12
0x18003ed3d  jz      short loc_18003ED48
0x18003ed3f  lea     rcx, [rbp+57h+var_A0]
0x18003ed43  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003ed48  mov     rcx, [rdi]
0x18003ed4b  mov     [rdi], r12
0x18003ed4e  mov     [rbp+57h+var_A0], rcx
0x18003ed52  cmp     [rbp+57h+arg_18], r12
0x18003ed56  jz      short loc_18003ED61
0x18003ed58  lea     rcx, [rbp+57h+arg_18]
0x18003ed5c  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003ed61  mov     rdi, [rbp+57h+pv]
0x18003ed65  lea     rsi, [rdi+0C8h]
0x18003ed6c  mov     rcx, rsi; lpCriticalSection
0x18003ed6f  call    cs:__imp_EnterCriticalSection
0x18003ed75  or      dword ptr [rdi+48h], 300h
0x18003ed7c  cmp     [rdi+0F8h], r12
0x18003ed83  jz      short loc_18003ED93
0x18003ed85  mov     edx, 2
0x18003ed8a  lea     rcx, [rdi+8]
0x18003ed8e  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18003ed93  test    rsi, rsi
0x18003ed96  jz      short loc_18003EDA2
0x18003ed98  mov     rcx, rsi; lpCriticalSection
0x18003ed9b  call    cs:__imp_LeaveCriticalSection
0x18003eda1  nop
0x18003eda2  cmp     [rbp+57h+var_90], r12
0x18003eda6  jz      short loc_18003EDB2
0x18003eda8  lea     rcx, [rbp+57h+var_90]
0x18003edac  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003edb1  nop
0x18003edb2  mov     rdi, [rbp+57h+pv]
0x18003edb6  test    rdi, rdi
0x18003edb9  jz      short loc_18003EDDC
0x18003edbb  or      eax, 0FFFFFFFFh
0x18003edbe  lock xadd [rdi+120h], eax
0x18003edc6  cmp     eax, 1
0x18003edc9  jnz     short loc_18003EDDC
0x18003edcb  mov     rcx, rdi
0x18003edce  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x18003edd3  mov     rcx, rdi; pv
0x18003edd6  call    cs:__imp_CoTaskMemFree
0x18003eddc  lea     rcx, [rbp+57h+var_58]; this
0x18003ede0  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18003ede5  nop
0x18003ede6  test    rbx, rbx
0x18003ede9  jz      short loc_18003EDF4
0x18003edeb  lea     rcx, [rbp+57h+var_98]
0x18003edef  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003edf4  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x18003edfb  cmp     [rbp+57h+var_A0], r12
0x18003edff  jz      short loc_18003EE68
0x18003ee01  lea     r8, aImageembedding_0; "ImageEmbeddingGenerationCommon : Succes"...
0x18003ee08  mov     edx, 488h; wchar_t *
0x18003ee0d  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18003ee12  lea     r8, [rbp+57h+var_A0]
0x18003ee16  mov     rdx, [r15+0A0h]
0x18003ee1d  lea     rcx, [rbp+57h+var_88]
0x18003ee21  call    _anonymous_namespace___EmbeddingToSemanticVector
0x18003ee26  movups  xmm0, xmmword ptr [rax]
0x18003ee29  movups  xmmword ptr [r14], xmm0
0x18003ee2d  movups  xmm1, xmmword ptr [rax+10h]
0x18003ee31  movups  xmmword ptr [r14+10h], xmm1
0x18003ee36  xorps   xmm0, xmm0
0x18003ee39  movups  xmmword ptr [rax], xmm0
0x18003ee3c  movups  xmmword ptr [rax+10h], xmm0
0x18003ee40  mov     rcx, [rbp+57h+var_80]; pv
0x18003ee44  test    rcx, rcx
0x18003ee47  jz      short loc_18003EE53
0x18003ee49  call    cs:__imp_CoTaskMemFree
0x18003ee4f  mov     [rbp+57h+var_80], r12
0x18003ee53  mov     rcx, [rbp+57h+var_70]; pv
0x18003ee57  test    rcx, rcx
0x18003ee5a  jz      short loc_18003EE85
0x18003ee5c  call    cs:__imp_CoTaskMemFree
0x18003ee62  mov     [rbp+57h+var_70], r12
0x18003ee66  jmp     short loc_18003EE85
0x18003ee68  lea     r8, aImageembedding; "ImageEmbeddingGenerationCommon : Failed"...
0x18003ee6f  mov     edx, 48Dh; wchar_t *
0x18003ee74  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18003ee79  xorps   xmm0, xmm0
0x18003ee7c  movups  xmmword ptr [r14], xmm0
0x18003ee80  movups  xmmword ptr [r14+10h], xmm0
0x18003ee85  cmp     [rbp+57h+var_A0], r12
0x18003ee89  jz      short loc_18003EE94
0x18003ee8b  lea     rcx, [rbp+57h+var_A0]
0x18003ee8f  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003ee94  mov     rax, r14
0x18003ee97  lea     r11, [rsp+0D0h+var_20]
0x18003ee9f  mov     rbx, [r11+30h]
0x18003eea3  mov     rsi, [r11+38h]
0x18003eea7  mov     rsp, r11
0x18003eeaa  pop     r15
0x18003eeac  pop     r14
0x18003eeae  pop     r12
0x18003eeb0  pop     rdi
0x18003eeb1  pop     rbp
0x18003eeb2  retn
0x18003eeb3  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x18003eeb8  nop
0x18003eeb9  mov     ebx, eax
0x18003eebb  lea     rdx, [rbp+57h+arg_18]
0x18003eebf  lea     rcx, [rbp+57h+var_60]
0x18003eec3  call    ??C?$test_watcher@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@1@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(void)
0x18003eec8  mov     rcx, rax
0x18003eecb  call    ??C?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@QEBAPEAVsrwlock@wil@@XZ; std::unique_ptr<wil::srwlock>::operator->(void)
0x18003eed0  mov     [rax+118h], ebx
0x18003eed6  lea     rcx, [rbp+57h+arg_18]
0x18003eeda  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003eedf  lea     rdx, [rbp+57h+arg_18]
0x18003eee3  lea     rcx, [rbp+57h+var_90]
0x18003eee7  call    ?ExtendedError@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(void)
0x18003eeec  mov     ecx, [rax]
0x18003eeee  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18003eef3  mov     r9d, eax; char *
0x18003eef6  mov     rcx, [rbp+5Fh]; this
0x18003eefa  lea     rax, aImageembedding_1; "ImageEmbeddingGenerationCommon: Failed "...
0x18003ef01  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18003ef06  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x18003ef0d  mov     edx, 480h; void *
0x18003ef12  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
