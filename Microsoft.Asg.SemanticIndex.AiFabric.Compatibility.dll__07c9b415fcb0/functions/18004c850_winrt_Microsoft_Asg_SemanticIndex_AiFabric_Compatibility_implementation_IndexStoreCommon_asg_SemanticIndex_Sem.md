# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::QueryText<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>>(winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>,winrt::hstring const &,unsigned __int64,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticQueryOptions &,asg::CancellationToken)

- ea: `0x18004c850`
- end: `0x18004cd03`
- name: `??$QueryText@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AUQueryResult@234567@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@7@AEBUhstring@7@_KAEAUSemanticQueryOptions@1234567@UCancellationToken@asg@@@Z`
- size: `1203`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004a320`
- `0x18023e230`

## callees

- `0x180003bd0`
- `0x180009770`
- `0x180009a70`
- `0x18000b2a0`
- `0x18002f8e0`
- `0x18002f9f0`
- `0x18004c850`
- `0x18004d5e0`
- `0x180054440`
- `0x18009ff30`
- `0x1801d2b20`
- `0x1801f7190`
- `0x180242120`

## string_xrefs

- `0x18004cb6b`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18004cb77`: `struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibil`

## pseudocode

```c
_QWORD *__fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::QueryText<winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>>(
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
  if ( !(unsigned __int8)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IsLoaded(
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
                    ":TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::imple"
                    "mentation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibil"
                    "ity::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::i"
                    "mplementation::TextEmbeddingsGenerator>::Query<struct winrt::com_ptr<struct winrt::Microsoft::Asg::S"
                    "emanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>>(struct winrt::com_pt"
                    "r<struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticText"
                    "IndexStore>,const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddi"
                    "ngs &,const struct asg::SemanticPipelines::QueryEmbeddings &,unsigned __int64,struct winrt::Microsof"
                    "t::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticQueryOptions &,struct asg::C"
                    "ancellationToken)";
  v45[0] = a1;
  v45[1] = &v34;
  v45[2] = &v39;
  v45[3] = &v43;
  v45[4] = a6;
  v45[5] = &v32;
  v45[6] = &v46;
  ___InvokeDbMethod_V_lambda_1___1____Query_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt_____IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AUQueryResult_456789_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___9_AEBUQueryEmbeddings_456789_AEBUQueryEmbeddings_SemanticPipelines_asg___KAEAUSemanticQueryOptions_3456789_UCancellationToken_asg___Z___A6AXX_E___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_A_P__QEAV_lambda_1___1____Query_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___winrt___01234567_AEAA_AUQueryResult_234567_U__com_ptr_USemanticTextIndexStore_implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___7_AEBUQueryEmbeddings_234567_AEBUQueryEmbeddings_SemanticPipelines_asg___KAEAUSemanticQueryOptions_1234567_UCancellationToken_asg___Z___Q6AXX_EAEBUsource_location_std___Z(
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
0x18004c850  mov     [rsp-8+arg_18], rbx
0x18004c855  mov     [rsp-8+arg_10], r8
0x18004c85a  mov     [rsp-8+arg_8], rdx
0x18004c85f  push    rbp
0x18004c860  push    rsi
0x18004c861  push    rdi
0x18004c862  push    r12
0x18004c864  push    r13
0x18004c866  push    r14
0x18004c868  push    r15
0x18004c86a  lea     rbp, [rsp-0Fh]
0x18004c86f  sub     rsp, 100h
0x18004c876  mov     r12, r9
0x18004c879  mov     r14, r8
0x18004c87c  mov     r13, rcx
0x18004c87f  xor     ebx, ebx
0x18004c881  mov     [rsp+130h+var_F0], rbx
0x18004c886  xorps   xmm0, xmm0
0x18004c889  movdqu  [rbp+3Fh+var_80], xmm0
0x18004c88e  mov     r8b, 1
0x18004c891  lea     rdx, [rsp+130h+var_E0]
0x18004c896  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18004c89b  nop
0x18004c89c  mov     r15d, ebx
0x18004c89f  mov     rdx, [r13+0F0h]
0x18004c8a6  test    rdx, rdx
0x18004c8a9  jz      short loc_18004C8D6
0x18004c8ab  add     rdx, 0FFFFFFFFFFFFFFF0h
0x18004c8af  jz      short loc_18004C8D6
0x18004c8b1  mov     r15, rdx
0x18004c8b4  mov     rax, [rdx+8]
0x18004c8b8  test    rax, rax
0x18004c8bb  js      short loc_18004C8D1
0x18004c8bd  nop     dword ptr [rax]
0x18004c8c0  lea     rcx, [rax+1]
0x18004c8c4  lock cmpxchg [rdx+8], rcx
0x18004c8ca  jz      short loc_18004C8D6
0x18004c8cc  test    rax, rax
0x18004c8cf  jns     short loc_18004C8C0
0x18004c8d1  lock inc dword ptr [rax+rax+18h]
0x18004c8d6  mov     [rsp+130h+var_F0], r15
0x18004c8db  mov     rax, [r15+0E8h]
0x18004c8e2  test    rax, rax
0x18004c8e5  jz      short loc_18004C8EB
0x18004c8e7  lock inc dword ptr [rax+8]
0x18004c8eb  mov     rsi, [r15+0E0h]
0x18004c8f2  mov     rdi, [r15+0E8h]
0x18004c8f9  mov     qword ptr [rbp+3Fh+var_80], rsi
0x18004c8fd  mov     qword ptr [rbp+3Fh+var_80+8], rdi
0x18004c901  mov     edx, 2
0x18004c906  mov     rcx, r13
0x18004c909  call    ?IsGeneratorClosed@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA_NW4CommonIndexModelKind@2345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IsGeneratorClosed(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CommonIndexModelKind)
0x18004c90e  test    al, al
0x18004c910  jz      loc_18004C9F0
0x18004c916  mov     ecx, 80h; Size
0x18004c91b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004c920  mov     [rbp+3Fh+arg_0], rax
0x18004c924  lea     rcx, [rax+10h]
0x18004c928  lea     rdx, ??_7?$produce@UQueryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIQueryResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryResult>::`vftable'
0x18004c92f  mov     [rcx], rdx
0x18004c932  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004c939  mov     qword ptr [rax+8], 1
0x18004c941  mov     dword ptr [rax+1Ch], 69h ; 'i'
0x18004c948  mov     dword ptr [rax+20h], 80004005h
0x18004c94f  mov     [rax+28h], rbx
0x18004c953  mov     [rax+30h], rbx
0x18004c957  mov     [rax+70h], rbx
0x18004c95b  mov     [rax+78h], rbx
0x18004c95f  lea     rdx, ??_7?$heap_implements@UQueryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult>::`vftable'
0x18004c966  mov     [rax], rdx
0x18004c969  mov     rdx, [rbp+3Fh+arg_8]
0x18004c96d  mov     [rdx], rcx
0x18004c970  cmp     [rsp+130h+var_D8], 0
0x18004c975  jz      short loc_18004C982
0x18004c977  mov     rcx, [rsp+130h+var_E0]; _Mtx_t
0x18004c97c  call    _Mtx_unlock
0x18004c981  nop
0x18004c982  test    rdi, rdi
0x18004c985  mov     ebx, 0FFFFFFFFh
0x18004c98a  jz      short loc_18004C9C4
0x18004c98c  mov     eax, ebx
0x18004c98e  lock xadd [rdi+8], eax
0x18004c993  cmp     eax, 1
0x18004c996  jnz     short loc_18004C9C4
0x18004c998  mov     rax, [rdi]
0x18004c99b  mov     rcx, rdi
0x18004c99e  mov     rax, [rax]
0x18004c9a1  call    cs:__guard_dispatch_icall_fptr
0x18004c9a7  mov     eax, ebx
0x18004c9a9  lock xadd [rdi+0Ch], eax
0x18004c9ae  cmp     eax, 1
0x18004c9b1  jnz     short loc_18004C9C4
0x18004c9b3  mov     rax, [rdi]
0x18004c9b6  mov     rcx, rdi
0x18004c9b9  mov     rax, [rax+8]
0x18004c9bd  call    cs:__guard_dispatch_icall_fptr
0x18004c9c3  nop
0x18004c9c4  test    r15, r15
0x18004c9c7  jz      short loc_18004C9D4
0x18004c9c9  lea     rcx, [rsp+130h+var_F0]
0x18004c9ce  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18004c9d3  nop
0x18004c9d4  cmp     qword ptr [r14], 0
0x18004c9d8  jz      short loc_18004C9E3
0x18004c9da  mov     rcx, r14
0x18004c9dd  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18004c9e2  nop
0x18004c9e3  mov     rax, [rbp+3Fh+arg_30]
0x18004c9e7  mov     rdi, [rax+8]
0x18004c9eb  jmp     loc_18004CCAA
0x18004c9f0  mov     edx, 2
0x18004c9f5  mov     rcx, r13
0x18004c9f8  call    ?IsLoaded@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEBA_NW4CommonIndexModelKind@2345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::IsLoaded(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::CommonIndexModelKind)
0x18004c9fd  test    al, al
0x18004c9ff  jnz     short loc_18004CA38
0x18004ca01  mov     ecx, 80h; Size
0x18004ca06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ca0b  mov     [rbp+3Fh+arg_0], rax
0x18004ca0f  lea     rcx, [rax+10h]
0x18004ca13  lea     rdx, ??_7?$produce@UQueryResult@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIQueryResult@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::QueryResult,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryResult>::`vftable'
0x18004ca1a  mov     [rcx], rdx
0x18004ca1d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004ca24  mov     qword ptr [rax+8], 1
0x18004ca2c  mov     dword ptr [rax+1Ch], 6Eh ; 'n'
0x18004ca33  jmp     loc_18004C948
0x18004ca38  cmp     [rsp+130h+var_D8], 0
0x18004ca3d  jz      short loc_18004CA49
0x18004ca3f  mov     rcx, [rsp+130h+var_E0]; _Mtx_t
0x18004ca44  call    _Mtx_unlock
0x18004ca49  mov     rax, [r12]
0x18004ca4d  test    rax, rax
0x18004ca50  jz      short loc_18004CA5B
0x18004ca52  mov     rcx, [rax+10h]
0x18004ca56  mov     ebx, [rax+4]
0x18004ca59  jmp     short loc_18004CA62
0x18004ca5b  lea     rcx, String
0x18004ca62  mov     qword ptr [rsp+130h+var_100], rcx
0x18004ca67  mov     qword ptr [rsp+130h+var_100+8], rbx
0x18004ca6c  movaps  xmm0, [rsp+130h+var_100]
0x18004ca71  movdqa  [rsp+130h+var_100], xmm0
0x18004ca77  xor     r9d, r9d
0x18004ca7a  lea     r8, [rsp+130h+var_100]
0x18004ca7f  lea     rdx, [rbp+3Fh+var_B0]
0x18004ca83  mov     rcx, rsi
0x18004ca86  call    ?ProcessText@DualTextQueryEmbeddingPipeline@SemanticPipelines@asg@@QEAA?AUQueryEmbeddings@23@V?$span@$$CB_S$0?0@std@@W4ExecutionPriorityHint@SemanticRegistry@3@@Z; asg::SemanticPipelines::DualTextQueryEmbeddingPipeline::ProcessText(std::span<char16_t const,-1>,asg::SemanticRegistry::ExecutionPriorityHint)
0x18004ca8b  nop
0x18004ca8c  xorps   xmm0, xmm0
0x18004ca8f  movdqu  [rsp+130h+var_D0], xmm0
0x18004ca95  mov     rcx, [rbp+3Fh+var_A8]
0x18004ca99  test    rcx, rcx
0x18004ca9c  jz      short loc_18004CAA6
0x18004ca9e  lock inc dword ptr [rcx+8]
0x18004caa2  mov     rcx, [rbp+3Fh+var_A8]
0x18004caa6  mov     rax, [rbp+3Fh+var_B0]
0x18004caaa  mov     qword ptr [rsp+130h+var_D0], rax
0x18004caaf  mov     qword ptr [rsp+130h+var_D0+8], rcx
0x18004cab4  movdqu  [rsp+130h+var_C0], xmm0
0x18004caba  mov     rcx, [rbp+3Fh+var_98]
0x18004cabe  test    rcx, rcx
0x18004cac1  jz      short loc_18004CACB
0x18004cac3  lock inc dword ptr [rcx+8]
0x18004cac7  mov     rcx, [rbp+3Fh+var_98]
0x18004cacb  mov     rax, [rbp+3Fh+var_A0]
0x18004cacf  mov     qword ptr [rsp+130h+var_C0], rax
0x18004cad4  mov     qword ptr [rbp+3Fh+var_C0+8], rcx
0x18004cad8  lea     rdx, [rsp+130h+var_D0]
0x18004cadd  lea     rcx, [rsp+130h+var_E8]
0x18004cae2  call    ?MakeTextQueryEmbeddings@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUQueryEmbeddings@234567@U8SemanticPipelines@asg@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MakeTextQueryEmbeddings(asg::SemanticPipelines::QueryEmbeddings)
0x18004cae7  nop
0x18004cae8  xorps   xmm0, xmm0
0x18004caeb  movdqu  [rsp+130h+var_100], xmm0
0x18004caf1  mov     r12, [rbp+3Fh+arg_30]
0x18004caf5  mov     rax, [r12+8]
0x18004cafa  test    rax, rax
0x18004cafd  jz      short loc_18004CB03
0x18004caff  lock inc dword ptr [rax+8]
0x18004cb03  mov     rax, [r12]
0x18004cb07  mov     qword ptr [rsp+130h+var_100], rax
0x18004cb0c  mov     rax, [r12+8]
0x18004cb11  mov     qword ptr [rsp+130h+var_100+8], rax
0x18004cb16  lea     rax, [rsp+130h+var_100]
0x18004cb1b  mov     [rbp+3Fh+var_38], rax
0x18004cb1f  mov     rdx, [r14]
0x18004cb22  mov     [rbp+3Fh+arg_0], rdx
0x18004cb26  test    rdx, rdx
0x18004cb29  jz      short loc_18004CB4A
0x18004cb2b  mov     rax, [rdx+8]
0x18004cb2f  test    rax, rax
0x18004cb32  js      short loc_18004CB45
0x18004cb34  lea     rcx, [rax+1]
0x18004cb38  lock cmpxchg [rdx+8], rcx
0x18004cb3e  jz      short loc_18004CB4A
0x18004cb40  test    rax, rax
0x18004cb43  jns     short loc_18004CB34
0x18004cb45  lock inc dword ptr [rax+rax+18h]
0x18004cb4a  lea     rax, [rbp+3Fh+arg_0]
0x18004cb4e  mov     [rsp+130h+var_E0], rax
0x18004cb53  mov     rax, [rbp+3Fh+arg_20]
0x18004cb57  mov     [rbp+3Fh+var_88], rax
0x18004cb5b  mov     dword ptr [rsp+130h+var_D0], 7BDh
0x18004cb63  mov     dword ptr [rsp+130h+var_D0+4], 14h
0x18004cb6b  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18004cb72  mov     qword ptr [rsp+130h+var_D0+8], rax
0x18004cb77  lea     rax, aStructWinrtMic_2; "struct winrt::Microsoft::Asg::SemanticI"...
0x18004cb7e  mov     qword ptr [rsp+130h+var_C0], rax
0x18004cb83  mov     [rbp+3Fh+var_70], r13
0x18004cb87  lea     rax, [rsp+130h+var_E8]
0x18004cb8c  mov     [rbp+3Fh+var_68], rax
0x18004cb90  lea     rax, [rbp+3Fh+var_B0]
0x18004cb94  mov     [rbp+3Fh+var_60], rax
0x18004cb98  lea     rax, [rbp+3Fh+var_88]
0x18004cb9c  mov     [rbp+3Fh+var_58], rax
0x18004cba0  mov     rax, [rbp+3Fh+arg_28]
0x18004cba4  mov     [rbp+3Fh+var_50], rax
0x18004cba8  lea     rax, [rsp+130h+var_100]
0x18004cbad  mov     [rbp+3Fh+var_48], rax
0x18004cbb1  lea     rax, [rbp+3Fh+arg_0]
0x18004cbb5  mov     [rbp+3Fh+var_40], rax
0x18004cbb9  lea     rax, [rsp+130h+var_D0]
0x18004cbbe  mov     [rsp+130h+var_110], rax
0x18004cbc3  lea     r8, [rbp+3Fh+var_70]
0x18004cbc7  mov     rdx, [rbp+3Fh+arg_8]
0x18004cbcb  mov     rcx, r13
0x18004cbce  call    ??$InvokeDbMethod@V_lambda_1_@?1???$Query@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUQueryResult@456789@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@9@AEBUQueryEmbeddings@456789@AEBUQueryEmbeddings@SemanticPipelines@asg@@_KAEAUSemanticQueryOptions@3456789@UCancellationToken@asg@@@Z@$$A6AXX_E@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?A_P$$QEAV_lambda_1_@?1???$Query@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@winrt@@@01234567@AEAA?AUQueryResult@234567@U?$com_ptr@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@7@AEBUQueryEmbeddings@234567@AEBUQueryEmbeddings@SemanticPipelines@asg@@_KAEAUSemanticQueryOptions@1234567@UCancellationToken@asg@@@Z@$$Q6AXX_EAEBUsource_location@std@@@Z
0x18004cbd3  nop
0x18004cbd4  cmp     [rbp+3Fh+arg_0], 0
0x18004cbd9  jz      short loc_18004CBE5
0x18004cbdb  lea     rcx, [rbp+3Fh+arg_0]
0x18004cbdf  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18004cbe4  nop
0x18004cbe5  mov     ebx, 0FFFFFFFFh
0x18004cbea  mov     rsi, qword ptr [rsp+130h+var_100+8]
0x18004cbef  test    rsi, rsi
0x18004cbf2  jz      short loc_18004CC2C
0x18004cbf4  mov     eax, ebx
0x18004cbf6  lock xadd [rsi+8], eax
0x18004cbfb  cmp     eax, 1
0x18004cbfe  jnz     short loc_18004CC2C
0x18004cc00  mov     rax, [rsi]
0x18004cc03  mov     rcx, rsi
0x18004cc06  mov     rax, [rax]
0x18004cc09  call    cs:__guard_dispatch_icall_fptr
0x18004cc0f  mov     eax, ebx
0x18004cc11  lock xadd [rsi+0Ch], eax
0x18004cc16  cmp     eax, 1
0x18004cc19  jnz     short loc_18004CC2C
0x18004cc1b  mov     rax, [rsi]
0x18004cc1e  mov     rcx, rsi
0x18004cc21  mov     rax, [rax+8]
0x18004cc25  call    cs:__guard_dispatch_icall_fptr
0x18004cc2b  nop
0x18004cc2c  cmp     [rsp+130h+var_E8], 0
0x18004cc32  jz      short loc_18004CC3F
0x18004cc34  lea     rcx, [rsp+130h+var_E8]
0x18004cc39  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18004cc3e  nop
0x18004cc3f  lea     rcx, [rbp+3Fh+var_B0]; this
0x18004cc43  call    ??1QueryEmbeddings@SemanticPipelines@asg@@QEAA@XZ; asg::SemanticPipelines::QueryEmbeddings::~QueryEmbeddings(void)
0x18004cc48  nop
0x18004cc49  test    rdi, rdi
0x18004cc4c  jz      short loc_18004CC86
0x18004cc4e  mov     eax, ebx
0x18004cc50  lock xadd [rdi+8], eax
0x18004cc55  cmp     eax, 1
0x18004cc58  jnz     short loc_18004CC86
0x18004cc5a  mov     rax, [rdi]
0x18004cc5d  mov     rcx, rdi
0x18004cc60  mov     rax, [rax]
0x18004cc63  call    cs:__guard_dispatch_icall_fptr
0x18004cc69  mov     eax, ebx
0x18004cc6b  lock xadd [rdi+0Ch], eax
0x18004cc70  cmp     eax, 1
0x18004cc73  jnz     short loc_18004CC86
0x18004cc75  mov     rax, [rdi]
0x18004cc78  mov     rcx, rdi
0x18004cc7b  mov     rax, [rax+8]
0x18004cc7f  call    cs:__guard_dispatch_icall_fptr
0x18004cc85  nop
0x18004cc86  test    r15, r15
0x18004cc89  jz      short loc_18004CC96
0x18004cc8b  lea     rcx, [rsp+130h+var_F0]
0x18004cc90  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18004cc95  nop
0x18004cc96  cmp     qword ptr [r14], 0
0x18004cc9a  jz      short loc_18004CCA5
0x18004cc9c  mov     rcx, r14
0x18004cc9f  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18004cca4  nop
0x18004cca5  mov     rdi, [r12+8]
0x18004ccaa  test    rdi, rdi
0x18004ccad  jz      short loc_18004CCE4
0x18004ccaf  mov     eax, ebx
0x18004ccb1  lock xadd [rdi+8], eax
0x18004ccb6  cmp     eax, 1
0x18004ccb9  jnz     short loc_18004CCE4
0x18004ccbb  mov     rax, [rdi]
0x18004ccbe  mov     rcx, rdi
0x18004ccc1  mov     rax, [rax]
0x18004ccc4  call    cs:__guard_dispatch_icall_fptr
0x18004ccca  lock xadd [rdi+0Ch], ebx
  ... truncated ...
```
