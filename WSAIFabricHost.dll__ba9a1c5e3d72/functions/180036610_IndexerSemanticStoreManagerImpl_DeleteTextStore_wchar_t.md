# IndexerSemanticStoreManagerImpl::DeleteTextStore(wchar_t *)

- ea: `0x180036610`
- end: `0x1800368e3`
- name: `?DeleteTextStore@IndexerSemanticStoreManagerImpl@@UEAAJPEA_W@Z`
- size: `723`
- prototype: `__int64 __fastcall(IndexerSemanticStoreManagerImpl *this, wchar_t *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800058cb`
- `0x18000591f`
- `0x18000c350`
- `0x18000c634`
- `0x180015f90`
- `0x180019c3c`
- `0x18002ac60`
- `0x18002c1a4`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x180036610`
- `0x18004d924`
- `0x18004dea8`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800368bf`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800368ce`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800368bf`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800368ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036855`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036855`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036692`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036829`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036692`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036829`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036884`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036884`

## string_xrefs

- `0x18003664e`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180036642`: `DeleteTextStore: Invalid argument basePath: %p`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IndexerSemanticStoreManagerImpl::DeleteTextStore(IndexerSemanticStoreManagerImpl *this, wchar_t *a2)
{
  const char *v3; // r9
  __int64 result; // rax
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  unsigned int v6; // edx
  __int64 v7; // rbx
  struct winrt::impl::shared_hstring_header *v8; // rdi
  volatile signed __int32 *v9; // rsi
  unsigned int v10; // r14d
  const void *v11; // rbx
  int v12; // eax
  int v13; // eax
  HANDLE ProcessHeap; // rax
  int v15; // eax
  HANDLE v16; // rax
  _DWORD *v17; // rbx
  struct _RTL_CRITICAL_SECTION *v18; // rdi
  void *v19; // rbx
  int v20; // [rsp+30h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+38h] [rbp-A0h]
  volatile signed __int32 *v22; // [rsp+48h] [rbp-90h] BYREF
  _BYTE v23[8]; // [rsp+70h] [rbp-68h] BYREF
  _BYTE v24[48]; // [rsp+78h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  _QWORD *v27; // [rsp+F0h] [rbp+18h] BYREF
  struct winrt::impl::shared_hstring_header *v28; // [rsp+F8h] [rbp+20h]

  try
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NullCheck>::__private_IsEnabled() && !a2 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
        (const wchar_t *)0xBBE,
        (unsigned int)L"DeleteTextStore: Invalid argument basePath: %p",
        0);
      return 2147500035LL;
    }
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>(v23);
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    v27 = pv;
    if ( pv )
      _InterlockedIncrement((volatile signed __int32 *)pv + 72);
    EnterCriticalSection(v5 + 5);
    ++LODWORD(v5[6].DebugInfo);
    LODWORD(v5[6].SpinCount) = 12;
    tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v27);
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    if ( (_DWORD)v7 )
    {
      v8 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v7, v6);
      memcpy_s((char *)v8 + 28, 2LL * (unsigned int)v7, a2, 2LL * (unsigned int)v7);
    }
    else
    {
      v8 = 0;
    }
    v28 = v8;
    if ( v8 )
    {
      if ( (*(_BYTE *)v8 & 1) == 0 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v8 + 6);
        v9 = (volatile signed __int32 *)v8;
        goto LABEL_18;
      }
      v10 = *((_DWORD *)v8 + 1);
      if ( v10 )
      {
        v11 = (const void *)*((_QWORD *)v8 + 2);
        v9 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)v10, v6);
        memcpy_s((void *const)(v9 + 7), 2LL * v10, v11, 2LL * v10);
        goto LABEL_18;
      }
    }
    v9 = 0;
LABEL_18:
    v22 = v9;
    v27 = &v22;
    _InterlockedIncrement64(&qword_1800AF6D8);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> )
    {
      v20 = 0;
      v21 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>
                                                                          + 120LL))(
              winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>,
              v22);
      if ( v12 < 0 )
        winrt::throw_hresult((unsigned int)v12, &v20);
      _InterlockedAdd64(&qword_1800AF6D8, 0xFFFFFFFFFFFFFFFFuLL);
    }
    else
    {
      _InterlockedAdd64(&qword_1800AF6D8, 0xFFFFFFFFFFFFFFFFuLL);
      winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>::call<_lambda_0ab8bf830596d857883e5c1e5d73dc8a_ &>(
        0,
        &v27);
    }
    if ( v9 )
    {
      v13 = _InterlockedDecrement(v9 + 6);
      if ( v13 )
      {
        if ( v13 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v9);
      }
    }
    if ( v8 )
    {
      v15 = _InterlockedDecrement((volatile signed __int32 *)v8 + 6);
      if ( v15 )
      {
        if ( v15 < 0 )
          abort();
      }
      else
      {
        v16 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v16, 0, v8);
      }
    }
    SemanticSearchTelemetry::SemanticIndexStoreDeleted<wchar_t * const &>(off_18008BE80);
    v17 = pv;
    v18 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    v17[18] |= 0x300u;
    if ( *((_QWORD *)v17 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper(v17 + 2, 2);
    if ( v18 )
      LeaveCriticalSection(v18);
    v19 = pv;
    if ( pv && !_InterlockedDecrement((volatile signed __int32 *)pv + 72) )
    {
      tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v19);
      CoTaskMemFree(v19);
    }
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v24);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v27) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xBCC,
                     (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
                     v3);
    return (unsigned int)v27;
  }
  return result;
}

```

## disassembly

```asm
0x180036610  mov     [rsp+arg_0], rbx
0x180036615  push    rsi
0x180036616  push    rdi
0x180036617  push    r12
0x180036619  push    r14
0x18003661b  push    r15
0x18003661d  sub     rsp, 0B0h
0x180036624  mov     rsi, rdx
0x180036627  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NullCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NullCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NullCheck> `wil::Feature<__WilFeatureTraits_Feature_NullCheck>::GetImpl(void)'::`2'::impl
0x18003662e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NullCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NullCheck>::__private_IsEnabled(void)
0x180036633  xor     r15d, r15d
0x180036636  test    al, al
0x180036638  jz      short loc_180036664
0x18003663a  test    rsi, rsi
0x18003663d  jnz     short loc_180036664
0x18003663f  xor     r9d, r9d; wchar_t *
0x180036642  lea     r8, aDeletetextstor; "DeleteTextStore: Invalid argument baseP"...
0x180036649  mov     edx, 0BBEh; wchar_t *
0x18003664e  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180036655  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18003665a  mov     eax, 80004003h
0x18003665f  jmp     loc_18003689F
0x180036664  lea     rcx, [rsp+0D8h+var_68]
0x180036669  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18003666e  nop
0x18003666f  mov     rbx, [rsp+0D8h+pv]
0x180036677  mov     [rsp+0D8h+arg_10], rbx
0x18003667f  test    rbx, rbx
0x180036682  jz      short loc_18003668B
0x180036684  lock inc dword ptr [rbx+120h]
0x18003668b  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180036692  call    cs:__imp_EnterCriticalSection
0x180036698  inc     dword ptr [rbx+0F0h]
0x18003669e  mov     dword ptr [rbx+110h], 0Ch
0x1800366a8  lea     rcx, [rsp+0D8h+arg_10]
0x1800366b0  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x1800366b5  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800366b9  mov     rbx, r12
0x1800366bc  inc     rbx
0x1800366bf  cmp     [rsi+rbx*2], r15w
0x1800366c4  jnz     short loc_1800366BC
0x1800366c6  test    ebx, ebx
0x1800366c8  jnz     short loc_1800366CF
0x1800366ca  mov     rdi, r15
0x1800366cd  jmp     short loc_1800366ED
0x1800366cf  mov     ecx, ebx; this
0x1800366d1  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800366d6  mov     rdi, rax
0x1800366d9  mov     edx, ebx
0x1800366db  add     rdx, rdx; DestinationSize
0x1800366de  lea     rcx, [rax+1Ch]; Destination
0x1800366e2  mov     r9, rdx; SourceSize
0x1800366e5  mov     r8, rsi; Source
0x1800366e8  call    memcpy_s
0x1800366ed  mov     [rsp+0D8h+arg_18], rdi
0x1800366f5  test    rdi, rdi
0x1800366f8  jnz     short loc_1800366FF
0x1800366fa  mov     rsi, r15
0x1800366fd  jmp     short loc_18003673A
0x1800366ff  test    byte ptr [rdi], 1
0x180036702  jnz     short loc_18003670D
0x180036704  lock inc dword ptr [rdi+18h]
0x180036708  mov     rsi, rdi
0x18003670b  jmp     short loc_18003673A
0x18003670d  mov     r14d, [rdi+4]
0x180036711  test    r14d, r14d
0x180036714  jz      short loc_1800366FA
0x180036716  mov     rbx, [rdi+10h]
0x18003671a  mov     ecx, r14d; this
0x18003671d  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180036722  mov     rsi, rax
0x180036725  mov     edx, r14d
0x180036728  add     rdx, rdx; DestinationSize
0x18003672b  lea     rcx, [rax+1Ch]; Destination
0x18003672f  mov     r9, rdx; SourceSize
0x180036732  mov     r8, rbx; Source
0x180036735  call    memcpy_s
0x18003673a  mov     [rsp+0D8h+var_B8], rsi
0x18003673f  mov     [rsp+0D8h+var_90], rsi
0x180036744  lea     rax, [rsp+0D8h+var_90]
0x180036749  mov     [rsp+0D8h+arg_10], rax
0x180036751  lea     rax, qword_1800AF6D8
0x180036758  mov     [rsp+0D8h+var_B0], rax
0x18003675d  lock inc cs:qword_1800AF6D8
0x180036765  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStoreStatics>
0x18003676c  test    rcx, rcx
0x18003676f  jz      short loc_1800367A2
0x180036771  mov     [rsp+0D8h+var_A8], r15d
0x180036776  xorps   xmm0, xmm0
0x180036779  movdqu  [rsp+0D8h+var_A0], xmm0
0x18003677f  mov     rax, [rcx]
0x180036782  mov     rdx, [rsp+0D8h+var_90]
0x180036787  mov     rax, [rax+78h]
0x18003678b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036790  test    eax, eax
0x180036792  js      loc_1800368D5
0x180036798  lock add cs:qword_1800AF6D8, r12
0x1800367a0  jmp     short loc_1800367B8
0x1800367a2  lock add cs:qword_1800AF6D8, r12
0x1800367aa  lea     rdx, [rsp+0D8h+arg_10]
0x1800367b2  call    ??$call@AEAV_lambda_0ab8bf830596d857883e5c1e5d73dc8a_@@@?$factory_cache_entry@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStoreStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_0ab8bf830596d857883e5c1e5d73dc8a_@@@Z
0x1800367b7  nop
0x1800367b8  test    rsi, rsi
0x1800367bb  jz      short loc_1800367E2
0x1800367bd  mov     eax, r12d
0x1800367c0  lock xadd [rsi+18h], eax
0x1800367c5  sub     eax, 1
0x1800367c8  jnz     loc_1800368B7
0x1800367ce  nop
0x1800367cf  call    WINRT_IMPL_GetProcessHeap
0x1800367d4  mov     rcx, rax; hHeap
0x1800367d7  mov     r8, rsi; lpMem
0x1800367da  xor     edx, edx; dwFlags
0x1800367dc  call    WINRT_IMPL_HeapFree
0x1800367e1  nop
0x1800367e2  test    rdi, rdi
0x1800367e5  jz      short loc_18003680B
0x1800367e7  mov     eax, r12d
0x1800367ea  lock xadd [rdi+18h], eax
0x1800367ef  sub     eax, 1
0x1800367f2  jnz     loc_1800368C6
0x1800367f8  nop
0x1800367f9  call    WINRT_IMPL_GetProcessHeap
0x1800367fe  mov     rcx, rax; hHeap
0x180036801  mov     r8, rdi; lpMem
0x180036804  xor     edx, edx; dwFlags
0x180036806  call    WINRT_IMPL_HeapFree
0x18003680b  lea     rcx, off_18008BE80; "SemanticTextStore"
0x180036812  call    ??$SemanticIndexStoreDeleted@AEBQEA_W@SemanticSearchTelemetry@@SAXAEBQEA_W@Z; SemanticSearchTelemetry::SemanticIndexStoreDeleted<wchar_t * const &>(wchar_t * const &)
0x180036817  mov     rbx, [rsp+0D8h+pv]
0x18003681f  lea     rdi, [rbx+0C8h]
0x180036826  mov     rcx, rdi; lpCriticalSection
0x180036829  call    cs:__imp_EnterCriticalSection
0x18003682f  or      dword ptr [rbx+48h], 300h
0x180036836  cmp     [rbx+0F8h], r15
0x18003683d  jz      short loc_18003684D
0x18003683f  mov     edx, 2
0x180036844  lea     rcx, [rbx+8]
0x180036848  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18003684d  test    rdi, rdi
0x180036850  jz      short loc_18003685C
0x180036852  mov     rcx, rdi; lpCriticalSection
0x180036855  call    cs:__imp_LeaveCriticalSection
0x18003685b  nop
0x18003685c  mov     rbx, [rsp+0D8h+pv]
0x180036864  test    rbx, rbx
0x180036867  jz      short loc_18003688A
0x180036869  mov     eax, r12d
0x18003686c  lock xadd [rbx+120h], eax
0x180036874  add     eax, r12d
0x180036877  jnz     short loc_18003688A
0x180036879  mov     rcx, rbx
0x18003687c  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180036881  mov     rcx, rbx; pv
0x180036884  call    cs:__imp_CoTaskMemFree
0x18003688a  lea     rcx, [rsp+0D8h+var_60]; this
0x18003688f  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180036894  xor     eax, eax
0x180036896  jmp     short loc_18003689F
0x180036898  mov     eax, dword ptr [rsp+0D8h+arg_10]
0x18003689f  mov     rbx, [rsp+0D8h+arg_0]
0x1800368a7  add     rsp, 0B0h
0x1800368ae  pop     r15
0x1800368b0  pop     r14
0x1800368b2  pop     r12
0x1800368b4  pop     rdi
0x1800368b5  pop     rsi
0x1800368b6  retn
0x1800368b7  test    eax, eax
0x1800368b9  jns     loc_1800367E2
0x1800368bf  call    cs:__imp_abort
0x1800368c6  test    eax, eax
0x1800368c8  jns     loc_18003680B
0x1800368ce  call    cs:__imp_abort
0x1800368d5  lea     rdx, [rsp+0D8h+var_A8]
0x1800368da  mov     ecx, eax
0x1800368dc  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
