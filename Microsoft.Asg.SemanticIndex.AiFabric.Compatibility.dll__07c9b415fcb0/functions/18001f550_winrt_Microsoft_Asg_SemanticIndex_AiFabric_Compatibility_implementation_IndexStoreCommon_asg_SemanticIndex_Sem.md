# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::QueryImage<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>>(winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,winrt::Windows::Graphics::Imaging::SoftwareBitmap const &,unsigned __int64,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticQueryOptions &,asg::CancellationToken)

- ea: `0x18001f550`
- end: `0x18001fc60`
- name: `??$QueryImage@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AUQueryResult@234567@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@7@AEBUSoftwareBitmap@Imaging@Graphics@Windows@7@_KAEAUSemanticQueryOptions@1234567@UCancellationToken@asg@@@Z`
- size: `1808`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001ad70`
- `0x180235e60`

## callees

- `0x180003bd0`
- `0x180009530`
- `0x180009770`
- `0x18000b2a0`
- `0x180010dd0`
- `0x18001f550`
- `0x18001fc60`
- `0x180022c60`
- `0x18002caf0`
- `0x18002f8e0`
- `0x18002f9f0`
- `0x1800678c0`
- `0x18009fc20`
- `0x1801d2b20`
- `0x1801f7190`
- `0x180242120`

## string_xrefs

- `0x18001f81d`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18001f78c`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Graphics.Imaging.h`
- `0x18001f8aa`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Graphics.Imaging.h`
- `0x18001f8e9`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Graphics.Imaging.h`
- `0x18001fa2d`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18001fa39`: `struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatib`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_QWORD *__fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::QueryImage<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *v8; // r14
  __int64 v11; // r15
  __int64 v12; // rdx
  __int64 v13; // rdx
  signed __int64 v14; // rax
  signed __int64 v15; // rtt
  __int64 v16; // rax
  __int64 v17; // rbx
  volatile signed __int32 *v18; // rdi
  _QWORD *v19; // rax
  volatile signed __int32 *v20; // rdi
  _QWORD *v21; // rax
  __int64 v22; // rcx
  int v23; // eax
  __int64 (__fastcall ***v24)(_QWORD, __int64 *, _QWORD **); // rcx
  int v25; // eax
  _QWORD *v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // r12
  __int64 v35; // rax
  _QWORD *v36; // rdx
  signed __int64 v37; // rax
  signed __int64 v38; // rtt
  volatile signed __int32 *v39; // rsi
  __int128 v41; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v42; // [rsp+40h] [rbp-C0h]
  int v43; // [rsp+50h] [rbp-B0h]
  __int64 v44; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v46; // [rsp+68h] [rbp-98h] BYREF
  __int64 v47; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h] BYREF
  _Mtx_t v49; // [rsp+80h] [rbp-80h] BYREF
  char v50; // [rsp+88h] [rbp-78h]
  __int128 v51; // [rsp+90h] [rbp-70h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h]
  __int64 v54; // [rsp+B0h] [rbp-50h]
  __int64 v55; // [rsp+B8h] [rbp-48h]
  __int128 v56; // [rsp+C0h] [rbp-40h]
  _QWORD v57[10]; // [rsp+D0h] [rbp-30h] BYREF
  char v58; // [rsp+120h] [rbp+20h]
  _BYTE v59[72]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD *v60; // [rsp+180h] [rbp+80h] BYREF
  _QWORD *v61; // [rsp+188h] [rbp+88h]
  _QWORD *v62; // [rsp+190h] [rbp+90h]

  v62 = a3;
  v61 = a2;
  v8 = a3;
  v43 = 0;
  v47 = 0;
  v56 = 0;
  LOBYTE(a3) = 1;
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
    a1,
    &v49,
    a3);
  v11 = 0;
  v12 = *(_QWORD *)(a1 + 232);
  if ( v12 )
  {
    v13 = v12 - 16;
    if ( v13 )
    {
      v11 = v13;
      v14 = *(_QWORD *)(v13 + 8);
      if ( v14 < 0 )
      {
LABEL_6:
        _InterlockedIncrement((volatile signed __int32 *)(2 * v14 + 24));
      }
      else
      {
        while ( 1 )
        {
          v15 = v14;
          v14 = _InterlockedCompareExchange64((volatile signed __int64 *)(v13 + 8), v14 + 1, v14);
          if ( v15 == v14 )
            break;
          if ( v14 < 0 )
            goto LABEL_6;
        }
      }
    }
  }
  v47 = v11;
  v16 = *(_QWORD *)(v11 + 232);
  if ( v16 )
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
  v17 = *(_QWORD *)(v11 + 224);
  v18 = *(volatile signed __int32 **)(v11 + 232);
  *(_QWORD *)&v56 = v17;
  *((_QWORD *)&v56 + 1) = v18;
  if ( (unsigned __int8)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IsGeneratorClosed(
                          a1,
                          1) )
  {
    v19 = operator new(0x80u);
    v60 = v19;
    v19[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v19[1] = 1;
    *((_DWORD *)v19 + 7) = 105;
    *((_DWORD *)v19 + 8) = -2147467259;
    v19[5] = 0;
    v19[6] = 0;
    v19[14] = 0;
    v19[15] = 0;
    *v19 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult>::`vftable';
    *a2 = v19 + 2;
LABEL_11:
    if ( v50 )
      Mtx_unlock(v49);
    if ( v18 )
    {
      if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    if ( v11 )
      winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(&v47);
    if ( *v8 )
      winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(v8);
    v20 = *(volatile signed __int32 **)(a7 + 8);
    goto LABEL_66;
  }
  if ( !(unsigned __int8)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IsLoaded(
                           a1,
                           1) )
  {
    v21 = operator new(0x80u);
    v60 = v21;
    v21[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v21[1] = 1;
    *((_DWORD *)v21 + 7) = 110;
    *((_DWORD *)v21 + 8) = -2147467259;
    v21[5] = 0;
    v21[6] = 0;
    v21[14] = 0;
    v21[15] = 0;
    *v21 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult>::`vftable';
    *a2 = v21 + 2;
    goto LABEL_11;
  }
  if ( v50 )
    Mtx_unlock(v49);
  v60 = 0;
  v22 = *a4;
  LODWORD(v41) = 1662;
  *((_QWORD *)&v41 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Windows.Graphics.Imaging.h";
  *(_QWORD *)&v42 = 0;
  v23 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)v22 + 120LL))(v22, 1, &v60);
  if ( v23 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v23, &v41);
  }
  v24 = (__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD **))v60;
  v46 = v60;
  v43 = 8;
  v44 = 0;
  v60 = 0;
  if ( v46 )
  {
    v25 = (**v24)(v24, &winrt::impl::guid_v<winrt::Windows::Foundation::IMemoryBuffer>, &v60);
    v26 = v60;
  }
  else
  {
    v25 = 0;
    v26 = 0;
  }
  LODWORD(v41) = 500;
  *((_QWORD *)&v41 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Windows.Foundation.h";
  *(_QWORD *)&v42 = 0;
  if ( v25 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v25, &v41);
  }
  LODWORD(v41) = 502;
  *((_QWORD *)&v41 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Windows.Foundation.h";
  *(_QWORD *)&v42 = 0;
  v27 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v26 + 48LL))(v26, &v44);
  if ( v27 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v27, &v41);
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v60);
  v45 = v44;
  v43 = 24;
  v57[8] = &v45;
  v57[9] = &v46;
  v58 = 1;
  LODWORD(v60) = 0;
  v28 = *a4;
  LODWORD(v41) = 1558;
  *((_QWORD *)&v41 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Windows.Graphics.Imaging.h";
  *(_QWORD *)&v42 = 0;
  v29 = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v28 + 72LL))(v28, &v60);
  if ( v29 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v29, &v41);
  }
  LODWORD(v44) = 0;
  v30 = *a4;
  LODWORD(v41) = 1540;
  *((_QWORD *)&v41 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\Windows.Graphics.Imaging.h";
  *(_QWORD *)&v42 = 0;
  v31 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 64LL))(v30, &v44);
  if ( v31 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v31, &v41);
  }
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ToBgra8ImageView(
    v59,
    (unsigned int)v44,
    (unsigned int)v60,
    &v45);
  asg::SemanticPipelines::DualImageQueryEmbeddingPipeline::ProcessImage(v17, &v52, v59, 0);
  v41 = 0;
  v32 = v53;
  if ( v53 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v53 + 8));
    v32 = v53;
  }
  *(_QWORD *)&v41 = v52;
  *((_QWORD *)&v41 + 1) = v32;
  v42 = 0;
  v33 = v55;
  if ( v55 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v55 + 8));
    v33 = v55;
  }
  *(_QWORD *)&v42 = v54;
  *((_QWORD *)&v42 + 1) = v33;
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MakeImageQueryEmbeddings(&v48, &v41);
  v51 = 0;
  v34 = a7;
  v35 = *(_QWORD *)(a7 + 8);
  if ( v35 )
    _InterlockedIncrement((volatile signed __int32 *)(v35 + 8));
  v51 = *(_OWORD *)v34;
  v57[7] = &v51;
  v36 = (_QWORD *)*v8;
  v60 = v36;
  if ( v36 )
  {
    v37 = v36[1];
    if ( v37 < 0 )
    {
LABEL_44:
      _InterlockedIncrement((volatile signed __int32 *)(2 * v37 + 24));
    }
    else
    {
      while ( 1 )
      {
        v38 = v37;
        v37 = _InterlockedCompareExchange64(v36 + 1, v37 + 1, v37);
        if ( v38 == v37 )
          break;
        if ( v37 < 0 )
          goto LABEL_44;
      }
    }
  }
  v49 = (_Mtx_t)&v60;
  v44 = a5;
  *(_QWORD *)&v41 = 0x14000007BDLL;
  *((_QWORD *)&v41 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
  *(_QWORD *)&v42 = "struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult __cdecl winrt::Mic"
                    "rosoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::Sem"
                    "anticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility:"
                    ":ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::impl"
                    "ementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatib"
                    "ility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility:"
                    ":implementation::TextEmbeddingsGenerator>::Query<struct winrt::com_ptr<struct winrt::Microsoft::Asg:"
                    ":SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>>(struct winrt::com"
                    "_ptr<struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticI"
                    "mageIndexStore>,const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmb"
                    "eddings &,const struct asg::SemanticPipelines::QueryEmbeddings &,unsigned __int64,struct winrt::Micr"
                    "osoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticQueryOptions &,struct as"
                    "g::CancellationToken)";
  v57[0] = a1;
  v57[1] = &v48;
  v57[2] = &v52;
  v57[3] = &v44;
  v57[4] = a6;
  v57[5] = &v51;
  v57[6] = &v60;
  ___InvokeDbMethod_V_lambda_1___1____Query_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt_____IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AUQueryResult_456789_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___9_AEBUQueryEmbeddings_456789_AEBUQueryEmbeddings_SemanticPipelines_asg___KAEAUSemanticQueryOptions_3456789_UCancellationToken_asg___Z___A6AXX_E___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_A_P__QEAV_lambda_1___1____Query_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt___01234567_AEAA_AUQueryResult_234567_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___7_AEBUQueryEmbeddings_234567_AEBUQueryEmbeddings_SemanticPipelines_asg___KAEAUSemanticQueryOptions_1234567_UCancellationToken_asg___Z___Q6AXX_EAEBUsource_location_std___Z(
    a1,
    a2,
    v57);
  if ( v60 )
    winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(&v60);
  v39 = (volatile signed __int32 *)*((_QWORD *)&v51 + 1);
  if ( *((_QWORD *)&v51 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v51 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
      if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
    }
  }
  v43 = 57;
  if ( v48 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v48);
  asg::SemanticPipelines::QueryEmbeddings::~QueryEmbeddings((asg::SemanticPipelines::QueryEmbeddings *)&v52);
  winrt::impl::consume_Windows_Foundation_IClosable<winrt::Windows::Graphics::Imaging::IBitmapBuffer>::Close(&v45);
  winrt::impl::consume_Windows_Foundation_IClosable<winrt::Windows::Graphics::Imaging::IBitmapBuffer>::Close(&v46);
  if ( v45 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v45);
  if ( v46 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v46);
  if ( v18 )
  {
    if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  if ( v11 )
    winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(&v47);
  if ( *v8 )
    winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(v8);
  v20 = *(volatile signed __int32 **)(v34 + 8);
LABEL_66:
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18001f550  mov     [rsp-8+arg_18], rbx
0x18001f555  mov     [rsp-8+arg_10], r8
0x18001f55a  mov     [rsp-8+arg_8], rdx
0x18001f55f  push    rbp
0x18001f560  push    rsi
0x18001f561  push    rdi
0x18001f562  push    r12
0x18001f564  push    r13
0x18001f566  push    r14
0x18001f568  push    r15
0x18001f56a  lea     rbp, [rsp-40h]
0x18001f56f  sub     rsp, 140h
0x18001f576  mov     r12, r9
0x18001f579  mov     r14, r8
0x18001f57c  mov     r13, rdx
0x18001f57f  mov     rsi, rcx
0x18001f582  xor     ebx, ebx
0x18001f584  mov     [rsp+170h+var_120], ebx
0x18001f588  mov     [rsp+170h+var_100], rbx
0x18001f58d  xorps   xmm0, xmm0
0x18001f590  movdqu  [rbp+70h+var_B0], xmm0
0x18001f595  mov     r8b, 1
0x18001f598  lea     rdx, [rbp+70h+var_F0]
0x18001f59c  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18001f5a1  nop
0x18001f5a2  mov     r15d, ebx
0x18001f5a5  mov     rdx, [rsi+0E8h]
0x18001f5ac  test    rdx, rdx
0x18001f5af  jz      short loc_18001F5D9
0x18001f5b1  add     rdx, 0FFFFFFFFFFFFFFF0h
0x18001f5b5  jz      short loc_18001F5D9
0x18001f5b7  mov     r15, rdx
0x18001f5ba  mov     rax, [rdx+8]
0x18001f5be  test    rax, rax
0x18001f5c1  js      short loc_18001F5D4
0x18001f5c3  lea     rcx, [rax+1]
0x18001f5c7  lock cmpxchg [rdx+8], rcx
0x18001f5cd  jz      short loc_18001F5D9
0x18001f5cf  test    rax, rax
0x18001f5d2  jns     short loc_18001F5C3
0x18001f5d4  lock inc dword ptr [rax+rax+18h]
0x18001f5d9  mov     [rsp+170h+var_100], r15
0x18001f5de  mov     rax, [r15+0E8h]
0x18001f5e5  test    rax, rax
0x18001f5e8  jz      short loc_18001F5EE
0x18001f5ea  lock inc dword ptr [rax+8]
0x18001f5ee  mov     rbx, [r15+0E0h]
0x18001f5f5  mov     rdi, [r15+0E8h]
0x18001f5fc  mov     qword ptr [rbp+70h+var_B0], rbx
0x18001f600  mov     qword ptr [rbp+70h+var_B0+8], rdi
0x18001f604  mov     edx, 1
0x18001f609  mov     rcx, rsi
0x18001f60c  call    ?IsGeneratorClosed@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA_NW4CommonIndexModelKind@2345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IsGeneratorClosed(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CommonIndexModelKind)
0x18001f611  test    al, al
0x18001f613  jz      loc_18001F6F6
0x18001f619  mov     ecx, 80h; Size
0x18001f61e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f623  mov     [rbp+70h+arg_0], rax
0x18001f62a  lea     rcx, [rax+10h]
0x18001f62e  lea     rdx, ??_7?$produce@UQueryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIQueryResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryResult>::`vftable'
0x18001f635  mov     [rcx], rdx
0x18001f638  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001f63f  mov     qword ptr [rax+8], 1
0x18001f647  mov     dword ptr [rax+1Ch], 69h ; 'i'
0x18001f64e  mov     dword ptr [rax+20h], 80004005h
0x18001f655  xor     edx, edx
0x18001f657  mov     [rax+28h], rdx
0x18001f65b  mov     [rax+30h], rdx
0x18001f65f  mov     [rax+70h], rdx
0x18001f663  mov     [rax+78h], rdx
0x18001f667  lea     rdx, ??_7?$heap_implements@UQueryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult>::`vftable'
0x18001f66e  mov     [rax], rdx
0x18001f671  mov     [r13+0], rcx
0x18001f675  cmp     [rbp+70h+var_E8], 0
0x18001f679  jz      short loc_18001F685
0x18001f67b  mov     rcx, [rbp+70h+var_F0]; _Mtx_t
0x18001f67f  call    _Mtx_unlock
0x18001f684  nop
0x18001f685  test    rdi, rdi
0x18001f688  mov     ebx, 0FFFFFFFFh
0x18001f68d  jz      short loc_18001F6C7
0x18001f68f  mov     eax, ebx
0x18001f691  lock xadd [rdi+8], eax
0x18001f696  cmp     eax, 1
0x18001f699  jnz     short loc_18001F6C7
0x18001f69b  mov     rax, [rdi]
0x18001f69e  mov     rcx, rdi
0x18001f6a1  mov     rax, [rax]
0x18001f6a4  call    cs:__guard_dispatch_icall_fptr
0x18001f6aa  mov     eax, ebx
0x18001f6ac  lock xadd [rdi+0Ch], eax
0x18001f6b1  cmp     eax, 1
0x18001f6b4  jnz     short loc_18001F6C7
0x18001f6b6  mov     rax, [rdi]
0x18001f6b9  mov     rcx, rdi
0x18001f6bc  mov     rax, [rax+8]
0x18001f6c0  call    cs:__guard_dispatch_icall_fptr
0x18001f6c6  nop
0x18001f6c7  test    r15, r15
0x18001f6ca  jz      short loc_18001F6D7
0x18001f6cc  lea     rcx, [rsp+170h+var_100]
0x18001f6d1  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18001f6d6  nop
0x18001f6d7  cmp     qword ptr [r14], 0
0x18001f6db  jz      short loc_18001F6E6
0x18001f6dd  mov     rcx, r14
0x18001f6e0  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18001f6e5  nop
0x18001f6e6  mov     rax, [rbp+70h+arg_30]
0x18001f6ed  mov     rdi, [rax+8]
0x18001f6f1  jmp     loc_18001FBB8
0x18001f6f6  mov     edx, 1
0x18001f6fb  mov     rcx, rsi
0x18001f6fe  call    ?IsLoaded@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEBA_NW4CommonIndexModelKind@2345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IsLoaded(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CommonIndexModelKind)
0x18001f703  test    al, al
0x18001f705  jnz     short loc_18001F768
0x18001f707  mov     ecx, 80h; Size
0x18001f70c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f711  mov     [rbp+70h+arg_0], rax
0x18001f718  lea     rcx, [rax+10h]
0x18001f71c  lea     rdx, ??_7?$produce@UQueryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIQueryResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryResult>::`vftable'
0x18001f723  mov     [rcx], rdx
0x18001f726  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001f72d  mov     qword ptr [rax+8], 1
0x18001f735  mov     dword ptr [rax+1Ch], 6Eh ; 'n'
0x18001f73c  mov     dword ptr [rax+20h], 80004005h
0x18001f743  xor     edx, edx
0x18001f745  mov     [rax+28h], rdx
0x18001f749  mov     [rax+30h], rdx
0x18001f74d  mov     [rax+70h], rdx
0x18001f751  mov     [rax+78h], rdx
0x18001f755  lea     rdx, ??_7?$heap_implements@UQueryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult>::`vftable'
0x18001f75c  mov     [rax], rdx
0x18001f75f  mov     [r13+0], rcx
0x18001f763  jmp     loc_18001F675
0x18001f768  cmp     [rbp+70h+var_E8], 0
0x18001f76c  jz      short loc_18001F777
0x18001f76e  mov     rcx, [rbp+70h+var_F0]; _Mtx_t
0x18001f772  call    _Mtx_unlock
0x18001f777  xor     eax, eax
0x18001f779  mov     [rbp+70h+arg_0], rax
0x18001f780  mov     rcx, [r12]
0x18001f784  mov     dword ptr [rsp+170h+var_140], 67Eh
0x18001f78c  lea     rdx, aCW1SX64Release_9; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18001f793  mov     qword ptr [rsp+170h+var_140+8], rdx
0x18001f798  mov     qword ptr [rsp+170h+var_130], rax
0x18001f79d  mov     rax, [rcx]
0x18001f7a0  lea     r8, [rbp+70h+arg_0]
0x18001f7a7  mov     edx, 1
0x18001f7ac  mov     rax, [rax+78h]
0x18001f7b0  call    cs:__guard_dispatch_icall_fptr
0x18001f7b6  test    eax, eax
0x18001f7b8  js      loc_18001FC20
0x18001f7be  mov     rcx, [rbp+70h+arg_0]
0x18001f7c5  mov     [rsp+170h+var_108], rcx
0x18001f7ca  mov     [rsp+170h+var_120], 8
0x18001f7d2  xor     edx, edx
0x18001f7d4  mov     [rsp+170h+var_118], rdx
0x18001f7d9  mov     [rbp+70h+arg_0], rdx
0x18001f7e0  test    rcx, rcx
0x18001f7e3  jnz     short loc_18001F7EB
0x18001f7e5  mov     eax, edx
0x18001f7e7  mov     ecx, edx
0x18001f7e9  jmp     short loc_18001F815
0x18001f7eb  mov     rax, [rcx]
0x18001f7ee  lea     r8, [rbp+70h+arg_0]
0x18001f7f5  lea     rdx, ??$guid_v@UIMemoryBuffer@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IMemoryBuffer>
0x18001f7fc  mov     rax, [rax]
0x18001f7ff  call    cs:__guard_dispatch_icall_fptr
0x18001f805  mov     rcx, [rbp+70h+arg_0]
0x18001f80c  mov     [rbp+70h+arg_0], rcx
0x18001f813  xor     edx, edx
0x18001f815  mov     dword ptr [rsp+170h+var_140], 1F4h
0x18001f81d  lea     r8, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18001f824  mov     qword ptr [rsp+170h+var_140+8], r8
0x18001f829  mov     qword ptr [rsp+170h+var_130], rdx
0x18001f82e  test    eax, eax
0x18001f830  js      loc_18001FC30
0x18001f836  mov     dword ptr [rsp+170h+var_140], 1F6h
0x18001f83e  mov     qword ptr [rsp+170h+var_140+8], r8
0x18001f843  mov     qword ptr [rsp+170h+var_130], rdx
0x18001f848  mov     rax, [rcx]
0x18001f84b  lea     rdx, [rsp+170h+var_118]
0x18001f850  mov     rax, [rax+30h]
0x18001f854  call    cs:__guard_dispatch_icall_fptr
0x18001f85a  test    eax, eax
0x18001f85c  js      loc_18001FC40
0x18001f862  lea     rcx, [rbp+70h+arg_0]
0x18001f869  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18001f86e  mov     rax, [rsp+170h+var_118]
0x18001f873  mov     [rsp+170h+var_110], rax
0x18001f878  mov     [rsp+170h+var_120], 18h
0x18001f880  lea     rax, [rsp+170h+var_110]
0x18001f885  mov     [rbp+70h+var_60], rax
0x18001f889  lea     rax, [rsp+170h+var_108]
0x18001f88e  mov     [rbp+70h+var_58], rax
0x18001f892  mov     [rbp+70h+var_50], 1
0x18001f896  xor     eax, eax
0x18001f898  mov     dword ptr [rbp+70h+arg_0], eax
0x18001f89e  mov     rcx, [r12]
0x18001f8a2  mov     dword ptr [rsp+170h+var_140], 616h
0x18001f8aa  lea     rdx, aCW1SX64Release_9; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18001f8b1  mov     qword ptr [rsp+170h+var_140+8], rdx
0x18001f8b6  mov     qword ptr [rsp+170h+var_130], rax
0x18001f8bb  mov     rax, [rcx]
0x18001f8be  lea     rdx, [rbp+70h+arg_0]
0x18001f8c5  mov     rax, [rax+48h]
0x18001f8c9  call    cs:__guard_dispatch_icall_fptr
0x18001f8cf  test    eax, eax
0x18001f8d1  js      loc_18001FC50
0x18001f8d7  xor     eax, eax
0x18001f8d9  mov     dword ptr [rsp+170h+var_118], eax
0x18001f8dd  mov     rcx, [r12]
0x18001f8e1  mov     dword ptr [rsp+170h+var_140], 604h
0x18001f8e9  lea     rdx, aCW1SX64Release_9; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18001f8f0  mov     qword ptr [rsp+170h+var_140+8], rdx
0x18001f8f5  mov     qword ptr [rsp+170h+var_130], rax
0x18001f8fa  mov     rax, [rcx]
0x18001f8fd  lea     rdx, [rsp+170h+var_118]
0x18001f902  mov     rax, [rax+40h]
0x18001f906  call    cs:__guard_dispatch_icall_fptr
0x18001f90c  test    eax, eax
0x18001f90e  js      loc_18001FC10
0x18001f914  lea     r9, [rsp+170h+var_110]
0x18001f919  mov     r8d, dword ptr [rbp+70h+arg_0]
0x18001f920  mov     edx, dword ptr [rsp+170h+var_118]
0x18001f924  lea     rcx, [rbp+70h+var_48]
0x18001f928  call    ?ToBgra8ImageView@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUBgra8ImageView@SemanticRegistry@asg@@HHAEBUIMemoryBufferReference@Foundation@Windows@7@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ToBgra8ImageView(int,int,winrt::Windows::Foundation::IMemoryBufferReference const &)
0x18001f92d  xor     r9d, r9d
0x18001f930  lea     r8, [rbp+70h+var_48]
0x18001f934  lea     rdx, [rbp+70h+var_D0]
0x18001f938  mov     rcx, rbx
0x18001f93b  call    ?ProcessImage@DualImageQueryEmbeddingPipeline@SemanticPipelines@asg@@QEAA?AUQueryEmbeddings@23@AEBUBgra8ImageView@SemanticRegistry@3@W4ExecutionPriorityHint@63@@Z; asg::SemanticPipelines::DualImageQueryEmbeddingPipeline::ProcessImage(asg::SemanticRegistry::Bgra8ImageView const &,asg::SemanticRegistry::ExecutionPriorityHint)
0x18001f940  nop
0x18001f941  xorps   xmm0, xmm0
0x18001f944  movdqu  [rsp+170h+var_140], xmm0
0x18001f94a  mov     rcx, [rbp+70h+var_C8]
0x18001f94e  test    rcx, rcx
0x18001f951  jz      short loc_18001F95B
0x18001f953  lock inc dword ptr [rcx+8]
0x18001f957  mov     rcx, [rbp+70h+var_C8]
0x18001f95b  mov     rax, [rbp+70h+var_D0]
0x18001f95f  mov     qword ptr [rsp+170h+var_140], rax
0x18001f964  mov     qword ptr [rsp+170h+var_140+8], rcx
0x18001f969  movdqu  [rsp+170h+var_130], xmm0
0x18001f96f  mov     rcx, [rbp+70h+var_B8]
0x18001f973  test    rcx, rcx
0x18001f976  jz      short loc_18001F980
0x18001f978  lock inc dword ptr [rcx+8]
0x18001f97c  mov     rcx, [rbp+70h+var_B8]
0x18001f980  mov     rax, [rbp+70h+var_C0]
0x18001f984  mov     qword ptr [rsp+170h+var_130], rax
0x18001f989  mov     qword ptr [rsp+170h+var_130+8], rcx
0x18001f98e  lea     rdx, [rsp+170h+var_140]
0x18001f993  lea     rcx, [rsp+170h+var_F8]
0x18001f998  call    ?MakeImageQueryEmbeddings@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUQueryEmbeddings@234567@U8SemanticPipelines@asg@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MakeImageQueryEmbeddings(asg::SemanticPipelines::QueryEmbeddings)
0x18001f99d  nop
0x18001f99e  xorps   xmm0, xmm0
0x18001f9a1  movdqu  [rbp+70h+var_E0], xmm0
0x18001f9a6  mov     r12, [rbp+70h+arg_30]
0x18001f9ad  mov     rax, [r12+8]
0x18001f9b2  test    rax, rax
0x18001f9b5  jz      short loc_18001F9BB
0x18001f9b7  lock inc dword ptr [rax+8]
0x18001f9bb  mov     rax, [r12]
0x18001f9bf  mov     qword ptr [rbp+70h+var_E0], rax
0x18001f9c3  mov     rax, [r12+8]
0x18001f9c8  mov     qword ptr [rbp+70h+var_E0+8], rax
0x18001f9cc  lea     rax, [rbp+70h+var_E0]
0x18001f9d0  mov     [rbp+70h+var_68], rax
0x18001f9d4  mov     rdx, [r14]
0x18001f9d7  mov     [rbp+70h+arg_0], rdx
0x18001f9de  test    rdx, rdx
0x18001f9e1  jz      short loc_18001FA06
0x18001f9e3  mov     rax, [rdx+8]
0x18001f9e7  test    rax, rax
0x18001f9ea  js      short loc_18001FA01
0x18001f9ec  nop     dword ptr [rax+00h]
0x18001f9f0  lea     rcx, [rax+1]
0x18001f9f4  lock cmpxchg [rdx+8], rcx
0x18001f9fa  jz      short loc_18001FA06
0x18001f9fc  test    rax, rax
0x18001f9ff  jns     short loc_18001F9F0
0x18001fa01  lock inc dword ptr [rax+rax+18h]
0x18001fa06  lea     rax, [rbp+70h+arg_0]
0x18001fa0d  mov     [rbp+70h+var_F0], rax
0x18001fa11  mov     rax, [rbp+70h+arg_20]
0x18001fa18  mov     [rsp+170h+var_118], rax
0x18001fa1d  mov     dword ptr [rsp+170h+var_140], 7BDh
0x18001fa25  mov     dword ptr [rsp+170h+var_140+4], 14h
0x18001fa2d  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18001fa34  mov     qword ptr [rsp+170h+var_140+8], rax
0x18001fa39  lea     rax, aStructWinrtMic_10; "struct winrt::Microsoft::Asg::SemanticI"...
0x18001fa40  mov     qword ptr [rsp+170h+var_130], rax
0x18001fa45  mov     [rbp+70h+var_A0], rsi
0x18001fa49  lea     rax, [rsp+170h+var_F8]
0x18001fa4e  mov     [rbp+70h+var_98], rax
0x18001fa52  lea     rax, [rbp+70h+var_D0]
0x18001fa56  mov     [rbp+70h+var_90], rax
0x18001fa5a  lea     rax, [rsp+170h+var_118]
  ... truncated ...
```
