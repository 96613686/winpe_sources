# IndexerSemanticSearchServicesImpl::CreateTextRegionStreamEmbeddings(wchar_t *,wchar_t *,ISemanticTextRegionStream * *)

- ea: `0x180035cb0`
- end: `0x180036324`
- name: `?CreateTextRegionStreamEmbeddings@IndexerSemanticSearchServicesImpl@@UEAAJPEA_W0PEAPEAUISemanticTextRegionStream@@@Z`
- size: `1652`
- prototype: `int(IndexerSemanticSearchServicesImpl *__hidden this, wchar_t *, wchar_t *, struct ISemanticTextRegionStream **)`
- caller_count: `0`
- callee_count: `22`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800058cb`
- `0x18000591f`
- `0x180007ad0`
- `0x18000b064`
- `0x18000c350`
- `0x18000c478`
- `0x18000c634`
- `0x180013930`
- `0x180015f90`
- `0x1800187b0`
- `0x180019c3c`
- `0x18002df50`
- `0x18002f924`
- `0x1800318c4`
- `0x180031bac`
- `0x1800326e8`
- `0x180032f28`
- `0x180035cb0`
- `0x18003d104`
- `0x18004d9c4`
- `0x18004dea8`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180035ff6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180036001`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180035ff6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180036001`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003619e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003619e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035da0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003607c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036172`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035da0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003607c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036134`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003627f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036134`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003627f`

## string_xrefs

- `0x180035d05`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x18003601f`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x1800360d8`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`
- `0x180036013`: `CreateTextRegionStreamEmbeddings : Failed to generate TextRegionStream using AIFabric`
- `0x180035cf9`: `CreateTextRegionStreamEmbeddings : Started`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall IndexerSemanticSearchServicesImpl::CreateTextRegionStreamEmbeddings(
        IndexerSemanticSearchServicesImpl *this,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t *a4)
{
  const wchar_t *v4; // rsi
  wchar_t *v5; // r13
  IndexerSemanticSearchServicesImpl *v6; // r12
  int v7; // r15d
  unsigned __int8 v8; // al
  unsigned int v9; // r10d
  __int64 v10; // r14
  __int64 *TextEmbeddingGenerator; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  void (__fastcall ***v13)(_QWORD, __int64 *, __int64 **); // rcx
  __int64 *v14; // rbx
  unsigned int v15; // edx
  int v16; // r15d
  __int64 v17; // rbx
  struct winrt::impl::shared_hstring_header *v18; // rsi
  volatile signed __int32 *v19; // r13
  unsigned int v20; // eax
  const void *v21; // rbx
  int v22; // eax
  char *v23; // r14
  int v24; // eax
  HANDLE ProcessHeap; // rax
  int v26; // eax
  HANDLE v27; // rax
  int v28; // r15d
  int v29; // eax
  const wchar_t *v30; // r9
  int v31; // eax
  int v32; // esi
  struct _RTL_CRITICAL_SECTION *v33; // rbx
  int v34; // eax
  unsigned int v35; // esi
  struct _RTL_CRITICAL_SECTION *v36; // rbx
  __int64 result; // rax
  _DWORD *v38; // rbx
  struct _RTL_CRITICAL_SECTION *v39; // rsi
  __int64 v40; // r13
  _QWORD *v41; // rsi
  struct _RTL_CRITICAL_SECTION *v42; // rbx
  int v43; // eax
  const char *v44; // [rsp+20h] [rbp-F8h]
  int v45; // [rsp+20h] [rbp-F8h]
  unsigned __int8 v46; // [rsp+30h] [rbp-E8h]
  char v47[7]; // [rsp+31h] [rbp-E7h] BYREF
  char *v48; // [rsp+38h] [rbp-E0h] BYREF
  int v49; // [rsp+40h] [rbp-D8h]
  void (__fastcall *v50)(__int64, __int64 *); // [rsp+48h] [rbp-D0h] BYREF
  __int64 v51; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v52; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v53; // [rsp+60h] [rbp-B8h]
  int v54; // [rsp+68h] [rbp-B0h] BYREF
  __int128 v55; // [rsp+70h] [rbp-A8h]
  __int64 v56; // [rsp+80h] [rbp-98h] BYREF
  __int64 v57[3]; // [rsp+88h] [rbp-90h] BYREF
  char v58[8]; // [rsp+A0h] [rbp-78h] BYREF
  _BYTE v59[48]; // [rsp+A8h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+D8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v4 = a3;
  v5 = a2;
  v6 = this;
  v7 = 0;
  v49 = 0;
  v8 = 0;
  v46 = 0;
  v9 = 0;
  while ( 2 )
  {
    if ( v8 >= 3u )
      return v9;
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const wchar_t *)0x5B7,
      (unsigned int)L"CreateTextRegionStreamEmbeddings : Started",
      a4);
    try
    {
      v10 = 0;
      v53 = 0;
      v51 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
      {
        TextEmbeddingGenerator = IndexerSemanticSearchServicesImpl::GetTextEmbeddingGenerator(v6, &v56, v4);
        if ( &v51 != TextEmbeddingGenerator )
        {
          v53 = *TextEmbeddingGenerator;
          v10 = v53;
          *TextEmbeddingGenerator = 0;
          v51 = v10;
        }
        if ( v56 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v56);
      }
      tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>>((__int64)v58);
      v12 = (struct _RTL_CRITICAL_SECTION *)pv;
      v50 = (void (__fastcall *)(__int64, __int64 *))pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 72);
      EnterCriticalSection(v12 + 5);
      ++LODWORD(v12[6].DebugInfo);
      LODWORD(v12[6].SpinCount) = 9;
      tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v50);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl'::`2'::impl) )
      {
        v14 = IndexerSemanticSearchServicesImpl::GetTextEmbeddingGenerator(v6, v57, v4);
        if ( &v51 != v14 )
        {
          if ( v10 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
          v53 = *v14;
          v10 = v53;
          *v14 = 0;
          v51 = v10;
        }
        if ( v57[0] )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v57);
      }
      v50 = (void (__fastcall *)(__int64, __int64 *))&qword_1800AF738;
      _InterlockedIncrement64(&qword_1800AF738);
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory> )
      {
        _lambda_1f675fac5d8dafc75d3c42376965940e_::operator()(
          v13,
          &v52,
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory>);
        v16 = v7 | 1;
        v49 = v16;
        _InterlockedAdd64(&qword_1800AF738, 0xFFFFFFFFFFFFFFFFuLL);
      }
      else
      {
        _InterlockedAdd64(&qword_1800AF738, 0xFFFFFFFFFFFFFFFFuLL);
        v50 = (void (__fastcall *)(__int64, __int64 *))_lambda_1f675fac5d8dafc75d3c42376965940e_::_lambda_invoker_cdecl_;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
          v13,
          (__int64)&v52,
          &v50);
        v16 = v7 | 1;
        v49 = v16;
      }
      v17 = -1;
      do
        ++v17;
      while ( v5[v17] );
      if ( (_DWORD)v17 )
      {
        v18 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v17, v15);
        memcpy_s((char *)v18 + 28, 2LL * (unsigned int)v17, v5, 2LL * (unsigned int)v17);
      }
      else
      {
        v18 = 0;
      }
      v50 = (void (__fastcall *)(__int64, __int64 *))v18;
      if ( v18 )
      {
        if ( (*(_BYTE *)v18 & 1) == 0 )
        {
          _InterlockedIncrement((volatile signed __int32 *)v18 + 6);
          v19 = (volatile signed __int32 *)v18;
          goto LABEL_32;
        }
        v20 = *((_DWORD *)v18 + 1);
        LODWORD(v48) = v20;
        if ( v20 )
        {
          v21 = (const void *)*((_QWORD *)v18 + 2);
          v19 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)v20, v15);
          memcpy_s((void *const)(v19 + 7), 2LL * (unsigned int)v48, v21, 2LL * (unsigned int)v48);
          goto LABEL_32;
        }
      }
      v19 = 0;
LABEL_32:
      v57[1] = (__int64)v19;
      v48 = 0;
      v54 = 0;
      v55 = 0;
      v22 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *, __int64, char **))(*(_QWORD *)v10 + 72LL))(
              v10,
              v19,
              v52,
              &v48);
      if ( v22 < 0 )
        winrt::throw_hresult((unsigned int)v22, &v54);
      v23 = v48;
      v50 = (void (__fastcall *)(__int64, __int64 *))v48;
      if ( v19 )
      {
        v24 = _InterlockedDecrement(v19 + 6);
        if ( v24 )
        {
          if ( v24 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v19);
        }
        v23 = v48;
      }
      if ( v18 )
      {
        v26 = _InterlockedDecrement((volatile signed __int32 *)v18 + 6);
        if ( v26 )
        {
          if ( v26 < 0 )
            abort();
        }
        else
        {
          v27 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v27, 0, v18);
        }
        v23 = v48;
      }
      v28 = v16 | 2;
      v49 = v28;
      v47[0] = 0;
      v54 = 0;
      v55 = 0;
      v29 = (*(__int64 (__fastcall **)(char *, char *))(*(_QWORD *)v23 + 48LL))(v23, v47);
      if ( v29 < 0 )
        winrt::throw_hresult((unsigned int)v29, &v54);
      if ( v47[0] )
      {
        v38 = pv;
        v39 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
        EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
        v38[18] |= 0x300u;
        if ( *((_QWORD *)v38 + 31) )
          tip2::details::shared_data<0,0,0>::complete_helper(v38 + 2, 2);
        if ( v39 )
          LeaveCriticalSection(v39);
        v40 = *((_QWORD *)this + 20);
        v41 = operator new(0x28u);
        *v41 = &winrt::impl::producers_base<SemanticTextRegionStream,std::tuple<ISemanticTextRegionStream>>::`vftable';
        winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v41 + 2));
        v41[2] = 1;
        *v41 = &winrt::impl::heap_implements<SemanticTextRegionStream>::`vftable'{for `winrt::impl::producers_base<SemanticTextRegionStream,std::tuple<ISemanticTextRegionStream>>'};
        v41[1] = &winrt::impl::heap_implements<SemanticTextRegionStream>::`vftable'{for `winrt::impl::root_implements<SemanticTextRegionStream,ISemanticTextRegionStream,winrt::non_agile>'};
        v41[3] = v23;
        if ( v23 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 8LL))(v23);
        v41[4] = v40;
        *v41 = &winrt::impl::heap_implements<SemanticTextRegionStream>::`vftable'{for `winrt::impl::producers_base<SemanticTextRegionStream,std::tuple<ISemanticTextRegionStream>>'};
        v41[1] = &winrt::impl::heap_implements<SemanticTextRegionStream>::`vftable'{for `winrt::impl::root_implements<SemanticTextRegionStream,ISemanticTextRegionStream,winrt::non_agile>'};
        v49 = v28 | 4;
        *(_QWORD *)a4 = v41;
        if ( v23 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v50);
        if ( v52 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v52);
        v42 = (struct _RTL_CRITICAL_SECTION *)pv;
        if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
        {
          tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v42);
          CoTaskMemFree(v42);
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v59);
        if ( v53 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
        result = 0;
      }
      else
      {
        SearchIndexerTrace::Error(
          (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
          (const wchar_t *)0x5CE,
          (unsigned int)L"CreateTextRegionStreamEmbeddings : Failed to generate TextRegionStream using AIFabric",
          v30);
        LODWORD(v48) = 0;
        v54 = 0;
        v55 = 0;
        v31 = (*(__int64 (__fastcall **)(char *, char **))(*(_QWORD *)v23 + 56LL))(v23, &v48);
        if ( v31 < 0 )
          winrt::throw_hresult((unsigned int)v31, &v54);
        v32 = (int)v48;
        v33 = (struct _RTL_CRITICAL_SECTION *)pv;
        v48 = (char *)pv;
        if ( pv )
          _InterlockedIncrement((volatile signed __int32 *)pv + 72);
        EnterCriticalSection(v33 + 5);
        ++LODWORD(v33[6].DebugInfo);
        LODWORD(v33[7].DebugInfo) = v32;
        tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(&v48);
        LODWORD(v48) = 0;
        v54 = 0;
        v55 = 0;
        v34 = (*(__int64 (__fastcall **)(char *, char **))(*(_QWORD *)v23 + 64LL))(v23, &v48);
        if ( v34 < 0 )
          winrt::throw_hresult((unsigned int)v34, &v54);
        v35 = (unsigned int)v48;
        if ( (int)v48 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5D0,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
            (const char *)(unsigned int)v48,
            v45);
        if ( v23 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v50);
        if ( v52 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v52);
        v36 = (struct _RTL_CRITICAL_SECTION *)pv;
        if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
        {
          tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(v36);
          CoTaskMemFree(v36);
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v59);
        if ( v53 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
        result = v35;
      }
    }
    catch ( ... )
    {
      IndexerSemanticSearchServicesImpl::ResetTextEmbeddingGenerator(this, a3);
      v43 = wil::details::in1diag3::Log_CaughtExceptionMsg(
              retaddr,
              (void *)0x5E3,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
              "CreateTextRegionStreamEmbeddings : Exception occurred while creating TextRegionStream",
              v44);
      LODWORD(v48) = v43;
      if ( v43 < 0
        && ((v43 & 0x1FFF0000) == 0x10000
         || (v43 & 0x1FFF0000) == 0x70000 && (unsigned int)(unsigned __int16)v43 - 1700 <= 0x12B) )
      {
        ++v46;
        v4 = a3;
        v5 = a2;
        v8 = v46;
        v9 = (unsigned int)v48;
        v7 = v49;
        v6 = this;
        continue;
      }
      return (unsigned int)v48;
    }
    return result;
  }
}

```

## disassembly

```asm
0x180035cb0  mov     rax, rsp
0x180035cb3  mov     [rax+20h], r9
0x180035cb7  mov     [rax+18h], r8
0x180035cbb  mov     [rax+10h], rdx
0x180035cbf  mov     [rax+8], rcx
0x180035cc3  push    rbx
0x180035cc4  push    rsi
0x180035cc5  push    rdi
0x180035cc6  push    r12
0x180035cc8  push    r13
0x180035cca  push    r14
0x180035ccc  push    r15
0x180035cce  sub     rsp, 0E0h
0x180035cd5  mov     rsi, r8
0x180035cd8  mov     r13, rdx
0x180035cdb  mov     r12, rcx
0x180035cde  xor     edi, edi
0x180035ce0  mov     r15d, edi
0x180035ce3  mov     [rsp+118h+var_D8], edi
0x180035ce7  mov     al, dil
0x180035cea  mov     [rsp+118h+var_E8], al
0x180035cee  mov     r10d, edi
0x180035cf1  cmp     al, 3
0x180035cf3  jnb     loc_1800362DB
0x180035cf9  lea     r8, aCreatetextregi_1; "CreateTextRegionStreamEmbeddings : Star"...
0x180035d00  mov     edx, 5B7h; wchar_t *
0x180035d05  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180035d0c  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180035d11  mov     r14, rdi
0x180035d14  mov     [rsp+118h+var_B8], rdi
0x180035d19  mov     [rsp+118h+var_C8], rdi
0x180035d1e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x180035d25  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x180035d2a  test    al, al
0x180035d2c  jz      short loc_180035D72
0x180035d2e  mov     r8, rsi
0x180035d31  lea     rdx, [rsp+118h+var_98]
0x180035d39  mov     rcx, r12
0x180035d3c  call    ?GetTextEmbeddingGenerator@IndexerSemanticSearchServicesImpl@@AEAA?AUTextEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@PEA_W@Z; IndexerSemanticSearchServicesImpl::GetTextEmbeddingGenerator(wchar_t *)
0x180035d41  lea     rcx, [rsp+118h+var_C8]
0x180035d46  cmp     rcx, rax
0x180035d49  jz      short loc_180035D5B
0x180035d4b  mov     r14, [rax]
0x180035d4e  mov     [rsp+118h+var_B8], r14
0x180035d53  mov     [rax], rdi
0x180035d56  mov     [rsp+118h+var_C8], r14
0x180035d5b  cmp     [rsp+118h+var_98], rdi
0x180035d63  jz      short loc_180035D72
0x180035d65  lea     rcx, [rsp+118h+var_98]
0x180035d6d  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180035d72  lea     rcx, [rsp+118h+var_78]
0x180035d7a  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x180035d7f  nop
0x180035d80  mov     rbx, [rsp+118h+pv]
0x180035d88  mov     [rsp+118h+var_D0], rbx
0x180035d8d  test    rbx, rbx
0x180035d90  jz      short loc_180035D99
0x180035d92  lock inc dword ptr [rbx+120h]
0x180035d99  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180035da0  call    cs:__imp_EnterCriticalSection
0x180035da6  inc     dword ptr [rbx+0F0h]
0x180035dac  mov     dword ptr [rbx+110h], 9
0x180035db6  lea     rcx, [rsp+118h+var_D0]
0x180035dbb  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180035dc0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics> `wil::Feature<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::GetImpl(void)'::`2'::impl
0x180035dc7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SemanticSearch_Improved_Diagnostics>::__private_IsEnabled(void)
0x180035dcc  test    al, al
0x180035dce  jnz     short loc_180035E26
0x180035dd0  mov     r8, rsi
0x180035dd3  lea     rdx, [rsp+118h+var_90]
0x180035ddb  mov     rcx, r12
0x180035dde  call    ?GetTextEmbeddingGenerator@IndexerSemanticSearchServicesImpl@@AEAA?AUTextEmbeddingsGenerator@SemanticSearch@Windows@Microsoft@winrt@@PEA_W@Z; IndexerSemanticSearchServicesImpl::GetTextEmbeddingGenerator(wchar_t *)
0x180035de3  mov     rbx, rax
0x180035de6  lea     rax, [rsp+118h+var_C8]
0x180035deb  cmp     rax, rbx
0x180035dee  jz      short loc_180035E0F
0x180035df0  test    r14, r14
0x180035df3  jz      short loc_180035DFF
0x180035df5  lea     rcx, [rsp+118h+var_C8]
0x180035dfa  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180035dff  mov     r14, [rbx]
0x180035e02  mov     [rsp+118h+var_B8], r14
0x180035e07  mov     [rbx], rdi
0x180035e0a  mov     [rsp+118h+var_C8], r14
0x180035e0f  cmp     [rsp+118h+var_90], rdi
0x180035e17  jz      short loc_180035E26
0x180035e19  lea     rcx, [rsp+118h+var_90]
0x180035e21  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180035e26  lea     rax, qword_1800AF738
0x180035e2d  mov     [rsp+118h+var_D0], rax
0x180035e32  lock inc cs:qword_1800AF738
0x180035e3a  cmp     cs:??$factory_cache_entry_v@UTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@impl@winrt@@3U?$factory_cache_entry@UTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@12@A, rdi; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory>
0x180035e41  jz      short loc_180035E6B
0x180035e43  lea     r8, ??$factory_cache_entry_v@UTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@impl@winrt@@3U?$factory_cache_entry@UTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@12@A; factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::SemanticSearch::TextEmbeddingsOptions,winrt::Windows::Foundation::IActivationFactory>
0x180035e4a  lea     rdx, [rsp+118h+var_C0]
0x180035e4f  call    ??R_lambda_1f675fac5d8dafc75d3c42376965940e_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_1f675fac5d8dafc75d3c42376965940e_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180035e54  or      r15d, 1
0x180035e58  mov     [rsp+118h+var_D8], r15d
0x180035e5d  or      r12, 0FFFFFFFFFFFFFFFFh
0x180035e61  lock add cs:qword_1800AF738, r12
0x180035e69  jmp     short loc_180035E9B
0x180035e6b  or      r12, 0FFFFFFFFFFFFFFFFh
0x180035e6f  lock add cs:qword_1800AF738, r12
0x180035e77  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1f675fac5d8dafc75d3c42376965940e_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_1f675fac5d8dafc75d3c42376965940e_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180035e7e  mov     [rsp+118h+var_D0], rax
0x180035e83  lea     r8, [rsp+118h+var_D0]
0x180035e88  lea     rdx, [rsp+118h+var_C0]
0x180035e8d  call    ??$call@P6A?AUTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@35@@Z@?$factory_cache_entry@UTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@35@@impl@winrt@@QEAA?A_P$$QEAP6A?AUTextEmbeddingsOptions@SemanticSearch@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@52@@Z@Z
0x180035e92  or      r15d, 1
0x180035e96  mov     [rsp+118h+var_D8], r15d
0x180035e9b  mov     rbx, r12
0x180035e9e  inc     rbx
0x180035ea1  cmp     [r13+rbx*2+0], di
0x180035ea7  jnz     short loc_180035E9E
0x180035ea9  test    ebx, ebx
0x180035eab  jnz     short loc_180035EB2
0x180035ead  mov     rsi, rdi
0x180035eb0  jmp     short loc_180035ED0
0x180035eb2  mov     ecx, ebx; this
0x180035eb4  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180035eb9  mov     rsi, rax
0x180035ebc  mov     edx, ebx
0x180035ebe  add     rdx, rdx; DestinationSize
0x180035ec1  lea     rcx, [rax+1Ch]; Destination
0x180035ec5  mov     r9, rdx; SourceSize
0x180035ec8  mov     r8, r13; Source
0x180035ecb  call    memcpy_s
0x180035ed0  mov     [rsp+118h+var_D0], rsi
0x180035ed5  test    rsi, rsi
0x180035ed8  jnz     short loc_180035EDF
0x180035eda  mov     r13, rdi
0x180035edd  jmp     short loc_180035F1C
0x180035edf  test    byte ptr [rsi], 1
0x180035ee2  jnz     short loc_180035EED
0x180035ee4  lock inc dword ptr [rsi+18h]
0x180035ee8  mov     r13, rsi
0x180035eeb  jmp     short loc_180035F1C
0x180035eed  mov     eax, [rsi+4]
0x180035ef0  mov     dword ptr [rsp+118h+var_E0], eax
0x180035ef4  test    eax, eax
0x180035ef6  jz      short loc_180035EDA
0x180035ef8  mov     rbx, [rsi+10h]
0x180035efc  mov     ecx, eax; this
0x180035efe  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180035f03  mov     r13, rax
0x180035f06  mov     edx, dword ptr [rsp+118h+var_E0]
0x180035f0a  add     rdx, rdx; DestinationSize
0x180035f0d  lea     rcx, [rax+1Ch]; Destination
0x180035f11  mov     r9, rdx; SourceSize
0x180035f14  mov     r8, rbx; Source
0x180035f17  call    memcpy_s
0x180035f1c  mov     [rsp+118h+var_88], r13
0x180035f24  mov     [rsp+118h+var_E0], rdi
0x180035f29  mov     [rsp+118h+var_B0], edi
0x180035f2d  xorps   xmm0, xmm0
0x180035f30  movdqu  [rsp+118h+var_A8], xmm0
0x180035f36  mov     rax, [r14]
0x180035f39  lea     r9, [rsp+118h+var_E0]
0x180035f3e  mov     r8, [rsp+118h+var_C0]
0x180035f43  mov     rdx, r13
0x180035f46  mov     rcx, r14
0x180035f49  mov     rax, [rax+48h]
0x180035f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f52  test    eax, eax
0x180035f54  js      loc_1800362F1
0x180035f5a  mov     r14, [rsp+118h+var_E0]
0x180035f5f  mov     [rsp+118h+var_D0], r14
0x180035f64  test    r13, r13
0x180035f67  jz      short loc_180035F8F
0x180035f69  mov     eax, r12d
0x180035f6c  lock xadd [r13+18h], eax
0x180035f72  sub     eax, 1
0x180035f75  jnz     short loc_180035FF2
0x180035f77  nop
0x180035f78  call    WINRT_IMPL_GetProcessHeap
0x180035f7d  mov     rcx, rax; hHeap
0x180035f80  mov     r8, r13; lpMem
0x180035f83  xor     edx, edx; dwFlags
0x180035f85  call    WINRT_IMPL_HeapFree
0x180035f8a  mov     r14, [rsp+118h+var_E0]
0x180035f8f  test    rsi, rsi
0x180035f92  jz      short loc_180035FB9
0x180035f94  mov     eax, r12d
0x180035f97  lock xadd [rsi+18h], eax
0x180035f9c  sub     eax, 1
0x180035f9f  jnz     short loc_180035FFD
0x180035fa1  nop
0x180035fa2  call    WINRT_IMPL_GetProcessHeap
0x180035fa7  mov     rcx, rax; hHeap
0x180035faa  mov     r8, rsi; lpMem
0x180035fad  xor     edx, edx; dwFlags
0x180035faf  call    WINRT_IMPL_HeapFree
0x180035fb4  mov     r14, [rsp+118h+var_E0]
0x180035fb9  or      r15d, 2
0x180035fbd  mov     [rsp+118h+var_D8], r15d
0x180035fc2  mov     [rsp+118h+var_E7], dil
0x180035fc7  mov     [rsp+118h+var_B0], edi
0x180035fcb  xorps   xmm0, xmm0
0x180035fce  movdqu  [rsp+118h+var_A8], xmm0
0x180035fd4  mov     rax, [r14]
0x180035fd7  lea     rdx, [rsp+118h+var_E7]
0x180035fdc  mov     rcx, r14
0x180035fdf  mov     rax, [rax+30h]
0x180035fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fe8  test    eax, eax
0x180035fea  js      loc_1800362FE
0x180035ff0  jmp     short loc_180036008
0x180035ff2  test    eax, eax
0x180035ff4  jns     short loc_180035F8A
0x180035ff6  call    cs:__imp_abort
0x180035ffd  test    eax, eax
0x180035fff  jns     short loc_180035FB4
0x180036001  call    cs:__imp_abort
0x180036008  cmp     [rsp+118h+var_E7], dil
0x18003600d  jnz     loc_180036160
0x180036013  lea     r8, aCreatetextregi; "CreateTextRegionStreamEmbeddings : Fail"...
0x18003601a  mov     edx, 5CEh; wchar_t *
0x18003601f  lea     rcx, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\com"...
0x180036026  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18003602b  mov     dword ptr [rsp+118h+var_E0], edi
0x18003602f  mov     [rsp+118h+var_B0], edi
0x180036033  xorps   xmm0, xmm0
0x180036036  movdqu  [rsp+118h+var_A8], xmm0
0x18003603c  mov     rax, [r14]
0x18003603f  lea     rdx, [rsp+118h+var_E0]
0x180036044  mov     rcx, r14
0x180036047  mov     rax, [rax+38h]
0x18003604b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036050  test    eax, eax
0x180036052  js      loc_18003630A
0x180036058  mov     esi, dword ptr [rsp+118h+var_E0]
0x18003605c  mov     rbx, [rsp+118h+pv]
0x180036064  mov     [rsp+118h+var_E0], rbx
0x180036069  test    rbx, rbx
0x18003606c  jz      short loc_180036075
0x18003606e  lock inc dword ptr [rbx+120h]
0x180036075  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18003607c  call    cs:__imp_EnterCriticalSection
0x180036082  inc     dword ptr [rbx+0F0h]
0x180036088  mov     [rbx+118h], esi
0x18003608e  lea     rcx, [rsp+118h+var_E0]
0x180036093  call    ??1?$test_data_control@V?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>::~test_data_control<tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>>(void)
0x180036098  mov     dword ptr [rsp+118h+var_E0], edi
0x18003609c  mov     [rsp+118h+var_B0], edi
0x1800360a0  xorps   xmm0, xmm0
0x1800360a3  movdqu  [rsp+118h+var_A8], xmm0
0x1800360a9  mov     rax, [r14]
0x1800360ac  lea     rdx, [rsp+118h+var_E0]
0x1800360b1  mov     rcx, r14
0x1800360b4  mov     rax, [rax+40h]
0x1800360b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360bd  test    eax, eax
0x1800360bf  js      loc_180036316
0x1800360c5  mov     esi, dword ptr [rsp+118h+var_E0]
0x1800360c9  test    esi, esi
0x1800360cb  jns     short loc_1800360EA
0x1800360cd  mov     rcx, [rsp+118h]; this
0x1800360d5  mov     r9d, esi; char *
0x1800360d8  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800360df  mov     edx, 5D0h; void *
0x1800360e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800360e9  nop
0x1800360ea  test    r14, r14
0x1800360ed  jz      short loc_1800360FA
0x1800360ef  lea     rcx, [rsp+118h+var_D0]
0x1800360f4  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800360f9  nop
0x1800360fa  cmp     [rsp+118h+var_C0], rdi
0x1800360ff  jz      short loc_18003610C
0x180036101  lea     rcx, [rsp+118h+var_C0]
0x180036106  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18003610b  nop
0x18003610c  mov     rbx, [rsp+118h+pv]
0x180036114  test    rbx, rbx
0x180036117  jz      short loc_18003613A
0x180036119  mov     eax, r12d
0x18003611c  lock xadd [rbx+120h], eax
0x180036124  add     eax, r12d
0x180036127  jnz     short loc_18003613A
0x180036129  mov     rcx, rbx
0x18003612c  call    ??1?$merged_data@U_tip_AIFabricAPIsPerfTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>::~merged_data<_tip_AIFabricAPIsPerfTest,_tip_AIFabricAPIsPerfTest>(void)
0x180036131  mov     rcx, rbx; pv
0x180036134  call    cs:__imp_CoTaskMemFree
0x18003613a  lea     rcx, [rsp+118h+var_70]; this
0x180036142  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180036147  nop
0x180036148  cmp     [rsp+118h+var_B8], rdi
0x18003614d  jz      short loc_180036159
0x18003614f  lea     rcx, [rsp+118h+var_C8]
0x180036154  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180036159  mov     eax, esi
0x18003615b  jmp     loc_1800362DE
0x180036160  mov     rbx, [rsp+118h+pv]
0x180036168  lea     rsi, [rbx+0C8h]
0x18003616f  mov     rcx, rsi; lpCriticalSection
0x180036172  call    cs:__imp_EnterCriticalSection
0x180036178  or      dword ptr [rbx+48h], 300h
0x18003617f  cmp     [rbx+0F8h], rdi
0x180036186  jz      short loc_180036196
0x180036188  mov     edx, 2
  ... truncated ...
```
