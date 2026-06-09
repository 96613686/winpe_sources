# `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::GetIndexingStateMany2(winrt::array_view<winrt::guid const>)'::`2'::_lambda_2_::operator()(void)

- ea: `0x180024770`
- end: `0x180024b07`
- name: `??R_lambda_2_@?1??GetIndexingStateMany2@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AU?$IVector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@9@U?$array_view@$$CBUguid@winrt@@@9@@Z@QEBA@XZ`
- size: `919`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180024b10`

## callees

- `0x180003df0`
- `0x180006220`
- `0x18000d230`
- `0x180024770`
- `0x18002b150`
- `0x18002d150`
- `0x18002f8e0`
- `0x18002fb90`
- `0x180039160`
- `0x180078ed0`
- `0x1801939e0`
- `0x1801d2b20`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206ec0`

## string_xrefs

- `0x180024839`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180024840`: `struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2 __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::C`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::GetIndexingStateMany2'::`2'::_lambda_2_::operator()(
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
  ___GetIndexingState_V__transform_view_V__ref_view_U__array_view___CBUguid_winrt___winrt___ranges_std__V_lambda_1___1__GetIndexingStateMany2___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAA_AU__IVector_UItemIndexingState2_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___Collections_Foundation_Windows_winrt__U__array_view___CBUguid_winrt___winrt___Z__ranges_std___SemanticIndexStore_SemanticIndex_asg__QEBA_AV__unordered_map_UGuid_asg__W4ItemIndexingStatus_SemanticIndex_2_U__hash_UGuid_asg___std__U__equal_to_UGuid_asg___6_V__allocator_U__pair___CBUGuid_asg__W4ItemIndexingStatus_SemanticIndex_2__std___6__std__AEBV__transform_view_V__ref_view_U__array_view___CBUguid_winrt___winrt___ranges_std__V_lambda_1___1__GetIndexingStateMany2___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAA_AU__IVector_UItemIndexingState2_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt___Collections_Foundation_Windows_winrt__U__array_view___CBUguid_winrt___winrt___Z__ranges_4__Z(
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
                "nticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Imag"
                "eEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementatio"
                "n::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEm"
                "beddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::"
                "TextEmbeddingsGenerator>::MakeIndexingState(enum asg::SemanticIndex::ItemIndexingStatus,const struct asg"
                "::Guid &,const class std::optional<struct asg::Guid> &)";
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
0x180024770  mov     rax, rsp
0x180024773  mov     [rax+10h], rbx
0x180024777  mov     [rax+18h], rsi
0x18002477b  mov     [rax+20h], rdi
0x18002477f  push    rbp
0x180024780  push    r12
0x180024782  push    r13
0x180024784  push    r14
0x180024786  push    r15
0x180024788  lea     rbp, [rax-58h]
0x18002478c  sub     rsp, 130h
0x180024793  movaps  xmmword ptr [rax-38h], xmm6
0x180024797  movaps  xmmword ptr [rax-48h], xmm7
0x18002479b  mov     r14, rdx
0x18002479e  mov     rbx, rcx
0x1800247a1  xor     r15d, r15d
0x1800247a4  mov     r8b, 1
0x1800247a7  lea     rdx, [rbp+50h+var_98]
0x1800247ab  mov     rcx, [rcx]
0x1800247ae  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x1800247b3  nop
0x1800247b4  mov     rcx, [rbx]
0x1800247b7  mov     r8, [rbx+8]
0x1800247bb  lea     rdx, [rbp+50h+var_80]
0x1800247bf  mov     rcx, [rcx+0A8h]
0x1800247c6  call    ??$GetIndexingState@V?$transform_view@V?$ref_view@U?$array_view@$$CBUguid@winrt@@@winrt@@@ranges@std@@V_lambda_1_@?1??GetIndexingStateMany2@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AU?$IVector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@winrt@@U?$array_view@$$CBUguid@winrt@@@winrt@@@Z@@ranges@std@@@SemanticIndexStore@SemanticIndex@asg@@QEBA?AV?$unordered_map@UGuid@asg@@W4ItemIndexingStatus@SemanticIndex@2@U?$hash@UGuid@asg@@@std@@U?$equal_to@UGuid@asg@@@6@V?$allocator@U?$pair@$$CBUGuid@asg@@W4ItemIndexingStatus@SemanticIndex@2@@std@@@6@@std@@AEBV?$transform_view@V?$ref_view@U?$array_view@$$CBUguid@winrt@@@winrt@@@ranges@std@@V_lambda_1_@?1??GetIndexingStateMany2@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AU?$IVector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@winrt@@U?$array_view@$$CBUguid@winrt@@@winrt@@@Z@@ranges@4@@Z; asg::SemanticIndex::SemanticIndexStore::GetIndexingState<std::ranges::transform_view<std::ranges::ref_view<winrt::array_view<winrt::guid const>>,`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::GetIndexingStateMany2(winrt::array_view<winrt::guid const>)'::`2'::_lambda_1_>>(std::ranges::transform_view<std::ranges::ref_view<winrt::array_view<winrt::guid const>>,`winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::GetIndexingStateMany2(winrt::array_view<winrt::guid const>)'::`2'::_lambda_1_> const &)
0x1800247cb  nop
0x1800247cc  mov     rax, [rbx]
0x1800247cf  mov     rdi, [rax+0A8h]
0x1800247d6  mov     rax, [rdi+0B0h]
0x1800247dd  movups  xmm7, xmmword ptr [rax+0C8h]
0x1800247e4  mov     rcx, rdi; this
0x1800247e7  call    ?IsPreviousGraphEmpty@SemanticIndexStore@SemanticIndex@asg@@QEBA_NXZ; asg::SemanticIndex::SemanticIndexStore::IsPreviousGraphEmpty(void)
0x1800247ec  test    al, al
0x1800247ee  jz      short loc_1800247F9
0x1800247f0  movups  xmm6, xmmword ptr [rbp+50h+var_98]
0x1800247f4  xor     sil, sil
0x1800247f7  jmp     short loc_18002480A
0x1800247f9  mov     rax, [rdi+0C0h]
0x180024800  movups  xmm6, xmmword ptr [rax+0C8h]
0x180024807  mov     sil, 1
0x18002480a  xorps   xmm0, xmm0
0x18002480d  movdqu  xmmword ptr [rsp+150h+Block+8], xmm0
0x180024813  mov     qword ptr [rsp+150h+var_110], r15
0x180024818  mov     rax, [rbx+10h]
0x18002481c  mov     edx, [rax+8]
0x18002481f  lea     rcx, [rsp+150h+Block+8]
0x180024824  call    ?reserve@?$vector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@QEAAX_K@Z; std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>::reserve(unsigned __int64)
0x180024829  mov     rdi, [rbp+50h+var_78]
0x18002482d  mov     rbx, [rdi]
0x180024830  cmp     rbx, rdi
0x180024833  jz      loc_18002493D
0x180024839  lea     r13, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180024840  lea     r12, aStructWinrtMic_20; "struct winrt::Microsoft::Asg::SemanticI"...
0x180024847  mov     rdx, [rsp+150h+var_118]
0x18002484c  nop     dword ptr [rax+00h]
0x180024850  mov     ecx, [rbx+20h]
0x180024853  test    ecx, ecx
0x180024855  jz      short loc_1800248C2
0x180024857  sub     ecx, 1
0x18002485a  jz      short loc_1800248AE
0x18002485c  sub     ecx, 1
0x18002485f  jz      short loc_180024878
0x180024861  cmp     ecx, 1
0x180024864  jnz     loc_180024AC1
0x18002486a  mov     dword ptr [rsp+150h+var_110+8], 4
0x180024872  mov     byte ptr [rsp+150h+var_F8+4], cl
0x180024876  jmp     short loc_1800248CC
0x180024878  mov     dword ptr [rsp+150h+var_E8+8], 711h
0x180024880  mov     dword ptr [rsp+150h+var_E8+0Ch], 16h
0x180024888  mov     [rsp+150h+var_D8], r13
0x18002488d  mov     [rbp+50h+var_D0], r12
0x180024891  test    sil, sil
0x180024894  jz      loc_180024A8C
0x18002489a  mov     dword ptr [rsp+150h+var_110+8], 4
0x1800248a2  movups  [rsp+150h+var_110+0Ch], xmm6
0x1800248a7  mov     byte ptr [rsp+150h+var_F8+4], 1
0x1800248ac  jmp     short loc_1800248D8
0x1800248ae  mov     dword ptr [rsp+150h+var_110+8], 2
0x1800248b6  movups  [rsp+150h+var_110+0Ch], xmm7
0x1800248bb  mov     byte ptr [rsp+150h+var_F8+4], 0
0x1800248c0  jmp     short loc_1800248D8
0x1800248c2  mov     dword ptr [rsp+150h+var_110+8], r15d
0x1800248c7  mov     byte ptr [rsp+150h+var_F8+4], 0
0x1800248cc  movups  xmm0, cs:?empty@?1??EmptyGuid@asg@@YA?AUGuid@2@XZ@4U32@B; asg::Guid const `asg::EmptyGuid(void)'::`2'::empty
0x1800248d3  movups  [rsp+150h+var_110+0Ch], xmm0
0x1800248d8  movzx   eax, word ptr [rsp+150h+var_110+5]
0x1800248dd  mov     word ptr [rsp+150h+var_F8+5], ax
0x1800248e2  movzx   eax, byte ptr [rsp+150h+var_110+7]
0x1800248e7  mov     byte ptr [rsp+150h+var_F8+7], al
0x1800248eb  movups  xmm0, [rsp+150h+var_110+8]
0x1800248f0  movups  [rbp+50h+pExceptionObject], xmm0
0x1800248f4  movsd   xmm1, [rsp+150h+var_F8]
0x1800248fa  movsd   [rbp+50h+var_B0], xmm1
0x1800248ff  cmp     rdx, qword ptr [rsp+150h+var_110]
0x180024904  jz      short loc_18002491E
0x180024906  movups  xmmword ptr [rdx], xmm0
0x180024909  movsd   qword ptr [rdx+10h], xmm1
0x18002490e  mov     rdx, [rsp+150h+var_118]
0x180024913  add     rdx, 18h
0x180024917  mov     [rsp+150h+var_118], rdx
0x18002491c  jmp     short loc_180024931
0x18002491e  lea     r8, [rbp+50h+pExceptionObject]
0x180024922  lea     rcx, [rsp+150h+Block+8]
0x180024927  call    ??$_Emplace_reallocate@UTokenText@SemanticRegistry@asg@@@?$vector@UTokenText@SemanticRegistry@asg@@V?$allocator@UTokenText@SemanticRegistry@asg@@@std@@@std@@AEAAPEAUTokenText@SemanticRegistry@asg@@QEAU234@$$QEAU234@@Z; std::vector<asg::SemanticRegistry::TokenText>::_Emplace_reallocate<asg::SemanticRegistry::TokenText>(asg::SemanticRegistry::TokenText * const,asg::SemanticRegistry::TokenText &&)
0x18002492c  mov     rdx, [rsp+150h+var_118]
0x180024931  mov     rbx, [rbx]
0x180024934  cmp     rbx, rdi
0x180024937  jnz     loc_180024850
0x18002493d  mov     ecx, 50h ; 'P'; Size
0x180024942  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024947  mov     r9, rax
0x18002494a  mov     [rbp+50h+arg_0], rax
0x18002494e  lea     r8, [rax+10h]
0x180024952  lea     rax, ??_7?$produce@U?$vector_impl@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@U?$IVector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>>::`vftable'
0x180024959  mov     [r8], rax
0x18002495c  lea     rax, ??_7?$produce@U?$vector_impl@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@U?$IVectorView@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>>::`vftable'
0x180024963  mov     [r8+8], rax
0x180024967  lea     rax, ??_7?$produce@U?$vector_impl@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@U?$IIterable@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>>::`vftable'
0x18002496e  mov     [r8+10h], rax
0x180024972  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180024979  mov     qword ptr [r9+8], 1
0x180024981  xor     eax, eax
0x180024983  mov     [r9+28h], eax
0x180024987  mov     [r9+30h], r15
0x18002498b  lea     rax, ??_7?$vector_impl@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@6B@; const winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>::`vftable'
0x180024992  mov     [r9], rax
0x180024995  mov     rdx, qword ptr [rsp+150h+var_110]
0x18002499a  mov     qword ptr [rsp+150h+var_110], r15
0x18002499f  mov     rcx, [rsp+150h+var_118]
0x1800249a4  mov     [rsp+150h+var_118], r15
0x1800249a9  mov     rax, [rsp+150h+Block+8]
0x1800249ae  mov     [rsp+150h+Block+8], r15
0x1800249b3  mov     [r9+38h], rax
0x1800249b7  mov     [r9+40h], rcx
0x1800249bb  mov     [r9+48h], rdx
0x1800249bf  lea     rax, ??_7?$heap_implements@U?$vector_impl@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$vector@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UItemIndexingState2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@7@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::vector_impl<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2,std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2>,winrt::impl::multi_threaded_collection_base>>::`vftable'
0x1800249c6  mov     [r9], rax
0x1800249c9  mov     [r14], r8
0x1800249cc  mov     r8, [rsp+150h+Block+8]
0x1800249d1  test    r8, r8
0x1800249d4  jz      short loc_180024A3C
0x1800249d6  mov     rcx, qword ptr [rsp+150h+var_110]
0x1800249db  sub     rcx, r8
0x1800249de  mov     rax, 2AAAAAAAAAAAAAABh
0x1800249e8  imul    rcx
0x1800249eb  sar     rdx, 2
0x1800249ef  mov     rax, rdx
0x1800249f2  shr     rax, 3Fh
0x1800249f6  add     rdx, rax
0x1800249f9  lea     rdx, [rdx+rdx*2]
0x1800249fd  shl     rdx, 3
0x180024a01  mov     rax, r8
0x180024a04  cmp     rdx, 1000h
0x180024a0b  jb      short loc_180024A26
0x180024a0d  add     rdx, 27h ; '''
0x180024a11  mov     r8, [r8-8]
0x180024a15  sub     rax, r8
0x180024a18  sub     rax, 8
0x180024a1c  cmp     rax, 1Fh
0x180024a20  ja      loc_180024AAC
0x180024a26  mov     rcx, r8; Block
0x180024a29  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024a2e  xorps   xmm0, xmm0
0x180024a31  movdqu  xmmword ptr [rsp+150h+Block+8], xmm0
0x180024a37  mov     qword ptr [rsp+150h+var_110], r15
0x180024a3c  lea     rcx, [rbp+50h+var_68]
0x180024a40  call    ?_Tidy@?$vector@U?$pair@II@std@@V?$allocator@U?$pair@II@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<uint,uint>>::_Tidy(void)
0x180024a45  lea     rcx, [rbp+50h+var_78]
0x180024a49  call    ??1?$list@U?$pair@$$CBUGuid@asg@@M@std@@V?$allocator@U?$pair@$$CBUGuid@asg@@M@std@@@2@@std@@QEAA@XZ; std::list<std::pair<asg::Guid const,float>>::~list<std::pair<asg::Guid const,float>>(void)
0x180024a4e  nop
0x180024a4f  cmp     byte ptr [rbp+50h+var_98+8], 0
0x180024a53  jz      short loc_180024A5E
0x180024a55  mov     rcx, [rbp+50h+var_98]; _Mtx_t
0x180024a59  call    _Mtx_unlock
0x180024a5e  mov     rax, r14
0x180024a61  lea     r11, [rsp+150h+var_20]
0x180024a69  mov     rbx, [r11+38h]
0x180024a6d  mov     rsi, [r11+40h]
0x180024a71  mov     rdi, [r11+48h]
0x180024a75  movaps  xmm6, xmmword ptr [r11-10h]
0x180024a7a  movaps  xmm7, xmmword ptr [r11-20h]
0x180024a7f  mov     rsp, r11
0x180024a82  pop     r15
0x180024a84  pop     r14
0x180024a86  pop     r13
0x180024a88  pop     r12
0x180024a8a  pop     rbp
0x180024a8b  retn
0x180024a8c  movaps  xmm0, [rsp+150h+var_E8+8]
0x180024a91  movaps  [rbp+50h+pExceptionObject], xmm0
0x180024a95  movsd   xmm1, [rbp+50h+var_D0]
0x180024a9a  movsd   [rbp+50h+var_B0], xmm1
0x180024a9f  mov     rdx, r12
0x180024aa2  lea     rcx, [rbp+50h+pExceptionObject]
0x180024aa6  call    ?AsgAssertFail@details@asg@@YAXUsource_location@std@@PEBD@Z; asg::details::AsgAssertFail(std::source_location,char const *)
0x180024aac  mov     [rsp+150h+Reserved], r15; Reserved
0x180024ab1  xor     r9d, r9d; LineNo
0x180024ab4  xor     r8d, r8d; FileName
0x180024ab7  xor     edx, edx; FunctionName
0x180024ab9  xor     ecx, ecx; Expression
0x180024abb  call    _invoke_watson
0x180024ac1  mov     dword ptr [rsp+150h+var_E8+8], 71Ah
0x180024ac9  mov     [rsp+150h+var_D8], r13
0x180024ace  mov     [rbp+50h+var_D0], r15
0x180024ad2  lea     rdx, aInvalidIndexin; "Invalid indexing state"
0x180024ad9  lea     rcx, [rsp+150h+var_110+8]; this
0x180024ade  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180024ae3  lea     r8, [rsp+150h+var_E8+8]; struct winrt::impl::slim_source_location *
0x180024ae8  lea     rdx, [rsp+150h+var_110+8]; struct winrt::param::hstring *
0x180024aed  lea     rcx, [rbp+50h+pExceptionObject]; this
0x180024af1  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180024af6  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180024afd  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x180024b01  call    _CxxThrowException
```
