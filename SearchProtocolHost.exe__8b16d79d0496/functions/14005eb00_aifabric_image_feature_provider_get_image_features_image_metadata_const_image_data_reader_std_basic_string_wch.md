# aifabric_image_feature_provider::get_image_features(image_metadata const &,image_data_reader &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &)

- ea: `0x14005eb00`
- end: `0x14005f262`
- name: `?get_image_features@aifabric_image_feature_provider@@UEBA?AUembedding@@AEBUimage_metadata@@AEAUimage_data_reader@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@6@@Z`
- size: `1890`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140005240`
- `0x14000c91c`
- `0x14000dd7c`
- `0x14000e678`
- `0x140015958`
- `0x140025ad0`
- `0x140032f70`
- `0x140033530`
- `0x1400344e4`
- `0x140036594`
- `0x14003900c`
- `0x140051180`
- `0x140058350`
- `0x14005ad1c`
- `0x14005ae2c`
- `0x14005aea8`
- `0x14005af98`
- `0x14005cb30`
- `0x14005cc24`
- `0x14005cc84`
- `0x14005cd0c`
- `0x14005cd84`
- `0x14005ce30`
- `0x14005cfac`
- `0x14005d030`
- `0x14005d0f4`
- `0x14005d338`
- `0x14005d4d4`
- `0x14005dc60`
- `0x14005dc90`
- `0x14005e16c`
- `0x14005e298`
- `0x14005e2d4`
- `0x14005e5fc`
- `0x14005eb00`
- `0x14005f598`
- `0x140070010`

## string_xrefs

- `0x14005ebfd`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`
- `0x14005f1ec`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`
- `0x14005ede0`: `Failed to copy pixels from filter with error: 0x%08x`
- `0x14005edec`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`
- `0x14005f216`: `Failed to copy pixels from filter.`
- `0x14005f242`: `Failed to copy pixels from filter.`
- `0x14005f1b2`: `Insufficient memory to copy pixels from filter.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  wil::com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>(v57);
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
        SemanticSearchTelemetryAggregated::ReportSemanticRequeueRequested(0, 2147942414LL);
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
    goto LABEL_57;
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
LABEL_49:
    v75[3] = 0;
    goto LABEL_50;
  }
  if ( v11 == 1 )
  {
    CImageHandler::ConvertPBGRA8ToBGRA8Buffer(v33, (const struct IMAGE_INFO *)&v55, v9[1]);
    goto LABEL_49;
  }
LABEL_50:
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
  std::_Variant_base<std::vector<float>,std::vector<enum gsl::byte>>::_Destroy(v65);
LABEL_57:
  tip2::test_watcher<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_watcher<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(v72);
  wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(v61);
  return a2;
}

```

## disassembly

```asm
0x14005eb00  mov     rax, rsp
0x14005eb03  push    rbp
0x14005eb04  push    rbx
0x14005eb05  push    rsi
0x14005eb06  push    rdi
0x14005eb07  push    r12
0x14005eb09  push    r13
0x14005eb0b  push    r14
0x14005eb0d  push    r15
0x14005eb0f  lea     rbp, [rsp-58h]
0x14005eb14  sub     rsp, 158h
0x14005eb1b  mov     [rbp+90h+var_80], 0FFFFFFFFFFFFFFFEh
0x14005eb23  movaps  xmmword ptr [rax-58h], xmm6
0x14005eb27  mov     rax, cs:__security_cookie
0x14005eb2e  xor     rax, rsp
0x14005eb31  mov     [rbp+90h+var_58], rax
0x14005eb35  mov     [rbp+90h+var_E0], r9
0x14005eb39  mov     rbx, r8
0x14005eb3c  mov     rdi, rdx
0x14005eb3f  mov     [rsp+190h+var_140], rdx
0x14005eb44  mov     rax, [rbp+90h+arg_20]
0x14005eb4b  mov     [rbp+90h+var_D0], rax
0x14005eb4f  mov     rax, [rbp+90h+arg_28]
0x14005eb56  mov     [rbp+90h+var_D8], rax
0x14005eb5a  xor     r13d, r13d
0x14005eb5d  mov     rsi, [rcx+8]
0x14005eb61  lea     rcx, [rsp+190h+var_120]
0x14005eb66  call    ?CreateSemanticSearchServices@@YA?AV?$com_ptr_t@UIIndexerSemanticSearchServices@@Uerr_exception_policy@wil@@@wil@@XZ; CreateSemanticSearchServices(void)
0x14005eb6b  nop
0x14005eb6c  xorps   xmm0, xmm0
0x14005eb6f  movups  xmmword ptr [rbp+90h+var_78], xmm0
0x14005eb73  mov     rcx, [rbx+8]
0x14005eb77  call    ??$narrow@K_K@gsl@@YAK_K@Z; gsl::narrow<ulong,unsigned __int64>(unsigned __int64)
0x14005eb7c  mov     [rbp+90h+var_78], eax
0x14005eb7f  mov     rcx, [rbx+10h]
0x14005eb83  call    ??$narrow@K_K@gsl@@YAK_K@Z; gsl::narrow<ulong,unsigned __int64>(unsigned __int64)
0x14005eb88  mov     [rbp+90h+var_78+4], eax
0x14005eb8b  mov     rcx, [rbx+8]
0x14005eb8f  imul    rcx, [rbx+10h]
0x14005eb94  shl     rcx, 2
0x14005eb98  call    ??$narrow@K_K@gsl@@YAK_K@Z; gsl::narrow<ulong,unsigned __int64>(unsigned __int64)
0x14005eb9d  mov     [rbp+90h+var_78+8], eax
0x14005eba0  xor     eax, eax
0x14005eba2  mov     [rsp+190h+var_158], rax
0x14005eba7  mov     [rsp+190h+var_150], eax
0x14005ebab  mov     rcx, [rbx+8]
0x14005ebaf  call    ??$narrow@K_K@gsl@@YAK_K@Z; gsl::narrow<ulong,unsigned __int64>(unsigned __int64)
0x14005ebb4  mov     r15d, eax
0x14005ebb7  mov     dword ptr [rsp+190h+var_158], eax
0x14005ebbb  mov     rcx, [rbx+10h]
0x14005ebbf  call    ??$narrow@K_K@gsl@@YAK_K@Z; gsl::narrow<ulong,unsigned __int64>(unsigned __int64)
0x14005ebc4  mov     dword ptr [rsp+190h+var_158+4], eax
0x14005ebc8  mov     ecx, [rbx]
0x14005ebca  test    ecx, ecx
0x14005ebcc  jz      short loc_14005EBE6
0x14005ebce  sub     ecx, 1
0x14005ebd1  jz      short loc_14005EBE1
0x14005ebd3  cmp     ecx, 1
0x14005ebd6  jnz     loc_14005F1CC
0x14005ebdc  mov     r14d, ecx
0x14005ebdf  jmp     short loc_14005EBEC
0x14005ebe1  mov     r14d, r13d
0x14005ebe4  jmp     short loc_14005EBEC
0x14005ebe6  mov     r14d, 2
0x14005ebec  mov     [rsp+190h+var_150], r14d
0x14005ebf1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56182531@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531> `wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl(void)'::`2'::impl
0x14005ebf8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(void)
0x14005ebfd  lea     rbx, aOnecoreuapBase_45; "onecoreuap\\base\\appmodel\\search\\com"...
0x14005ec04  lea     rdx, [rsp+190h+var_158]; struct IMAGE_INFO *
0x14005ec09  test    al, al
0x14005ec0b  jz      short loc_14005EC8A
0x14005ec0d  call    ?CanHandleImage@CImageHandler@@QEAAJAEBUIMAGE_INFO@@@Z; CImageHandler::CanHandleImage(IMAGE_INFO const &)
0x14005ec12  mov     rcx, [rbp+98h]; this
0x14005ec19  lea     rdx, aIndexerCannotH; "Indexer cannot handle this image."
0x14005ec20  mov     [rsp+190h+Src], rdx; __int64
0x14005ec25  mov     r9d, eax; char *
0x14005ec28  mov     r8, rbx; unsigned int
0x14005ec2b  mov     edx, 0EBh; void *
0x14005ec30  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14005ec35  mov     qword ptr [rsp+190h+var_148], r13
0x14005ec3a  lea     rdx, [rbp+90h+var_C0]
0x14005ec3e  lea     rcx, [rsp+190h+var_148]
0x14005ec43  call    ?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@2@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::start_and_watch_errors(void)
0x14005ec48  lea     rcx, [rsp+190h+var_148]
0x14005ec4d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>,wil::err_returncode_policy>(void)
0x14005ec52  nop
0x14005ec53  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57519991@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991> `wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl(void)'::`2'::impl
0x14005ec5a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(void)
0x14005ec5f  test    al, al
0x14005ec61  jz      short loc_14005EC99
0x14005ec63  lea     r8, [rsp+190h+var_158]
0x14005ec68  lea     rdx, [rsp+190h+var_118]
0x14005ec6d  call    ?GetBufferInfoForImageFrame@CImageHandler@@QEAA?AUImageBufferInfo@@AEBUIMAGE_INFO@@@Z; CImageHandler::GetBufferInfoForImageFrame(IMAGE_INFO const &)
0x14005ec72  mov     r12d, [rax]
0x14005ec75  mov     r13d, [rax+4]
0x14005ec79  mov     ecx, [rax+0Ch]
0x14005ec7c  movss   xmm6, dword ptr [rax+8]
0x14005ec81  mov     eax, r13d
0x14005ec84  imul    eax, r12d
0x14005ec88  jmp     short loc_14005ECCA
0x14005ec8a  call    ?CanHandle@CImageHandler@@QEAAHAEBUIMAGE_INFO@@@Z; CImageHandler::CanHandle(IMAGE_INFO const &)
0x14005ec8f  test    eax, eax
0x14005ec91  jz      loc_14005F16B
0x14005ec97  jmp     short loc_14005EC35
0x14005ec99  mov     r12d, r13d
0x14005ec9c  movss   xmm6, cs:__real@3f800000
0x14005eca4  mov     eax, 20h ; ' '
0x14005eca9  lea     r8d, [rax-8]
0x14005ecad  cmp     r14d, 2
0x14005ecb1  cmovnz  r8d, eax; unsigned int
0x14005ecb5  mov     edx, r15d; unsigned int
0x14005ecb8  call    ?GetStride@CImageHandler@@QEAAIII@Z; CImageHandler::GetStride(uint,uint)
0x14005ecbd  mov     ecx, eax
0x14005ecbf  mov     eax, dword ptr [rsp+190h+var_158+4]
0x14005ecc3  imul    ecx, eax
0x14005ecc6  imul    eax, r15d
0x14005ecca  mov     [rsp+190h+var_160], ecx
0x14005ecce  shl     eax, 2
0x14005ecd1  mov     [rsp+190h+var_148], eax
0x14005ecd5  mov     r15, [rbp+90h+var_88]
0x14005ecd9  mov     [rsp+190h+var_140], r15
0x14005ecde  test    r15, r15
0x14005ece1  jz      short loc_14005ECEB
0x14005ece3  lock inc dword ptr [r15+118h]
0x14005eceb  lea     rcx, [r15+8]
0x14005ecef  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x14005ecf4  mov     eax, [rsp+190h+var_160]
0x14005ecf8  mov     [r15+110h], eax
0x14005ecff  lea     rcx, [rsp+190h+var_140]
0x14005ed04  call    ??1?$test_data_control@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(void)
0x14005ed09  mov     edx, [rsp+190h+var_148]; unsigned int
0x14005ed0d  mov     rcx, rsi; this
0x14005ed10  call    ?PrepareSharedMem@CImageHandler@@QEAAJK@Z; CImageHandler::PrepareSharedMem(ulong)
0x14005ed15  mov     rcx, [rbp+98h]; this
0x14005ed1c  lea     rdx, aFailedToPrepar; "Failed to prepare shared memory for ima"...
0x14005ed23  mov     [rsp+190h+Src], rdx; __int64
0x14005ed28  mov     r9d, eax; char *
0x14005ed2b  mov     r8, rbx; unsigned int
0x14005ed2e  mov     edx, 110h; void *
0x14005ed33  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x14005ed38  mov     r15, [rbp+90h+var_88]
0x14005ed3c  mov     [rsp+190h+var_140], r15
0x14005ed41  test    r15, r15
0x14005ed44  jz      short loc_14005ED4E
0x14005ed46  lock inc dword ptr [r15+118h]
0x14005ed4e  lea     rcx, [r15+8]
0x14005ed52  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x14005ed57  mov     byte ptr [r15+114h], 0
0x14005ed5f  lea     rcx, [rsp+190h+var_140]
0x14005ed64  call    ??1?$test_data_control@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(void)
0x14005ed69  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56182531@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531> `wil::Feature<__WilFeatureTraits_Feature_56182531>::GetImpl(void)'::`2'::impl
0x14005ed70  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56182531@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56182531>::__private_IsEnabled(void)
0x14005ed75  xor     edx, edx
0x14005ed77  test    al, al
0x14005ed79  jz      loc_14005EF2D
0x14005ed7f  mov     [rsp+190h+var_118], rsi
0x14005ed84  mov     byte ptr [rbp+90h+var_110], 1
0x14005ed88  mov     eax, [rsp+190h+var_160]
0x14005ed8c  mov     rcx, [rsi+8]; this
0x14005ed90  test    rcx, rcx
0x14005ed93  jnz     short loc_14005ED9E
0x14005ed95  test    rax, rax
0x14005ed98  jnz     loc_14005F1FE
0x14005ed9e  mov     [rbp+90h+var_68], rdx
0x14005eda2  mov     edx, dword ptr [rsp+190h+var_158]
0x14005eda6  mov     dword ptr [rbp+90h+var_60], edx
0x14005eda9  mov     edx, dword ptr [rsp+190h+var_158+4]
0x14005edad  mov     dword ptr [rbp+90h+var_60+4], edx
0x14005edb0  mov     [rsp+190h+var_140], rax
0x14005edb5  mov     [rsp+190h+var_138], rcx
0x14005edba  mov     rcx, [rbp+90h+var_E0]
0x14005edbe  mov     rax, [rcx]
0x14005edc1  lea     r9, [rsp+190h+var_140]
0x14005edc6  lea     r8, [rbp+90h+var_68]
0x14005edca  movaps  xmm1, xmm6
0x14005edcd  mov     rax, [rax+8]
0x14005edd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005edd6  mov     r15d, eax
0x14005edd9  test    eax, eax
0x14005eddb  jns     short loc_14005EE1F
0x14005eddd  mov     r9d, eax; wchar_t *
0x14005ede0  lea     r8, aFailedToCopyPi_0; "Failed to copy pixels from filter with "...
0x14005ede7  mov     edx, 120h; wchar_t *
0x14005edec  lea     rcx, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\com"...
0x14005edf3  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14005edf8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56631575@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56631575@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56631575> `wil::Feature<__WilFeatureTraits_Feature_56631575>::GetImpl(void)'::`2'::impl
0x14005edff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56631575@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56631575>::__private_IsEnabled(void)
0x14005ee04  test    al, al
0x14005ee06  jnz     loc_14005F204
0x14005ee0c  mov     edx, 8007000Eh
0x14005ee11  cmp     r15d, edx
0x14005ee14  jz      loc_14005F197
0x14005ee1a  jmp     loc_14005F230
0x14005ee1f  mov     r15, [rbp+90h+var_88]
0x14005ee23  mov     [rsp+190h+var_140], r15
0x14005ee28  test    r15, r15
0x14005ee2b  jz      short loc_14005EE35
0x14005ee2d  lock inc dword ptr [r15+118h]
0x14005ee35  lea     rcx, [r15+8]
0x14005ee39  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x14005ee3e  mov     byte ptr [r15+115h], 0
0x14005ee46  lea     rcx, [rsp+190h+var_140]
0x14005ee4b  call    ??1?$test_data_control@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(void)
0x14005ee50  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57519991@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991> `wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl(void)'::`2'::impl
0x14005ee57  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(void)
0x14005ee5c  xor     r15d, r15d
0x14005ee5f  test    al, al
0x14005ee61  jz      short loc_14005EE7C
0x14005ee63  mov     dword ptr [rsp+190h+var_158], r12d
0x14005ee68  mov     [rbp+90h+var_78], r12d
0x14005ee6c  mov     dword ptr [rsp+190h+var_158+4], r13d
0x14005ee71  mov     [rbp+90h+var_78+4], r13d
0x14005ee75  mov     eax, [rsp+190h+var_148]
0x14005ee79  mov     [rbp+90h+var_78+8], eax
0x14005ee7c  cmp     r14d, 2
0x14005ee80  jnz     short loc_14005EEB5
0x14005ee82  mov     dword ptr [rsp+190h+var_140], 145h
0x14005ee8a  mov     [rsp+190h+var_138], rbx
0x14005ee8f  mov     [rsp+190h+var_130], r15
0x14005ee94  mov     r8, [rsi+8]; unsigned __int8 *
0x14005ee98  lea     rdx, [rsp+190h+var_158]; struct IMAGE_INFO *
0x14005ee9d  call    ?ConvertBGR8ToBGRA8Buffer@CImageHandler@@QEAAJAEBUIMAGE_INFO@@PEAE@Z; CImageHandler::ConvertBGR8ToBGRA8Buffer(IMAGE_INFO const &,uchar *)
0x14005eea2  lea     r8, [rsp+190h+var_140]
0x14005eea7  mov     edx, eax
0x14005eea9  lea     rcx, [rsp+190h+var_148]
0x14005eeae  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x14005eeb3  jmp     short loc_14005EEC9
0x14005eeb5  cmp     r14d, 1
0x14005eeb9  jnz     short loc_14005EECD
0x14005eebb  mov     r8, [rsi+8]; unsigned __int8 *
0x14005eebf  lea     rdx, [rsp+190h+var_158]; struct IMAGE_INFO *
0x14005eec4  call    ?ConvertPBGRA8ToBGRA8Buffer@CImageHandler@@QEAAXAEBUIMAGE_INFO@@PEAE@Z; CImageHandler::ConvertPBGRA8ToBGRA8Buffer(IMAGE_INFO const &,uchar *)
0x14005eec9  mov     [rbp+90h+var_78+0Ch], r15d
0x14005eecd  mov     rcx, [rbp+90h+var_88]
0x14005eed1  add     rcx, 8
0x14005eed5  call    ?complete_without_lock@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::complete_without_lock(void)
0x14005eeda  mov     rax, [rbp+90h+var_D8]
0x14005eede  mov     [rsp+190h+var_168], rax; __int64
0x14005eee3  mov     rax, [rbp+90h+var_D0]
0x14005eee7  mov     [rsp+190h+Src], rax; int
0x14005eeec  mov     r9, [rsi]; int
0x14005eeef  lea     r8, [rbp+90h+var_78]; int
0x14005eef3  mov     rdx, qword ptr [rsp+190h+var_120]; int
0x14005eef8  mov     rcx, rdi; int
0x14005eefb  call    _anonymous_namespace___get_image_features
0x14005ef00  nop
0x14005ef01  mov     rcx, rsi; this
0x14005ef04  call    ?CloseImageMapping@CMemMappedImage@@QEAAJXZ; CMemMappedImage::CloseImageMapping(void)
0x14005ef09  mov     rcx, [rbp+98h]; this
0x14005ef10  test    eax, eax
0x14005ef12  jns     loc_14005F0D9
0x14005ef18  mov     r9d, eax; char *
0x14005ef1b  mov     r8, rbx; unsigned int
0x14005ef1e  mov     edx, 116h; void *
0x14005ef23  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14005ef28  jmp     loc_14005F0D9
0x14005ef2d  mov     eax, [rsp+190h+var_160]
0x14005ef31  mov     rcx, [rsi+8]; this
0x14005ef35  test    rcx, rcx
0x14005ef38  jnz     short loc_14005EF43
0x14005ef3a  test    rax, rax
0x14005ef3d  jnz     loc_14005F25C
0x14005ef43  mov     [rbp+90h+var_68], rdx
0x14005ef47  mov     edx, dword ptr [rsp+190h+var_158]
0x14005ef4b  mov     dword ptr [rbp+90h+var_60], edx
0x14005ef4e  mov     edx, dword ptr [rsp+190h+var_158+4]
0x14005ef52  mov     dword ptr [rbp+90h+var_60+4], edx
0x14005ef55  mov     [rsp+190h+var_140], rax
0x14005ef5a  mov     [rsp+190h+var_138], rcx
0x14005ef5f  mov     rcx, [rbp+90h+var_E0]
0x14005ef63  mov     rax, [rcx]
0x14005ef66  lea     r9, [rsp+190h+var_140]
0x14005ef6b  lea     r8, [rbp+90h+var_68]
0x14005ef6f  movaps  xmm1, xmm6
0x14005ef72  mov     rax, [rax+8]
0x14005ef76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005ef7b  mov     [rsp+190h+var_160], eax
0x14005ef7f  mov     r15, [rbp+90h+var_88]
0x14005ef83  mov     [rsp+190h+var_140], r15
0x14005ef88  test    r15, r15
0x14005ef8b  jz      short loc_14005EF95
0x14005ef8d  lock inc dword ptr [r15+118h]
0x14005ef95  lea     rcx, [r15+8]
0x14005ef99  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x14005ef9e  mov     byte ptr [r15+115h], 0
0x14005efa6  lea     rcx, [rsp+190h+var_140]
0x14005efab  call    ??1?$test_data_control@V?$merged_data@U_tip_ImagePixelExtractionTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>::~test_data_control<tip2::details::merged_data<_tip_ImagePixelExtractionTest,_tip_ImagePixelExtractionTest>>(void)
0x14005efb0  xor     r15d, r15d
0x14005efb3  cmp     [rsp+190h+var_160], r15d
0x14005efb8  jl      loc_14005F118
0x14005efbe  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57519991@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991> `wil::Feature<__WilFeatureTraits_Feature_57519991>::GetImpl(void)'::`2'::impl
0x14005efc5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57519991@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57519991>::__private_IsEnabled(void)
0x14005efca  test    al, al
0x14005efcc  jz      short loc_14005EFE7
0x14005efce  mov     dword ptr [rsp+190h+var_158], r12d
0x14005efd3  mov     [rbp+90h+var_78], r12d
0x14005efd7  mov     dword ptr [rsp+190h+var_158+4], r13d
0x14005efdc  mov     [rbp+90h+var_78+4], r13d
0x14005efe0  mov     eax, [rsp+190h+var_148]
0x14005efe4  mov     [rbp+90h+var_78+8], eax
  ... truncated ...
```
