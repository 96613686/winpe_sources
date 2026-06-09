# Mso::SVG::SVGCreatingCommandSink::GetEmbeddedImageForBitmap(ARC::IBitmap const &,Math::TRect<Math::TUnits<float,Math::DevicePixels>> const &,Math::TAffine3x3<float> const &,Math::TAffine3x3<float> const *,ARC::InterpolationMode)

- ea: `0x180054bec`
- end: `0x18005552d`
- name: `?GetEmbeddedImageForBitmap@SVGCreatingCommandSink@SVG@Mso@@AEAA?AV?$TCntPtr@UISVGEmbeddedImage@SVG@Mso@@@3@AEBUIBitmap@ARC@@AEBU?$TRect@V?$TUnits@MUDevicePixels@Math@@@Math@@@Math@@AEBU?$TAffine3x3@M@8@PEBU98@W4InterpolationMode@6@@Z`
- size: `2369`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18004ff0c`
- `0x180052528`
- `0x1800555c4`
- `0x180056440`
- `0x180057838`

## callees

- `0x180008a80`
- `0x180054560`
- `0x180054968`
- `0x180054bec`
- `0x180059ef4`
- `0x18005a03c`
- `0x18005b198`
- `0x18005b284`
- `0x18010801c`
- `0x180129c04`
- `0x18013f70e`
- `0x18013f760`

## import_xrefs

- `mso40uiWin32Client!__imp_?Create@IPlatformBitmap@ARC@@SA?AV?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@W4SurfaceFormat@2@HPEBEAEBU?$TVector2@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@6@@Z` at `0x1800552a9`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmap@ARC@@SA?AV?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@W4SurfaceFormat@2@HPEBEAEBU?$TVector2@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@6@@Z` at `0x1800552a9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180055526`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180055526`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180055250`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180055250`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180055246`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180055246`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z` at `0x1800552ed`
- `gfx!?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@AEAUIPlatformBitmap@ARC@@@Z` at `0x1800552ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall Mso::SVG::SVGCreatingCommandSink::GetEmbeddedImageForBitmap(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        float *a4,
        __m64 *a5,
        __int64 a6,
        int a7)
{
  bool v11; // bl
  float v12; // xmm8_4
  float v13; // xmm0_4
  int v14; // esi
  float v15; // xmm0_4
  int v16; // edx
  __int64 *v17; // rdi
  __int64 *v18; // rbx
  __int64 *v19; // rax
  __int64 *v20; // rcx
  __int64 v21; // rbx
  __int64 v22; // xmm6_8
  __int64 v23; // xmm7_8
  _QWORD *v24; // rax
  int v25; // r9d
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 *v28; // rcx
  __int64 v29; // rbx
  __int64 v30; // rsi
  float v31; // xmm6_4
  float v32; // xmm6_4
  __int64 **BitmapDownsampled; // rax
  __int64 *v34; // r14
  void (__fastcall *v35)(__int64, void (__fastcall ***)(_QWORD), unsigned __int64 *, __int64, int); // r14
  int v36; // ebx
  __int64 v37; // rax
  void (__fastcall ***v38)(_QWORD); // rbx
  __int64 v39; // rbx
  __int64 v40; // rbx
  double *v41; // r14
  __int64 v42; // rcx
  bool v43; // zf
  double v44; // rax
  __int64 v45; // rbx
  float v46; // xmm0_4
  float *v47; // rax
  float v48; // xmm7_4
  float v49; // xmm1_4
  _QWORD *v50; // rax
  int v51; // r9d
  __int64 v52; // rcx
  void *v53; // rdx
  __int64 v54; // rax
  __int64 *v55; // rax
  __int64 v56; // r14
  __int64 v57; // rcx
  __int64 v58; // rbx
  float v59; // xmm0_4
  float *v60; // rax
  float v61; // xmm7_4
  float v62; // xmm1_4
  _QWORD *v63; // rax
  int v64; // r9d
  __int64 v65; // rcx
  void (__fastcall ***v67)(_QWORD); // [rsp+48h] [rbp-C0h] BYREF
  double v68; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v69; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v70; // [rsp+60h] [rbp-A8h]
  __int64 v71; // [rsp+68h] [rbp-A0h]
  void (__fastcall ***v72)(_QWORD); // [rsp+70h] [rbp-98h]
  __int64 v73; // [rsp+78h] [rbp-90h] BYREF
  __m128d v74; // [rsp+80h] [rbp-88h] BYREF
  __m128d v75; // [rsp+90h] [rbp-78h]
  __m128d v76; // [rsp+A0h] [rbp-68h]
  void *Block[2]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v78; // [rsp+C0h] [rbp-48h]
  __int64 *v79; // [rsp+D0h] [rbp-38h]
  __int64 v80; // [rsp+D8h] [rbp-30h]
  __int64 v81; // [rsp+E0h] [rbp-28h]
  __int64 v82; // [rsp+178h] [rbp+70h] BYREF
  __int64 *v83; // [rsp+188h] [rbp+80h] BYREF
  unsigned __int64 v84; // [rsp+190h] [rbp+88h] BYREF

  v82 = a1;
  v11 = *a4 > a4[2];
  v12 = 0.0;
  if ( *a4 > a4[2] || a4[1] > a4[3] )
    v13 = 0.0;
  else
    v13 = a4[3] - a4[1];
  v14 = (int)ceilf_0(v13);
  if ( v11 || a4[1] > a4[3] )
    v15 = 0.0;
  else
    v15 = a4[2] - *a4;
  v16 = (int)ceilf_0(v15);
  v84 = __PAIR64__(v14, v16);
  v17 = a3;
  v79 = a3;
  if ( a3 )
  {
    (*(void (__fastcall **)(__int64 *))*a3)(a3);
    v14 = HIDWORD(v84);
    v16 = v84;
  }
  v18 = *(__int64 **)(a1 + 248);
  v19 = (__int64 *)v18[1];
  HIDWORD(v74.m128d_f64[1]) = 0;
  v20 = v18;
  if ( !*((_BYTE *)v19 + 25) )
  {
    do
    {
      if ( v19[4] >= (unsigned __int64)a3 )
        v18 = v19;
      else
        v19 += 2;
      v19 = (__int64 *)*v19;
    }
    while ( !*((_BYTE *)v19 + 25) );
    v20 = *(__int64 **)(a1 + 248);
  }
  if ( *((_BYTE *)v18 + 25) || (unsigned __int64)a3 < v18[4] )
    v18 = v20;
  if ( v18 == v20 )
  {
    v29 = (*(__int64 (__fastcall **)(__int64 *))(*a3 + 24))(a3);
    v30 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 **, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v29 + 176LL))(
                       v29,
                       &v83,
                       0xFFFFFFFFLL,
                       0,
                       0,
                       0);
    v80 = v30;
    (**(void (__fastcall ***)(__int64))v30)(v30);
    if ( v83 )
      (*(void (__fastcall **)(__int64 *))(*v83 + 8))(v83);
    v31 = *(float *)(a1 + 20);
    if ( *(float *)(*(__int64 (__fastcall **)(__int64 *, __m128d *))(*a3 + 72))(a3, &v74) > v31
      || (v32 = *(float *)(a1 + 24),
          *(float *)((*(__int64 (__fastcall **)(__int64 *, __m128d *))(*a3 + 72))(a3, &v74) + 4) > v32) )
    {
      BitmapDownsampled = (__int64 **)Mso::SVG::SVGCreatingCommandSink::GetBitmapDownsampled(
                                        a1,
                                        (unsigned int)&v74,
                                        (_DWORD)a3,
                                        (_DWORD)a4,
                                        a7,
                                        v29,
                                        v30,
                                        a6);
      v34 = *BitmapDownsampled;
      if ( a3 != *BitmapDownsampled )
      {
        *BitmapDownsampled = 0;
        (*(void (__fastcall **)(__int64 *))(*a3 + 8))(a3);
        v17 = v34;
        v79 = v34;
      }
      if ( *(_QWORD *)&v74.m128d_f64[0] )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v74.m128d_f64[0] + 8LL))(*(_QWORD *)&v74.m128d_f64[0]);
      if ( !v17 )
      {
        *a2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
        return a2;
      }
      v84 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64 *, __m128d *))(*v17 + 64))(v17, &v74);
    }
    (*(void (__fastcall **)(__int64, void (__fastcall ****)(_QWORD)))(*(_QWORD *)v29 + 256LL))(v29, &v67);
    v35 = *(void (__fastcall **)(__int64, void (__fastcall ***)(_QWORD), unsigned __int64 *, __int64, int))(*(_QWORD *)v30 + 256LL);
    v36 = (*(__int64 (__fastcall **)(__int64 *))(*v17 + 80))(v17);
    v37 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(*v17 + 72))(v17, &v83);
    v35(v30, v67, &v84, v37, v36);
    (*(void (__fastcall **)(__int64, void (__fastcall ***)(_QWORD), __int64 *))(*(_QWORD *)v30 + 768LL))(v30, v67, v17);
    *(_OWORD *)Block = 0;
    v78 = 0;
    v38 = v67;
    v68 = 0.0;
    v69 = 0;
    v70 = 0x800000000LL;
    v71 = v30;
    (**(void (__fastcall ***)(__int64))v30)(v30);
    v72 = v38;
    (**v38)(v38);
    v74.m128d_f64[0] = 0.0;
    LODWORD(v83) = 0;
    LODWORD(v35) = ((__int64 (__fastcall *)(_QWORD))(*v72)[10])(v72);
    v39 = *(_QWORD *)((__int64 (__fastcall *)(_QWORD))(*v72)[8])(v72);
    ((void (__fastcall *)(void (__fastcall ***)(_QWORD), __int64, _QWORD, __m128d *, __int64 **))(*v72)[11])(
      v72,
      v30,
      (unsigned int)v35,
      &v74,
      &v83);
    v68 = v74.m128d_f64[0];
    v69 = v39;
    v70 = __PAIR64__((unsigned int)v35, (unsigned int)v83);
    LODWORD(v83) = sub_180054560(&v68, Block);
    v40 = v82;
    v41 = (double *)(v82 + 264);
    std::_Tree<std::_Tmap_traits<std::vector<unsigned char> const,Ofc::TCntPtr<GEL::IImage>,std::less<std::vector<unsigned char> const>,std::allocator<std::pair<std::vector<unsigned char> const,Ofc::TCntPtr<GEL::IImage>>>,0>>::_Find_lower_bound<std::vector<unsigned char>>(
      v82 + 264,
      &v74,
      Block);
    v43 = (unsigned __int8)std::_Tree<std::_Tmap_traits<std::vector<unsigned char> const,Ofc::TCntPtr<GEL::IImage>,std::less<std::vector<unsigned char> const>,std::allocator<std::pair<std::vector<unsigned char> const,Ofc::TCntPtr<GEL::IImage>>>,0>>::_Lower_bound_duplicate<std::vector<unsigned char>>(
                             v42,
                             *(_QWORD *)&v75.m128d_f64[0],
                             Block) == 0;
    v44 = v75.m128d_f64[0];
    if ( v43 )
      v44 = *v41;
    if ( *(_QWORD *)&v44 == *(_QWORD *)v41 )
    {
      v54 = (*(__int64 (__fastcall **)(__int64 *, __m128d *))(*v17 + 72))(v17, &v74);
      v55 = (__int64 *)ARC::IPlatformBitmap::Create(
                         &v82,
                         &v69,
                         (unsigned int)v83,
                         (unsigned int)v70,
                         *(_QWORD *)&v68,
                         v54);
      v56 = *v55;
      v81 = v56;
      if ( !v56 )
      {
        CrashWithRecovery(0x1E3CB504u, 0);
        JUMPOUT(0x18005552CLL);
      }
      *v55 = 0;
      v57 = v82;
      if ( v82 )
      {
        v82 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 8LL))(v57);
      }
      GEL::IImage::Create(&v73, v56);
      v83 = a3;
      (*(void (__fastcall **)(__int64 *))*a3)(a3);
      std::_Tree<std::_Tmap_traits<ARC::TPtr<ARC::IBitmap const>,Ofc::TCntPtr<GEL::IImage>,std::less<ARC::TPtr<ARC::IBitmap const>>,std::allocator<std::pair<ARC::TPtr<ARC::IBitmap const> const,Ofc::TCntPtr<GEL::IImage>>>,0>>::emplace<ARC::TPtr<ARC::IBitmap const> &,Ofc::TCntPtr<GEL::IImage> &>(
        v40 + 248,
        &v74,
        &v83,
        &v73);
      if ( Block[0] != Block[1] )
        std::_Tree<std::_Tmap_traits<std::vector<unsigned char> const,Ofc::TCntPtr<GEL::IImage>,std::less<std::vector<unsigned char> const>,std::allocator<std::pair<std::vector<unsigned char> const,Ofc::TCntPtr<GEL::IImage>>>,0>>::emplace<std::vector<unsigned char> &,Ofc::TCntPtr<GEL::IImage> &>(
          v40 + 264,
          &v74,
          Block,
          &v73);
      v58 = v73;
      v59 = a4[1];
      v60 = a4 + 3;
      v61 = v59;
      if ( *a4 > a4[2] || v59 > *v60 )
        v62 = 0.0;
      else
        v62 = *v60 - a4[1];
      if ( *a4 <= a4[2] )
      {
        v61 = a4[1];
        if ( v59 <= *v60 )
          v12 = a4[2] - *a4;
      }
      v74 = _mm_cvtps_pd((__m64)a5->m64_u64);
      v75 = _mm_cvtps_pd(a5[1]);
      v76 = _mm_cvtps_pd(a5[2]);
      v63 = (_QWORD *)Mso::SVG::ISVGStyleProps::Create(&v82);
      Mso::SVG::ISVGEmbeddedImage::Create(
        (_DWORD)a2,
        *v63,
        (unsigned int)&v74,
        v64,
        COERCE__INT64(v61),
        COERCE__INT64(v12),
        COERCE__INT64(v62),
        v58);
      v65 = v82;
      if ( v82 )
      {
        v82 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 8LL))(v65);
      }
      if ( v83 )
        (*(void (__fastcall **)(__int64 *))(*v83 + 8))(v83);
      if ( v73 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 8LL))(v73);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 8LL))(v56);
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD), __int64))(*v72)[12])(v72, v71);
      (*v72)[1](v72);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 8LL))(v71);
      std::vector<char>::~vector<char>(Block);
    }
    else
    {
      v45 = *(_QWORD *)(*(_QWORD *)&v44 + 56LL);
      v46 = a4[1];
      v47 = a4 + 3;
      v48 = v46;
      if ( *a4 > a4[2] || v46 > *v47 )
        v49 = 0.0;
      else
        v49 = *v47 - a4[1];
      if ( *a4 <= a4[2] )
      {
        v48 = a4[1];
        if ( v46 <= *v47 )
          v12 = a4[2] - *a4;
      }
      v74 = _mm_cvtps_pd((__m64)a5->m64_u64);
      v75 = _mm_cvtps_pd(a5[1]);
      v76 = _mm_cvtps_pd(a5[2]);
      v50 = (_QWORD *)Mso::SVG::ISVGStyleProps::Create(&v82);
      Mso::SVG::ISVGEmbeddedImage::Create(
        (_DWORD)a2,
        *v50,
        (unsigned int)&v74,
        v51,
        COERCE__INT64(v48),
        COERCE__INT64(v12),
        COERCE__INT64(v49),
        v45);
      v52 = v82;
      if ( v82 )
      {
        v82 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
      }
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD), __int64))(*v72)[12])(v72, v71);
      (*v72)[1](v72);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 8LL))(v71);
      v53 = Block[0];
      if ( Block[0] )
      {
        if ( v78 - (unsigned __int64)Block[0] >= 0x1000 )
        {
          v53 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v53 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v53);
      }
      *(__m128i *)Block = _mm_load_si128((const __m128i *)&_xmm);
      v78 = 19937;
    }
    if ( v67 )
      (*v67)[1](v67);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 8LL))(v30);
    v28 = v17;
    v27 = *v17;
    goto LABEL_76;
  }
  v21 = v18[5];
  *(double *)&v22 = (double)v16;
  *(double *)&v23 = a4[1];
  v74 = _mm_cvtps_pd((__m64)a5->m64_u64);
  v75 = _mm_cvtps_pd(a5[1]);
  v76 = _mm_cvtps_pd(a5[2]);
  v24 = (_QWORD *)Mso::SVG::ISVGStyleProps::Create(&v82);
  Mso::SVG::ISVGEmbeddedImage::Create(
    (_DWORD)a2,
    *v24,
    (unsigned int)&v74,
    v25,
    v23,
    v22,
    COERCE__INT64((double)v14),
    v21);
  v26 = v82;
  if ( v82 )
  {
    v82 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
  }
  if ( a3 )
  {
    v27 = *a3;
    v28 = a3;
LABEL_76:
    (*(void (__fastcall **)(__int64 *))(v27 + 8))(v28);
  }
  return a2;
}

```

## disassembly

```asm
0x180054bec  mov     rax, rsp
0x180054bef  mov     [rax+10h], rbx
0x180054bf3  mov     [rax+8], rcx
0x180054bf7  push    rbp
0x180054bf8  push    rsi
0x180054bf9  push    rdi
0x180054bfa  push    r12
0x180054bfc  push    r13
0x180054bfe  push    r14
0x180054c00  push    r15
0x180054c02  lea     rbp, [rax-68h]
0x180054c06  sub     rsp, 130h
0x180054c0d  movaps  xmmword ptr [rax-48h], xmm6
0x180054c11  movaps  xmmword ptr [rax-58h], xmm7
0x180054c15  movaps  xmmword ptr [rax-68h], xmm8
0x180054c1a  movaps  xmmword ptr [rax-78h], xmm9
0x180054c1f  movaps  xmmword ptr [rax-88h], xmm10
0x180054c27  mov     r15, r9
0x180054c2a  mov     r12, r8
0x180054c2d  mov     r13, rdx
0x180054c30  mov     r14, rcx
0x180054c33  movss   xmm0, dword ptr [r9]
0x180054c38  comiss  xmm0, dword ptr [r9+8]
0x180054c3d  setnbe  al
0x180054c40  mov     bl, al
0x180054c42  xorps   xmm8, xmm8
0x180054c46  test    al, al
0x180054c48  jnz     short loc_180054C65
0x180054c4a  movss   xmm0, dword ptr [r9+4]
0x180054c50  comiss  xmm0, dword ptr [r9+0Ch]
0x180054c55  ja      short loc_180054C65
0x180054c57  movss   xmm0, dword ptr [r9+0Ch]
0x180054c5d  subss   xmm0, dword ptr [r9+4]
0x180054c63  jmp     short loc_180054C68
0x180054c65  xorps   xmm0, xmm0; X
0x180054c68  call    ceilf_0
0x180054c6d  movss   xmm6, cs:__real@4f800000
0x180054c75  cvttss2si rsi, xmm0
0x180054c7a  test    bl, bl
0x180054c7c  jnz     short loc_180054C98
0x180054c7e  movss   xmm0, dword ptr [r15+4]
0x180054c84  comiss  xmm0, dword ptr [r15+0Ch]
0x180054c89  ja      short loc_180054C98
0x180054c8b  movss   xmm0, dword ptr [r15+8]
0x180054c91  subss   xmm0, dword ptr [r15]
0x180054c96  jmp     short loc_180054C9B
0x180054c98  xorps   xmm0, xmm0; X
0x180054c9b  call    ceilf_0
0x180054ca0  cvttss2si rdx, xmm0
0x180054ca5  mov     dword ptr [rbp+60h+arg_18], edx
0x180054cab  mov     dword ptr [rbp+60h+arg_18+4], esi
0x180054cb1  mov     rdi, r12
0x180054cb4  mov     [rbp+60h+var_98], r12
0x180054cb8  test    r12, r12
0x180054cbb  jz      short loc_180054CD9
0x180054cbd  mov     rax, [r12]
0x180054cc1  mov     rcx, r12
0x180054cc4  mov     rax, [rax]
0x180054cc7  call    cs:__guard_dispatch_icall_fptr
0x180054ccd  mov     esi, dword ptr [rbp+60h+arg_18+4]
0x180054cd3  mov     edx, dword ptr [rbp+60h+arg_18]
0x180054cd9  mov     rbx, [r14+0F8h]
0x180054ce0  mov     rax, [rbx+8]
0x180054ce4  xor     ecx, ecx
0x180054ce6  mov     [rbp+60h+var_DC], ecx
0x180054ce9  mov     rcx, rbx
0x180054cec  cmp     byte ptr [rax+19h], 0
0x180054cf0  jnz     short loc_180054D11
0x180054cf2  cmp     [rax+20h], r12
0x180054cf6  jnb     short loc_180054CFE
0x180054cf8  add     rax, 10h
0x180054cfc  jmp     short loc_180054D01
0x180054cfe  mov     rbx, rax
0x180054d01  mov     rax, [rax]
0x180054d04  cmp     byte ptr [rax+19h], 0
0x180054d08  jz      short loc_180054CF2
0x180054d0a  mov     rcx, [r14+0F8h]
0x180054d11  cmp     byte ptr [rbx+19h], 0
0x180054d15  jnz     short loc_180054D1D
0x180054d17  cmp     r12, [rbx+20h]
0x180054d1b  jnb     short loc_180054D20
0x180054d1d  mov     rbx, rcx
0x180054d20  cmp     rbx, rcx
0x180054d23  jz      loc_180054DDC
0x180054d29  mov     rbx, [rbx+28h]
0x180054d2d  mov     eax, esi
0x180054d2f  xorps   xmm9, xmm9
0x180054d33  cvtsi2sd xmm9, rax
0x180054d38  mov     eax, edx
0x180054d3a  xorps   xmm6, xmm6
0x180054d3d  cvtsi2sd xmm6, rax
0x180054d42  movss   xmm7, dword ptr [r15+4]
0x180054d48  cvtps2pd xmm7, xmm7
0x180054d4b  movss   xmm8, dword ptr [r15]
0x180054d50  cvtps2pd xmm8, xmm8
0x180054d54  mov     rax, [rbp+60h+arg_20]
0x180054d5b  cvtps2pd xmm0, qword ptr [rax]
0x180054d5e  movups  [rsp+160h+var_F0+8], xmm0
0x180054d63  cvtps2pd xmm0, qword ptr [rax+8]
0x180054d67  movups  [rbp+60h+var_D8], xmm0
0x180054d6b  cvtps2pd xmm0, qword ptr [rax+10h]
0x180054d6f  movups  [rbp+60h+var_C8], xmm0
0x180054d73  lea     rcx, [rbp+60h+arg_0]
0x180054d77  call    ?Create@ISVGStyleProps@SVG@Mso@@SA?AV?$TCntPtr@UISVGStyleProps@SVG@Mso@@@3@XZ; Mso::SVG::ISVGStyleProps::Create(void)
0x180054d7c  mov     [rsp+160h+var_128], rbx
0x180054d81  movsd   [rsp+160h+var_130], xmm9
0x180054d88  movsd   [rsp+160h+var_138], xmm6
0x180054d8e  movsd   [rsp+160h+Reserved], xmm7
0x180054d94  movaps  xmm3, xmm8
0x180054d98  lea     r8, [rsp+160h+var_F0+8]
0x180054d9d  mov     rdx, [rax]
0x180054da0  mov     rcx, r13
0x180054da3  call    ?Create@ISVGEmbeddedImage@SVG@Mso@@SA?AV?$TCntPtr@UISVGEmbeddedImage@SVG@Mso@@@3@PEAUISVGStyleProps@23@AEBU?$TAffine3x3@N@Math@@NNNNPEBUIImage@GEL@@@Z; Mso::SVG::ISVGEmbeddedImage::Create(Mso::SVG::ISVGStyleProps *,Math::TAffine3x3<double> const &,double,double,double,double,GEL::IImage const *)
0x180054da8  mov     rcx, [rbp+60h+arg_0]
0x180054dac  test    rcx, rcx
0x180054daf  jz      short loc_180054DC7
0x180054db1  mov     [rbp+60h+arg_0], 0
0x180054db9  mov     rax, [rcx]
0x180054dbc  mov     rax, [rax+8]
0x180054dc0  call    cs:__guard_dispatch_icall_fptr
0x180054dc6  nop
0x180054dc7  test    r12, r12
0x180054dca  jz      loc_1800554E8
0x180054dd0  mov     rax, [r12]
0x180054dd4  mov     rcx, r12
0x180054dd7  jmp     loc_1800554DE
0x180054ddc  mov     rax, [r12]
0x180054de0  mov     rcx, r12
0x180054de3  mov     rax, [rax+18h]
0x180054de7  call    cs:__guard_dispatch_icall_fptr
0x180054ded  mov     rbx, rax
0x180054df0  mov     rcx, [rax]
0x180054df3  mov     rax, [rcx+0B0h]
0x180054dfa  mov     [rsp+160h+var_138], 0
0x180054e03  mov     [rsp+160h+Reserved], 0
0x180054e0c  xor     r9d, r9d
0x180054e0f  or      r8d, 0FFFFFFFFh
0x180054e13  lea     rdx, [rbp+60h+arg_10]
0x180054e1a  mov     rcx, rbx
0x180054e1d  call    cs:__guard_dispatch_icall_fptr
0x180054e23  mov     rsi, [rax]
0x180054e26  mov     [rbp+60h+var_90], rsi
0x180054e2a  mov     rax, [rsi]
0x180054e2d  mov     rcx, rsi
0x180054e30  mov     rax, [rax]
0x180054e33  call    cs:__guard_dispatch_icall_fptr
0x180054e39  nop
0x180054e3a  mov     rcx, [rbp+60h+arg_10]
0x180054e41  test    rcx, rcx
0x180054e44  jz      short loc_180054E53
0x180054e46  mov     rax, [rcx]
0x180054e49  mov     rax, [rax+8]
0x180054e4d  call    cs:__guard_dispatch_icall_fptr
0x180054e53  movss   xmm6, dword ptr [r14+14h]
0x180054e59  mov     rax, [r12]
0x180054e5d  lea     rdx, [rsp+160h+var_F0+8]
0x180054e62  mov     rcx, r12
0x180054e65  mov     rax, [rax+48h]
0x180054e69  call    cs:__guard_dispatch_icall_fptr
0x180054e6f  movss   xmm0, dword ptr [rax]
0x180054e73  comiss  xmm0, xmm6
0x180054e76  ja      short loc_180054EA2
0x180054e78  movss   xmm6, dword ptr [r14+18h]
0x180054e7e  mov     rax, [r12]
0x180054e82  lea     rdx, [rsp+160h+var_F0+8]
0x180054e87  mov     rcx, r12
0x180054e8a  mov     rax, [rax+48h]
0x180054e8e  call    cs:__guard_dispatch_icall_fptr
0x180054e94  movss   xmm0, dword ptr [rax+4]
0x180054e99  comiss  xmm0, xmm6
0x180054e9c  jbe     loc_180054F50
0x180054ea2  mov     rax, [rbp+60h+arg_28]
0x180054ea9  mov     [rsp+160h+var_128], rax
0x180054eae  mov     [rsp+160h+var_130], rsi
0x180054eb3  mov     [rsp+160h+var_138], rbx
0x180054eb8  mov     eax, [rbp+60h+arg_30]
0x180054ebe  mov     dword ptr [rsp+160h+Reserved], eax
0x180054ec2  mov     r9, r15
0x180054ec5  mov     r8, r12
0x180054ec8  lea     rdx, [rsp+160h+var_F0+8]
0x180054ecd  mov     rcx, r14
0x180054ed0  call    ?GetBitmapDownsampled@SVGCreatingCommandSink@SVG@Mso@@AEAA?AV?$TPtr@UIBitmap@ARC@@@ARC@@AEBUIBitmap@5@AEBU?$TRect@V?$TUnits@MUDevicePixels@Math@@@Math@@@Math@@W4InterpolationMode@5@AEAUIFactory@5@AEAUIDeviceContext@5@PEBU?$TAffine3x3@M@8@@Z; Mso::SVG::SVGCreatingCommandSink::GetBitmapDownsampled(ARC::IBitmap const &,Math::TRect<Math::TUnits<float,Math::DevicePixels>> const &,ARC::InterpolationMode,ARC::IFactory &,ARC::IDeviceContext &,Math::TAffine3x3<float> const *)
0x180054ed5  mov     r14, [rax]
0x180054ed8  cmp     r12, r14
0x180054edb  jz      short loc_180054EFC
0x180054edd  mov     qword ptr [rax], 0
0x180054ee4  mov     rax, [r12]
0x180054ee8  mov     rcx, r12
0x180054eeb  mov     rax, [rax+8]
0x180054eef  call    cs:__guard_dispatch_icall_fptr
0x180054ef5  mov     rdi, r14
0x180054ef8  mov     [rbp+60h+var_98], r14
0x180054efc  mov     rcx, qword ptr [rsp+160h+var_F0+8]
0x180054f01  test    rcx, rcx
0x180054f04  jz      short loc_180054F13
0x180054f06  mov     rax, [rcx]
0x180054f09  mov     rax, [rax+8]
0x180054f0d  call    cs:__guard_dispatch_icall_fptr
0x180054f13  test    rdi, rdi
0x180054f16  jnz     short loc_180054F31
0x180054f18  mov     [r13+0], rdi
0x180054f1c  mov     rax, [rsi]
0x180054f1f  mov     rcx, rsi
0x180054f22  mov     rax, [rax+8]
0x180054f26  call    cs:__guard_dispatch_icall_fptr
0x180054f2c  jmp     loc_1800554E8
0x180054f31  mov     rax, [rdi]
0x180054f34  lea     rdx, [rsp+160h+var_F0+8]
0x180054f39  mov     rcx, rdi
0x180054f3c  mov     rax, [rax+40h]
0x180054f40  call    cs:__guard_dispatch_icall_fptr
0x180054f46  mov     rcx, [rax]
0x180054f49  mov     [rbp+60h+arg_18], rcx
0x180054f50  mov     rax, [rbx]
0x180054f53  lea     rdx, [rsp+160h+var_120]
0x180054f58  mov     rcx, rbx
0x180054f5b  mov     rax, [rax+100h]
0x180054f62  call    cs:__guard_dispatch_icall_fptr
0x180054f68  nop
0x180054f69  mov     rax, [rsi]
0x180054f6c  mov     r14, [rax+100h]
0x180054f73  mov     rax, [rdi]
0x180054f76  mov     rcx, rdi
0x180054f79  mov     rax, [rax+50h]
0x180054f7d  call    cs:__guard_dispatch_icall_fptr
0x180054f83  mov     ebx, eax
0x180054f85  mov     rcx, [rdi]
0x180054f88  mov     rax, [rcx+48h]
0x180054f8c  lea     rdx, [rbp+60h+arg_10]
0x180054f93  mov     rcx, rdi
0x180054f96  call    cs:__guard_dispatch_icall_fptr
0x180054f9c  mov     dword ptr [rsp+160h+Reserved], ebx
0x180054fa0  mov     r9, rax
0x180054fa3  lea     r8, [rbp+60h+arg_18]
0x180054faa  mov     rdx, [rsp+160h+var_120]
0x180054faf  mov     rcx, rsi
0x180054fb2  mov     rax, r14
0x180054fb5  call    cs:__guard_dispatch_icall_fptr
0x180054fbb  mov     rax, [rsi]
0x180054fbe  mov     r8, rdi
0x180054fc1  mov     rdx, [rsp+160h+var_120]
0x180054fc6  mov     rcx, rsi
0x180054fc9  mov     rax, [rax+300h]
0x180054fd0  call    cs:__guard_dispatch_icall_fptr
0x180054fd6  xorps   xmm0, xmm0
0x180054fd9  movdqu  xmmword ptr [rbp+60h+Block], xmm0
0x180054fde  xor     r14d, r14d
0x180054fe1  mov     [rbp+60h+var_A8], r14
0x180054fe5  mov     rbx, [rsp+160h+var_120]
0x180054fea  mov     [rsp+160h+var_118], r14
0x180054fef  mov     [rsp+160h+var_110], r14
0x180054ff4  mov     dword ptr [rsp+160h+var_108], r14d
0x180054ff9  mov     dword ptr [rsp+160h+var_108+4], 8
0x180055001  mov     [rsp+160h+var_100], rsi
0x180055006  mov     rax, [rsi]
0x180055009  mov     rcx, rsi
0x18005500c  mov     rax, [rax]
0x18005500f  call    cs:__guard_dispatch_icall_fptr
0x180055015  mov     [rsp+160h+var_F8], rbx
0x18005501a  mov     rax, [rbx]
0x18005501d  mov     rcx, rbx
0x180055020  mov     rax, [rax]
0x180055023  call    cs:__guard_dispatch_icall_fptr
0x180055029  mov     qword ptr [rsp+160h+var_F0+8], r14
0x18005502e  mov     dword ptr [rbp+60h+arg_10], r14d
0x180055035  mov     rcx, [rsp+160h+var_F8]
0x18005503a  mov     rax, [rcx]
0x18005503d  mov     rax, [rax+50h]
0x180055041  call    cs:__guard_dispatch_icall_fptr
0x180055047  mov     r14d, eax
0x18005504a  mov     rcx, [rsp+160h+var_F8]
0x18005504f  mov     rdx, [rcx]
0x180055052  mov     rax, [rdx+40h]
0x180055056  call    cs:__guard_dispatch_icall_fptr
0x18005505c  mov     rbx, [rax]
0x18005505f  mov     rcx, [rsp+160h+var_F8]
0x180055064  mov     rdx, [rcx]
0x180055067  mov     rax, [rdx+58h]
0x18005506b  lea     rdx, [rbp+60h+arg_10]
0x180055072  mov     [rsp+160h+Reserved], rdx
0x180055077  lea     r9, [rsp+160h+var_F0+8]
0x18005507c  mov     r8d, r14d
0x18005507f  mov     rdx, rsi
0x180055082  call    cs:__guard_dispatch_icall_fptr
0x180055088  mov     rax, qword ptr [rsp+160h+var_F0+8]
0x18005508d  mov     [rsp+160h+var_118], rax
0x180055092  mov     [rsp+160h+var_110], rbx
0x180055097  mov     eax, dword ptr [rbp+60h+arg_10]
0x18005509d  mov     dword ptr [rsp+160h+var_108], eax
0x1800550a1  mov     dword ptr [rsp+160h+var_108+4], r14d
0x1800550a6  lea     rdx, [rbp+60h+Block]
0x1800550aa  lea     rcx, [rsp+160h+var_118]
0x1800550af  call    sub_180054560
0x1800550b4  mov     dword ptr [rbp+60h+arg_10], eax
0x1800550ba  mov     rbx, [rbp+60h+arg_0]
0x1800550be  lea     r14, [rbx+108h]
0x1800550c5  lea     r8, [rbp+60h+Block]
0x1800550c9  lea     rdx, [rsp+160h+var_F0+8]
0x1800550ce  mov     rcx, r14
0x1800550d1  call    ??$_Find_lower_bound@V?$vector@EV?$allocator@E@std@@@std@@@?$_Tree@V?$_Tmap_traits@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$TCntPtr@UIImage@GEL@@@Ofc@@U?$less@$$CBV?$vector@EV?$allocator@E@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$TCntPtr@UIImage@GEL@@@Ofc@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$vector@EV?$allocator@E@std@@@std@@V?$TCntPtr@UIImage@GEL@@@Ofc@@@std@@PEAX@std@@@1@AEBV?$vector@EV?$allocator@E@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::vector<uchar> const,Ofc::TCntPtr<GEL::IImage>,std::less<std::vector<uchar> const>,std::allocator<std::pair<std::vector<uchar> const,Ofc::TCntPtr<GEL::IImage>>>,0>>::_Find_lower_bound<std::vector<uchar>>(std::vector<uchar> const &)
  ... truncated ...
```
