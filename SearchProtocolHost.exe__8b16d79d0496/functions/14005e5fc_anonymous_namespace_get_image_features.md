# _anonymous_namespace_::get_image_features

- ea: `0x14005e5fc`
- end: `0x14005eaf2`
- name: `_anonymous_namespace_::get_image_features`
- size: `1270`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14005eb00`

## callees

- `0x140005240`
- `0x1400072f4`
- `0x140009cf0`
- `0x14000b144`
- `0x14000c91c`
- `0x14000cca0`
- `0x14000cce4`
- `0x140025ad0`
- `0x14003376c`
- `0x1400511b0`
- `0x14005ad1c`
- `0x14005adb0`
- `0x14005af20`
- `0x14005af98`
- `0x14005c69c`
- `0x14005c850`
- `0x14005cbec`
- `0x14005cc5c`
- `0x14005ccb8`
- `0x14005ced4`
- `0x14005d48c`
- `0x14005e16c`
- `0x14005e2d4`
- `0x14005e314`
- `0x14005e5fc`
- `0x140070010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14005e865`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14005e98e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14005e865`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14005e98e`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14005e73f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14005e8aa`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14005e73f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14005e8aa`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x14005e7c8`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x14005e8fc`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x14005e7c8`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x14005e8fc`

## string_xrefs

- `0x14005e71e`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`
- `0x14005eaa5`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`
- `0x14005eae0`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`

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
  SAFEARRAY *v10; // rdi
  int v11; // eax
  unsigned int UBound; // eax
  _QWORD *v13; // rcx
  _WORD *v14; // rcx
  unsigned int Element; // eax
  __int64 v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rax
  unsigned int v21; // eax
  __int64 v22; // rdi
  int v23; // eax
  SAFEARRAY *v24; // rbx
  unsigned int v26; // eax
  unsigned int v27; // eax
  char *v28; // [rsp+28h] [rbp-D8h]
  char *v29; // [rsp+28h] [rbp-D8h]
  char *v30; // [rsp+28h] [rbp-D8h]
  char *v31; // [rsp+28h] [rbp-D8h]
  LONG plUbound; // [rsp+50h] [rbp-B0h] BYREF
  LONG rgIndices; // [rsp+54h] [rbp-ACh] BYREF
  SAFEARRAY *v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 pv; // [rsp+60h] [rbp-A0h] BYREF
  SAFEARRAY *psa; // [rsp+68h] [rbp-98h] BYREF
  char v37[16]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v38; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+98h] [rbp-68h]
  _BYTE v40[56]; // [rsp+A0h] [rbp-60h] BYREF
  SAFEARRAY *v41; // [rsp+D8h] [rbp-28h]
  _DWORD v42[4]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v43[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v44[32]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v39 = -2;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>>(v40);
  v10 = v41;
  v34 = v41;
  if ( v41 )
    _InterlockedIncrement((volatile signed __int32 *)&v41[9].cLocks);
  tip2::details::shared_data<0,0,0>::begin_update(&v10->cLocks);
  HIDWORD(v10[8].pvData) = 10;
  tip2::test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::~test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>(&v34);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_48532826>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl'::`2'::impl);
    v42[0] = 1000;
    v42[1] = 1000;
    v42[2] = 1000;
    psa = 0;
    v34 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, _DWORD *, char *, SAFEARRAY **, SAFEARRAY **))(*(_QWORD *)a2 + 56LL))(
            a2,
            a4,
            a3,
            3,
            v42,
            v37,
            &psa,
            &v34);
    if ( v11 < 0 )
    {
      SemanticSearchTelemetryAggregated::ReportSemanticRequeueRequested(0, (unsigned int)v11);
      v26 = wil::verify_hresult<long>(2147750438LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)v26,
        (int)"Failed to extract image properties.",
        v29);
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
        v29);
      ++plUbound;
      if ( Src[3] <= 7u )
        v13 = Src;
      else
        v13 = (_QWORD *)*Src;
      if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v13, Src[2], &dword_14007696C, 0) )
      {
        Src[2] = 0;
        if ( Src[3] <= 7u )
          v14 = Src;
        else
          v14 = (_WORD *)*Src;
        *v14 = 0;
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
          v30);
        v16 = std::wstring::wstring(v44, pv);
        std::operator+<wchar_t>(v43, v16, L"\n");
        std::wstring::_Append<wchar_t>(Src);
        std::wstring::_Tidy_deallocate(v43);
        std::wstring::_Tidy_deallocate(v44);
        wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pv);
      }
      v17 = SafeArrayDestroy(psa);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)v17,
        (__int64)"Failed to destroy OCR Lines array.",
        v30);
    }
    if ( v34 )
    {
      plUbound = 0;
      v18 = SafeArrayGetUBound(v34, 1u, &plUbound);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x7A,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)v18,
        (__int64)"Failed to get upper bound of imageCat array",
        v29);
      ++plUbound;
      for ( rgIndices = 0; rgIndices < plUbound; ++rgIndices )
      {
        LODWORD(pv) = 0;
        v19 = SafeArrayGetElement(v34, &rgIndices, &pv);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x81,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
          (const char *)v19,
          (__int64)"Failed to get element from imageCat array.",
          v31);
        v20 = CategoryEnumToString(v44, (unsigned int)pv);
        std::wstring::wstring(v43, v20);
        if ( *(_QWORD *)(a6 + 8) == *(_QWORD *)(a6 + 16) )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring &>(a6, *(_QWORD *)(a6 + 8), v43);
        }
        else
        {
          std::wstring::wstring(*(_QWORD *)(a6 + 8), v43);
          *(_QWORD *)(a6 + 8) += 32LL;
        }
        std::wstring::_Tidy_deallocate(v43);
      }
      v21 = SafeArrayDestroy(v34);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)v21,
        (__int64)"Failed to destroy imageCat array.",
        v31);
    }
  }
  else
  {
    v23 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, char *))(*(_QWORD *)a2 + 64LL))(a2, a4, a3, v37);
    if ( v23 < 0 )
    {
      SemanticSearchTelemetryAggregated::ReportSemanticRequeueRequested(0, (unsigned int)v23);
      v27 = wil::verify_hresult<long>(2147750438LL);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x93,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)v27,
        (int)"Failed to extract image features.",
        v28);
    }
  }
  if ( *(_DWORD *)v37 )
  {
    v22 = 0;
    if ( *(_DWORD *)v37 == 1 )
      v22 = (unsigned int)v38;
  }
  else
  {
    v22 = *(unsigned int *)&v37[4];
  }
  v24 = v41;
  v34 = v41;
  if ( v41 )
    _InterlockedIncrement((volatile signed __int32 *)&v41[9].cLocks);
  tip2::details::shared_data<0,0,0>::begin_update(&v24->cLocks);
  LOBYTE(v24[8].pvData) = v22 == 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::~test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>(&v34);
  tip2::details::shared_data<0,0,0>::complete_without_lock(&v41->cLocks);
  anonymous_namespace_::create_embedding(a1, v37);
  tip2::test_watcher<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::~test_watcher<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>(v40);
  FreeSemanticVector((struct tagSemanticVector *)v37);
  return a1;
}

```

## disassembly

```asm
0x14005e5fc  push    rbp
0x14005e5fe  push    rbx
0x14005e5ff  push    rsi
0x14005e600  push    rdi
0x14005e601  push    r12
0x14005e603  push    r13
0x14005e605  push    r14
0x14005e607  push    r15
0x14005e609  lea     rbp, [rsp-48h]
0x14005e60e  sub     rsp, 148h
0x14005e615  mov     [rbp+80h+var_E8], 0FFFFFFFFFFFFFFFEh
0x14005e61d  mov     rax, cs:__security_cookie
0x14005e624  xor     rax, rsp
0x14005e627  mov     [rbp+80h+var_50], rax
0x14005e62b  mov     r12, r9
0x14005e62e  mov     r15, r8
0x14005e631  mov     rsi, rdx
0x14005e634  mov     r13, rcx
0x14005e637  mov     rbx, [rbp+80h+Src]
0x14005e63e  mov     [rsp+180h+var_128], rcx
0x14005e643  mov     r14, [rbp+80h+arg_28]
0x14005e64a  xorps   xmm0, xmm0
0x14005e64d  movups  xmmword ptr [rsp+180h+var_110], xmm0
0x14005e652  movups  [rbp+80h+var_100], xmm0
0x14005e656  lea     rcx, [rbp+80h+var_E0]
0x14005e65a  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x14005e65f  nop
0x14005e660  mov     rdi, [rbp+80h+var_A8]
0x14005e664  mov     [rsp+180h+var_128], rdi
0x14005e669  test    rdi, rdi
0x14005e66c  jz      short loc_14005E675
0x14005e66e  lock inc dword ptr [rdi+128h]
0x14005e675  lea     rcx, [rdi+8]
0x14005e679  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x14005e67e  mov     dword ptr [rdi+114h], 0Ah
0x14005e688  lea     rcx, [rsp+180h+var_128]
0x14005e68d  call    ??1?$test_data_control@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::~test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>(void)
0x14005e692  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_48532826@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_48532826@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826> `wil::Feature<__WilFeatureTraits_Feature_48532826>::GetImpl(void)'::`2'::impl
0x14005e699  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_48532826@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_48532826>::__private_IsEnabled(void)
0x14005e69e  test    al, al
0x14005e6a0  jz      loc_14005E9C5
0x14005e6a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57180361@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361> `wil::Feature<__WilFeatureTraits_Feature_57180361>::GetImpl(void)'::`2'::impl
0x14005e6ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57180361@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57180361>::__private_IsEnabled(void)
0x14005e6b2  mov     eax, 3E8h
0x14005e6b7  mov     [rbp+80h+var_A0], eax
0x14005e6ba  mov     [rbp+80h+var_9C], eax
0x14005e6bd  mov     [rbp+80h+var_98], eax
0x14005e6c0  mov     [rsp+180h+psa], 0
0x14005e6c9  mov     [rsp+180h+var_128], 0
0x14005e6d2  mov     rax, [rsi]
0x14005e6d5  lea     rcx, [rsp+180h+var_128]
0x14005e6da  mov     [rsp+180h+var_148], rcx
0x14005e6df  lea     rcx, [rsp+180h+psa]
0x14005e6e4  mov     [rsp+180h+var_150], rcx
0x14005e6e9  lea     rcx, [rsp+180h+var_110]
0x14005e6ee  mov     [rsp+180h+var_158], rcx; char *
0x14005e6f3  lea     rcx, [rbp+80h+var_A0]
0x14005e6f7  mov     [rsp+180h+var_160], rcx
0x14005e6fc  mov     r9d, 3
0x14005e702  mov     r8, r15
0x14005e705  mov     rdx, r12
0x14005e708  mov     rcx, rsi
0x14005e70b  mov     rax, [rax+38h]
0x14005e70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005e714  xor     esi, esi
0x14005e716  test    eax, eax
0x14005e718  js      loc_14005EA7C
0x14005e71e  lea     rdi, aOnecoreuapBase_45; "onecoreuap\\base\\appmodel\\search\\com"...
0x14005e725  mov     rcx, [rsp+180h+psa]; psa
0x14005e72a  test    rcx, rcx
0x14005e72d  jz      loc_14005E88E
0x14005e733  mov     [rsp+180h+plUbound], esi
0x14005e737  lea     r8, [rsp+180h+plUbound]; plUbound
0x14005e73c  lea     edx, [rsi+1]; nDim
0x14005e73f  call    cs:__imp_SafeArrayGetUBound
0x14005e745  mov     rcx, [rbp+88h]; this
0x14005e74c  lea     rdx, aFailedToGetUpp; "Failed to get upper bound of OCR Lines "...
0x14005e753  mov     [rsp+180h+var_160], rdx; __int64
0x14005e758  mov     r9d, eax; char *
0x14005e75b  mov     r8, rdi; unsigned int
0x14005e75e  lea     edx, [rsi+68h]; void *
0x14005e761  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14005e766  inc     [rsp+180h+plUbound]
0x14005e76a  cmp     qword ptr [rbx+18h], 7
0x14005e76f  jbe     short loc_14005E776
0x14005e771  mov     rcx, [rbx]
0x14005e774  jmp     short loc_14005E779
0x14005e776  mov     rcx, rbx
0x14005e779  xor     r9d, r9d
0x14005e77c  lea     r8, dword_14007696C
0x14005e783  mov     rdx, [rbx+10h]
0x14005e787  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14005e78c  test    al, al
0x14005e78e  jnz     short loc_14005E7A6
0x14005e790  mov     [rbx+10h], rsi
0x14005e794  cmp     qword ptr [rbx+18h], 7
0x14005e799  jbe     short loc_14005E7A0
0x14005e79b  mov     rcx, [rbx]
0x14005e79e  jmp     short loc_14005E7A3
0x14005e7a0  mov     rcx, rbx
0x14005e7a3  mov     [rcx], si
0x14005e7a6  mov     [rsp+180h+rgIndices], esi
0x14005e7aa  cmp     [rsp+180h+plUbound], esi
0x14005e7ae  jle     loc_14005E860
0x14005e7b4  mov     [rsp+180h+pv], rsi
0x14005e7b9  lea     r8, [rsp+180h+pv]; pv
0x14005e7be  lea     rdx, [rsp+180h+rgIndices]; rgIndices
0x14005e7c3  mov     rcx, [rsp+180h+psa]; psa
0x14005e7c8  call    cs:__imp_SafeArrayGetElement
0x14005e7ce  mov     rcx, [rbp+88h]; this
0x14005e7d5  lea     rdx, aFailedToGetEle_0; "Failed to get element from OCR Lines ar"...
0x14005e7dc  mov     [rsp+180h+var_160], rdx; __int64
0x14005e7e1  mov     r9d, eax; char *
0x14005e7e4  mov     r8, rdi; unsigned int
0x14005e7e7  mov     edx, 71h ; 'q'; void *
0x14005e7ec  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14005e7f1  mov     rdx, [rsp+180h+pv]
0x14005e7f6  lea     rcx, [rbp+80h+var_70]
0x14005e7fa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14005e7ff  nop
0x14005e800  lea     r8, asc_140076B10; "\n"
0x14005e807  mov     rdx, rax
0x14005e80a  lea     rcx, [rbp+80h+var_90]
0x14005e80e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x14005e813  nop
0x14005e814  mov     r8, [rax+10h]
0x14005e818  cmp     qword ptr [rax+18h], 7
0x14005e81d  jbe     short loc_14005E822
0x14005e81f  mov     rax, [rax]
0x14005e822  mov     rdx, rax
0x14005e825  mov     rcx, rbx; Src
0x14005e828  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x14005e82d  nop
0x14005e82e  lea     rcx, [rbp+80h+var_90]
0x14005e832  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005e837  nop
0x14005e838  lea     rcx, [rbp+80h+var_70]
0x14005e83c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005e841  nop
0x14005e842  lea     rcx, [rsp+180h+pv]
0x14005e847  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x14005e84c  mov     eax, [rsp+180h+rgIndices]
0x14005e850  inc     eax
0x14005e852  mov     [rsp+180h+rgIndices], eax
0x14005e856  cmp     eax, [rsp+180h+plUbound]
0x14005e85a  jl      loc_14005E7B4
0x14005e860  mov     rcx, [rsp+180h+psa]; psa
0x14005e865  call    cs:__imp_SafeArrayDestroy
0x14005e86b  mov     rcx, [rbp+88h]; this
0x14005e872  lea     rdx, aFailedToDestro; "Failed to destroy OCR Lines array."
0x14005e879  mov     [rsp+180h+var_160], rdx; __int64
0x14005e87e  mov     r9d, eax; char *
0x14005e881  mov     r8, rdi; unsigned int
0x14005e884  mov     edx, 74h ; 't'; void *
0x14005e889  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14005e88e  mov     rcx, [rsp+180h+var_128]; psa
0x14005e893  test    rcx, rcx
0x14005e896  jz      loc_14005E9B7
0x14005e89c  mov     [rsp+180h+plUbound], esi
0x14005e8a0  lea     r8, [rsp+180h+plUbound]; plUbound
0x14005e8a5  mov     edx, 1; nDim
0x14005e8aa  call    cs:__imp_SafeArrayGetUBound
0x14005e8b0  mov     rcx, [rbp+88h]; this
0x14005e8b7  lea     rdx, aFailedToGetUpp_0; "Failed to get upper bound of imageCat a"...
0x14005e8be  mov     [rsp+180h+var_160], rdx; __int64
0x14005e8c3  mov     r9d, eax; char *
0x14005e8c6  mov     r8, rdi; unsigned int
0x14005e8c9  mov     edx, 7Ah ; 'z'; void *
0x14005e8ce  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14005e8d3  mov     eax, [rsp+180h+plUbound]
0x14005e8d7  inc     eax
0x14005e8d9  mov     [rsp+180h+plUbound], eax
0x14005e8dd  mov     [rsp+180h+rgIndices], esi
0x14005e8e1  test    eax, eax
0x14005e8e3  jle     loc_14005E989
0x14005e8e9  mov     dword ptr [rsp+180h+pv], esi
0x14005e8ed  lea     r8, [rsp+180h+pv]; pv
0x14005e8f2  lea     rdx, [rsp+180h+rgIndices]; rgIndices
0x14005e8f7  mov     rcx, [rsp+180h+var_128]; psa
0x14005e8fc  call    cs:__imp_SafeArrayGetElement
0x14005e902  mov     rcx, [rbp+88h]; this
0x14005e909  lea     rdx, aFailedToGetEle; "Failed to get element from imageCat arr"...
0x14005e910  mov     [rsp+180h+var_160], rdx; __int64
0x14005e915  mov     r9d, eax; char *
0x14005e918  mov     r8, rdi; unsigned int
0x14005e91b  mov     edx, 81h; void *
0x14005e920  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14005e925  mov     edx, dword ptr [rsp+180h+pv]
0x14005e929  lea     rcx, [rbp+80h+var_70]
0x14005e92d  call    ?CategoryEnumToString@@YA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@W4SearchImageCategory@@@Z; CategoryEnumToString(SearchImageCategory)
0x14005e932  mov     rdx, rax
0x14005e935  lea     rcx, [rbp+80h+var_90]
0x14005e939  call    ??$?0V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(std::wstring_view const &,std::allocator<wchar_t> const &)
0x14005e93e  nop
0x14005e93f  mov     rax, [r14+8]
0x14005e943  cmp     rax, [r14+10h]
0x14005e947  jz      short loc_14005E95C
0x14005e949  lea     rdx, [rbp+80h+var_90]
0x14005e94d  mov     rcx, rax
0x14005e950  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14005e955  add     qword ptr [r14+8], 20h ; ' '
0x14005e95a  jmp     short loc_14005E96C
0x14005e95c  lea     r8, [rbp+80h+var_90]
0x14005e960  mov     rdx, rax
0x14005e963  mov     rcx, r14
0x14005e966  call    ??$_Emplace_reallocate@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring &>(std::wstring * const,std::wstring &)
0x14005e96b  nop
0x14005e96c  lea     rcx, [rbp+80h+var_90]
0x14005e970  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14005e975  mov     eax, [rsp+180h+rgIndices]
0x14005e979  inc     eax
0x14005e97b  mov     [rsp+180h+rgIndices], eax
0x14005e97f  cmp     eax, [rsp+180h+plUbound]
0x14005e983  jl      loc_14005E8E9
0x14005e989  mov     rcx, [rsp+180h+var_128]; psa
0x14005e98e  call    cs:__imp_SafeArrayDestroy
0x14005e994  mov     rcx, [rbp+88h]; this
0x14005e99b  lea     rdx, aFailedToDestro_0; "Failed to destroy imageCat array."
0x14005e9a2  mov     [rsp+180h+var_160], rdx; __int64
0x14005e9a7  mov     r9d, eax; char *
0x14005e9aa  mov     r8, rdi; unsigned int
0x14005e9ad  mov     edx, 88h; void *
0x14005e9b2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14005e9b7  mov     eax, dword ptr [rsp+180h+var_110]
0x14005e9bb  test    eax, eax
0x14005e9bd  jnz     short loc_14005E9EB
0x14005e9bf  mov     edi, dword ptr [rsp+180h+var_110+4]
0x14005e9c3  jmp     short loc_14005E9F6
0x14005e9c5  mov     rax, [rsi]
0x14005e9c8  lea     r9, [rsp+180h+var_110]
0x14005e9cd  mov     r8, r15
0x14005e9d0  mov     rdx, r12
0x14005e9d3  mov     rcx, rsi
0x14005e9d6  mov     rax, [rax+40h]
0x14005e9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005e9df  xor     esi, esi
0x14005e9e1  test    eax, eax
0x14005e9e3  js      loc_14005EAB7
0x14005e9e9  jmp     short loc_14005E9B7
0x14005e9eb  mov     rdi, rsi
0x14005e9ee  cmp     eax, 1
0x14005e9f1  jnz     short loc_14005E9F6
0x14005e9f3  mov     edi, dword ptr [rbp+80h+var_100]
0x14005e9f6  mov     rbx, [rbp+80h+var_A8]
0x14005e9fa  mov     [rsp+180h+var_128], rbx
0x14005e9ff  test    rbx, rbx
0x14005ea02  jz      short loc_14005EA0B
0x14005ea04  lock inc dword ptr [rbx+128h]
0x14005ea0b  lea     rcx, [rbx+8]
0x14005ea0f  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x14005ea14  test    rdi, rdi
0x14005ea17  setz    al
0x14005ea1a  mov     [rbx+110h], al
0x14005ea20  lea     rcx, [rsp+180h+var_128]
0x14005ea25  call    ??1?$test_data_control@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::~test_data_control<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>(void)
0x14005ea2a  mov     rcx, [rbp+80h+var_A8]
0x14005ea2e  add     rcx, 8
0x14005ea32  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x14005ea37  lea     rdx, [rsp+180h+var_110]
0x14005ea3c  mov     rcx, r13
0x14005ea3f  call    _anonymous_namespace___create_embedding
0x14005ea44  nop
0x14005ea45  lea     rcx, [rbp+80h+var_E0]
0x14005ea49  call    ??1?$test_watcher@V?$merged_data@U_tip_EmbeddingGenerationTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>::~test_watcher<tip2::details::merged_data<_tip_EmbeddingGenerationTest,_tip_EmbeddingGenerationTest>>(void)
0x14005ea4e  nop
0x14005ea4f  lea     rcx, [rsp+180h+var_110]; struct tagSemanticVector *
0x14005ea54  call    ?FreeSemanticVector@@YAXPEAUtagSemanticVector@@@Z; FreeSemanticVector(tagSemanticVector *)
0x14005ea59  mov     rax, r13
0x14005ea5c  mov     rcx, [rbp+80h+var_50]
0x14005ea60  xor     rcx, rsp; StackCookie
0x14005ea63  call    __security_check_cookie
0x14005ea68  add     rsp, 148h
0x14005ea6f  pop     r15
0x14005ea71  pop     r14
0x14005ea73  pop     r13
0x14005ea75  pop     r12
0x14005ea77  pop     rdi
0x14005ea78  pop     rsi
0x14005ea79  pop     rbx
0x14005ea7a  pop     rbp
0x14005ea7b  retn
0x14005ea7c  mov     edx, eax
0x14005ea7e  xor     ecx, ecx
0x14005ea80  call    ?ReportSemanticRequeueRequested@SemanticSearchTelemetryAggregated@@SAXW4SemanticOperationType@@J@Z; SemanticSearchTelemetryAggregated::ReportSemanticRequeueRequested(SemanticOperationType,long)
0x14005ea85  mov     ecx, 80041226h
0x14005ea8a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x14005ea8f  mov     r9d, eax; char *
0x14005ea92  mov     rcx, [rbp+88h]; this
0x14005ea99  lea     rax, aFailedToExtrac; "Failed to extract image properties."
0x14005eaa0  mov     [rsp+180h+var_160], rax; int
0x14005eaa5  lea     r8, aOnecoreuapBase_45; "onecoreuap\\base\\appmodel\\search\\com"...
0x14005eaac  mov     edx, 63h ; 'c'; void *
0x14005eab1  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x14005eab7  mov     edx, eax
0x14005eab9  xor     ecx, ecx
0x14005eabb  call    ?ReportSemanticRequeueRequested@SemanticSearchTelemetryAggregated@@SAXW4SemanticOperationType@@J@Z; SemanticSearchTelemetryAggregated::ReportSemanticRequeueRequested(SemanticOperationType,long)
0x14005eac0  mov     ecx, 80041226h
0x14005eac5  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x14005eaca  mov     r9d, eax; char *
0x14005eacd  mov     rcx, [rbp+88h]; this
  ... truncated ...
```
