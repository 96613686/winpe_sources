# GEL::BitmapBasedPrinter::ProcessMetafile(bool)

- ea: `0x1800c26d0`
- end: `0x1800c2e8c`
- name: `?ProcessMetafile@BitmapBasedPrinter@GEL@@IEAAX_N@Z`
- size: `1980`
- prototype: `void __fastcall(GEL::BitmapBasedPrinter *__hidden this, bool)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1800c2678`

## callees

- `0x18002f5d0`
- `0x180036a00`
- `0x180050434`
- `0x180052fc8`
- `0x180055b26`
- `0x180056ee0`
- `0x18005f210`
- `0x180060884`
- `0x180061c38`
- `0x180062394`
- `0x180064888`
- `0x1800649b0`
- `0x180064bb8`
- `0x180064d9c`
- `0x180064e30`
- `0x1800c0f60`
- `0x1800c21c4`
- `0x1800c26d0`
- `0x1800c35f0`
- `0x1800c4838`
- `0x1800c489c`
- `0x1800c5f50`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800c2e34`
- `KERNEL32!SetLastError` at `0x1800c2e34`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c2762`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c2a37`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c2762`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800c2a37`
- `GDI32!DeleteDC` at `0x1800c27cd`
- `GDI32!DeleteDC` at `0x1800c27f4`
- `GDI32!DeleteDC` at `0x1800c2e2c`
- `GDI32!DeleteDC` at `0x1800c27cd`
- `GDI32!DeleteDC` at `0x1800c27f4`
- `GDI32!DeleteDC` at `0x1800c2e2c`
- `GDI32!CreateCompatibleDC` at `0x1800c2748`
- `GDI32!CreateCompatibleDC` at `0x1800c2c9e`
- `GDI32!CreateCompatibleDC` at `0x1800c2748`
- `GDI32!CreateCompatibleDC` at `0x1800c2c9e`
- `GDI32!GetEnhMetaFileHeader` at `0x1800c2873`
- `GDI32!GetEnhMetaFileHeader` at `0x1800c2873`
- `GDI32!CloseEnhMetaFile` at `0x1800c282d`
- `GDI32!CloseEnhMetaFile` at `0x1800c282d`
- `GDI32!SelectObject` at `0x1800c2cb5`
- `GDI32!SelectObject` at `0x1800c2cb5`
- `GDI32!DeleteEnhMetaFile` at `0x1800c2880`
- `GDI32!DeleteEnhMetaFile` at `0x1800c293c`
- `GDI32!DeleteEnhMetaFile` at `0x1800c2880`
- `GDI32!DeleteEnhMetaFile` at `0x1800c293c`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1800c296e`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1800c296e`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x1800c29e6`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x1800c29e6`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1800c27b8`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1800c27b8`
- `gdiplus!GdipDeleteRegion` at `0x1800c2b6f`
- `gdiplus!GdipDeleteRegion` at `0x1800c2b6f`
- `gdiplus!GdipCreateRegion` at `0x1800c2a42`
- `gdiplus!GdipCreateRegion` at `0x1800c2a42`
- `gdiplus!GdipGetClip` at `0x1800c2a5c`
- `gdiplus!GdipGetClip` at `0x1800c2a5c`
- `gdiplus!GdipResetWorldTransform` at `0x1800c2cfd`
- `gdiplus!GdipResetWorldTransform` at `0x1800c2cfd`
- `gdiplus!GdipDrawImageRectRectI` at `0x1800c2b3c`
- `gdiplus!GdipDrawImageRectRectI` at `0x1800c2dfd`
- `gdiplus!GdipDrawImageRectRectI` at `0x1800c2b3c`
- `gdiplus!GdipDrawImageRectRectI` at `0x1800c2dfd`
- `gdiplus!GdipSetPageUnit` at `0x1800c2ce6`
- `gdiplus!GdipSetPageUnit` at `0x1800c2ce6`
- `gdiplus!GdipSetInterpolationMode` at `0x1800c2d35`
- `gdiplus!GdipSetInterpolationMode` at `0x1800c2d35`
- `gdiplus!GdipDeleteGraphics` at `0x1800c27e1`
- `gdiplus!GdipDeleteGraphics` at `0x1800c2804`
- `gdiplus!GdipDeleteGraphics` at `0x1800c2e1a`
- `gdiplus!GdipDeleteGraphics` at `0x1800c27e1`
- `gdiplus!GdipDeleteGraphics` at `0x1800c2804`
- `gdiplus!GdipDeleteGraphics` at `0x1800c2e1a`
- `gdiplus!GdipCreateFromHDC` at `0x1800c2770`
- `gdiplus!GdipCreateFromHDC` at `0x1800c2cca`
- `gdiplus!GdipCreateFromHDC` at `0x1800c2770`
- `gdiplus!GdipCreateFromHDC` at `0x1800c2cca`
- `gdiplus!GdipDisposeImage` at `0x1800c2e43`
- `gdiplus!GdipDisposeImage` at `0x1800c2e43`
- `gdiplus!GdipSetSmoothingMode` at `0x1800c2d19`
- `gdiplus!GdipSetSmoothingMode` at `0x1800c2d19`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall GEL::BitmapBasedPrinter::ProcessMetafile(GEL::BitmapBasedPrinter *this, char a2)
{
  HDC CompatibleDC; // rbx
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD *v7; // rdi
  HENHMETAFILE v8; // rbx
  __m128i v9; // xmm6
  unsigned __int64 v10; // xmm0_8
  int v11; // r13d
  int v12; // r12d
  LONG top; // r14d
  LONG left; // r15d
  unsigned int MetafileHeaderFromMetafile; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  GEL::GraphicsSurface *v21; // rax
  struct Gdiplus::GpGraphics *GpGraphics; // rbx
  unsigned int Region; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  unsigned int Clip; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  int v29; // r8d
  int v30; // edx
  int v31; // ecx
  int v32; // eax
  __int64 v33; // r10
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  double v37; // xmm3_8
  double v38; // xmm2_8
  int v39; // ecx
  int v40; // eax
  int v41; // r9d
  int v42; // r8d
  int v43; // r10d
  int v44; // edx
  __m128i v45; // xmm6
  int v46; // ebx
  _DWORD *v47; // rax
  int v48; // edi
  HDC v49; // rbx
  unsigned int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // r8
  unsigned int v53; // eax
  __int64 v54; // rdx
  __int64 v55; // r8
  unsigned int v56; // eax
  __int64 v57; // rdx
  __int64 v58; // r8
  unsigned int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // r8
  unsigned int v62; // eax
  __int64 v63; // rdx
  __int64 v64; // r8
  int v65; // edx
  int v66; // r12d
  int v67; // ecx
  int v68; // eax
  __int64 v69; // r10
  unsigned int v70; // eax
  __int64 v71; // rdx
  __int64 v72; // r8
  _BYTE v73[16]; // [rsp+78h] [rbp-90h] BYREF
  struct Gdiplus::GpGraphics *v74[2]; // [rsp+88h] [rbp-80h] BYREF
  char v75; // [rsp+98h] [rbp-70h]
  _QWORD v76[2]; // [rsp+A0h] [rbp-68h] BYREF
  int v77; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v78; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v79; // [rsp+C8h] [rbp-40h] BYREF
  __m128i v80; // [rsp+D8h] [rbp-30h] BYREF
  _OWORD v81[2]; // [rsp+F8h] [rbp-10h] BYREF
  tagENHMETAHEADER EnhMetaHeader; // [rsp+118h] [rbp+10h] BYREF

  v75 = a2;
  GEL::BitmapBasedPrinter::FinishGDIRendering((GEL::BitmapBasedPrinter *)((char *)this + 24));
  GEL::PrinterClipStack::ReleaseGraphics((char *)this + 248, 1, *((_QWORD *)this + 8));
  Mso::TCntPtr<GEL::GraphicsSurface>::Clear((char *)this + 576);
  v76[0] = 0;
  v74[1] = 0;
  CompatibleDC = CreateCompatibleDC(0);
  v74[0] = (struct Gdiplus::GpGraphics *)CompatibleDC;
  v4 = GdipCreateFromHDC(CompatibleDC, v76);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v4, v5, v6, 38869201);
  v79 = 0;
  v73[0] = 0;
  v7 = (_QWORD *)((char *)this + 552);
  GdipEnumerateMetafileDestPoint(
    v76[0],
    *((_QWORD *)this + 69),
    &v79,
    &GEL::BitmapBasedPrinter::AnalyzeMetafileForDrawing,
    v73,
    0);
  if ( !v73[0] )
  {
    if ( CompatibleDC )
      DeleteDC(CompatibleDC);
    if ( v76[0] )
      GdipDeleteGraphics();
    return;
  }
  if ( CompatibleDC )
    DeleteDC(CompatibleDC);
  if ( v76[0] )
    GdipDeleteGraphics();
  v8 = 0;
  *(struct Gdiplus::GpGraphics **)((char *)v74 + 4) = (struct Gdiplus::GpGraphics *)1;
  HIDWORD(v74[1]) = 0;
  if ( *((_BYTE *)this + 584) )
  {
    memset_0(&EnhMetaHeader, 0, 0x8Cu);
    MetafileHeaderFromMetafile = GdipGetMetafileHeaderFromMetafile(*v7, &EnhMetaHeader);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(MetafileHeaderFromMetafile, v16, v17, 38869202);
    left = EnhMetaHeader.rclFrame.left;
    v74[0] = *(struct Gdiplus::GpGraphics **)&EnhMetaHeader.rclFrame.left;
    top = EnhMetaHeader.rclFrame.top;
    v12 = EnhMetaHeader.rclFrame.left + EnhMetaHeader.rclFrame.right + 1;
    LODWORD(v74[1]) = v12;
    v11 = EnhMetaHeader.rclFrame.top + EnhMetaHeader.rclFrame.bottom + 1;
    HIDWORD(v74[1]) = v11;
    v9 = *(__m128i *)v74;
    goto LABEL_22;
  }
  v8 = CloseEnhMetaFile(*((HDC *)this + 68));
  if ( !v8 )
  {
    ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty((char *)this + 552);
    *((_QWORD *)this + 68) = 0;
    Ofc::CLastErrorException::ThrowTag(0x2CA6D2u);
    __debugbreak();
  }
  memset_0(&EnhMetaHeader, 0, sizeof(EnhMetaHeader));
  if ( !GetEnhMetaFileHeader(v8, 0x6Cu, &EnhMetaHeader) )
  {
    DeleteEnhMetaFile(v8);
    ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty((char *)this + 552);
    *((_QWORD *)this + 68) = 0;
    Ofc::CLastErrorException::ThrowTag(0x2CA6D3u);
    __debugbreak();
  }
  LODWORD(v74[0]) = EnhMetaHeader.rclBounds.left;
  HIDWORD(v74[0]) = EnhMetaHeader.rclBounds.right + 1;
  LODWORD(v74[1]) = EnhMetaHeader.rclBounds.top;
  HIDWORD(v74[1]) = EnhMetaHeader.rclBounds.bottom + 1;
  v80 = *(__m128i *)((char *)this + 324);
  Math::TRect<Math::TUnits<int,Math::DevicePixels>>::IntersectWith<Math::TUnits<int,Math::DevicePixels>,0>(&v80, v74);
  v9 = v80;
  v10 = _mm_srli_si128(v80, 8).m128i_u64[0];
  if ( v80.m128i_i32[0] < (int)v10 && v80.m128i_i32[1] < SHIDWORD(v10) )
  {
    v11 = _mm_cvtsi128_si32(_mm_srli_si128(v80, 12));
    v12 = _mm_cvtsi128_si32(_mm_srli_si128(v80, 8));
    top = _mm_cvtsi128_si32(_mm_srli_si128(v80, 4));
    left = _mm_cvtsi128_si32(v80);
LABEL_22:
    v76[0] = (char *)this + 324;
    CodeMarker(1536);
    v78 = 0;
    if ( !*((_BYTE *)this + 584) )
    {
      v18 = GdipCreateMetafileFromEmf(v8, 1, &v78);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v18, v19, v20, 38869203);
    }
    v21 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->((char *)this + 312);
    GpGraphics = GEL::GraphicsSurface::GetGpGraphics(v21);
    v74[0] = 0;
    v74[1] = GpGraphics;
    GEL::GDIPixelModeRestorer::GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v81, GpGraphics);
    if ( v74[0] )
      CrashWithRecovery(0x1E55E058u, 0);
    Region = GdipCreateRegion(v74);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(Region, v24, v25, 39081176);
    Clip = GdipGetClip(GpGraphics, v74[0]);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(Clip, v27, v28, 39081177);
    GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)v81);
    GEL::GDIPixelModeRestorer::GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)&v80, GpGraphics);
    GEL::Printer::SetClipToBounds(GpGraphics, v76[0]);
    GEL::BitmapBasedPrinter::SendBitmapToPrinter(this);
    if ( left > v12 || top > v11 )
      v29 = 0;
    else
      v29 = v11 - top;
    if ( left > v12 || top > v11 )
      v30 = 0;
    else
      v30 = v12 - left;
    if ( left > v12 || top > v11 )
      v31 = 0;
    else
      v31 = v11 - top;
    if ( left > v12 || top > v11 )
      v32 = 0;
    else
      v32 = v12 - left;
    if ( *((_BYTE *)this + 584) )
      v33 = *v7;
    else
      v33 = v78;
    v34 = GdipDrawImageRectRectI(
            GpGraphics,
            v33,
            (unsigned int)left,
            (unsigned int)top,
            v32,
            v31,
            left,
            top,
            v30,
            v29,
            2,
            0,
            0,
            0);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v34, v35, v36, 38869204);
    GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer((GEL::GDIPixelModeRestorer *)&v80);
    GEL::GDIClip::Unapply((GEL::GDIClip *)v74, v74[1]);
    if ( v74[0] )
      GdipDeleteRegion();
    if ( !v75 )
    {
      *(__m128i *)v74 = v9;
      GEL::BitmapBasedPrinter::GetScalingFactor(this, &v80);
      v37 = 1.0 / *(double *)&v80.m128i_i64[1];
      v38 = 1.0 / *(double *)v80.m128i_i64;
      v39 = -*((_DWORD *)this + 82);
      v40 = -*(_DWORD *)v76[0];
      v41 = left - *(_DWORD *)v76[0];
      LODWORD(v74[0]) = v41;
      v42 = v39 + HIDWORD(v74[0]);
      HIDWORD(v74[0]) += v39;
      v43 = v40 + LODWORD(v74[1]);
      LODWORD(v74[1]) = v43;
      v44 = v39 + HIDWORD(v74[1]);
      HIDWORD(v74[1]) += v39;
      if ( v41 > v43 || v42 > v44 )
      {
        v81[0] = _mm_load_si128((const __m128i *)&_xmm);
        v81[1] = 0;
      }
      else
      {
        *(double *)v74 = (double)v43 * v38;
        *(double *)&v74[1] = (double)v44 * v37;
        *(double *)v80.m128i_i64 = (double)v41 * v38;
        *(double *)&v80.m128i_i64[1] = (double)v42 * v37;
        Math::TRect<Math::TUnits<double,Math::DevicePixels>>::TRect<Math::TUnits<double,Math::DevicePixels>>(
          v81,
          &v80,
          v74);
      }
      v45 = *(__m128i *)Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(
                          v76,
                          v81);
      *(__m128i *)v74 = v45;
      v46 = *(_DWORD *)sub_1800C21C4(&v77);
      v47 = (_DWORD *)sub_1800C21C4(v76);
      LODWORD(v79) = *v47 + _mm_cvtsi128_si32(v45);
      LODWORD(v74[0]) = v79;
      HIDWORD(v74[0]) += v46;
      v77 = *v47 + LODWORD(v74[1]);
      LODWORD(v74[1]) = v77;
      v48 = v46 + HIDWORD(v74[1]);
      HIDWORD(v74[1]) += v46;
      v49 = CreateCompatibleDC(0);
      v80.m128i_i64[0] = (__int64)v49;
      SelectObject(v49, *((HGDIOBJ *)this + 59));
      v76[0] = 0;
      v50 = GdipCreateFromHDC(v49, v76);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v50, v51, v52, 38869205);
      v53 = GdipSetPageUnit(v76[0], 2);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v53, v54, v55, 38869206);
      v56 = GdipResetWorldTransform(v76[0]);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v56, v57, v58, 38869207);
      v59 = GdipSetSmoothingMode(v76[0], 3);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v59, v60, v61, 38869208);
      v62 = GdipSetInterpolationMode(v76[0], 5);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v62, v63, v64, 38869209);
      GEL::Printer::SetClipToBounds(v76[0], v74);
      if ( left > v12 || top > v11 )
        v65 = 0;
      else
        v65 = v11 - top;
      if ( left > v12 || top > v11 )
        v66 = 0;
      else
        v66 = v12 - left;
      if ( (int)v79 > v77 || SHIDWORD(v74[0]) > v48 )
        v67 = 0;
      else
        v67 = v48 - HIDWORD(v74[0]);
      if ( (int)v79 > v77 || SHIDWORD(v74[0]) > v48 )
        v68 = 0;
      else
        v68 = v77 - v79;
      if ( *((_BYTE *)this + 584) )
        v69 = *((_QWORD *)this + 69);
      else
        v69 = v78;
      v70 = GdipDrawImageRectRectI(
              v76[0],
              v69,
              (unsigned int)v79,
              HIDWORD(v74[0]),
              v68,
              v67,
              left,
              top,
              v66,
              v65,
              2,
              0,
              0,
              0);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v70, v71, v72, 38869210);
      if ( v76[0] )
      {
        GdipDeleteGraphics();
        v76[0] = 0;
      }
      if ( v49 )
        DeleteDC(v49);
    }
    SetLastError(0);
    if ( v78 )
    {
      GdipDisposeImage();
      v78 = 0;
    }
    CodeMarker(1537);
    return;
  }
  if ( !*((_BYTE *)this + 584) )
    DeleteEnhMetaFile(v8);
  ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty((char *)this + 552);
  *((_QWORD *)this + 68) = 0;
}

```

## disassembly

```asm
0x1800c26d0  mov     rax, rsp
0x1800c26d3  mov     [rax+10h], rbx
0x1800c26d7  mov     [rax+18h], rsi
0x1800c26db  mov     [rax+20h], rdi
0x1800c26df  push    rbp
0x1800c26e0  push    r12
0x1800c26e2  push    r13
0x1800c26e4  push    r14
0x1800c26e6  push    r15
0x1800c26e8  lea     rbp, [rax-0E8h]
0x1800c26ef  sub     rsp, 1C0h
0x1800c26f6  movaps  xmmword ptr [rax-38h], xmm6
0x1800c26fa  mov     rax, cs:__security_cookie
0x1800c2701  xor     rax, rsp
0x1800c2704  mov     [rbp+0E0h+var_38], rax
0x1800c270b  mov     [rbp+0E0h+var_150], dl
0x1800c270e  mov     rsi, rcx
0x1800c2711  add     rcx, 18h; this
0x1800c2715  call    ?FinishGDIRendering@BitmapBasedPrinter@GEL@@UEAAXXZ; GEL::BitmapBasedPrinter::FinishGDIRendering(void)
0x1800c271a  lea     rcx, [rsi+0F8h]
0x1800c2721  mov     r8, [rsi+40h]
0x1800c2725  mov     edx, 1
0x1800c272a  call    ?ReleaseGraphics@PrinterClipStack@GEL@@QEAAXW4SurfaceType@12@PEBVFrame@ITarget@Gfx@@@Z; GEL::PrinterClipStack::ReleaseGraphics(GEL::PrinterClipStack::SurfaceType,Gfx::ITarget::Frame const *)
0x1800c272f  lea     rcx, [rsi+240h]
0x1800c2736  call    ?Clear@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAXXZ; Mso::TCntPtr<GEL::GraphicsSurface>::Clear(void)
0x1800c273b  xor     r15d, r15d
0x1800c273e  mov     [rbp+0E0h+var_148], r15
0x1800c2742  mov     [rbp+0E0h+var_160+8], r15
0x1800c2746  xor     ecx, ecx; hdc
0x1800c2748  call    cs:__imp_CreateCompatibleDC
0x1800c274e  mov     rbx, rax
0x1800c2751  mov     [rbp+0E0h+var_160], rax
0x1800c2755  cmp     [rbp+0E0h+var_148], r15
0x1800c2759  jz      short loc_1800C2769
0x1800c275b  xor     edx, edx
0x1800c275d  mov     ecx, 1E55E058h
0x1800c2762  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800c2768  nop
0x1800c2769  lea     rdx, [rbp+0E0h+var_148]
0x1800c276d  mov     rcx, rbx
0x1800c2770  call    cs:__imp_GdipCreateFromHDC
0x1800c2776  mov     r9d, 25118D1h
0x1800c277c  mov     ecx, eax
0x1800c277e  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c2783  mov     [rbp+0E0h+var_120], 0
0x1800c278b  mov     [rsp+1E0h+var_170], r15b
0x1800c2790  lea     rdi, [rsi+228h]
0x1800c2797  mov     qword ptr [rsp+1E0h+var_1B8], r15
0x1800c279c  lea     rax, [rsp+1E0h+var_170]
0x1800c27a1  mov     [rsp+1E0h+var_1C0], rax
0x1800c27a6  lea     r9, ?AnalyzeMetafileForDrawing@BitmapBasedPrinter@GEL@@KAHW4EmfPlusRecordType@Gdiplus@@IIPEBEPEAX@Z; GEL::BitmapBasedPrinter::AnalyzeMetafileForDrawing(Gdiplus::EmfPlusRecordType,uint,uint,uchar const *,void *)
0x1800c27ad  lea     r8, [rbp+0E0h+var_120]
0x1800c27b1  mov     rdx, [rdi]
0x1800c27b4  mov     rcx, [rbp+0E0h+var_148]
0x1800c27b8  call    cs:__imp_GdipEnumerateMetafileDestPoint
0x1800c27be  cmp     [rsp+1E0h+var_170], r15b
0x1800c27c3  jnz     short loc_1800C27EC
0x1800c27c5  test    rbx, rbx
0x1800c27c8  jz      short loc_1800C27D4
0x1800c27ca  mov     rcx, rbx; hdc
0x1800c27cd  call    cs:__imp_DeleteDC
0x1800c27d3  nop
0x1800c27d4  mov     rcx, [rbp+0E0h+var_148]
0x1800c27d8  test    rcx, rcx
0x1800c27db  jz      loc_1800C2E57
0x1800c27e1  call    cs:__imp_GdipDeleteGraphics
0x1800c27e7  jmp     loc_1800C2E57
0x1800c27ec  test    rbx, rbx
0x1800c27ef  jz      short loc_1800C27FB
0x1800c27f1  mov     rcx, rbx; hdc
0x1800c27f4  call    cs:__imp_DeleteDC
0x1800c27fa  nop
0x1800c27fb  mov     rcx, [rbp+0E0h+var_148]
0x1800c27ff  test    rcx, rcx
0x1800c2802  jz      short loc_1800C280A
0x1800c2804  call    cs:__imp_GdipDeleteGraphics
0x1800c280a  mov     rbx, r15
0x1800c280d  mov     [rbp+0E0h+var_160+4], 1
0x1800c2815  mov     dword ptr [rbp+0E0h+var_160+0Ch], r15d
0x1800c2819  cmp     [rsi+248h], r15b
0x1800c2820  jnz     loc_1800C2956
0x1800c2826  mov     rcx, [rsi+220h]; hdc
0x1800c282d  call    cs:__imp_CloseEnhMetaFile
0x1800c2833  mov     rbx, rax
0x1800c2836  test    rax, rax
0x1800c2839  jnz     short loc_1800C2855
0x1800c283b  mov     rcx, rdi
0x1800c283e  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800c2843  mov     [rsi+220h], r15
0x1800c284a  mov     ecx, 2CA6D2h; unsigned int
0x1800c284f  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x1800c2854  int     3; Trap to Debugger
0x1800c2855  mov     r14d, 6Ch ; 'l'
0x1800c285b  mov     r8d, r14d; Size
0x1800c285e  xor     edx, edx; Val
0x1800c2860  lea     rcx, [rbp+0E0h+EnhMetaHeader]; void *
0x1800c2864  call    memset_0
0x1800c2869  lea     r8, [rbp+0E0h+EnhMetaHeader]; lpEnhMetaHeader
0x1800c286d  mov     edx, r14d; nSize
0x1800c2870  mov     rcx, rbx; hemf
0x1800c2873  call    cs:__imp_GetEnhMetaFileHeader
0x1800c2879  test    eax, eax
0x1800c287b  jnz     short loc_1800C28A0
0x1800c287d  mov     rcx, rbx; hmf
0x1800c2880  call    cs:__imp_DeleteEnhMetaFile
0x1800c2886  mov     rcx, rdi
0x1800c2889  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800c288e  mov     [rsi+220h], r15
0x1800c2895  mov     ecx, 2CA6D3h; unsigned int
0x1800c289a  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x1800c289f  int     3; Trap to Debugger
0x1800c28a0  mov     eax, [rbp+0E0h+EnhMetaHeader.rclBounds.left]
0x1800c28a3  mov     dword ptr [rbp+0E0h+var_160], eax
0x1800c28a6  mov     eax, [rbp+0E0h+EnhMetaHeader.rclBounds.right]
0x1800c28a9  inc     eax
0x1800c28ab  mov     dword ptr [rbp+0E0h+var_160+4], eax
0x1800c28ae  mov     eax, [rbp+0E0h+EnhMetaHeader.rclBounds.top]
0x1800c28b1  mov     dword ptr [rbp+0E0h+var_160+8], eax
0x1800c28b4  mov     eax, [rbp+0E0h+EnhMetaHeader.rclBounds.bottom]
0x1800c28b7  inc     eax
0x1800c28b9  mov     dword ptr [rbp+0E0h+var_160+0Ch], eax
0x1800c28bc  movups  xmm0, xmmword ptr [rsi+144h]
0x1800c28c3  movdqu  [rbp+0E0h+var_110], xmm0
0x1800c28c8  lea     rdx, [rbp+0E0h+var_160]
0x1800c28cc  lea     rcx, [rbp+0E0h+var_110]
0x1800c28d0  call    ??$IntersectWith@V?$TUnits@HUDevicePixels@Math@@@Math@@$0A@@?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@QEAAXAEBU01@@Z; Math::TRect<Math::TUnits<int,Math::DevicePixels>>::IntersectWith<Math::TUnits<int,Math::DevicePixels>,0>(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &)
0x1800c28d5  movaps  xmm6, [rbp+0E0h+var_110]
0x1800c28d9  movq    rax, xmm6
0x1800c28de  movdqa  xmm0, xmm6
0x1800c28e2  psrldq  xmm0, 8
0x1800c28e7  movq    rcx, xmm0
0x1800c28ec  cmp     eax, ecx
0x1800c28ee  jge     short loc_1800C2930
0x1800c28f0  shr     rax, 20h
0x1800c28f4  shr     rcx, 20h
0x1800c28f8  cmp     eax, ecx
0x1800c28fa  jge     short loc_1800C2930
0x1800c28fc  movdqa  xmm0, xmm6
0x1800c2900  psrldq  xmm0, 0Ch
0x1800c2905  movd    r13d, xmm0
0x1800c290a  movdqa  xmm1, xmm6
0x1800c290e  psrldq  xmm1, 8
0x1800c2913  movd    r12d, xmm1
0x1800c2918  movdqa  xmm0, xmm6
0x1800c291c  psrldq  xmm0, 4
0x1800c2921  movd    r14d, xmm0
0x1800c2926  movd    r15d, xmm6
0x1800c292b  jmp     loc_1800C29B1
0x1800c2930  cmp     [rsi+248h], r15b
0x1800c2937  jnz     short loc_1800C2942
0x1800c2939  mov     rcx, rbx; hmf
0x1800c293c  call    cs:__imp_DeleteEnhMetaFile
0x1800c2942  mov     rcx, rdi
0x1800c2945  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800c294a  mov     [rsi+220h], r15
0x1800c2951  jmp     loc_1800C2E57
0x1800c2956  xor     edx, edx; Val
0x1800c2958  mov     r8d, 8Ch; Size
0x1800c295e  lea     rcx, [rbp+0E0h+EnhMetaHeader]; void *
0x1800c2962  call    memset_0
0x1800c2967  lea     rdx, [rbp+0E0h+EnhMetaHeader]
0x1800c296b  mov     rcx, [rdi]
0x1800c296e  call    cs:__imp_GdipGetMetafileHeaderFromMetafile
0x1800c2974  mov     r9d, 25118D2h
0x1800c297a  mov     ecx, eax
0x1800c297c  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c2981  mov     r15d, [rbp+0E0h+EnhMetaHeader.rclFrame.left]
0x1800c2985  mov     dword ptr [rbp+0E0h+var_160], r15d
0x1800c2989  mov     r14d, [rbp+0E0h+EnhMetaHeader.rclFrame.top]
0x1800c298d  mov     dword ptr [rbp+0E0h+var_160+4], r14d
0x1800c2991  mov     r12d, [rbp+0E0h+EnhMetaHeader.rclFrame.right]
0x1800c2995  inc     r12d
0x1800c2998  add     r12d, r15d
0x1800c299b  mov     dword ptr [rbp+0E0h+var_160+8], r12d
0x1800c299f  mov     r13d, [rbp+0E0h+EnhMetaHeader.rclFrame.bottom]
0x1800c29a3  inc     r13d
0x1800c29a6  add     r13d, r14d
0x1800c29a9  mov     dword ptr [rbp+0E0h+var_160+0Ch], r13d
0x1800c29ad  movaps  xmm6, xmmword ptr [rbp+0E0h+var_160]
0x1800c29b1  mov     rax, rsi
0x1800c29b4  add     rax, 144h
0x1800c29ba  mov     [rbp+0E0h+var_148], rax
0x1800c29be  mov     ecx, 600h
0x1800c29c3  call    CodeMarker
0x1800c29c8  nop
0x1800c29c9  mov     [rbp+0E0h+var_130], 0
0x1800c29d1  cmp     byte ptr [rsi+248h], 0
0x1800c29d8  jnz     short loc_1800C29F9
0x1800c29da  lea     r8, [rbp+0E0h+var_130]
0x1800c29de  mov     edx, 1
0x1800c29e3  mov     rcx, rbx
0x1800c29e6  call    cs:__imp_GdipCreateMetafileFromEmf
0x1800c29ec  mov     r9d, 25118D3h
0x1800c29f2  mov     ecx, eax
0x1800c29f4  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c29f9  lea     rcx, [rsi+138h]
0x1800c2a00  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800c2a05  mov     rcx, rax; this
0x1800c2a08  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c2a0d  mov     rbx, rax
0x1800c2a10  mov     [rbp+0E0h+var_160], 0
0x1800c2a18  mov     [rbp+0E0h+var_160+8], rax
0x1800c2a1c  mov     rdx, rax; struct Gdiplus::GpGraphics *
0x1800c2a1f  lea     rcx, [rbp+0E0h+var_F0]; this
0x1800c2a23  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800c2a28  nop
0x1800c2a29  cmp     [rbp+0E0h+var_160], 0
0x1800c2a2e  jz      short loc_1800C2A3E
0x1800c2a30  xor     edx, edx
0x1800c2a32  mov     ecx, 1E55E058h
0x1800c2a37  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800c2a3d  nop
0x1800c2a3e  lea     rcx, [rbp+0E0h+var_160]
0x1800c2a42  call    cs:__imp_GdipCreateRegion
0x1800c2a48  mov     r9d, 25454D8h
0x1800c2a4e  mov     ecx, eax
0x1800c2a50  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c2a55  mov     rdx, [rbp+0E0h+var_160]
0x1800c2a59  mov     rcx, rbx
0x1800c2a5c  call    cs:__imp_GdipGetClip
0x1800c2a62  mov     r9d, 25454D9h
0x1800c2a68  mov     ecx, eax
0x1800c2a6a  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c2a6f  nop
0x1800c2a70  lea     rcx, [rbp+0E0h+var_F0]; this
0x1800c2a74  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x1800c2a79  mov     rdx, rbx; struct Gdiplus::GpGraphics *
0x1800c2a7c  lea     rcx, [rbp+0E0h+var_110]; this
0x1800c2a80  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800c2a85  mov     rdx, [rbp+0E0h+var_148]
0x1800c2a89  mov     rcx, rbx
0x1800c2a8c  call    ?SetClipToBounds@Printer@GEL@@KAXPEAVGpGraphics@Gdiplus@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z; GEL::Printer::SetClipToBounds(Gdiplus::GpGraphics *,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &)
0x1800c2a91  mov     rcx, rsi; this
0x1800c2a94  call    ?SendBitmapToPrinter@BitmapBasedPrinter@GEL@@IEAAXXZ; GEL::BitmapBasedPrinter::SendBitmapToPrinter(void)
0x1800c2a99  cmp     r15d, r12d
0x1800c2a9c  jg      short loc_1800C2AAB
0x1800c2a9e  cmp     r14d, r13d
0x1800c2aa1  jg      short loc_1800C2AAB
0x1800c2aa3  mov     r8d, r13d
0x1800c2aa6  sub     r8d, r14d
0x1800c2aa9  jmp     short loc_1800C2AAE
0x1800c2aab  xor     r8d, r8d
0x1800c2aae  cmp     r15d, r12d
0x1800c2ab1  jg      short loc_1800C2AC0
0x1800c2ab3  cmp     r14d, r13d
0x1800c2ab6  jg      short loc_1800C2AC0
0x1800c2ab8  mov     edx, r12d
0x1800c2abb  sub     edx, r15d
0x1800c2abe  jmp     short loc_1800C2AC2
0x1800c2ac0  xor     edx, edx
0x1800c2ac2  cmp     r15d, r12d
0x1800c2ac5  jg      short loc_1800C2AD4
0x1800c2ac7  cmp     r14d, r13d
0x1800c2aca  jg      short loc_1800C2AD4
0x1800c2acc  mov     ecx, r13d
0x1800c2acf  sub     ecx, r14d
0x1800c2ad2  jmp     short loc_1800C2AD6
0x1800c2ad4  xor     ecx, ecx
0x1800c2ad6  cmp     r15d, r12d
0x1800c2ad9  jg      short loc_1800C2AE8
0x1800c2adb  cmp     r14d, r13d
0x1800c2ade  jg      short loc_1800C2AE8
0x1800c2ae0  mov     eax, r12d
0x1800c2ae3  sub     eax, r15d
0x1800c2ae6  jmp     short loc_1800C2AEA
0x1800c2ae8  xor     eax, eax
0x1800c2aea  cmp     byte ptr [rsi+248h], 0
0x1800c2af1  jz      short loc_1800C2AF8
0x1800c2af3  mov     r10, [rdi]
0x1800c2af6  jmp     short loc_1800C2AFC
0x1800c2af8  mov     r10, [rbp+0E0h+var_130]
0x1800c2afc  xor     edi, edi
0x1800c2afe  mov     qword ptr [rsp+1E0h+var_178], rdi
0x1800c2b03  mov     [rsp+1E0h+var_180], rdi
0x1800c2b08  mov     [rsp+1E0h+var_188], rdi
0x1800c2b0d  mov     dword ptr [rsp+1E0h+var_190], 2
0x1800c2b15  mov     [rsp+1E0h+var_198], r8d
0x1800c2b1a  mov     [rsp+1E0h+var_1A0], edx
0x1800c2b1e  mov     [rsp+1E0h+var_1A8], r14d
0x1800c2b23  mov     [rsp+1E0h+var_1B0], r15d
0x1800c2b28  mov     [rsp+1E0h+var_1B8], ecx
0x1800c2b2c  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x1800c2b30  mov     r9d, r14d
0x1800c2b33  mov     r8d, r15d
0x1800c2b36  mov     rdx, r10
0x1800c2b39  mov     rcx, rbx
0x1800c2b3c  call    cs:__imp_GdipDrawImageRectRectI
0x1800c2b42  mov     r9d, 25118D4h
0x1800c2b48  mov     ecx, eax
0x1800c2b4a  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c2b4f  nop
0x1800c2b50  lea     rcx, [rbp+0E0h+var_110]; this
0x1800c2b54  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x1800c2b59  mov     rdx, [rbp+0E0h+var_160+8]; struct Gdiplus::GpGraphics *
0x1800c2b5d  lea     rcx, [rbp+0E0h+var_160]; this
0x1800c2b61  call    ?Unapply@GDIClip@GEL@@QEAAXAEAVGpGraphics@Gdiplus@@@Z; GEL::GDIClip::Unapply(Gdiplus::GpGraphics &)
0x1800c2b66  mov     rcx, [rbp+0E0h+var_160]
0x1800c2b6a  test    rcx, rcx
0x1800c2b6d  jz      short loc_1800C2B75
0x1800c2b6f  call    cs:__imp_GdipDeleteRegion
  ... truncated ...
```
