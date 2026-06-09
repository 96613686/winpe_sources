# IndexerSemanticSearchServicesImpl::ImageEmbedding(winrt::Windows::Graphics::Imaging::SoftwareBitmap const &)

- ea: `0x18003e914`
- end: `0x18003eb73`
- name: `?ImageEmbedding@IndexerSemanticSearchServicesImpl@@AEAA?AUEmbedding@SemanticSearch@Windows@Microsoft@winrt@@AEBUSoftwareBitmap@Imaging@Graphics@46@@Z`
- size: `607`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003eb7c`
- `0x180046140`

## callees

- `0x180008f84`
- `0x18000c478`
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
- `0x1800373cc`
- `0x18003acac`
- `0x18003e914`
- `0x18004ba10`
- `0x18004d9c4`
- `0x18004dea8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003eaa1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003eaa1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e9a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ea74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e9a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ea74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003eadd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003eadd`

## string_xrefs

- `0x18003eb61`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18003eb55`: `ImageEmbeddingGenerationCommon: Failed to create image embedding!`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IndexerSemanticSearchServicesImpl::ImageEmbedding(
        void (__fastcall *a1)(__int64, __int64 *),
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rbx
  __int64 *ImageEmbeddingGenerator; // rax
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  __int64 *v9; // rdi
  _DWORD *v10; // rdi
  struct _RTL_CRITICAL_SECTION *v11; // rsi
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  int matched; // ebx
  __int64 v15; // rax
  unsigned int *v16; // rax
  unsigned int v17; // eax
  const char *v18; // [rsp+28h] [rbp-61h]
  __int64 v19; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v20[2]; // [rsp+38h] [rbp-51h] BYREF
  _DWORD *v21; // [rsp+48h] [rbp-41h] BYREF
  _DWORD v22[4]; // [rsp+50h] [rbp-39h] BYREF
  const wchar_t *v23; // [rsp+60h] [rbp-29h]
  char v24[8]; // [rsp+70h] [rbp-19h] BYREF
  char v25[48]; // [rsp+78h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  struct _RTL_CRITICAL_SECTION *v28; // [rsp+108h] [rbp+7Fh] BYREF

  v6 = 0;
  v19 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
  {
    ImageEmbeddingGenerator = IndexerSemanticSearchServicesImpl::GetImageEmbeddingGenerator(a1, (__int64 *)&v28);
    if ( &v19 != ImageEmbeddingGenerator )
    {
      v6 = *ImageEmbeddingGenerator;
      *ImageEmbeddingGenerator = 0;
      v19 = v6;
    }
    if ( v28 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v28);
  }
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v24);
  v8 = (struct _RTL_CRITICAL_SECTION *)pv;
  v28 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv )
    _InterlockedIncrement((volatile signed __int32 *)pv + 72);
  EnterCriticalSection(v8 + 5);
  ++LODWORD(v8[6].DebugInfo);
  LODWORD(v8[6].SpinCount) = 10;
  tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v28);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
  {
    v9 = IndexerSemanticSearchServicesImpl::GetImageEmbeddingGenerator(a1, (__int64 *)&v28);
    if ( &v19 != v9 )
    {
      if ( v6 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v19);
      v6 = *v9;
      *v9 = 0;
      v19 = v6;
    }
    if ( v28 )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v28);
  }
  v22[0] = 1;
  v22[1] = 1;
  v23 = L"0";
  v21 = v22;
  winrt::impl::consume_Microsoft_Windows_SemanticSearch_IImageEmbeddingsGenerator<winrt::Microsoft::Windows::SemanticSearch::IImageEmbeddingsGenerator>::CreateItemEmbedding(
    &v19,
    v20,
    &v21,
    a3);
  if ( !(unsigned __int8)winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(v20) )
  {
    matched = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(v20);
    v15 = tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(
            v24,
            &v28);
    *(_DWORD *)(std::unique_ptr<wil::srwlock>::operator->(v15) + 280) = matched;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v28);
    v16 = (unsigned int *)winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(
                            v20,
                            &v28);
    v17 = wil::verify_hresult(*v16);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x4AA,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const char *)v17,
      (int)"ImageEmbeddingGenerationCommon: Failed to create image embedding!",
      v18);
  }
  winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(
    v20,
    a2);
  v10 = pv;
  v11 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
  v10[18] |= 0x300u;
  if ( *((_QWORD *)v10 + 31) )
    tip2::details::shared_data<0,0,0>::complete_helper(v10 + 2, 2);
  if ( v11 )
    LeaveCriticalSection(v11);
  if ( v20[0] )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v20);
  v12 = (struct _RTL_CRITICAL_SECTION *)pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
  {
    tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v12);
    CoTaskMemFree(v12);
  }
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v25);
  if ( v6 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v19);
  return a2;
}

```

## disassembly

```asm
0x18003e914  push    rbp
0x18003e916  push    rbx
0x18003e917  push    rsi
0x18003e918  push    rdi
0x18003e919  push    r14
0x18003e91b  push    r15
0x18003e91d  lea     rbp, [rsp-2Fh]
0x18003e922  sub     rsp, 0B8h
0x18003e929  mov     r15, r8
0x18003e92c  mov     r14, rdx
0x18003e92f  mov     rsi, rcx
0x18003e932  xor     ebx, ebx
0x18003e934  mov     [rbp+57h+var_B0], rbx
0x18003e938  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x18003e93f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x18003e944  test    al, al
0x18003e946  jz      short loc_18003E97B
0x18003e948  lea     rdx, [rbp+57h+arg_18]
0x18003e94c  mov     rcx, rsi
0x18003e94f  call    ?GetImageEmbeddingGenerator@IndexerSemanticSearchServicesImpl@@AEAA?AUImageEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@XZ; IndexerSemanticSearchServicesImpl::GetImageEmbeddingGenerator(void)
0x18003e954  lea     rcx, [rbp+57h+var_B0]
0x18003e958  cmp     rcx, rax
0x18003e95b  jz      short loc_18003E96B
0x18003e95d  mov     rbx, [rax]
0x18003e960  mov     qword ptr [rax], 0
0x18003e967  mov     [rbp+57h+var_B0], rbx
0x18003e96b  cmp     [rbp+57h+arg_18], 0
0x18003e970  jz      short loc_18003E97B
0x18003e972  lea     rcx, [rbp+57h+arg_18]
0x18003e976  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003e97b  lea     rcx, [rbp+57h+var_70]
0x18003e97f  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18003e984  nop
0x18003e985  mov     rdi, [rbp+57h+pv]
0x18003e989  mov     [rbp+57h+arg_18], rdi
0x18003e98d  test    rdi, rdi
0x18003e990  jz      short loc_18003E999
0x18003e992  lock inc dword ptr [rdi+120h]
0x18003e999  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x18003e9a0  call    cs:__imp_EnterCriticalSection
0x18003e9a6  inc     dword ptr [rdi+0F0h]
0x18003e9ac  mov     dword ptr [rdi+110h], 0Ah
0x18003e9b6  lea     rcx, [rbp+57h+arg_18]
0x18003e9ba  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003e9bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x18003e9c6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x18003e9cb  test    al, al
0x18003e9cd  jnz     short loc_18003EA13
0x18003e9cf  lea     rdx, [rbp+57h+arg_18]
0x18003e9d3  mov     rcx, rsi
0x18003e9d6  call    ?GetImageEmbeddingGenerator@IndexerSemanticSearchServicesImpl@@AEAA?AUImageEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@XZ; IndexerSemanticSearchServicesImpl::GetImageEmbeddingGenerator(void)
0x18003e9db  mov     rdi, rax
0x18003e9de  lea     rax, [rbp+57h+var_B0]
0x18003e9e2  cmp     rax, rdi
0x18003e9e5  jz      short loc_18003EA03
0x18003e9e7  test    rbx, rbx
0x18003e9ea  jz      short loc_18003E9F5
0x18003e9ec  lea     rcx, [rbp+57h+var_B0]
0x18003e9f0  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003e9f5  mov     rbx, [rdi]
0x18003e9f8  mov     qword ptr [rdi], 0
0x18003e9ff  mov     [rbp+57h+var_B0], rbx
0x18003ea03  cmp     [rbp+57h+arg_18], 0
0x18003ea08  jz      short loc_18003EA13
0x18003ea0a  lea     rcx, [rbp+57h+arg_18]
0x18003ea0e  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003ea13  mov     [rbp+57h+var_90], 1
0x18003ea1a  mov     [rbp+57h+var_8C], 1
0x18003ea21  lea     rax, a0; "0"
0x18003ea28  mov     [rbp+57h+var_80], rax
0x18003ea2c  lea     rax, [rbp+57h+var_90]
0x18003ea30  mov     [rbp+57h+var_98], rax
0x18003ea34  mov     r9, r15
0x18003ea37  lea     r8, [rbp+57h+var_98]
0x18003ea3b  lea     rdx, [rbp+57h+var_A8]
0x18003ea3f  lea     rcx, [rbp+57h+var_B0]
0x18003ea43  call    ?CreateItemEmbedding@?$consume_Microsoft_Windows_SemanticSearch_IImageEmbeddingsGenerator@UIImageEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUSoftwareBitmap@Imaging@Graphics@Windows@3@@Z; winrt::impl::consume_Microsoft_Windows_SemanticSearch_IImageEmbeddingsGenerator<winrt::Microsoft::Windows::SemanticSearch::IImageEmbeddingsGenerator>::CreateItemEmbedding(winrt::param::hstring const &,winrt::Windows::Graphics::Imaging::SoftwareBitmap const &)
0x18003ea48  nop
0x18003ea49  lea     rcx, [rbp+57h+var_A8]
0x18003ea4d  call    ?VerifyIsOK@?$consume_Windows_ApplicationModel_IPackageStatus@UIPackageStatus@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(void)
0x18003ea52  lea     rcx, [rbp+57h+var_A8]
0x18003ea56  test    al, al
0x18003ea58  jz      loc_18003EB0E
0x18003ea5e  mov     rdx, r14
0x18003ea61  call    ?ErrorText@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ErrorText(void)
0x18003ea66  mov     rdi, [rbp+57h+pv]
0x18003ea6a  lea     rsi, [rdi+0C8h]
0x18003ea71  mov     rcx, rsi; lpCriticalSection
0x18003ea74  call    cs:__imp_EnterCriticalSection
0x18003ea7a  or      dword ptr [rdi+48h], 300h
0x18003ea81  cmp     qword ptr [rdi+0F8h], 0
0x18003ea89  jz      short loc_18003EA99
0x18003ea8b  mov     edx, 2
0x18003ea90  lea     rcx, [rdi+8]
0x18003ea94  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18003ea99  test    rsi, rsi
0x18003ea9c  jz      short loc_18003EAA8
0x18003ea9e  mov     rcx, rsi; lpCriticalSection
0x18003eaa1  call    cs:__imp_LeaveCriticalSection
0x18003eaa7  nop
0x18003eaa8  cmp     [rbp+57h+var_A8], 0
0x18003eaad  jz      short loc_18003EAB9
0x18003eaaf  lea     rcx, [rbp+57h+var_A8]
0x18003eab3  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003eab8  nop
0x18003eab9  mov     rdi, [rbp+57h+pv]
0x18003eabd  test    rdi, rdi
0x18003eac0  jz      short loc_18003EAE3
0x18003eac2  or      eax, 0FFFFFFFFh
0x18003eac5  lock xadd [rdi+120h], eax
0x18003eacd  cmp     eax, 1
0x18003ead0  jnz     short loc_18003EAE3
0x18003ead2  mov     rcx, rdi
0x18003ead5  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x18003eada  mov     rcx, rdi; pv
0x18003eadd  call    cs:__imp_CoTaskMemFree
0x18003eae3  lea     rcx, [rbp+57h+var_68]; this
0x18003eae7  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18003eaec  nop
0x18003eaed  test    rbx, rbx
0x18003eaf0  jz      short loc_18003EAFB
0x18003eaf2  lea     rcx, [rbp+57h+var_B0]
0x18003eaf6  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003eafb  mov     rax, r14
0x18003eafe  add     rsp, 0B8h
0x18003eb05  pop     r15
0x18003eb07  pop     r14
0x18003eb09  pop     rdi
0x18003eb0a  pop     rsi
0x18003eb0b  pop     rbx
0x18003eb0c  pop     rbp
0x18003eb0d  retn
0x18003eb0e  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x18003eb13  nop
0x18003eb14  mov     ebx, eax
0x18003eb16  lea     rdx, [rbp+57h+arg_18]
0x18003eb1a  lea     rcx, [rbp+57h+var_70]
0x18003eb1e  call    ??C?$test_watcher@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@1@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::operator->(void)
0x18003eb23  mov     rcx, rax
0x18003eb26  call    ??C?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@QEBAPEAVsrwlock@wil@@XZ; std::unique_ptr<wil::srwlock>::operator->(void)
0x18003eb2b  mov     [rax+118h], ebx
0x18003eb31  lea     rcx, [rbp+57h+arg_18]
0x18003eb35  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003eb3a  lea     rdx, [rbp+57h+arg_18]
0x18003eb3e  lea     rcx, [rbp+57h+var_A8]
0x18003eb42  call    ?ExtendedError@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(void)
0x18003eb47  mov     ecx, [rax]
0x18003eb49  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18003eb4e  mov     r9d, eax; char *
0x18003eb51  mov     rcx, [rbp+5Fh]; this
0x18003eb55  lea     rax, aImageembedding_1; "ImageEmbeddingGenerationCommon: Failed "...
0x18003eb5c  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18003eb61  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x18003eb68  mov     edx, 4AAh; void *
0x18003eb6d  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
