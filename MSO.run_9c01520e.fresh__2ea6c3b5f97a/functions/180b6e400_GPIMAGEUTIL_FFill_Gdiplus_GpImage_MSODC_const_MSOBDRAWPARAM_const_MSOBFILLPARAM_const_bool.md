# GPIMAGEUTIL::FFill(Gdiplus::GpImage &,MSODC const *,MSOBDRAWPARAM const *,MSOBFILLPARAM const *,bool)

- ea: `0x180b6e400`
- end: `0x180b6ec08`
- name: `?FFill@GPIMAGEUTIL@@SAHAEAVGpImage@Gdiplus@@PEBUMSODC@@PEBUMSOBDRAWPARAM@@PEBUMSOBFILLPARAM@@_N@Z`
- size: `2056`
- prototype: `__int64 __usercall@<rax>(struct Gdiplus::GpImage *@<rcx>, const struct MSODC *@<rdx>, const struct MSOBDRAWPARAM *this@<r8>, const struct MSOBFILLPARAM *@<r9>, bool)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18014fbe4`

## callees

- `0x18000d26c`
- `0x1801513a0`
- `0x180151dc8`
- `0x180151e90`
- `0x180151eec`
- `0x180151f80`
- `0x180152e60`
- `0x18016eca0`
- `0x180831ed0`
- `0x180a3d9f8`
- `0x180b6e400`
- `0x180b6ec08`
- `0x180c01b20`
- `0x181284c70`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180b6ebb6`
- `KERNEL32!SetLastError` at `0x180b6ebb6`
- `mso40uiWin32Client!__imp_?FSetClipPath@MSODC@@AEBA_NPEAVGpPath@Gdiplus@@PEAVMSOCLIPPATHSAVER@@_N@Z` at `0x180b6eb7c`
- `mso40uiWin32Client!__imp_?FSetClipPath@MSODC@@AEBA_NPEAVGpPath@Gdiplus@@PEAVMSOCLIPPATHSAVER@@_N@Z` at `0x180b6eba3`
- `mso40uiWin32Client!__imp_?FSetClipPath@MSODC@@AEBA_NPEAVGpPath@Gdiplus@@PEAVMSOCLIPPATHSAVER@@_N@Z` at `0x180b6eb7c`
- `mso40uiWin32Client!__imp_?FSetClipPath@MSODC@@AEBA_NPEAVGpPath@Gdiplus@@PEAVMSOCLIPPATHSAVER@@_N@Z` at `0x180b6eba3`
- `mso40uiWin32Client!__imp_??0FPState@@QEAA@K@Z` at `0x180b6e500`
- `mso40uiWin32Client!__imp_??0FPState@@QEAA@K@Z` at `0x180b6e500`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180b6ea35`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180b6eb3e`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180b6ea35`
- `mso40uiWin32Client!__imp_??1FPState@@QEAA@XZ` at `0x180b6eb3e`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6e509`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6e971`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6e9aa`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6ea50`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6ea79`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6eac1`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6eb0f`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6e509`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6e971`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6e9aa`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6ea50`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6ea79`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6eac1`
- `mso40uiWin32Client!__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ` at `0x180b6eb0f`
- `gdiplus!GdipDisposeImage` at `0x180b6e9d3`
- `gdiplus!GdipDisposeImage` at `0x180b6e9d3`
- `gdiplus!GdipDeleteGraphics` at `0x180b6e9e2`
- `gdiplus!GdipDeleteGraphics` at `0x180b6e9e2`
- `gdiplus!GdipGetImageWidth` at `0x180b6e53c`
- `gdiplus!GdipGetImageWidth` at `0x180b6e53c`
- `gdiplus!GdipGetImageHeight` at `0x180b6e552`
- `gdiplus!GdipGetImageHeight` at `0x180b6e552`
- `gdiplus!GdipGetImageType` at `0x180b6e48f`
- `gdiplus!GdipGetImageType` at `0x180b6e48f`
- `gdiplus!GdipCreateMatrix2` at `0x180b6e741`
- `gdiplus!GdipCreateMatrix2` at `0x180b6e741`
- `gdiplus!GdipDeleteMatrix` at `0x180b6e9f1`
- `gdiplus!GdipDeleteMatrix` at `0x180b6e9f1`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180b6e8b3`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180b6e8b3`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180b6e8a0`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180b6e8a0`
- `gdiplus!GdipDeleteBrush` at `0x180b6ea01`
- `gdiplus!GdipDeleteBrush` at `0x180b6ea11`
- `gdiplus!GdipDeleteBrush` at `0x180b6ea01`
- `gdiplus!GdipDeleteBrush` at `0x180b6ea11`
- `gdiplus!GdipCreateSolidFill` at `0x180b6e7ee`
- `gdiplus!GdipCreateSolidFill` at `0x180b6e7ee`
- `gdiplus!GdipFillRectangle` at `0x180b6eae1`
- `gdiplus!GdipFillRectangle` at `0x180b6eb2f`
- `gdiplus!GdipFillRectangle` at `0x180b6eae1`
- `gdiplus!GdipFillRectangle` at `0x180b6eb2f`
- `gdiplus!GdipGetImageRawFormat` at `0x180b6e839`
- `gdiplus!GdipGetImageRawFormat` at `0x180b6e839`
- `gdiplus!GdipGetImagePixelFormat` at `0x180b6e86c`
- `gdiplus!GdipGetImagePixelFormat` at `0x180b6e86c`
- `gdiplus!GdipDeletePen` at `0x180b6ea21`
- `gdiplus!GdipDeletePen` at `0x180b6ea21`
- `gdiplus!GdipDrawPath` at `0x180b6e980`
- `gdiplus!GdipDrawPath` at `0x180b6e9b9`
- `gdiplus!GdipDrawPath` at `0x180b6e980`
- `gdiplus!GdipDrawPath` at `0x180b6e9b9`
- `gdiplus!GdipFillPath` at `0x180b6ea5f`
- `gdiplus!GdipFillPath` at `0x180b6ea88`
- `gdiplus!GdipFillPath` at `0x180b6ea5f`
- `gdiplus!GdipFillPath` at `0x180b6ea88`
- `gdiplus!GdipDisposeImageAttributes` at `0x180b6ea2b`
- `gdiplus!GdipDisposeImageAttributes` at `0x180b6ea2b`
- `gdiplus!GdipSetTextureTransform` at `0x180b6e91d`
- `gdiplus!GdipSetTextureTransform` at `0x180b6e91d`
- `gdiplus!GdipClonePen` at `0x180b6e942`
- `gdiplus!GdipClonePen` at `0x180b6e942`
- `gdiplus!GdipDrawImageI` at `0x180b6e8ca`
- `gdiplus!GdipDrawImageI` at `0x180b6e8ca`
- `gdiplus!GdipCreateTextureIA` at `0x180b6e8fe`
- `gdiplus!GdipCreateTextureIA` at `0x180b6e8fe`
- `gdiplus!GdipSetPenBrushFill` at `0x180b6e95b`
- `gdiplus!GdipSetPenBrushFill` at `0x180b6e994`
- `gdiplus!GdipSetPenBrushFill` at `0x180b6e95b`
- `gdiplus!GdipSetPenBrushFill` at `0x180b6e994`

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
  int v48; // [rsp+4Ch] [rbp-BCh]
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
  __int64 v60; // [rsp+D0h] [rbp-38h]
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
  if ( (unsigned int)GdipGetImageWidth(v8) || (unsigned int)GdipGetImageHeight(v8, &v47) )
    goto LABEL_82;
  v10 = 0;
  v55.m256i_i64[0] = 0;
  *(float *)&v55.m256i_i32[2] = (float)v48;
  *(float *)&v55.m256i_i32[3] = (float)v47;
  if ( (_DWORD)v49 == 2 )
    sub_181284C70(&v55, a2, this, v64);
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
  sub_180151E90(a2);
  GPIMAGEUTIL::SetImageAttributesFromBdp(v61, this, v24);
  GPIMAGEUTIL::SetImageAttributesFromDc((struct Gdiplus::ImageAttributes *)v61, a2, this);
  Buf1 = 0;
  if ( !(unsigned int)GdipGetImageRawFormat(v8, &Buf1) && !memcmp_0(&Buf1, &ImageFormatTIFF, 0x10u) )
  {
    LODWORD(v52) = 0;
    if ( !(unsigned int)GdipGetImagePixelFormat(v8, &v52)
      && (_DWORD)v52 == 8207
      && !(unsigned int)GdipCreateBitmapFromScan0((unsigned int)v48, (unsigned int)v47, 0, 2498570, 0, &v54)
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
0x180b6e400  mov     rax, rsp
0x180b6e403  push    rbp
0x180b6e404  push    rbx
0x180b6e405  push    rsi
0x180b6e406  push    rdi
0x180b6e407  push    r12
0x180b6e409  push    r13
0x180b6e40b  push    r14
0x180b6e40d  push    r15
0x180b6e40f  lea     rbp, [rax-8E8h]
0x180b6e416  sub     rsp, 9A8h
0x180b6e41d  movaps  xmmword ptr [rax-58h], xmm6
0x180b6e421  movaps  xmmword ptr [rax-68h], xmm7
0x180b6e425  movaps  xmmword ptr [rax-78h], xmm8
0x180b6e42a  movaps  xmmword ptr [rax-88h], xmm9
0x180b6e432  movaps  xmmword ptr [rax-98h], xmm12
0x180b6e43a  movaps  xmmword ptr [rax-0A8h], xmm13
0x180b6e442  movaps  xmmword ptr [rax-0B8h], xmm14
0x180b6e44a  mov     rax, cs:__security_cookie
0x180b6e451  xor     rax, rsp
0x180b6e454  mov     [rbp+8E0h+var_C0], rax
0x180b6e45b  mov     rsi, r9
0x180b6e45e  mov     rdi, r8
0x180b6e461  mov     r14, rdx
0x180b6e464  mov     rbx, rcx
0x180b6e467  xor     r13d, r13d
0x180b6e46a  test    rdx, rdx
0x180b6e46d  jz      loc_180B6EBB1
0x180b6e473  test    r8, r8
0x180b6e476  jz      loc_180B6EBB1
0x180b6e47c  test    r9, r9
0x180b6e47f  jz      loc_180B6EBB1
0x180b6e485  mov     dword ptr [rsp+9E0h+var_998], r13d
0x180b6e48a  lea     rdx, [rsp+9E0h+var_998]
0x180b6e48f  call    cs:__imp_GdipGetImageType
0x180b6e495  test    eax, eax
0x180b6e497  jnz     loc_180B6EBBC
0x180b6e49d  cmp     [rdi+0A8h], r13d
0x180b6e4a4  jnz     loc_180B6EB46
0x180b6e4aa  mov     ecx, [r14+50h]
0x180b6e4ae  and     ecx, 70000h
0x180b6e4b4  lea     eax, [rcx-50000h]
0x180b6e4ba  test    eax, 0FFFEFFFFh
0x180b6e4bf  jnz     short loc_180B6E4C7
0x180b6e4c1  cmp     [rsi+18h], r13
0x180b6e4c5  jnz     short loc_180B6E4CE
0x180b6e4c7  cmp     dword ptr [rsp+9E0h+var_998], 2
0x180b6e4cc  jnz     short loc_180B6E4FA
0x180b6e4ce  cmp     [rsi+10h], r13d
0x180b6e4d2  jnz     short loc_180B6E4FA
0x180b6e4d4  cmp     [rsi+8], r13
0x180b6e4d8  jz      short loc_180B6E4E1
0x180b6e4da  cmp     dword ptr [rsp+9E0h+var_998], 2
0x180b6e4df  jnz     short loc_180B6E4FA
0x180b6e4e1  cmp     ecx, 60000h
0x180b6e4e7  jnz     loc_180B6EB46
0x180b6e4ed  cmp     [rbp+8E0h+arg_20], r13b
0x180b6e4f4  jz      loc_180B6EB46
0x180b6e4fa  xor     edx, edx
0x180b6e4fc  lea     rcx, [rbp+8E0h+var_8B0]
0x180b6e500  call    cs:__imp_??0FPState@@QEAA@K@Z; FPState::FPState(ulong)
0x180b6e506  mov     rcx, r14
0x180b6e509  call    cs:__imp_?Pgraphics@MSODC@@QEBAPEAVGpGraphics@Gdiplus@@XZ; MSODC::Pgraphics(void)
0x180b6e50f  test    rax, rax
0x180b6e512  jz      loc_180B6EB3A
0x180b6e518  mov     r8, rdi; struct MSOBDRAWPARAM *
0x180b6e51b  mov     rdx, r14; struct MSODC *
0x180b6e51e  mov     rcx, rbx; struct Gdiplus::GpImage *
0x180b6e521  call    ?SelectActiveFrameFromCache@GPIMAGEUTIL@@KAXAEAVGpImage@Gdiplus@@AEBUMSODC@@AEBUMSOBDRAWPARAM@@@Z; GPIMAGEUTIL::SelectActiveFrameFromCache(Gdiplus::GpImage &,MSODC const &,MSOBDRAWPARAM const &)
0x180b6e526  mov     [rbp+8E0h+var_918], r13
0x180b6e52a  mov     [rsp+9E0h+var_99C], r13d
0x180b6e52f  mov     [rsp+9E0h+var_9A0], r13d
0x180b6e534  lea     rdx, [rsp+9E0h+var_99C]
0x180b6e539  mov     rcx, rbx
0x180b6e53c  call    cs:__imp_GdipGetImageWidth
0x180b6e542  test    eax, eax
0x180b6e544  jnz     loc_180B6EB3A
0x180b6e54a  lea     rdx, [rsp+9E0h+var_9A0]
0x180b6e54f  mov     rcx, rbx
0x180b6e552  call    cs:__imp_GdipGetImageHeight
0x180b6e558  test    eax, eax
0x180b6e55a  jnz     loc_180B6EB3A
0x180b6e560  xorps   xmm6, xmm6
0x180b6e563  mov     qword ptr [rbp+8E0h+var_960], r13
0x180b6e567  mov     eax, [rsp+9E0h+var_99C]
0x180b6e56b  xorps   xmm0, xmm0
0x180b6e56e  cvtsi2ss xmm0, rax
0x180b6e573  movss   [rbp+8E0h+var_960+8], xmm0
0x180b6e578  mov     eax, [rsp+9E0h+var_9A0]
0x180b6e57c  xorps   xmm1, xmm1
0x180b6e57f  cvtsi2ss xmm1, rax
0x180b6e584  movss   [rbp+8E0h+var_960+0Ch], xmm1
0x180b6e589  cmp     dword ptr [rsp+9E0h+var_998], 2
0x180b6e58e  jnz     short loc_180B6E5A5
0x180b6e590  lea     r9, [rbp+8E0h+var_8B0]
0x180b6e594  mov     r8, rdi
0x180b6e597  mov     rdx, r14
0x180b6e59a  lea     rcx, [rbp+8E0h+var_960]
0x180b6e59e  call    sub_181284C70
0x180b6e5a3  jmp     short loc_180B6E5B1
0x180b6e5a5  lea     rdx, [rbp+8E0h+var_960]; struct Gdiplus::RectF *
0x180b6e5a9  mov     rcx, rdi; struct MSOBDRAWPARAM *
0x180b6e5ac  call    ?ApplyCrop@GPIMAGEUTIL@@SAXAEBUMSOBDRAWPARAM@@AEAVRectF@Gdiplus@@@Z; GPIMAGEUTIL::ApplyCrop(MSOBDRAWPARAM const &,Gdiplus::RectF &)
0x180b6e5b1  movss   xmm12, [rbp+8E0h+var_960]
0x180b6e5b7  movaps  xmm0, xmm12
0x180b6e5bb  movss   xmm9, [rbp+8E0h+var_960+4]
0x180b6e5c1  movss   xmm2, [rbp+8E0h+var_960+8]
0x180b6e5c6  movaps  xmm8, xmm2
0x180b6e5ca  movss   xmm7, [rbp+8E0h+var_960+0Ch]
0x180b6e5cf  comiss  xmm6, xmm0
0x180b6e5d2  jbe     short loc_180B6E5E1
0x180b6e5d4  movaps  xmm8, xmm0
0x180b6e5d8  addss   xmm8, xmm2
0x180b6e5dd  xorps   xmm12, xmm12
0x180b6e5e1  setnbe  r15b
0x180b6e5e5  comiss  xmm6, xmm9
0x180b6e5e9  jbe     short loc_180B6E5F7
0x180b6e5eb  addss   xmm7, xmm9
0x180b6e5f0  xorps   xmm9, xmm9
0x180b6e5f4  mov     r15b, 1
0x180b6e5f7  mov     eax, [rsp+9E0h+var_99C]
0x180b6e5fb  xorps   xmm1, xmm1
0x180b6e5fe  cvtsi2ss xmm1, rax
0x180b6e603  movaps  xmm0, xmm8
0x180b6e607  addss   xmm0, xmm12
0x180b6e60c  comiss  xmm0, xmm1
0x180b6e60f  jbe     short loc_180B6E61A
0x180b6e611  movaps  xmm8, xmm1
0x180b6e615  subss   xmm8, xmm12
0x180b6e61a  mov     eax, [rsp+9E0h+var_9A0]
0x180b6e61e  xorps   xmm1, xmm1
0x180b6e621  cvtsi2ss xmm1, rax
0x180b6e626  movaps  xmm0, xmm7
0x180b6e629  addss   xmm0, xmm9
0x180b6e62e  comiss  xmm0, xmm1
0x180b6e631  jbe     short loc_180B6E63B
0x180b6e633  movaps  xmm7, xmm1
0x180b6e636  subss   xmm7, xmm9
0x180b6e63b  movdqa  xmm13, cs:__xmm@00000000000000003ff0000000000000
0x180b6e644  movaps  [rbp+8E0h+var_900], xmm13
0x180b6e649  movdqa  xmm14, cs:__xmm@3ff00000000000000000000000000000
0x180b6e652  movaps  [rbp+8E0h+var_8F0], xmm14
0x180b6e657  xorps   xmm0, xmm0
0x180b6e65a  movaps  [rbp+8E0h+var_8E0], xmm0
0x180b6e65e  xorps   xmm1, xmm1
0x180b6e661  movaps  [rbp+8E0h+var_8D0], xmm1
0x180b6e665  lea     rdx, [rdi+10h]; struct FPMatrix2D *
0x180b6e669  movss   xmm3, [rbp+8E0h+var_960+0Ch]; float
0x180b6e66e  lea     rcx, [rbp+8E0h+var_900]; this
0x180b6e672  call    ?BDPMatrixFromSource@BDPUTIL@@YAXAEAVFPMatrix2D@@PEBUMSOBDRAWPOS@@MM@Z; BDPUTIL::BDPMatrixFromSource(FPMatrix2D &,MSOBDRAWPOS const *,float,float)
0x180b6e677  test    r15b, r15b
0x180b6e67a  jz      short loc_180B6E6F6
0x180b6e67c  xorps   xmm0, xmm0
0x180b6e67f  comiss  xmm6, [rbp+8E0h+var_960]
0x180b6e683  jbe     short loc_180B6E68A
0x180b6e685  movss   xmm0, [rbp+8E0h+var_960]
0x180b6e68a  comiss  xmm6, [rbp+8E0h+var_960+4]
0x180b6e68e  jbe     short loc_180B6E695
0x180b6e690  movss   xmm6, [rbp+8E0h+var_960+4]
0x180b6e695  movaps  xmmword ptr [rbp+8E0h+var_960], xmm13
0x180b6e69a  movaps  [rbp+8E0h+var_950], xmm14
0x180b6e69f  xorps   xmm0, cs:__xmm@80000000800000008000000080000000
0x180b6e6a6  cvtss2sd xmm0, xmm0
0x180b6e6aa  movsd   [rbp+8E0h+var_940], xmm0
0x180b6e6af  xorps   xmm6, cs:__xmm@80000000800000008000000080000000
0x180b6e6b6  xorps   xmm0, xmm0
0x180b6e6b9  cvtss2sd xmm0, xmm6
0x180b6e6bd  movsd   [rbp+8E0h+var_938], xmm0
0x180b6e6c2  xorps   xmm1, xmm1
0x180b6e6c5  movaps  [rbp+8E0h+var_930], xmm1
0x180b6e6c9  lea     rdx, [rbp+8E0h+var_900]
0x180b6e6cd  lea     rcx, [rbp+8E0h+var_960]
0x180b6e6d1  call    ??XFPMatrix2D@@QEAAAEAV0@AEBV0@@Z; FPMatrix2D::operator*=(FPMatrix2D const &)
0x180b6e6d6  movsd   xmm0, qword ptr [rbp+8E0h+var_960]
0x180b6e6db  movsd   xmm1, qword ptr [rbp+8E0h+var_960+8]
0x180b6e6e0  movsd   xmm6, qword ptr [rbp+8E0h+var_950]
0x180b6e6e5  movsd   xmm2, qword ptr [rbp+8E0h+var_950+8]
0x180b6e6ea  movsd   xmm3, [rbp+8E0h+var_940]
0x180b6e6ef  movsd   xmm4, [rbp+8E0h+var_938]
0x180b6e6f4  jmp     short loc_180B6E714
0x180b6e6f6  movsd   xmm4, qword ptr [rbp+8E0h+var_8E0+8]
0x180b6e6fb  movsd   xmm3, qword ptr [rbp+8E0h+var_8E0]
0x180b6e700  movsd   xmm2, qword ptr [rbp+8E0h+var_8F0+8]
0x180b6e705  movsd   xmm6, qword ptr [rbp+8E0h+var_8F0]
0x180b6e70a  movsd   xmm1, qword ptr [rbp+8E0h+var_900+8]
0x180b6e70f  movsd   xmm0, qword ptr [rbp+8E0h+var_900]
0x180b6e714  cvtpd2ps xmm4, xmm4
0x180b6e718  cvtpd2ps xmm5, xmm3
0x180b6e71c  cvtpd2ps xmm3, xmm2
0x180b6e720  cvtpd2ps xmm2, xmm1
0x180b6e724  cvtpd2ps xmm1, xmm6
0x180b6e728  cvtpd2ps xmm0, xmm0
0x180b6e72c  lea     rax, [rbp+8E0h+var_918]
0x180b6e730  mov     [rsp+9E0h+var_9B0], rax
0x180b6e735  movss   dword ptr [rsp+9E0h+var_9B8], xmm4
0x180b6e73b  movss   dword ptr [rsp+9E0h+var_9C0], xmm5
0x180b6e741  call    cs:__imp_GdipCreateMatrix2
0x180b6e747  test    eax, eax
0x180b6e749  jnz     loc_180B6EB3A
0x180b6e74f  mov     r12d, r13d
0x180b6e752  mov     [rsp+9E0h+var_990], r13
0x180b6e757  mov     [rsp+9E0h+var_978], r13
0x180b6e75c  mov     [rsp+9E0h+var_988], r13
0x180b6e761  mov     [rsp+9E0h+var_970], r13
0x180b6e766  mov     [rbp+8E0h+var_920], r13
0x180b6e76a  lea     rcx, [rbp+8E0h+var_910]; this
0x180b6e76e  call    ??0ImageAttributesExtractable@@QEAA@XZ; ImageAttributesExtractable::ImageAttributesExtractable(void)
0x180b6e773  mov     eax, [rsi+10h]
0x180b6e776  neg     eax
0x180b6e778  sbb     r15d, r15d
0x180b6e77b  not     r15d
0x180b6e77e  and     r15d, 4
0x180b6e782  movss   xmm1, cs:__real@3f800000
0x180b6e78a  comiss  xmm1, xmm7
0x180b6e78d  jb      short loc_180B6E7A4
0x180b6e78f  mov     eax, [rsp+9E0h+var_9A0]
0x180b6e793  xorps   xmm0, xmm0
0x180b6e796  cvtsi2ss xmm0, rax
0x180b6e79b  comiss  xmm0, xmm7
0x180b6e79e  ja      loc_180B6E9C3
0x180b6e7a4  comiss  xmm1, xmm8
0x180b6e7a8  jb      short loc_180B6E7C0
0x180b6e7aa  mov     eax, [rsp+9E0h+var_99C]
0x180b6e7ae  xorps   xmm0, xmm0
0x180b6e7b1  cvtsi2ss xmm0, rax
0x180b6e7b6  comiss  xmm0, xmm8
0x180b6e7ba  ja      loc_180B6E9C3
0x180b6e7c0  mov     eax, [rdi+58h]
0x180b6e7c3  cmp     eax, 0FFFFFFFFh
0x180b6e7c6  jz      short loc_180B6E7FC
0x180b6e7c8  movzx   ecx, ax
0x180b6e7cb  movzx   r8d, al
0x180b6e7cf  mov     edx, 0FFFFFF00h
0x180b6e7d4  or      r8d, edx
0x180b6e7d7  shl     r8d, 10h
0x180b6e7db  shr     eax, 10h
0x180b6e7de  movzx   eax, al
0x180b6e7e1  or      r8d, eax
0x180b6e7e4  and     ecx, edx
0x180b6e7e6  or      ecx, r8d
0x180b6e7e9  lea     rdx, [rsp+9E0h+var_978]
0x180b6e7ee  call    cs:__imp_GdipCreateSolidFill
0x180b6e7f4  test    eax, eax
0x180b6e7f6  jnz     loc_180B6E9C9
0x180b6e7fc  mov     rcx, r14
0x180b6e7ff  call    sub_180151E90
0x180b6e804  mov     [rsp+9E0h+var_9B8], rbx
0x180b6e809  mov     byte ptr [rsp+9E0h+var_9C0], al
0x180b6e80d  mov     r8d, r15d
0x180b6e810  mov     rdx, rdi
0x180b6e813  lea     rcx, [rbp+8E0h+var_910]
0x180b6e817  call    ?SetImageAttributesFromBdp@GPIMAGEUTIL@@SAXPEAVImageAttributes@Gdiplus@@PEBUMSOBDRAWPARAM@@W4WrapMode@3@PEBVFPState@@_NAEAVGpImage@3@@Z; GPIMAGEUTIL::SetImageAttributesFromBdp(Gdiplus::ImageAttributes *,MSOBDRAWPARAM const *,Gdiplus::WrapMode,FPState const *,bool,Gdiplus::GpImage &)
0x180b6e81c  mov     r8, rdi; struct MSOBDRAWPARAM *
0x180b6e81f  mov     rdx, r14; struct MSODC *
0x180b6e822  lea     rcx, [rbp+8E0h+var_910]; struct Gdiplus::ImageAttributes *
0x180b6e826  call    ?SetImageAttributesFromDc@GPIMAGEUTIL@@SAXPEAVImageAttributes@Gdiplus@@PEBUMSODC@@PEBUMSOBDRAWPARAM@@@Z; GPIMAGEUTIL::SetImageAttributesFromDc(Gdiplus::ImageAttributes *,MSODC const *,MSOBDRAWPARAM const *)
0x180b6e82b  xorps   xmm0, xmm0
0x180b6e82e  movups  [rbp+8E0h+Buf1], xmm0
0x180b6e832  lea     rdx, [rbp+8E0h+Buf1]
0x180b6e836  mov     rcx, rbx
0x180b6e839  call    cs:__imp_GdipGetImageRawFormat
0x180b6e83f  test    eax, eax
0x180b6e841  jnz     loc_180B6E8D8
0x180b6e847  lea     r8d, [rax+10h]; Size
0x180b6e84b  lea     rdx, ImageFormatTIFF; Buf2
0x180b6e852  lea     rcx, [rbp+8E0h+Buf1]; Buf1
0x180b6e856  call    memcmp_0
0x180b6e85b  test    eax, eax
0x180b6e85d  jnz     short loc_180B6E8D8
0x180b6e85f  mov     dword ptr [rsp+9E0h+var_980], r13d
0x180b6e864  lea     rdx, [rsp+9E0h+var_980]
0x180b6e869  mov     rcx, rbx
0x180b6e86c  call    cs:__imp_GdipGetImagePixelFormat
0x180b6e872  test    eax, eax
0x180b6e874  jnz     short loc_180B6E8D8
0x180b6e876  cmp     dword ptr [rsp+9E0h+var_980], 200Fh
0x180b6e87e  jnz     short loc_180B6E8D8
0x180b6e880  lea     rax, [rsp+9E0h+var_970]
0x180b6e885  mov     [rsp+9E0h+var_9B8], rax
0x180b6e88a  mov     [rsp+9E0h+var_9C0], r13
0x180b6e88f  mov     r9d, 26200Ah
0x180b6e895  xor     r8d, r8d
0x180b6e898  mov     edx, [rsp+9E0h+var_9A0]
0x180b6e89c  mov     ecx, [rsp+9E0h+var_99C]
0x180b6e8a0  call    cs:__imp_GdipCreateBitmapFromScan0
0x180b6e8a6  test    eax, eax
0x180b6e8a8  jnz     short loc_180B6E8D8
0x180b6e8aa  lea     rdx, [rbp+8E0h+var_920]
0x180b6e8ae  mov     rcx, [rsp+9E0h+var_970]
0x180b6e8b3  call    cs:__imp_GdipGetImageGraphicsContext
0x180b6e8b9  test    eax, eax
0x180b6e8bb  jnz     short loc_180B6E8D8
0x180b6e8bd  xor     r9d, r9d
0x180b6e8c0  xor     r8d, r8d
0x180b6e8c3  mov     rdx, rbx
0x180b6e8c6  mov     rcx, [rbp+8E0h+var_920]
0x180b6e8ca  call    cs:__imp_GdipDrawImageI
0x180b6e8d0  test    eax, eax
0x180b6e8d2  cmovz   rbx, [rsp+9E0h+var_970]
0x180b6e8d8  lea     rax, [rsp+9E0h+var_990]
  ... truncated ...
```
