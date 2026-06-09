# aifabric_image_feature_provider::get_image_features(image_metadata const &,image_data_reader &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &)

- ea: `0x1400459e0`
- end: `0x140046140`
- name: `?get_image_features@aifabric_image_feature_provider@@UEBA?AUembedding@@AEBUimage_metadata@@AEAUimage_data_reader@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@6@@Z`
- size: `1888`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400030a0`
- `0x140005ec8`
- `0x14000da64`
- `0x1400155e0`
- `0x1400158a8`
- `0x1400158dc`
- `0x140016668`
- `0x14001801c`
- `0x14001b858`
- `0x14001e440`
- `0x140028550`
- `0x140033df0`
- `0x1400342b8`
- `0x140037ab4`
- `0x14003a168`
- `0x14003a278`
- `0x140043990`
- `0x140043a8c`
- `0x140043aec`
- `0x140043bbc`
- `0x140043c34`
- `0x140043ce0`
- `0x140043e5c`
- `0x140043ee0`
- `0x140043fa4`
- `0x1400441e8`
- `0x140044384`
- `0x140044b10`
- `0x140044b40`
- `0x14004501c`
- `0x140045148`
- `0x140045184`
- `0x1400454ac`
- `0x1400459e0`
- `0x140046478`
- `0x140046540`
- `0x14004f010`

## string_xrefs

- `0x140045add`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`
- `0x1400460ca`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`
- `0x140045cc0`: `Failed to copy pixels from filter with error: 0x%08x`
- `0x140045ccc`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`
- `0x1400460f4`: `Failed to copy pixels from filter.`
- `0x140046120`: `Failed to copy pixels from filter.`
- `0x140046090`: `Insufficient memory to copy pixels from filter.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall aifabric_image_feature_provider::get_image_features(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        __int64 a6)
{
  int v8; // r13d
  unsigned __int8 **v9; // rsi
  unsigned int v10; // r15d
  int v11; // r14d
  CImageHandler *v12; // rcx
  unsigned int CanHandleImage; // eax
  CImageHandler *v14; // rcx
  int *BufferInfoForImageFrame; // rax
  int v16; // r12d
  int v17; // ecx
  int v18; // eax
  unsigned int v19; // r8d
  unsigned int Stride; // eax
  __int64 v21; // r15
  unsigned int v22; // eax
  __int64 v23; // r15
  const char *v24; // rcx
  int v25; // eax
  unsigned int v26; // r15d
  __int64 v27; // r15
  CImageHandler *v28; // rcx
  unsigned int v29; // eax
  int v30; // eax
  const char *v31; // rcx
  __int64 v32; // r15
  CImageHandler *v33; // rcx
  unsigned int v34; // eax
  int v35; // eax
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  bool v39; // zf
  __int64 v40; // rax
  __int64 v42; // rax
  unsigned int *v43; // rax
  unsigned int *v44; // rax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  int Src; // [rsp+20h] [rbp-E0h]
  int Srca; // [rsp+20h] [rbp-E0h]
  const char *v51; // [rsp+28h] [rbp-D8h]
  const char *v52; // [rsp+28h] [rbp-D8h]
  unsigned int v53; // [rsp+30h] [rbp-D0h]
  int v54; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v55; // [rsp+38h] [rbp-C8h] BYREF
  int v56; // [rsp+40h] [rbp-C0h]
  unsigned int v57[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v58; // [rsp+50h] [rbp-B0h] BYREF
  const char *v59; // [rsp+58h] [rbp-A8h]
  __int64 v60; // [rsp+60h] [rbp-A0h]
  int v61[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 **v62; // [rsp+78h] [rbp-88h] BYREF
  const char *v63; // [rsp+80h] [rbp-80h]
  __int64 v64; // [rsp+88h] [rbp-78h]
  int v65[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v66; // [rsp+98h] [rbp-68h]
  __int64 v67; // [rsp+A0h] [rbp-60h]
  char v68; // [rsp+A8h] [rbp-58h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  __int64 v70; // [rsp+B8h] [rbp-48h]
  void *v71; // [rsp+C0h] [rbp-40h]
  _BYTE v72[56]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v73; // [rsp+108h] [rbp+8h]
  __int64 v74; // [rsp+110h] [rbp+10h]
  int v75[4]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v76; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int64 v77; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v74 = -2;
  v69 = a4;
  v58 = a2;
  v71 = a5;
  v70 = a6;
  v8 = 0;
  v9 = *(unsigned __int8 ***)(a1 + 8);
  CreateSemanticSearchServices(v61);
  *(_OWORD *)v75 = 0;
  v75[0] = gsl::narrow<unsigned long,unsigned __int64>(*(_QWORD *)(a3 + 8));
  v75[1] = gsl::narrow<unsigned long,unsigned __int64>(*(_QWORD *)(a3 + 16));
  v75[2] = gsl::narrow<unsigned long,unsigned __int64>(4LL * *(_QWORD *)(a3 + 16) * *(_QWORD *)(a3 + 8));
  v55 = 0;
  v56 = 0;
  v10 = gsl::narrow<unsigned long,unsigned __int64>(*(_QWORD *)(a3 + 8));
  LODWORD(v55) = v10;
  HIDWORD(v55) = gsl::narrow<unsigned long,unsigned __int64>(*(_QWORD *)(a3 + 16));
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v11 = 0;
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        v46 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0xB9,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
          (const char *)v46,
          (int)"Unsupported image_data_format.",
          v51);
      }
      v11 = 1;
    }
  }
  else
  {
    v11 = 2;
  }
  v56 = v11;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl'::`2'::impl) )
  {
    CanHandleImage = CImageHandler::CanHandleImage(v12, (const struct IMAGE_INFO *)&v55);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xEB,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
      (const char *)CanHandleImage,
      (__int64)"Indexer cannot handle this image.",
      v51);
  }
  else if ( !(unsigned int)CImageHandler::CanHandle(v12, (const struct IMAGE_INFO *)&v55) )
  {
    LODWORD(v62) = 242;
    v63 = "onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp";
    v64 = 0;
    v44 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)v57, -2147467259);
    winrt::throw_hresult(*v44, &v62);
  }
  *(_QWORD *)v57 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::start_and_watch_errors(
    v57,
    v72);
  wil::com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>((void **)v57);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl'::`2'::impl) )
  {
    BufferInfoForImageFrame = (int *)CImageHandler::GetBufferInfoForImageFrame(v14, &v62, &v55);
    v16 = *BufferInfoForImageFrame;
    v8 = BufferInfoForImageFrame[1];
    v17 = BufferInfoForImageFrame[3];
    v18 = *BufferInfoForImageFrame * v8;
  }
  else
  {
    v16 = 0;
    v19 = 24;
    if ( v11 != 2 )
      v19 = 32;
    Stride = CImageHandler::GetStride(v14, v10, v19);
    v17 = HIDWORD(v55) * Stride;
    v18 = v10 * HIDWORD(v55);
  }
  v53 = v17;
  v57[0] = 4 * v18;
  v21 = v73;
  v58 = v73;
  if ( v73 )
    _InterlockedIncrement((volatile signed __int32 *)(v73 + 280));
  tip2::details::shared_data<0,0,0>::begin_update(v21 + 8);
  *(_DWORD *)(v21 + 272) = v53;
  tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(&v58);
  v22 = CImageHandler::PrepareSharedMem((CImageHandler *)v9, v57[0]);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x110,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
    (const char *)v22,
    (__int64)"Failed to prepare shared memory for image pixel extraction.",
    v51);
  v23 = v73;
  v58 = v73;
  if ( v73 )
    _InterlockedIncrement((volatile signed __int32 *)(v73 + 280));
  tip2::details::shared_data<0,0,0>::begin_update(v23 + 8);
  *(_BYTE *)(v23 + 276) = 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(&v58);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl'::`2'::impl) )
  {
    v62 = v9;
    LOBYTE(v63) = 1;
    v24 = (const char *)v9[1];
    if ( !v24 && v53 )
      gsl::details::terminate(0);
    v76 = 0;
    v77 = v55;
    v58 = v53;
    v59 = v24;
    v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v69 + 8LL))(
            v69,
            HIDWORD(v55),
            &v76,
            &v58);
    v26 = v25;
    if ( v25 < 0 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const wchar_t *)0x120,
        (unsigned int)L"Failed to copy pixels from filter with error: 0x%08x",
        (const wchar_t *)(unsigned int)v25);
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56631575>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56631575>::GetImpl'::`2'::impl) )
      {
        if ( v26 != -2147024882 )
        {
          v48 = wil::verify_hresult<long>(v26);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x132,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
            (const char *)v48,
            (int)"Failed to copy pixels from filter.",
            v52);
        }
        SemanticSearchTelemetryAggregated::ReportSemanticRequeueRequested(0);
        v45 = wil::verify_hresult<long>(2147750438LL);
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x12E,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
          (const char *)v45,
          (int)"Insufficient memory to copy pixels from filter.",
          v52);
      }
      v47 = wil::verify_hresult<long>(v26);
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)v47,
        (int)"Failed to copy pixels from filter.",
        v52);
    }
    v27 = v73;
    v58 = v73;
    if ( v73 )
      _InterlockedIncrement((volatile signed __int32 *)(v73 + 280));
    tip2::details::shared_data<0,0,0>::begin_update(v27 + 8);
    *(_BYTE *)(v27 + 277) = 0;
    tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(&v58);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl'::`2'::impl) )
    {
      v55 = __PAIR64__(v8, v16);
      v75[0] = v16;
      v75[1] = v8;
      v75[2] = v57[0];
    }
    if ( v11 == 2 )
    {
      LODWORD(v58) = 325;
      v59 = "onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp";
      v60 = 0;
      v29 = CImageHandler::ConvertBGR8ToBGRA8Buffer(v28, (const struct IMAGE_INFO *)&v55, v9[1]);
      winrt::check_hresult(v57, v29, &v58);
    }
    else
    {
      if ( v11 != 1 )
        goto LABEL_36;
      CImageHandler::ConvertPBGRA8ToBGRA8Buffer(v28, (const struct IMAGE_INFO *)&v55, v9[1]);
    }
    v75[3] = 0;
LABEL_36:
    tip2::details::shared_data<0,0,0>::complete_without_lock(v73 + 8);
    anonymous_namespace_::get_image_features(a2, v61[0], (int)v75, (int)*v9, v71, v70);
    v30 = CMemMappedImage::CloseImageMapping((CMemMappedImage *)v9);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x116,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)(unsigned int)v30,
        Src);
    goto LABEL_58;
  }
  v31 = (const char *)v9[1];
  if ( !v31 && v53 )
    gsl::details::terminate(0);
  v76 = 0;
  v77 = v55;
  v58 = v53;
  v59 = v31;
  v54 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v69 + 8LL))(
          v69,
          HIDWORD(v55),
          &v76,
          &v58);
  v32 = v73;
  v58 = v73;
  if ( v73 )
    _InterlockedIncrement((volatile signed __int32 *)(v73 + 280));
  tip2::details::shared_data<0,0,0>::begin_update(v32 + 8);
  *(_BYTE *)(v32 + 277) = 0;
  tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(&v58);
  if ( v54 < 0 )
  {
    v42 = tip2::test_watcher<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::operator->(
            v72,
            &v58);
    *(_BYTE *)(tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::operator->(v42)
             + 277) = 1;
    tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(&v58);
    LODWORD(v62) = 351;
    v63 = "onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp";
    v64 = 0;
    v43 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)v57, -2147483637);
    winrt::throw_hresult(*v43, &v62);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl'::`2'::impl) )
  {
    v55 = __PAIR64__(v8, v16);
    v75[0] = v16;
    v75[1] = v8;
    v75[2] = v57[0];
  }
  if ( v11 == 2 )
  {
    LODWORD(v62) = 365;
    v63 = "onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp";
    v64 = 0;
    v34 = CImageHandler::ConvertBGR8ToBGRA8Buffer(v33, (const struct IMAGE_INFO *)&v55, v9[1]);
    winrt::check_hresult(v57, v34, &v62);
LABEL_50:
    v75[3] = 0;
    goto LABEL_51;
  }
  if ( v11 == 1 )
  {
    CImageHandler::ConvertPBGRA8ToBGRA8Buffer(v33, (const struct IMAGE_INFO *)&v55, v9[1]);
    goto LABEL_50;
  }
LABEL_51:
  anonymous_namespace_::get_image_features((int)v65, v61[0], (int)v75, (int)*v9, v71, v70);
  v35 = CMemMappedImage::CloseImageMapping((CMemMappedImage *)v9);
  if ( v35 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
      (const char *)(unsigned int)v35,
      Srca);
  tip2::details::shared_data<0,0,0>::complete_without_lock(v73 + 8);
  *(_BYTE *)(a2 + 24) = -1;
  v36 = v68 + 1LL;
  if ( v68 != -1 )
  {
    v37 = v67;
    v38 = v66;
    v67 = 0;
    *(_QWORD *)(a2 + 16) = v37;
    v66 = 0;
    *(_QWORD *)(a2 + 8) = v38;
    v39 = v36 == 1;
    v40 = *(_QWORD *)v65;
    *(_QWORD *)v65 = 0;
    *(_QWORD *)a2 = v40;
    *(_BYTE *)(a2 + 24) = !v39;
  }
  std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy((__int64)v65);
LABEL_58:
  tip2::test_watcher<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_watcher<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(v72);
  wil::com_ptr_t<IFilter,wil::err_exception_policy>::~com_ptr_t<IFilter,wil::err_exception_policy>((__int64 *)v61);
  return a2;
}

```

## disassembly

```asm
0x1400459e0  mov     rax, rsp
0x1400459e3  push    rbp
0x1400459e4  push    rbx
0x1400459e5  push    rsi
0x1400459e6  push    rdi
0x1400459e7  push    r12
0x1400459e9  push    r13
0x1400459eb  push    r14
0x1400459ed  push    r15
0x1400459ef  lea     rbp, [rsp-58h]
0x1400459f4  sub     rsp, 158h
0x1400459fb  mov     [rbp+90h+var_80], 0FFFFFFFFFFFFFFFEh
0x140045a03  movaps  xmmword ptr [rax-58h], xmm6
0x140045a07  mov     rax, cs:__security_cookie
0x140045a0e  xor     rax, rsp
0x140045a11  mov     [rbp+90h+var_58], rax
0x140045a15  mov     [rbp+90h+var_E0], r9
0x140045a19  mov     rbx, r8
0x140045a1c  mov     rdi, rdx
0x140045a1f  mov     [rsp+190h+var_140], rdx
0x140045a24  mov     rax, [rbp+90h+arg_20]
0x140045a2b  mov     [rbp+90h+var_D0], rax
0x140045a2f  mov     rax, [rbp+90h+arg_28]
0x140045a36  mov     [rbp+90h+var_D8], rax
0x140045a3a  xor     r13d, r13d
0x140045a3d  mov     rsi, [rcx+8]
0x140045a41  lea     rcx, [rsp+190h+var_120]
0x140045a46  call    ?CreateSemanticSearchServices@@YA?AV?$com_ptr_t@UIIndexerSemanticSearchServices@@Uerr_exception_policy@wil@@@wil@@XZ; CreateSemanticSearchServices(void)
0x140045a4b  nop
0x140045a4c  xorps   xmm0, xmm0
0x140045a4f  movups  xmmword ptr [rbp+90h+var_78], xmm0
0x140045a53  mov     rcx, [rbx+8]
0x140045a57  call    ??$narrow@K_K@gsl@@YAK_K@Z; gsl::narrow<ulong,unsigned __int64>(unsigned __int64)
0x140045a5c  mov     [rbp+90h+var_78], eax
0x140045a5f  mov     rcx, [rbx+10h]
0x140045a63  call    ??$narrow@K_K@gsl@@YAK_K@Z; gsl::narrow<ulong,unsigned __int64>(unsigned __int64)
0x140045a68  mov     [rbp+90h+var_78+4], eax
0x140045a6b  mov     rcx, [rbx+8]
0x140045a6f  imul    rcx, [rbx+10h]
0x140045a74  shl     rcx, 2
0x140045a78  call    ??$narrow@K_K@gsl@@YAK_K@Z; gsl::narrow<ulong,unsigned __int64>(unsigned __int64)
0x140045a7d  mov     [rbp+90h+var_78+8], eax
0x140045a80  xor     eax, eax
0x140045a82  mov     [rsp+190h+var_158], rax
0x140045a87  mov     [rsp+190h+var_150], eax
0x140045a8b  mov     rcx, [rbx+8]
0x140045a8f  call    ??$narrow@K_K@gsl@@YAK_K@Z; gsl::narrow<ulong,unsigned __int64>(unsigned __int64)
0x140045a94  mov     r15d, eax
0x140045a97  mov     dword ptr [rsp+190h+var_158], eax
0x140045a9b  mov     rcx, [rbx+10h]
0x140045a9f  call    ??$narrow@K_K@gsl@@YAK_K@Z; gsl::narrow<ulong,unsigned __int64>(unsigned __int64)
0x140045aa4  mov     dword ptr [rsp+190h+var_158+4], eax
0x140045aa8  mov     ecx, [rbx]
0x140045aaa  test    ecx, ecx
0x140045aac  jz      short loc_140045AC6
0x140045aae  sub     ecx, 1
0x140045ab1  jz      short loc_140045AC1
0x140045ab3  cmp     ecx, 1
0x140045ab6  jnz     loc_1400460AA
0x140045abc  mov     r14d, ecx
0x140045abf  jmp     short loc_140045ACC
0x140045ac1  mov     r14d, r13d
0x140045ac4  jmp     short loc_140045ACC
0x140045ac6  mov     r14d, 2
0x140045acc  mov     [rsp+190h+var_150], r14d
0x140045ad1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56182531@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531> `wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl(void)'::`2'::impl
0x140045ad8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(void)
0x140045add  lea     rbx, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\search\\com"...
0x140045ae4  lea     rdx, [rsp+190h+var_158]; struct IMAGE_INFO *
0x140045ae9  test    al, al
0x140045aeb  jz      short loc_140045B6A
0x140045aed  call    ?CanHandleImage@CImageHandler@@QEAAJAEBUIMAGE_INFO@@@Z; CImageHandler::CanHandleImage(IMAGE_INFO const &)
0x140045af2  mov     rcx, [rbp+98h]; this
0x140045af9  lea     rdx, aIndexerCannotH; "Indexer cannot handle this image."
0x140045b00  mov     [rsp+190h+Src], rdx; __int64
0x140045b05  mov     r9d, eax; char *
0x140045b08  mov     r8, rbx; unsigned int
0x140045b0b  mov     edx, 0EBh; void *
0x140045b10  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x140045b15  mov     qword ptr [rsp+190h+var_148], r13
0x140045b1a  lea     rdx, [rbp+90h+var_C0]
0x140045b1e  lea     rcx, [rsp+190h+var_148]
0x140045b23  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::start_and_watch_errors(void)
0x140045b28  lea     rcx, [rsp+190h+var_148]
0x140045b2d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>(void)
0x140045b32  nop
0x140045b33  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57519991@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991> `wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl(void)'::`2'::impl
0x140045b3a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(void)
0x140045b3f  test    al, al
0x140045b41  jz      short loc_140045B79
0x140045b43  lea     r8, [rsp+190h+var_158]
0x140045b48  lea     rdx, [rsp+190h+var_118]
0x140045b4d  call    ?GetBufferInfoForImageFrame@CImageHandler@@QEAA?AUImageBufferInfo@@AEBUIMAGE_INFO@@@Z; CImageHandler::GetBufferInfoForImageFrame(IMAGE_INFO const &)
0x140045b52  mov     r12d, [rax]
0x140045b55  mov     r13d, [rax+4]
0x140045b59  mov     ecx, [rax+0Ch]
0x140045b5c  movss   xmm6, dword ptr [rax+8]
0x140045b61  mov     eax, r13d
0x140045b64  imul    eax, r12d
0x140045b68  jmp     short loc_140045BAA
0x140045b6a  call    ?CanHandle@CImageHandler@@QEAAHAEBUIMAGE_INFO@@@Z; CImageHandler::CanHandle(IMAGE_INFO const &)
0x140045b6f  test    eax, eax
0x140045b71  jz      loc_140046049
0x140045b77  jmp     short loc_140045B15
0x140045b79  mov     r12d, r13d
0x140045b7c  movss   xmm6, cs:__real@3f800000
0x140045b84  mov     eax, 20h ; ' '
0x140045b89  lea     r8d, [rax-8]
0x140045b8d  cmp     r14d, 2
0x140045b91  cmovnz  r8d, eax; unsigned int
0x140045b95  mov     edx, r15d; unsigned int
0x140045b98  call    ?GetStride@CImageHandler@@QEAAIII@Z; CImageHandler::GetStride(uint,uint)
0x140045b9d  mov     ecx, eax
0x140045b9f  mov     eax, dword ptr [rsp+190h+var_158+4]
0x140045ba3  imul    ecx, eax
0x140045ba6  imul    eax, r15d
0x140045baa  mov     [rsp+190h+var_160], ecx
0x140045bae  shl     eax, 2
0x140045bb1  mov     [rsp+190h+var_148], eax
0x140045bb5  mov     r15, [rbp+90h+var_88]
0x140045bb9  mov     [rsp+190h+var_140], r15
0x140045bbe  test    r15, r15
0x140045bc1  jz      short loc_140045BCB
0x140045bc3  lock inc dword ptr [r15+118h]
0x140045bcb  lea     rcx, [r15+8]
0x140045bcf  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x140045bd4  mov     eax, [rsp+190h+var_160]
0x140045bd8  mov     [r15+110h], eax
0x140045bdf  lea     rcx, [rsp+190h+var_140]
0x140045be4  call    ??1?$test_data_control@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(void)
0x140045be9  mov     edx, [rsp+190h+var_148]; unsigned int
0x140045bed  mov     rcx, rsi; this
0x140045bf0  call    ?PrepareSharedMem@CImageHandler@@QEAAJK@Z; CImageHandler::PrepareSharedMem(ulong)
0x140045bf5  mov     rcx, [rbp+98h]; this
0x140045bfc  lea     rdx, aFailedToPrepar; "Failed to prepare shared memory for ima"...
0x140045c03  mov     [rsp+190h+Src], rdx; __int64
0x140045c08  mov     r9d, eax; char *
0x140045c0b  mov     r8, rbx; unsigned int
0x140045c0e  mov     edx, 110h; void *
0x140045c13  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x140045c18  mov     r15, [rbp+90h+var_88]
0x140045c1c  mov     [rsp+190h+var_140], r15
0x140045c21  test    r15, r15
0x140045c24  jz      short loc_140045C2E
0x140045c26  lock inc dword ptr [r15+118h]
0x140045c2e  lea     rcx, [r15+8]
0x140045c32  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x140045c37  mov     byte ptr [r15+114h], 0
0x140045c3f  lea     rcx, [rsp+190h+var_140]
0x140045c44  call    ??1?$test_data_control@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(void)
0x140045c49  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56182531@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531> `wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl(void)'::`2'::impl
0x140045c50  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(void)
0x140045c55  xor     edx, edx
0x140045c57  test    al, al
0x140045c59  jz      loc_140045E0A
0x140045c5f  mov     [rsp+190h+var_118], rsi
0x140045c64  mov     byte ptr [rbp+90h+var_110], 1
0x140045c68  mov     eax, [rsp+190h+var_160]
0x140045c6c  mov     rcx, [rsi+8]; this
0x140045c70  test    rcx, rcx
0x140045c73  jnz     short loc_140045C7E
0x140045c75  test    rax, rax
0x140045c78  jnz     loc_1400460DC
0x140045c7e  mov     [rbp+90h+var_68], rdx
0x140045c82  mov     edx, dword ptr [rsp+190h+var_158]
0x140045c86  mov     dword ptr [rbp+90h+var_60], edx
0x140045c89  mov     edx, dword ptr [rsp+190h+var_158+4]
0x140045c8d  mov     dword ptr [rbp+90h+var_60+4], edx
0x140045c90  mov     [rsp+190h+var_140], rax
0x140045c95  mov     [rsp+190h+var_138], rcx
0x140045c9a  mov     rcx, [rbp+90h+var_E0]
0x140045c9e  mov     rax, [rcx]
0x140045ca1  lea     r9, [rsp+190h+var_140]
0x140045ca6  lea     r8, [rbp+90h+var_68]
0x140045caa  movaps  xmm1, xmm6
0x140045cad  mov     rax, [rax+8]
0x140045cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045cb6  mov     r15d, eax
0x140045cb9  test    eax, eax
0x140045cbb  jns     short loc_140045CFF
0x140045cbd  mov     r9d, eax; wchar_t *
0x140045cc0  lea     r8, aFailedToCopyPi_0; "Failed to copy pixels from filter with "...
0x140045cc7  mov     edx, 120h; wchar_t *
0x140045ccc  lea     rcx, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x140045cd3  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140045cd8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56631575@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56631575@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56631575> `wil::Feature<__WilFeatureTraits_Feature_56631575>::GetImpl(void)'::`2'::impl
0x140045cdf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56631575@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56631575>::__private_IsEnabled(void)
0x140045ce4  test    al, al
0x140045ce6  jnz     loc_1400460E2
0x140045cec  mov     edx, 8007000Eh
0x140045cf1  cmp     r15d, edx
0x140045cf4  jz      loc_140046075
0x140045cfa  jmp     loc_14004610E
0x140045cff  mov     r15, [rbp+90h+var_88]
0x140045d03  mov     [rsp+190h+var_140], r15
0x140045d08  test    r15, r15
0x140045d0b  jz      short loc_140045D15
0x140045d0d  lock inc dword ptr [r15+118h]
0x140045d15  lea     rcx, [r15+8]
0x140045d19  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x140045d1e  mov     byte ptr [r15+115h], 0
0x140045d26  lea     rcx, [rsp+190h+var_140]
0x140045d2b  call    ??1?$test_data_control@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(void)
0x140045d30  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57519991@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991> `wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl(void)'::`2'::impl
0x140045d37  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(void)
0x140045d3c  xor     r15d, r15d
0x140045d3f  test    al, al
0x140045d41  jz      short loc_140045D5C
0x140045d43  mov     dword ptr [rsp+190h+var_158], r12d
0x140045d48  mov     [rbp+90h+var_78], r12d
0x140045d4c  mov     dword ptr [rsp+190h+var_158+4], r13d
0x140045d51  mov     [rbp+90h+var_78+4], r13d
0x140045d55  mov     eax, [rsp+190h+var_148]
0x140045d59  mov     [rbp+90h+var_78+8], eax
0x140045d5c  cmp     r14d, 2
0x140045d60  jnz     short loc_140045D95
0x140045d62  mov     dword ptr [rsp+190h+var_140], 145h
0x140045d6a  mov     [rsp+190h+var_138], rbx
0x140045d6f  mov     [rsp+190h+var_130], r15
0x140045d74  mov     r8, [rsi+8]; unsigned __int8 *
0x140045d78  lea     rdx, [rsp+190h+var_158]; struct IMAGE_INFO *
0x140045d7d  call    ?ConvertBGR8ToBGRA8Buffer@CImageHandler@@QEAAJAEBUIMAGE_INFO@@PEAE@Z; CImageHandler::ConvertBGR8ToBGRA8Buffer(IMAGE_INFO const &,uchar *)
0x140045d82  lea     r8, [rsp+190h+var_140]
0x140045d87  mov     edx, eax
0x140045d89  lea     rcx, [rsp+190h+var_148]
0x140045d8e  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x140045d93  jmp     short loc_140045DA9
0x140045d95  cmp     r14d, 1
0x140045d99  jnz     short loc_140045DAD
0x140045d9b  mov     r8, [rsi+8]; unsigned __int8 *
0x140045d9f  lea     rdx, [rsp+190h+var_158]; struct IMAGE_INFO *
0x140045da4  call    ?ConvertPBGRA8ToBGRA8Buffer@CImageHandler@@QEAAXAEBUIMAGE_INFO@@PEAE@Z; CImageHandler::ConvertPBGRA8ToBGRA8Buffer(IMAGE_INFO const &,uchar *)
0x140045da9  mov     [rbp+90h+var_78+0Ch], r15d
0x140045dad  mov     rcx, [rbp+90h+var_88]
0x140045db1  add     rcx, 8
0x140045db5  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x140045dba  mov     rax, [rbp+90h+var_D8]
0x140045dbe  mov     [rsp+190h+var_168], rax; __int64
0x140045dc3  mov     rax, [rbp+90h+var_D0]
0x140045dc7  mov     [rsp+190h+Src], rax; int
0x140045dcc  mov     r9, [rsi]; int
0x140045dcf  lea     r8, [rbp+90h+var_78]; int
0x140045dd3  mov     rdx, qword ptr [rsp+190h+var_120]; int
0x140045dd8  mov     rcx, rdi; int
0x140045ddb  call    _anonymous_namespace___get_image_features
0x140045de0  nop
0x140045de1  mov     rcx, rsi; this
0x140045de4  call    ?CloseImageMapping@CMemMappedImage@@QEAAJXZ; CMemMappedImage::CloseImageMapping(void)
0x140045de9  mov     rcx, [rbp+98h]; this
0x140045df0  test    eax, eax
0x140045df2  jns     short loc_140045E05
0x140045df4  mov     r9d, eax; char *
0x140045df7  mov     r8, rbx; unsigned int
0x140045dfa  mov     edx, 116h; void *
0x140045dff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140045e04  nop
0x140045e05  jmp     loc_140045FB7
0x140045e0a  mov     eax, [rsp+190h+var_160]
0x140045e0e  mov     rcx, [rsi+8]; this
0x140045e12  test    rcx, rcx
0x140045e15  jnz     short loc_140045E20
0x140045e17  test    rax, rax
0x140045e1a  jnz     loc_14004613A
0x140045e20  mov     [rbp+90h+var_68], rdx
0x140045e24  mov     edx, dword ptr [rsp+190h+var_158]
0x140045e28  mov     dword ptr [rbp+90h+var_60], edx
0x140045e2b  mov     edx, dword ptr [rsp+190h+var_158+4]
0x140045e2f  mov     dword ptr [rbp+90h+var_60+4], edx
0x140045e32  mov     [rsp+190h+var_140], rax
0x140045e37  mov     [rsp+190h+var_138], rcx
0x140045e3c  mov     rcx, [rbp+90h+var_E0]
0x140045e40  mov     rax, [rcx]
0x140045e43  lea     r9, [rsp+190h+var_140]
0x140045e48  lea     r8, [rbp+90h+var_68]
0x140045e4c  movaps  xmm1, xmm6
0x140045e4f  mov     rax, [rax+8]
0x140045e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045e58  mov     [rsp+190h+var_160], eax
0x140045e5c  mov     r15, [rbp+90h+var_88]
0x140045e60  mov     [rsp+190h+var_140], r15
0x140045e65  test    r15, r15
0x140045e68  jz      short loc_140045E72
0x140045e6a  lock inc dword ptr [r15+118h]
0x140045e72  lea     rcx, [r15+8]
0x140045e76  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x140045e7b  mov     byte ptr [r15+115h], 0
0x140045e83  lea     rcx, [rsp+190h+var_140]
0x140045e88  call    ??1?$test_data_control@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(void)
0x140045e8d  xor     r15d, r15d
0x140045e90  cmp     [rsp+190h+var_160], r15d
0x140045e95  jl      loc_140045FF6
0x140045e9b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57519991@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991> `wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl(void)'::`2'::impl
0x140045ea2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(void)
0x140045ea7  test    al, al
0x140045ea9  jz      short loc_140045EC4
0x140045eab  mov     dword ptr [rsp+190h+var_158], r12d
0x140045eb0  mov     [rbp+90h+var_78], r12d
0x140045eb4  mov     dword ptr [rsp+190h+var_158+4], r13d
0x140045eb9  mov     [rbp+90h+var_78+4], r13d
0x140045ebd  mov     eax, [rsp+190h+var_148]
  ... truncated ...
```
