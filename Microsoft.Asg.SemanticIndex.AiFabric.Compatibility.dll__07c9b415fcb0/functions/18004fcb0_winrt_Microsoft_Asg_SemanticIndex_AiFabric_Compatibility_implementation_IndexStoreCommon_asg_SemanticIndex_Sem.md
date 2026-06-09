# `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::GetItemEmbeddings(winrt::guid)'::`2'::_lambda_1_::operator()(void)

- ea: `0x18004fcb0`
- end: `0x180050060`
- name: `??R_lambda_1_@?1??GetItemEmbeddings@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AU?$IVector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@9@Uguid@9@@Z@QEBA@XZ`
- size: `944`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180050060`

## callees

- `0x180003bd0`
- `0x180006e30`
- `0x180007ba0`
- `0x18002f8e0`
- `0x180032070`
- `0x18004fcb0`
- `0x1800551d0`
- `0x180196e60`
- `0x1801d2b20`
- `0x1801f7160`
- `0x1801f7190`
- `0x180206ec0`

## string_xrefs

- `0x18004fe18`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18004fe1f`: `struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibilit`

## pseudocode

```c
_QWORD *__fastcall `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::GetItemEmbeddings'::`2'::_lambda_1_::operator()(
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
          "dexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct "
          "winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct "
          "winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft"
          "::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::TryGetEmbedding(const"
          " struct asg::SemanticIndex::ItemEmbeddingKey &)";
    v34[0] = v16;
    v34[1] = v7;
    ___InvokeDbMethod_V_lambda_1___1__TryGetEmbedding___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_AUEmbedding_56789winrt__AEBUItemEmbeddingKey_7asg___Z___A6AXX_E___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_A_P__QEAV_lambda_1___1__TryGetEmbedding_01234567_AEAA_AUEmbedding_234567_AEBUItemEmbeddingKey_4asg___Z___Q6AXX_EAEBUsource_location_std___Z(
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
0x18004fcb0  mov     [rsp-8+arg_8], rbx
0x18004fcb5  mov     [rsp-8+arg_10], rsi
0x18004fcba  mov     [rsp-8+arg_18], rdi
0x18004fcbf  push    rbp
0x18004fcc0  push    r12
0x18004fcc2  push    r13
0x18004fcc4  push    r14
0x18004fcc6  push    r15
0x18004fcc8  lea     rbp, [rsp-37h]
0x18004fccd  sub     rsp, 0A0h
0x18004fcd4  mov     r12, rdx
0x18004fcd7  mov     r15, rcx
0x18004fcda  xor     r13d, r13d
0x18004fcdd  mov     r8b, 1
0x18004fce0  lea     rdx, [rbp+57h+var_30]
0x18004fce4  mov     rcx, [rcx]
0x18004fce7  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18004fcec  nop
0x18004fced  mov     rcx, [r15]
0x18004fcf0  mov     r8, [r15+8]
0x18004fcf4  lea     rdx, [rbp+57h+var_78]
0x18004fcf8  mov     rcx, [rcx+0A8h]
0x18004fcff  call    ?TryGetItemEmbeddingKeys@SemanticIndexStore@SemanticIndex@asg@@QEBA?AV?$vector@UItemEmbeddingKey@SemanticIndex@asg@@V?$allocator@UItemEmbeddingKey@SemanticIndex@asg@@@std@@@std@@AEBUGuid@3@@Z; asg::SemanticIndex::SemanticIndexStore::TryGetItemEmbeddingKeys(asg::Guid const &)
0x18004fd04  nop
0x18004fd05  xorps   xmm0, xmm0
0x18004fd08  movdqu  xmmword ptr [rbp+57h+Block], xmm0
0x18004fd0d  mov     [rbp+57h+var_80], r13
0x18004fd11  mov     rdi, [rbp+57h+var_78+8]
0x18004fd15  mov     rcx, rdi
0x18004fd18  mov     rbx, [rbp+57h+var_78]
0x18004fd1c  sub     rcx, rbx
0x18004fd1f  mov     rax, 2AAAAAAAAAAAAAABh
0x18004fd29  imul    rcx
0x18004fd2c  sar     rdx, 3
0x18004fd30  mov     rax, rdx
0x18004fd33  shr     rax, 3Fh
0x18004fd37  add     rdx, rax
0x18004fd3a  jz      loc_18004FE13
0x18004fd40  mov     rax, 1FFFFFFFFFFFFFFFh
0x18004fd4a  cmp     rdx, rax
0x18004fd4d  ja      loc_180050030
0x18004fd53  lfence
0x18004fd56  lea     r14, ds:0[rdx*8]
0x18004fd5e  mov     rcx, r14
0x18004fd61  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18004fd66  mov     rsi, rax
0x18004fd69  mov     rdi, [rbp+57h+Block+8]
0x18004fd6d  mov     rcx, rax
0x18004fd70  mov     rbx, [rbp+57h+Block]
0x18004fd74  cmp     rbx, rdi
0x18004fd77  jz      short loc_18004FD9E
0x18004fd79  nop     dword ptr [rax+00000000h]
0x18004fd80  mov     rax, [rbx]
0x18004fd83  mov     [rbx], r13
0x18004fd86  mov     [rcx], rax
0x18004fd89  lea     rcx, [rcx+8]
0x18004fd8d  add     rbx, 8
0x18004fd91  cmp     rbx, rdi
0x18004fd94  jnz     short loc_18004FD80
0x18004fd96  mov     rdi, [rbp+57h+Block+8]
0x18004fd9a  mov     rbx, [rbp+57h+Block]
0x18004fd9e  test    rbx, rbx
0x18004fda1  jz      short loc_18004FDFB
0x18004fda3  cmp     rbx, rdi
0x18004fda6  jz      short loc_18004FDC3
0x18004fda8  cmp     qword ptr [rbx], 0
0x18004fdac  jz      short loc_18004FDB6
0x18004fdae  mov     rcx, rbx
0x18004fdb1  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18004fdb6  add     rbx, 8
0x18004fdba  cmp     rbx, rdi
0x18004fdbd  jnz     short loc_18004FDA8
0x18004fdbf  mov     rbx, [rbp+57h+Block]
0x18004fdc3  mov     rdx, [rbp+57h+var_80]
0x18004fdc7  sub     rdx, rbx
0x18004fdca  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18004fdce  mov     rax, rbx
0x18004fdd1  cmp     rdx, 1000h
0x18004fdd8  jb      short loc_18004FDF3
0x18004fdda  add     rdx, 27h ; '''
0x18004fdde  mov     rbx, [rbx-8]
0x18004fde2  sub     rax, rbx
0x18004fde5  sub     rax, 8
0x18004fde9  cmp     rax, 1Fh
0x18004fded  ja      loc_180050036
0x18004fdf3  mov     rcx, rbx; Block
0x18004fdf6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004fdfb  mov     [rbp+57h+Block], rsi
0x18004fdff  mov     [rbp+57h+Block+8], rsi
0x18004fe03  lea     rax, [r14+rsi]
0x18004fe07  mov     [rbp+57h+var_80], rax
0x18004fe0b  mov     rdi, [rbp+57h+var_78+8]
0x18004fe0f  mov     rbx, [rbp+57h+var_78]
0x18004fe13  cmp     rbx, rdi
0x18004fe16  jz      short loc_18004FE85
0x18004fe18  lea     rsi, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18004fe1f  lea     r14, aStructWinrtMic_28; "struct winrt::Microsoft::Asg::SemanticI"...
0x18004fe26  mov     rcx, [r15]
0x18004fe29  mov     [rbp+57h+var_58], 721h
0x18004fe30  mov     [rbp+57h+var_54], 14h
0x18004fe37  mov     [rbp+57h+var_50], rsi
0x18004fe3b  mov     [rbp+57h+var_48], r14
0x18004fe3f  mov     [rbp+57h+var_40], rcx
0x18004fe43  mov     [rbp+57h+var_38], rbx
0x18004fe47  lea     rax, [rbp+57h+var_58]
0x18004fe4b  mov     [rsp+0C0h+Reserved], rax
0x18004fe50  lea     r8, [rbp+57h+var_40]
0x18004fe54  lea     rdx, [rbp+57h+arg_0]
0x18004fe58  call    ??$InvokeDbMethod@V_lambda_1_@?1??TryGetEmbedding@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AUEmbedding@56789winrt@@AEBUItemEmbeddingKey@7asg@@@Z@$$A6AXX_E@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?A_P$$QEAV_lambda_1_@?1??TryGetEmbedding@01234567@AEAA?AUEmbedding@234567@AEBUItemEmbeddingKey@4asg@@@Z@$$Q6AXX_EAEBUsource_location@std@@@Z
0x18004fe5d  nop
0x18004fe5e  lea     rdx, [rbp+57h+arg_0]
0x18004fe62  lea     rcx, [rbp+57h+Block]
0x18004fe66  call    ??$_Emplace_one_at_back@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@AEAAAEAUEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@$$QEAU2345678@@Z; std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>::_Emplace_one_at_back<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding &&)
0x18004fe6b  nop
0x18004fe6c  cmp     [rbp+57h+arg_0], 0
0x18004fe71  jz      short loc_18004FE7C
0x18004fe73  lea     rcx, [rbp+57h+arg_0]
0x18004fe77  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18004fe7c  add     rbx, 30h ; '0'
0x18004fe80  cmp     rbx, rdi
0x18004fe83  jnz     short loc_18004FE26
0x18004fe85  mov     ecx, 50h ; 'P'; Size
0x18004fe8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004fe8f  mov     r9, rax
0x18004fe92  mov     [rbp+57h+arg_0], rax
0x18004fe96  lea     r8, [rax+10h]
0x18004fe9a  lea     rax, ??_7?$produce@U?$vector_impl@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@U?$IVector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>>::`vftable'
0x18004fea1  mov     [r8], rax
0x18004fea4  lea     rax, ??_7?$produce@U?$vector_impl@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@U?$IVectorView@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>>::`vftable'
0x18004feab  mov     [r8+8], rax
0x18004feaf  lea     rax, ??_7?$produce@U?$vector_impl@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@U?$IIterable@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>>::`vftable'
0x18004feb6  mov     [r8+10h], rax
0x18004feba  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004fec1  mov     qword ptr [r9+8], 1
0x18004fec9  xor     eax, eax
0x18004fecb  mov     [r9+28h], eax
0x18004fecf  mov     [r9+30h], r13
0x18004fed3  lea     rax, ??_7?$vector_impl@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@6B@; const winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>::`vftable'
0x18004feda  mov     [r9], rax
0x18004fedd  mov     rdx, [rbp+57h+var_80]
0x18004fee1  mov     [rbp+57h+var_80], r13
0x18004fee5  mov     rcx, [rbp+57h+Block+8]
0x18004fee9  mov     [rbp+57h+Block+8], r13
0x18004feed  mov     rax, [rbp+57h+Block]
0x18004fef1  mov     [rbp+57h+Block], r13
0x18004fef5  mov     [r9+38h], rax
0x18004fef9  mov     [r9+40h], rcx
0x18004fefd  mov     [r9+48h], rdx
0x18004ff01  lea     rax, ??_7?$heap_implements@U?$vector_impl@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>,winrt::impl::multi_threaded_collection_base>>::`vftable'
0x18004ff08  mov     [r9], rax
0x18004ff0b  mov     [r12], r8
0x18004ff0f  mov     rbx, [rbp+57h+Block]
0x18004ff13  test    rbx, rbx
0x18004ff16  jz      short loc_18004FF80
0x18004ff18  mov     rdi, [rbp+57h+Block+8]
0x18004ff1c  cmp     rbx, rdi
0x18004ff1f  jz      short loc_18004FF3C
0x18004ff21  cmp     qword ptr [rbx], 0
0x18004ff25  jz      short loc_18004FF2F
0x18004ff27  mov     rcx, rbx
0x18004ff2a  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18004ff2f  add     rbx, 8
0x18004ff33  cmp     rbx, rdi
0x18004ff36  jnz     short loc_18004FF21
0x18004ff38  mov     rbx, [rbp+57h+Block]
0x18004ff3c  mov     rdx, [rbp+57h+var_80]
0x18004ff40  sub     rdx, rbx
0x18004ff43  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18004ff47  mov     rax, rbx
0x18004ff4a  cmp     rdx, 1000h
0x18004ff51  jb      short loc_18004FF6C
0x18004ff53  add     rdx, 27h ; '''
0x18004ff57  mov     rbx, [rbx-8]
0x18004ff5b  sub     rax, rbx
0x18004ff5e  sub     rax, 8
0x18004ff62  cmp     rax, 1Fh
0x18004ff66  ja      loc_18005004B
0x18004ff6c  mov     rcx, rbx; Block
0x18004ff6f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004ff74  xorps   xmm0, xmm0
0x18004ff77  movdqu  xmmword ptr [rbp+57h+Block], xmm0
0x18004ff7c  mov     [rbp+57h+var_80], r13
0x18004ff80  mov     r8, [rbp+57h+var_78]
0x18004ff84  test    r8, r8
0x18004ff87  jz      short loc_18004FFE8
0x18004ff89  mov     rcx, [rbp+57h+var_68]
0x18004ff8d  sub     rcx, r8
0x18004ff90  mov     rax, 2AAAAAAAAAAAAAABh
0x18004ff9a  imul    rcx
0x18004ff9d  sar     rdx, 3
0x18004ffa1  mov     rax, rdx
0x18004ffa4  shr     rax, 3Fh
0x18004ffa8  add     rdx, rax
0x18004ffab  lea     rdx, [rdx+rdx*2]
0x18004ffaf  shl     rdx, 4
0x18004ffb3  mov     rax, r8
0x18004ffb6  cmp     rdx, 1000h
0x18004ffbd  jb      short loc_18004FFD4
0x18004ffbf  add     rdx, 27h ; '''
0x18004ffc3  mov     r8, [r8-8]
0x18004ffc7  sub     rax, r8
0x18004ffca  sub     rax, 8
0x18004ffce  cmp     rax, 1Fh
0x18004ffd2  ja      short loc_18005001B
0x18004ffd4  mov     rcx, r8; Block
0x18004ffd7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004ffdc  xorps   xmm0, xmm0
0x18004ffdf  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x18004ffe4  mov     [rbp+57h+var_68], r13
0x18004ffe8  cmp     [rbp+57h+var_28], 0
0x18004ffec  jz      short loc_18004FFF7
0x18004ffee  mov     rcx, [rbp+57h+var_30]; _Mtx_t
0x18004fff2  call    _Mtx_unlock
0x18004fff7  mov     rax, r12
0x18004fffa  lea     r11, [rsp+0C0h+var_20]
0x180050002  mov     rbx, [r11+38h]
0x180050006  mov     rsi, [r11+40h]
0x18005000a  mov     rdi, [r11+48h]
0x18005000e  mov     rsp, r11
0x180050011  pop     r15
0x180050013  pop     r14
0x180050015  pop     r13
0x180050017  pop     r12
0x180050019  pop     rbp
0x18005001a  retn
0x18005001b  mov     [rsp+0C0h+Reserved], r13; Reserved
0x180050020  xor     r9d, r9d; LineNo
0x180050023  xor     r8d, r8d; FileName
0x180050026  xor     edx, edx; FunctionName
0x180050028  xor     ecx, ecx; Expression
0x18005002a  call    _invoke_watson
0x180050030  call    ?_Xlength@?$vector@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@V?$allocator@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_2@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@json_abi_v3_11_2@nlohmann@@@std@@@std@@CAXXZ; std::vector<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> *,std::allocator<nlohmann::json_abi_v3_11_2::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::json_abi_v3_11_2::adl_serializer,std::vector<uchar>> *>>::_Xlength(void)
0x180050036  mov     [rsp+0C0h+Reserved], r13; Reserved
0x18005003b  xor     r9d, r9d; LineNo
0x18005003e  xor     r8d, r8d; FileName
0x180050041  xor     edx, edx; FunctionName
0x180050043  xor     ecx, ecx; Expression
0x180050045  call    _invoke_watson
0x18005004b  mov     [rsp+0C0h+Reserved], r13; Reserved
0x180050050  xor     r9d, r9d; LineNo
0x180050053  xor     r8d, r8d; FileName
0x180050056  xor     edx, edx; FunctionName
0x180050058  xor     ecx, ecx; Expression
0x18005005a  call    _invoke_watson
```
