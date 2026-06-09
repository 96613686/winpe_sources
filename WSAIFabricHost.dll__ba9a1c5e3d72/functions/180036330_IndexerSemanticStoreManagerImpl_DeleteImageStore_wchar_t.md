# IndexerSemanticStoreManagerImpl::DeleteImageStore(wchar_t *)

- ea: `0x180036330`
- end: `0x180036606`
- name: `?DeleteImageStore@IndexerSemanticStoreManagerImpl@@UEAAJPEA_W@Z`
- size: `726`
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
- `0x18002ca08`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x180036330`
- `0x18004d924`
- `0x18004dea8`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800365e2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800365f1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800365e2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800365f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036578`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036578`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800363b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003654c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800363b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003654c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800365a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800365a7`

## string_xrefs

- `0x18003636e`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180036362`: `DeleteImageStore: Invalid argument basePath: %p`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IndexerSemanticStoreManagerImpl::DeleteImageStore(
        IndexerSemanticStoreManagerImpl *this,
        wchar_t *a2)
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
        (const wchar_t *)0xBD5,
        (unsigned int)L"DeleteImageStore: Invalid argument basePath: %p",
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
    LODWORD(v5[6].SpinCount) = 14;
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
    _InterlockedIncrement64(&qword_1800AF658);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> )
    {
      v20 = 0;
      v21 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>
                                                                          + 168LL))(
              winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>,
              v22);
      if ( v12 < 0 )
        winrt::throw_hresult((unsigned int)v12, &v20);
      _InterlockedAdd64(&qword_1800AF658, 0xFFFFFFFFFFFFFFFFuLL);
    }
    else
    {
      _InterlockedAdd64(&qword_1800AF658, 0xFFFFFFFFFFFFFFFFuLL);
      winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::call<_lambda_3668e2938f0fc1a3a6b5fc281c2032e3_ &>(
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
    SemanticSearchTelemetry::SemanticIndexStoreDeleted<wchar_t * const &>(off_18008BE88);
    v17 = pv;
    v18 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
    EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
    v17[18] |= 0x300u;
    if ( *((_QWORD *)v17 + 31) )
      tip2::details::shared_data<0,0,0>::complete_helper(v17 + 2, 2);
    if ( v18 )
      LeaveCriticalSection(v18);
    v19 = pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
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
                     (void *)0xBE3,
                     (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
                     v3);
    return (unsigned int)v27;
  }
  return result;
}

```

## disassembly

```asm
0x180036330  mov     [rsp+arg_0], rbx
0x180036335  push    rsi
0x180036336  push    rdi
0x180036337  push    r12
0x180036339  push    r14
0x18003633b  push    r15
0x18003633d  sub     rsp, 0B0h
0x180036344  mov     rsi, rdx
0x180036347  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NullCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NullCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NullCheck> `wil::Feature<__WilFeatureTraits_Feature_NullCheck>::GetImpl(void)'::`2'::impl
0x18003634e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NullCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NullCheck>::__private_IsEnabled(void)
0x180036353  xor     r15d, r15d
0x180036356  test    al, al
0x180036358  jz      short loc_180036384
0x18003635a  test    rsi, rsi
0x18003635d  jnz     short loc_180036384
0x18003635f  xor     r9d, r9d; wchar_t *
0x180036362  lea     r8, aDeleteimagesto; "DeleteImageStore: Invalid argument base"...
0x180036369  mov     edx, 0BD5h; wchar_t *
0x18003636e  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180036375  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18003637a  mov     eax, 80004003h
0x18003637f  jmp     loc_1800365C2
0x180036384  lea     rcx, [rsp+0D8h+var_68]
0x180036389  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18003638e  nop
0x18003638f  mov     rbx, [rsp+0D8h+pv]
0x180036397  mov     [rsp+0D8h+arg_10], rbx
0x18003639f  test    rbx, rbx
0x1800363a2  jz      short loc_1800363AB
0x1800363a4  lock inc dword ptr [rbx+120h]
0x1800363ab  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800363b2  call    cs:__imp_EnterCriticalSection
0x1800363b8  inc     dword ptr [rbx+0F0h]
0x1800363be  mov     dword ptr [rbx+110h], 0Eh
0x1800363c8  lea     rcx, [rsp+0D8h+arg_10]
0x1800363d0  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x1800363d5  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800363d9  mov     rbx, r12
0x1800363dc  inc     rbx
0x1800363df  cmp     [rsi+rbx*2], r15w
0x1800363e4  jnz     short loc_1800363DC
0x1800363e6  test    ebx, ebx
0x1800363e8  jnz     short loc_1800363EF
0x1800363ea  mov     rdi, r15
0x1800363ed  jmp     short loc_18003640D
0x1800363ef  mov     ecx, ebx; this
0x1800363f1  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x1800363f6  mov     rdi, rax
0x1800363f9  mov     edx, ebx
0x1800363fb  add     rdx, rdx; DestinationSize
0x1800363fe  lea     rcx, [rax+1Ch]; Destination
0x180036402  mov     r9, rdx; SourceSize
0x180036405  mov     r8, rsi; Source
0x180036408  call    memcpy_s
0x18003640d  mov     [rsp+0D8h+arg_18], rdi
0x180036415  test    rdi, rdi
0x180036418  jnz     short loc_18003641F
0x18003641a  mov     rsi, r15
0x18003641d  jmp     short loc_18003645A
0x18003641f  test    byte ptr [rdi], 1
0x180036422  jnz     short loc_18003642D
0x180036424  lock inc dword ptr [rdi+18h]
0x180036428  mov     rsi, rdi
0x18003642b  jmp     short loc_18003645A
0x18003642d  mov     r14d, [rdi+4]
0x180036431  test    r14d, r14d
0x180036434  jz      short loc_18003641A
0x180036436  mov     rbx, [rdi+10h]
0x18003643a  mov     ecx, r14d; this
0x18003643d  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180036442  mov     rsi, rax
0x180036445  mov     edx, r14d
0x180036448  add     rdx, rdx; DestinationSize
0x18003644b  lea     rcx, [rax+1Ch]; Destination
0x18003644f  mov     r9, rdx; SourceSize
0x180036452  mov     r8, rbx; Source
0x180036455  call    memcpy_s
0x18003645a  mov     [rsp+0D8h+var_B8], rsi
0x18003645f  mov     [rsp+0D8h+var_90], rsi
0x180036464  lea     rax, [rsp+0D8h+var_90]
0x180036469  mov     [rsp+0D8h+arg_10], rax
0x180036471  lea     rax, qword_1800AF658
0x180036478  mov     [rsp+0D8h+var_B0], rax
0x18003647d  lock inc cs:qword_1800AF658
0x180036485  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::SemanticImageIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticImageIndexStoreStatics>
0x18003648c  test    rcx, rcx
0x18003648f  jz      short loc_1800364C5
0x180036491  mov     [rsp+0D8h+var_A8], r15d
0x180036496  xorps   xmm0, xmm0
0x180036499  movdqu  [rsp+0D8h+var_A0], xmm0
0x18003649f  mov     rax, [rcx]
0x1800364a2  mov     rdx, [rsp+0D8h+var_90]
0x1800364a7  mov     rax, [rax+0A8h]
0x1800364ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364b3  test    eax, eax
0x1800364b5  js      loc_1800365F8
0x1800364bb  lock add cs:qword_1800AF658, r12
0x1800364c3  jmp     short loc_1800364DB
0x1800364c5  lock add cs:qword_1800AF658, r12
0x1800364cd  lea     rdx, [rsp+0D8h+arg_10]
0x1800364d5  call    ??$call@AEAV_lambda_3668e2938f0fc1a3a6b5fc281c2032e3_@@@?$factory_cache_entry@USemanticImageIndexStore@SemanticSearch@Windows@Microsoft@winrt@@UISemanticImageIndexStoreStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_3668e2938f0fc1a3a6b5fc281c2032e3_@@@Z
0x1800364da  nop
0x1800364db  test    rsi, rsi
0x1800364de  jz      short loc_180036505
0x1800364e0  mov     eax, r12d
0x1800364e3  lock xadd [rsi+18h], eax
0x1800364e8  sub     eax, 1
0x1800364eb  jnz     loc_1800365DA
0x1800364f1  nop
0x1800364f2  call    WINRT_IMPL_GetProcessHeap
0x1800364f7  mov     rcx, rax; hHeap
0x1800364fa  mov     r8, rsi; lpMem
0x1800364fd  xor     edx, edx; dwFlags
0x1800364ff  call    WINRT_IMPL_HeapFree
0x180036504  nop
0x180036505  test    rdi, rdi
0x180036508  jz      short loc_18003652E
0x18003650a  mov     eax, r12d
0x18003650d  lock xadd [rdi+18h], eax
0x180036512  sub     eax, 1
0x180036515  jnz     loc_1800365E9
0x18003651b  nop
0x18003651c  call    WINRT_IMPL_GetProcessHeap
0x180036521  mov     rcx, rax; hHeap
0x180036524  mov     r8, rdi; lpMem
0x180036527  xor     edx, edx; dwFlags
0x180036529  call    WINRT_IMPL_HeapFree
0x18003652e  lea     rcx, off_18008BE88; "SemanticImageStore"
0x180036535  call    ??$SemanticIndexStoreDeleted@AEBQEA_W@SemanticSearchTelemetry@@SAXAEBQEA_W@Z; SemanticSearchTelemetry::SemanticIndexStoreDeleted<wchar_t * const &>(wchar_t * const &)
0x18003653a  mov     rbx, [rsp+0D8h+pv]
0x180036542  lea     rdi, [rbx+0C8h]
0x180036549  mov     rcx, rdi; lpCriticalSection
0x18003654c  call    cs:__imp_EnterCriticalSection
0x180036552  or      dword ptr [rbx+48h], 300h
0x180036559  cmp     [rbx+0F8h], r15
0x180036560  jz      short loc_180036570
0x180036562  mov     edx, 2
0x180036567  lea     rcx, [rbx+8]
0x18003656b  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180036570  test    rdi, rdi
0x180036573  jz      short loc_18003657F
0x180036575  mov     rcx, rdi; lpCriticalSection
0x180036578  call    cs:__imp_LeaveCriticalSection
0x18003657e  nop
0x18003657f  mov     rbx, [rsp+0D8h+pv]
0x180036587  test    rbx, rbx
0x18003658a  jz      short loc_1800365AD
0x18003658c  mov     eax, r12d
0x18003658f  lock xadd [rbx+120h], eax
0x180036597  add     eax, r12d
0x18003659a  jnz     short loc_1800365AD
0x18003659c  mov     rcx, rbx
0x18003659f  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x1800365a4  mov     rcx, rbx; pv
0x1800365a7  call    cs:__imp_CoTaskMemFree
0x1800365ad  lea     rcx, [rsp+0D8h+var_60]; this
0x1800365b2  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800365b7  xor     eax, eax
0x1800365b9  jmp     short loc_1800365C2
0x1800365bb  mov     eax, dword ptr [rsp+0D8h+arg_10]
0x1800365c2  mov     rbx, [rsp+0D8h+arg_0]
0x1800365ca  add     rsp, 0B0h
0x1800365d1  pop     r15
0x1800365d3  pop     r14
0x1800365d5  pop     r12
0x1800365d7  pop     rdi
0x1800365d8  pop     rsi
0x1800365d9  retn
0x1800365da  test    eax, eax
0x1800365dc  jns     loc_180036505
0x1800365e2  call    cs:__imp_abort
0x1800365e9  test    eax, eax
0x1800365eb  jns     loc_18003652E
0x1800365f1  call    cs:__imp_abort
0x1800365f8  lea     rdx, [rsp+0D8h+var_A8]
0x1800365fd  mov     ecx, eax
0x1800365ff  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
