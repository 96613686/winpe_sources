# _dynamic_initializer_for__s_modelKindToApiClassName__

- ea: `0x180001dc0`
- end: `0x180002304`
- name: `_dynamic_initializer_for__s_modelKindToApiClassName__`
- size: `1348`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000db50`
- `0x1800101e0`
- `0x1800139b0`
- `0x1800157c0`
- `0x18002cd30`
- `0x180035060`
- `0x1800353fc`
- `0x180035430`

## string_xrefs

- `0x180001f23`: `Microsoft.Graphics.Imaging.ImageObjectRemover`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
int dynamic_initializer_for__s_modelKindToApiClassName__()
{
  __int64 v0; // rcx
  _QWORD *v1; // r14
  winrt::impl **v2; // rbx
  __int64 v3; // rax
  void *v4; // rdi
  _DWORD *v5; // rsi
  struct winrt::impl::hstring_header *v6; // rdx
  const wchar_t *v8; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v9; // [rsp+28h] [rbp-D8h]
  __int128 v10; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  struct winrt::impl::shared_hstring_header *v12; // [rsp+48h] [rbp-B8h] BYREF
  int v13; // [rsp+50h] [rbp-B0h]
  struct winrt::impl::shared_hstring_header *v14; // [rsp+58h] [rbp-A8h] BYREF
  int v15; // [rsp+60h] [rbp-A0h]
  struct winrt::impl::shared_hstring_header *v16; // [rsp+68h] [rbp-98h] BYREF
  int v17; // [rsp+70h] [rbp-90h]
  struct winrt::impl::shared_hstring_header *v18; // [rsp+78h] [rbp-88h] BYREF
  int v19; // [rsp+80h] [rbp-80h]
  struct winrt::impl::shared_hstring_header *v20; // [rsp+88h] [rbp-78h] BYREF
  int v21; // [rsp+90h] [rbp-70h]
  struct winrt::impl::shared_hstring_header *v22; // [rsp+98h] [rbp-68h] BYREF
  int v23; // [rsp+A0h] [rbp-60h]
  struct winrt::impl::shared_hstring_header *v24; // [rsp+A8h] [rbp-58h] BYREF
  int v25; // [rsp+B0h] [rbp-50h]
  struct winrt::impl::shared_hstring_header *v26; // [rsp+B8h] [rbp-48h] BYREF
  int v27; // [rsp+C0h] [rbp-40h]
  struct winrt::impl::shared_hstring_header *v28; // [rsp+C8h] [rbp-38h] BYREF
  int v29; // [rsp+D0h] [rbp-30h]
  struct winrt::impl::shared_hstring_header *v30; // [rsp+D8h] [rbp-28h] BYREF
  int v31; // [rsp+E0h] [rbp-20h]
  struct winrt::impl::shared_hstring_header *v32; // [rsp+E8h] [rbp-18h] BYREF
  int v33; // [rsp+F0h] [rbp-10h]
  struct winrt::impl::shared_hstring_header *v34; // [rsp+F8h] [rbp-8h] BYREF
  int v35; // [rsp+100h] [rbp+0h]
  struct winrt::impl::shared_hstring_header *v36; // [rsp+108h] [rbp+8h] BYREF
  int v37; // [rsp+110h] [rbp+10h]
  struct winrt::impl::shared_hstring_header *v38; // [rsp+118h] [rbp+18h] BYREF
  int v39; // [rsp+120h] [rbp+20h]
  struct winrt::impl::shared_hstring_header *v40; // [rsp+128h] [rbp+28h] BYREF
  int v41; // [rsp+130h] [rbp+30h]
  struct winrt::impl::shared_hstring_header *v42; // [rsp+138h] [rbp+38h] BYREF
  int v43; // [rsp+140h] [rbp+40h]
  struct winrt::impl::shared_hstring_header *v44; // [rsp+148h] [rbp+48h] BYREF
  int v45; // [rsp+150h] [rbp+50h]
  struct winrt::impl::shared_hstring_header *v46; // [rsp+158h] [rbp+58h] BYREF
  int v47; // [rsp+160h] [rbp+60h]
  struct winrt::impl::shared_hstring_header *v48; // [rsp+168h] [rbp+68h] BYREF
  int v49; // [rsp+170h] [rbp+70h]
  struct winrt::impl::shared_hstring_header *v50; // [rsp+178h] [rbp+78h] BYREF
  int v51; // [rsp+180h] [rbp+80h]
  struct winrt::impl::shared_hstring_header *v52; // [rsp+188h] [rbp+88h] BYREF
  int v53; // [rsp+190h] [rbp+90h]
  struct winrt::impl::shared_hstring_header *v54; // [rsp+198h] [rbp+98h] BYREF
  char v55; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v56; // [rsp+1B0h] [rbp+B0h]
  _BYTE v57[24]; // [rsp+1B8h] [rbp+B8h] BYREF

  v11 = 0;
  v8 = L"Microsoft.Graphics.Imaging.DepthMapCreator";
  v9 = 42;
  winrt::hstring::hstring(&v12, (__int64)&v8);
  v13 = 1;
  v8 = L"Microsoft.Windows.AI.ContentModeration.ImageContentModeration";
  v9 = 61;
  winrt::hstring::hstring(&v14, (__int64)&v8);
  v15 = 2;
  v8 = L"Microsoft.Graphics.Imaging.ImageSegmenter";
  v9 = 41;
  winrt::hstring::hstring(&v16, (__int64)&v8);
  v17 = 19;
  v8 = L"Microsoft.Graphics.Imaging.ImageObjectExtractor";
  v9 = 47;
  winrt::hstring::hstring(&v18, (__int64)&v8);
  v19 = 3;
  v8 = L"Microsoft.Graphics.Imaging.TrimapImageSegmenter";
  v9 = 47;
  winrt::hstring::hstring(&v20, (__int64)&v8);
  v21 = 4;
  v8 = L"Microsoft.Graphics.Imaging.ParallaxCreator";
  v9 = 42;
  winrt::hstring::hstring(&v22, (__int64)&v8);
  v23 = 5;
  v8 = L"Microsoft.Graphics.Imaging.ImageScaler";
  v9 = 38;
  winrt::hstring::hstring(&v24, (__int64)&v8);
  v25 = 20;
  v8 = L"Microsoft.Graphics.Imaging.ImageObjectRemover";
  v9 = 45;
  winrt::hstring::hstring(&v26, (__int64)&v8);
  v27 = 6;
  v8 = L"Microsoft.Windows.SemanticSearch.ImageSearchEmbeddingsCreator+Image";
  v9 = 67;
  winrt::hstring::hstring(&v28, (__int64)&v8);
  v29 = 7;
  v8 = L"Microsoft.Windows.SemanticSearch.ImageSearchEmbeddingsCreator+Text";
  v9 = 66;
  winrt::hstring::hstring(&v30, (__int64)&v8);
  v31 = 8;
  v8 = L"Microsoft.Windows.SemanticSearch.QueryBlockList";
  v9 = 47;
  winrt::hstring::hstring(&v32, (__int64)&v8);
  v33 = 9;
  v8 = L"Microsoft.Windows.SemanticSearch.QueryProcessor";
  v9 = 47;
  winrt::hstring::hstring(&v34, (__int64)&v8);
  v35 = 10;
  v8 = L"Microsoft.Windows.SemanticSearch.LocalSkillsRetriever";
  v9 = 53;
  winrt::hstring::hstring(&v36, (__int64)&v8);
  v37 = 11;
  v8 = L"Microsoft.Windows.SemanticSearch.SemanticTextEmbeddingsCreator";
  v9 = 62;
  winrt::hstring::hstring(&v38, (__int64)&v8);
  v39 = 12;
  v8 = L"Microsoft.Windows.Vision.ScreenRegionDetector";
  v9 = 45;
  winrt::hstring::hstring(&v40, (__int64)&v8);
  v41 = 13;
  v8 = L"Microsoft.Windows.Vision.TextRecognizer";
  v9 = 39;
  winrt::hstring::hstring(&v42, (__int64)&v8);
  v43 = 14;
  v8 = L"Microsoft.Windows.SemanticSearch.NamedEntityRecognitionRetriever";
  v9 = 64;
  winrt::hstring::hstring(&v44, (__int64)&v8);
  v45 = 15;
  v8 = L"Microsoft.Windows.SemanticSearch.TopicProcessor";
  v9 = 47;
  winrt::hstring::hstring(&v46, (__int64)&v8);
  v47 = 21;
  v8 = L"Microsoft.Windows.AI.Generative.ImageLLMAdapterCreator";
  v9 = 54;
  winrt::hstring::hstring(&v48, (__int64)&v8);
  v49 = 16;
  v8 = L"Microsoft.Windows.AI.Generative.LanguageModel";
  v9 = 45;
  winrt::hstring::hstring(&v50, (__int64)&v8);
  v51 = 17;
  v8 = L"Microsoft.Windows.AI.ContentModeration.TextContentModeration";
  v9 = 60;
  winrt::hstring::hstring(&v52, (__int64)&v8);
  v53 = 18;
  v8 = L"Microsoft.Windows.ImageCreation.ImageGenerator";
  v9 = 46;
  winrt::hstring::hstring(&v54, (__int64)&v8);
  qword_180059D50 = 0;
  qword_180059D58 = 0;
  v1 = operator new(0x30u);
  *v1 = v1;
  v1[1] = v1;
  v1[2] = v1;
  *((_WORD *)v1 + 12) = 257;
  qword_180059D50 = v1;
  v2 = (winrt::impl **)&v11;
  do
  {
    v3 = std::_Tree<std::_Tmap_traits<enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind,winrt::hstring,std::less<enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind>,std::allocator<std::pair<enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind const,winrt::hstring>>,0>>::_Find_hint<enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind>(
           v0,
           v57,
           v1,
           v2);
    v10 = *(_OWORD *)v3;
    v56 = *(_QWORD *)(v3 + 16);
    if ( !(_BYTE)v56 )
    {
      if ( qword_180059D58 == 0x555555555555555LL )
        std::_Throw_tree_length_error();
      v4 = qword_180059D50;
      v8 = (const wchar_t *)&qword_180059D50;
      v9 = 0;
      v5 = operator new(0x30u);
      v9 = (__int64)v5;
      v5[8] = *(_DWORD *)v2;
      *((_QWORD *)v5 + 5) = winrt::impl::duplicate_hstring(v2[1], v6);
      *(_QWORD *)v5 = v4;
      *((_QWORD *)v5 + 1) = v4;
      *((_QWORD *)v5 + 2) = v4;
      *((_WORD *)v5 + 12) = 0;
      v9 = 0;
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>>>::_Insert_node(
        &qword_180059D50,
        (__int64)&v10,
        (__int64)v5);
    }
    v2 += 2;
  }
  while ( v2 != (winrt::impl **)&v55 );
  `eh vector destructor iterator'(
    &v11,
    0x10u,
    0x16u,
    (void (*)(void *))std::pair<enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind const,winrt::hstring>::~pair<enum winrt::Microsoft::Windows::Workloads::Internal::ModelKind const,winrt::hstring>);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__s_modelKindToApiClassName__);
}

```

## disassembly

```asm
0x180001dc0  mov     [rsp-8+arg_0], rbx
0x180001dc5  mov     [rsp-8+arg_8], rsi
0x180001dca  mov     [rsp-8+arg_10], rdi
0x180001dcf  push    rbp
0x180001dd0  push    r12
0x180001dd2  push    r13
0x180001dd4  push    r14
0x180001dd6  push    r15
0x180001dd8  lea     rbp, [rsp-0D0h]
0x180001de0  sub     rsp, 1D0h
0x180001de7  xor     r15d, r15d
0x180001dea  mov     [rsp+1F0h+var_1B0], r15d
0x180001def  lea     rax, aMicrosoftGraph_4; "Microsoft.Graphics.Imaging.DepthMapCrea"...
0x180001df6  mov     [rsp+1F0h+var_1D0], rax
0x180001dfb  mov     [rsp+1F0h+var_1C8], 2Ah ; '*'
0x180001e04  lea     rdx, [rsp+1F0h+var_1D0]
0x180001e09  lea     rcx, [rsp+1F0h+var_1A8]
0x180001e0e  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180001e13  nop
0x180001e14  mov     [rsp+1F0h+var_1A0], 1
0x180001e1c  lea     rax, aMicrosoftWindo_17; "Microsoft.Windows.AI.ContentModeration."...
0x180001e23  mov     [rsp+1F0h+var_1D0], rax
0x180001e28  mov     [rsp+1F0h+var_1C8], 3Dh ; '='
0x180001e31  lea     rdx, [rsp+1F0h+var_1D0]
0x180001e36  lea     rcx, [rsp+1F0h+var_198]
0x180001e3b  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180001e40  nop
0x180001e41  mov     [rsp+1F0h+var_190], 2
0x180001e49  lea     rax, aMicrosoftGraph_2; "Microsoft.Graphics.Imaging.ImageSegment"...
0x180001e50  mov     [rsp+1F0h+var_1D0], rax
0x180001e55  mov     [rsp+1F0h+var_1C8], 29h ; ')'
0x180001e5e  lea     rdx, [rsp+1F0h+var_1D0]
0x180001e63  lea     rcx, [rsp+1F0h+var_188]
0x180001e68  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180001e6d  nop
0x180001e6e  mov     [rsp+1F0h+var_180], 13h
0x180001e76  lea     rax, aMicrosoftGraph_3; "Microsoft.Graphics.Imaging.ImageObjectE"...
0x180001e7d  mov     [rsp+1F0h+var_1D0], rax
0x180001e82  mov     [rsp+1F0h+var_1C8], 2Fh ; '/'
0x180001e8b  lea     rdx, [rsp+1F0h+var_1D0]
0x180001e90  lea     rcx, [rsp+1F0h+var_178]
0x180001e95  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180001e9a  nop
0x180001e9b  mov     [rbp+0F0h+var_170], 3
0x180001ea2  lea     rax, aMicrosoftGraph_1; "Microsoft.Graphics.Imaging.TrimapImageS"...
0x180001ea9  mov     [rsp+1F0h+var_1D0], rax
0x180001eae  mov     [rsp+1F0h+var_1C8], 2Fh ; '/'
0x180001eb7  lea     rdx, [rsp+1F0h+var_1D0]
0x180001ebc  lea     rcx, [rbp+0F0h+var_168]
0x180001ec0  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180001ec5  nop
0x180001ec6  mov     [rbp+0F0h+var_160], 4
0x180001ecd  lea     rax, aMicrosoftGraph; "Microsoft.Graphics.Imaging.ParallaxCrea"...
0x180001ed4  mov     [rsp+1F0h+var_1D0], rax
0x180001ed9  mov     [rsp+1F0h+var_1C8], 2Ah ; '*'
0x180001ee2  lea     rdx, [rsp+1F0h+var_1D0]
0x180001ee7  lea     rcx, [rbp+0F0h+var_158]
0x180001eeb  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180001ef0  nop
0x180001ef1  mov     [rbp+0F0h+var_150], 5
0x180001ef8  lea     rax, aMicrosoftGraph_5; "Microsoft.Graphics.Imaging.ImageScaler"
0x180001eff  mov     [rsp+1F0h+var_1D0], rax
0x180001f04  mov     [rsp+1F0h+var_1C8], 26h ; '&'
0x180001f0d  lea     rdx, [rsp+1F0h+var_1D0]
0x180001f12  lea     rcx, [rbp+0F0h+var_148]
0x180001f16  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180001f1b  nop
0x180001f1c  mov     [rbp+0F0h+var_140], 14h
0x180001f23  lea     rax, aMicrosoftGraph_0; "Microsoft.Graphics.Imaging.ImageObjectR"...
0x180001f2a  mov     [rsp+1F0h+var_1D0], rax
0x180001f2f  mov     [rsp+1F0h+var_1C8], 2Dh ; '-'
0x180001f38  lea     rdx, [rsp+1F0h+var_1D0]
0x180001f3d  lea     rcx, [rbp+0F0h+var_138]
0x180001f41  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180001f46  nop
0x180001f47  mov     [rbp+0F0h+var_130], 6
0x180001f4e  lea     rax, aMicrosoftWindo_15; "Microsoft.Windows.SemanticSearch.ImageS"...
0x180001f55  mov     [rsp+1F0h+var_1D0], rax
0x180001f5a  mov     [rsp+1F0h+var_1C8], 43h ; 'C'
0x180001f63  lea     rdx, [rsp+1F0h+var_1D0]
0x180001f68  lea     rcx, [rbp+0F0h+var_128]
0x180001f6c  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180001f71  nop
0x180001f72  mov     [rbp+0F0h+var_120], 7
0x180001f79  lea     rax, aMicrosoftWindo_23; "Microsoft.Windows.SemanticSearch.ImageS"...
0x180001f80  mov     [rsp+1F0h+var_1D0], rax
0x180001f85  mov     [rsp+1F0h+var_1C8], 42h ; 'B'
0x180001f8e  lea     rdx, [rsp+1F0h+var_1D0]
0x180001f93  lea     rcx, [rbp+0F0h+var_118]
0x180001f97  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180001f9c  nop
0x180001f9d  mov     [rbp+0F0h+var_110], 8
0x180001fa4  lea     rax, aMicrosoftWindo_25; "Microsoft.Windows.SemanticSearch.QueryB"...
0x180001fab  mov     [rsp+1F0h+var_1D0], rax
0x180001fb0  mov     [rsp+1F0h+var_1C8], 2Fh ; '/'
0x180001fb9  lea     rdx, [rsp+1F0h+var_1D0]
0x180001fbe  lea     rcx, [rbp+0F0h+var_108]
0x180001fc2  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180001fc7  nop
0x180001fc8  mov     [rbp+0F0h+var_100], 9
0x180001fcf  lea     rax, aMicrosoftWindo_7; "Microsoft.Windows.SemanticSearch.QueryP"...
0x180001fd6  mov     [rsp+1F0h+var_1D0], rax
0x180001fdb  mov     [rsp+1F0h+var_1C8], 2Fh ; '/'
0x180001fe4  lea     rdx, [rsp+1F0h+var_1D0]
0x180001fe9  lea     rcx, [rbp+0F0h+var_F8]
0x180001fed  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180001ff2  nop
0x180001ff3  mov     [rbp+0F0h+var_F0], 0Ah
0x180001ffa  lea     rax, aMicrosoftWindo_12; "Microsoft.Windows.SemanticSearch.LocalS"...
0x180002001  mov     [rsp+1F0h+var_1D0], rax
0x180002006  mov     [rsp+1F0h+var_1C8], 35h ; '5'
0x18000200f  lea     rdx, [rsp+1F0h+var_1D0]
0x180002014  lea     rcx, [rbp+0F0h+var_E8]
0x180002018  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x18000201d  nop
0x18000201e  mov     [rbp+0F0h+var_E0], 0Bh
0x180002025  lea     rax, aMicrosoftWindo_24; "Microsoft.Windows.SemanticSearch.Semant"...
0x18000202c  mov     [rsp+1F0h+var_1D0], rax
0x180002031  mov     [rsp+1F0h+var_1C8], 3Eh ; '>'
0x18000203a  lea     rdx, [rsp+1F0h+var_1D0]
0x18000203f  lea     rcx, [rbp+0F0h+var_D8]
0x180002043  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180002048  nop
0x180002049  mov     [rbp+0F0h+var_D0], 0Ch
0x180002050  lea     rax, aMicrosoftWindo_20; "Microsoft.Windows.Vision.ScreenRegionDe"...
0x180002057  mov     [rsp+1F0h+var_1D0], rax
0x18000205c  mov     [rsp+1F0h+var_1C8], 2Dh ; '-'
0x180002065  lea     rdx, [rsp+1F0h+var_1D0]
0x18000206a  lea     rcx, [rbp+0F0h+var_C8]
0x18000206e  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x180002073  nop
0x180002074  mov     [rbp+0F0h+var_C0], 0Dh
0x18000207b  lea     rax, aMicrosoftWindo_28; "Microsoft.Windows.Vision.TextRecognizer"
0x180002082  mov     [rsp+1F0h+var_1D0], rax
0x180002087  mov     [rsp+1F0h+var_1C8], 27h ; '''
0x180002090  lea     rdx, [rsp+1F0h+var_1D0]
0x180002095  lea     rcx, [rbp+0F0h+var_B8]
0x180002099  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x18000209e  nop
0x18000209f  mov     [rbp+0F0h+var_B0], 0Eh
0x1800020a6  lea     rax, aMicrosoftWindo_27; "Microsoft.Windows.SemanticSearch.NamedE"...
0x1800020ad  mov     [rsp+1F0h+var_1D0], rax
0x1800020b2  mov     [rsp+1F0h+var_1C8], 40h ; '@'
0x1800020bb  lea     rdx, [rsp+1F0h+var_1D0]
0x1800020c0  lea     rcx, [rbp+0F0h+var_A8]
0x1800020c4  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x1800020c9  nop
0x1800020ca  mov     [rbp+0F0h+var_A0], 0Fh
0x1800020d1  lea     rax, aMicrosoftWindo_9; "Microsoft.Windows.SemanticSearch.TopicP"...
0x1800020d8  mov     [rsp+1F0h+var_1D0], rax
0x1800020dd  mov     [rsp+1F0h+var_1C8], 2Fh ; '/'
0x1800020e6  lea     rdx, [rsp+1F0h+var_1D0]
0x1800020eb  lea     rcx, [rbp+0F0h+var_98]
0x1800020ef  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x1800020f4  nop
0x1800020f5  mov     [rbp+0F0h+var_90], 15h
0x1800020fc  lea     rax, aMicrosoftWindo_10; "Microsoft.Windows.AI.Generative.ImageLL"...
0x180002103  mov     [rsp+1F0h+var_1D0], rax
0x180002108  mov     [rsp+1F0h+var_1C8], 36h ; '6'
0x180002111  lea     rdx, [rsp+1F0h+var_1D0]
0x180002116  lea     rcx, [rbp+0F0h+var_88]
0x18000211a  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x18000211f  nop
0x180002120  mov     [rbp+0F0h+var_80], 10h
0x180002127  lea     rax, aMicrosoftWindo_4; "Microsoft.Windows.AI.Generative.Languag"...
0x18000212e  mov     [rsp+1F0h+var_1D0], rax
0x180002133  mov     [rsp+1F0h+var_1C8], 2Dh ; '-'
0x18000213c  lea     rdx, [rsp+1F0h+var_1D0]
0x180002141  lea     rcx, [rbp+0F0h+var_78]
0x180002145  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x18000214a  nop
0x18000214b  mov     [rbp+0F0h+var_70], 11h
0x180002155  lea     rax, aMicrosoftWindo_18; "Microsoft.Windows.AI.ContentModeration."...
0x18000215c  mov     [rsp+1F0h+var_1D0], rax
0x180002161  mov     [rsp+1F0h+var_1C8], 3Ch ; '<'
0x18000216a  lea     rdx, [rsp+1F0h+var_1D0]
0x18000216f  lea     rcx, [rbp+0F0h+var_68]
0x180002176  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x18000217b  nop
0x18000217c  mov     [rbp+0F0h+var_60], 12h
0x180002186  lea     rax, aMicrosoftWindo_8; "Microsoft.Windows.ImageCreation.ImageGe"...
0x18000218d  mov     [rsp+1F0h+var_1D0], rax
0x180002192  mov     [rsp+1F0h+var_1C8], 2Eh ; '.'
0x18000219b  lea     rdx, [rsp+1F0h+var_1D0]
0x1800021a0  lea     rcx, [rbp+0F0h+var_58]
0x1800021a7  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x1800021ac  nop
0x1800021ad  mov     cs:qword_180059D50, r15
0x1800021b4  mov     cs:qword_180059D58, r15
0x1800021bb  mov     ecx, 30h ; '0'; Size
0x1800021c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800021c5  mov     r14, rax
0x1800021c8  mov     [rax], rax
0x1800021cb  mov     [rax+8], rax
0x1800021cf  mov     [rax+10h], rax
0x1800021d3  mov     word ptr [rax+18h], 101h
0x1800021d9  mov     cs:qword_180059D50, rax
0x1800021e0  lea     rbx, [rsp+1F0h+var_1B0]
0x1800021e5  mov     r13, 555555555555555h
0x1800021ef  lea     r12, qword_180059D50
0x1800021f6  nop     word ptr [rax+rax+00000000h]
0x180002200  mov     r9, rbx
0x180002203  mov     r8, r14
0x180002206  lea     rdx, [rbp+0F0h+var_38]
0x18000220d  call    ??$_Find_hint@W4ModelKind@Internal@Workloads@Windows@Microsoft@winrt@@@?$_Tree@V?$_Tmap_traits@W4ModelKind@Internal@Workloads@Windows@Microsoft@winrt@@Uhstring@6@U?$less@W4ModelKind@Internal@Workloads@Windows@Microsoft@winrt@@@std@@V?$allocator@U?$pair@$$CBW4ModelKind@Internal@Workloads@Windows@Microsoft@winrt@@Uhstring@6@@std@@@9@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@U?$pair@$$CBW4ModelKind@Internal@Workloads@Windows@Microsoft@winrt@@Uhstring@6@@std@@PEAX@std@@@1@QEAU?$_Tree_node@U?$pair@$$CBW4ModelKind@Internal@Workloads@Windows@Microsoft@winrt@@Uhstring@6@@std@@PEAX@1@AEBW4ModelKind@Internal@Workloads@Windows@Microsoft@winrt@@@Z; std::_Tree<std::_Tmap_traits<winrt::Microsoft::Windows::Workloads::Internal::ModelKind,winrt::hstring,std::less<winrt::Microsoft::Windows::Workloads::Internal::ModelKind>,std::allocator<std::pair<winrt::Microsoft::Windows::Workloads::Internal::ModelKind const,winrt::hstring>>,0>>::_Find_hint<winrt::Microsoft::Windows::Workloads::Internal::ModelKind>(std::_Tree_node<std::pair<winrt::Microsoft::Windows::Workloads::Internal::ModelKind const,winrt::hstring>,void *> * const,winrt::Microsoft::Windows::Workloads::Internal::ModelKind const &)
0x180002212  movups  xmm0, xmmword ptr [rax]
0x180002215  movups  [rsp+1F0h+var_1C0], xmm0
0x18000221a  movsd   xmm0, qword ptr [rax+10h]
0x18000221f  movsd   [rbp+0F0h+var_40], xmm0
0x180002227  cmp     byte ptr [rbp+0F0h+var_40], 0
0x18000222e  jnz     short loc_1800022A2
0x180002230  cmp     cs:qword_180059D58, r13
0x180002237  jz      loc_1800022FE
0x18000223d  mov     rdi, cs:qword_180059D50
0x180002244  mov     [rsp+1F0h+var_1D0], r12
0x180002249  mov     [rsp+1F0h+var_1C8], r15
0x18000224e  mov     ecx, 30h ; '0'; Size
0x180002253  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002258  mov     rsi, rax
0x18000225b  mov     [rsp+1F0h+var_1C8], rax
0x180002260  mov     ecx, [rbx]
0x180002262  mov     [rax+20h], ecx
0x180002265  mov     rcx, [rbx+8]; this
0x180002269  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000226e  mov     [rsi+28h], rax
0x180002272  mov     [rsi], rdi
0x180002275  mov     [rsi+8], rdi
0x180002279  mov     [rsi+10h], rdi
0x18000227d  mov     word ptr [rsi+18h], 0
0x180002283  mov     [rsp+1F0h+var_1C8], r15
0x180002288  movups  xmm0, [rsp+1F0h+var_1C0]
0x18000228d  movaps  [rsp+1F0h+var_1C0], xmm0
0x180002292  mov     r8, rsi
0x180002295  lea     rdx, [rsp+1F0h+var_1C0]
0x18000229a  mov     rcx, r12
0x18000229d  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>,void *> * const)
0x1800022a2  add     rbx, 10h
0x1800022a6  lea     rax, [rbp+0F0h+var_50]
0x1800022ad  cmp     rbx, rax
0x1800022b0  jnz     loc_180002200
0x1800022b6  lea     r9, ??1?$pair@$$CBW4ModelKind@Internal@Workloads@Windows@Microsoft@winrt@@Uhstring@6@@std@@QEAA@XZ; void (*)(void *)
0x1800022bd  mov     edx, 10h; unsigned __int64
0x1800022c2  mov     r8d, 16h; unsigned __int64
0x1800022c8  lea     rcx, [rsp+1F0h+var_1B0]; void *
0x1800022cd  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800022d2  lea     rcx, _dynamic_atexit_destructor_for__s_modelKindToApiClassName__
0x1800022d9  lea     r11, [rsp+1F0h+var_20]
0x1800022e1  mov     rbx, [r11+30h]
0x1800022e5  mov     rsi, [r11+38h]
0x1800022e9  mov     rdi, [r11+40h]
0x1800022ed  mov     rsp, r11
0x1800022f0  pop     r15
0x1800022f2  pop     r14
0x1800022f4  pop     r13
0x1800022f6  pop     r12
0x1800022f8  pop     rbp
0x1800022f9  jmp     atexit
0x1800022fe  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
