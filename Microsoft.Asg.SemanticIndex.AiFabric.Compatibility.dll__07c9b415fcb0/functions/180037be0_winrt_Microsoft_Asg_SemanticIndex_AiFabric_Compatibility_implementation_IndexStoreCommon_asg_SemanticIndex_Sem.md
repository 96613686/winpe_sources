# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::QueryCore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,asg::SemanticPipelines::QueryEmbeddings const &,unsigned __int64,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticQueryOptions &,asg::CancellationToken)

- ea: `0x180037be0`
- end: `0x1800384b5`
- name: `?QueryCore@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AV?$tuple@V?$vector@UItemQueryMatch@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemQueryMatch@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@UQueryContinuationToken@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@AEBUQueryEmbeddings@345678@AEBUQueryEmbeddings@SemanticPipelines@asg@@_KAEAUSemanticQueryOptions@2345678@UCancellationToken@asg@@@Z`
- size: `2261`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002c8d0`

## callees

- `0x180003bd0`
- `0x180004280`
- `0x18000a930`
- `0x18000cc40`
- `0x180010dd0`
- `0x1800128e0`
- `0x18001ec80`
- `0x180026570`
- `0x18002c390`
- `0x18002f8e0`
- `0x180037be0`
- `0x180038920`
- `0x180039ba0`
- `0x1801941b0`
- `0x1801d2b20`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206ec0`
- `0x18022ae90`
- `0x18022aeae`
- `0x180242120`

## string_xrefs

- `0x180037c5d`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.Collections.h`
- `0x180037e2a`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.Collections.h`
- `0x180037eb6`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.Collections.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
unsigned __int64 *winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::QueryCore(
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
    LODWORD(v91) = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DefaultQueryDistanceThreshold(a1);
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
  ___ToVector_V__transform_view_V__ref_view_V__vector_UItemMatch_SemanticIndex_asg__V__allocator_UItemMatch_SemanticIndex_asg___std___std___ranges_std__V_lambda_1___1__QueryCore___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AV__tuple_V__vector_UItemQueryMatch_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__V__allocator_UItemQueryMatch_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___std___std__UQueryContinuationToken_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___3_AEBUQueryEmbeddings_89SemanticIndex_Asg_Microsoft_winrt__AEBUQueryEmbeddings_SemanticPipelines_asg___KAEAUSemanticQueryOptions_789SemanticIndex_Asg_Microsoft_winrt__UCancellationToken_asg___Z__ranges_std___implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__YA_A_P__QEAV__transform_view_V__ref_view_V__vector_UItemMatch_SemanticIndex_asg__V__allocator_UItemMatch_SemanticIndex_asg___std___std___ranges_std__V_lambda_1___1__QueryCore___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AV__tuple_V__vector_UItemQueryMatch_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__V__allocator_UItemQueryMatch_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___std___std__UQueryContinuationToken_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___3_AEBUQueryEmbeddings_89SemanticIndex_Asg_Microsoft_winrt__AEBUQueryEmbeddings_SemanticPipelines_asg___KAEAUSemanticQueryOptions_789SemanticIndex_Asg_Microsoft_winrt__UCancellationToken_asg___Z__ranges_std___Z(
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
0x180037be0  mov     rax, rsp
0x180037be3  mov     [rax+20h], r9
0x180037be7  mov     [rax+18h], r8
0x180037beb  mov     [rax+10h], rdx
0x180037bef  mov     [rax+8], rcx
0x180037bf3  push    rbp
0x180037bf4  push    rbx
0x180037bf5  push    rsi
0x180037bf6  push    rdi
0x180037bf7  push    r12
0x180037bf9  push    r13
0x180037bfb  push    r14
0x180037bfd  push    r15
0x180037bff  lea     rbp, [rax-118h]
0x180037c06  sub     rsp, 1D8h
0x180037c0d  movaps  xmmword ptr [rax-58h], xmm6
0x180037c11  xor     esi, esi
0x180037c13  xorps   xmm0, xmm0
0x180037c16  movdqu  [rsp+210h+var_1E0+8], xmm0
0x180037c1c  xorps   xmm1, xmm1
0x180037c1f  movdqu  [rsp+210h+var_1D0+8], xmm1
0x180037c25  mov     [rsp+210h+var_1B8], rsi
0x180037c2a  mov     r13, [rbp+110h+arg_28]
0x180037c31  mov     rdi, [r13+28h]
0x180037c35  mov     [rbp+110h+arg_28], rdi
0x180037c3c  test    rdi, rdi
0x180037c3f  jz      short loc_180037C52
0x180037c41  mov     rax, [rdi]
0x180037c44  mov     rcx, rdi
0x180037c47  mov     rax, [rax+8]
0x180037c4b  call    cs:__guard_dispatch_icall_fptr
0x180037c51  nop
0x180037c52  mov     dword ptr [rsp+210h+var_1E0], esi
0x180037c56  mov     dword ptr [rbp+110h+pExceptionObject], 248h
0x180037c5d  lea     rax, aCW1SX64Release; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180037c64  mov     [rbp+110h+var_188], rax
0x180037c68  mov     [rbp+110h+var_180], rsi
0x180037c6c  mov     rax, [rdi]
0x180037c6f  lea     rdx, [rsp+210h+var_1E0]
0x180037c74  mov     rcx, rdi
0x180037c77  mov     rax, [rax+38h]
0x180037c7b  call    cs:__guard_dispatch_icall_fptr
0x180037c81  test    eax, eax
0x180037c83  js      loc_180038453
0x180037c89  test    rdi, rdi
0x180037c8c  jz      short loc_180037C9A
0x180037c8e  lea     rcx, [rbp+110h+arg_28]
0x180037c95  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180037c9a  mov     rcx, [r13+1Ch]
0x180037c9e  xor     r12b, r12b
0x180037ca1  mov     rax, rcx
0x180037ca4  shr     rax, 20h
0x180037ca8  mov     ebx, dword ptr [rsp+210h+var_1A0+1]
0x180037cac  movzx   r14d, [rsp+210h+var_19B]
0x180037cb2  movzx   r15d, [rsp+210h+var_199]
0x180037cb8  test    al, al
0x180037cba  jz      short loc_180037CD1
0x180037cbc  mov     eax, ecx
0x180037cbe  mov     rdi, [rbp+110h+arg_20]
0x180037cc5  cmp     rax, rdi
0x180037cc8  cmovb   rdi, rax
0x180037ccc  mov     r12b, 1
0x180037ccf  jmp     short loc_180037CD8
0x180037cd1  mov     rdi, [rbp+110h+arg_28]
0x180037cd8  mov     ecx, [r13+18h]
0x180037cdc  and     ecx, 1
0x180037cdf  mov     esi, ecx
0x180037ce1  or      esi, 2
0x180037ce4  test    byte ptr [r13+18h], 2
0x180037ce9  cmovz   esi, ecx
0x180037cec  mov     rax, [r13+30h]
0x180037cf0  mov     [rbp+110h+arg_28], rax
0x180037cf7  shr     rax, 20h
0x180037cfb  test    al, al
0x180037cfd  jnz     short loc_180037D2C
0x180037cff  mov     rcx, [rbp+110h+arg_0]
0x180037d06  call    ?DefaultQueryDistanceThreshold@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAAMXZ; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::DefaultQueryDistanceThreshold(void)
0x180037d0b  movss   dword ptr [rbp+110h+arg_28], xmm0
0x180037d13  mov     byte ptr [rbp+110h+arg_28+4], 1
0x180037d1a  mov     rax, [rbp+110h+arg_28]
0x180037d21  mov     [rbp+110h+arg_28], rax
0x180037d28  shr     rax, 20h
0x180037d2c  mov     [rbp+110h+var_130], 0
0x180037d33  test    al, al
0x180037d35  jz      loc_180038462
0x180037d3b  movss   xmm0, dword ptr [rbp+110h+arg_28]
0x180037d43  movss   [rbp+110h+var_12C], xmm0
0x180037d48  mov     [rbp+110h+var_124], 0
0x180037d4c  mov     [rbp+110h+var_120], rdi
0x180037d50  mov     [rbp+110h+var_118], r12b
0x180037d54  mov     [rbp+110h+var_117], ebx
0x180037d57  mov     [rbp+110h+var_113], r14w
0x180037d5c  mov     [rbp+110h+var_111], r15b
0x180037d60  mov     [rbp+110h+var_110], esi
0x180037d63  mov     [rbp+110h+var_F8], 0
0x180037d67  mov     [rbp+110h+var_E8], 0
0x180037d6b  mov     [rbp+110h+var_D0], 0
0x180037d6f  xorps   xmm0, xmm0
0x180037d72  movups  [rbp+110h+var_C8], xmm0
0x180037d76  xor     edi, edi
0x180037d78  mov     qword ptr [rbp+110h+var_C8], rdi
0x180037d7c  mov     qword ptr [rbp+110h+var_C8+8], rdi
0x180037d80  movups  [rbp+110h+var_B8], xmm0
0x180037d84  mov     qword ptr [rbp+110h+var_B8], rdi
0x180037d88  mov     qword ptr [rbp+110h+var_B8+8], rdi
0x180037d8c  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_58375376@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_58375376>>(void)
0x180037d91  mov     ebx, 0FFFFFFFFh
0x180037d96  test    al, al
0x180037d98  jz      short loc_180037DFF
0x180037d9a  mov     rcx, [rbp+110h+arg_30]
0x180037da1  mov     rax, [rcx+8]
0x180037da5  test    rax, rax
0x180037da8  jz      short loc_180037DAE
0x180037daa  lock inc dword ptr [rax+8]
0x180037dae  mov     rax, [rcx]
0x180037db1  mov     qword ptr [rbp+110h+var_B8], rax
0x180037db5  mov     rdi, qword ptr [rbp+110h+var_B8+8]
0x180037db9  mov     rax, [rcx+8]
0x180037dbd  mov     qword ptr [rbp+110h+var_B8+8], rax
0x180037dc1  test    rdi, rdi
0x180037dc4  jz      short loc_180037DFD
0x180037dc6  mov     eax, ebx
0x180037dc8  lock xadd [rdi+8], eax
0x180037dcd  cmp     eax, 1
0x180037dd0  jnz     short loc_180037DFD
0x180037dd2  mov     rax, [rdi]
0x180037dd5  mov     rcx, rdi
0x180037dd8  mov     rax, [rax]
0x180037ddb  call    cs:__guard_dispatch_icall_fptr
0x180037de1  mov     eax, ebx
0x180037de3  lock xadd [rdi+0Ch], eax
0x180037de8  cmp     eax, 1
0x180037deb  jnz     short loc_180037DFD
0x180037ded  mov     rax, [rdi]
0x180037df0  mov     rcx, rdi
0x180037df3  mov     rax, [rax+8]
0x180037df7  call    cs:__guard_dispatch_icall_fptr
0x180037dfd  xor     edi, edi
0x180037dff  mov     r14, [r13+28h]
0x180037e03  mov     qword ptr [rbp+110h+var_160], r14
0x180037e07  test    r14, r14
0x180037e0a  jz      short loc_180037E1D
0x180037e0c  mov     rax, [r14]
0x180037e0f  mov     rcx, r14
0x180037e12  mov     rax, [rax+8]
0x180037e16  call    cs:__guard_dispatch_icall_fptr
0x180037e1c  nop
0x180037e1d  mov     dword ptr [rbp+110h+arg_28], edi
0x180037e23  mov     dword ptr [rbp+110h+pExceptionObject], 248h
0x180037e2a  lea     rsi, aCW1SX64Release; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180037e31  mov     [rbp+110h+var_188], rsi
0x180037e35  mov     [rbp+110h+var_180], rdi
0x180037e39  mov     rax, [r14]
0x180037e3c  lea     rdx, [rbp+110h+arg_28]
0x180037e43  mov     rcx, r14
0x180037e46  mov     rax, [rax+38h]
0x180037e4a  call    cs:__guard_dispatch_icall_fptr
0x180037e50  test    eax, eax
0x180037e52  js      loc_180038468
0x180037e58  xorps   xmm6, xmm6
0x180037e5b  mov     r15, rdi
0x180037e5e  mov     [rsp+68h], rdi
0x180037e63  mov     r12d, edi
0x180037e66  mov     dword ptr [rsp+210h+var_1A0], edi
0x180037e6a  mov     edi, dword ptr [rbp+110h+arg_28]
0x180037e70  test    edi, edi
0x180037e72  jz      short loc_180037EBD
0x180037e74  mov     ecx, edi
0x180037e76  shl     rcx, 4; cb
0x180037e7a  call    WINRT_IMPL_CoTaskMemAlloc
0x180037e7f  mov     r15, rax
0x180037e82  mov     [rsp+68h], rax
0x180037e87  test    rax, rax
0x180037e8a  jz      loc_180038477
0x180037e90  mov     r12d, edi
0x180037e93  mov     dword ptr [rsp+210h+var_1A0], edi
0x180037e97  test    edi, edi
0x180037e99  jz      short loc_180037EBD
0x180037e9b  movups  xmmword ptr [rax], xmm6
0x180037e9e  mov     ecx, edi
0x180037ea0  shl     rcx, 4
0x180037ea4  sub     rcx, 9
0x180037ea8  shr     rcx, 3
0x180037eac  lea     rdi, [rax+10h]
0x180037eb0  mov     rsi, rax
0x180037eb3  rep movsq
0x180037eb6  lea     rsi, aCW1SX64Release; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180037ebd  test    r14, r14
0x180037ec0  jz      short loc_180037ECB
0x180037ec2  lea     rcx, [rbp+110h+var_160]
0x180037ec6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180037ecb  mov     rdi, [r13+28h]
0x180037ecf  mov     qword ptr [rbp+110h+var_160], rdi
0x180037ed3  test    rdi, rdi
0x180037ed6  jz      short loc_180037EE9
0x180037ed8  mov     rax, [rdi]
0x180037edb  mov     rcx, rdi
0x180037ede  mov     rax, [rax+8]
0x180037ee2  call    cs:__guard_dispatch_icall_fptr
0x180037ee8  nop
0x180037ee9  xor     r13d, r13d
0x180037eec  mov     dword ptr [rbp+110h+arg_28], r13d
0x180037ef3  mov     dword ptr [rbp+110h+pExceptionObject], 2DEh
0x180037efa  mov     [rbp+110h+var_188], rsi
0x180037efe  mov     [rbp+110h+var_180], r13
0x180037f02  mov     rax, [rdi]
0x180037f05  mov     r9d, 4
0x180037f0b  test    r12d, r12d
0x180037f0e  cmovnz  r9, r15
0x180037f12  lea     rcx, [rbp+110h+arg_28]
0x180037f19  mov     [rsp+20h], rcx
0x180037f1e  mov     r8d, r12d
0x180037f21  xor     edx, edx
0x180037f23  mov     rcx, rdi
0x180037f26  mov     rax, [rax+80h]
0x180037f2d  call    cs:__guard_dispatch_icall_fptr
0x180037f33  test    eax, eax
0x180037f35  js      loc_180038491
0x180037f3b  lea     rcx, [rbp+110h+var_160]
0x180037f3f  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180037f44  cmp     dword ptr [rsp+210h+var_1E0], r13d
0x180037f49  jz      short loc_180037F60
0x180037f4b  mov     eax, r12d
0x180037f4e  mov     [rbp+110h+var_108], r15
0x180037f52  mov     [rbp+110h+var_100], rax
0x180037f56  cmp     [rbp+110h+var_F8], r13b
0x180037f5a  jnz     short loc_180037F60
0x180037f5c  mov     [rbp+110h+var_F8], 1
0x180037f60  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_58362677@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_58362677>>(void)
0x180037f65  test    al, al
0x180037f67  jz      loc_180038157
0x180037f6d  xorps   xmm0, xmm0
0x180037f70  movdqu  [rbp+110h+var_160], xmm0
0x180037f75  mov     r8b, 1
0x180037f78  lea     rdx, [rbp+110h+pExceptionObject]
0x180037f7c  mov     rsi, [rbp+110h+arg_0]
0x180037f83  mov     rcx, rsi
0x180037f86  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x180037f8b  mov     rax, [rsi+0B0h]
0x180037f92  test    rax, rax
0x180037f95  jz      short loc_180037F9B
0x180037f97  lock inc dword ptr [rax+8]
0x180037f9b  mov     rdi, [rsi+0A8h]
0x180037fa2  mov     qword ptr [rbp+110h+var_160], rdi
0x180037fa6  mov     rsi, [rsi+0B0h]
0x180037fad  mov     qword ptr [rbp+110h+var_160+8], rsi
0x180037fb1  cmp     byte ptr [rbp+110h+var_188], 0
0x180037fb5  jz      short loc_180037FC0
0x180037fb7  mov     rcx, [rbp+110h+pExceptionObject]; _Mtx_t
0x180037fbb  call    _Mtx_unlock
0x180037fc0  lea     r9, [rbp+110h+var_130]
0x180037fc4  mov     r8, [rbp+110h+arg_18]
0x180037fcb  lea     rdx, [rbp+110h+pExceptionObject]
0x180037fcf  mov     rcx, rdi
0x180037fd2  call    ?Match@SemanticIndexStore@SemanticIndex@asg@@QEBA?AUMatchResult@23@AEBUQueryEmbeddings@SemanticPipelines@3@AEBUMatchOptions@23@@Z; asg::SemanticIndex::SemanticIndexStore::Match(asg::SemanticPipelines::QueryEmbeddings const &,asg::SemanticIndex::MatchOptions const &)
0x180037fd7  mov     rdi, rax
0x180037fda  lea     rax, [rsp+210h+var_1E0+8]
0x180037fdf  cmp     rax, rdi
0x180037fe2  jz      short loc_18003805C
0x180037fe4  mov     rcx, qword ptr [rsp+210h+var_1E0+8]
0x180037fe9  test    rcx, rcx
0x180037fec  jz      short loc_180038037
0x180037fee  mov     rdx, qword ptr [rsp+210h+var_1D0+8]
0x180037ff3  sub     rdx, rcx
0x180037ff6  and     rdx, 0FFFFFFFFFFFFFFC0h
0x180037ffa  cmp     rdx, 1000h
0x180038001  jb      short loc_180038024
0x180038003  lfence
0x180038006  add     rdx, 27h ; '''
0x18003800a  mov     rax, qword ptr [rsp+210h+var_1E0+8]
0x18003800f  mov     rcx, [rax-8]; Block
0x180038013  sub     rax, rcx
0x180038016  sub     rax, 8
0x18003801a  cmp     rax, 1Fh
0x18003801e  ja      loc_1800384A0
0x180038024  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180038029  xorps   xmm0, xmm0
0x18003802c  movdqu  [rsp+210h+var_1E0+8], xmm0
0x180038032  mov     qword ptr [rsp+210h+var_1D0+8], r13
0x180038037  mov     rax, [rdi]
0x18003803a  mov     qword ptr [rsp+210h+var_1E0+8], rax
0x18003803f  mov     rax, [rdi+8]
0x180038043  mov     qword ptr [rsp+210h+var_1D0], rax
0x180038048  mov     rax, [rdi+10h]
0x18003804c  mov     qword ptr [rsp+210h+var_1D0+8], rax
0x180038051  mov     [rdi], r13
0x180038054  mov     [rdi+8], r13
0x180038058  mov     [rdi+10h], r13
0x18003805c  mov     rax, [rdi+18h]
0x180038060  mov     rcx, [rdi+20h]
0x180038064  mov     [rdi+18h], r13
0x180038068  mov     [rdi+20h], r13
0x18003806c  mov     [rsp+210h+var_1C0], rax
0x180038071  mov     r14, [rsp+210h+var_1B8]
0x180038076  mov     [rsp+210h+var_1B8], rcx
0x18003807b  test    r14, r14
0x18003807e  jz      short loc_1800380B9
0x180038080  mov     eax, ebx
0x180038082  lock xadd [r14+8], eax
0x180038088  cmp     eax, 1
  ... truncated ...
```
