# IndexerSemanticStore::AddItemsForId(_GUID,ulong,tagSemanticStoreItem const *)

- ea: `0x180033500`
- end: `0x180033b04`
- name: `?AddItemsForId@IndexerSemanticStore@@UEAAJU_GUID@@KPEBUtagSemanticStoreItem@@@Z`
- size: `1540`
- prototype: `__int64 __fastcall(IndexerSemanticStore *this, struct _GUID *, unsigned int, const struct tagSemanticStoreItem *)`
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007ad0`
- `0x18000b064`
- `0x18000c478`
- `0x180015f90`
- `0x1800187b0`
- `0x1800189d8`
- `0x180019c3c`
- `0x180028c20`
- `0x18002b1dc`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x180032254`
- `0x1800326e8`
- `0x180032ac4`
- `0x180033500`
- `0x180034540`
- `0x180034e2c`
- `0x1800496d4`
- `0x180049900`
- `0x18004c720`
- `0x18004cd60`
- `0x18004ceb8`
- `0x18004dea8`
- `0x1800542b4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003386b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003386b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003389a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003389a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033a51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033a51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800336b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800338f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033940`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033a25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800336b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800338f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033940`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033a25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033a90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800339ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033a90`

## string_xrefs

- `0x180033538`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18003382f`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x1800339a4`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IndexerSemanticStore::AddItemsForId(
        IndexerSemanticStore *this,
        struct _GUID *a2,
        unsigned int a3,
        const struct tagSemanticStoreItem *a4)
{
  __int64 v5; // rsi
  IndexerSemanticStore *v6; // r15
  size_t v7; // rcx
  _QWORD *v8; // rdx
  void *v9; // rax
  __int64 *v10; // r9
  _QWORD *v11; // r8
  __int64 *i; // rcx
  __int64 v13; // rax
  __int64 v14; // r14
  unsigned int j; // edi
  __int64 v16; // r15
  char *v17; // rcx
  struct _RTL_CRITICAL_SECTION *v18; // rbx
  __int64 v19; // r8
  unsigned __int8 v20; // r11
  unsigned __int8 v21; // bl
  unsigned __int8 v22; // di
  unsigned __int8 v23; // si
  unsigned __int8 v24; // r14
  unsigned __int8 v25; // r15
  unsigned __int8 v26; // r12
  unsigned __int8 v27; // r13
  unsigned __int16 Data3; // r10
  unsigned __int16 Data2; // dx
  unsigned int Data1; // ecx
  __int64 *v31; // rax
  __int64 v32; // rax
  __int64 v33; // r9
  __int64 v34; // rbx
  int v35; // eax
  __int64 v36; // rdi
  int v37; // eax
  const wchar_t *v38; // r9
  IndexerSemanticSearchServicesImpl *v39; // rbx
  RTL_SRWLOCK *v40; // rsi
  char *v41; // rbx
  struct _RTL_CRITICAL_SECTION *v42; // rbx
  int matched; // esi
  struct _RTL_CRITICAL_SECTION *v44; // rbx
  int v45; // eax
  unsigned int v46; // esi
  void *v47; // rbx
  const char *v48; // r9
  __int64 result; // rax
  _DWORD *v50; // rbx
  struct _RTL_CRITICAL_SECTION *v51; // rsi
  void *v52; // rbx
  char v53[8]; // [rsp+30h] [rbp-108h] BYREF
  char *v54; // [rsp+38h] [rbp-100h] BYREF
  _QWORD v55[2]; // [rsp+40h] [rbp-F8h] BYREF
  struct _GUID *v56; // [rsp+50h] [rbp-E8h] BYREF
  unsigned __int8 v57; // [rsp+58h] [rbp-E0h]
  unsigned __int8 v58; // [rsp+59h] [rbp-DFh]
  unsigned __int8 v59; // [rsp+5Ah] [rbp-DEh]
  unsigned __int8 v60; // [rsp+5Bh] [rbp-DDh]
  unsigned __int8 v61; // [rsp+5Ch] [rbp-DCh]
  unsigned __int8 v62; // [rsp+5Dh] [rbp-DBh]
  unsigned __int8 v63; // [rsp+5Eh] [rbp-DAh]
  unsigned __int8 v64; // [rsp+5Fh] [rbp-D9h]
  int v65[2]; // [rsp+60h] [rbp-D8h] BYREF
  __int128 v66; // [rsp+68h] [rbp-D0h] BYREF
  __int64 v67; // [rsp+78h] [rbp-C0h]
  int v68; // [rsp+80h] [rbp-B8h] BYREF
  __int128 v69; // [rsp+88h] [rbp-B0h]
  char v70[8]; // [rsp+A0h] [rbp-98h] BYREF
  _BYTE v71[48]; // [rsp+A8h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+D8h] [rbp-60h]
  char v73; // [rsp+E0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v5 = a3;
  v56 = a2;
  v6 = this;
  v55[0] = this;
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
    (const wchar_t *)0x838,
    (unsigned int)L"AddItemsForId : itemCount: %lu",
    (const wchar_t *)a3);
  try
  {
    v66 = 0;
    v67 = 0;
    if ( (_DWORD)v5 )
    {
      v7 = 8 * v5;
      if ( 8 * v5 )
      {
        if ( v7 < 0x1000 )
        {
          v8 = operator new(v7);
        }
        else
        {
          if ( v7 + 39 < v7 )
            __scrt_throw_std_bad_array_new_length();
          v9 = operator new(v7 + 39);
          if ( !v9 )
            __fastfail(5u);
          v8 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *(v8 - 1) = v9;
        }
      }
      else
      {
        v8 = 0;
      }
      v10 = (__int64 *)*((_QWORD *)&v66 + 1);
      v11 = v8;
      for ( i = (__int64 *)v66; i != v10; ++i )
      {
        v13 = *i;
        *i = 0;
        *v11++ = v13;
      }
      std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>::_Change_array(&v66, v8, 0, v5);
    }
    v14 = 0;
    for ( j = 0; j < (unsigned int)v5; ++j )
    {
      anonymous_namespace_::to_winrt_embedding(
        (gsl::details *)&v54,
        *((_QWORD *)v6 + 9),
        (_QWORD *)v6 + 7,
        (__int64)a4 + 48 * j);
      v16 = (unsigned int)winrt::impl::consume_Microsoft_Windows_SemanticSearch_IEmbedding<winrt::Microsoft::Windows::SemanticSearch::IEmbedding>::ByteLength(&v54);
      if ( *((_QWORD *)&v66 + 1) == v67 )
      {
        std::vector<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtension>::_Emplace_reallocate<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtension>(
          &v66,
          *((_QWORD *)&v66 + 1),
          &v54);
      }
      else
      {
        v17 = v54;
        v54 = 0;
        **((_QWORD **)&v66 + 1) = v17;
        *((_QWORD *)&v66 + 1) += 8LL;
      }
      v14 += v16;
      if ( v54 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v54);
      v6 = (IndexerSemanticStore *)v55[0];
    }
    SemanticSearchTelemetryAggregated::ReportSemanticVectorSize(v14, v5);
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(v70);
    v18 = (struct _RTL_CRITICAL_SECTION *)pv;
    *(_QWORD *)v65 = pv;
    if ( pv )
      _InterlockedIncrement((volatile signed __int32 *)pv + 72);
    EnterCriticalSection(v18 + 5);
    ++LODWORD(v18[6].DebugInfo);
    LODWORD(v18[6].SpinCount) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(v65);
    v19 = (__int64)(*((_QWORD *)&v66 + 1) - v66) >> 3;
    v20 = v56->Data4[0];
    v21 = v56->Data4[1];
    v22 = v56->Data4[2];
    v23 = v56->Data4[3];
    v24 = v56->Data4[4];
    v25 = v56->Data4[5];
    v26 = v56->Data4[6];
    v27 = v56->Data4[7];
    Data3 = v56->Data3;
    Data2 = v56->Data2;
    Data1 = v56->Data1;
    *(_QWORD *)v65 = 0;
    v31 = *(__int64 **)(v55[0] + 32LL);
    v68 = 0;
    v69 = 0;
    v32 = *v31;
    v33 = 8;
    if ( (_DWORD)v19 )
      v33 = v66;
    LODWORD(v56) = Data1;
    WORD2(v56) = Data2;
    HIWORD(v56) = Data3;
    v57 = v20;
    v58 = v21;
    v59 = v22;
    v60 = v23;
    v61 = v24;
    v62 = v25;
    v63 = v26;
    v64 = v27;
    v34 = v55[0];
    v35 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID **, __int64, __int64))(v32 + 120))(
            *(_QWORD *)(v55[0] + 32LL),
            &v56,
            v19,
            v33);
    if ( v35 < 0 )
      winrt::throw_hresult((unsigned int)v35, &v68);
    v36 = *(_QWORD *)v65;
    v55[0] = *(_QWORD *)v65;
    v53[0] = 0;
    v68 = 0;
    v69 = 0;
    v37 = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)v65 + 48LL))(*(_QWORD *)v65, v53);
    if ( v37 < 0 )
      winrt::throw_hresult((unsigned int)v37, &v68);
    if ( v53[0] )
    {
      v50 = pv;
      v51 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      v50[18] |= 0x300u;
      if ( *((_QWORD *)v50 + 31) )
        tip2::details::shared_data<0,0,0>::complete_helper(v50 + 2, 2);
      if ( v51 )
        LeaveCriticalSection(v51);
      if ( v36 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v55);
      v52 = pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v52);
        CoTaskMemFree(v52);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v71);
      std::vector<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtension>::_Tidy(&v66);
      result = 0;
    }
    else
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52491438>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_52491438>::GetImpl'::`2'::impl) )
      {
        if ( (unsigned int)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(v55) == 108 )
        {
          SearchIndexerTrace::Error(
            (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
            (const wchar_t *)0x852,
            (unsigned int)L"AddItemsForId : Failed to add embeddings to semantic index because of vector space mismatch",
            v38);
          if ( (unsigned int)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(v34 + 32) )
          {
            if ( (unsigned int)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(v34 + 32) == 1 )
              IndexerSemanticSearchServicesImpl::ResetImageEmbeddingGenerators(g_singletonIndexerSemanticSearchServices);
          }
          else
          {
            v39 = g_singletonIndexerSemanticSearchServices;
            LODWORD(v54) = 1;
            v40 = *(RTL_SRWLOCK **)std::unordered_map<enum AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](
                                     (char *)g_singletonIndexerSemanticSearchServices + 32,
                                     &v54);
            AcquireSRWLockExclusive(v40);
            v41 = (char *)v39 + 104;
            if ( v41 != &v73 )
            {
              if ( *(_QWORD *)v41 )
                winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v41);
              *(_QWORD *)v41 = 0;
            }
            if ( v40 )
              ReleaseSRWLockExclusive(v40);
          }
        }
        else if ( (unsigned int)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(v55) == 105 )
        {
          v42 = (struct _RTL_CRITICAL_SECTION *)pv;
          v56 = (struct _GUID *)pv;
          if ( pv )
          {
            _InterlockedIncrement((volatile signed __int32 *)pv + 72);
            v36 = *(_QWORD *)v65;
          }
          EnterCriticalSection(v42 + 5);
          ++LODWORD(v42[6].DebugInfo);
          BYTE5(v42[6].SpinCount) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v56);
        }
      }
      matched = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(v55);
      v44 = (struct _RTL_CRITICAL_SECTION *)pv;
      v56 = (struct _GUID *)pv;
      if ( pv )
      {
        _InterlockedIncrement((volatile signed __int32 *)pv + 72);
        v36 = *(_QWORD *)v65;
      }
      EnterCriticalSection(v44 + 5);
      ++LODWORD(v44[6].DebugInfo);
      LODWORD(v44[7].DebugInfo) = matched;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v56);
      LODWORD(v54) = 0;
      v68 = 0;
      v69 = 0;
      v45 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v36 + 64LL))(v36, &v54);
      if ( v45 < 0 )
        winrt::throw_hresult((unsigned int)v45, &v68);
      v46 = (unsigned int)v54;
      if ( (int)v54 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x868,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
          (const char *)(unsigned int)v54,
          (int)v65);
      if ( v36 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v55);
      v47 = pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v47);
        CoTaskMemFree(v47);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v71);
      std::vector<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtension>::_Tidy(&v66);
      result = v46;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x86E,
                           (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
                           v48);
  }
  return result;
}

```

## disassembly

```asm
0x180033500  push    rbx
0x180033502  push    rsi
0x180033503  push    rdi
0x180033504  push    r12
0x180033506  push    r13
0x180033508  push    r14
0x18003350a  push    r15
0x18003350c  sub     rsp, 100h
0x180033513  mov     r12, r9
0x180033516  mov     esi, r8d
0x180033519  mov     [rsp+138h+var_E8], rdx
0x18003351e  mov     r15, rcx
0x180033521  mov     [rsp+138h+var_F8], rcx
0x180033526  xor     r13d, r13d
0x180033529  mov     r9d, esi; wchar_t *
0x18003352c  lea     r8, aAdditemsforidI; "AddItemsForId : itemCount: %lu"
0x180033533  mov     edx, 838h; wchar_t *
0x180033538  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x18003353f  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180033544  xorps   xmm0, xmm0
0x180033547  movdqu  [rsp+138h+var_D0], xmm0
0x18003354d  mov     [rsp+138h+var_C0], r13
0x180033552  test    esi, esi
0x180033554  jz      loc_1800335F7
0x18003355a  mov     rax, 1FFFFFFFFFFFFFFFh
0x180033564  cmp     rsi, rax
0x180033567  ja      loc_180033AC9
0x18003356d  lea     rcx, ds:0[rsi*8]; Size
0x180033575  test    rcx, rcx
0x180033578  jnz     short loc_18003357F
0x18003357a  mov     rdx, r13
0x18003357d  jmp     short loc_1800335BD
0x18003357f  cmp     rcx, 1000h
0x180033586  jb      short loc_1800335B5
0x180033588  lea     rax, [rcx+27h]
0x18003358c  cmp     rax, rcx
0x18003358f  jbe     loc_180033ACE
0x180033595  mov     rcx, rax; Size
0x180033598  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003359d  test    rax, rax
0x1800335a0  jnz     short loc_1800335A7
0x1800335a2  lea     ecx, [rax+5]
0x1800335a5  int     29h; Win8: RtlFailFast(ecx)
0x1800335a7  lea     rdx, [rax+27h]
0x1800335ab  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800335af  mov     [rdx-8], rax
0x1800335b3  jmp     short loc_1800335BD
0x1800335b5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800335ba  mov     rdx, rax
0x1800335bd  mov     r9, qword ptr [rsp+138h+var_D0+8]
0x1800335c2  mov     r8, rdx
0x1800335c5  mov     rcx, qword ptr [rsp+138h+var_D0]
0x1800335ca  mov     ebx, 8
0x1800335cf  cmp     rcx, r9
0x1800335d2  jz      short loc_1800335E5
0x1800335d4  mov     rax, [rcx]
0x1800335d7  mov     [rcx], r13
0x1800335da  mov     [r8], rax
0x1800335dd  add     r8, rbx
0x1800335e0  add     rcx, rbx
0x1800335e3  jmp     short loc_1800335CF
0x1800335e5  mov     r9, rsi
0x1800335e8  xor     r8d, r8d
0x1800335eb  lea     rcx, [rsp+138h+var_D0]
0x1800335f0  call    ?_Change_array@?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@AEAAXQEAUEmbedding@SemanticSearch@Windows@Microsoft@winrt@@_K1@Z; std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>::_Change_array(winrt::Microsoft::Windows::SemanticSearch::Embedding * const,unsigned __int64,unsigned __int64)
0x1800335f5  jmp     short loc_1800335FC
0x1800335f7  mov     ebx, 8
0x1800335fc  mov     r14, r13
0x1800335ff  mov     edi, r13d
0x180033602  cmp     edi, esi
0x180033604  jnb     short loc_180033680
0x180033606  mov     eax, edi
0x180033608  lea     r9, [rax+rax*2]
0x18003360c  shl     r9, 4
0x180033610  add     r9, r12
0x180033613  lea     r8, [r15+38h]
0x180033617  mov     rdx, [r15+48h]
0x18003361b  lea     rcx, [rsp+138h+var_100]
0x180033620  call    _anonymous_namespace___to_winrt_embedding
0x180033625  nop
0x180033626  lea     rcx, [rsp+138h+var_100]
0x18003362b  call    ?ByteLength@?$consume_Microsoft_Windows_SemanticSearch_IEmbedding@UIEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_SemanticSearch_IEmbedding<winrt::Microsoft::Windows::SemanticSearch::IEmbedding>::ByteLength(void)
0x180033630  mov     r15d, eax
0x180033633  mov     rdx, qword ptr [rsp+138h+var_D0+8]
0x180033638  cmp     rdx, [rsp+138h+var_C0]
0x18003363d  jz      short loc_180033653
0x18003363f  mov     rcx, [rsp+138h+var_100]
0x180033644  mov     [rsp+138h+var_100], r13
0x180033649  mov     [rdx], rcx
0x18003364c  add     qword ptr [rsp+138h+var_D0+8], rbx
0x180033651  jmp     short loc_180033663
0x180033653  lea     r8, [rsp+138h+var_100]
0x180033658  lea     rcx, [rsp+138h+var_D0]
0x18003365d  call    ??$_Emplace_reallocate@UPackageExtension@PackageExtensions@ApplicationModel@Windows@winrt@@@?$vector@UPackageExtension@PackageExtensions@ApplicationModel@Windows@winrt@@V?$allocator@UPackageExtension@PackageExtensions@ApplicationModel@Windows@winrt@@@std@@@std@@AEAAPEAUPackageExtension@PackageExtensions@ApplicationModel@Windows@winrt@@QEAU23456@$$QEAU23456@@Z; std::vector<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtension>::_Emplace_reallocate<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtension>(winrt::Windows::ApplicationModel::PackageExtensions::PackageExtension * const,winrt::Windows::ApplicationModel::PackageExtensions::PackageExtension &&)
0x180033662  nop
0x180033663  add     r14, r15
0x180033666  cmp     [rsp+138h+var_100], r13
0x18003366b  jz      short loc_180033677
0x18003366d  lea     rcx, [rsp+138h+var_100]
0x180033672  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180033677  inc     edi
0x180033679  mov     r15, [rsp+138h+var_F8]
0x18003367e  jmp     short loc_180033602
0x180033680  mov     edx, esi; unsigned int
0x180033682  mov     rcx, r14; __int64
0x180033685  call    ?ReportSemanticVectorSize@SemanticSearchTelemetryAggregated@@SAX_JI@Z; SemanticSearchTelemetryAggregated::ReportSemanticVectorSize(__int64,uint)
0x18003368a  lea     rcx, [rsp+138h+var_98]
0x180033692  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180033697  nop
0x180033698  mov     rbx, [rsp+138h+pv]
0x1800336a0  mov     qword ptr [rsp+138h+var_D8], rbx
0x1800336a5  test    rbx, rbx
0x1800336a8  jz      short loc_1800336B1
0x1800336aa  lock inc dword ptr [rbx+120h]
0x1800336b1  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800336b8  call    cs:__imp_EnterCriticalSection
0x1800336be  inc     dword ptr [rbx+0F0h]
0x1800336c4  mov     dword ptr [rbx+110h], 1
0x1800336ce  lea     rcx, [rsp+138h+var_D8]
0x1800336d3  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x1800336d8  mov     r8, qword ptr [rsp+138h+var_D0+8]
0x1800336dd  sub     r8, qword ptr [rsp+138h+var_D0]
0x1800336e2  sar     r8, 3
0x1800336e6  mov     rax, [rsp+138h+var_E8]
0x1800336eb  mov     r11b, [rax+8]
0x1800336ef  mov     bl, [rax+9]
0x1800336f2  mov     dil, [rax+0Ah]
0x1800336f6  mov     sil, [rax+0Bh]
0x1800336fa  mov     r14b, [rax+0Ch]
0x1800336fe  mov     r15b, [rax+0Dh]
0x180033702  mov     r12b, [rax+0Eh]
0x180033706  mov     r13b, [rax+0Fh]
0x18003370a  movzx   r10d, word ptr [rax+6]
0x18003370f  movzx   edx, word ptr [rax+4]
0x180033713  mov     ecx, [rax]
0x180033715  mov     qword ptr [rsp+138h+var_D8], 0
0x18003371e  mov     rax, [rsp+138h+var_F8]
0x180033723  mov     rax, [rax+20h]
0x180033727  mov     [rsp+138h+var_B8], 0
0x180033732  xorps   xmm0, xmm0
0x180033735  movdqu  [rsp+138h+var_B0], xmm0
0x18003373e  mov     rax, [rax]
0x180033741  test    r8d, r8d
0x180033744  mov     r9d, 8
0x18003374a  cmovnz  r9, qword ptr [rsp+138h+var_D0]
0x180033750  mov     dword ptr [rsp+138h+var_E8], ecx
0x180033754  mov     word ptr [rsp+138h+var_E8+4], dx
0x180033759  mov     word ptr [rsp+138h+var_E8+6], r10w
0x18003375f  mov     [rsp+138h+var_E0], r11b
0x180033764  mov     [rsp+138h+var_DF], bl
0x180033768  mov     [rsp+138h+var_DE], dil
0x18003376d  mov     [rsp+138h+var_DD], sil
0x180033772  mov     [rsp+138h+var_DC], r14b
0x180033777  mov     [rsp+138h+var_DB], r15b
0x18003377c  mov     [rsp+138h+var_DA], r12b
0x180033781  mov     [rsp+138h+var_D9], r13b
0x180033786  lea     rcx, [rsp+138h+var_D8]
0x18003378b  mov     qword ptr [rsp+138h+var_118], rcx; int
0x180033790  lea     rdx, [rsp+138h+var_E8]
0x180033795  mov     rbx, [rsp+138h+var_F8]
0x18003379a  mov     rcx, [rbx+20h]
0x18003379e  mov     rax, [rax+78h]
0x1800337a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337a7  xor     r14d, r14d
0x1800337aa  test    eax, eax
0x1800337ac  js      loc_180033AD4
0x1800337b2  mov     rdi, qword ptr [rsp+138h+var_D8]
0x1800337b7  mov     [rsp+138h+var_F8], rdi
0x1800337bc  mov     [rsp+138h+var_108], r14b
0x1800337c1  mov     [rsp+138h+var_B8], r14d
0x1800337c9  xorps   xmm0, xmm0
0x1800337cc  movdqu  [rsp+138h+var_B0], xmm0
0x1800337d5  mov     rax, [rdi]
0x1800337d8  lea     rdx, [rsp+138h+var_108]
0x1800337dd  mov     rcx, rdi
0x1800337e0  mov     rax, [rax+30h]
0x1800337e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337e9  test    eax, eax
0x1800337eb  js      loc_180033AE4
0x1800337f1  cmp     [rsp+138h+var_108], r14b
0x1800337f6  jnz     loc_180033A13
0x1800337fc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_52491438@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_52491438@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52491438> `wil::Feature<__WilFeatureTraits_Feature_52491438>::GetImpl(void)'::`2'::impl
0x180033803  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_52491438@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52491438>::__private_IsEnabled(void)
0x180033808  test    al, al
0x18003380a  jz      loc_18003390F
0x180033810  lea     rcx, [rsp+138h+var_F8]
0x180033815  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x18003381a  cmp     eax, 6Ch ; 'l'
0x18003381d  jnz     loc_1800338BE
0x180033823  lea     r8, aAdditemsforidF; "AddItemsForId : Failed to add embedding"...
0x18003382a  mov     edx, 852h; wchar_t *
0x18003382f  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180033836  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18003383b  lea     rcx, [rbx+20h]
0x18003383f  call    ?Size@?$consume_Windows_Indexer_SemanticSearch_ISparseBitIds@UISparseBitIds@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(void)
0x180033844  test    eax, eax
0x180033846  jnz     short loc_1800338A2
0x180033848  mov     rbx, cs:?g_singletonIndexerSemanticSearchServices@@3U?$com_ptr@UIndexerSemanticSearchServicesImpl@@@winrt@@A; winrt::com_ptr<IndexerSemanticSearchServicesImpl> g_singletonIndexerSemanticSearchServices
0x18003384f  mov     dword ptr [rsp+138h+var_100], 1
0x180033857  lea     rcx, [rbx+20h]
0x18003385b  lea     rdx, [rsp+138h+var_100]
0x180033860  call    ??A?$unordered_map@W4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@U?$hash@W4AIFabric_Component@@@3@U?$equal_to@W4AIFabric_Component@@@3@V?$allocator@U?$pair@$$CBW4AIFabric_Component@@V?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@std@@@std@@@3@@std@@QEAAAEAV?$unique_ptr@Vsrwlock@wil@@U?$default_delete@Vsrwlock@wil@@@std@@@1@$$QEAW4AIFabric_Component@@@Z; std::unordered_map<AIFabric_Component,std::unique_ptr<wil::srwlock>>::operator[](AIFabric_Component &&)
0x180033865  mov     rsi, [rax]
0x180033868  mov     rcx, rsi; SRWLock
0x18003386b  call    cs:__imp_AcquireSRWLockExclusive
0x180033871  add     rbx, 68h ; 'h'
0x180033875  lea     rax, [rsp+138h+var_58]
0x18003387d  cmp     rbx, rax
0x180033880  jz      short loc_180033892
0x180033882  cmp     [rbx], r14
0x180033885  jz      short loc_18003388F
0x180033887  mov     rcx, rbx
0x18003388a  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003388f  mov     [rbx], r14
0x180033892  test    rsi, rsi
0x180033895  jz      short loc_18003390F
0x180033897  mov     rcx, rsi; SRWLock
0x18003389a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800338a0  jmp     short loc_18003390F
0x1800338a2  lea     rcx, [rbx+20h]
0x1800338a6  call    ?Size@?$consume_Windows_Indexer_SemanticSearch_ISparseBitIds@UISparseBitIds@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISparseBitIds<winrt::Windows::Indexer::SemanticSearch::ISparseBitIds>::Size(void)
0x1800338ab  cmp     eax, 1
0x1800338ae  jnz     short loc_18003390F
0x1800338b0  mov     rcx, cs:?g_singletonIndexerSemanticSearchServices@@3U?$com_ptr@UIndexerSemanticSearchServicesImpl@@@winrt@@A; this
0x1800338b7  call    ?ResetImageEmbeddingGenerators@IndexerSemanticSearchServicesImpl@@QEAAXXZ; IndexerSemanticSearchServicesImpl::ResetImageEmbeddingGenerators(void)
0x1800338bc  jmp     short loc_18003390F
0x1800338be  lea     rcx, [rsp+138h+var_F8]
0x1800338c3  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x1800338c8  cmp     eax, 69h ; 'i'
0x1800338cb  jnz     short loc_18003390F
0x1800338cd  mov     rbx, [rsp+138h+pv]
0x1800338d5  mov     [rsp+138h+var_E8], rbx
0x1800338da  test    rbx, rbx
0x1800338dd  jz      short loc_1800338EB
0x1800338df  lock inc dword ptr [rbx+120h]
0x1800338e6  mov     rdi, qword ptr [rsp+138h+var_D8]
0x1800338eb  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800338f2  call    cs:__imp_EnterCriticalSection
0x1800338f8  inc     dword ptr [rbx+0F0h]
0x1800338fe  mov     byte ptr [rbx+115h], 1
0x180033905  lea     rcx, [rsp+138h+var_E8]
0x18003390a  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003390f  lea     rcx, [rsp+138h+var_F8]
0x180033914  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x180033919  mov     esi, eax
0x18003391b  mov     rbx, [rsp+138h+pv]
0x180033923  mov     [rsp+138h+var_E8], rbx
0x180033928  test    rbx, rbx
0x18003392b  jz      short loc_180033939
0x18003392d  lock inc dword ptr [rbx+120h]
0x180033934  mov     rdi, qword ptr [rsp+138h+var_D8]
0x180033939  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180033940  call    cs:__imp_EnterCriticalSection
0x180033946  inc     dword ptr [rbx+0F0h]
0x18003394c  mov     [rbx+118h], esi
0x180033952  lea     rcx, [rsp+138h+var_E8]
0x180033957  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003395c  mov     dword ptr [rsp+138h+var_100], r14d
0x180033961  mov     [rsp+138h+var_B8], r14d
0x180033969  xorps   xmm0, xmm0
0x18003396c  movdqu  [rsp+138h+var_B0], xmm0
0x180033975  mov     rax, [rdi]
0x180033978  lea     rdx, [rsp+138h+var_100]
0x18003397d  mov     rcx, rdi
0x180033980  mov     rax, [rax+40h]
0x180033984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033989  test    eax, eax
0x18003398b  js      loc_180033AF3
0x180033991  mov     esi, dword ptr [rsp+138h+var_100]
0x180033995  test    esi, esi
0x180033997  jns     short loc_1800339B6
0x180033999  mov     rcx, [rsp+138h]; this
0x1800339a1  mov     r9d, esi; char *
0x1800339a4  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800339ab  mov     edx, 868h; void *
0x1800339b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800339b5  nop
0x1800339b6  test    rdi, rdi
0x1800339b9  jz      short loc_1800339C6
0x1800339bb  lea     rcx, [rsp+138h+var_F8]
0x1800339c0  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800339c5  nop
0x1800339c6  mov     rbx, [rsp+138h+pv]
0x1800339ce  test    rbx, rbx
0x1800339d1  jz      short loc_1800339F4
0x1800339d3  or      edx, 0FFFFFFFFh
0x1800339d6  lock xadd [rbx+120h], edx
0x1800339de  cmp     edx, 1
0x1800339e1  jnz     short loc_1800339F4
0x1800339e3  mov     rcx, rbx
0x1800339e6  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x1800339eb  mov     rcx, rbx; pv
0x1800339ee  call    cs:__imp_CoTaskMemFree
0x1800339f4  lea     rcx, [rsp+138h+var_90]; this
0x1800339fc  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180033a01  nop
0x180033a02  lea     rcx, [rsp+138h+var_D0]
0x180033a07  call    ?_Tidy@?$vector@UPackageExtension@PackageExtensions@ApplicationModel@Windows@winrt@@V?$allocator@UPackageExtension@PackageExtensions@ApplicationModel@Windows@winrt@@@std@@@std@@AEAAXXZ; std::vector<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtension>::_Tidy(void)
0x180033a0c  mov     eax, esi
0x180033a0e  jmp     loc_180033AB6
  ... truncated ...
```
