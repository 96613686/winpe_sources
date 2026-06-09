# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::QueryText<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>>(winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,winrt::hstring const &,unsigned __int64,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticQueryOptions &,asg::CancellationToken)

- ea: `0x18001f090`
- end: `0x18001f543`
- name: `??$QueryText@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AUQueryResult@234567@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@7@AEBUhstring@7@_KAEAUSemanticQueryOptions@1234567@UCancellationToken@asg@@@Z`
- size: `1203`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001ab80`
- `0x1802366a0`

## callees

- `0x180003bd0`
- `0x180009770`
- `0x180009a70`
- `0x18000b2a0`
- `0x18001f090`
- `0x180022c60`
- `0x18002caf0`
- `0x18002f8e0`
- `0x18002f9f0`
- `0x18009ff30`
- `0x1801d2b20`
- `0x1801f7190`
- `0x180242120`

## string_xrefs

- `0x18001f3ab`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18001f3b7`: `struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatib`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::QueryText<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD *v8; // r14
  __int128 v10; // rcx
  __int64 v11; // r15
  __int64 v12; // rdx
  __int64 v13; // rdx
  signed __int64 v14; // rax
  signed __int64 v15; // rtt
  __int64 v16; // rax
  __int64 v17; // rsi
  volatile signed __int32 *v18; // rdi
  _QWORD *v19; // rax
  char *v20; // rcx
  volatile signed __int32 *v21; // rdi
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // r12
  __int64 v26; // rax
  _QWORD *v27; // rdx
  signed __int64 v28; // rax
  signed __int64 v29; // rtt
  volatile signed __int32 *v30; // rsi
  __int128 v32; // [rsp+30h] [rbp-C1h] BYREF
  __int64 v33; // [rsp+40h] [rbp-B1h] BYREF
  __int64 v34; // [rsp+48h] [rbp-A9h] BYREF
  _Mtx_t v35; // [rsp+50h] [rbp-A1h] BYREF
  char v36; // [rsp+58h] [rbp-99h]
  __int128 v37; // [rsp+60h] [rbp-91h] BYREF
  __int128 v38; // [rsp+70h] [rbp-81h]
  __int64 v39; // [rsp+80h] [rbp-71h] BYREF
  __int64 v40; // [rsp+88h] [rbp-69h]
  __int64 v41; // [rsp+90h] [rbp-61h]
  __int64 v42; // [rsp+98h] [rbp-59h]
  __int64 v43; // [rsp+A8h] [rbp-49h] BYREF
  __int128 v44; // [rsp+B0h] [rbp-41h]
  _QWORD v45[14]; // [rsp+C0h] [rbp-31h] BYREF
  _QWORD *v46; // [rsp+140h] [rbp+4Fh] BYREF
  _QWORD *v47; // [rsp+148h] [rbp+57h]
  _QWORD *v48; // [rsp+150h] [rbp+5Fh]

  v48 = a3;
  v47 = a2;
  v8 = a3;
  *((_QWORD *)&v10 + 1) = 0;
  v33 = 0;
  v44 = 0;
  LOBYTE(a3) = 1;
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
    a1,
    &v35,
    a3);
  v11 = 0;
  v12 = *(_QWORD *)(a1 + 240);
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
  v33 = v11;
  v16 = *(_QWORD *)(v11 + 232);
  if ( v16 )
    _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
  v17 = *(_QWORD *)(v11 + 224);
  v18 = *(volatile signed __int32 **)(v11 + 232);
  *(_QWORD *)&v44 = v17;
  *((_QWORD *)&v44 + 1) = v18;
  if ( (unsigned __int8)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IsGeneratorClosed(
                          a1,
                          2) )
  {
    v19 = operator new(0x80u);
    v46 = v19;
    v20 = (char *)(v19 + 2);
    v19[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v19[1] = 1;
    *((_DWORD *)v19 + 7) = 105;
LABEL_11:
    *((_DWORD *)v19 + 8) = -2147467259;
    v19[5] = 0;
    v19[6] = 0;
    v19[14] = 0;
    v19[15] = 0;
    *v19 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult>::`vftable';
    *v47 = v20;
    if ( v36 )
      Mtx_unlock(v35);
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
      winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(&v33);
    if ( *v8 )
      winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(v8);
    v21 = *(volatile signed __int32 **)(a7 + 8);
    goto LABEL_57;
  }
  if ( !(unsigned __int8)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IsLoaded(
                           a1,
                           2) )
  {
    v19 = operator new(0x80u);
    v46 = v19;
    v20 = (char *)(v19 + 2);
    v19[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryResult>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v19[1] = 1;
    *((_DWORD *)v19 + 7) = 110;
    goto LABEL_11;
  }
  if ( v36 )
    Mtx_unlock(v35);
  v22 = *a4;
  if ( *a4 )
  {
    *(_QWORD *)&v10 = *(_QWORD *)(v22 + 16);
    *((_QWORD *)&v10 + 1) = *(unsigned int *)(v22 + 4);
  }
  else
  {
    *(_QWORD *)&v10 = &String;
  }
  v32 = v10;
  asg::SemanticPipelines::DualTextQueryEmbeddingPipeline::ProcessText(v17, &v39, &v32, 0);
  v37 = 0;
  v23 = v40;
  if ( v40 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v40 + 8));
    v23 = v40;
  }
  *(_QWORD *)&v37 = v39;
  *((_QWORD *)&v37 + 1) = v23;
  v38 = 0;
  v24 = v42;
  if ( v42 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v42 + 8));
    v24 = v42;
  }
  *(_QWORD *)&v38 = v41;
  *((_QWORD *)&v38 + 1) = v24;
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MakeTextQueryEmbeddings(&v34, &v37);
  v32 = 0;
  v25 = a7;
  v26 = *(_QWORD *)(a7 + 8);
  if ( v26 )
    _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
  v32 = *(_OWORD *)v25;
  v45[7] = &v32;
  v27 = (_QWORD *)*v8;
  v46 = v27;
  if ( v27 )
  {
    v28 = v27[1];
    if ( v28 < 0 )
    {
LABEL_39:
      _InterlockedIncrement((volatile signed __int32 *)(2 * v28 + 24));
    }
    else
    {
      while ( 1 )
      {
        v29 = v28;
        v28 = _InterlockedCompareExchange64(v27 + 1, v28 + 1, v28);
        if ( v29 == v28 )
          break;
        if ( v28 < 0 )
          goto LABEL_39;
      }
    }
  }
  v35 = (_Mtx_t)&v46;
  v43 = a5;
  *(_QWORD *)&v37 = 0x14000007BDLL;
  *((_QWORD *)&v37 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
  *(_QWORD *)&v38 = "struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult __cdecl winrt::Mic"
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
  v45[0] = a1;
  v45[1] = &v34;
  v45[2] = &v39;
  v45[3] = &v43;
  v45[4] = a6;
  v45[5] = &v32;
  v45[6] = &v46;
  ___InvokeDbMethod_V_lambda_1___1____Query_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt_____IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AUQueryResult_456789_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___9_AEBUQueryEmbeddings_456789_AEBUQueryEmbeddings_SemanticPipelines_asg___KAEAUSemanticQueryOptions_3456789_UCancellationToken_asg___Z___A6AXX_E___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_A_P__QEAV_lambda_1___1____Query_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt___01234567_AEAA_AUQueryResult_234567_U__com_ptr_USemanticImageIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___7_AEBUQueryEmbeddings_234567_AEBUQueryEmbeddings_SemanticPipelines_asg___KAEAUSemanticQueryOptions_1234567_UCancellationToken_asg___Z___Q6AXX_EAEBUsource_location_std___Z(
    a1,
    v47,
    v45);
  if ( v46 )
    winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(&v46);
  v30 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
  if ( *((_QWORD *)&v32 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
      if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
    }
  }
  if ( v34 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v34);
  asg::SemanticPipelines::QueryEmbeddings::~QueryEmbeddings((asg::SemanticPipelines::QueryEmbeddings *)&v39);
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
    winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(&v33);
  if ( *v8 )
    winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(v8);
  v21 = *(volatile signed __int32 **)(v25 + 8);
LABEL_57:
  if ( v21 )
  {
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  return v47;
}

```

## disassembly

```asm
0x18001f090  mov     [rsp-8+arg_18], rbx
0x18001f095  mov     [rsp-8+arg_10], r8
0x18001f09a  mov     [rsp-8+arg_8], rdx
0x18001f09f  push    rbp
0x18001f0a0  push    rsi
0x18001f0a1  push    rdi
0x18001f0a2  push    r12
0x18001f0a4  push    r13
0x18001f0a6  push    r14
0x18001f0a8  push    r15
0x18001f0aa  lea     rbp, [rsp-0Fh]
0x18001f0af  sub     rsp, 100h
0x18001f0b6  mov     r12, r9
0x18001f0b9  mov     r14, r8
0x18001f0bc  mov     r13, rcx
0x18001f0bf  xor     ebx, ebx
0x18001f0c1  mov     [rsp+130h+var_F0], rbx
0x18001f0c6  xorps   xmm0, xmm0
0x18001f0c9  movdqu  [rbp+3Fh+var_80], xmm0
0x18001f0ce  mov     r8b, 1
0x18001f0d1  lea     rdx, [rsp+130h+var_E0]
0x18001f0d6  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18001f0db  nop
0x18001f0dc  mov     r15d, ebx
0x18001f0df  mov     rdx, [r13+0F0h]
0x18001f0e6  test    rdx, rdx
0x18001f0e9  jz      short loc_18001F116
0x18001f0eb  add     rdx, 0FFFFFFFFFFFFFFF0h
0x18001f0ef  jz      short loc_18001F116
0x18001f0f1  mov     r15, rdx
0x18001f0f4  mov     rax, [rdx+8]
0x18001f0f8  test    rax, rax
0x18001f0fb  js      short loc_18001F111
0x18001f0fd  nop     dword ptr [rax]
0x18001f100  lea     rcx, [rax+1]
0x18001f104  lock cmpxchg [rdx+8], rcx
0x18001f10a  jz      short loc_18001F116
0x18001f10c  test    rax, rax
0x18001f10f  jns     short loc_18001F100
0x18001f111  lock inc dword ptr [rax+rax+18h]
0x18001f116  mov     [rsp+130h+var_F0], r15
0x18001f11b  mov     rax, [r15+0E8h]
0x18001f122  test    rax, rax
0x18001f125  jz      short loc_18001F12B
0x18001f127  lock inc dword ptr [rax+8]
0x18001f12b  mov     rsi, [r15+0E0h]
0x18001f132  mov     rdi, [r15+0E8h]
0x18001f139  mov     qword ptr [rbp+3Fh+var_80], rsi
0x18001f13d  mov     qword ptr [rbp+3Fh+var_80+8], rdi
0x18001f141  mov     edx, 2
0x18001f146  mov     rcx, r13
0x18001f149  call    ?IsGeneratorClosed@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA_NW4CommonIndexModelKind@2345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IsGeneratorClosed(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CommonIndexModelKind)
0x18001f14e  test    al, al
0x18001f150  jz      loc_18001F230
0x18001f156  mov     ecx, 80h; Size
0x18001f15b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f160  mov     [rbp+3Fh+arg_0], rax
0x18001f164  lea     rcx, [rax+10h]
0x18001f168  lea     rdx, ??_7?$produce@UQueryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIQueryResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryResult>::`vftable'
0x18001f16f  mov     [rcx], rdx
0x18001f172  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001f179  mov     qword ptr [rax+8], 1
0x18001f181  mov     dword ptr [rax+1Ch], 69h ; 'i'
0x18001f188  mov     dword ptr [rax+20h], 80004005h
0x18001f18f  mov     [rax+28h], rbx
0x18001f193  mov     [rax+30h], rbx
0x18001f197  mov     [rax+70h], rbx
0x18001f19b  mov     [rax+78h], rbx
0x18001f19f  lea     rdx, ??_7?$heap_implements@UQueryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult>::`vftable'
0x18001f1a6  mov     [rax], rdx
0x18001f1a9  mov     rdx, [rbp+3Fh+arg_8]
0x18001f1ad  mov     [rdx], rcx
0x18001f1b0  cmp     [rsp+130h+var_D8], 0
0x18001f1b5  jz      short loc_18001F1C2
0x18001f1b7  mov     rcx, [rsp+130h+var_E0]; _Mtx_t
0x18001f1bc  call    _Mtx_unlock
0x18001f1c1  nop
0x18001f1c2  test    rdi, rdi
0x18001f1c5  mov     ebx, 0FFFFFFFFh
0x18001f1ca  jz      short loc_18001F204
0x18001f1cc  mov     eax, ebx
0x18001f1ce  lock xadd [rdi+8], eax
0x18001f1d3  cmp     eax, 1
0x18001f1d6  jnz     short loc_18001F204
0x18001f1d8  mov     rax, [rdi]
0x18001f1db  mov     rcx, rdi
0x18001f1de  mov     rax, [rax]
0x18001f1e1  call    cs:__guard_dispatch_icall_fptr
0x18001f1e7  mov     eax, ebx
0x18001f1e9  lock xadd [rdi+0Ch], eax
0x18001f1ee  cmp     eax, 1
0x18001f1f1  jnz     short loc_18001F204
0x18001f1f3  mov     rax, [rdi]
0x18001f1f6  mov     rcx, rdi
0x18001f1f9  mov     rax, [rax+8]
0x18001f1fd  call    cs:__guard_dispatch_icall_fptr
0x18001f203  nop
0x18001f204  test    r15, r15
0x18001f207  jz      short loc_18001F214
0x18001f209  lea     rcx, [rsp+130h+var_F0]
0x18001f20e  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18001f213  nop
0x18001f214  cmp     qword ptr [r14], 0
0x18001f218  jz      short loc_18001F223
0x18001f21a  mov     rcx, r14
0x18001f21d  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18001f222  nop
0x18001f223  mov     rax, [rbp+3Fh+arg_30]
0x18001f227  mov     rdi, [rax+8]
0x18001f22b  jmp     loc_18001F4EA
0x18001f230  mov     edx, 2
0x18001f235  mov     rcx, r13
0x18001f238  call    ?IsLoaded@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEBA_NW4CommonIndexModelKind@2345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IsLoaded(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CommonIndexModelKind)
0x18001f23d  test    al, al
0x18001f23f  jnz     short loc_18001F278
0x18001f241  mov     ecx, 80h; Size
0x18001f246  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f24b  mov     [rbp+3Fh+arg_0], rax
0x18001f24f  lea     rcx, [rax+10h]
0x18001f253  lea     rdx, ??_7?$produce@UQueryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIQueryResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryResult>::`vftable'
0x18001f25a  mov     [rcx], rdx
0x18001f25d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001f264  mov     qword ptr [rax+8], 1
0x18001f26c  mov     dword ptr [rax+1Ch], 6Eh ; 'n'
0x18001f273  jmp     loc_18001F188
0x18001f278  cmp     [rsp+130h+var_D8], 0
0x18001f27d  jz      short loc_18001F289
0x18001f27f  mov     rcx, [rsp+130h+var_E0]; _Mtx_t
0x18001f284  call    _Mtx_unlock
0x18001f289  mov     rax, [r12]
0x18001f28d  test    rax, rax
0x18001f290  jz      short loc_18001F29B
0x18001f292  mov     rcx, [rax+10h]
0x18001f296  mov     ebx, [rax+4]
0x18001f299  jmp     short loc_18001F2A2
0x18001f29b  lea     rcx, String
0x18001f2a2  mov     qword ptr [rsp+130h+var_100], rcx
0x18001f2a7  mov     qword ptr [rsp+130h+var_100+8], rbx
0x18001f2ac  movaps  xmm0, [rsp+130h+var_100]
0x18001f2b1  movdqa  [rsp+130h+var_100], xmm0
0x18001f2b7  xor     r9d, r9d
0x18001f2ba  lea     r8, [rsp+130h+var_100]
0x18001f2bf  lea     rdx, [rbp+3Fh+var_B0]
0x18001f2c3  mov     rcx, rsi
0x18001f2c6  call    ?ProcessText@DualTextQueryEmbeddingPipeline@SemanticPipelines@asg@@QEAA?AUQueryEmbeddings@23@V?$span@$$CB_S$0?0@std@@W4ExecutionPriorityHint@SemanticRegistry@3@@Z; asg::SemanticPipelines::DualTextQueryEmbeddingPipeline::ProcessText(std::span<char16_t const,-1>,asg::SemanticRegistry::ExecutionPriorityHint)
0x18001f2cb  nop
0x18001f2cc  xorps   xmm0, xmm0
0x18001f2cf  movdqu  [rsp+130h+var_D0], xmm0
0x18001f2d5  mov     rcx, [rbp+3Fh+var_A8]
0x18001f2d9  test    rcx, rcx
0x18001f2dc  jz      short loc_18001F2E6
0x18001f2de  lock inc dword ptr [rcx+8]
0x18001f2e2  mov     rcx, [rbp+3Fh+var_A8]
0x18001f2e6  mov     rax, [rbp+3Fh+var_B0]
0x18001f2ea  mov     qword ptr [rsp+130h+var_D0], rax
0x18001f2ef  mov     qword ptr [rsp+130h+var_D0+8], rcx
0x18001f2f4  movdqu  [rsp+130h+var_C0], xmm0
0x18001f2fa  mov     rcx, [rbp+3Fh+var_98]
0x18001f2fe  test    rcx, rcx
0x18001f301  jz      short loc_18001F30B
0x18001f303  lock inc dword ptr [rcx+8]
0x18001f307  mov     rcx, [rbp+3Fh+var_98]
0x18001f30b  mov     rax, [rbp+3Fh+var_A0]
0x18001f30f  mov     qword ptr [rsp+130h+var_C0], rax
0x18001f314  mov     qword ptr [rbp+3Fh+var_C0+8], rcx
0x18001f318  lea     rdx, [rsp+130h+var_D0]
0x18001f31d  lea     rcx, [rsp+130h+var_E8]
0x18001f322  call    ?MakeTextQueryEmbeddings@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUQueryEmbeddings@234567@U8SemanticPipelines@asg@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MakeTextQueryEmbeddings(asg::SemanticPipelines::QueryEmbeddings)
0x18001f327  nop
0x18001f328  xorps   xmm0, xmm0
0x18001f32b  movdqu  [rsp+130h+var_100], xmm0
0x18001f331  mov     r12, [rbp+3Fh+arg_30]
0x18001f335  mov     rax, [r12+8]
0x18001f33a  test    rax, rax
0x18001f33d  jz      short loc_18001F343
0x18001f33f  lock inc dword ptr [rax+8]
0x18001f343  mov     rax, [r12]
0x18001f347  mov     qword ptr [rsp+130h+var_100], rax
0x18001f34c  mov     rax, [r12+8]
0x18001f351  mov     qword ptr [rsp+130h+var_100+8], rax
0x18001f356  lea     rax, [rsp+130h+var_100]
0x18001f35b  mov     [rbp+3Fh+var_38], rax
0x18001f35f  mov     rdx, [r14]
0x18001f362  mov     [rbp+3Fh+arg_0], rdx
0x18001f366  test    rdx, rdx
0x18001f369  jz      short loc_18001F38A
0x18001f36b  mov     rax, [rdx+8]
0x18001f36f  test    rax, rax
0x18001f372  js      short loc_18001F385
0x18001f374  lea     rcx, [rax+1]
0x18001f378  lock cmpxchg [rdx+8], rcx
0x18001f37e  jz      short loc_18001F38A
0x18001f380  test    rax, rax
0x18001f383  jns     short loc_18001F374
0x18001f385  lock inc dword ptr [rax+rax+18h]
0x18001f38a  lea     rax, [rbp+3Fh+arg_0]
0x18001f38e  mov     [rsp+130h+var_E0], rax
0x18001f393  mov     rax, [rbp+3Fh+arg_20]
0x18001f397  mov     [rbp+3Fh+var_88], rax
0x18001f39b  mov     dword ptr [rsp+130h+var_D0], 7BDh
0x18001f3a3  mov     dword ptr [rsp+130h+var_D0+4], 14h
0x18001f3ab  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18001f3b2  mov     qword ptr [rsp+130h+var_D0+8], rax
0x18001f3b7  lea     rax, aStructWinrtMic_10; "struct winrt::Microsoft::Asg::SemanticI"...
0x18001f3be  mov     qword ptr [rsp+130h+var_C0], rax
0x18001f3c3  mov     [rbp+3Fh+var_70], r13
0x18001f3c7  lea     rax, [rsp+130h+var_E8]
0x18001f3cc  mov     [rbp+3Fh+var_68], rax
0x18001f3d0  lea     rax, [rbp+3Fh+var_B0]
0x18001f3d4  mov     [rbp+3Fh+var_60], rax
0x18001f3d8  lea     rax, [rbp+3Fh+var_88]
0x18001f3dc  mov     [rbp+3Fh+var_58], rax
0x18001f3e0  mov     rax, [rbp+3Fh+arg_28]
0x18001f3e4  mov     [rbp+3Fh+var_50], rax
0x18001f3e8  lea     rax, [rsp+130h+var_100]
0x18001f3ed  mov     [rbp+3Fh+var_48], rax
0x18001f3f1  lea     rax, [rbp+3Fh+arg_0]
0x18001f3f5  mov     [rbp+3Fh+var_40], rax
0x18001f3f9  lea     rax, [rsp+130h+var_D0]
0x18001f3fe  mov     [rsp+130h+var_110], rax
0x18001f403  lea     r8, [rbp+3Fh+var_70]
0x18001f407  mov     rdx, [rbp+3Fh+arg_8]
0x18001f40b  mov     rcx, r13
0x18001f40e  call    ??$InvokeDbMethod@V_lambda_1_@?1???$Query@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUQueryResult@456789@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@9@AEBUQueryEmbeddings@456789@AEBUQueryEmbeddings@SemanticPipelines@asg@@_KAEAUSemanticQueryOptions@3456789@UCancellationToken@asg@@@Z@$$A6AXX_E@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?A_P$$QEAV_lambda_1_@?1???$Query@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@01234567@AEAA?AUQueryResult@234567@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@7@AEBUQueryEmbeddings@234567@AEBUQueryEmbeddings@SemanticPipelines@asg@@_KAEAUSemanticQueryOptions@1234567@UCancellationToken@asg@@@Z@$$Q6AXX_EAEBUsource_location@std@@@Z
0x18001f413  nop
0x18001f414  cmp     [rbp+3Fh+arg_0], 0
0x18001f419  jz      short loc_18001F425
0x18001f41b  lea     rcx, [rbp+3Fh+arg_0]
0x18001f41f  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18001f424  nop
0x18001f425  mov     ebx, 0FFFFFFFFh
0x18001f42a  mov     rsi, qword ptr [rsp+130h+var_100+8]
0x18001f42f  test    rsi, rsi
0x18001f432  jz      short loc_18001F46C
0x18001f434  mov     eax, ebx
0x18001f436  lock xadd [rsi+8], eax
0x18001f43b  cmp     eax, 1
0x18001f43e  jnz     short loc_18001F46C
0x18001f440  mov     rax, [rsi]
0x18001f443  mov     rcx, rsi
0x18001f446  mov     rax, [rax]
0x18001f449  call    cs:__guard_dispatch_icall_fptr
0x18001f44f  mov     eax, ebx
0x18001f451  lock xadd [rsi+0Ch], eax
0x18001f456  cmp     eax, 1
0x18001f459  jnz     short loc_18001F46C
0x18001f45b  mov     rax, [rsi]
0x18001f45e  mov     rcx, rsi
0x18001f461  mov     rax, [rax+8]
0x18001f465  call    cs:__guard_dispatch_icall_fptr
0x18001f46b  nop
0x18001f46c  cmp     [rsp+130h+var_E8], 0
0x18001f472  jz      short loc_18001F47F
0x18001f474  lea     rcx, [rsp+130h+var_E8]
0x18001f479  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18001f47e  nop
0x18001f47f  lea     rcx, [rbp+3Fh+var_B0]; this
0x18001f483  call    ??1QueryEmbeddings@SemanticPipelines@asg@@QEAA@XZ; asg::SemanticPipelines::QueryEmbeddings::~QueryEmbeddings(void)
0x18001f488  nop
0x18001f489  test    rdi, rdi
0x18001f48c  jz      short loc_18001F4C6
0x18001f48e  mov     eax, ebx
0x18001f490  lock xadd [rdi+8], eax
0x18001f495  cmp     eax, 1
0x18001f498  jnz     short loc_18001F4C6
0x18001f49a  mov     rax, [rdi]
0x18001f49d  mov     rcx, rdi
0x18001f4a0  mov     rax, [rax]
0x18001f4a3  call    cs:__guard_dispatch_icall_fptr
0x18001f4a9  mov     eax, ebx
0x18001f4ab  lock xadd [rdi+0Ch], eax
0x18001f4b0  cmp     eax, 1
0x18001f4b3  jnz     short loc_18001F4C6
0x18001f4b5  mov     rax, [rdi]
0x18001f4b8  mov     rcx, rdi
0x18001f4bb  mov     rax, [rax+8]
0x18001f4bf  call    cs:__guard_dispatch_icall_fptr
0x18001f4c5  nop
0x18001f4c6  test    r15, r15
0x18001f4c9  jz      short loc_18001F4D6
0x18001f4cb  lea     rcx, [rsp+130h+var_F0]
0x18001f4d0  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18001f4d5  nop
0x18001f4d6  cmp     qword ptr [r14], 0
0x18001f4da  jz      short loc_18001F4E5
0x18001f4dc  mov     rcx, r14
0x18001f4df  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18001f4e4  nop
0x18001f4e5  mov     rdi, [r12+8]
0x18001f4ea  test    rdi, rdi
0x18001f4ed  jz      short loc_18001F524
0x18001f4ef  mov     eax, ebx
0x18001f4f1  lock xadd [rdi+8], eax
0x18001f4f6  cmp     eax, 1
0x18001f4f9  jnz     short loc_18001F524
0x18001f4fb  mov     rax, [rdi]
0x18001f4fe  mov     rcx, rdi
0x18001f501  mov     rax, [rax]
0x18001f504  call    cs:__guard_dispatch_icall_fptr
0x18001f50a  lock xadd [rdi+0Ch], ebx
  ... truncated ...
```
