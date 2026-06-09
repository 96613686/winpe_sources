# `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::GetIndexingStateMany2(winrt::array_view<winrt::guid const>)'::`2'::_lambda_2_::operator()(void)

- ea: `0x18004f410`
- end: `0x18004f7a7`
- name: `??R_lambda_2_@?1??GetIndexingStateMany2@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AU?$IVector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@9@U?$array_view@$$CBUguid@winrt@@@9@@Z@QEBA@XZ`
- size: `919`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004f7b0`

## callees

- `0x180003df0`
- `0x180006220`
- `0x18000d230`
- `0x18002b150`
- `0x18002f8e0`
- `0x18002fb90`
- `0x180039160`
- `0x18004f410`
- `0x1800546c0`
- `0x180078ed0`
- `0x1801939e0`
- `0x1801d2b20`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206ec0`

## string_xrefs

- `0x18004f4d9`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18004f4e0`: `struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2 __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Com`

## pseudocode

```c
_QWORD *__fastcall `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::GetIndexingStateMany2'::`2'::_lambda_2_::operator()(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  asg::SemanticIndex::SemanticIndexStore *v5; // rdi
  __int128 v6; // xmm7
  __int128 v7; // xmm6
  char v8; // si
  _QWORD *v9; // rdi
  _QWORD *v10; // rbx
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  __int64 v15; // xmm1_8
  __int64 v16; // rdx
  void *v17; // rcx
  void *v18; // rax
  void *v19; // r8
  void *Block_8[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-C0h]
  _BYTE v23[24]; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v24; // [rsp+78h] [rbp-90h] BYREF
  const char *v25; // [rsp+88h] [rbp-80h]
  __int128 pExceptionObject; // [rsp+98h] [rbp-70h] BYREF
  const char *v27; // [rsp+A8h] [rbp-60h]
  _Mtx_t v28[2]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v29[8]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD *v30; // [rsp+E0h] [rbp-28h] BYREF
  _BYTE v31[72]; // [rsp+F0h] [rbp-18h] BYREF
  _QWORD *v32; // [rsp+168h] [rbp+60h]

  LOBYTE(a3) = 1;
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
    *a1,
    v28,
    a3);
  ___GetIndexingState_V__transform_view_V__ref_view_U__array_view___CBUguid_winrt___winrt___ranges_std__V_lambda_1___1__GetIndexingStateMany2___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAA_AU__IVector_UItemIndexingState2_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___Collections_Foundation_Windows_winrt__U__array_view___CBUguid_winrt___winrt___Z__ranges_std___SemanticIndexStore_SemanticIndex_asg__QEBA_AV__unordered_map_UGuid_asg__W4ItemIndexingStatus_SemanticIndex_2_U__hash_UGuid_asg___std__U__equal_to_UGuid_asg___6_V__allocator_U__pair___CBUGuid_asg__W4ItemIndexingStatus_SemanticIndex_2__std___6__std__AEBV__transform_view_V__ref_view_U__array_view___CBUguid_winrt___winrt___ranges_std__V_lambda_1___1__GetIndexingStateMany2___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAA_AU__IVector_UItemIndexingState2_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___Collections_Foundation_Windows_winrt__U__array_view___CBUguid_winrt___winrt___Z__ranges_4__Z(
    *(_QWORD *)(*a1 + 168LL),
    (__int64)v29,
    (__int64 **)a1[1]);
  v5 = *(asg::SemanticIndex::SemanticIndexStore **)(*a1 + 168LL);
  v6 = *(_OWORD *)(*((_QWORD *)v5 + 22) + 200LL);
  if ( asg::SemanticIndex::SemanticIndexStore::IsPreviousGraphEmpty(v5) )
  {
    v7 = *(_OWORD *)v28;
    v8 = 0;
  }
  else
  {
    v7 = *(_OWORD *)(*((_QWORD *)v5 + 24) + 200LL);
    v8 = 1;
  }
  *(_OWORD *)Block_8 = 0;
  v22 = 0;
  std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>::reserve(
    Block_8,
    *(unsigned int *)(a1[2] + 8LL));
  v9 = v30;
  v10 = (_QWORD *)*v30;
  if ( (_QWORD *)*v30 != v30 )
  {
    v11 = (__int64)Block_8[1];
    while ( 1 )
    {
      v12 = *((_DWORD *)v10 + 8);
      if ( !v12 )
        break;
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( !v14 )
        {
          *(_QWORD *)&v24 = 0x1600000711LL;
          *((_QWORD *)&v24 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
          v25 = "struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2 __cdecl winrt::"
                "Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::Sema"
                "nticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Text"
                "EmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation"
                "::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbe"
                "ddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::Te"
                "xtEmbeddingsGenerator>::MakeIndexingState(enum asg::SemanticIndex::ItemIndexingStatus,const struct asg::"
                "Guid &,const class std::optional<struct asg::Guid> &)";
          if ( !v8 )
          {
            pExceptionObject = v24;
            v27 = v25;
            asg::details::AsgAssertFail(&pExceptionObject);
          }
          *(_DWORD *)v23 = 4;
          *(_OWORD *)&v23[4] = v7;
          v23[20] = 1;
          goto LABEL_16;
        }
        if ( v14 != 1 )
        {
          LODWORD(v24) = 1818;
          *((_QWORD *)&v24 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
          v25 = 0;
          winrt::param::hstring::hstring((winrt::param::hstring *)v23, L"Invalid indexing state");
          winrt::hresult_invalid_argument::hresult_invalid_argument(
            (winrt::hresult_invalid_argument *)&pExceptionObject,
            (const struct winrt::param::hstring *)v23,
            (const struct winrt::impl::slim_source_location *)&v24);
          throw (winrt::hresult_invalid_argument *)&pExceptionObject;
        }
        *(_DWORD *)v23 = 4;
        v23[20] = 1;
        goto LABEL_15;
      }
      *(_DWORD *)v23 = 2;
      *(_OWORD *)&v23[4] = v6;
      v23[20] = 0;
LABEL_16:
      *(_WORD *)&v23[21] = *(_WORD *)((char *)&v22 + 5);
      v23[23] = HIBYTE(v22);
      pExceptionObject = *(_OWORD *)v23;
      v15 = *(_QWORD *)&v23[16];
      v27 = *(const char **)&v23[16];
      if ( v11 == v22 )
      {
        std::vector<asg::SemanticRegistry::TokenText>::_Emplace_reallocate<asg::SemanticRegistry::TokenText>(
          (const void **)Block_8,
          (_BYTE *)v11,
          (__int64)&pExceptionObject);
        v11 = (__int64)Block_8[1];
      }
      else
      {
        *(_OWORD *)v11 = *(_OWORD *)v23;
        *(_QWORD *)(v11 + 16) = v15;
        v11 = (__int64)Block_8[1] + 24;
        Block_8[1] = (char *)Block_8[1] + 24;
      }
      v10 = (_QWORD *)*v10;
      if ( v10 == v9 )
        goto LABEL_20;
    }
    *(_DWORD *)v23 = 0;
    v23[20] = 0;
LABEL_15:
    *(_OWORD *)&v23[4] = `asg::EmptyGuid'::`2'::empty;
    goto LABEL_16;
  }
LABEL_20:
  v32 = operator new(0x50u);
  v32[2] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>>::`vftable';
  v32[3] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>>::`vftable';
  v32[4] = &winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v32[1] = 1;
  *((_DWORD *)v32 + 10) = 0;
  v32[6] = 0;
  *v32 = &winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>::`vftable';
  v16 = v22;
  v22 = 0;
  v17 = Block_8[1];
  v18 = Block_8[0];
  *(_OWORD *)Block_8 = 0u;
  v32[7] = v18;
  v32[8] = v17;
  v32[9] = v16;
  *v32 = &winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>>::`vftable';
  *a2 = v32 + 2;
  v19 = Block_8[0];
  if ( Block_8[0] )
  {
    if ( (unsigned __int64)(24 * ((signed __int64)(v22 - (unsigned __int64)Block_8[0]) / 24)) >= 0x1000 )
    {
      v19 = (void *)*((_QWORD *)Block_8[0] - 1);
      if ( (unsigned __int64)((char *)Block_8[0] - (char *)v19 - 8) > 0x1F )
        invoke_watson(0, 0, 0, 0, 0);
    }
    operator delete(v19);
    *(_OWORD *)Block_8 = 0;
    v22 = 0;
  }
  std::vector<std::pair<unsigned int,unsigned int>>::_Tidy(v31);
  std::list<std::pair<asg::Guid const,float>>::~list<std::pair<asg::Guid const,float>>(&v30);
  if ( LOBYTE(v28[1]) )
    Mtx_unlock(v28[0]);
  return a2;
}

```

## disassembly

```asm
0x18004f410  mov     rax, rsp
0x18004f413  mov     [rax+10h], rbx
0x18004f417  mov     [rax+18h], rsi
0x18004f41b  mov     [rax+20h], rdi
0x18004f41f  push    rbp
0x18004f420  push    r12
0x18004f422  push    r13
0x18004f424  push    r14
0x18004f426  push    r15
0x18004f428  lea     rbp, [rax-58h]
0x18004f42c  sub     rsp, 130h
0x18004f433  movaps  xmmword ptr [rax-38h], xmm6
0x18004f437  movaps  xmmword ptr [rax-48h], xmm7
0x18004f43b  mov     r14, rdx
0x18004f43e  mov     rbx, rcx
0x18004f441  xor     r15d, r15d
0x18004f444  mov     r8b, 1
0x18004f447  lea     rdx, [rbp+50h+var_98]
0x18004f44b  mov     rcx, [rcx]
0x18004f44e  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18004f453  nop
0x18004f454  mov     rcx, [rbx]
0x18004f457  mov     r8, [rbx+8]
0x18004f45b  lea     rdx, [rbp+50h+var_80]
0x18004f45f  mov     rcx, [rcx+0A8h]
0x18004f466  call    ??$GetIndexingState@V?$transform_view@V?$ref_view@U?$array_view@$$CBUguid@winrt@@@winrt@@@ranges@std@@V_lambda_1_@?1??GetIndexingStateMany2@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AU?$IVector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@winrt@@U?$array_view@$$CBUguid@winrt@@@winrt@@@Z@@ranges@std@@@SemanticIndexStore@SemanticIndex@asg@@QEBA?AV?$unordered_map@UGuid@asg@@W4ItemIndexingStatus@SemanticIndex@2@U?$hash@UGuid@asg@@@std@@U?$equal_to@UGuid@asg@@@6@V?$allocator@U?$pair@$$CBUGuid@asg@@W4ItemIndexingStatus@SemanticIndex@2@@std@@@6@@std@@AEBV?$transform_view@V?$ref_view@U?$array_view@$$CBUguid@winrt@@@winrt@@@ranges@std@@V_lambda_1_@?1??GetIndexingStateMany2@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AU?$IVector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@winrt@@U?$array_view@$$CBUguid@winrt@@@winrt@@@Z@@ranges@4@@Z; asg::SemanticIndex::SemanticIndexStore::GetIndexingState<std::ranges::transform_view<std::ranges::ref_view<winrt::array_view<winrt::guid const>>,`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::GetIndexingStateMany2(winrt::array_view<winrt::guid const>)'::`2'::_lambda_1_>>(std::ranges::transform_view<std::ranges::ref_view<winrt::array_view<winrt::guid const>>,`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::GetIndexingStateMany2(winrt::array_view<winrt::guid const>)'::`2'::_lambda_1_> const &)
0x18004f46b  nop
0x18004f46c  mov     rax, [rbx]
0x18004f46f  mov     rdi, [rax+0A8h]
0x18004f476  mov     rax, [rdi+0B0h]
0x18004f47d  movups  xmm7, xmmword ptr [rax+0C8h]
0x18004f484  mov     rcx, rdi; this
0x18004f487  call    ?IsPreviousGraphEmpty@SemanticIndexStore@SemanticIndex@asg@@QEBA_NXZ; asg::SemanticIndex::SemanticIndexStore::IsPreviousGraphEmpty(void)
0x18004f48c  test    al, al
0x18004f48e  jz      short loc_18004F499
0x18004f490  movups  xmm6, xmmword ptr [rbp+50h+var_98]
0x18004f494  xor     sil, sil
0x18004f497  jmp     short loc_18004F4AA
0x18004f499  mov     rax, [rdi+0C0h]
0x18004f4a0  movups  xmm6, xmmword ptr [rax+0C8h]
0x18004f4a7  mov     sil, 1
0x18004f4aa  xorps   xmm0, xmm0
0x18004f4ad  movdqu  xmmword ptr [rsp+150h+Block+8], xmm0
0x18004f4b3  mov     qword ptr [rsp+150h+var_110], r15
0x18004f4b8  mov     rax, [rbx+10h]
0x18004f4bc  mov     edx, [rax+8]
0x18004f4bf  lea     rcx, [rsp+150h+Block+8]
0x18004f4c4  call    ?reserve@?$vector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@QEAAX_K@Z; std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>::reserve(unsigned __int64)
0x18004f4c9  mov     rdi, [rbp+50h+var_78]
0x18004f4cd  mov     rbx, [rdi]
0x18004f4d0  cmp     rbx, rdi
0x18004f4d3  jz      loc_18004F5DD
0x18004f4d9  lea     r13, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18004f4e0  lea     r12, aStructWinrtMic_16; "struct winrt::Microsoft::Asg::SemanticI"...
0x18004f4e7  mov     rdx, [rsp+150h+var_118]
0x18004f4ec  nop     dword ptr [rax+00h]
0x18004f4f0  mov     ecx, [rbx+20h]
0x18004f4f3  test    ecx, ecx
0x18004f4f5  jz      short loc_18004F562
0x18004f4f7  sub     ecx, 1
0x18004f4fa  jz      short loc_18004F54E
0x18004f4fc  sub     ecx, 1
0x18004f4ff  jz      short loc_18004F518
0x18004f501  cmp     ecx, 1
0x18004f504  jnz     loc_18004F761
0x18004f50a  mov     dword ptr [rsp+150h+var_110+8], 4
0x18004f512  mov     byte ptr [rsp+150h+var_F8+4], cl
0x18004f516  jmp     short loc_18004F56C
0x18004f518  mov     dword ptr [rsp+150h+var_E8+8], 711h
0x18004f520  mov     dword ptr [rsp+150h+var_E8+0Ch], 16h
0x18004f528  mov     [rsp+150h+var_D8], r13
0x18004f52d  mov     [rbp+50h+var_D0], r12
0x18004f531  test    sil, sil
0x18004f534  jz      loc_18004F72C
0x18004f53a  mov     dword ptr [rsp+150h+var_110+8], 4
0x18004f542  movups  [rsp+150h+var_110+0Ch], xmm6
0x18004f547  mov     byte ptr [rsp+150h+var_F8+4], 1
0x18004f54c  jmp     short loc_18004F578
0x18004f54e  mov     dword ptr [rsp+150h+var_110+8], 2
0x18004f556  movups  [rsp+150h+var_110+0Ch], xmm7
0x18004f55b  mov     byte ptr [rsp+150h+var_F8+4], 0
0x18004f560  jmp     short loc_18004F578
0x18004f562  mov     dword ptr [rsp+150h+var_110+8], r15d
0x18004f567  mov     byte ptr [rsp+150h+var_F8+4], 0
0x18004f56c  movups  xmm0, cs:?empty@?1??EmptyGuid@asg@@YA?AUGuid@2@XZ@4U32@B; asg::Guid const `asg::EmptyGuid(void)'::`2'::empty
0x18004f573  movups  [rsp+150h+var_110+0Ch], xmm0
0x18004f578  movzx   eax, word ptr [rsp+150h+var_110+5]
0x18004f57d  mov     word ptr [rsp+150h+var_F8+5], ax
0x18004f582  movzx   eax, byte ptr [rsp+150h+var_110+7]
0x18004f587  mov     byte ptr [rsp+150h+var_F8+7], al
0x18004f58b  movups  xmm0, [rsp+150h+var_110+8]
0x18004f590  movups  [rbp+50h+pExceptionObject], xmm0
0x18004f594  movsd   xmm1, [rsp+150h+var_F8]
0x18004f59a  movsd   [rbp+50h+var_B0], xmm1
0x18004f59f  cmp     rdx, qword ptr [rsp+150h+var_110]
0x18004f5a4  jz      short loc_18004F5BE
0x18004f5a6  movups  xmmword ptr [rdx], xmm0
0x18004f5a9  movsd   qword ptr [rdx+10h], xmm1
0x18004f5ae  mov     rdx, [rsp+150h+var_118]
0x18004f5b3  add     rdx, 18h
0x18004f5b7  mov     [rsp+150h+var_118], rdx
0x18004f5bc  jmp     short loc_18004F5D1
0x18004f5be  lea     r8, [rbp+50h+pExceptionObject]
0x18004f5c2  lea     rcx, [rsp+150h+Block+8]
0x18004f5c7  call    ??$_Emplace_reallocate@UTokenText@SemanticRegistry@asg@@@?$vector@UTokenText@SemanticRegistry@asg@@V?$allocator@UTokenText@SemanticRegistry@asg@@@std@@@std@@AEAAPEAUTokenText@SemanticRegistry@asg@@QEAU234@$$QEAU234@@Z; std::vector<asg::SemanticRegistry::TokenText>::_Emplace_reallocate<asg::SemanticRegistry::TokenText>(asg::SemanticRegistry::TokenText * const,asg::SemanticRegistry::TokenText &&)
0x18004f5cc  mov     rdx, [rsp+150h+var_118]
0x18004f5d1  mov     rbx, [rbx]
0x18004f5d4  cmp     rbx, rdi
0x18004f5d7  jnz     loc_18004F4F0
0x18004f5dd  mov     ecx, 50h ; 'P'; Size
0x18004f5e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f5e7  mov     r9, rax
0x18004f5ea  mov     [rbp+50h+arg_0], rax
0x18004f5ee  lea     r8, [rax+10h]
0x18004f5f2  lea     rax, ??_7?$produce@U?$vector_impl@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@U?$IVector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>>::`vftable'
0x18004f5f9  mov     [r8], rax
0x18004f5fc  lea     rax, ??_7?$produce@U?$vector_impl@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@U?$IVectorView@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>>::`vftable'
0x18004f603  mov     [r8+8], rax
0x18004f607  lea     rax, ??_7?$produce@U?$vector_impl@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@U?$IIterable@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>>::`vftable'
0x18004f60e  mov     [r8+10h], rax
0x18004f612  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004f619  mov     qword ptr [r9+8], 1
0x18004f621  xor     eax, eax
0x18004f623  mov     [r9+28h], eax
0x18004f627  mov     [r9+30h], r15
0x18004f62b  lea     rax, ??_7?$vector_impl@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@6B@; const winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>::`vftable'
0x18004f632  mov     [r9], rax
0x18004f635  mov     rdx, qword ptr [rsp+150h+var_110]
0x18004f63a  mov     qword ptr [rsp+150h+var_110], r15
0x18004f63f  mov     rcx, [rsp+150h+var_118]
0x18004f644  mov     [rsp+150h+var_118], r15
0x18004f649  mov     rax, [rsp+150h+Block+8]
0x18004f64e  mov     [rsp+150h+Block+8], r15
0x18004f653  mov     [r9+38h], rax
0x18004f657  mov     [r9+40h], rcx
0x18004f65b  mov     [r9+48h], rdx
0x18004f65f  lea     rax, ??_7?$heap_implements@U?$vector_impl@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>>::`vftable'
0x18004f666  mov     [r9], rax
0x18004f669  mov     [r14], r8
0x18004f66c  mov     r8, [rsp+150h+Block+8]
0x18004f671  test    r8, r8
0x18004f674  jz      short loc_18004F6DC
0x18004f676  mov     rcx, qword ptr [rsp+150h+var_110]
0x18004f67b  sub     rcx, r8
0x18004f67e  mov     rax, 2AAAAAAAAAAAAAABh
0x18004f688  imul    rcx
0x18004f68b  sar     rdx, 2
0x18004f68f  mov     rax, rdx
0x18004f692  shr     rax, 3Fh
0x18004f696  add     rdx, rax
0x18004f699  lea     rdx, [rdx+rdx*2]
0x18004f69d  shl     rdx, 3
0x18004f6a1  mov     rax, r8
0x18004f6a4  cmp     rdx, 1000h
0x18004f6ab  jb      short loc_18004F6C6
0x18004f6ad  add     rdx, 27h ; '''
0x18004f6b1  mov     r8, [r8-8]
0x18004f6b5  sub     rax, r8
0x18004f6b8  sub     rax, 8
0x18004f6bc  cmp     rax, 1Fh
0x18004f6c0  ja      loc_18004F74C
0x18004f6c6  mov     rcx, r8; Block
0x18004f6c9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004f6ce  xorps   xmm0, xmm0
0x18004f6d1  movdqu  xmmword ptr [rsp+150h+Block+8], xmm0
0x18004f6d7  mov     qword ptr [rsp+150h+var_110], r15
0x18004f6dc  lea     rcx, [rbp+50h+var_68]
0x18004f6e0  call    ?_Tidy@?$vector@U?$pair@II@std@@V?$allocator@U?$pair@II@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<uint,uint>>::_Tidy(void)
0x18004f6e5  lea     rcx, [rbp+50h+var_78]
0x18004f6e9  call    ??1?$list@U?$pair@$$CBUGuid@asg@@M@std@@V?$allocator@U?$pair@$$CBUGuid@asg@@M@std@@@2@@std@@QEAA@XZ; std::list<std::pair<asg::Guid const,float>>::~list<std::pair<asg::Guid const,float>>(void)
0x18004f6ee  nop
0x18004f6ef  cmp     byte ptr [rbp+50h+var_98+8], 0
0x18004f6f3  jz      short loc_18004F6FE
0x18004f6f5  mov     rcx, [rbp+50h+var_98]; _Mtx_t
0x18004f6f9  call    _Mtx_unlock
0x18004f6fe  mov     rax, r14
0x18004f701  lea     r11, [rsp+150h+var_20]
0x18004f709  mov     rbx, [r11+38h]
0x18004f70d  mov     rsi, [r11+40h]
0x18004f711  mov     rdi, [r11+48h]
0x18004f715  movaps  xmm6, xmmword ptr [r11-10h]
0x18004f71a  movaps  xmm7, xmmword ptr [r11-20h]
0x18004f71f  mov     rsp, r11
0x18004f722  pop     r15
0x18004f724  pop     r14
0x18004f726  pop     r13
0x18004f728  pop     r12
0x18004f72a  pop     rbp
0x18004f72b  retn
0x18004f72c  movaps  xmm0, [rsp+150h+var_E8+8]
0x18004f731  movaps  [rbp+50h+pExceptionObject], xmm0
0x18004f735  movsd   xmm1, [rbp+50h+var_D0]
0x18004f73a  movsd   [rbp+50h+var_B0], xmm1
0x18004f73f  mov     rdx, r12
0x18004f742  lea     rcx, [rbp+50h+pExceptionObject]
0x18004f746  call    ?AsgAssertFail@details@asg@@YAXUsource_location@std@@PEBD@Z; asg::details::AsgAssertFail(std::source_location,char const *)
0x18004f74c  mov     [rsp+150h+Reserved], r15; Reserved
0x18004f751  xor     r9d, r9d; LineNo
0x18004f754  xor     r8d, r8d; FileName
0x18004f757  xor     edx, edx; FunctionName
0x18004f759  xor     ecx, ecx; Expression
0x18004f75b  call    _invoke_watson
0x18004f761  mov     dword ptr [rsp+150h+var_E8+8], 71Ah
0x18004f769  mov     [rsp+150h+var_D8], r13
0x18004f76e  mov     [rbp+50h+var_D0], r15
0x18004f772  lea     rdx, aInvalidIndexin; "Invalid indexing state"
0x18004f779  lea     rcx, [rsp+150h+var_110+8]; this
0x18004f77e  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18004f783  lea     r8, [rsp+150h+var_E8+8]; struct winrt::impl::slim_source_location *
0x18004f788  lea     rdx, [rsp+150h+var_110+8]; struct winrt::param::hstring *
0x18004f78d  lea     rcx, [rbp+50h+pExceptionObject]; this
0x18004f791  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18004f796  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18004f79d  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x18004f7a1  call    _CxxThrowException
```
