# _anonymous_namespace_::get_image_features

- ea: `0x1400454ac`
- end: `0x1400459d9`
- name: `_anonymous_namespace_::get_image_features`
- size: `1325`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400459e0`

## callees

- `0x1400030a0`
- `0x140005ec8`
- `0x140005f10`
- `0x14000b5c4`
- `0x14000cc34`
- `0x14000d1d4`
- `0x1400158a8`
- `0x14001aff0`
- `0x14002cba0`
- `0x140033df0`
- `0x14003a168`
- `0x14003a1fc`
- `0x14003a2f0`
- `0x140043428`
- `0x1400436b0`
- `0x140043a54`
- `0x140043ac4`
- `0x140043b20`
- `0x140043d84`
- `0x14004433c`
- `0x14004501c`
- `0x140045184`
- `0x1400451c4`
- `0x1400454ac`
- `0x14004f010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140045748`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140045874`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140045748`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x140045874`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1400455f2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14004578e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1400455f2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14004578e`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x140045681`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1400457e2`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x140045681`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1400457e2`

## string_xrefs

- `0x1400455cf`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`
- `0x14004598c`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`
- `0x1400459c7`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall anonymous_namespace_::get_image_features(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *Src,
        __int64 a6)
{
  SAFEARRAY *v10; // rbx
  unsigned int UBound; // eax
  _QWORD *v12; // rcx
  _WORD *v13; // rcx
  unsigned int Element; // eax
  void *v15; // rax
  __int64 v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rax
  unsigned int v21; // eax
  __int64 v22; // rdi
  SAFEARRAY *v23; // rbx
  unsigned int v25; // eax
  unsigned int v26; // eax
  char *v27; // [rsp+28h] [rbp-D8h]
  char *v28; // [rsp+28h] [rbp-D8h]
  char *v29; // [rsp+28h] [rbp-D8h]
  char *v30; // [rsp+28h] [rbp-D8h]
  LONG plUbound; // [rsp+50h] [rbp-B0h] BYREF
  LONG rgIndices; // [rsp+54h] [rbp-ACh] BYREF
  SAFEARRAY *v33; // [rsp+58h] [rbp-A8h] BYREF
  __int64 pv; // [rsp+60h] [rbp-A0h] BYREF
  SAFEARRAY *psa; // [rsp+68h] [rbp-98h] BYREF
  char v36[16]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v37; // [rsp+80h] [rbp-80h]
  __int64 v38; // [rsp+98h] [rbp-68h]
  _BYTE v39[56]; // [rsp+A0h] [rbp-60h] BYREF
  SAFEARRAY *v40; // [rsp+D8h] [rbp-28h]
  _DWORD v41[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v42[4]; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v43[2]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v38 = -2;
  *(_OWORD *)v36 = 0;
  v37 = 0;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>>(v39);
  v10 = v40;
  v33 = v40;
  if ( v40 )
    _InterlockedIncrement((volatile signed __int32 *)&v40[9].cLocks);
  tip2::details::shared_data<0,0,0>::begin_update((__int64)&v10->cLocks);
  HIDWORD(v10[8].pvData) = 10;
  tip2::test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::~test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>(&v33);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_48532826>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl'::`2'::impl);
    v41[0] = 1000;
    v41[1] = 1000;
    v41[2] = 1000;
    psa = 0;
    v33 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int64, _DWORD *, char *, SAFEARRAY **, SAFEARRAY **))(*(_QWORD *)a2 + 56LL))(
           a2,
           a4,
           a3,
           3,
           v41,
           v36,
           &psa,
           &v33) < 0 )
    {
      SemanticSearchTelemetryAggregated::ReportSemanticRequeueRequested(0);
      v25 = wil::verify_hresult<long>(2147750438LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)v25,
        (int)"Failed to extract image properties.",
        v28);
    }
    if ( psa )
    {
      plUbound = 0;
      UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)UBound,
        (__int64)"Failed to get upper bound of OCR Lines array",
        v28);
      ++plUbound;
      if ( Src[3] <= 7u )
        v12 = Src;
      else
        v12 = (_QWORD *)*Src;
      if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v12, Src[2], &dword_140053AD4, 0) )
      {
        Src[2] = 0;
        if ( Src[3] <= 7u )
          v13 = Src;
        else
          v13 = (_WORD *)*Src;
        *v13 = 0;
      }
      for ( rgIndices = 0; rgIndices < plUbound; ++rgIndices )
      {
        pv = 0;
        Element = SafeArrayGetElement(psa, &rgIndices, &pv);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x71,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
          (const char *)Element,
          (__int64)"Failed to get element from OCR Lines array.",
          v29);
        v15 = (void *)std::wstring::wstring((__int64)v42, pv);
        v16 = std::wstring::_Append<wchar_t>(v15);
        v43[0] = *(_OWORD *)v16;
        v43[1] = *(_OWORD *)(v16 + 16);
        *(_QWORD *)(v16 + 16) = 0;
        *(_QWORD *)(v16 + 24) = 7;
        *(_WORD *)v16 = 0;
        std::wstring::_Append<wchar_t>(Src);
        std::wstring::_Tidy_deallocate((__int64)v43);
        std::wstring::_Tidy_deallocate((__int64)v42);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pv);
      }
      v17 = SafeArrayDestroy(psa);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)v17,
        (__int64)"Failed to destroy OCR Lines array.",
        v29);
    }
    if ( v33 )
    {
      plUbound = 0;
      v18 = SafeArrayGetUBound(v33, 1u, &plUbound);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)v18,
        (__int64)"Failed to get upper bound of imageCat array",
        v28);
      ++plUbound;
      for ( rgIndices = 0; rgIndices < plUbound; ++rgIndices )
      {
        LODWORD(pv) = 0;
        v19 = SafeArrayGetElement(v33, &rgIndices, &pv);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x81,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
          (const char *)v19,
          (__int64)"Failed to get element from imageCat array.",
          v30);
        v20 = CategoryEnumToString(v43, (unsigned int)pv);
        std::wstring::wstring(v42, v20);
        if ( *(_QWORD *)(a6 + 8) == *(_QWORD *)(a6 + 16) )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring &>(a6, *(_QWORD *)(a6 + 8), v42);
        }
        else
        {
          std::wstring::wstring(*(_QWORD *)(a6 + 8), v42);
          *(_QWORD *)(a6 + 8) += 32LL;
        }
        std::wstring::_Tidy_deallocate((__int64)v42);
      }
      v21 = SafeArrayDestroy(v33);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)v21,
        (__int64)"Failed to destroy imageCat array.",
        v30);
    }
  }
  else if ( (*(int (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)a2 + 64LL))(a2, a4, a3, v36) < 0 )
  {
    SemanticSearchTelemetryAggregated::ReportSemanticRequeueRequested(0);
    v26 = wil::verify_hresult<long>(2147750438LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
      (const char *)v26,
      (int)"Failed to extract image features.",
      v27);
  }
  if ( *(_DWORD *)v36 )
  {
    v22 = 0;
    if ( *(_DWORD *)v36 == 1 )
      v22 = (unsigned int)v37;
  }
  else
  {
    v22 = *(unsigned int *)&v36[4];
  }
  v23 = v40;
  v33 = v40;
  if ( v40 )
    _InterlockedIncrement((volatile signed __int32 *)&v40[9].cLocks);
  tip2::details::shared_data<0,0,0>::begin_update((__int64)&v23->cLocks);
  LOBYTE(v23[8].pvData) = v22 == 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::~test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>(&v33);
  tip2::details::shared_data<0,0,0>::complete_without_lock(&v40->cLocks);
  anonymous_namespace_::create_embedding(a1, v36);
  tip2::test_watcher<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::~test_watcher<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>(v39);
  FreeSemanticVector((struct tagSemanticVector *)v36);
  return a1;
}

```

## disassembly

```asm
0x1400454ac  push    rbp
0x1400454ae  push    rbx
0x1400454af  push    rsi
0x1400454b0  push    rdi
0x1400454b1  push    r12
0x1400454b3  push    r13
0x1400454b5  push    r14
0x1400454b7  push    r15
0x1400454b9  lea     rbp, [rsp-48h]
0x1400454be  sub     rsp, 148h
0x1400454c5  mov     [rbp+80h+var_E8], 0FFFFFFFFFFFFFFFEh
0x1400454cd  mov     rax, cs:__security_cookie
0x1400454d4  xor     rax, rsp
0x1400454d7  mov     [rbp+80h+var_50], rax
0x1400454db  mov     r13, r9
0x1400454de  mov     r12, r8
0x1400454e1  mov     r14, rdx
0x1400454e4  mov     r15, rcx
0x1400454e7  mov     rdi, [rbp+80h+Src]
0x1400454ee  mov     [rsp+180h+var_128], rcx
0x1400454f3  mov     rsi, [rbp+80h+arg_28]
0x1400454fa  xorps   xmm0, xmm0
0x1400454fd  movups  xmmword ptr [rsp+180h+var_110], xmm0
0x140045502  movups  [rbp+80h+var_100], xmm0
0x140045506  lea     rcx, [rbp+80h+var_E0]
0x14004550a  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x14004550f  nop
0x140045510  mov     rbx, [rbp+80h+var_A8]
0x140045514  mov     [rsp+180h+var_128], rbx
0x140045519  test    rbx, rbx
0x14004551c  jz      short loc_140045525
0x14004551e  lock inc dword ptr [rbx+128h]
0x140045525  lea     rcx, [rbx+8]
0x140045529  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x14004552e  mov     dword ptr [rbx+114h], 0Ah
0x140045538  lea     rcx, [rsp+180h+var_128]
0x14004553d  call    ??1?$test_data_control@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::~test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>(void)
0x140045542  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_48532826@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_48532826@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826> `wil::Feature<__WilFeatureTraits_Feature_48532826>::GetImpl(void)'::`2'::impl
0x140045549  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_48532826@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826>::__private_IsEnabled(void)
0x14004554e  test    al, al
0x140045550  jz      loc_1400458AB
0x140045556  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57180361@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361> `wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl(void)'::`2'::impl
0x14004555d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(void)
0x140045562  mov     eax, 3E8h
0x140045567  mov     [rbp+80h+var_A0], eax
0x14004556a  mov     [rbp+80h+var_9C], eax
0x14004556d  mov     [rbp+80h+var_98], eax
0x140045570  mov     [rsp+180h+psa], 0
0x140045579  mov     [rsp+180h+var_128], 0
0x140045582  mov     rax, [r14]
0x140045585  lea     rcx, [rsp+180h+var_128]
0x14004558a  mov     [rsp+180h+var_148], rcx
0x14004558f  lea     rcx, [rsp+180h+psa]
0x140045594  mov     [rsp+180h+var_150], rcx
0x140045599  lea     rcx, [rsp+180h+var_110]
0x14004559e  mov     [rsp+180h+var_158], rcx; char *
0x1400455a3  lea     rcx, [rbp+80h+var_A0]
0x1400455a7  mov     [rsp+180h+var_160], rcx
0x1400455ac  mov     r9d, 3
0x1400455b2  mov     r8, r12
0x1400455b5  mov     rdx, r13
0x1400455b8  mov     rcx, r14
0x1400455bb  mov     rax, [rax+38h]
0x1400455bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400455c4  xor     r14d, r14d
0x1400455c7  test    eax, eax
0x1400455c9  js      loc_140045963
0x1400455cf  lea     rbx, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400455d6  mov     rcx, [rsp+180h+psa]; psa
0x1400455db  test    rcx, rcx
0x1400455de  jz      loc_140045771
0x1400455e4  mov     [rsp+180h+plUbound], r14d
0x1400455e9  lea     r8, [rsp+180h+plUbound]; plUbound
0x1400455ee  lea     edx, [r14+1]; nDim
0x1400455f2  call    cs:__imp_SafeArrayGetUBound
0x1400455f8  mov     rcx, [rbp+88h]; this
0x1400455ff  lea     rdx, aFailedToGetUpp; "Failed to get upper bound of OCR Lines "...
0x140045606  mov     [rsp+180h+var_160], rdx; __int64
0x14004560b  mov     r9d, eax; char *
0x14004560e  mov     r8, rbx; unsigned int
0x140045611  lea     edx, [r14+68h]; void *
0x140045615  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14004561a  inc     [rsp+180h+plUbound]
0x14004561e  lea     r12d, [r14+7]
0x140045622  cmp     [rdi+18h], r12
0x140045626  jbe     short loc_14004562D
0x140045628  mov     rcx, [rdi]
0x14004562b  jmp     short loc_140045630
0x14004562d  mov     rcx, rdi
0x140045630  xor     r9d, r9d
0x140045633  lea     r8, dword_140053AD4
0x14004563a  mov     rdx, [rdi+10h]
0x14004563e  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x140045643  test    al, al
0x140045645  jnz     short loc_14004565D
0x140045647  mov     [rdi+10h], r14
0x14004564b  cmp     [rdi+18h], r12
0x14004564f  jbe     short loc_140045656
0x140045651  mov     rcx, [rdi]
0x140045654  jmp     short loc_140045659
0x140045656  mov     rcx, rdi
0x140045659  mov     [rcx], r14w
0x14004565d  mov     [rsp+180h+rgIndices], r14d
0x140045662  cmp     [rsp+180h+plUbound], r14d
0x140045667  jle     loc_140045743
0x14004566d  mov     [rsp+180h+pv], r14
0x140045672  lea     r8, [rsp+180h+pv]; pv
0x140045677  lea     rdx, [rsp+180h+rgIndices]; rgIndices
0x14004567c  mov     rcx, [rsp+180h+psa]; psa
0x140045681  call    cs:__imp_SafeArrayGetElement
0x140045687  mov     rcx, [rbp+88h]; this
0x14004568e  lea     rdx, aFailedToGetEle_0; "Failed to get element from OCR Lines ar"...
0x140045695  mov     [rsp+180h+var_160], rdx; __int64
0x14004569a  mov     r9d, eax; char *
0x14004569d  mov     r8, rbx; unsigned int
0x1400456a0  mov     edx, 71h ; 'q'; void *
0x1400456a5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1400456aa  mov     rdx, [rsp+180h+pv]
0x1400456af  lea     rcx, [rbp+80h+var_90]
0x1400456b3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400456b8  nop
0x1400456b9  mov     r8d, 1
0x1400456bf  lea     rdx, asc_140053C78; "\n"
0x1400456c6  mov     rcx, rax; Src
0x1400456c9  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1400456ce  movups  xmm0, xmmword ptr [rax]
0x1400456d1  movups  [rbp+80h+var_70], xmm0
0x1400456d5  movups  xmm1, xmmword ptr [rax+10h]
0x1400456d9  movups  [rbp+80h+var_60], xmm1
0x1400456dd  mov     [rax+10h], r14
0x1400456e1  mov     [rax+18h], r12
0x1400456e5  mov     [rax], r14w
0x1400456e9  movq    r8, xmm1
0x1400456ee  lea     rdx, [rbp+80h+var_70]
0x1400456f2  movq    rcx, xmm0
0x1400456f7  psrldq  xmm1, 8
0x1400456fc  movq    rax, xmm1
0x140045701  cmp     rax, r12
0x140045704  cmova   rdx, rcx
0x140045708  mov     rcx, rdi; Src
0x14004570b  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x140045710  nop
0x140045711  lea     rcx, [rbp+80h+var_70]
0x140045715  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14004571a  nop
0x14004571b  lea     rcx, [rbp+80h+var_90]
0x14004571f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140045724  nop
0x140045725  lea     rcx, [rsp+180h+pv]
0x14004572a  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x14004572f  mov     eax, [rsp+180h+rgIndices]
0x140045733  inc     eax
0x140045735  mov     [rsp+180h+rgIndices], eax
0x140045739  cmp     eax, [rsp+180h+plUbound]
0x14004573d  jl      loc_14004566D
0x140045743  mov     rcx, [rsp+180h+psa]; psa
0x140045748  call    cs:__imp_SafeArrayDestroy
0x14004574e  mov     rcx, [rbp+88h]; this
0x140045755  lea     rdx, aFailedToDestro; "Failed to destroy OCR Lines array."
0x14004575c  mov     [rsp+180h+var_160], rdx; __int64
0x140045761  mov     r9d, eax; char *
0x140045764  mov     r8, rbx; unsigned int
0x140045767  mov     edx, 74h ; 't'; void *
0x14004576c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x140045771  mov     rcx, [rsp+180h+var_128]; psa
0x140045776  test    rcx, rcx
0x140045779  jz      loc_14004589D
0x14004577f  mov     [rsp+180h+plUbound], r14d
0x140045784  lea     r8, [rsp+180h+plUbound]; plUbound
0x140045789  mov     edx, 1; nDim
0x14004578e  call    cs:__imp_SafeArrayGetUBound
0x140045794  mov     rcx, [rbp+88h]; this
0x14004579b  lea     rdx, aFailedToGetUpp_0; "Failed to get upper bound of imageCat a"...
0x1400457a2  mov     [rsp+180h+var_160], rdx; __int64
0x1400457a7  mov     r9d, eax; char *
0x1400457aa  mov     r8, rbx; unsigned int
0x1400457ad  mov     edx, 7Ah ; 'z'; void *
0x1400457b2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1400457b7  mov     eax, [rsp+180h+plUbound]
0x1400457bb  inc     eax
0x1400457bd  mov     [rsp+180h+plUbound], eax
0x1400457c1  mov     [rsp+180h+rgIndices], r14d
0x1400457c6  test    eax, eax
0x1400457c8  jle     loc_14004586F
0x1400457ce  mov     dword ptr [rsp+180h+pv], r14d
0x1400457d3  lea     r8, [rsp+180h+pv]; pv
0x1400457d8  lea     rdx, [rsp+180h+rgIndices]; rgIndices
0x1400457dd  mov     rcx, [rsp+180h+var_128]; psa
0x1400457e2  call    cs:__imp_SafeArrayGetElement
0x1400457e8  mov     rcx, [rbp+88h]; this
0x1400457ef  lea     rdx, aFailedToGetEle; "Failed to get element from imageCat arr"...
0x1400457f6  mov     [rsp+180h+var_160], rdx; __int64
0x1400457fb  mov     r9d, eax; char *
0x1400457fe  mov     r8, rbx; unsigned int
0x140045801  mov     edx, 81h; void *
0x140045806  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14004580b  mov     edx, dword ptr [rsp+180h+pv]
0x14004580f  lea     rcx, [rbp+80h+var_70]
0x140045813  call    ?CategoryEnumToString@@YA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@W4SearchImageCategory@@@Z; CategoryEnumToString(SearchImageCategory)
0x140045818  mov     rdx, rax
0x14004581b  lea     rcx, [rbp+80h+var_90]
0x14004581f  call    ??$?0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring_view const &,std::allocator<wchar_t> const &)
0x140045824  nop
0x140045825  mov     rax, [rsi+8]
0x140045829  cmp     rax, [rsi+10h]
0x14004582d  jz      short loc_140045842
0x14004582f  lea     rdx, [rbp+80h+var_90]
0x140045833  mov     rcx, rax
0x140045836  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14004583b  add     qword ptr [rsi+8], 20h ; ' '
0x140045840  jmp     short loc_140045852
0x140045842  lea     r8, [rbp+80h+var_90]
0x140045846  mov     rdx, rax
0x140045849  mov     rcx, rsi
0x14004584c  call    ??$_Emplace_reallocate@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring &>(std::wstring * const,std::wstring &)
0x140045851  nop
0x140045852  lea     rcx, [rbp+80h+var_90]
0x140045856  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14004585b  mov     eax, [rsp+180h+rgIndices]
0x14004585f  inc     eax
0x140045861  mov     [rsp+180h+rgIndices], eax
0x140045865  cmp     eax, [rsp+180h+plUbound]
0x140045869  jl      loc_1400457CE
0x14004586f  mov     rcx, [rsp+180h+var_128]; psa
0x140045874  call    cs:__imp_SafeArrayDestroy
0x14004587a  mov     rcx, [rbp+88h]; this
0x140045881  lea     rdx, aFailedToDestro_0; "Failed to destroy imageCat array."
0x140045888  mov     [rsp+180h+var_160], rdx; __int64
0x14004588d  mov     r9d, eax; char *
0x140045890  mov     r8, rbx; unsigned int
0x140045893  mov     edx, 88h; void *
0x140045898  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14004589d  mov     eax, dword ptr [rsp+180h+var_110]
0x1400458a1  test    eax, eax
0x1400458a3  jnz     short loc_1400458D2
0x1400458a5  mov     edi, dword ptr [rsp+180h+var_110+4]
0x1400458a9  jmp     short loc_1400458DD
0x1400458ab  mov     rax, [r14]
0x1400458ae  lea     r9, [rsp+180h+var_110]
0x1400458b3  mov     r8, r12
0x1400458b6  mov     rdx, r13
0x1400458b9  mov     rcx, r14
0x1400458bc  mov     rax, [rax+40h]
0x1400458c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400458c5  xor     r14d, r14d
0x1400458c8  test    eax, eax
0x1400458ca  js      loc_14004599E
0x1400458d0  jmp     short loc_14004589D
0x1400458d2  mov     rdi, r14
0x1400458d5  cmp     eax, 1
0x1400458d8  jnz     short loc_1400458DD
0x1400458da  mov     edi, dword ptr [rbp+80h+var_100]
0x1400458dd  mov     rbx, [rbp+80h+var_A8]
0x1400458e1  mov     [rsp+180h+var_128], rbx
0x1400458e6  test    rbx, rbx
0x1400458e9  jz      short loc_1400458F2
0x1400458eb  lock inc dword ptr [rbx+128h]
0x1400458f2  lea     rcx, [rbx+8]
0x1400458f6  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1400458fb  test    rdi, rdi
0x1400458fe  setz    al
0x140045901  mov     [rbx+110h], al
0x140045907  lea     rcx, [rsp+180h+var_128]
0x14004590c  call    ??1?$test_data_control@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::~test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>(void)
0x140045911  mov     rcx, [rbp+80h+var_A8]
0x140045915  add     rcx, 8
0x140045919  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x14004591e  lea     rdx, [rsp+180h+var_110]
0x140045923  mov     rcx, r15
0x140045926  call    _anonymous_namespace___create_embedding
0x14004592b  nop
0x14004592c  lea     rcx, [rbp+80h+var_E0]
0x140045930  call    ??1?$test_watcher@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::~test_watcher<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>(void)
0x140045935  nop
0x140045936  lea     rcx, [rsp+180h+var_110]; struct tagSemanticVector *
0x14004593b  call    ?FreeSemanticVector@@YAXPEAUtagSemanticVector@@@Z; FreeSemanticVector(tagSemanticVector *)
0x140045940  mov     rax, r15
0x140045943  mov     rcx, [rbp+80h+var_50]
0x140045947  xor     rcx, rsp; StackCookie
0x14004594a  call    __security_check_cookie
0x14004594f  add     rsp, 148h
0x140045956  pop     r15
0x140045958  pop     r14
0x14004595a  pop     r13
0x14004595c  pop     r12
0x14004595e  pop     rdi
0x14004595f  pop     rsi
0x140045960  pop     rbx
0x140045961  pop     rbp
0x140045962  retn
0x140045963  mov     edx, eax
0x140045965  xor     ecx, ecx
0x140045967  call    ?ReportSemanticRequeueRequested@SemanticSearchTelemetryAggregated@@SAXW4SemanticOperationType@@J@Z; SemanticSearchTelemetryAggregated::ReportSemanticRequeueRequested(SemanticOperationType,long)
0x14004596c  mov     ecx, 80041226h
0x140045971  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x140045976  mov     r9d, eax; char *
0x140045979  mov     rcx, [rbp+88h]; this
0x140045980  lea     rax, aFailedToExtrac; "Failed to extract image properties."
0x140045987  mov     [rsp+180h+var_160], rax; int
0x14004598c  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\search\\com"...
  ... truncated ...
```
