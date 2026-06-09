# IndexerSemanticStore::FindMatchesFromTextInternal(ulong,wchar_t const *,winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions const &,ulong *,tagSemanticMatch * *)

- ea: `0x180037488`
- end: `0x18003792a`
- name: `?FindMatchesFromTextInternal@IndexerSemanticStore@@AEAAJKPEB_WAEBUSemanticQueryOptions@SemanticSearch@Windows@Microsoft@winrt@@PEAKPEAPEAUtagSemanticMatch@@@Z`
- size: `1186`
- prototype: `int(IndexerSemanticStore *__hidden this, unsigned int, const wchar_t *, const struct winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions *, unsigned int *, struct tagSemanticMatch **)`
- caller_count: `2`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037420`
- `0x180037930`

## callees

- `0x1800058cb`
- `0x18000591f`
- `0x18000b064`
- `0x18000c350`
- `0x18000c478`
- `0x18000c634`
- `0x180015f90`
- `0x180021290`
- `0x180022760`
- `0x180028c20`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x1800373cc`
- `0x180037488`
- `0x180047404`
- `0x180048248`
- `0x180048310`
- `0x18004d9c4`
- `0x18004dea8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800376c1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800377bc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800376c1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800377bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800378a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800378a2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037500`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003755b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037668`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037705`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037876`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037500`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003755b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037668`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037705`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037876`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003783d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800378ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003783d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800378ec`

## string_xrefs

- `0x1800374b2`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x1800376a8`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x1800377e4`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180037803`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IndexerSemanticStore::FindMatchesFromTextInternal(
        IndexerSemanticStore *this,
        unsigned int a2,
        const wchar_t *a3,
        const wchar_t *a4,
        unsigned int *a5,
        struct tagSemanticMatch **a6)
{
  __int64 v8; // rsi
  __int64 v10; // rdi
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  unsigned int v12; // edx
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  struct winrt::impl::shared_hstring_header *v14; // rbx
  __int64 *v15; // rax
  int v16; // eax
  HANDLE ProcessHeap; // rax
  int matched; // esi
  struct _RTL_CRITICAL_SECTION *v19; // rbx
  unsigned int v20; // edx
  struct _RTL_CRITICAL_SECTION *v21; // rbx
  __int64 *v22; // rax
  int v23; // eax
  int v24; // ebx
  unsigned int v25; // eax
  unsigned int v26; // esi
  struct _RTL_CRITICAL_SECTION *v27; // rbx
  const char *v28; // r9
  __int64 result; // rax
  _DWORD *v30; // rbx
  struct _RTL_CRITICAL_SECTION *v31; // rdi
  IndexerSemanticStore *v32; // rcx
  unsigned int v33; // edi
  struct _RTL_CRITICAL_SECTION *v34; // rbx
  int v35; // [rsp+20h] [rbp-C8h]
  LPVOID v36; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v37; // [rsp+38h] [rbp-B0h] BYREF
  wchar_t *v38; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v39[8]; // [rsp+50h] [rbp-98h] BYREF
  _BYTE v40[48]; // [rsp+58h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-60h]
  _QWORD v42[11]; // [rsp+90h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v8 = a2;
  SearchIndexerTrace::Information(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
    (const wchar_t *)0xAF2,
    (unsigned int)L"FindMatchesFromTextInternal : Started",
    a4);
  v10 = 0;
  v37 = 0;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v39);
  try
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
    {
      v11 = (struct _RTL_CRITICAL_SECTION *)pv;
      v36 = pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 72);
      EnterCriticalSection(v11 + 5);
      ++LODWORD(v11[6].DebugInfo);
      LODWORD(v11[6].SpinCount) = 17;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v36);
    }
    if ( *((_QWORD *)this + 5) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
      {
        v13 = (struct _RTL_CRITICAL_SECTION *)pv;
        v36 = pv;
        if ( pv )
          _InterlockedIncrement((volatile signed __int32 *)pv + 72);
        EnterCriticalSection(v13 + 5);
        ++LODWORD(v13[6].DebugInfo);
        LODWORD(v13[6].SpinCount) = 42;
        tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v36);
      }
      if ( (_DWORD)v8 )
      {
        v14 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v8, v12);
        memcpy_s((char *)v14 + 28, 2 * v8, a3, 2 * v8);
      }
      else
      {
        v14 = 0;
      }
      v38 = (wchar_t *)v14;
      v42[0] = v14;
      v15 = (__int64 *)winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndex<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>::QueryText(
                         (char *)this + 40,
                         &v36,
                         v42,
                         a4);
      if ( &v37 != v15 )
      {
        v10 = *v15;
        *v15 = 0;
        v37 = v10;
      }
      if ( v36 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v36);
      if ( !v14 )
        goto LABEL_21;
      v16 = _InterlockedDecrement((volatile signed __int32 *)v14 + 6);
      if ( v16 )
      {
        if ( v16 < 0 )
          abort();
        goto LABEL_21;
      }
    }
    else
    {
      if ( !*((_QWORD *)this + 6) )
        goto LABEL_21;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
      {
        v21 = (struct _RTL_CRITICAL_SECTION *)pv;
        v36 = pv;
        if ( pv )
          _InterlockedIncrement((volatile signed __int32 *)pv + 72);
        EnterCriticalSection(v21 + 5);
        ++LODWORD(v21[6].DebugInfo);
        LODWORD(v21[6].SpinCount) = 43;
        tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v36);
      }
      if ( (_DWORD)v8 )
      {
        v14 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v8, v20);
        memcpy_s((char *)v14 + 28, 2 * v8, a3, 2 * v8);
      }
      else
      {
        v14 = 0;
      }
      v38 = (wchar_t *)v14;
      v42[0] = v14;
      v22 = (__int64 *)winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticImageIndex<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>::QueryText(
                         (char *)this + 48,
                         &v36,
                         v42,
                         a4);
      if ( &v37 != v22 )
      {
        v10 = *v22;
        *v22 = 0;
        v37 = v10;
      }
      if ( v36 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v36);
      if ( !v14 )
        goto LABEL_21;
      v23 = _InterlockedDecrement((volatile signed __int32 *)v14 + 6);
      if ( v23 )
      {
        if ( v23 < 0 )
          abort();
        goto LABEL_21;
      }
    }
    ProcessHeap = WINRT_IMPL_GetProcessHeap();
    WINRT_IMPL_HeapFree(ProcessHeap, 0, v14);
LABEL_21:
    if ( (unsigned __int8)winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(&v37) )
    {
      v30 = pv;
      v31 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
      EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
      v30[18] |= 0x300u;
      if ( *((_QWORD *)v30 + 31) )
        tip2::details::shared_data<0,0,0>::complete_helper(v30 + 2, 2);
      if ( v31 )
        LeaveCriticalSection(v31);
      v33 = IndexerSemanticStore::ProcessQueryResult(
              v32,
              (const struct winrt::Microsoft::Windows::SemanticSearch::IQueryResult *)&v37,
              a5,
              a6);
      v34 = (struct _RTL_CRITICAL_SECTION *)pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v34);
        CoTaskMemFree(v34);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v40);
      if ( v37 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v37);
      result = v33;
    }
    else
    {
      winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(
        &v37,
        &v38);
      matched = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v37);
      v19 = (struct _RTL_CRITICAL_SECTION *)pv;
      v36 = pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 72);
      EnterCriticalSection(v19 + 5);
      ++LODWORD(v19[6].DebugInfo);
      LODWORD(v19[7].DebugInfo) = matched;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v36);
      if ( (unsigned int)winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v37) == 110 )
      {
        SearchIndexerTrace::Error(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
          (const wchar_t *)0xB16,
          (unsigned int)L"FindMatchesFromTextInternal : Query failed because models are not loaded hr(0x%08x)",
          (const wchar_t *)(unsigned int)v38);
      }
      else
      {
        v24 = (int)v38;
        v25 = winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(&v37);
        v35 = v24;
        SearchIndexerTrace::Error(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
          (const wchar_t *)0xB1B,
          (unsigned int)L"FindMatchesFromTextInternal : Query failed with status %lu and hr(0x%08x)",
          (const wchar_t *)v25);
      }
      v26 = (unsigned int)v38;
      if ( (int)v38 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB1D,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
          (const char *)(unsigned int)v38,
          v35);
      v27 = (struct _RTL_CRITICAL_SECTION *)pv;
      if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v27);
        CoTaskMemFree(v27);
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v40);
      if ( v10 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v37);
      result = v26;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB23,
                           (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
                           v28);
  }
  return result;
}

```

## disassembly

```asm
0x180037488  push    rbx
0x18003748a  push    rsi
0x18003748b  push    rdi
0x18003748c  push    r12
0x18003748e  push    r13
0x180037490  push    r14
0x180037492  push    r15
0x180037494  sub     rsp, 0B0h
0x18003749b  mov     r12, r9
0x18003749e  mov     r13, r8
0x1800374a1  mov     esi, edx
0x1800374a3  mov     r14, rcx
0x1800374a6  lea     r8, aFindmatchesfro_1; "FindMatchesFromTextInternal : Started"
0x1800374ad  mov     edx, 0AF2h; wchar_t *
0x1800374b2  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800374b9  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x1800374be  xor     edi, edi
0x1800374c0  mov     [rsp+0E8h+var_B0], rdi
0x1800374c5  lea     rcx, [rsp+0E8h+var_98]
0x1800374ca  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1800374cf  nop
0x1800374d0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x1800374d7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x1800374dc  test    al, al
0x1800374de  jnz     short loc_180037520
0x1800374e0  mov     rbx, [rsp+0E8h+pv]
0x1800374e8  mov     [rsp+0E8h+var_B8], rbx
0x1800374ed  test    rbx, rbx
0x1800374f0  jz      short loc_1800374F9
0x1800374f2  lock inc dword ptr [rbx+120h]
0x1800374f9  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180037500  call    cs:__imp_EnterCriticalSection
0x180037506  inc     dword ptr [rbx+0F0h]
0x18003750c  mov     dword ptr [rbx+110h], 11h
0x180037516  lea     rcx, [rsp+0E8h+var_B8]
0x18003751b  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180037520  cmp     qword ptr [r14+28h], 0
0x180037525  jz      loc_1800376C8
0x18003752b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x180037532  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x180037537  test    al, al
0x180037539  jz      short loc_18003757B
0x18003753b  mov     rbx, [rsp+0E8h+pv]
0x180037543  mov     [rsp+0E8h+var_B8], rbx
0x180037548  test    rbx, rbx
0x18003754b  jz      short loc_180037554
0x18003754d  lock inc dword ptr [rbx+120h]
0x180037554  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18003755b  call    cs:__imp_EnterCriticalSection
0x180037561  inc     dword ptr [rbx+0F0h]
0x180037567  mov     dword ptr [rbx+110h], 2Ah ; '*'
0x180037571  lea     rcx, [rsp+0E8h+var_B8]
0x180037576  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x18003757b  test    esi, esi
0x18003757d  jnz     short loc_180037583
0x18003757f  xor     ebx, ebx
0x180037581  jmp     short loc_1800375A2
0x180037583  mov     ecx, esi; this
0x180037585  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18003758a  mov     rbx, rax
0x18003758d  mov     rdx, rsi
0x180037590  add     rdx, rdx; DestinationSize
0x180037593  lea     rcx, [rax+1Ch]; Destination
0x180037597  mov     r9, rdx; SourceSize
0x18003759a  mov     r8, r13; Source
0x18003759d  call    memcpy_s
0x1800375a2  mov     [rsp+0E8h+var_A8], rbx
0x1800375a7  mov     [rsp+0E8h+var_58], rbx
0x1800375af  mov     r9, r12
0x1800375b2  lea     r8, [rsp+0E8h+var_58]
0x1800375ba  lea     rdx, [rsp+0E8h+var_B8]
0x1800375bf  lea     rcx, [r14+28h]
0x1800375c3  call    ?QueryText@?$consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndex@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUSemanticQueryOptions@SemanticSearch@Windows@Microsoft@3@@Z; winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticTextIndex<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>::QueryText(winrt::param::hstring const &,winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions const &)
0x1800375c8  lea     rcx, [rsp+0E8h+var_B0]
0x1800375cd  xor     r15d, r15d
0x1800375d0  cmp     rcx, rax
0x1800375d3  jz      short loc_1800375E0
0x1800375d5  mov     rdi, [rax]
0x1800375d8  mov     [rax], r15
0x1800375db  mov     [rsp+0E8h+var_B0], rdi
0x1800375e0  cmp     [rsp+0E8h+var_B8], r15
0x1800375e5  jz      short loc_1800375F2
0x1800375e7  lea     rcx, [rsp+0E8h+var_B8]
0x1800375ec  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800375f1  nop
0x1800375f2  test    rbx, rbx
0x1800375f5  jz      short loc_18003761B
0x1800375f7  or      eax, 0FFFFFFFFh
0x1800375fa  lock xadd [rbx+18h], eax
0x1800375ff  sub     eax, 1
0x180037602  jnz     loc_1800376B9
0x180037608  nop
0x180037609  call    WINRT_IMPL_GetProcessHeap
0x18003760e  mov     rcx, rax; hHeap
0x180037611  mov     r8, rbx; lpMem
0x180037614  xor     edx, edx; dwFlags
0x180037616  call    WINRT_IMPL_HeapFree
0x18003761b  lea     rcx, [rsp+0E8h+var_B0]
0x180037620  call    ?VerifyIsOK@?$consume_Windows_ApplicationModel_IPackageStatus@UIPackageStatus@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageStatus<winrt::Windows::ApplicationModel::IPackageStatus>::VerifyIsOK(void)
0x180037625  test    al, al
0x180037627  jnz     loc_180037864
0x18003762d  lea     rdx, [rsp+0E8h+var_A8]
0x180037632  lea     rcx, [rsp+0E8h+var_B0]
0x180037637  call    ?ExtendedError@?$consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult@UIPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageDeploymentResult<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentResult>::ExtendedError(void)
0x18003763c  lea     rcx, [rsp+0E8h+var_B0]
0x180037641  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x180037646  mov     esi, eax
0x180037648  mov     rbx, [rsp+0E8h+pv]
0x180037650  mov     [rsp+0E8h+var_B8], rbx
0x180037655  test    rbx, rbx
0x180037658  jz      short loc_180037661
0x18003765a  lock inc dword ptr [rbx+120h]
0x180037661  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180037668  call    cs:__imp_EnterCriticalSection
0x18003766e  inc     dword ptr [rbx+0F0h]
0x180037674  mov     [rbx+118h], esi
0x18003767a  lea     rcx, [rsp+0E8h+var_B8]
0x18003767f  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180037684  lea     rcx, [rsp+0E8h+var_B0]
0x180037689  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x18003768e  cmp     eax, 6Eh ; 'n'
0x180037691  jnz     loc_1800377C3
0x180037697  mov     r9d, dword ptr [rsp+0E8h+var_A8]; wchar_t *
0x18003769c  lea     r8, aFindmatchesfro_0; "FindMatchesFromTextInternal : Query fai"...
0x1800376a3  mov     edx, 0B16h; wchar_t *
0x1800376a8  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800376af  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800376b4  jmp     loc_1800377F0
0x1800376b9  test    eax, eax
0x1800376bb  jns     loc_18003761B
0x1800376c1  call    cs:__imp_abort
0x1800376c8  xor     r15d, r15d
0x1800376cb  cmp     [r14+30h], r15
0x1800376cf  jz      loc_18003761B
0x1800376d5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x1800376dc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x1800376e1  test    al, al
0x1800376e3  jz      short loc_180037725
0x1800376e5  mov     rbx, [rsp+0E8h+pv]
0x1800376ed  mov     [rsp+0E8h+var_B8], rbx
0x1800376f2  test    rbx, rbx
0x1800376f5  jz      short loc_1800376FE
0x1800376f7  lock inc dword ptr [rbx+120h]
0x1800376fe  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180037705  call    cs:__imp_EnterCriticalSection
0x18003770b  inc     dword ptr [rbx+0F0h]
0x180037711  mov     dword ptr [rbx+110h], 2Bh ; '+'
0x18003771b  lea     rcx, [rsp+0E8h+var_B8]
0x180037720  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180037725  test    esi, esi
0x180037727  jnz     short loc_18003772E
0x180037729  mov     rbx, r15
0x18003772c  jmp     short loc_18003774D
0x18003772e  mov     ecx, esi; this
0x180037730  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180037735  mov     rbx, rax
0x180037738  mov     rdx, rsi
0x18003773b  add     rdx, rdx; DestinationSize
0x18003773e  lea     rcx, [rax+1Ch]; Destination
0x180037742  mov     r9, rdx; SourceSize
0x180037745  mov     r8, r13; Source
0x180037748  call    memcpy_s
0x18003774d  mov     [rsp+0E8h+var_A8], rbx
0x180037752  mov     [rsp+0E8h+var_58], rbx
0x18003775a  mov     r9, r12
0x18003775d  lea     r8, [rsp+0E8h+var_58]
0x180037765  lea     rdx, [rsp+0E8h+var_B8]
0x18003776a  lea     rcx, [r14+30h]
0x18003776e  call    ?QueryText@?$consume_Microsoft_Windows_SemanticSearch_ISemanticImageIndex@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBUSemanticQueryOptions@SemanticSearch@Windows@Microsoft@3@@Z; winrt::impl::consume_Microsoft_Windows_SemanticSearch_ISemanticImageIndex<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore>::QueryText(winrt::param::hstring const &,winrt::Microsoft::Windows::SemanticSearch::SemanticQueryOptions const &)
0x180037773  lea     rcx, [rsp+0E8h+var_B0]
0x180037778  cmp     rcx, rax
0x18003777b  jz      short loc_180037788
0x18003777d  mov     rdi, [rax]
0x180037780  mov     [rax], r15
0x180037783  mov     [rsp+0E8h+var_B0], rdi
0x180037788  cmp     [rsp+0E8h+var_B8], r15
0x18003778d  jz      short loc_18003779A
0x18003778f  lea     rcx, [rsp+0E8h+var_B8]
0x180037794  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180037799  nop
0x18003779a  test    rbx, rbx
0x18003779d  jz      loc_18003761B
0x1800377a3  or      eax, 0FFFFFFFFh
0x1800377a6  lock xadd [rbx+18h], eax
0x1800377ab  sub     eax, 1
0x1800377ae  jz      loc_180037608
0x1800377b4  test    eax, eax
0x1800377b6  jns     loc_18003761B
0x1800377bc  call    cs:__imp_abort
0x1800377c3  mov     ebx, dword ptr [rsp+0E8h+var_A8]
0x1800377c7  lea     rcx, [rsp+0E8h+var_B0]
0x1800377cc  call    ?MaxMatchCount@?$consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters@UISemanticQueryParameters@SemanticSearch@Indexer@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Indexer_SemanticSearch_ISemanticQueryParameters<winrt::Windows::Indexer::SemanticSearch::ISemanticQueryParameters>::MaxMatchCount(void)
0x1800377d1  mov     [rsp+0E8h+var_C8], ebx; int
0x1800377d5  mov     r9d, eax; wchar_t *
0x1800377d8  lea     r8, aFindmatchesfro; "FindMatchesFromTextInternal : Query fai"...
0x1800377df  mov     edx, 0B1Bh; wchar_t *
0x1800377e4  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800377eb  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800377f0  mov     esi, dword ptr [rsp+0E8h+var_A8]
0x1800377f4  test    esi, esi
0x1800377f6  jns     short loc_180037815
0x1800377f8  mov     rcx, [rsp+0E8h]; this
0x180037800  mov     r9d, esi; char *
0x180037803  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x18003780a  mov     edx, 0B1Dh; void *
0x18003780f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037814  nop
0x180037815  mov     rbx, [rsp+0E8h+pv]
0x18003781d  test    rbx, rbx
0x180037820  jz      short loc_180037843
0x180037822  or      eax, 0FFFFFFFFh
0x180037825  lock xadd [rbx+120h], eax
0x18003782d  cmp     eax, 1
0x180037830  jnz     short loc_180037843
0x180037832  mov     rcx, rbx
0x180037835  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x18003783a  mov     rcx, rbx; pv
0x18003783d  call    cs:__imp_CoTaskMemFree
0x180037843  lea     rcx, [rsp+0E8h+var_90]; this
0x180037848  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18003784d  nop
0x18003784e  test    rdi, rdi
0x180037851  jz      short loc_18003785D
0x180037853  lea     rcx, [rsp+0E8h+var_B0]
0x180037858  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003785d  mov     eax, esi
0x18003785f  jmp     loc_180037916
0x180037864  mov     rbx, [rsp+0E8h+pv]
0x18003786c  lea     rdi, [rbx+0C8h]
0x180037873  mov     rcx, rdi; lpCriticalSection
0x180037876  call    cs:__imp_EnterCriticalSection
0x18003787c  or      dword ptr [rbx+48h], 300h
0x180037883  cmp     [rbx+0F8h], r15
0x18003788a  jz      short loc_18003789A
0x18003788c  mov     edx, 2
0x180037891  lea     rcx, [rbx+8]
0x180037895  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18003789a  test    rdi, rdi
0x18003789d  jz      short loc_1800378A8
0x18003789f  mov     rcx, rdi; lpCriticalSection
0x1800378a2  call    cs:__imp_LeaveCriticalSection
0x1800378a8  mov     r9, [rsp+0E8h+arg_28]; struct tagSemanticMatch **
0x1800378b0  mov     r8, [rsp+0E8h+arg_20]; unsigned int *
0x1800378b8  lea     rdx, [rsp+0E8h+var_B0]; struct winrt::Microsoft::Windows::SemanticSearch::IQueryResult *
0x1800378bd  call    ?ProcessQueryResult@IndexerSemanticStore@@AEAAJAEBUIQueryResult@SemanticSearch@Windows@Microsoft@winrt@@PEAKPEAPEAUtagSemanticMatch@@@Z; IndexerSemanticStore::ProcessQueryResult(winrt::Microsoft::Windows::SemanticSearch::IQueryResult const &,ulong *,tagSemanticMatch * *)
0x1800378c2  mov     edi, eax
0x1800378c4  mov     rbx, [rsp+0E8h+pv]
0x1800378cc  test    rbx, rbx
0x1800378cf  jz      short loc_1800378F2
0x1800378d1  or      edx, 0FFFFFFFFh
0x1800378d4  lock xadd [rbx+120h], edx
0x1800378dc  cmp     edx, 1
0x1800378df  jnz     short loc_1800378F2
0x1800378e1  mov     rcx, rbx
0x1800378e4  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x1800378e9  mov     rcx, rbx; pv
0x1800378ec  call    cs:__imp_CoTaskMemFree
0x1800378f2  lea     rcx, [rsp+0E8h+var_90]; this
0x1800378f7  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800378fc  nop
0x1800378fd  cmp     [rsp+0E8h+var_B0], r15
0x180037902  jz      short loc_18003790E
0x180037904  lea     rcx, [rsp+0E8h+var_B0]
0x180037909  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003790e  mov     eax, edi
0x180037910  jmp     short loc_180037916
0x180037912  mov     eax, dword ptr [rsp+0E8h+var_A8]
0x180037916  add     rsp, 0B0h
0x18003791d  pop     r15
0x18003791f  pop     r14
0x180037921  pop     r13
0x180037923  pop     r12
0x180037925  pop     rdi
0x180037926  pop     rsi
0x180037927  pop     rbx
0x180037928  retn
```
