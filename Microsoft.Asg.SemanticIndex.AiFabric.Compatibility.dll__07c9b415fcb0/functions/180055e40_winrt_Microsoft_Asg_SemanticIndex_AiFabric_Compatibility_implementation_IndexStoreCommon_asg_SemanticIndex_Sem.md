# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::QueryCore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,asg::SemanticPipelines::QueryEmbeddings const &,unsigned __int64,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticQueryOptions &,asg::CancellationToken)

- ea: `0x180055e40`
- end: `0x180056715`
- name: `?QueryCore@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AV?$tuple@V?$vector@UItemQueryMatch@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemQueryMatch@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@UQueryContinuationToken@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@AEBUQueryEmbeddings@345678@AEBUQueryEmbeddings@SemanticPipelines@asg@@_KAEAUSemanticQueryOptions@2345678@UCancellationToken@asg@@@Z`
- size: `2261`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180054220`

## callees

- `0x180003bd0`
- `0x180004280`
- `0x18000a930`
- `0x18000cc40`
- `0x180010dd0`
- `0x1800128e0`
- `0x18002c390`
- `0x18002f8e0`
- `0x180038920`
- `0x180039ba0`
- `0x18004c670`
- `0x180050550`
- `0x180055e40`
- `0x1801941b0`
- `0x1801d2b20`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206ec0`
- `0x18022ae90`
- `0x18022aeae`
- `0x180242120`

## string_xrefs

- `0x180055ebd`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.Collections.h`
- `0x18005608a`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.Collections.h`
- `0x180056116`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.Collections.h`

## pseudocode

```c
unsigned __int64 *winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::QueryCore(
        __int64 a1,
        unsigned __int64 *a2,
        __int64 *a3,
        __int64 a4,
        unsigned __int64 a5,
        ...)
{
  __int64 v5; // r13
  __int64 v6; // rdi
  int v7; // eax
  __int64 v8; // rcx
  char v9; // r12
  int v10; // ebx
  __int16 v11; // r14
  char v12; // r15
  unsigned __int64 v13; // rdi
  int v14; // esi
  unsigned __int64 v15; // rax
  __int128 *v16; // rcx
  __int64 v17; // rax
  volatile signed __int32 *v18; // rdi
  __int64 v19; // r14
  int v20; // eax
  void *v21; // r15
  unsigned int v22; // r12d
  unsigned int v23; // edi
  _OWORD *v24; // rax
  __int64 v25; // rdi
  __int64 v26; // r9
  int v27; // eax
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // rdi
  volatile signed __int32 *v31; // rsi
  __int64 v32; // rdi
  void *v33; // rcx
  __int64 v34; // rax
  volatile signed __int32 *v35; // rcx
  volatile signed __int32 *v36; // r14
  volatile signed __int32 *v37; // rdi
  __int64 v38; // rdi
  void *v39; // rcx
  __int64 v40; // rax
  volatile signed __int32 *v41; // rcx
  volatile signed __int32 *v42; // rsi
  volatile signed __int32 *v43; // rdi
  unsigned __int64 v44; // rdi
  _QWORD *v45; // rax
  unsigned __int64 v46; // rdi
  unsigned __int64 v47; // rdx
  unsigned __int64 v48; // rax
  volatile signed __int32 *v49; // rdi
  volatile signed __int32 *v50; // rdi
  int v52; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v53[4]; // [rsp+40h] [rbp-C8h] BYREF
  volatile signed __int32 *v54; // [rsp+60h] [rbp-A8h]
  __int64 v55; // [rsp+68h] [rbp-A0h]
  _OWORD *v56; // [rsp+70h] [rbp-98h]
  _BYTE v57[5]; // [rsp+78h] [rbp-90h]
  __int16 v58; // [rsp+7Dh] [rbp-8Bh]
  char v59; // [rsp+7Fh] [rbp-89h]
  int v60; // [rsp+80h] [rbp-88h] BYREF
  _Mtx_t pExceptionObject; // [rsp+88h] [rbp-80h] BYREF
  const char *v62; // [rsp+90h] [rbp-78h]
  __int64 v63; // [rsp+98h] [rbp-70h]
  volatile signed __int32 *v64; // [rsp+A8h] [rbp-60h]
  __int128 v65; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 v66; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int64 v67; // [rsp+D0h] [rbp-38h]
  unsigned __int64 v68; // [rsp+D8h] [rbp-30h]
  _DWORD v69[3]; // [rsp+E8h] [rbp-20h] BYREF
  char v70; // [rsp+F4h] [rbp-14h]
  unsigned __int64 v71; // [rsp+F8h] [rbp-10h]
  char v72; // [rsp+100h] [rbp-8h]
  int v73; // [rsp+101h] [rbp-7h]
  __int16 v74; // [rsp+105h] [rbp-3h]
  char v75; // [rsp+107h] [rbp-1h]
  int v76; // [rsp+108h] [rbp+0h]
  void *v77; // [rsp+110h] [rbp+8h]
  __int64 v78; // [rsp+118h] [rbp+10h]
  char v79; // [rsp+120h] [rbp+18h]
  char v80; // [rsp+130h] [rbp+28h]
  char v81; // [rsp+148h] [rbp+40h]
  __int128 v82; // [rsp+150h] [rbp+48h]
  __int128 v83; // [rsp+160h] [rbp+58h]
  _QWORD v84[3]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v85[32]; // [rsp+190h] [rbp+88h] BYREF
  volatile signed __int32 *v86; // [rsp+1B0h] [rbp+A8h]
  unsigned __int64 v91; // [rsp+250h] [rbp+148h] BYREF
  va_list va; // [rsp+250h] [rbp+148h]
  __int64 v93; // [rsp+258h] [rbp+150h]
  va_list va1; // [rsp+260h] [rbp+158h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v91 = va_arg(va1, _QWORD);
  v93 = va_arg(va1, _QWORD);
  memset(v53, 0, sizeof(v53));
  v54 = 0;
  v5 = v91;
  v6 = *(_QWORD *)(v91 + 40);
  v91 = v6;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  v52 = 0;
  LODWORD(pExceptionObject) = 584;
  v62 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windows"
        ".Foundation.Collections.h";
  v63 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v6 + 56LL))(v6, &v52);
  if ( v7 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v7, &pExceptionObject);
  }
  if ( v6 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref((unsigned __int64 *)va);
  v8 = *(_QWORD *)(v5 + 28);
  v9 = 0;
  v10 = *(_DWORD *)&v57[1];
  v11 = v58;
  v12 = v59;
  if ( BYTE4(v8) )
  {
    v13 = a5;
    if ( (unsigned int)v8 < a5 )
      v13 = (unsigned int)v8;
    v9 = 1;
  }
  else
  {
    v13 = v91;
  }
  v14 = *(_DWORD *)(v5 + 24) & 1 | 2;
  if ( (*(_BYTE *)(v5 + 24) & 2) == 0 )
    v14 = *(_DWORD *)(v5 + 24) & 1;
  v91 = *(_QWORD *)(v5 + 48);
  v15 = HIDWORD(v91);
  if ( !BYTE4(v91) )
  {
    LODWORD(v91) = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DefaultQueryDistanceThreshold(a1);
    BYTE4(v91) = 1;
    v15 = HIDWORD(v91);
  }
  v69[0] = 0;
  if ( !(_BYTE)v15 )
    std::_Throw_bad_optional_access();
  v69[1] = v91;
  v70 = 0;
  v71 = v13;
  v72 = v9;
  v73 = v10;
  v74 = v11;
  v75 = v12;
  v76 = v14;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0u;
  v83 = 0u;
  if ( (unsigned __int8)asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_58375376>>() )
  {
    v16 = (__int128 *)v93;
    v17 = *(_QWORD *)(v93 + 8);
    if ( v17 )
      _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
    v18 = (volatile signed __int32 *)*((_QWORD *)&v83 + 1);
    v83 = *v16;
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
  }
  v19 = *(_QWORD *)(v5 + 40);
  *(_QWORD *)&v65 = v19;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
  LODWORD(v91) = 0;
  LODWORD(pExceptionObject) = 584;
  v62 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windows"
        ".Foundation.Collections.h";
  v63 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v19 + 56LL))(v19, (unsigned __int64 *)va);
  if ( v20 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v20, &pExceptionObject);
  }
  v21 = 0;
  v56 = 0;
  v22 = 0;
  *(_DWORD *)v57 = 0;
  v23 = v91;
  if ( (_DWORD)v91 )
  {
    v24 = WINRT_IMPL_CoTaskMemAlloc(16LL * (unsigned int)v91);
    v21 = v24;
    v56 = v24;
    if ( !v24 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)&pExceptionObject);
      throw (std::bad_alloc *)&pExceptionObject;
    }
    v22 = v23;
    *(_DWORD *)v57 = v23;
    if ( v23 )
    {
      *v24 = 0;
      qmemcpy(v24 + 1, v24, 8 * ((16 * (unsigned __int64)v23 - 9) >> 3));
    }
  }
  if ( v19 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v65);
  v25 = *(_QWORD *)(v5 + 40);
  *(_QWORD *)&v65 = v25;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
  LODWORD(v91) = 0;
  LODWORD(pExceptionObject) = 734;
  v62 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windows"
        ".Foundation.Collections.h";
  v63 = 0;
  v26 = 4;
  if ( v22 )
    v26 = (__int64)v21;
  v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, unsigned __int64 *))(*(_QWORD *)v25 + 128LL))(
          v25,
          0,
          v22,
          v26,
          (unsigned __int64 *)va);
  if ( v27 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v27, &pExceptionObject);
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v65);
  if ( v52 )
  {
    v77 = v21;
    v78 = v22;
    if ( !v79 )
      v79 = 1;
  }
  if ( (unsigned __int8)asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_58362677>>() )
  {
    v65 = 0;
    LOBYTE(v28) = 1;
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
      a1,
      &pExceptionObject,
      v28);
    v29 = *(_QWORD *)(a1 + 176);
    if ( v29 )
      _InterlockedIncrement((volatile signed __int32 *)(v29 + 8));
    v30 = *(_QWORD *)(a1 + 168);
    *(_QWORD *)&v65 = v30;
    v31 = *(volatile signed __int32 **)(a1 + 176);
    *((_QWORD *)&v65 + 1) = v31;
    if ( (_BYTE)v62 )
      Mtx_unlock(pExceptionObject);
    v32 = asg::SemanticIndex::SemanticIndexStore::Match(v30, &pExceptionObject, a4, v69);
    if ( v53 != (_QWORD *)v32 )
    {
      v33 = (void *)v53[0];
      if ( v53[0] )
      {
        if ( ((v53[2] - v53[0]) & 0xFFFFFFFFFFFFFFC0uLL) >= 0x1000 )
        {
          _mm_lfence();
          v33 = *(void **)(v53[0] - 8LL);
          if ( (unsigned __int64)(v53[0] - (_QWORD)v33 - 8LL) > 0x1F )
            invoke_watson(0, 0, 0, 0, 0);
        }
        operator delete(v33);
        memset(v53, 0, 24);
      }
      v53[0] = *(_QWORD *)v32;
      *(_OWORD *)&v53[1] = *(_OWORD *)(v32 + 8);
      *(_QWORD *)v32 = 0;
      *(_QWORD *)(v32 + 8) = 0;
      *(_QWORD *)(v32 + 16) = 0;
    }
    v34 = *(_QWORD *)(v32 + 24);
    v35 = *(volatile signed __int32 **)(v32 + 32);
    *(_QWORD *)(v32 + 24) = 0;
    *(_QWORD *)(v32 + 32) = 0;
    v53[3] = v34;
    v36 = v54;
    v54 = v35;
    if ( v36 )
    {
      if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
        if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
      }
    }
    LODWORD(v55) = *(_DWORD *)(v32 + 40);
    v37 = v64;
    if ( v64 )
    {
      if ( _InterlockedExchangeAdd(v64 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
        if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
      }
    }
    std::vector<asg::SemanticIndex::ItemMatch>::_Tidy(&pExceptionObject);
    if ( v31 )
    {
      if ( _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
  }
  else
  {
    LOBYTE(v28) = 1;
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
      a1,
      &pExceptionObject,
      v28);
    v38 = asg::SemanticIndex::SemanticIndexStore::Match(*(_QWORD *)(a1 + 168), v85, a4, v69);
    if ( v53 != (_QWORD *)v38 )
    {
      v39 = (void *)v53[0];
      if ( v53[0] )
      {
        if ( ((v53[2] - v53[0]) & 0xFFFFFFFFFFFFFFC0uLL) >= 0x1000 )
        {
          _mm_lfence();
          v39 = *(void **)(v53[0] - 8LL);
          if ( (unsigned __int64)(v53[0] - (_QWORD)v39 - 8LL) > 0x1F )
            invoke_watson(0, 0, 0, 0, 0);
        }
        operator delete(v39);
        memset(v53, 0, 24);
      }
      v53[0] = *(_QWORD *)v38;
      *(_OWORD *)&v53[1] = *(_OWORD *)(v38 + 8);
      *(_QWORD *)v38 = 0;
      *(_QWORD *)(v38 + 8) = 0;
      *(_QWORD *)(v38 + 16) = 0;
    }
    v40 = *(_QWORD *)(v38 + 24);
    v41 = *(volatile signed __int32 **)(v38 + 32);
    *(_QWORD *)(v38 + 24) = 0;
    *(_QWORD *)(v38 + 32) = 0;
    v53[3] = v40;
    v42 = v54;
    v54 = v41;
    if ( v42 )
    {
      if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
        if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
      }
    }
    LODWORD(v55) = *(_DWORD *)(v38 + 40);
    v43 = v86;
    if ( v86 )
    {
      if ( _InterlockedExchangeAdd(v86 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
        if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
      }
    }
    std::vector<asg::SemanticIndex::ItemMatch>::_Tidy(v85);
    if ( (_BYTE)v62 )
      Mtx_unlock(pExceptionObject);
  }
  v60 = 0;
  v84[0] = v53;
  v84[1] = a1;
  v84[2] = &v60;
  v91 = 0;
  v44 = 0;
  if ( v53[3] && !*(_BYTE *)(v53[3] + 488LL) )
  {
    v45 = winrt::impl::create_and_initialize<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryContinuationToken,std::shared_ptr<asg::SemanticIndex::DiskAnn::QueryContinuationData const> &,asg::SemanticIndex::MatchOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &>(
            (__int128 *)&v53[3],
            (__int64)v69,
            a3);
    v44 = (unsigned __int64)(v45 + 2);
    if ( !v45 )
      v44 = 0;
    v91 = v44;
  }
  ___ToVector_V__transform_view_V__ref_view_V__vector_UItemMatch_SemanticIndex_asg__V__allocator_UItemMatch_SemanticIndex_asg___std___std___ranges_std__V_lambda_1___1__QueryCore___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AV__tuple_V__vector_UItemQueryMatch_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__V__allocator_UItemQueryMatch_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___std___std__UQueryContinuationToken_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___3_AEBUQueryEmbeddings_89SemanticIndex_Asg_Microsoft_winrt__AEBUQueryEmbeddings_SemanticPipelines_asg___KAEAUSemanticQueryOptions_789SemanticIndex_Asg_Microsoft_winrt__UCancellationToken_asg___Z__ranges_std___implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__YA_A_P__QEAV__transform_view_V__ref_view_V__vector_UItemMatch_SemanticIndex_asg__V__allocator_UItemMatch_SemanticIndex_asg___std___std___ranges_std__V_lambda_1___1__QueryCore___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AV__tuple_V__vector_UItemQueryMatch_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__V__allocator_UItemQueryMatch_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___std___std__UQueryContinuationToken_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___3_AEBUQueryEmbeddings_89SemanticIndex_Asg_Microsoft_winrt__AEBUQueryEmbeddings_SemanticPipelines_asg___KAEAUSemanticQueryOptions_789SemanticIndex_Asg_Microsoft_winrt__UCancellationToken_asg___Z__ranges_std___Z(
    &v66,
    v84);
  *a2 = v44;
  v46 = v68;
  v68 = 0;
  v47 = v67;
  v67 = 0;
  v48 = v66;
  v66 = 0;
  a2[1] = v48;
  a2[2] = v47;
  a2[3] = v46;
  if ( v21 )
    CoTaskMemFree_0(v21);
  asg::SemanticIndex::MatchOptions::~MatchOptions((asg::SemanticIndex::MatchOptions *)v69);
  v49 = v54;
  if ( v54 )
  {
    if ( _InterlockedExchangeAdd(v54 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
      if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
    }
  }
  std::vector<asg::SemanticIndex::ItemMatch>::_Tidy(v53);
  v50 = *(volatile signed __int32 **)(v93 + 8);
  if ( v50 )
  {
    if ( _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
      if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180055e40  mov     rax, rsp
0x180055e43  mov     [rax+20h], r9
0x180055e47  mov     [rax+18h], r8
0x180055e4b  mov     [rax+10h], rdx
0x180055e4f  mov     [rax+8], rcx
0x180055e53  push    rbp
0x180055e54  push    rbx
0x180055e55  push    rsi
0x180055e56  push    rdi
0x180055e57  push    r12
0x180055e59  push    r13
0x180055e5b  push    r14
0x180055e5d  push    r15
0x180055e5f  lea     rbp, [rax-118h]
0x180055e66  sub     rsp, 1D8h
0x180055e6d  movaps  xmmword ptr [rax-58h], xmm6
0x180055e71  xor     esi, esi
0x180055e73  xorps   xmm0, xmm0
0x180055e76  movdqu  [rsp+210h+var_1E0+8], xmm0
0x180055e7c  xorps   xmm1, xmm1
0x180055e7f  movdqu  [rsp+210h+var_1D0+8], xmm1
0x180055e85  mov     [rsp+210h+var_1B8], rsi
0x180055e8a  mov     r13, [rbp+110h+arg_28]
0x180055e91  mov     rdi, [r13+28h]
0x180055e95  mov     [rbp+110h+arg_28], rdi
0x180055e9c  test    rdi, rdi
0x180055e9f  jz      short loc_180055EB2
0x180055ea1  mov     rax, [rdi]
0x180055ea4  mov     rcx, rdi
0x180055ea7  mov     rax, [rax+8]
0x180055eab  call    cs:__guard_dispatch_icall_fptr
0x180055eb1  nop
0x180055eb2  mov     dword ptr [rsp+210h+var_1E0], esi
0x180055eb6  mov     dword ptr [rbp+110h+pExceptionObject], 248h
0x180055ebd  lea     rax, aCW1SX64Release; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180055ec4  mov     [rbp+110h+var_188], rax
0x180055ec8  mov     [rbp+110h+var_180], rsi
0x180055ecc  mov     rax, [rdi]
0x180055ecf  lea     rdx, [rsp+210h+var_1E0]
0x180055ed4  mov     rcx, rdi
0x180055ed7  mov     rax, [rax+38h]
0x180055edb  call    cs:__guard_dispatch_icall_fptr
0x180055ee1  test    eax, eax
0x180055ee3  js      loc_1800566B3
0x180055ee9  test    rdi, rdi
0x180055eec  jz      short loc_180055EFA
0x180055eee  lea     rcx, [rbp+110h+arg_28]
0x180055ef5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180055efa  mov     rcx, [r13+1Ch]
0x180055efe  xor     r12b, r12b
0x180055f01  mov     rax, rcx
0x180055f04  shr     rax, 20h
0x180055f08  mov     ebx, dword ptr [rsp+210h+var_1A0+1]
0x180055f0c  movzx   r14d, [rsp+210h+var_19B]
0x180055f12  movzx   r15d, [rsp+210h+var_199]
0x180055f18  test    al, al
0x180055f1a  jz      short loc_180055F31
0x180055f1c  mov     eax, ecx
0x180055f1e  mov     rdi, [rbp+110h+arg_20]
0x180055f25  cmp     rax, rdi
0x180055f28  cmovb   rdi, rax
0x180055f2c  mov     r12b, 1
0x180055f2f  jmp     short loc_180055F38
0x180055f31  mov     rdi, [rbp+110h+arg_28]
0x180055f38  mov     ecx, [r13+18h]
0x180055f3c  and     ecx, 1
0x180055f3f  mov     esi, ecx
0x180055f41  or      esi, 2
0x180055f44  test    byte ptr [r13+18h], 2
0x180055f49  cmovz   esi, ecx
0x180055f4c  mov     rax, [r13+30h]
0x180055f50  mov     [rbp+110h+arg_28], rax
0x180055f57  shr     rax, 20h
0x180055f5b  test    al, al
0x180055f5d  jnz     short loc_180055F8C
0x180055f5f  mov     rcx, [rbp+110h+arg_0]
0x180055f66  call    ?DefaultQueryDistanceThreshold@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAAMXZ; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DefaultQueryDistanceThreshold(void)
0x180055f6b  movss   dword ptr [rbp+110h+arg_28], xmm0
0x180055f73  mov     byte ptr [rbp+110h+arg_28+4], 1
0x180055f7a  mov     rax, [rbp+110h+arg_28]
0x180055f81  mov     [rbp+110h+arg_28], rax
0x180055f88  shr     rax, 20h
0x180055f8c  mov     [rbp+110h+var_130], 0
0x180055f93  test    al, al
0x180055f95  jz      loc_1800566C2
0x180055f9b  movss   xmm0, dword ptr [rbp+110h+arg_28]
0x180055fa3  movss   [rbp+110h+var_12C], xmm0
0x180055fa8  mov     [rbp+110h+var_124], 0
0x180055fac  mov     [rbp+110h+var_120], rdi
0x180055fb0  mov     [rbp+110h+var_118], r12b
0x180055fb4  mov     [rbp+110h+var_117], ebx
0x180055fb7  mov     [rbp+110h+var_113], r14w
0x180055fbc  mov     [rbp+110h+var_111], r15b
0x180055fc0  mov     [rbp+110h+var_110], esi
0x180055fc3  mov     [rbp+110h+var_F8], 0
0x180055fc7  mov     [rbp+110h+var_E8], 0
0x180055fcb  mov     [rbp+110h+var_D0], 0
0x180055fcf  xorps   xmm0, xmm0
0x180055fd2  movups  [rbp+110h+var_C8], xmm0
0x180055fd6  xor     edi, edi
0x180055fd8  mov     qword ptr [rbp+110h+var_C8], rdi
0x180055fdc  mov     qword ptr [rbp+110h+var_C8+8], rdi
0x180055fe0  movups  [rbp+110h+var_B8], xmm0
0x180055fe4  mov     qword ptr [rbp+110h+var_B8], rdi
0x180055fe8  mov     qword ptr [rbp+110h+var_B8+8], rdi
0x180055fec  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_58375376@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_58375376>>(void)
0x180055ff1  mov     ebx, 0FFFFFFFFh
0x180055ff6  test    al, al
0x180055ff8  jz      short loc_18005605F
0x180055ffa  mov     rcx, [rbp+110h+arg_30]
0x180056001  mov     rax, [rcx+8]
0x180056005  test    rax, rax
0x180056008  jz      short loc_18005600E
0x18005600a  lock inc dword ptr [rax+8]
0x18005600e  mov     rax, [rcx]
0x180056011  mov     qword ptr [rbp+110h+var_B8], rax
0x180056015  mov     rdi, qword ptr [rbp+110h+var_B8+8]
0x180056019  mov     rax, [rcx+8]
0x18005601d  mov     qword ptr [rbp+110h+var_B8+8], rax
0x180056021  test    rdi, rdi
0x180056024  jz      short loc_18005605D
0x180056026  mov     eax, ebx
0x180056028  lock xadd [rdi+8], eax
0x18005602d  cmp     eax, 1
0x180056030  jnz     short loc_18005605D
0x180056032  mov     rax, [rdi]
0x180056035  mov     rcx, rdi
0x180056038  mov     rax, [rax]
0x18005603b  call    cs:__guard_dispatch_icall_fptr
0x180056041  mov     eax, ebx
0x180056043  lock xadd [rdi+0Ch], eax
0x180056048  cmp     eax, 1
0x18005604b  jnz     short loc_18005605D
0x18005604d  mov     rax, [rdi]
0x180056050  mov     rcx, rdi
0x180056053  mov     rax, [rax+8]
0x180056057  call    cs:__guard_dispatch_icall_fptr
0x18005605d  xor     edi, edi
0x18005605f  mov     r14, [r13+28h]
0x180056063  mov     qword ptr [rbp+110h+var_160], r14
0x180056067  test    r14, r14
0x18005606a  jz      short loc_18005607D
0x18005606c  mov     rax, [r14]
0x18005606f  mov     rcx, r14
0x180056072  mov     rax, [rax+8]
0x180056076  call    cs:__guard_dispatch_icall_fptr
0x18005607c  nop
0x18005607d  mov     dword ptr [rbp+110h+arg_28], edi
0x180056083  mov     dword ptr [rbp+110h+pExceptionObject], 248h
0x18005608a  lea     rsi, aCW1SX64Release; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180056091  mov     [rbp+110h+var_188], rsi
0x180056095  mov     [rbp+110h+var_180], rdi
0x180056099  mov     rax, [r14]
0x18005609c  lea     rdx, [rbp+110h+arg_28]
0x1800560a3  mov     rcx, r14
0x1800560a6  mov     rax, [rax+38h]
0x1800560aa  call    cs:__guard_dispatch_icall_fptr
0x1800560b0  test    eax, eax
0x1800560b2  js      loc_1800566C8
0x1800560b8  xorps   xmm6, xmm6
0x1800560bb  mov     r15, rdi
0x1800560be  mov     [rsp+68h], rdi
0x1800560c3  mov     r12d, edi
0x1800560c6  mov     dword ptr [rsp+210h+var_1A0], edi
0x1800560ca  mov     edi, dword ptr [rbp+110h+arg_28]
0x1800560d0  test    edi, edi
0x1800560d2  jz      short loc_18005611D
0x1800560d4  mov     ecx, edi
0x1800560d6  shl     rcx, 4; cb
0x1800560da  call    WINRT_IMPL_CoTaskMemAlloc
0x1800560df  mov     r15, rax
0x1800560e2  mov     [rsp+68h], rax
0x1800560e7  test    rax, rax
0x1800560ea  jz      loc_1800566D7
0x1800560f0  mov     r12d, edi
0x1800560f3  mov     dword ptr [rsp+210h+var_1A0], edi
0x1800560f7  test    edi, edi
0x1800560f9  jz      short loc_18005611D
0x1800560fb  movups  xmmword ptr [rax], xmm6
0x1800560fe  mov     ecx, edi
0x180056100  shl     rcx, 4
0x180056104  sub     rcx, 9
0x180056108  shr     rcx, 3
0x18005610c  lea     rdi, [rax+10h]
0x180056110  mov     rsi, rax
0x180056113  rep movsq
0x180056116  lea     rsi, aCW1SX64Release; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18005611d  test    r14, r14
0x180056120  jz      short loc_18005612B
0x180056122  lea     rcx, [rbp+110h+var_160]
0x180056126  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005612b  mov     rdi, [r13+28h]
0x18005612f  mov     qword ptr [rbp+110h+var_160], rdi
0x180056133  test    rdi, rdi
0x180056136  jz      short loc_180056149
0x180056138  mov     rax, [rdi]
0x18005613b  mov     rcx, rdi
0x18005613e  mov     rax, [rax+8]
0x180056142  call    cs:__guard_dispatch_icall_fptr
0x180056148  nop
0x180056149  xor     r13d, r13d
0x18005614c  mov     dword ptr [rbp+110h+arg_28], r13d
0x180056153  mov     dword ptr [rbp+110h+pExceptionObject], 2DEh
0x18005615a  mov     [rbp+110h+var_188], rsi
0x18005615e  mov     [rbp+110h+var_180], r13
0x180056162  mov     rax, [rdi]
0x180056165  mov     r9d, 4
0x18005616b  test    r12d, r12d
0x18005616e  cmovnz  r9, r15
0x180056172  lea     rcx, [rbp+110h+arg_28]
0x180056179  mov     [rsp+20h], rcx
0x18005617e  mov     r8d, r12d
0x180056181  xor     edx, edx
0x180056183  mov     rcx, rdi
0x180056186  mov     rax, [rax+80h]
0x18005618d  call    cs:__guard_dispatch_icall_fptr
0x180056193  test    eax, eax
0x180056195  js      loc_1800566F1
0x18005619b  lea     rcx, [rbp+110h+var_160]
0x18005619f  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800561a4  cmp     dword ptr [rsp+210h+var_1E0], r13d
0x1800561a9  jz      short loc_1800561C0
0x1800561ab  mov     eax, r12d
0x1800561ae  mov     [rbp+110h+var_108], r15
0x1800561b2  mov     [rbp+110h+var_100], rax
0x1800561b6  cmp     [rbp+110h+var_F8], r13b
0x1800561ba  jnz     short loc_1800561C0
0x1800561bc  mov     [rbp+110h+var_F8], 1
0x1800561c0  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_58362677@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_58362677>>(void)
0x1800561c5  test    al, al
0x1800561c7  jz      loc_1800563B7
0x1800561cd  xorps   xmm0, xmm0
0x1800561d0  movdqu  [rbp+110h+var_160], xmm0
0x1800561d5  mov     r8b, 1
0x1800561d8  lea     rdx, [rbp+110h+pExceptionObject]
0x1800561dc  mov     rsi, [rbp+110h+arg_0]
0x1800561e3  mov     rcx, rsi
0x1800561e6  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x1800561eb  mov     rax, [rsi+0B0h]
0x1800561f2  test    rax, rax
0x1800561f5  jz      short loc_1800561FB
0x1800561f7  lock inc dword ptr [rax+8]
0x1800561fb  mov     rdi, [rsi+0A8h]
0x180056202  mov     qword ptr [rbp+110h+var_160], rdi
0x180056206  mov     rsi, [rsi+0B0h]
0x18005620d  mov     qword ptr [rbp+110h+var_160+8], rsi
0x180056211  cmp     byte ptr [rbp+110h+var_188], 0
0x180056215  jz      short loc_180056220
0x180056217  mov     rcx, [rbp+110h+pExceptionObject]; _Mtx_t
0x18005621b  call    _Mtx_unlock
0x180056220  lea     r9, [rbp+110h+var_130]
0x180056224  mov     r8, [rbp+110h+arg_18]
0x18005622b  lea     rdx, [rbp+110h+pExceptionObject]
0x18005622f  mov     rcx, rdi
0x180056232  call    ?Match@SemanticIndexStore@SemanticIndex@asg@@QEBA?AUMatchResult@23@AEBUQueryEmbeddings@SemanticPipelines@3@AEBUMatchOptions@23@@Z; asg::SemanticIndex::SemanticIndexStore::Match(asg::SemanticPipelines::QueryEmbeddings const &,asg::SemanticIndex::MatchOptions const &)
0x180056237  mov     rdi, rax
0x18005623a  lea     rax, [rsp+210h+var_1E0+8]
0x18005623f  cmp     rax, rdi
0x180056242  jz      short loc_1800562BC
0x180056244  mov     rcx, qword ptr [rsp+210h+var_1E0+8]
0x180056249  test    rcx, rcx
0x18005624c  jz      short loc_180056297
0x18005624e  mov     rdx, qword ptr [rsp+210h+var_1D0+8]
0x180056253  sub     rdx, rcx
0x180056256  and     rdx, 0FFFFFFFFFFFFFFC0h
0x18005625a  cmp     rdx, 1000h
0x180056261  jb      short loc_180056284
0x180056263  lfence
0x180056266  add     rdx, 27h ; '''
0x18005626a  mov     rax, qword ptr [rsp+210h+var_1E0+8]
0x18005626f  mov     rcx, [rax-8]; Block
0x180056273  sub     rax, rcx
0x180056276  sub     rax, 8
0x18005627a  cmp     rax, 1Fh
0x18005627e  ja      loc_180056700
0x180056284  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180056289  xorps   xmm0, xmm0
0x18005628c  movdqu  [rsp+210h+var_1E0+8], xmm0
0x180056292  mov     qword ptr [rsp+210h+var_1D0+8], r13
0x180056297  mov     rax, [rdi]
0x18005629a  mov     qword ptr [rsp+210h+var_1E0+8], rax
0x18005629f  mov     rax, [rdi+8]
0x1800562a3  mov     qword ptr [rsp+210h+var_1D0], rax
0x1800562a8  mov     rax, [rdi+10h]
0x1800562ac  mov     qword ptr [rsp+210h+var_1D0+8], rax
0x1800562b1  mov     [rdi], r13
0x1800562b4  mov     [rdi+8], r13
0x1800562b8  mov     [rdi+10h], r13
0x1800562bc  mov     rax, [rdi+18h]
0x1800562c0  mov     rcx, [rdi+20h]
0x1800562c4  mov     [rdi+18h], r13
0x1800562c8  mov     [rdi+20h], r13
0x1800562cc  mov     [rsp+210h+var_1C0], rax
0x1800562d1  mov     r14, [rsp+210h+var_1B8]
0x1800562d6  mov     [rsp+210h+var_1B8], rcx
0x1800562db  test    r14, r14
0x1800562de  jz      short loc_180056319
0x1800562e0  mov     eax, ebx
0x1800562e2  lock xadd [r14+8], eax
0x1800562e8  cmp     eax, 1
  ... truncated ...
```
