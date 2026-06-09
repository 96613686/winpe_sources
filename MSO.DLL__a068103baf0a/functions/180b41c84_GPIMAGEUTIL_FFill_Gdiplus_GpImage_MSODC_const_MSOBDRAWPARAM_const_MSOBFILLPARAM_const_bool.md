# GPIMAGEUTIL::FFill(Gdiplus::GpImage &,MSODC const *,MSOBDRAWPARAM const *,MSOBFILLPARAM const *,bool)

- ea: `0x180b41c84`
- end: `0x180b4248c`
- name: `?FFill@GPIMAGEUTIL@@SAHAEAVGpImage@Gdiplus@@PEBUMSODC@@PEBUMSOBDRAWPARAM@@PEBUMSOBFILLPARAM@@_N@Z`
- size: `2056`
- prototype: `__int64 __usercall@<rax>(struct Gdiplus::GpImage *@<rcx>, const struct MSODC *@<rdx>, const struct MSOBDRAWPARAM *this@<r8>, const struct MSOBFILLPARAM *@<r9>, bool)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180228714`

## callees

- `0x1800fd43c`
- `0x1800fd498`
- `0x1800fd560`
- `0x1800fd5f0`
- `0x1800fd6e8`
- `0x1800fe2d0`
- `0x180239a7c`
- `0x18023c2e0`
- `0x180832b30`
- `0x1809db02c`
- `0x180b41c84`
- `0x180b42490`
- `0x180be5190`
- `0x1812d2020`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180b4243a`
- `KERNEL32!SetLastError` at `0x180b4243a`
- `mso40uiWin32Client!__imp_?FSetClipPath@MSODC@@AEBA_NPEAVGpPath@Gdiplus@@PEAVMSOCLIPPATHSAVER@@_N@Z` at `0x180b42400`
- `mso40uiWin32Client!__imp_?FSetClipPath@MSODC@@AEBA_NPEAVGpPath@Gdiplus@@PEAVMSOCLIPPATHSAVER@@_N@Z` at `0x180b42427`
- `mso40uiWin32Client!__imp_?FSetClipPath@MSODC@@AEBA_NPEAVGpPath@Gdiplus@@PEAVMSOCLIPPATHSAVER@@_N@Z` at `0x180b42400`
- `mso40uiWin32Client!__imp_?FSetClipPath@MSODC@@AEBA_NPEAVGpPath@Gdiplus@@PEAVMSOCLIPPATHSAVER@@_N@Z` at `0x180b42427`
- `mso40uiWin32Client!__imp_??0FPState@@QEAA@K@Z` at `0x180b41d84`
- `mso40uiWin32Client!__imp_??0FPState@@QEAA@K@Z` at `0x180b41d84`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180b422b9`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180b423c2`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180b422b9`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180b423c2`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b41d8d`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b421f5`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b4222e`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b422d4`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b422fd`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b42345`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b42393`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b41d8d`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b421f5`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b4222e`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b422d4`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b422fd`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b42345`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b42393`
- `gdiplus!GdipDisposeImage` at `0x180b42257`
- `gdiplus!GdipDisposeImage` at `0x180b42257`
- `gdiplus!GdipDeleteGraphics` at `0x180b42266`
- `gdiplus!GdipDeleteGraphics` at `0x180b42266`
- `gdiplus!GdipGetImageWidth` at `0x180b41dc0`
- `gdiplus!GdipGetImageWidth` at `0x180b41dc0`
- `gdiplus!GdipGetImageHeight` at `0x180b41dd6`
- `gdiplus!GdipGetImageHeight` at `0x180b41dd6`
- `gdiplus!GdipGetImageType` at `0x180b41d13`
- `gdiplus!GdipGetImageType` at `0x180b41d13`
- `gdiplus!GdipCreateMatrix2` at `0x180b41fc5`
- `gdiplus!GdipCreateMatrix2` at `0x180b41fc5`
- `gdiplus!GdipDeleteMatrix` at `0x180b42275`
- `gdiplus!GdipDeleteMatrix` at `0x180b42275`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180b42137`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180b42137`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180b42124`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180b42124`
- `gdiplus!GdipDeleteBrush` at `0x180b42285`
- `gdiplus!GdipDeleteBrush` at `0x180b42295`
- `gdiplus!GdipDeleteBrush` at `0x180b42285`
- `gdiplus!GdipDeleteBrush` at `0x180b42295`
- `gdiplus!GdipCreateSolidFill` at `0x180b42072`
- `gdiplus!GdipCreateSolidFill` at `0x180b42072`
- `gdiplus!GdipFillRectangle` at `0x180b42365`
- `gdiplus!GdipFillRectangle` at `0x180b423b3`
- `gdiplus!GdipFillRectangle` at `0x180b42365`
- `gdiplus!GdipFillRectangle` at `0x180b423b3`
- `gdiplus!GdipGetImageRawFormat` at `0x180b420bd`
- `gdiplus!GdipGetImageRawFormat` at `0x180b420bd`
- `gdiplus!GdipGetImagePixelFormat` at `0x180b420f0`
- `gdiplus!GdipGetImagePixelFormat` at `0x180b420f0`
- `gdiplus!GdipDeletePen` at `0x180b422a5`
- `gdiplus!GdipDeletePen` at `0x180b422a5`
- `gdiplus!GdipDisposeImageAttributes` at `0x180b422af`
- `gdiplus!GdipDisposeImageAttributes` at `0x180b422af`
- `gdiplus!GdipDrawPath` at `0x180b42204`
- `gdiplus!GdipDrawPath` at `0x180b4223d`
- `gdiplus!GdipDrawPath` at `0x180b42204`
- `gdiplus!GdipDrawPath` at `0x180b4223d`
- `gdiplus!GdipFillPath` at `0x180b422e3`
- `gdiplus!GdipFillPath` at `0x180b4230c`
- `gdiplus!GdipFillPath` at `0x180b422e3`
- `gdiplus!GdipFillPath` at `0x180b4230c`
- `gdiplus!GdipSetTextureTransform` at `0x180b421a1`
- `gdiplus!GdipSetTextureTransform` at `0x180b421a1`
- `gdiplus!GdipClonePen` at `0x180b421c6`
- `gdiplus!GdipClonePen` at `0x180b421c6`
- `gdiplus!GdipDrawImageI` at `0x180b4214e`
- `gdiplus!GdipDrawImageI` at `0x180b4214e`
- `gdiplus!GdipCreateTextureIA` at `0x180b42182`
- `gdiplus!GdipCreateTextureIA` at `0x180b42182`
- `gdiplus!GdipSetPenBrushFill` at `0x180b421df`
- `gdiplus!GdipSetPenBrushFill` at `0x180b42218`
- `gdiplus!GdipSetPenBrushFill` at `0x180b421df`
- `gdiplus!GdipSetPenBrushFill` at `0x180b42218`

## pseudocode

```c
__int64 __fastcall GPIMAGEUTIL::FFill(
        struct Gdiplus::GpImage *a1,
        const struct MSODC *a2,
        const struct MSOBDRAWPARAM *this,
        struct Gdiplus::GpPath **a4,
        bool a5)
{
  struct Gdiplus::GpImage *v8; // rbx
  int v9; // ecx
  __int32 v10; // xmm6_4
  const struct MSOBDRAWPOS *v11; // r8
  float v12; // xmm12_4
  float v13; // xmm9_4
  float v14; // xmm8_4
  float v15; // xmm7_4
  bool v16; // r15
  __m128i si128; // xmm13
  __m128i v18; // xmm14
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int32 v22; // xmm0_4
  unsigned int v23; // r12d
  unsigned int v24; // r15d
  int v25; // eax
  struct Gdiplus::GpPath *v26; // rdi
  struct Gdiplus::GpPath *v27; // rcx
  struct Gdiplus::GpPath *v28; // rbx
  __int64 v29; // rdi
  struct Gdiplus::GpGraphics *v30; // rax
  struct Gdiplus::GpPath *v31; // rbx
  __int64 v32; // rdi
  struct Gdiplus::GpGraphics *v33; // rax
  int v34; // eax
  __int64 v36; // rbx
  struct Gdiplus::GpGraphics *v37; // rax
  struct Gdiplus::GpPath *v38; // rbx
  __int64 v39; // rdi
  struct Gdiplus::GpGraphics *v40; // rax
  __int64 v41; // rbx
  struct Gdiplus::GpGraphics *v42; // rax
  __int64 v43; // rbx
  struct Gdiplus::GpGraphics *v44; // rax
  int v45; // ebx
  float v46; // [rsp+28h] [rbp-E0h]
  int v47; // [rsp+48h] [rbp-C0h] BYREF
  int v48; // [rsp+4Ch] [rbp-BCh] BYREF
  __int64 v49; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v50; // [rsp+58h] [rbp-B0h]
  __int64 v51; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v52; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v53; // [rsp+70h] [rbp-98h] BYREF
  struct Gdiplus::GpImage *v54; // [rsp+78h] [rbp-90h] BYREF
  __m256i v55; // [rsp+88h] [rbp-80h] BYREF
  double v56; // [rsp+A8h] [rbp-60h]
  double v57; // [rsp+B0h] [rbp-58h]
  __int128 v58; // [rsp+B8h] [rbp-50h]
  __int64 v59; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v60; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD v61[2]; // [rsp+D8h] [rbp-30h] BYREF
  _OWORD v62[4]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 Buf1; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v64[2032]; // [rsp+138h] [rbp+30h] BYREF

  v8 = a1;
  if ( !a2 || !this || !a4 )
  {
    SetLastError(0xE0040057);
    return 0;
  }
  LODWORD(v49) = 0;
  if ( (unsigned int)GdipGetImageType(a1, &v49) )
    return 0;
  if ( *((_DWORD *)this + 42)
    || ((v9 = *((_DWORD *)a2 + 20) & 0x70000, ((v9 - 327680) & 0xFFFEFFFF) == 0) && a4[3] || (_DWORD)v49 == 2)
    && !*((_DWORD *)a4 + 4)
    && (!a4[1] || (_DWORD)v49 == 2)
    && (v9 != 393216 || !a5) )
  {
    v55.m256i_i64[0] = (__int64)a2;
    memset(&v55.m256i_u64[1], 0, 17);
    if ( MSOCLIPPATHSAVER::FApplyClipPath((MSOCLIPPATHSAVER *)&v55, a4[3]) )
    {
      v45 = GPIMAGEUTIL::FDraw(v8, a2, this);
      return v45
           & (unsigned int)-MSODC::FSetClipPath(
                              (MSODC *)v55.m256i_i64[0],
                              (struct Gdiplus::GpPath *)v55.m256i_i64[1],
                              (struct MSOCLIPPATHSAVER *)&v55,
                              0);
    }
    if ( v55.m256i_i8[24] )
      MSODC::FSetClipPath(
        (MSODC *)v55.m256i_i64[0],
        (struct Gdiplus::GpPath *)v55.m256i_i64[1],
        (struct MSOCLIPPATHSAVER *)&v55,
        0);
    return 0;
  }
  FPState::FPState((FPState *)v64, 0);
  if ( !MSODC::Pgraphics(a2) )
    goto LABEL_82;
  GPIMAGEUTIL::SelectActiveFrameFromCache(v8, a2, this);
  v60 = 0;
  v48 = 0;
  v47 = 0;
  if ( (unsigned int)GdipGetImageWidth(v8, &v48) || (unsigned int)GdipGetImageHeight(v8, &v47) )
    goto LABEL_82;
  v10 = 0;
  v55.m256i_i64[0] = 0;
  *(float *)&v55.m256i_i32[2] = (float)v48;
  *(float *)&v55.m256i_i32[3] = (float)v47;
  if ( (_DWORD)v49 == 2 )
    sub_1812D2020(&v55, a2, this, v64);
  else
    GPIMAGEUTIL::ApplyCrop(this, (struct Gdiplus::RectF *)&v55);
  v12 = *(float *)v55.m256i_i32;
  v13 = *(float *)&v55.m256i_i32[1];
  v14 = *(float *)&v55.m256i_i32[2];
  v15 = *(float *)&v55.m256i_i32[3];
  if ( *(float *)v55.m256i_i32 < 0.0 )
  {
    v14 = *(float *)v55.m256i_i32 + *(float *)&v55.m256i_i32[2];
    v12 = 0.0;
  }
  v16 = *(float *)v55.m256i_i32 < 0.0;
  if ( *(float *)&v55.m256i_i32[1] < 0.0 )
  {
    v15 = *(float *)&v55.m256i_i32[3] + *(float *)&v55.m256i_i32[1];
    v13 = 0.0;
    v16 = 1;
  }
  if ( (float)(v14 + v12) > (float)v48 )
    v14 = (float)v48 - v12;
  if ( (float)(v15 + v13) > (float)v47 )
    v15 = (float)v47 - v13;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v62[0] = si128;
  v18 = _mm_load_si128((const __m128i *)&_xmm);
  v62[1] = v18;
  memset(&v62[2], 0, 32);
  BDPUTIL::BDPMatrixFromSource(
    (BDPUTIL *)v62,
    (const struct MSOBDRAWPARAM *)((char *)this + 16),
    v11,
    *(float *)&v55.m256i_i32[3],
    v46);
  if ( v16 )
  {
    v22 = 0;
    if ( *(float *)v55.m256i_i32 < 0.0 )
      v22 = v55.m256i_i32[0];
    if ( *(float *)&v55.m256i_i32[1] < 0.0 )
      v10 = v55.m256i_i32[1];
    *(__m128i *)v55.m256i_i8 = si128;
    *(__m128i *)&v55.m256i_u64[2] = v18;
    v56 = COERCE_FLOAT(v22 ^ _xmm);
    v57 = COERCE_FLOAT(v10 ^ _xmm);
    v58 = 0;
    FPMatrix2D::operator*=(&v55, v62);
  }
  if ( (unsigned int)GdipCreateMatrix2(v20, v19, v21) )
  {
LABEL_82:
    FPState::~FPState((FPState *)v64);
    return 0;
  }
  v23 = 0;
  v50 = 0;
  v53 = 0;
  v51 = 0;
  v54 = 0;
  v59 = 0;
  ImageAttributesExtractable::ImageAttributesExtractable((ImageAttributesExtractable *)v61);
  v24 = *((_DWORD *)a4 + 4) == 0 ? 4 : 0;
  if ( v15 <= 1.0 && (float)v47 > v15 || v14 <= 1.0 && (float)v48 > v14 )
    goto LABEL_61;
  if ( *((_DWORD *)this + 22) != -1 )
  {
    GdipCreateSolidFill(
      (unsigned __int8)BYTE2(*((_DWORD *)this + 22))
    | ((*((_DWORD *)this + 22) | 0xFFFFFF00) << 16)
    | *((_DWORD *)this + 22) & 0xFF00,
      &v53);
    if ( v25 )
      goto LABEL_62;
  }
  sub_1800FD43C(a2);
  GPIMAGEUTIL::SetImageAttributesFromBdp(v61, this, v24);
  GPIMAGEUTIL::SetImageAttributesFromDc((struct Gdiplus::ImageAttributes *)v61, a2, this);
  Buf1 = 0;
  if ( !(unsigned int)GdipGetImageRawFormat(v8, &Buf1) && !memcmp_0(&Buf1, &ImageFormatTIFF, 0x10u) )
  {
    LODWORD(v52) = 0;
    if ( !(unsigned int)GdipGetImagePixelFormat(v8, &v52)
      && (_DWORD)v52 == 8207
      && !(unsigned int)GdipCreateBitmapFromScan0((unsigned int)v48, (unsigned int)v47, 0, 2498570, 0, &v54, &v60)
      && !(unsigned int)GdipGetImageGraphicsContext(v54, &v59)
      && !(unsigned int)GdipDrawImageI(v59, v8, 0, 0) )
    {
      v8 = v54;
    }
  }
  if ( (unsigned int)GdipCreateTextureIA(v8, v61[0]) )
    goto LABEL_62;
  if ( v60 )
    GdipSetTextureTransform(v50, v60);
  v26 = a4[3];
  if ( v26 )
  {
    v27 = a4[1];
    if ( v27 )
    {
      if ( (unsigned int)GdipClonePen(v27, &v51) )
        goto LABEL_62;
      if ( v53 )
      {
        if ( (unsigned int)GdipSetPenBrushFill(v51) )
          goto LABEL_62;
        v28 = a4[3];
        v29 = v51;
        v30 = MSODC::Pgraphics(a2);
        if ( (unsigned int)GdipDrawPath(v30, v29, v28) )
          goto LABEL_62;
      }
      if ( (unsigned int)GdipSetPenBrushFill(v51) )
        goto LABEL_62;
      v31 = a4[3];
      v32 = v51;
      v33 = MSODC::Pgraphics(a2);
      v34 = GdipDrawPath(v33, v32, v31);
    }
    else
    {
      v36 = v53;
      if ( v53 )
      {
        v37 = MSODC::Pgraphics(a2);
        if ( (unsigned int)GdipFillPath(v37, v36, v26) )
          goto LABEL_62;
      }
      v38 = a4[3];
      v39 = v50;
      v40 = MSODC::Pgraphics(a2);
      v34 = GdipFillPath(v40, v39, v38);
    }
  }
  else
  {
    if ( !*a4 )
      goto LABEL_61;
    v41 = v53;
    if ( v53 )
    {
      v42 = MSODC::Pgraphics(a2);
      if ( (unsigned int)GdipFillRectangle(v42, v41) )
        goto LABEL_62;
    }
    v43 = v50;
    v44 = MSODC::Pgraphics(a2);
    v34 = GdipFillRectangle(v44, v43);
  }
  if ( !v34 )
LABEL_61:
    v23 = 1;
LABEL_62:
  if ( v54 )
    GdipDisposeImage(v54);
  if ( v59 )
    GdipDeleteGraphics(v59);
  if ( v60 )
    GdipDeleteMatrix(v60);
  if ( v50 )
    GdipDeleteBrush(v50);
  if ( v53 )
    GdipDeleteBrush(v53);
  if ( v51 )
    GdipDeletePen(v51);
  GdipDisposeImageAttributes(v61[0]);
  FPState::~FPState((FPState *)v64);
  return v23;
}

```

## disassembly

```asm
0x180b41c84  mov     rax, rsp
0x180b41c87  push    rbp
0x180b41c88  push    rbx
0x180b41c89  push    rsi
0x180b41c8a  push    rdi
0x180b41c8b  push    r12
0x180b41c8d  push    r13
0x180b41c8f  push    r14
0x180b41c91  push    r15
0x180b41c93  lea     rbp, [rax-8E8h]
0x180b41c9a  sub     rsp, 9A8h
0x180b41ca1  movaps  xmmword ptr [rax-58h], xmm6
0x180b41ca5  movaps  xmmword ptr [rax-68h], xmm7
0x180b41ca9  movaps  xmmword ptr [rax-78h], xmm8
0x180b41cae  movaps  xmmword ptr [rax-88h], xmm9
0x180b41cb6  movaps  xmmword ptr [rax-98h], xmm12
0x180b41cbe  movaps  xmmword ptr [rax-0A8h], xmm13
0x180b41cc6  movaps  xmmword ptr [rax-0B8h], xmm14
0x180b41cce  mov     rax, cs:__security_cookie
0x180b41cd5  xor     rax, rsp
0x180b41cd8  mov     [rbp+8E0h+var_C0], rax
0x180b41cdf  mov     rsi, r9
0x180b41ce2  mov     rdi, r8
0x180b41ce5  mov     r14, rdx
0x180b41ce8  mov     rbx, rcx
0x180b41ceb  xor     r13d, r13d
0x180b41cee  test    rdx, rdx
0x180b41cf1  jz      loc_180B42435
0x180b41cf7  test    r8, r8
0x180b41cfa  jz      loc_180B42435
0x180b41d00  test    r9, r9
0x180b41d03  jz      loc_180B42435
0x180b41d09  mov     dword ptr [rsp+9E0h+var_998], r13d
0x180b41d0e  lea     rdx, [rsp+9E0h+var_998]
0x180b41d13  call    cs:__imp_GdipGetImageType
0x180b41d19  test    eax, eax
0x180b41d1b  jnz     loc_180B42440
0x180b41d21  cmp     [rdi+0A8h], r13d
0x180b41d28  jnz     loc_180B423CA
0x180b41d2e  mov     ecx, [r14+50h]
0x180b41d32  and     ecx, 70000h
0x180b41d38  lea     eax, [rcx-50000h]
0x180b41d3e  test    eax, 0FFFEFFFFh
0x180b41d43  jnz     short loc_180B41D4B
0x180b41d45  cmp     [rsi+18h], r13
0x180b41d49  jnz     short loc_180B41D52
0x180b41d4b  cmp     dword ptr [rsp+9E0h+var_998], 2
0x180b41d50  jnz     short loc_180B41D7E
0x180b41d52  cmp     [rsi+10h], r13d
0x180b41d56  jnz     short loc_180B41D7E
0x180b41d58  cmp     [rsi+8], r13
0x180b41d5c  jz      short loc_180B41D65
0x180b41d5e  cmp     dword ptr [rsp+9E0h+var_998], 2
0x180b41d63  jnz     short loc_180B41D7E
0x180b41d65  cmp     ecx, 60000h
0x180b41d6b  jnz     loc_180B423CA
0x180b41d71  cmp     [rbp+8E0h+arg_20], r13b
0x180b41d78  jz      loc_180B423CA
0x180b41d7e  xor     edx, edx
0x180b41d80  lea     rcx, [rbp+8E0h+var_8B0]
0x180b41d84  call    cs:__imp_??0FPState@@QEAA@K@Z; FPState::FPState(ulong)
0x180b41d8a  mov     rcx, r14
0x180b41d8d  call    cs:__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ; MSODC::Pgraphics(void)
0x180b41d93  test    rax, rax
0x180b41d96  jz      loc_180B423BE
0x180b41d9c  mov     r8, rdi; struct MSOBDRAWPARAM *
0x180b41d9f  mov     rdx, r14; struct MSODC *
0x180b41da2  mov     rcx, rbx; struct Gdiplus::GpImage *
0x180b41da5  call    ?SelectActiveFrameFromCache@GPIMAGEUTIL@@KAXAEAVGpImage@Gdiplus@@AEBUMSODC@@AEBUMSOBDRAWPARAM@@@Z; GPIMAGEUTIL::SelectActiveFrameFromCache(Gdiplus::GpImage &,MSODC const &,MSOBDRAWPARAM const &)
0x180b41daa  mov     [rbp+8E0h+var_918], r13
0x180b41dae  mov     [rsp+9E0h+var_99C], r13d
0x180b41db3  mov     [rsp+9E0h+var_9A0], r13d
0x180b41db8  lea     rdx, [rsp+9E0h+var_99C]
0x180b41dbd  mov     rcx, rbx
0x180b41dc0  call    cs:__imp_GdipGetImageWidth
0x180b41dc6  test    eax, eax
0x180b41dc8  jnz     loc_180B423BE
0x180b41dce  lea     rdx, [rsp+9E0h+var_9A0]
0x180b41dd3  mov     rcx, rbx
0x180b41dd6  call    cs:__imp_GdipGetImageHeight
0x180b41ddc  test    eax, eax
0x180b41dde  jnz     loc_180B423BE
0x180b41de4  xorps   xmm6, xmm6
0x180b41de7  mov     qword ptr [rbp+8E0h+var_960], r13
0x180b41deb  mov     eax, [rsp+9E0h+var_99C]
0x180b41def  xorps   xmm0, xmm0
0x180b41df2  cvtsi2ss xmm0, rax
0x180b41df7  movss   [rbp+8E0h+var_960+8], xmm0
0x180b41dfc  mov     eax, [rsp+9E0h+var_9A0]
0x180b41e00  xorps   xmm1, xmm1
0x180b41e03  cvtsi2ss xmm1, rax
0x180b41e08  movss   [rbp+8E0h+var_960+0Ch], xmm1
0x180b41e0d  cmp     dword ptr [rsp+9E0h+var_998], 2
0x180b41e12  jnz     short loc_180B41E29
0x180b41e14  lea     r9, [rbp+8E0h+var_8B0]
0x180b41e18  mov     r8, rdi
0x180b41e1b  mov     rdx, r14
0x180b41e1e  lea     rcx, [rbp+8E0h+var_960]
0x180b41e22  call    sub_1812D2020
0x180b41e27  jmp     short loc_180B41E35
0x180b41e29  lea     rdx, [rbp+8E0h+var_960]; struct Gdiplus::RectF *
0x180b41e2d  mov     rcx, rdi; struct MSOBDRAWPARAM *
0x180b41e30  call    ?ApplyCrop@GPIMAGEUTIL@@SAXAEBUMSOBDRAWPARAM@@AEAVRectF@Gdiplus@@@Z; GPIMAGEUTIL::ApplyCrop(MSOBDRAWPARAM const &,Gdiplus::RectF &)
0x180b41e35  movss   xmm12, [rbp+8E0h+var_960]
0x180b41e3b  movaps  xmm0, xmm12
0x180b41e3f  movss   xmm9, [rbp+8E0h+var_960+4]
0x180b41e45  movss   xmm2, [rbp+8E0h+var_960+8]
0x180b41e4a  movaps  xmm8, xmm2
0x180b41e4e  movss   xmm7, [rbp+8E0h+var_960+0Ch]
0x180b41e53  comiss  xmm6, xmm0
0x180b41e56  jbe     short loc_180B41E65
0x180b41e58  movaps  xmm8, xmm0
0x180b41e5c  addss   xmm8, xmm2
0x180b41e61  xorps   xmm12, xmm12
0x180b41e65  setnbe  r15b
0x180b41e69  comiss  xmm6, xmm9
0x180b41e6d  jbe     short loc_180B41E7B
0x180b41e6f  addss   xmm7, xmm9
0x180b41e74  xorps   xmm9, xmm9
0x180b41e78  mov     r15b, 1
0x180b41e7b  mov     eax, [rsp+9E0h+var_99C]
0x180b41e7f  xorps   xmm1, xmm1
0x180b41e82  cvtsi2ss xmm1, rax
0x180b41e87  movaps  xmm0, xmm8
0x180b41e8b  addss   xmm0, xmm12
0x180b41e90  comiss  xmm0, xmm1
0x180b41e93  jbe     short loc_180B41E9E
0x180b41e95  movaps  xmm8, xmm1
0x180b41e99  subss   xmm8, xmm12
0x180b41e9e  mov     eax, [rsp+9E0h+var_9A0]
0x180b41ea2  xorps   xmm1, xmm1
0x180b41ea5  cvtsi2ss xmm1, rax
0x180b41eaa  movaps  xmm0, xmm7
0x180b41ead  addss   xmm0, xmm9
0x180b41eb2  comiss  xmm0, xmm1
0x180b41eb5  jbe     short loc_180B41EBF
0x180b41eb7  movaps  xmm7, xmm1
0x180b41eba  subss   xmm7, xmm9
0x180b41ebf  movdqa  xmm13, cs:__xmm@00000000000000003ff0000000000000
0x180b41ec8  movaps  [rbp+8E0h+var_900], xmm13
0x180b41ecd  movdqa  xmm14, cs:__xmm@3ff00000000000000000000000000000
0x180b41ed6  movaps  [rbp+8E0h+var_8F0], xmm14
0x180b41edb  xorps   xmm0, xmm0
0x180b41ede  movaps  [rbp+8E0h+var_8E0], xmm0
0x180b41ee2  xorps   xmm1, xmm1
0x180b41ee5  movaps  [rbp+8E0h+var_8D0], xmm1
0x180b41ee9  lea     rdx, [rdi+10h]; struct FPMatrix2D *
0x180b41eed  movss   xmm3, [rbp+8E0h+var_960+0Ch]; float
0x180b41ef2  lea     rcx, [rbp+8E0h+var_900]; this
0x180b41ef6  call    ?BDPMatrixFromSource@BDPUTIL@@YAXAEAVFPMatrix2D@@PEBUMSOBDRAWPOS@@MM@Z; BDPUTIL::BDPMatrixFromSource(FPMatrix2D &,MSOBDRAWPOS const *,float,float)
0x180b41efb  test    r15b, r15b
0x180b41efe  jz      short loc_180B41F7A
0x180b41f00  xorps   xmm0, xmm0
0x180b41f03  comiss  xmm6, [rbp+8E0h+var_960]
0x180b41f07  jbe     short loc_180B41F0E
0x180b41f09  movss   xmm0, [rbp+8E0h+var_960]
0x180b41f0e  comiss  xmm6, [rbp+8E0h+var_960+4]
0x180b41f12  jbe     short loc_180B41F19
0x180b41f14  movss   xmm6, [rbp+8E0h+var_960+4]
0x180b41f19  movaps  xmmword ptr [rbp+8E0h+var_960], xmm13
0x180b41f1e  movaps  [rbp+8E0h+var_950], xmm14
0x180b41f23  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180b41f2a  cvtss2sd xmm0, xmm0
0x180b41f2e  movsd   [rbp+8E0h+var_940], xmm0
0x180b41f33  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x180b41f3a  xorps   xmm0, xmm0
0x180b41f3d  cvtss2sd xmm0, xmm6
0x180b41f41  movsd   [rbp+8E0h+var_938], xmm0
0x180b41f46  xorps   xmm1, xmm1
0x180b41f49  movaps  [rbp+8E0h+var_930], xmm1
0x180b41f4d  lea     rdx, [rbp+8E0h+var_900]
0x180b41f51  lea     rcx, [rbp+8E0h+var_960]
0x180b41f55  call    ??XFPMatrix2D@@QEAAAEAV0@AEBV0@@Z; FPMatrix2D::operator*=(FPMatrix2D const &)
0x180b41f5a  movsd   xmm0, qword ptr [rbp+8E0h+var_960]
0x180b41f5f  movsd   xmm1, qword ptr [rbp+8E0h+var_960+8]
0x180b41f64  movsd   xmm6, qword ptr [rbp+8E0h+var_950]
0x180b41f69  movsd   xmm2, qword ptr [rbp+8E0h+var_950+8]
0x180b41f6e  movsd   xmm3, [rbp+8E0h+var_940]
0x180b41f73  movsd   xmm4, [rbp+8E0h+var_938]
0x180b41f78  jmp     short loc_180B41F98
0x180b41f7a  movsd   xmm4, qword ptr [rbp+8E0h+var_8E0+8]
0x180b41f7f  movsd   xmm3, qword ptr [rbp+8E0h+var_8E0]
0x180b41f84  movsd   xmm2, qword ptr [rbp+8E0h+var_8F0+8]
0x180b41f89  movsd   xmm6, qword ptr [rbp+8E0h+var_8F0]
0x180b41f8e  movsd   xmm1, qword ptr [rbp+8E0h+var_900+8]
0x180b41f93  movsd   xmm0, qword ptr [rbp+8E0h+var_900]
0x180b41f98  cvtpd2ps xmm4, xmm4
0x180b41f9c  cvtpd2ps xmm5, xmm3
0x180b41fa0  cvtpd2ps xmm3, xmm2
0x180b41fa4  cvtpd2ps xmm2, xmm1
0x180b41fa8  cvtpd2ps xmm1, xmm6
0x180b41fac  cvtpd2ps xmm0, xmm0
0x180b41fb0  lea     rax, [rbp+8E0h+var_918]
0x180b41fb4  mov     [rsp+9E0h+var_9B0], rax
0x180b41fb9  movss   dword ptr [rsp+9E0h+var_9B8], xmm4
0x180b41fbf  movss   dword ptr [rsp+9E0h+var_9C0], xmm5
0x180b41fc5  call    cs:__imp_GdipCreateMatrix2
0x180b41fcb  test    eax, eax
0x180b41fcd  jnz     loc_180B423BE
0x180b41fd3  mov     r12d, r13d
0x180b41fd6  mov     [rsp+9E0h+var_990], r13
0x180b41fdb  mov     [rsp+9E0h+var_978], r13
0x180b41fe0  mov     [rsp+9E0h+var_988], r13
0x180b41fe5  mov     [rsp+9E0h+var_970], r13
0x180b41fea  mov     [rbp+8E0h+var_920], r13
0x180b41fee  lea     rcx, [rbp+8E0h+var_910]; this
0x180b41ff2  call    ??0ImageAttributesExtractable@@QEAA@XZ; ImageAttributesExtractable::ImageAttributesExtractable(void)
0x180b41ff7  mov     eax, [rsi+10h]
0x180b41ffa  neg     eax
0x180b41ffc  sbb     r15d, r15d
0x180b41fff  not     r15d
0x180b42002  and     r15d, 4
0x180b42006  movss   xmm1, cs:__real@3f800000
0x180b4200e  comiss  xmm1, xmm7
0x180b42011  jb      short loc_180B42028
0x180b42013  mov     eax, [rsp+9E0h+var_9A0]
0x180b42017  xorps   xmm0, xmm0
0x180b4201a  cvtsi2ss xmm0, rax
0x180b4201f  comiss  xmm0, xmm7
0x180b42022  ja      loc_180B42247
0x180b42028  comiss  xmm1, xmm8
0x180b4202c  jb      short loc_180B42044
0x180b4202e  mov     eax, [rsp+9E0h+var_99C]
0x180b42032  xorps   xmm0, xmm0
0x180b42035  cvtsi2ss xmm0, rax
0x180b4203a  comiss  xmm0, xmm8
0x180b4203e  ja      loc_180B42247
0x180b42044  mov     eax, [rdi+58h]
0x180b42047  cmp     eax, 0FFFFFFFFh
0x180b4204a  jz      short loc_180B42080
0x180b4204c  movzx   ecx, ax
0x180b4204f  movzx   r8d, al
0x180b42053  mov     edx, 0FFFFFF00h
0x180b42058  or      r8d, edx
0x180b4205b  shl     r8d, 10h
0x180b4205f  shr     eax, 10h
0x180b42062  movzx   eax, al
0x180b42065  or      r8d, eax
0x180b42068  and     ecx, edx
0x180b4206a  or      ecx, r8d
0x180b4206d  lea     rdx, [rsp+9E0h+var_978]
0x180b42072  call    cs:__imp_GdipCreateSolidFill
0x180b42078  test    eax, eax
0x180b4207a  jnz     loc_180B4224D
0x180b42080  mov     rcx, r14
0x180b42083  call    sub_1800FD43C
0x180b42088  mov     [rsp+9E0h+var_9B8], rbx
0x180b4208d  mov     byte ptr [rsp+9E0h+var_9C0], al
0x180b42091  mov     r8d, r15d
0x180b42094  mov     rdx, rdi
0x180b42097  lea     rcx, [rbp+8E0h+var_910]
0x180b4209b  call    ?SetImageAttributesFromBdp@GPIMAGEUTIL@@SAXPEAVImageAttributes@Gdiplus@@PEBUMSOBDRAWPARAM@@W4WrapMode@3@PEBVFPState@@_NAEAVGpImage@3@@Z; GPIMAGEUTIL::SetImageAttributesFromBdp(Gdiplus::ImageAttributes *,MSOBDRAWPARAM const *,Gdiplus::WrapMode,FPState const *,bool,Gdiplus::GpImage &)
0x180b420a0  mov     r8, rdi; struct MSOBDRAWPARAM *
0x180b420a3  mov     rdx, r14; struct MSODC *
0x180b420a6  lea     rcx, [rbp+8E0h+var_910]; struct Gdiplus::ImageAttributes *
0x180b420aa  call    ?SetImageAttributesFromDc@GPIMAGEUTIL@@SAXPEAVImageAttributes@Gdiplus@@PEBUMSODC@@PEBUMSOBDRAWPARAM@@@Z; GPIMAGEUTIL::SetImageAttributesFromDc(Gdiplus::ImageAttributes *,MSODC const *,MSOBDRAWPARAM const *)
0x180b420af  xorps   xmm0, xmm0
0x180b420b2  movups  [rbp+8E0h+Buf1], xmm0
0x180b420b6  lea     rdx, [rbp+8E0h+Buf1]
0x180b420ba  mov     rcx, rbx
0x180b420bd  call    cs:__imp_GdipGetImageRawFormat
0x180b420c3  test    eax, eax
0x180b420c5  jnz     loc_180B4215C
0x180b420cb  lea     r8d, [rax+10h]; Size
0x180b420cf  lea     rdx, ImageFormatTIFF; Buf2
0x180b420d6  lea     rcx, [rbp+8E0h+Buf1]; Buf1
0x180b420da  call    memcmp_0
0x180b420df  test    eax, eax
0x180b420e1  jnz     short loc_180B4215C
0x180b420e3  mov     dword ptr [rsp+9E0h+var_980], r13d
0x180b420e8  lea     rdx, [rsp+9E0h+var_980]
0x180b420ed  mov     rcx, rbx
0x180b420f0  call    cs:__imp_GdipGetImagePixelFormat
0x180b420f6  test    eax, eax
0x180b420f8  jnz     short loc_180B4215C
0x180b420fa  cmp     dword ptr [rsp+9E0h+var_980], 200Fh
0x180b42102  jnz     short loc_180B4215C
0x180b42104  lea     rax, [rsp+9E0h+var_970]
0x180b42109  mov     [rsp+9E0h+var_9B8], rax
0x180b4210e  mov     [rsp+9E0h+var_9C0], r13
0x180b42113  mov     r9d, 26200Ah
0x180b42119  xor     r8d, r8d
0x180b4211c  mov     edx, [rsp+9E0h+var_9A0]
0x180b42120  mov     ecx, [rsp+9E0h+var_99C]
0x180b42124  call    cs:__imp_GdipCreateBitmapFromScan0
0x180b4212a  test    eax, eax
0x180b4212c  jnz     short loc_180B4215C
0x180b4212e  lea     rdx, [rbp+8E0h+var_920]
0x180b42132  mov     rcx, [rsp+9E0h+var_970]
0x180b42137  call    cs:__imp_GdipGetImageGraphicsContext
0x180b4213d  test    eax, eax
0x180b4213f  jnz     short loc_180B4215C
0x180b42141  xor     r9d, r9d
0x180b42144  xor     r8d, r8d
0x180b42147  mov     rdx, rbx
0x180b4214a  mov     rcx, [rbp+8E0h+var_920]
0x180b4214e  call    cs:__imp_GdipDrawImageI
0x180b42154  test    eax, eax
0x180b42156  cmovz   rbx, [rsp+9E0h+var_970]
0x180b4215c  lea     rax, [rsp+9E0h+var_990]
  ... truncated ...
```
