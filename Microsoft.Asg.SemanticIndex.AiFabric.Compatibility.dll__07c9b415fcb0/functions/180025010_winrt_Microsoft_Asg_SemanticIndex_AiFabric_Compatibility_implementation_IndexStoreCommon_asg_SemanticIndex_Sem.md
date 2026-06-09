# `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::GetItemEmbeddings(winrt::guid)'::`2'::_lambda_1_::operator()(void)

- ea: `0x180025010`
- end: `0x1800253c0`
- name: `??R_lambda_1_@?1??GetItemEmbeddings@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AU?$IVector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@9@Uguid@9@@Z@QEBA@XZ`
- size: `944`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800253c0`

## callees

- `0x180003bd0`
- `0x180006e30`
- `0x180007ba0`
- `0x180025010`
- `0x18002f890`
- `0x18002f8e0`
- `0x180032070`
- `0x180196e60`
- `0x1801d2b20`
- `0x1801f7160`
- `0x1801f7190`
- `0x180206ec0`

## string_xrefs

- `0x180025178`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18002517f`: `struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibil`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::GetItemEmbeddings'::`2'::_lambda_1_::operator()(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v5; // r8
  char *v6; // rdi
  char *v7; // rbx
  unsigned __int64 v8; // rdx
  __int64 v9; // r14
  _QWORD *v10; // rsi
  char *v11; // rdi
  _QWORD *v12; // rcx
  char *v13; // rbx
  __int64 v14; // rax
  char *v15; // rax
  __int64 v16; // rcx
  _QWORD *v17; // r9
  char *v18; // rdx
  void *v19; // rcx
  void *v20; // rax
  char *v21; // rbx
  char *v22; // rdi
  char *v23; // rax
  void *v24; // r8
  void *Block[2]; // [rsp+30h] [rbp-39h] BYREF
  char *v27; // [rsp+40h] [rbp-29h]
  void *v28[2]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v29; // [rsp+58h] [rbp-11h]
  int v30; // [rsp+68h] [rbp-1h]
  int v31; // [rsp+6Ch] [rbp+3h]
  const char *v32; // [rsp+70h] [rbp+7h]
  const char *v33; // [rsp+78h] [rbp+Fh]
  _QWORD v34[2]; // [rsp+80h] [rbp+17h] BYREF
  _Mtx_t v35; // [rsp+90h] [rbp+27h] BYREF
  char v36; // [rsp+98h] [rbp+2Fh]
  _QWORD *v37; // [rsp+D0h] [rbp+67h] BYREF

  LOBYTE(a3) = 1;
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
    *a1,
    &v35,
    a3);
  asg::SemanticIndex::SemanticIndexStore::TryGetItemEmbeddingKeys(*(_QWORD *)(*a1 + 168LL), v28, a1[1]);
  *(_OWORD *)Block = 0;
  v27 = 0;
  v6 = (char *)v28[1];
  v7 = (char *)v28[0];
  v8 = ((char *)v28[1] - (char *)v28[0]) / 48;
  if ( v8 )
  {
    if ( v8 > 0x1FFFFFFFFFFFFFFFLL )
      std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<unsigned char>> *>>::_Xlength(
        (char *)v28[1] - (char *)v28[0],
        v8,
        v5);
    _mm_lfence();
    v9 = v8;
    v10 = std::_Allocate<16,std::_Default_allocate_traits>(8 * v8);
    v11 = (char *)Block[1];
    v12 = v10;
    v13 = (char *)Block[0];
    if ( Block[0] != Block[1] )
    {
      do
      {
        v14 = *(_QWORD *)v13;
        *(_QWORD *)v13 = 0;
        *v12++ = v14;
        v13 += 8;
      }
      while ( v13 != v11 );
      v11 = (char *)Block[1];
      v13 = (char *)Block[0];
    }
    if ( v13 )
    {
      if ( v13 != v11 )
      {
        do
        {
          if ( *(_QWORD *)v13 )
            winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v13);
          v13 += 8;
        }
        while ( v13 != v11 );
        v13 = (char *)Block[0];
      }
      v15 = v13;
      if ( ((v27 - v13) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
      {
        v13 = (char *)*((_QWORD *)v13 - 1);
        if ( (unsigned __int64)(v15 - v13 - 8) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v13);
    }
    Block[0] = v10;
    Block[1] = v10;
    v27 = (char *)&v10[v9];
    v6 = (char *)v28[1];
    v7 = (char *)v28[0];
  }
  for ( ; v7 != v6; v7 += 48 )
  {
    v16 = *a1;
    v30 = 1825;
    v31 = 20;
    v32 = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
    v33 = "struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding __cdecl winrt::Microsoft::Asg:"
          ":SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIn"
          "dexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct"
          " winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struc"
          "t winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microso"
          "ft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::TryGetEmbedding(con"
          "st struct asg::SemanticIndex::ItemEmbeddingKey &)";
    v34[0] = v16;
    v34[1] = v7;
    ___InvokeDbMethod_V_lambda_1___1__TryGetEmbedding___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AUEmbedding_56789winrt__AEBUItemEmbeddingKey_7asg___Z___A6AXX_E___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_A_P__QEAV_lambda_1___1__TryGetEmbedding_01234567_AEAA_AUEmbedding_234567_AEBUItemEmbeddingKey_4asg___Z___Q6AXX_EAEBUsource_location_std___Z(
      v16,
      &v37,
      v34);
    std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>::_Emplace_one_at_back<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>(
      (__int64 **)Block,
      (__int64 *)&v37);
    if ( v37 )
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v37);
  }
  v17 = operator new(0x50u);
  v37 = v17;
  v17[2] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>>::`vftable';
  v17[3] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>>::`vftable';
  v17[4] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v17[1] = 1;
  *((_DWORD *)v17 + 10) = 0;
  v17[6] = 0;
  *v17 = &winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>::`vftable';
  v18 = v27;
  v27 = 0;
  v19 = Block[1];
  Block[1] = 0;
  v20 = Block[0];
  Block[0] = 0;
  v17[7] = v20;
  v17[8] = v19;
  v17[9] = v18;
  *v17 = &winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>>::`vftable';
  *a2 = v17 + 2;
  v21 = (char *)Block[0];
  if ( Block[0] )
  {
    v22 = (char *)Block[1];
    if ( Block[0] != Block[1] )
    {
      do
      {
        if ( *(_QWORD *)v21 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v21);
        v21 += 8;
      }
      while ( v21 != v22 );
      v21 = (char *)Block[0];
    }
    v23 = v21;
    if ( ((v27 - v21) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
    {
      v21 = (char *)*((_QWORD *)v21 - 1);
      if ( (unsigned __int64)(v23 - v21 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v21);
    *(_OWORD *)Block = 0;
    v27 = 0;
  }
  v24 = v28[0];
  if ( v28[0] )
  {
    if ( (unsigned __int64)(48 * ((signed __int64)(v29 - (unsigned __int64)v28[0]) / 48)) >= 0x1000 )
    {
      v24 = (void *)*((_QWORD *)v28[0] - 1);
      if ( (unsigned __int64)((char *)v28[0] - (char *)v24 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v24);
    *(_OWORD *)v28 = 0;
    v29 = 0;
  }
  if ( v36 )
    Mtx_unlock(v35);
  return a2;
}

```

## disassembly

```asm
0x180025010  mov     [rsp-8+arg_8], rbx
0x180025015  mov     [rsp-8+arg_10], rsi
0x18002501a  mov     [rsp-8+arg_18], rdi
0x18002501f  push    rbp
0x180025020  push    r12
0x180025022  push    r13
0x180025024  push    r14
0x180025026  push    r15
0x180025028  lea     rbp, [rsp-37h]
0x18002502d  sub     rsp, 0A0h
0x180025034  mov     r12, rdx
0x180025037  mov     r15, rcx
0x18002503a  xor     r13d, r13d
0x18002503d  mov     r8b, 1
0x180025040  lea     rdx, [rbp+57h+var_30]
0x180025044  mov     rcx, [rcx]
0x180025047  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18002504c  nop
0x18002504d  mov     rcx, [r15]
0x180025050  mov     r8, [r15+8]
0x180025054  lea     rdx, [rbp+57h+var_78]
0x180025058  mov     rcx, [rcx+0A8h]
0x18002505f  call    ?TryGetItemEmbeddingKeys@SemanticIndexStore@SemanticIndex@asg@@QEBA?AV?$vector@UItemEmbeddingKey@SemanticIndex@asg@@V?$allocator@UItemEmbeddingKey@SemanticIndex@asg@@@std@@@std@@AEBUGuid@3@@Z; asg::SemanticIndex::SemanticIndexStore::TryGetItemEmbeddingKeys(asg::Guid const &)
0x180025064  nop
0x180025065  xorps   xmm0, xmm0
0x180025068  movdqu  xmmword ptr [rbp+57h+Block], xmm0
0x18002506d  mov     [rbp+57h+var_80], r13
0x180025071  mov     rdi, [rbp+57h+var_78+8]
0x180025075  mov     rcx, rdi
0x180025078  mov     rbx, [rbp+57h+var_78]
0x18002507c  sub     rcx, rbx
0x18002507f  mov     rax, 2AAAAAAAAAAAAAABh
0x180025089  imul    rcx
0x18002508c  sar     rdx, 3
0x180025090  mov     rax, rdx
0x180025093  shr     rax, 3Fh
0x180025097  add     rdx, rax
0x18002509a  jz      loc_180025173
0x1800250a0  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800250aa  cmp     rdx, rax
0x1800250ad  ja      loc_180025390
0x1800250b3  lfence
0x1800250b6  lea     r14, ds:0[rdx*8]
0x1800250be  mov     rcx, r14
0x1800250c1  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800250c6  mov     rsi, rax
0x1800250c9  mov     rdi, [rbp+57h+Block+8]
0x1800250cd  mov     rcx, rax
0x1800250d0  mov     rbx, [rbp+57h+Block]
0x1800250d4  cmp     rbx, rdi
0x1800250d7  jz      short loc_1800250FE
0x1800250d9  nop     dword ptr [rax+00000000h]
0x1800250e0  mov     rax, [rbx]
0x1800250e3  mov     [rbx], r13
0x1800250e6  mov     [rcx], rax
0x1800250e9  lea     rcx, [rcx+8]
0x1800250ed  add     rbx, 8
0x1800250f1  cmp     rbx, rdi
0x1800250f4  jnz     short loc_1800250E0
0x1800250f6  mov     rdi, [rbp+57h+Block+8]
0x1800250fa  mov     rbx, [rbp+57h+Block]
0x1800250fe  test    rbx, rbx
0x180025101  jz      short loc_18002515B
0x180025103  cmp     rbx, rdi
0x180025106  jz      short loc_180025123
0x180025108  cmp     qword ptr [rbx], 0
0x18002510c  jz      short loc_180025116
0x18002510e  mov     rcx, rbx
0x180025111  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180025116  add     rbx, 8
0x18002511a  cmp     rbx, rdi
0x18002511d  jnz     short loc_180025108
0x18002511f  mov     rbx, [rbp+57h+Block]
0x180025123  mov     rdx, [rbp+57h+var_80]
0x180025127  sub     rdx, rbx
0x18002512a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002512e  mov     rax, rbx
0x180025131  cmp     rdx, 1000h
0x180025138  jb      short loc_180025153
0x18002513a  add     rdx, 27h ; '''
0x18002513e  mov     rbx, [rbx-8]
0x180025142  sub     rax, rbx
0x180025145  sub     rax, 8
0x180025149  cmp     rax, 1Fh
0x18002514d  ja      loc_180025396
0x180025153  mov     rcx, rbx; Block
0x180025156  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002515b  mov     [rbp+57h+Block], rsi
0x18002515f  mov     [rbp+57h+Block+8], rsi
0x180025163  lea     rax, [r14+rsi]
0x180025167  mov     [rbp+57h+var_80], rax
0x18002516b  mov     rdi, [rbp+57h+var_78+8]
0x18002516f  mov     rbx, [rbp+57h+var_78]
0x180025173  cmp     rbx, rdi
0x180025176  jz      short loc_1800251E5
0x180025178  lea     rsi, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18002517f  lea     r14, aStructWinrtMic_8; "struct winrt::Microsoft::Asg::SemanticI"...
0x180025186  mov     rcx, [r15]
0x180025189  mov     [rbp+57h+var_58], 721h
0x180025190  mov     [rbp+57h+var_54], 14h
0x180025197  mov     [rbp+57h+var_50], rsi
0x18002519b  mov     [rbp+57h+var_48], r14
0x18002519f  mov     [rbp+57h+var_40], rcx
0x1800251a3  mov     [rbp+57h+var_38], rbx
0x1800251a7  lea     rax, [rbp+57h+var_58]
0x1800251ab  mov     [rsp+0C0h+Reserved], rax
0x1800251b0  lea     r8, [rbp+57h+var_40]
0x1800251b4  lea     rdx, [rbp+57h+arg_0]
0x1800251b8  call    ??$InvokeDbMethod@V_lambda_1_@?1??TryGetEmbedding@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUEmbedding@56789winrt@@AEBUItemEmbeddingKey@7asg@@@Z@$$A6AXX_E@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?A_P$$QEAV_lambda_1_@?1??TryGetEmbedding@01234567@AEAA?AUEmbedding@234567@AEBUItemEmbeddingKey@4asg@@@Z@$$Q6AXX_EAEBUsource_location@std@@@Z
0x1800251bd  nop
0x1800251be  lea     rdx, [rbp+57h+arg_0]
0x1800251c2  lea     rcx, [rbp+57h+Block]
0x1800251c6  call    ??$_Emplace_one_at_back@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@AEAAAEAUEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@$$QEAU2345678@@Z; std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>::_Emplace_one_at_back<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding &&)
0x1800251cb  nop
0x1800251cc  cmp     [rbp+57h+arg_0], 0
0x1800251d1  jz      short loc_1800251DC
0x1800251d3  lea     rcx, [rbp+57h+arg_0]
0x1800251d7  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800251dc  add     rbx, 30h ; '0'
0x1800251e0  cmp     rbx, rdi
0x1800251e3  jnz     short loc_180025186
0x1800251e5  mov     ecx, 50h ; 'P'; Size
0x1800251ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800251ef  mov     r9, rax
0x1800251f2  mov     [rbp+57h+arg_0], rax
0x1800251f6  lea     r8, [rax+10h]
0x1800251fa  lea     rax, ??_7?$produce@U?$vector_impl@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@U?$IVector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>>::`vftable'
0x180025201  mov     [r8], rax
0x180025204  lea     rax, ??_7?$produce@U?$vector_impl@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@U?$IVectorView@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>>::`vftable'
0x18002520b  mov     [r8+8], rax
0x18002520f  lea     rax, ??_7?$produce@U?$vector_impl@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@U?$IIterable@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>>::`vftable'
0x180025216  mov     [r8+10h], rax
0x18002521a  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180025221  mov     qword ptr [r9+8], 1
0x180025229  xor     eax, eax
0x18002522b  mov     [r9+28h], eax
0x18002522f  mov     [r9+30h], r13
0x180025233  lea     rax, ??_7?$vector_impl@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@6B@; const winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>::`vftable'
0x18002523a  mov     [r9], rax
0x18002523d  mov     rdx, [rbp+57h+var_80]
0x180025241  mov     [rbp+57h+var_80], r13
0x180025245  mov     rcx, [rbp+57h+Block+8]
0x180025249  mov     [rbp+57h+Block+8], r13
0x18002524d  mov     rax, [rbp+57h+Block]
0x180025251  mov     [rbp+57h+Block], r13
0x180025255  mov     [r9+38h], rax
0x180025259  mov     [r9+40h], rcx
0x18002525d  mov     [r9+48h], rdx
0x180025261  lea     rax, ??_7?$heap_implements@U?$vector_impl@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>>::`vftable'
0x180025268  mov     [r9], rax
0x18002526b  mov     [r12], r8
0x18002526f  mov     rbx, [rbp+57h+Block]
0x180025273  test    rbx, rbx
0x180025276  jz      short loc_1800252E0
0x180025278  mov     rdi, [rbp+57h+Block+8]
0x18002527c  cmp     rbx, rdi
0x18002527f  jz      short loc_18002529C
0x180025281  cmp     qword ptr [rbx], 0
0x180025285  jz      short loc_18002528F
0x180025287  mov     rcx, rbx
0x18002528a  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18002528f  add     rbx, 8
0x180025293  cmp     rbx, rdi
0x180025296  jnz     short loc_180025281
0x180025298  mov     rbx, [rbp+57h+Block]
0x18002529c  mov     rdx, [rbp+57h+var_80]
0x1800252a0  sub     rdx, rbx
0x1800252a3  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800252a7  mov     rax, rbx
0x1800252aa  cmp     rdx, 1000h
0x1800252b1  jb      short loc_1800252CC
0x1800252b3  add     rdx, 27h ; '''
0x1800252b7  mov     rbx, [rbx-8]
0x1800252bb  sub     rax, rbx
0x1800252be  sub     rax, 8
0x1800252c2  cmp     rax, 1Fh
0x1800252c6  ja      loc_1800253AB
0x1800252cc  mov     rcx, rbx; Block
0x1800252cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800252d4  xorps   xmm0, xmm0
0x1800252d7  movdqu  xmmword ptr [rbp+57h+Block], xmm0
0x1800252dc  mov     [rbp+57h+var_80], r13
0x1800252e0  mov     r8, [rbp+57h+var_78]
0x1800252e4  test    r8, r8
0x1800252e7  jz      short loc_180025348
0x1800252e9  mov     rcx, [rbp+57h+var_68]
0x1800252ed  sub     rcx, r8
0x1800252f0  mov     rax, 2AAAAAAAAAAAAAABh
0x1800252fa  imul    rcx
0x1800252fd  sar     rdx, 3
0x180025301  mov     rax, rdx
0x180025304  shr     rax, 3Fh
0x180025308  add     rdx, rax
0x18002530b  lea     rdx, [rdx+rdx*2]
0x18002530f  shl     rdx, 4
0x180025313  mov     rax, r8
0x180025316  cmp     rdx, 1000h
0x18002531d  jb      short loc_180025334
0x18002531f  add     rdx, 27h ; '''
0x180025323  mov     r8, [r8-8]
0x180025327  sub     rax, r8
0x18002532a  sub     rax, 8
0x18002532e  cmp     rax, 1Fh
0x180025332  ja      short loc_18002537B
0x180025334  mov     rcx, r8; Block
0x180025337  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002533c  xorps   xmm0, xmm0
0x18002533f  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x180025344  mov     [rbp+57h+var_68], r13
0x180025348  cmp     [rbp+57h+var_28], 0
0x18002534c  jz      short loc_180025357
0x18002534e  mov     rcx, [rbp+57h+var_30]; _Mtx_t
0x180025352  call    _Mtx_unlock
0x180025357  mov     rax, r12
0x18002535a  lea     r11, [rsp+0C0h+var_20]
0x180025362  mov     rbx, [r11+38h]
0x180025366  mov     rsi, [r11+40h]
0x18002536a  mov     rdi, [r11+48h]
0x18002536e  mov     rsp, r11
0x180025371  pop     r15
0x180025373  pop     r14
0x180025375  pop     r13
0x180025377  pop     r12
0x180025379  pop     rbp
0x18002537a  retn
0x18002537b  mov     [rsp+0C0h+Reserved], r13; Reserved
0x180025380  xor     r9d, r9d; LineNo
0x180025383  xor     r8d, r8d; FileName
0x180025386  xor     edx, edx; FunctionName
0x180025388  xor     ecx, ecx; Expression
0x18002538a  call    _invoke_watson
0x180025390  call    ?_Xlength@?$vector@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@V?$allocator@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@std@@@std@@CAXXZ; std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> *,std::allocator<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> *>>::_Xlength(void)
0x180025396  mov     [rsp+0C0h+Reserved], r13; Reserved
0x18002539b  xor     r9d, r9d; LineNo
0x18002539e  xor     r8d, r8d; FileName
0x1800253a1  xor     edx, edx; FunctionName
0x1800253a3  xor     ecx, ecx; Expression
0x1800253a5  call    _invoke_watson
0x1800253ab  mov     [rsp+0C0h+Reserved], r13; Reserved
0x1800253b0  xor     r9d, r9d; LineNo
0x1800253b3  xor     r8d, r8d; FileName
0x1800253b6  xor     edx, edx; FunctionName
0x1800253b8  xor     ecx, ecx; Expression
0x1800253ba  call    _invoke_watson
```
