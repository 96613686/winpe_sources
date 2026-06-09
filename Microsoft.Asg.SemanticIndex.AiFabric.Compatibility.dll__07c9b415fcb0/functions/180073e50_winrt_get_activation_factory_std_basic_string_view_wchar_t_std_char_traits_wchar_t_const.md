# winrt_get_activation_factory(std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &)

- ea: `0x180073e50`
- end: `0x18007434b`
- name: `?winrt_get_activation_factory@@YAPEAXAEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `1275`
- prototype: `void *__fastcall(char **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074460`

## callees

- `0x180003d40`
- `0x180057b00`
- `0x1800609f0`
- `0x180064e40`
- `0x180073e50`
- `0x180074350`
- `0x1801f7190`

## string_xrefs

- `0x1800742dc`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.TextEmbeddingsGenerator`
- `0x1800742ab`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticVectorSpaceModelRegistry`
- `0x18007430d`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.TextEmbeddingsOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void *__fastcall winrt_get_activation_factory(char **a1)
{
  char *v2; // rax
  __int64 v3; // rcx
  char *v4; // rdx
  __int64 v5; // rcx
  signed __int64 v6; // r9
  char *v7; // r8
  char *v8; // rdx
  void ***v9; // rcx
  void *result; // rax
  void **v11; // rdx
  signed __int64 v12; // r9
  char *v13; // r8
  char *v14; // rdx
  char *v15; // rcx
  char *v16; // rdx
  char *v17; // r8
  char *v18; // rcx
  char *v19; // rdx
  char *v20; // r8
  char *v21; // rcx
  char *v22; // rdx
  char *v23; // r8
  char *v24; // rcx
  char *v25; // rdx
  char *v26; // r8
  char *v27; // rcx
  char *v28; // rdx
  char *v29; // r8
  char *v30; // rcx
  char *v31; // rdx
  char *v32; // r8
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  _BYTE v36[24]; // [rsp+20h] [rbp-18h] BYREF

  v2 = *a1;
  v3 = 2LL * (_QWORD)a1[1];
  v4 = &v2[v3];
  v5 = v3 >> 1;
  if ( v5 == 71 )
  {
    if ( v4 == v2 )
    {
LABEL_12:
      v9 = (void ***)operator new(0x28u);
      *v9 = 0;
      v9[1] = 0;
      result = v9 + 2;
      v9[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::EmbeddingsSerializer,winrt::Windows::Foundation::IActivationFactory>::`vftable';
      v9[3] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics>::`vftable';
      v9[4] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>::`vftable';
      v11 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::EmbeddingsSerializer>::`vftable';
      goto LABEL_13;
    }
    v12 = (char *)L"" - v4;
    v13 = v4 - 2;
    while ( 1 )
    {
      v14 = v13;
      if ( *(_WORD *)v13 != *(_WORD *)&v13[v12] )
        break;
      v13 -= 2;
      if ( v14 == v2 )
        goto LABEL_12;
    }
  }
  else if ( v5 == 75 )
  {
    if ( v4 == v2 )
    {
LABEL_7:
      v9 = (void ***)operator new(0x20u);
      *v9 = 0;
      v9[1] = 0;
      result = v9 + 2;
      v9[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::ImageEmbeddingsGenerator,winrt::Windows::Foundation::IActivationFactory>::`vftable';
      v9[3] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>::`vftable';
      v11 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::ImageEmbeddingsGenerator>::`vftable';
      goto LABEL_13;
    }
    v6 = (char *)L"" - v4;
    v7 = v4 - 2;
    while ( 1 )
    {
      v8 = v7;
      if ( *(_WORD *)v7 != *(_WORD *)&v7[v6] )
        break;
      v7 -= 2;
      if ( v8 == v2 )
        goto LABEL_7;
    }
  }
  v15 = &v2[2 * (_QWORD)a1[1]];
  if ( 2LL * (_QWORD)a1[1] == 132 )
  {
    if ( v15 == v2 )
    {
LABEL_19:
      v9 = (void ***)operator new(0x20u);
      *v9 = 0;
      v9[1] = 0;
      result = v9 + 2;
      v9[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::QueryEmbeddings,winrt::Windows::Foundation::IActivationFactory>::`vftable';
      v9[3] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::QueryEmbeddings,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryEmbeddingsFactory>::`vftable';
      v11 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::QueryEmbeddings>::`vftable';
      goto LABEL_13;
    }
    v16 = v15 - 2;
    while ( 1 )
    {
      v17 = v16;
      if ( *(_WORD *)v16 != *(_WORD *)&v16[(char *)L"" - v15] )
        break;
      v16 -= 2;
      if ( v17 == v2 )
        goto LABEL_19;
    }
  }
  v18 = &v2[2 * (_QWORD)a1[1]];
  if ( 2LL * (_QWORD)a1[1] == 148 )
  {
    if ( v18 == v2 )
    {
LABEL_25:
      v9 = (void ***)operator new(0x30u);
      *v9 = 0;
      v9[1] = 0;
      result = v9 + 2;
      v9[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStore,winrt::Windows::Foundation::IActivationFactory>::`vftable';
      v9[3] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::`vftable';
      v9[4] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::`vftable';
      v9[5] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics3>::`vftable';
      v11 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStore>::`vftable';
      goto LABEL_13;
    }
    v19 = v18 - 2;
    while ( 1 )
    {
      v20 = v19;
      if ( *(_WORD *)v19 != *(_WORD *)&v19[(char *)L"" - v18] )
        break;
      v19 -= 2;
      if ( v20 == v2 )
        goto LABEL_25;
    }
  }
  v21 = &v2[2 * (_QWORD)a1[1]];
  if ( 2LL * (_QWORD)a1[1] == 162 )
  {
    if ( v21 == v2 )
    {
LABEL_31:
      v9 = (void ***)operator new(0x28u);
      *v9 = 0;
      v9[1] = 0;
      result = v9 + 2;
      v9[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStoreOptions,winrt::Windows::Foundation::IActivationFactory>::`vftable';
      v9[3] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory>::`vftable';
      v9[4] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2>::`vftable';
      v11 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStoreOptions>::`vftable';
      goto LABEL_13;
    }
    v22 = v21 - 2;
    while ( 1 )
    {
      v23 = v22;
      if ( *(_WORD *)v22 != *(_WORD *)&v22[(char *)L"" - v21] )
        break;
      v22 -= 2;
      if ( v23 == v2 )
        goto LABEL_31;
    }
  }
  v24 = &v2[2 * (_QWORD)a1[1]];
  if ( 2LL * (_QWORD)a1[1] == 142 )
  {
    if ( v24 == v2 )
    {
LABEL_37:
      v9 = (void ***)operator new(0x18u);
      *v9 = 0;
      v9[1] = 0;
      result = v9 + 2;
      v9[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticQueryOptions,winrt::Windows::Foundation::IActivationFactory>::`vftable';
      v11 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticQueryOptions>::`vftable';
      goto LABEL_13;
    }
    v25 = v24 - 2;
    while ( 1 )
    {
      v26 = v25;
      if ( *(_WORD *)v25 != *(_WORD *)&v25[(char *)L"" - v24] )
        break;
      v25 -= 2;
      if ( v26 == v2 )
        goto LABEL_37;
    }
  }
  v27 = &v2[2 * (_QWORD)a1[1]];
  if ( 2LL * (_QWORD)a1[1] == 146 )
  {
    if ( v27 == v2 )
    {
LABEL_43:
      v9 = (void ***)operator new(0x30u);
      *v9 = 0;
      v9[1] = 0;
      result = v9 + 2;
      v9[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStore,winrt::Windows::Foundation::IActivationFactory>::`vftable';
      v9[3] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::`vftable';
      v9[4] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>::`vftable';
      v9[5] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3>::`vftable';
      v11 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStore>::`vftable';
      goto LABEL_13;
    }
    v28 = v27 - 2;
    while ( 1 )
    {
      v29 = v28;
      if ( *(_WORD *)v28 != *(_WORD *)&v28[(char *)L"" - v27] )
        break;
      v28 -= 2;
      if ( v29 == v2 )
        goto LABEL_43;
    }
  }
  v30 = &v2[2 * (_QWORD)a1[1]];
  if ( 2LL * (_QWORD)a1[1] == 160 )
  {
    if ( v30 != v2 )
    {
      v31 = v30 - 2;
      do
      {
        v32 = v31;
        if ( *(_WORD *)v31 != *(_WORD *)&v31[(char *)L"" - v30] )
          goto LABEL_50;
        v31 -= 2;
      }
      while ( v32 != v2 );
    }
    v9 = (void ***)operator new(0x28u);
    *v9 = 0;
    v9[1] = 0;
    result = v9 + 2;
    v9[2] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStoreOptions,winrt::Windows::Foundation::IActivationFactory>::`vftable';
    v9[3] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory>::`vftable';
    v9[4] = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2>::`vftable';
    v11 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStoreOptions>::`vftable';
LABEL_13:
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *v9 = v11;
    v9[1] = (void **)1;
    return result;
  }
LABEL_50:
  std::wstring_view::basic_string_view<wchar_t,std::char_traits<wchar_t>>(
    v36,
    L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticVectorSpaceModelRegistry");
  if ( (unsigned __int8)winrt_get_activation_factory_::_2_::_lambda_1_::operator()(v33, a1, v36) )
    return winrt_make_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_SemanticVectorSpaceModelRegistry();
  std::wstring_view::basic_string_view<wchar_t,std::char_traits<wchar_t>>(
    v36,
    L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.TextEmbeddingsGenerator");
  if ( (unsigned __int8)winrt_get_activation_factory_::_2_::_lambda_1_::operator()(v34, a1, v36) )
    return winrt_make_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_TextEmbeddingsGenerator();
  std::wstring_view::basic_string_view<wchar_t,std::char_traits<wchar_t>>(
    v36,
    L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.TextEmbeddingsOptions");
  if ( (unsigned __int8)winrt_get_activation_factory_::_2_::_lambda_1_::operator()(v35, a1, v36) )
    return winrt_make_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_TextEmbeddingsOptions();
  else
    return 0;
}

```

## disassembly

```asm
0x180073e50  mov     [rsp+arg_8], rbx
0x180073e55  push    rdi
0x180073e56  sub     rsp, 30h
0x180073e5a  mov     rdx, [rcx+8]
0x180073e5e  mov     rbx, rcx
0x180073e61  mov     rax, [rcx]
0x180073e64  xor     edi, edi
0x180073e66  lea     rcx, [rdx+rdx]
0x180073e6a  lea     rdx, [rcx+rax]
0x180073e6e  sar     rcx, 1
0x180073e71  cmp     rcx, 47h ; 'G'
0x180073e75  jz      short loc_180073EE8
0x180073e77  cmp     rcx, 4Bh ; 'K'
0x180073e7b  jnz     loc_180073F73
0x180073e81  cmp     rdx, rax
0x180073e84  jz      short loc_180073EAF
0x180073e86  lea     r9, aMicrosoftAsgSe_25+96h; ""
0x180073e8d  sub     r9, rdx
0x180073e90  lea     r8, [rdx-2]
0x180073e94  movzx   ecx, word ptr [r9+r8]
0x180073e99  mov     rdx, r8
0x180073e9c  cmp     [r8], cx
0x180073ea0  jnz     loc_180073F73
0x180073ea6  sub     r8, 2
0x180073eaa  cmp     rdx, rax
0x180073ead  jnz     short loc_180073E94
0x180073eaf  mov     ecx, 20h ; ' '; Size
0x180073eb4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180073eb9  lea     rdx, ??_7?$produce@UImageEmbeddingsGenerator@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIActivationFactory@Foundation@Windows@8@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::ImageEmbeddingsGenerator,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180073ec0  mov     rcx, rax
0x180073ec3  mov     [rax], rdi
0x180073ec6  mov     [rax+8], rdi
0x180073eca  add     rax, 10h
0x180073ece  mov     [rax], rdx
0x180073ed1  lea     rdx, ??_7?$produce@UImageEmbeddingsGenerator@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIImageEmbeddingsGeneratorStatics@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IImageEmbeddingsGeneratorStatics>::`vftable'
0x180073ed8  mov     [rax+8], rdx
0x180073edc  lea     rdx, ??_7?$heap_implements@UImageEmbeddingsGenerator@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::ImageEmbeddingsGenerator>::`vftable'
0x180073ee3  jmp     loc_180073F56
0x180073ee8  cmp     rdx, rax
0x180073eeb  jz      short loc_180073F17
0x180073eed  lea     r9, aMicrosoftAsgSe_18+8Eh; ""
0x180073ef4  sub     r9, rdx
0x180073ef7  lea     r8, [rdx-2]
0x180073efb  nop     dword ptr [rax+rax+00h]
0x180073f00  movzx   ecx, word ptr [r9+r8]
0x180073f05  mov     rdx, r8
0x180073f08  cmp     [r8], cx
0x180073f0c  jnz     short loc_180073F73
0x180073f0e  sub     r8, 2
0x180073f12  cmp     rdx, rax
0x180073f15  jnz     short loc_180073F00
0x180073f17  mov     ecx, 28h ; '('; Size
0x180073f1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180073f21  lea     rdx, ??_7?$produce@UEmbeddingsSerializer@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIActivationFactory@Foundation@Windows@8@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::EmbeddingsSerializer,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180073f28  mov     rcx, rax
0x180073f2b  mov     [rax], rdi
0x180073f2e  mov     [rax+8], rdi
0x180073f32  add     rax, 10h
0x180073f36  mov     [rax], rdx
0x180073f39  lea     rdx, ??_7?$produce@UEmbeddingsSerializer@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics>::`vftable'
0x180073f40  mov     [rax+8], rdx
0x180073f44  lea     rdx, ??_7?$produce@UEmbeddingsSerializer@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIEmbeddingsSerializerStatics2@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::EmbeddingsSerializer,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsSerializerStatics2>::`vftable'
0x180073f4b  mov     [rax+10h], rdx
0x180073f4f  lea     rdx, ??_7?$heap_implements@UEmbeddingsSerializer@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::EmbeddingsSerializer>::`vftable'
0x180073f56  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180073f5d  mov     [rcx], rdx
0x180073f60  mov     qword ptr [rcx+8], 1
0x180073f68  mov     rbx, [rsp+38h+arg_8]
0x180073f6d  add     rsp, 30h
0x180073f71  pop     rdi
0x180073f72  retn
0x180073f73  mov     rcx, [rbx+8]
0x180073f77  lea     rdx, [rcx+rcx]
0x180073f7b  lea     rcx, [rdx+rax]
0x180073f7f  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180073f83  cmp     rdx, 84h
0x180073f8a  jnz     short loc_180073FEF
0x180073f8c  cmp     rcx, rax
0x180073f8f  jz      short loc_180073FB6
0x180073f91  lea     r9, aMicrosoftAsgSe_1+84h; ""
0x180073f98  sub     r9, rcx
0x180073f9b  lea     rdx, [rcx-2]
0x180073f9f  nop
0x180073fa0  movzx   ecx, word ptr [r9+rdx]
0x180073fa5  mov     r8, rdx
0x180073fa8  cmp     [rdx], cx
0x180073fab  jnz     short loc_180073FEF
0x180073fad  sub     rdx, 2
0x180073fb1  cmp     r8, rax
0x180073fb4  jnz     short loc_180073FA0
0x180073fb6  mov     ecx, 20h ; ' '; Size
0x180073fbb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180073fc0  lea     rdx, ??_7?$produce@UQueryEmbeddings@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIActivationFactory@Foundation@Windows@8@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::QueryEmbeddings,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180073fc7  mov     rcx, rax
0x180073fca  mov     [rax], rdi
0x180073fcd  mov     [rax+8], rdi
0x180073fd1  add     rax, 10h
0x180073fd5  mov     [rax], rdx
0x180073fd8  lea     rdx, ??_7?$produce@UQueryEmbeddings@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIQueryEmbeddingsFactory@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::QueryEmbeddings,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IQueryEmbeddingsFactory>::`vftable'
0x180073fdf  mov     [rax+8], rdx
0x180073fe3  lea     rdx, ??_7?$heap_implements@UQueryEmbeddings@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::QueryEmbeddings>::`vftable'
0x180073fea  jmp     loc_180073F56
0x180073fef  mov     rcx, [rbx+8]
0x180073ff3  lea     rdx, [rcx+rcx]
0x180073ff7  lea     rcx, [rdx+rax]
0x180073ffb  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180073fff  cmp     rdx, 94h
0x180074006  jnz     loc_180074085
0x18007400c  cmp     rcx, rax
0x18007400f  jz      short loc_180074036
0x180074011  lea     r9, aMicrosoftAsgSe_26+94h; ""
0x180074018  sub     r9, rcx
0x18007401b  lea     rdx, [rcx-2]
0x18007401f  nop
0x180074020  movzx   ecx, word ptr [r9+rdx]
0x180074025  mov     r8, rdx
0x180074028  cmp     [rdx], cx
0x18007402b  jnz     short loc_180074085
0x18007402d  sub     rdx, 2
0x180074031  cmp     r8, rax
0x180074034  jnz     short loc_180074020
0x180074036  mov     ecx, 30h ; '0'; Size
0x18007403b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074040  lea     rdx, ??_7?$produce@USemanticImageIndexStore@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIActivationFactory@Foundation@Windows@8@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStore,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180074047  mov     rcx, rax
0x18007404a  mov     [rax], rdi
0x18007404d  mov     [rax+8], rdi
0x180074051  add     rax, 10h
0x180074055  mov     [rax], rdx
0x180074058  lea     rdx, ??_7?$produce@USemanticImageIndexStore@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::`vftable'
0x18007405f  mov     [rax+8], rdx
0x180074063  lea     rdx, ??_7?$produce@USemanticImageIndexStore@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::`vftable'
0x18007406a  mov     [rax+10h], rdx
0x18007406e  lea     rdx, ??_7?$produce@USemanticImageIndexStore@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics3@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics3>::`vftable'
0x180074075  mov     [rax+18h], rdx
0x180074079  lea     rdx, ??_7?$heap_implements@USemanticImageIndexStore@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStore>::`vftable'
0x180074080  jmp     loc_180073F56
0x180074085  mov     rcx, [rbx+8]
0x180074089  lea     rdx, [rcx+rcx]
0x18007408d  lea     rcx, [rdx+rax]
0x180074091  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180074095  cmp     rdx, 0A2h
0x18007409c  jnz     short loc_18007410B
0x18007409e  cmp     rcx, rax
0x1800740a1  jz      short loc_1800740C7
0x1800740a3  lea     r9, aMicrosoftAsgSe_9+0A2h; ""
0x1800740aa  sub     r9, rcx
0x1800740ad  lea     rdx, [rcx-2]
0x1800740b1  movzx   ecx, word ptr [r9+rdx]
0x1800740b6  mov     r8, rdx
0x1800740b9  cmp     [rdx], cx
0x1800740bc  jnz     short loc_18007410B
0x1800740be  sub     rdx, 2
0x1800740c2  cmp     r8, rax
0x1800740c5  jnz     short loc_1800740B1
0x1800740c7  mov     ecx, 28h ; '('; Size
0x1800740cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800740d1  lea     rdx, ??_7?$produce@USemanticImageIndexStoreOptions@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIActivationFactory@Foundation@Windows@8@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStoreOptions,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x1800740d8  mov     rcx, rax
0x1800740db  mov     [rax], rdi
0x1800740de  mov     [rax+8], rdi
0x1800740e2  add     rax, 10h
0x1800740e6  mov     [rax], rdx
0x1800740e9  lea     rdx, ??_7?$produce@USemanticImageIndexStoreOptions@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreOptionsFactory@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory>::`vftable'
0x1800740f0  mov     [rax+8], rdx
0x1800740f4  lea     rdx, ??_7?$produce@USemanticImageIndexStoreOptions@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreOptionsFactory2@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2>::`vftable'
0x1800740fb  mov     [rax+10h], rdx
0x1800740ff  lea     rdx, ??_7?$heap_implements@USemanticImageIndexStoreOptions@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticImageIndexStoreOptions>::`vftable'
0x180074106  jmp     loc_180073F56
0x18007410b  mov     rcx, [rbx+8]
0x18007410f  lea     rdx, [rcx+rcx]
0x180074113  lea     rcx, [rdx+rax]
0x180074117  and     rdx, 0FFFFFFFFFFFFFFFEh
0x18007411b  cmp     rdx, 8Eh
0x180074122  jnz     short loc_180074184
0x180074124  cmp     rcx, rax
0x180074127  jz      short loc_180074156
0x180074129  lea     r9, aMicrosoftAsgSe_14+8Eh; ""
0x180074130  sub     r9, rcx
0x180074133  lea     rdx, [rcx-2]
0x180074137  nop     word ptr [rax+rax+00000000h]
0x180074140  movzx   ecx, word ptr [rdx+r9]
0x180074145  mov     r8, rdx
0x180074148  cmp     [rdx], cx
0x18007414b  jnz     short loc_180074184
0x18007414d  sub     rdx, 2
0x180074151  cmp     r8, rax
0x180074154  jnz     short loc_180074140
0x180074156  mov     ecx, 18h; Size
0x18007415b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074160  lea     rdx, ??_7?$produce@USemanticQueryOptions@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIActivationFactory@Foundation@Windows@8@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticQueryOptions,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180074167  mov     rcx, rax
0x18007416a  mov     [rax], rdi
0x18007416d  mov     [rax+8], rdi
0x180074171  add     rax, 10h
0x180074175  mov     [rax], rdx
0x180074178  lea     rdx, ??_7?$heap_implements@USemanticQueryOptions@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticQueryOptions>::`vftable'
0x18007417f  jmp     loc_180073F56
0x180074184  mov     rcx, [rbx+8]
0x180074188  lea     rdx, [rcx+rcx]
0x18007418c  lea     rcx, [rdx+rax]
0x180074190  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180074194  cmp     rdx, 92h
0x18007419b  jnz     loc_180074225
0x1800741a1  cmp     rcx, rax
0x1800741a4  jz      short loc_1800741D6
0x1800741a6  lea     r9, aMicrosoftAsgSe_4+92h; ""
0x1800741ad  sub     r9, rcx
0x1800741b0  lea     rdx, [rcx-2]
0x1800741b4  nop     dword ptr [rax+00h]
0x1800741b8  nop     dword ptr [rax+rax+00000000h]
0x1800741c0  movzx   ecx, word ptr [rdx+r9]
0x1800741c5  mov     r8, rdx
0x1800741c8  cmp     [rdx], cx
0x1800741cb  jnz     short loc_180074225
0x1800741cd  sub     rdx, 2
0x1800741d1  cmp     r8, rax
0x1800741d4  jnz     short loc_1800741C0
0x1800741d6  mov     ecx, 30h ; '0'; Size
0x1800741db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800741e0  lea     rdx, ??_7?$produce@USemanticTextIndexStore@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIActivationFactory@Foundation@Windows@8@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStore,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x1800741e7  mov     rcx, rax
0x1800741ea  mov     [rax], rdi
0x1800741ed  mov     [rax+8], rdi
0x1800741f1  add     rax, 10h
0x1800741f5  mov     [rax], rdx
0x1800741f8  lea     rdx, ??_7?$produce@USemanticTextIndexStore@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::`vftable'
0x1800741ff  mov     [rax+8], rdx
0x180074203  lea     rdx, ??_7?$produce@USemanticTextIndexStore@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>::`vftable'
0x18007420a  mov     [rax+10h], rdx
0x18007420e  lea     rdx, ??_7?$produce@USemanticTextIndexStore@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics3@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3>::`vftable'
0x180074215  mov     [rax+18h], rdx
0x180074219  lea     rdx, ??_7?$heap_implements@USemanticTextIndexStore@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStore>::`vftable'
0x180074220  jmp     loc_180073F56
0x180074225  mov     rcx, [rbx+8]
0x180074229  lea     rdx, [rcx+rcx]
0x18007422d  lea     rcx, [rdx+rax]
0x180074231  and     rdx, 0FFFFFFFFFFFFFFFEh
0x180074235  cmp     rdx, 0A0h
0x18007423c  jnz     short loc_1800742AB
0x18007423e  cmp     rcx, rax
0x180074241  jz      short loc_180074267
0x180074243  lea     r9, aMicrosoftAsgSe_21+0A0h; ""
0x18007424a  sub     r9, rcx
0x18007424d  lea     rdx, [rcx-2]
0x180074251  movzx   ecx, word ptr [rdx+r9]
0x180074256  mov     r8, rdx
0x180074259  cmp     [rdx], cx
0x18007425c  jnz     short loc_1800742AB
0x18007425e  sub     rdx, 2
0x180074262  cmp     r8, rax
0x180074265  jnz     short loc_180074251
0x180074267  mov     ecx, 28h ; '('; Size
0x18007426c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074271  lea     rdx, ??_7?$produce@USemanticTextIndexStoreOptions@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIActivationFactory@Foundation@Windows@8@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStoreOptions,winrt::Windows::Foundation::IActivationFactory>::`vftable'
0x180074278  mov     rcx, rax
0x18007427b  mov     [rax], rdi
0x18007427e  mov     [rax+8], rdi
0x180074282  add     rax, 10h
0x180074286  mov     [rax], rdx
0x180074289  lea     rdx, ??_7?$produce@USemanticTextIndexStoreOptions@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreOptionsFactory@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory>::`vftable'
0x180074290  mov     [rax+8], rdx
0x180074294  lea     rdx, ??_7?$produce@USemanticTextIndexStoreOptions@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreOptionsFactory2@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2>::`vftable'
0x18007429b  mov     [rax+10h], rdx
0x18007429f  lea     rdx, ??_7?$heap_implements@USemanticTextIndexStoreOptions@factory_implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::factory_implementation::SemanticTextIndexStoreOptions>::`vftable'
0x1800742a6  jmp     loc_180073F56
0x1800742ab  lea     rdx, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x1800742b2  lea     rcx, [rsp+38h+var_18]
0x1800742b7  call    ??0?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEAA@QEB_W@Z; std::wstring_view::basic_string_view<wchar_t,std::char_traits<wchar_t>>(wchar_t const * const)
0x1800742bc  lea     r8, [rsp+38h+var_18]
0x1800742c1  mov     rdx, rbx
0x1800742c4  call    _winrt_get_activation_factory____2____lambda_1___operator__
0x1800742c9  test    al, al
0x1800742cb  jz      short loc_1800742DC
0x1800742cd  mov     rbx, [rsp+38h+arg_8]
0x1800742d2  add     rsp, 30h
0x1800742d6  pop     rdi
0x1800742d7  jmp     ?winrt_make_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_SemanticVectorSpaceModelRegistry@@YAPEAXXZ; winrt_make_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_SemanticVectorSpaceModelRegistry(void)
0x1800742dc  lea     rdx, aMicrosoftAsgSe_23; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x1800742e3  lea     rcx, [rsp+38h+var_18]
0x1800742e8  call    ??0?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEAA@QEB_W@Z; std::wstring_view::basic_string_view<wchar_t,std::char_traits<wchar_t>>(wchar_t const * const)
0x1800742ed  lea     r8, [rsp+38h+var_18]
0x1800742f2  mov     rdx, rbx
0x1800742f5  call    _winrt_get_activation_factory____2____lambda_1___operator__
0x1800742fa  test    al, al
0x1800742fc  jz      short loc_18007430D
0x1800742fe  mov     rbx, [rsp+38h+arg_8]
0x180074303  add     rsp, 30h
0x180074307  pop     rdi
0x180074308  jmp     ?winrt_make_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_TextEmbeddingsGenerator@@YAPEAXXZ; winrt_make_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_TextEmbeddingsGenerator(void)
0x18007430d  lea     rdx, aMicrosoftAsgSe_27; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180074314  lea     rcx, [rsp+38h+var_18]
0x180074319  call    ??0?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEAA@QEB_W@Z; std::wstring_view::basic_string_view<wchar_t,std::char_traits<wchar_t>>(wchar_t const * const)
0x18007431e  lea     r8, [rsp+38h+var_18]
0x180074323  mov     rdx, rbx
0x180074326  call    _winrt_get_activation_factory____2____lambda_1___operator__
0x18007432b  test    al, al
0x18007432d  jz      short loc_18007433E
0x18007432f  mov     rbx, [rsp+38h+arg_8]
0x180074334  add     rsp, 30h
  ... truncated ...
```
