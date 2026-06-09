# GPIMAGEUTIL::FFill(Gdiplus::GpImage &,MSODC const *,MSOBDRAWPARAM const *,MSOBFILLPARAM const *,bool)

- ea: `0x180b6949c`
- end: `0x180b69ca4`
- name: `?FFill@GPIMAGEUTIL@@SAHAEAVGpImage@Gdiplus@@PEBUMSODC@@PEBUMSOBDRAWPARAM@@PEBUMSOBFILLPARAM@@_N@Z`
- size: `2056`
- prototype: `__int64 __usercall@<rax>(struct Gdiplus::GpImage *@<rcx>, const struct MSODC *@<rdx>, const struct MSOBDRAWPARAM *this@<r8>, const struct MSOBFILLPARAM *@<r9>, bool)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x1801530a4`

## callees

- `0x18000d26c`
- `0x180159700`
- `0x18015a128`
- `0x18015a1f0`
- `0x18015a24c`
- `0x18015a2e0`
- `0x18015aec0`
- `0x180485240`
- `0x180828d90`
- `0x180a384a8`
- `0x180b6949c`
- `0x180b69ca4`
- `0x180bfd060`
- `0x1812846b0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180b69c52`
- `KERNEL32!SetLastError` at `0x180b69c52`
- `mso40uiWin32Client!__imp_?FSetClipPath@MSODC@@AEBA_NPEAVGpPath@Gdiplus@@PEAVMSOCLIPPATHSAVER@@_N@Z` at `0x180b69c18`
- `mso40uiWin32Client!__imp_?FSetClipPath@MSODC@@AEBA_NPEAVGpPath@Gdiplus@@PEAVMSOCLIPPATHSAVER@@_N@Z` at `0x180b69c3f`
- `mso40uiWin32Client!__imp_?FSetClipPath@MSODC@@AEBA_NPEAVGpPath@Gdiplus@@PEAVMSOCLIPPATHSAVER@@_N@Z` at `0x180b69c18`
- `mso40uiWin32Client!__imp_?FSetClipPath@MSODC@@AEBA_NPEAVGpPath@Gdiplus@@PEAVMSOCLIPPATHSAVER@@_N@Z` at `0x180b69c3f`
- `mso40uiWin32Client!__imp_??0FPState@@QEAA@K@Z` at `0x180b6959c`
- `mso40uiWin32Client!__imp_??0FPState@@QEAA@K@Z` at `0x180b6959c`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180b69ad1`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180b69bda`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180b69ad1`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180b69bda`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b695a5`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b69a0d`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b69a46`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b69aec`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b69b15`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b69b5d`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b69bab`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b695a5`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b69a0d`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b69a46`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b69aec`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b69b15`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b69b5d`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b69bab`
- `gdiplus!GdipDisposeImage` at `0x180b69a6f`
- `gdiplus!GdipDisposeImage` at `0x180b69a6f`
- `gdiplus!GdipDeleteGraphics` at `0x180b69a7e`
- `gdiplus!GdipDeleteGraphics` at `0x180b69a7e`
- `gdiplus!GdipGetImageWidth` at `0x180b695d8`
- `gdiplus!GdipGetImageWidth` at `0x180b695d8`
- `gdiplus!GdipGetImageHeight` at `0x180b695ee`
- `gdiplus!GdipGetImageHeight` at `0x180b695ee`
- `gdiplus!GdipGetImageType` at `0x180b6952b`
- `gdiplus!GdipGetImageType` at `0x180b6952b`
- `gdiplus!GdipCreateMatrix2` at `0x180b697dd`
- `gdiplus!GdipCreateMatrix2` at `0x180b697dd`
- `gdiplus!GdipDeleteMatrix` at `0x180b69a8d`
- `gdiplus!GdipDeleteMatrix` at `0x180b69a8d`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180b6994f`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180b6994f`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180b6993c`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180b6993c`
- `gdiplus!GdipDeleteBrush` at `0x180b69a9d`
- `gdiplus!GdipDeleteBrush` at `0x180b69aad`
- `gdiplus!GdipDeleteBrush` at `0x180b69a9d`
- `gdiplus!GdipDeleteBrush` at `0x180b69aad`
- `gdiplus!GdipCreateSolidFill` at `0x180b6988a`
- `gdiplus!GdipCreateSolidFill` at `0x180b6988a`
- `gdiplus!GdipFillRectangle` at `0x180b69b7d`
- `gdiplus!GdipFillRectangle` at `0x180b69bcb`
- `gdiplus!GdipFillRectangle` at `0x180b69b7d`
- `gdiplus!GdipFillRectangle` at `0x180b69bcb`
- `gdiplus!GdipGetImageRawFormat` at `0x180b698d5`
- `gdiplus!GdipGetImageRawFormat` at `0x180b698d5`
- `gdiplus!GdipGetImagePixelFormat` at `0x180b69908`
- `gdiplus!GdipGetImagePixelFormat` at `0x180b69908`
- `gdiplus!GdipDeletePen` at `0x180b69abd`
- `gdiplus!GdipDeletePen` at `0x180b69abd`
- `gdiplus!GdipDrawPath` at `0x180b69a1c`
- `gdiplus!GdipDrawPath` at `0x180b69a55`
- `gdiplus!GdipDrawPath` at `0x180b69a1c`
- `gdiplus!GdipDrawPath` at `0x180b69a55`
- `gdiplus!GdipFillPath` at `0x180b69afb`
- `gdiplus!GdipFillPath` at `0x180b69b24`
- `gdiplus!GdipFillPath` at `0x180b69afb`
- `gdiplus!GdipFillPath` at `0x180b69b24`
- `gdiplus!GdipDisposeImageAttributes` at `0x180b69ac7`
- `gdiplus!GdipDisposeImageAttributes` at `0x180b69ac7`
- `gdiplus!GdipSetTextureTransform` at `0x180b699b9`
- `gdiplus!GdipSetTextureTransform` at `0x180b699b9`
- `gdiplus!GdipClonePen` at `0x180b699de`
- `gdiplus!GdipClonePen` at `0x180b699de`
- `gdiplus!GdipDrawImageI` at `0x180b69966`
- `gdiplus!GdipDrawImageI` at `0x180b69966`
- `gdiplus!GdipCreateTextureIA` at `0x180b6999a`
- `gdiplus!GdipCreateTextureIA` at `0x180b6999a`
- `gdiplus!GdipSetPenBrushFill` at `0x180b699f7`
- `gdiplus!GdipSetPenBrushFill` at `0x180b69a30`
- `gdiplus!GdipSetPenBrushFill` at `0x180b699f7`
- `gdiplus!GdipSetPenBrushFill` at `0x180b69a30`

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
    sub_1812846B0(&v55, a2, this, v64);
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
  sub_18015A1F0(a2);
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
0x180b6949c  mov     rax, rsp
0x180b6949f  push    rbp
0x180b694a0  push    rbx
0x180b694a1  push    rsi
0x180b694a2  push    rdi
0x180b694a3  push    r12
0x180b694a5  push    r13
0x180b694a7  push    r14
0x180b694a9  push    r15
0x180b694ab  lea     rbp, [rax-8E8h]
0x180b694b2  sub     rsp, 9A8h
0x180b694b9  movaps  xmmword ptr [rax-58h], xmm6
0x180b694bd  movaps  xmmword ptr [rax-68h], xmm7
0x180b694c1  movaps  xmmword ptr [rax-78h], xmm8
0x180b694c6  movaps  xmmword ptr [rax-88h], xmm9
0x180b694ce  movaps  xmmword ptr [rax-98h], xmm12
0x180b694d6  movaps  xmmword ptr [rax-0A8h], xmm13
0x180b694de  movaps  xmmword ptr [rax-0B8h], xmm14
0x180b694e6  mov     rax, cs:__security_cookie
0x180b694ed  xor     rax, rsp
0x180b694f0  mov     [rbp+8E0h+var_C0], rax
0x180b694f7  mov     rsi, r9
0x180b694fa  mov     rdi, r8
0x180b694fd  mov     r14, rdx
0x180b69500  mov     rbx, rcx
0x180b69503  xor     r13d, r13d
0x180b69506  test    rdx, rdx
0x180b69509  jz      loc_180B69C4D
0x180b6950f  test    r8, r8
0x180b69512  jz      loc_180B69C4D
0x180b69518  test    r9, r9
0x180b6951b  jz      loc_180B69C4D
0x180b69521  mov     dword ptr [rsp+9E0h+var_998], r13d
0x180b69526  lea     rdx, [rsp+9E0h+var_998]
0x180b6952b  call    cs:__imp_GdipGetImageType
0x180b69531  test    eax, eax
0x180b69533  jnz     loc_180B69C58
0x180b69539  cmp     [rdi+0A8h], r13d
0x180b69540  jnz     loc_180B69BE2
0x180b69546  mov     ecx, [r14+50h]
0x180b6954a  and     ecx, 70000h
0x180b69550  lea     eax, [rcx-50000h]
0x180b69556  test    eax, 0FFFEFFFFh
0x180b6955b  jnz     short loc_180B69563
0x180b6955d  cmp     [rsi+18h], r13
0x180b69561  jnz     short loc_180B6956A
0x180b69563  cmp     dword ptr [rsp+9E0h+var_998], 2
0x180b69568  jnz     short loc_180B69596
0x180b6956a  cmp     [rsi+10h], r13d
0x180b6956e  jnz     short loc_180B69596
0x180b69570  cmp     [rsi+8], r13
0x180b69574  jz      short loc_180B6957D
0x180b69576  cmp     dword ptr [rsp+9E0h+var_998], 2
0x180b6957b  jnz     short loc_180B69596
0x180b6957d  cmp     ecx, 60000h
0x180b69583  jnz     loc_180B69BE2
0x180b69589  cmp     [rbp+8E0h+arg_20], r13b
0x180b69590  jz      loc_180B69BE2
0x180b69596  xor     edx, edx
0x180b69598  lea     rcx, [rbp+8E0h+var_8B0]
0x180b6959c  call    cs:__imp_??0FPState@@QEAA@K@Z; FPState::FPState(ulong)
0x180b695a2  mov     rcx, r14
0x180b695a5  call    cs:__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ; MSODC::Pgraphics(void)
0x180b695ab  test    rax, rax
0x180b695ae  jz      loc_180B69BD6
0x180b695b4  mov     r8, rdi; struct MSOBDRAWPARAM *
0x180b695b7  mov     rdx, r14; struct MSODC *
0x180b695ba  mov     rcx, rbx; struct Gdiplus::GpImage *
0x180b695bd  call    ?SelectActiveFrameFromCache@GPIMAGEUTIL@@KAXAEAVGpImage@Gdiplus@@AEBUMSODC@@AEBUMSOBDRAWPARAM@@@Z; GPIMAGEUTIL::SelectActiveFrameFromCache(Gdiplus::GpImage &,MSODC const &,MSOBDRAWPARAM const &)
0x180b695c2  mov     [rbp+8E0h+var_918], r13
0x180b695c6  mov     [rsp+9E0h+var_99C], r13d
0x180b695cb  mov     [rsp+9E0h+var_9A0], r13d
0x180b695d0  lea     rdx, [rsp+9E0h+var_99C]
0x180b695d5  mov     rcx, rbx
0x180b695d8  call    cs:__imp_GdipGetImageWidth
0x180b695de  test    eax, eax
0x180b695e0  jnz     loc_180B69BD6
0x180b695e6  lea     rdx, [rsp+9E0h+var_9A0]
0x180b695eb  mov     rcx, rbx
0x180b695ee  call    cs:__imp_GdipGetImageHeight
0x180b695f4  test    eax, eax
0x180b695f6  jnz     loc_180B69BD6
0x180b695fc  xorps   xmm6, xmm6
0x180b695ff  mov     qword ptr [rbp+8E0h+var_960], r13
0x180b69603  mov     eax, [rsp+9E0h+var_99C]
0x180b69607  xorps   xmm0, xmm0
0x180b6960a  cvtsi2ss xmm0, rax
0x180b6960f  movss   [rbp+8E0h+var_960+8], xmm0
0x180b69614  mov     eax, [rsp+9E0h+var_9A0]
0x180b69618  xorps   xmm1, xmm1
0x180b6961b  cvtsi2ss xmm1, rax
0x180b69620  movss   [rbp+8E0h+var_960+0Ch], xmm1
0x180b69625  cmp     dword ptr [rsp+9E0h+var_998], 2
0x180b6962a  jnz     short loc_180B69641
0x180b6962c  lea     r9, [rbp+8E0h+var_8B0]
0x180b69630  mov     r8, rdi
0x180b69633  mov     rdx, r14
0x180b69636  lea     rcx, [rbp+8E0h+var_960]
0x180b6963a  call    sub_1812846B0
0x180b6963f  jmp     short loc_180B6964D
0x180b69641  lea     rdx, [rbp+8E0h+var_960]; struct Gdiplus::RectF *
0x180b69645  mov     rcx, rdi; struct MSOBDRAWPARAM *
0x180b69648  call    ?ApplyCrop@GPIMAGEUTIL@@SAXAEBUMSOBDRAWPARAM@@AEAVRectF@Gdiplus@@@Z; GPIMAGEUTIL::ApplyCrop(MSOBDRAWPARAM const &,Gdiplus::RectF &)
0x180b6964d  movss   xmm12, [rbp+8E0h+var_960]
0x180b69653  movaps  xmm0, xmm12
0x180b69657  movss   xmm9, [rbp+8E0h+var_960+4]
0x180b6965d  movss   xmm2, [rbp+8E0h+var_960+8]
0x180b69662  movaps  xmm8, xmm2
0x180b69666  movss   xmm7, [rbp+8E0h+var_960+0Ch]
0x180b6966b  comiss  xmm6, xmm0
0x180b6966e  jbe     short loc_180B6967D
0x180b69670  movaps  xmm8, xmm0
0x180b69674  addss   xmm8, xmm2
0x180b69679  xorps   xmm12, xmm12
0x180b6967d  setnbe  r15b
0x180b69681  comiss  xmm6, xmm9
0x180b69685  jbe     short loc_180B69693
0x180b69687  addss   xmm7, xmm9
0x180b6968c  xorps   xmm9, xmm9
0x180b69690  mov     r15b, 1
0x180b69693  mov     eax, [rsp+9E0h+var_99C]
0x180b69697  xorps   xmm1, xmm1
0x180b6969a  cvtsi2ss xmm1, rax
0x180b6969f  movaps  xmm0, xmm8
0x180b696a3  addss   xmm0, xmm12
0x180b696a8  comiss  xmm0, xmm1
0x180b696ab  jbe     short loc_180B696B6
0x180b696ad  movaps  xmm8, xmm1
0x180b696b1  subss   xmm8, xmm12
0x180b696b6  mov     eax, [rsp+9E0h+var_9A0]
0x180b696ba  xorps   xmm1, xmm1
0x180b696bd  cvtsi2ss xmm1, rax
0x180b696c2  movaps  xmm0, xmm7
0x180b696c5  addss   xmm0, xmm9
0x180b696ca  comiss  xmm0, xmm1
0x180b696cd  jbe     short loc_180B696D7
0x180b696cf  movaps  xmm7, xmm1
0x180b696d2  subss   xmm7, xmm9
0x180b696d7  movdqa  xmm13, cs:__xmm@00000000000000003ff0000000000000
0x180b696e0  movaps  [rbp+8E0h+var_900], xmm13
0x180b696e5  movdqa  xmm14, cs:__xmm@3ff00000000000000000000000000000
0x180b696ee  movaps  [rbp+8E0h+var_8F0], xmm14
0x180b696f3  xorps   xmm0, xmm0
0x180b696f6  movaps  [rbp+8E0h+var_8E0], xmm0
0x180b696fa  xorps   xmm1, xmm1
0x180b696fd  movaps  [rbp+8E0h+var_8D0], xmm1
0x180b69701  lea     rdx, [rdi+10h]; struct FPMatrix2D *
0x180b69705  movss   xmm3, [rbp+8E0h+var_960+0Ch]; float
0x180b6970a  lea     rcx, [rbp+8E0h+var_900]; this
0x180b6970e  call    ?BDPMatrixFromSource@BDPUTIL@@YAXAEAVFPMatrix2D@@PEBUMSOBDRAWPOS@@MM@Z; BDPUTIL::BDPMatrixFromSource(FPMatrix2D &,MSOBDRAWPOS const *,float,float)
0x180b69713  test    r15b, r15b
0x180b69716  jz      short loc_180B69792
0x180b69718  xorps   xmm0, xmm0
0x180b6971b  comiss  xmm6, [rbp+8E0h+var_960]
0x180b6971f  jbe     short loc_180B69726
0x180b69721  movss   xmm0, [rbp+8E0h+var_960]
0x180b69726  comiss  xmm6, [rbp+8E0h+var_960+4]
0x180b6972a  jbe     short loc_180B69731
0x180b6972c  movss   xmm6, [rbp+8E0h+var_960+4]
0x180b69731  movaps  xmmword ptr [rbp+8E0h+var_960], xmm13
0x180b69736  movaps  [rbp+8E0h+var_950], xmm14
0x180b6973b  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180b69742  cvtss2sd xmm0, xmm0
0x180b69746  movsd   [rbp+8E0h+var_940], xmm0
0x180b6974b  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x180b69752  xorps   xmm0, xmm0
0x180b69755  cvtss2sd xmm0, xmm6
0x180b69759  movsd   [rbp+8E0h+var_938], xmm0
0x180b6975e  xorps   xmm1, xmm1
0x180b69761  movaps  [rbp+8E0h+var_930], xmm1
0x180b69765  lea     rdx, [rbp+8E0h+var_900]
0x180b69769  lea     rcx, [rbp+8E0h+var_960]
0x180b6976d  call    ??XFPMatrix2D@@QEAAAEAV0@AEBV0@@Z; FPMatrix2D::operator*=(FPMatrix2D const &)
0x180b69772  movsd   xmm0, qword ptr [rbp+8E0h+var_960]
0x180b69777  movsd   xmm1, qword ptr [rbp+8E0h+var_960+8]
0x180b6977c  movsd   xmm6, qword ptr [rbp+8E0h+var_950]
0x180b69781  movsd   xmm2, qword ptr [rbp+8E0h+var_950+8]
0x180b69786  movsd   xmm3, [rbp+8E0h+var_940]
0x180b6978b  movsd   xmm4, [rbp+8E0h+var_938]
0x180b69790  jmp     short loc_180B697B0
0x180b69792  movsd   xmm4, qword ptr [rbp+8E0h+var_8E0+8]
0x180b69797  movsd   xmm3, qword ptr [rbp+8E0h+var_8E0]
0x180b6979c  movsd   xmm2, qword ptr [rbp+8E0h+var_8F0+8]
0x180b697a1  movsd   xmm6, qword ptr [rbp+8E0h+var_8F0]
0x180b697a6  movsd   xmm1, qword ptr [rbp+8E0h+var_900+8]
0x180b697ab  movsd   xmm0, qword ptr [rbp+8E0h+var_900]
0x180b697b0  cvtpd2ps xmm4, xmm4
0x180b697b4  cvtpd2ps xmm5, xmm3
0x180b697b8  cvtpd2ps xmm3, xmm2
0x180b697bc  cvtpd2ps xmm2, xmm1
0x180b697c0  cvtpd2ps xmm1, xmm6
0x180b697c4  cvtpd2ps xmm0, xmm0
0x180b697c8  lea     rax, [rbp+8E0h+var_918]
0x180b697cc  mov     [rsp+9E0h+var_9B0], rax
0x180b697d1  movss   dword ptr [rsp+9E0h+var_9B8], xmm4
0x180b697d7  movss   dword ptr [rsp+9E0h+var_9C0], xmm5
0x180b697dd  call    cs:__imp_GdipCreateMatrix2
0x180b697e3  test    eax, eax
0x180b697e5  jnz     loc_180B69BD6
0x180b697eb  mov     r12d, r13d
0x180b697ee  mov     [rsp+9E0h+var_990], r13
0x180b697f3  mov     [rsp+9E0h+var_978], r13
0x180b697f8  mov     [rsp+9E0h+var_988], r13
0x180b697fd  mov     [rsp+9E0h+var_970], r13
0x180b69802  mov     [rbp+8E0h+var_920], r13
0x180b69806  lea     rcx, [rbp+8E0h+var_910]; this
0x180b6980a  call    ??0ImageAttributesExtractable@@QEAA@XZ; ImageAttributesExtractable::ImageAttributesExtractable(void)
0x180b6980f  mov     eax, [rsi+10h]
0x180b69812  neg     eax
0x180b69814  sbb     r15d, r15d
0x180b69817  not     r15d
0x180b6981a  and     r15d, 4
0x180b6981e  movss   xmm1, cs:__real@3f800000
0x180b69826  comiss  xmm1, xmm7
0x180b69829  jb      short loc_180B69840
0x180b6982b  mov     eax, [rsp+9E0h+var_9A0]
0x180b6982f  xorps   xmm0, xmm0
0x180b69832  cvtsi2ss xmm0, rax
0x180b69837  comiss  xmm0, xmm7
0x180b6983a  ja      loc_180B69A5F
0x180b69840  comiss  xmm1, xmm8
0x180b69844  jb      short loc_180B6985C
0x180b69846  mov     eax, [rsp+9E0h+var_99C]
0x180b6984a  xorps   xmm0, xmm0
0x180b6984d  cvtsi2ss xmm0, rax
0x180b69852  comiss  xmm0, xmm8
0x180b69856  ja      loc_180B69A5F
0x180b6985c  mov     eax, [rdi+58h]
0x180b6985f  cmp     eax, 0FFFFFFFFh
0x180b69862  jz      short loc_180B69898
0x180b69864  movzx   ecx, ax
0x180b69867  movzx   r8d, al
0x180b6986b  mov     edx, 0FFFFFF00h
0x180b69870  or      r8d, edx
0x180b69873  shl     r8d, 10h
0x180b69877  shr     eax, 10h
0x180b6987a  movzx   eax, al
0x180b6987d  or      r8d, eax
0x180b69880  and     ecx, edx
0x180b69882  or      ecx, r8d
0x180b69885  lea     rdx, [rsp+9E0h+var_978]
0x180b6988a  call    cs:__imp_GdipCreateSolidFill
0x180b69890  test    eax, eax
0x180b69892  jnz     loc_180B69A65
0x180b69898  mov     rcx, r14
0x180b6989b  call    sub_18015A1F0
0x180b698a0  mov     [rsp+9E0h+var_9B8], rbx
0x180b698a5  mov     byte ptr [rsp+9E0h+var_9C0], al
0x180b698a9  mov     r8d, r15d
0x180b698ac  mov     rdx, rdi
0x180b698af  lea     rcx, [rbp+8E0h+var_910]
0x180b698b3  call    ?SetImageAttributesFromBdp@GPIMAGEUTIL@@SAXPEAVImageAttributes@Gdiplus@@PEBUMSOBDRAWPARAM@@W4WrapMode@3@PEBVFPState@@_NAEAVGpImage@3@@Z; GPIMAGEUTIL::SetImageAttributesFromBdp(Gdiplus::ImageAttributes *,MSOBDRAWPARAM const *,Gdiplus::WrapMode,FPState const *,bool,Gdiplus::GpImage &)
0x180b698b8  mov     r8, rdi; struct MSOBDRAWPARAM *
0x180b698bb  mov     rdx, r14; struct MSODC *
0x180b698be  lea     rcx, [rbp+8E0h+var_910]; struct Gdiplus::ImageAttributes *
0x180b698c2  call    ?SetImageAttributesFromDc@GPIMAGEUTIL@@SAXPEAVImageAttributes@Gdiplus@@PEBUMSODC@@PEBUMSOBDRAWPARAM@@@Z; GPIMAGEUTIL::SetImageAttributesFromDc(Gdiplus::ImageAttributes *,MSODC const *,MSOBDRAWPARAM const *)
0x180b698c7  xorps   xmm0, xmm0
0x180b698ca  movups  [rbp+8E0h+Buf1], xmm0
0x180b698ce  lea     rdx, [rbp+8E0h+Buf1]
0x180b698d2  mov     rcx, rbx
0x180b698d5  call    cs:__imp_GdipGetImageRawFormat
0x180b698db  test    eax, eax
0x180b698dd  jnz     loc_180B69974
0x180b698e3  lea     r8d, [rax+10h]; Size
0x180b698e7  lea     rdx, ImageFormatTIFF; Buf2
0x180b698ee  lea     rcx, [rbp+8E0h+Buf1]; Buf1
0x180b698f2  call    memcmp_0
0x180b698f7  test    eax, eax
0x180b698f9  jnz     short loc_180B69974
0x180b698fb  mov     dword ptr [rsp+9E0h+var_980], r13d
0x180b69900  lea     rdx, [rsp+9E0h+var_980]
0x180b69905  mov     rcx, rbx
0x180b69908  call    cs:__imp_GdipGetImagePixelFormat
0x180b6990e  test    eax, eax
0x180b69910  jnz     short loc_180B69974
0x180b69912  cmp     dword ptr [rsp+9E0h+var_980], 200Fh
0x180b6991a  jnz     short loc_180B69974
0x180b6991c  lea     rax, [rsp+9E0h+var_970]
0x180b69921  mov     [rsp+9E0h+var_9B8], rax
0x180b69926  mov     [rsp+9E0h+var_9C0], r13
0x180b6992b  mov     r9d, 26200Ah
0x180b69931  xor     r8d, r8d
0x180b69934  mov     edx, [rsp+9E0h+var_9A0]
0x180b69938  mov     ecx, [rsp+9E0h+var_99C]
0x180b6993c  call    cs:__imp_GdipCreateBitmapFromScan0
0x180b69942  test    eax, eax
0x180b69944  jnz     short loc_180B69974
0x180b69946  lea     rdx, [rbp+8E0h+var_920]
0x180b6994a  mov     rcx, [rsp+9E0h+var_970]
0x180b6994f  call    cs:__imp_GdipGetImageGraphicsContext
0x180b69955  test    eax, eax
0x180b69957  jnz     short loc_180B69974
0x180b69959  xor     r9d, r9d
0x180b6995c  xor     r8d, r8d
0x180b6995f  mov     rdx, rbx
0x180b69962  mov     rcx, [rbp+8E0h+var_920]
0x180b69966  call    cs:__imp_GdipDrawImageI
0x180b6996c  test    eax, eax
0x180b6996e  cmovz   rbx, [rsp+9E0h+var_970]
0x180b69974  lea     rax, [rsp+9E0h+var_990]
  ... truncated ...
```
