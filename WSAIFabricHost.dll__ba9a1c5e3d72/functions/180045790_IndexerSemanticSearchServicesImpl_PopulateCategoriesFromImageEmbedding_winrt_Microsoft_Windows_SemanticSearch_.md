# IndexerSemanticSearchServicesImpl::PopulateCategoriesFromImageEmbedding(winrt::Microsoft::Windows::SemanticSearch::Embedding const &,tagSAFEARRAY * *)

- ea: `0x180045790`
- end: `0x180045f76`
- name: `?PopulateCategoriesFromImageEmbedding@IndexerSemanticSearchServicesImpl@@AEAAJAEBUEmbedding@SemanticSearch@Windows@Microsoft@winrt@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `2022`
- prototype: `__int64 __fastcall(IndexerSemanticSearchServicesImpl *__hidden this, const struct winrt::Microsoft::Windows::SemanticSearch::Embedding *, struct tagSAFEARRAY **)`
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180045f80`
- `0x180046140`

## callees

- `0x180007fae`
- `0x18000b064`
- `0x18000c478`
- `0x180019c3c`
- `0x18002d010`
- `0x18002dabc`
- `0x18002f9e4`
- `0x180031950`
- `0x180031c34`
- `0x1800326e8`
- `0x180032dd8`
- `0x180034540`
- `0x180034e80`
- `0x180045790`
- `0x18004dbdc`
- `0x18004ddf0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045c4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045dbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045c4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045dbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045c22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045d90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045e71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045c22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045d90`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045e23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045f06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045cab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045e23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045f06`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180045dc6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180045dc6`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180045cf1`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180045cf1`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180045b83`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180045b83`

## string_xrefs

- `0x1800457c9`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\semanticsupportimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall IndexerSemanticSearchServicesImpl::PopulateCategoriesFromImageEmbedding(
        IndexerSemanticSearchServicesImpl *this,
        const struct winrt::Microsoft::Windows::SemanticSearch::Embedding *a2,
        struct tagSAFEARRAY **a3)
{
  __int64 v6; // rcx
  unsigned int v7; // r15d
  void *v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // r12
  int v11; // eax
  int v12; // eax
  __int64 (__fastcall ***v13)(_QWORD, __int64 *, __int64 *); // rbx
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  __int64 *v18; // r13
  __int64 *v19; // r14
  __int64 v20; // rcx
  __int64 v21; // rax
  _BYTE *v22; // rdi
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // eax
  unsigned __int8 *v26; // r14
  signed int v27; // r15d
  _DWORD *v28; // rdi
  SAFEARRAY *Vector; // rdi
  _DWORD *v30; // rdi
  _DWORD *v31; // rdi
  _DWORD *v32; // rdi
  struct _RTL_CRITICAL_SECTION *v33; // r15
  void *v34; // rbx
  __int64 v35; // rax
  HRESULT v36; // r13d
  _DWORD *v37; // r15
  _DWORD *v38; // r15
  _DWORD *v39; // r15
  struct _RTL_CRITICAL_SECTION *v40; // r13
  void *v41; // rbx
  _DWORD *v42; // rdi
  struct _RTL_CRITICAL_SECTION *v43; // r15
  void *v44; // rbx
  int v45; // [rsp+20h] [rbp-108h]
  LPVOID p_rgIndices; // [rsp+30h] [rbp-F8h] BYREF
  __int64 v47; // [rsp+38h] [rbp-F0h] BYREF
  ULONG cElements[2]; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v49; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v50; // [rsp+50h] [rbp-D8h] BYREF
  LPVOID v51; // [rsp+58h] [rbp-D0h] BYREF
  __int64 v52; // [rsp+60h] [rbp-C8h] BYREF
  __int128 v53; // [rsp+68h] [rbp-C0h]
  __int64 *v54; // [rsp+78h] [rbp-B0h]
  _BYTE v55[8]; // [rsp+80h] [rbp-A8h] BYREF
  _BYTE v56[48]; // [rsp+88h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp-70h]
  int v58; // [rsp+C0h] [rbp-68h] BYREF
  __int128 v59; // [rsp+C8h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]
  struct tagSAFEARRAY **v61; // [rsp+140h] [rbp+18h] BYREF
  __int64 (__fastcall ***rgIndices)(_QWORD, __int64 *, __int64 *); // [rsp+148h] [rbp+20h] BYREF

  v61 = a3;
  if ( a3 )
  {
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>>(v55);
    v7 = winrt::impl::consume_Microsoft_Windows_SemanticSearch_IEmbedding<winrt::Microsoft::Windows::SemanticSearch::IEmbedding>::ByteLength(a2);
    if ( (v7 & 3) != 0 )
    {
      v8 = pv;
      if ( pv )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
        {
          tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(v8);
          CoTaskMemFree(v8);
        }
      }
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v56);
      return 2147500037LL;
    }
    else
    {
      LODWORD(rgIndices) = v7;
      p_rgIndices = &rgIndices;
      v54 = &qword_1800AF078;
      _InterlockedIncrement64(&qword_1800AF078);
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::MemoryBuffer,winrt::Windows::Foundation::IMemoryBufferFactory> )
      {
        winrt::impl::consume_Windows_Storage_Streams_IBufferFactory<winrt::Windows::Storage::Streams::IBufferFactory>::Create(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::MemoryBuffer,winrt::Windows::Foundation::IMemoryBufferFactory>,
          &v49,
          (unsigned int)rgIndices);
        _InterlockedDecrement64(&qword_1800AF078);
      }
      else
      {
        _InterlockedDecrement64(&qword_1800AF078);
        winrt::impl::factory_cache_entry<winrt::Windows::Foundation::MemoryBuffer,winrt::Windows::Foundation::IMemoryBufferFactory>::call<_lambda_ef09b9dc8738d2f6e100a7a74329b9c2_ &>(
          v6,
          &v49,
          &p_rgIndices);
      }
      LODWORD(rgIndices) = 0;
      v9 = *(_QWORD *)a2;
      LODWORD(v52) = 0;
      v53 = 0;
      v10 = v49;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v9 + 80LL))(
              v9,
              v49,
              (LPVOID *)&rgIndices);
      if ( v11 < 0 )
        winrt::throw_hresult((unsigned int)v11, &v52);
      rgIndices = 0;
      LODWORD(v52) = 0;
      v53 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *)))(*(_QWORD *)v10 + 48LL))(
              v10,
              &rgIndices);
      if ( v12 < 0 )
        winrt::throw_hresult((unsigned int)v12, &v52);
      v13 = rgIndices;
      v51 = rgIndices;
      *(_QWORD *)cElements = 0;
      LODWORD(rgIndices) = 0;
      v58 = 0;
      v59 = 0;
      v47 = 0;
      if ( v51 )
      {
        LODWORD(v52) = 0;
        v53 = 0;
        v15 = (**v13)(v13, winrt::impl::guid_v<winrt::impl::IMemoryBufferByteAccess>, &v47);
        if ( v15 < 0 )
          winrt::throw_hresult((unsigned int)v15, &v52);
        v14 = v47;
      }
      else
      {
        v14 = 0;
      }
      v16 = (*(__int64 (__fastcall **)(__int64, ULONG *, LPVOID *))(*(_QWORD *)v14 + 24LL))(
              v14,
              cElements,
              (LPVOID *)&rgIndices);
      if ( v16 < 0 )
        winrt::throw_hresult((unsigned int)v16, &v58);
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v47);
      v18 = *(__int64 **)cElements;
      v54 = *(__int64 **)cElements;
      LODWORD(v47) = v7;
      v52 = 0;
      LODWORD(v53) = 0;
      LODWORD(rgIndices) = 0;
      v19 = (__int64 *)((char *)this + 176);
      if ( !*v19 )
      {
        p_rgIndices = &qword_1800AF598;
        _InterlockedIncrement64(&qword_1800AF598);
        if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Search::Indexer::AutoCategorizer,winrt::Windows::Foundation::IActivationFactory> )
        {
          _lambda_0a59f8c016b120c5d3cd56dab679a519_::operator()(
            v17,
            &v50,
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Search::Indexer::AutoCategorizer,winrt::Windows::Foundation::IActivationFactory>);
          _InterlockedDecrement64(&qword_1800AF598);
        }
        else
        {
          _InterlockedDecrement64(&qword_1800AF598);
          p_rgIndices = _lambda_0a59f8c016b120c5d3cd56dab679a519_::_lambda_invoker_cdecl_;
          winrt::impl::factory_cache_entry<winrt::Windows::Internal::Search::Indexer::AutoCategorizer,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Internal::Search::Indexer::AutoCategorizer (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
            v17,
            &v50,
            &p_rgIndices);
        }
        if ( v19 == &v50 )
        {
          v21 = v50;
        }
        else
        {
          if ( *v19 )
            winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(v19);
          v20 = v50;
          v21 = 0;
          v50 = 0;
          *v19 = v20;
        }
        if ( v21 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v50);
        v22 = pv;
        p_rgIndices = pv;
        if ( pv )
          _InterlockedIncrement((volatile signed __int32 *)pv + 72);
        tip2::details::shared_data<1,0,0>::begin_update(v22 + 8);
        v22[280] = 1;
        tip2::test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::~test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>(&p_rgIndices);
      }
      cElements[0] = 0;
      p_rgIndices = 0;
      v23 = *v19;
      v58 = 0;
      v59 = 0;
      v24 = 1;
      if ( v7 )
        v24 = (__int64)v18;
      v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, ULONG *, LPVOID *))(*(_QWORD *)v23 + 48LL))(
              v23,
              v7,
              v24,
              cElements,
              &p_rgIndices);
      if ( v25 < 0 )
        winrt::throw_hresult((unsigned int)v25, &v58);
      v26 = (unsigned __int8 *)p_rgIndices;
      v27 = cElements[0];
      v28 = pv;
      rgIndices = (__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *))pv;
      if ( pv )
        _InterlockedIncrement((volatile signed __int32 *)pv + 72);
      tip2::details::shared_data<1,0,0>::begin_update(v28 + 2);
      v28[69] = 0;
      tip2::test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::~test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>(&rgIndices);
      Vector = SafeArrayCreateVector(3u, 0, v27);
      if ( Vector )
      {
        LODWORD(rgIndices) = 0;
        v35 = 0;
        while ( (int)v35 < v27 )
        {
          LODWORD(v47) = v26[v35];
          v36 = SafeArrayPutElement(Vector, (LONG *)&rgIndices, &v47);
          cElements[0] = v36;
          if ( v36 < 0 )
          {
            v37 = pv;
            v61 = (struct tagSAFEARRAY **)pv;
            if ( pv )
              _InterlockedIncrement((volatile signed __int32 *)pv + 72);
            tip2::details::shared_data<1,0,0>::begin_update(v37 + 2);
            v37[68] = 7;
            tip2::test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::~test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>(&v61);
            v38 = pv;
            v61 = (struct tagSAFEARRAY **)pv;
            if ( pv )
              _InterlockedIncrement((volatile signed __int32 *)pv + 72);
            tip2::details::shared_data<1,0,0>::begin_update(v38 + 2);
            v38[69] = v36;
            tip2::test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::~test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>(&v61);
            v39 = pv;
            v40 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
            EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
            v39[18] |= 0x300u;
            if ( *((_QWORD *)v39 + 31) )
              tip2::details::shared_data<1,0,0>::complete_helper(v39 + 2, 2);
            if ( v40 )
              LeaveCriticalSection(v40);
            SafeArrayDestroy(Vector);
            if ( v26 )
              CoTaskMemFree_0(v26);
            if ( v13 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
            if ( v10 )
              winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v49);
            v41 = pv;
            if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
            {
              tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(v41);
              CoTaskMemFree(v41);
            }
            wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v56);
            return cElements[0];
          }
          v35 = (unsigned int)((_DWORD)rgIndices + 1);
          LODWORD(rgIndices) = (_DWORD)rgIndices + 1;
        }
        *v61 = Vector;
        v42 = pv;
        v43 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
        EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
        v42[18] |= 0x300u;
        if ( *((_QWORD *)v42 + 31) )
          tip2::details::shared_data<1,0,0>::complete_helper(v42 + 2, 2);
        if ( v43 )
          LeaveCriticalSection(v43);
        if ( v26 )
          CoTaskMemFree_0(v26);
        if ( v13 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
        if ( v10 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v49);
        v44 = pv;
        if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
        {
          tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(v44);
          CoTaskMemFree(v44);
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v56);
        return 0;
      }
      else
      {
        v30 = pv;
        v61 = (struct tagSAFEARRAY **)pv;
        if ( pv )
          _InterlockedIncrement((volatile signed __int32 *)pv + 72);
        tip2::details::shared_data<1,0,0>::begin_update(v30 + 2);
        v30[68] = 7;
        tip2::test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::~test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>(&v61);
        v31 = pv;
        v61 = (struct tagSAFEARRAY **)pv;
        if ( pv )
          _InterlockedIncrement((volatile signed __int32 *)pv + 72);
        tip2::details::shared_data<1,0,0>::begin_update(v31 + 2);
        v31[69] = -2147024882;
        tip2::test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::~test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>(&v61);
        v32 = pv;
        v33 = (struct _RTL_CRITICAL_SECTION *)((char *)pv + 200);
        EnterCriticalSection((LPCRITICAL_SECTION)pv + 5);
        v32[18] |= 0x300u;
        if ( *((_QWORD *)v32 + 31) )
          tip2::details::shared_data<1,0,0>::complete_helper(v32 + 2, 2);
        if ( v33 )
          LeaveCriticalSection(v33);
        if ( v26 )
          CoTaskMemFree_0(v26);
        if ( v13 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v51);
        if ( v10 )
          winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v49);
        v34 = pv;
        if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
        {
          tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(v34);
          CoTaskMemFree(v34);
        }
        wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v56);
        return 2147942414LL;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x606,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\semanticsupportimpl.cpp",
      (const char *)0x80004003LL,
      v45);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180045790  mov     [rsp+arg_10], r8
0x180045795  mov     [rsp+arg_0], rcx
0x18004579a  push    rbx
0x18004579b  push    rsi
0x18004579c  push    rdi
0x18004579d  push    r12
0x18004579f  push    r13
0x1800457a1  push    r14
0x1800457a3  push    r15
0x1800457a5  sub     rsp, 0F0h
0x1800457ac  mov     rbx, rdx
0x1800457af  mov     r14, rcx
0x1800457b2  xor     esi, esi
0x1800457b4  test    r8, r8
0x1800457b7  jnz     short loc_1800457E1
0x1800457b9  mov     rcx, [rsp+128h]; this
0x1800457c1  mov     ebx, 80004003h
0x1800457c6  mov     r9d, ebx; char *
0x1800457c9  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800457d0  mov     edx, 606h; void *
0x1800457d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800457da  mov     eax, ebx
0x1800457dc  jmp     loc_180045F1B
0x1800457e1  lea     rcx, [rsp+128h+var_A8]
0x1800457e9  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1800457ee  nop
0x1800457ef  mov     rcx, rbx
0x1800457f2  call    ?ByteLength@?$consume_Microsoft_Windows_SemanticSearch_IEmbedding@UIEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Windows_SemanticSearch_IEmbedding<winrt::Microsoft::Windows::SemanticSearch::IEmbedding>::ByteLength(void)
0x1800457f7  mov     r15d, eax
0x1800457fa  test    al, 3
0x1800457fc  jz      short loc_180045843
0x1800457fe  mov     rbx, [rsp+128h+pv]
0x180045806  test    rbx, rbx
0x180045809  jz      short loc_18004582C
0x18004580b  or      eax, 0FFFFFFFFh
0x18004580e  lock xadd [rbx+120h], eax
0x180045816  cmp     eax, 1
0x180045819  jnz     short loc_18004582C
0x18004581b  mov     rcx, rbx
0x18004581e  call    ??1?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(void)
0x180045823  mov     rcx, rbx; pv
0x180045826  call    cs:__imp_CoTaskMemFree
0x18004582c  lea     rcx, [rsp+128h+var_A0]; this
0x180045834  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180045839  mov     eax, 80004005h
0x18004583e  jmp     loc_180045F1B
0x180045843  mov     dword ptr [rsp+128h+rgIndices], r15d
0x18004584b  lea     rax, [rsp+128h+rgIndices]
0x180045853  mov     [rsp+128h+var_F8], rax
0x180045858  lea     rax, qword_1800AF078
0x18004585f  mov     [rsp+128h+var_B0], rax
0x180045864  lock inc cs:qword_1800AF078
0x18004586c  cmp     cs:??$factory_cache_entry_v@UMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferFactory@234@@impl@winrt@@3U?$factory_cache_entry@UMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferFactory@234@@12@A, rsi; factory_cache_entry<winrt::Windows::Foundation::MemoryBuffer,winrt::Windows::Foundation::IMemoryBufferFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::MemoryBuffer,winrt::Windows::Foundation::IMemoryBufferFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::MemoryBuffer,winrt::Windows::Foundation::IMemoryBufferFactory>
0x180045873  jz      short loc_180045899
0x180045875  mov     r8d, dword ptr [rsp+128h+rgIndices]
0x18004587d  lea     rdx, [rsp+128h+var_E0]
0x180045882  lea     rcx, ??$factory_cache_entry_v@UMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferFactory@234@@impl@winrt@@3U?$factory_cache_entry@UMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferFactory@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::MemoryBuffer,winrt::Windows::Foundation::IMemoryBufferFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::MemoryBuffer,winrt::Windows::Foundation::IMemoryBufferFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::MemoryBuffer,winrt::Windows::Foundation::IMemoryBufferFactory>
0x180045889  call    ?Create@?$consume_Windows_Storage_Streams_IBufferFactory@UIBufferFactory@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Storage_Streams_IBufferFactory<winrt::Windows::Storage::Streams::IBufferFactory>::Create(uint)
0x18004588e  nop
0x18004588f  lock dec cs:qword_1800AF078
0x180045897  jmp     short loc_1800458B1
0x180045899  lock dec cs:qword_1800AF078
0x1800458a1  lea     r8, [rsp+128h+var_F8]
0x1800458a6  lea     rdx, [rsp+128h+var_E0]
0x1800458ab  call    ??$call@AEAV_lambda_ef09b9dc8738d2f6e100a7a74329b9c2_@@@?$factory_cache_entry@UMemoryBuffer@Foundation@Windows@winrt@@UIMemoryBufferFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_ef09b9dc8738d2f6e100a7a74329b9c2_@@@Z
0x1800458b0  nop
0x1800458b1  mov     dword ptr [rsp+128h+rgIndices], esi
0x1800458b8  mov     rcx, [rbx]
0x1800458bb  mov     dword ptr [rsp+128h+var_C8], esi
0x1800458bf  xorps   xmm0, xmm0
0x1800458c2  movdqu  [rsp+128h+var_C0], xmm0
0x1800458c8  mov     rax, [rcx]
0x1800458cb  lea     r8, [rsp+128h+rgIndices]
0x1800458d3  mov     r12, [rsp+128h+var_E0]
0x1800458d8  mov     rdx, r12
0x1800458db  mov     rax, [rax+50h]
0x1800458df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458e4  test    eax, eax
0x1800458e6  js      loc_180045F2E
0x1800458ec  mov     [rsp+128h+rgIndices], rsi
0x1800458f4  mov     dword ptr [rsp+128h+var_C8], esi
0x1800458f8  xorps   xmm0, xmm0
0x1800458fb  movdqu  [rsp+128h+var_C0], xmm0
0x180045901  mov     rax, [r12]
0x180045905  lea     rdx, [rsp+128h+rgIndices]
0x18004590d  mov     rcx, r12
0x180045910  mov     rax, [rax+30h]
0x180045914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045919  test    eax, eax
0x18004591b  js      loc_180045F3B
0x180045921  mov     rbx, [rsp+128h+rgIndices]
0x180045929  mov     [rsp+128h+var_D0], rbx
0x18004592e  mov     qword ptr [rsp+128h+cElements], rsi
0x180045933  mov     dword ptr [rsp+128h+rgIndices], esi
0x18004593a  mov     [rsp+128h+var_68], esi
0x180045941  xorps   xmm0, xmm0
0x180045944  movdqu  [rsp+128h+var_60], xmm0
0x18004594d  mov     [rsp+128h+var_F0], rsi
0x180045952  test    rbx, rbx
0x180045955  jnz     short loc_18004595C
0x180045957  mov     rcx, rsi
0x18004595a  jmp     short loc_180045992
0x18004595c  mov     dword ptr [rsp+128h+var_C8], esi
0x180045960  movdqu  [rsp+128h+var_C0], xmm0
0x180045966  mov     rax, [rbx]
0x180045969  lea     r8, [rsp+128h+var_F0]
0x18004596e  lea     rdx, ??$guid_v@UIMemoryBufferByteAccess@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IMemoryBufferByteAccess>
0x180045975  mov     rcx, rbx
0x180045978  mov     rax, [rax]
0x18004597b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045980  test    eax, eax
0x180045982  js      loc_180045F48
0x180045988  mov     rcx, [rsp+128h+var_F0]
0x18004598d  mov     [rsp+128h+var_F0], rcx
0x180045992  mov     rax, [rcx]
0x180045995  lea     r8, [rsp+128h+rgIndices]
0x18004599d  lea     rdx, [rsp+128h+cElements]
0x1800459a2  mov     rax, [rax+18h]
0x1800459a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459ab  test    eax, eax
0x1800459ad  js      loc_180045F55
0x1800459b3  lea     rcx, [rsp+128h+var_F0]
0x1800459b8  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800459bd  mov     r13, qword ptr [rsp+128h+cElements]
0x1800459c2  mov     [rsp+128h+var_B0], r13
0x1800459c7  mov     dword ptr [rsp+128h+var_F0], r15d
0x1800459cc  mov     [rsp+128h+var_C8], rsi
0x1800459d1  mov     dword ptr [rsp+128h+var_C0], esi
0x1800459d5  mov     dword ptr [rsp+128h+rgIndices], esi
0x1800459dc  add     r14, 0B0h
0x1800459e3  cmp     [r14], rsi
0x1800459e6  jnz     loc_180045AB8
0x1800459ec  lea     rax, qword_1800AF598
0x1800459f3  mov     [rsp+128h+var_F8], rax
0x1800459f8  lock inc cs:qword_1800AF598
0x180045a00  cmp     cs:??$factory_cache_entry_v@UAutoCategorizer@Indexer@Search@Internal@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UAutoCategorizer@Indexer@Search@Internal@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A, rsi; factory_cache_entry<winrt::Windows::Internal::Search::Indexer::AutoCategorizer,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Internal::Search::Indexer::AutoCategorizer,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Search::Indexer::AutoCategorizer,winrt::Windows::Foundation::IActivationFactory>
0x180045a07  jz      short loc_180045A25
0x180045a09  lea     r8, ??$factory_cache_entry_v@UAutoCategorizer@Indexer@Search@Internal@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UAutoCategorizer@Indexer@Search@Internal@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A; factory_cache_entry<winrt::Windows::Internal::Search::Indexer::AutoCategorizer,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Internal::Search::Indexer::AutoCategorizer,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Internal::Search::Indexer::AutoCategorizer,winrt::Windows::Foundation::IActivationFactory>
0x180045a10  lea     rdx, [rsp+128h+var_D8]
0x180045a15  call    ??R_lambda_0a59f8c016b120c5d3cd56dab679a519_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_0a59f8c016b120c5d3cd56dab679a519_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180045a1a  nop
0x180045a1b  lock dec cs:qword_1800AF598
0x180045a23  jmp     short loc_180045A48
0x180045a25  lock dec cs:qword_1800AF598
0x180045a2d  lea     rax, ?_lambda_invoker_cdecl_@_lambda_0a59f8c016b120c5d3cd56dab679a519_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_0a59f8c016b120c5d3cd56dab679a519_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180045a34  mov     [rsp+128h+var_F8], rax
0x180045a39  lea     r8, [rsp+128h+var_F8]
0x180045a3e  lea     rdx, [rsp+128h+var_D8]
0x180045a43  call    ??$call@P6A?AUAutoCategorizer@Indexer@Search@Internal@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UAutoCategorizer@Indexer@Search@Internal@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAutoCategorizer@Indexer@Search@Internal@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z
0x180045a48  lea     rax, [rsp+128h+var_D8]
0x180045a4d  cmp     r14, rax
0x180045a50  jz      short loc_180045A71
0x180045a52  cmp     [r14], rsi
0x180045a55  jz      short loc_180045A5F
0x180045a57  mov     rcx, r14
0x180045a5a  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180045a5f  mov     rcx, [rsp+128h+var_D8]
0x180045a64  mov     rax, rsi
0x180045a67  mov     [rsp+128h+var_D8], rax
0x180045a6c  mov     [r14], rcx
0x180045a6f  jmp     short loc_180045A76
0x180045a71  mov     rax, [rsp+128h+var_D8]
0x180045a76  test    rax, rax
0x180045a79  jz      short loc_180045A85
0x180045a7b  lea     rcx, [rsp+128h+var_D8]
0x180045a80  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180045a85  mov     rdi, [rsp+128h+pv]
0x180045a8d  mov     [rsp+128h+var_F8], rdi
0x180045a92  test    rdi, rdi
0x180045a95  jz      short loc_180045A9E
0x180045a97  lock inc dword ptr [rdi+120h]
0x180045a9e  lea     rcx, [rdi+8]
0x180045aa2  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180045aa7  mov     byte ptr [rdi+118h], 1
0x180045aae  lea     rcx, [rsp+128h+var_F8]
0x180045ab3  call    ??1?$test_data_control@V?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::~test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>(void)
0x180045ab8  mov     [rsp+128h+cElements], esi
0x180045abc  mov     [rsp+128h+var_F8], rsi
0x180045ac1  mov     rcx, [r14]
0x180045ac4  mov     [rsp+128h+var_68], esi
0x180045acb  xorps   xmm0, xmm0
0x180045ace  movdqu  [rsp+128h+var_60], xmm0
0x180045ad7  mov     rax, [rcx]
0x180045ada  mov     r8d, 1
0x180045ae0  test    r15d, r15d
0x180045ae3  cmovnz  r8, r13
0x180045ae7  lea     rdx, [rsp+128h+var_F8]
0x180045aec  mov     qword ptr [rsp+128h+var_108], rdx
0x180045af1  lea     r9, [rsp+128h+cElements]
0x180045af6  mov     edx, r15d
0x180045af9  mov     rax, [rax+30h]
0x180045afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045b02  test    eax, eax
0x180045b04  js      loc_180045F65
0x180045b0a  jmp     short loc_180045B36
0x180045b0c  inc     dword ptr [rsp+128h+rgIndices]
0x180045b13  xor     esi, esi
0x180045b15  mov     r14, [rsp+128h+arg_0]
0x180045b1d  mov     r12, [rsp+128h+var_E0]
0x180045b22  mov     rbx, [rsp+128h+var_D0]
0x180045b27  mov     r15d, dword ptr [rsp+128h+var_F0]
0x180045b2c  mov     r13, [rsp+128h+var_B0]
0x180045b31  jmp     loc_1800459DC
0x180045b36  mov     r14, [rsp+128h+var_F8]
0x180045b3b  mov     r15d, [rsp+128h+cElements]
0x180045b40  mov     rdi, [rsp+128h+pv]
0x180045b48  mov     [rsp+128h+rgIndices], rdi
0x180045b50  test    rdi, rdi
0x180045b53  jz      short loc_180045B5C
0x180045b55  lock inc dword ptr [rdi+120h]
0x180045b5c  lea     rcx, [rdi+8]
0x180045b60  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180045b65  mov     [rdi+114h], esi
0x180045b6b  lea     rcx, [rsp+128h+rgIndices]
0x180045b73  call    ??1?$test_data_control@V?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::~test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>(void)
0x180045b78  nop
0x180045b79  mov     ecx, 3; vt
0x180045b7e  mov     r8d, r15d; cElements
0x180045b81  xor     edx, edx; lLbound
0x180045b83  call    cs:__imp_SafeArrayCreateVector
0x180045b89  mov     rdi, rax
0x180045b8c  test    rax, rax
0x180045b8f  jnz     loc_180045CC6
0x180045b95  mov     rdi, [rsp+128h+pv]
0x180045b9d  mov     [rsp+128h+arg_10], rdi
0x180045ba5  test    rdi, rdi
0x180045ba8  jz      short loc_180045BB1
0x180045baa  lock inc dword ptr [rdi+120h]
0x180045bb1  lea     rcx, [rdi+8]
0x180045bb5  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180045bba  mov     dword ptr [rdi+110h], 7
0x180045bc4  lea     rcx, [rsp+128h+arg_10]
0x180045bcc  call    ??1?$test_data_control@V?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::~test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>(void)
0x180045bd1  mov     rdi, [rsp+128h+pv]
0x180045bd9  mov     [rsp+128h+arg_10], rdi
0x180045be1  test    rdi, rdi
0x180045be4  jz      short loc_180045BED
0x180045be6  lock inc dword ptr [rdi+120h]
0x180045bed  lea     rcx, [rdi+8]
0x180045bf1  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180045bf6  mov     r13d, 8007000Eh
0x180045bfc  mov     [rdi+114h], r13d
0x180045c03  lea     rcx, [rsp+128h+arg_10]
0x180045c0b  call    ??1?$test_data_control@V?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>::~test_data_control<tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>>(void)
0x180045c10  mov     rdi, [rsp+128h+pv]
0x180045c18  lea     r15, [rdi+0C8h]
0x180045c1f  mov     rcx, r15; lpCriticalSection
0x180045c22  call    cs:__imp_EnterCriticalSection
0x180045c28  or      dword ptr [rdi+48h], 300h
0x180045c2f  cmp     [rdi+0F8h], rsi
0x180045c36  jz      short loc_180045C46
0x180045c38  mov     edx, 2
0x180045c3d  lea     rcx, [rdi+8]
0x180045c41  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x180045c46  test    r15, r15
0x180045c49  jz      short loc_180045C55
0x180045c4b  mov     rcx, r15; lpCriticalSection
0x180045c4e  call    cs:__imp_LeaveCriticalSection
0x180045c54  nop
0x180045c55  test    r14, r14
0x180045c58  jz      short loc_180045C63
0x180045c5a  mov     rcx, r14; pv
0x180045c5d  call    CoTaskMemFree_0
0x180045c62  nop
0x180045c63  test    rbx, rbx
0x180045c66  jz      short loc_180045C73
0x180045c68  lea     rcx, [rsp+128h+var_D0]
0x180045c6d  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180045c72  nop
0x180045c73  test    r12, r12
0x180045c76  jz      short loc_180045C83
0x180045c78  lea     rcx, [rsp+128h+var_E0]
0x180045c7d  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180045c82  nop
0x180045c83  mov     rbx, [rsp+128h+pv]
0x180045c8b  test    rbx, rbx
0x180045c8e  jz      short loc_180045CB1
0x180045c90  or      edx, 0FFFFFFFFh
0x180045c93  lock xadd [rbx+120h], edx
0x180045c9b  cmp     edx, 1
0x180045c9e  jnz     short loc_180045CB1
0x180045ca0  mov     rcx, rbx
0x180045ca3  call    ??1?$merged_data@U_tip_AutoCategorizationTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>::~merged_data<_tip_AutoCategorizationTest,_tip_AutoCategorizationTest>(void)
0x180045ca8  mov     rcx, rbx; pv
0x180045cab  call    cs:__imp_CoTaskMemFree
0x180045cb1  lea     rcx, [rsp+128h+var_A0]; this
0x180045cb9  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180045cbe  mov     eax, r13d
0x180045cc1  jmp     loc_180045F1B
0x180045cc6  mov     dword ptr [rsp+128h+rgIndices], esi
0x180045ccd  mov     eax, esi
0x180045ccf  cmp     eax, r15d
0x180045cd2  jge     loc_180045E54
0x180045cd8  movzx   ecx, byte ptr [rax+r14]
0x180045cdd  mov     dword ptr [rsp+128h+var_F0], ecx
0x180045ce1  lea     r8, [rsp+128h+var_F0]; pv
0x180045ce6  lea     rdx, [rsp+128h+rgIndices]; rgIndices
0x180045cee  mov     rcx, rdi; psa
0x180045cf1  call    cs:__imp_SafeArrayPutElement
0x180045cf7  mov     r13d, eax
  ... truncated ...
```
