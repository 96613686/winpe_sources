# GEL::BitmapBasedPrinter::ProcessMetafile(bool)

- ea: `0x1800a4d60`
- end: `0x1800a551c`
- name: `?ProcessMetafile@BitmapBasedPrinter@GEL@@IEAAX_N@Z`
- size: `1980`
- prototype: `void __fastcall(GEL::BitmapBasedPrinter *__hidden this, bool)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1800a4d08`

## callees

- `0x18002fc50`
- `0x18003e924`
- `0x180051d08`
- `0x1800532f8`
- `0x1800565ba`
- `0x1800578b0`
- `0x180072d00`
- `0x18007efec`
- `0x18007f754`
- `0x1800817d4`
- `0x180082268`
- `0x180082598`
- `0x1800826c0`
- `0x1800828c8`
- `0x180082aac`
- `0x1800a4550`
- `0x1800a4d60`
- `0x1800a5ac0`
- `0x1800a67a8`
- `0x1800a6848`
- `0x1800a68c8`
- `0x1800cb9c0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800a54c4`
- `KERNEL32!SetLastError` at `0x1800a54c4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a4df2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a50c7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a4df2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a50c7`
- `GDI32!DeleteDC` at `0x1800a4e5d`
- `GDI32!DeleteDC` at `0x1800a4e84`
- `GDI32!DeleteDC` at `0x1800a54bc`
- `GDI32!DeleteDC` at `0x1800a4e5d`
- `GDI32!DeleteDC` at `0x1800a4e84`
- `GDI32!DeleteDC` at `0x1800a54bc`
- `GDI32!CreateCompatibleDC` at `0x1800a4dd8`
- `GDI32!CreateCompatibleDC` at `0x1800a532e`
- `GDI32!CreateCompatibleDC` at `0x1800a4dd8`
- `GDI32!CreateCompatibleDC` at `0x1800a532e`
- `GDI32!GetEnhMetaFileHeader` at `0x1800a4f03`
- `GDI32!GetEnhMetaFileHeader` at `0x1800a4f03`
- `GDI32!CloseEnhMetaFile` at `0x1800a4ebd`
- `GDI32!CloseEnhMetaFile` at `0x1800a4ebd`
- `GDI32!SelectObject` at `0x1800a5345`
- `GDI32!SelectObject` at `0x1800a5345`
- `GDI32!DeleteEnhMetaFile` at `0x1800a4f10`
- `GDI32!DeleteEnhMetaFile` at `0x1800a4fcc`
- `GDI32!DeleteEnhMetaFile` at `0x1800a4f10`
- `GDI32!DeleteEnhMetaFile` at `0x1800a4fcc`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1800a4ffe`
- `gdiplus!GdipGetMetafileHeaderFromMetafile` at `0x1800a4ffe`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x1800a5076`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x1800a5076`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1800a4e48`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1800a4e48`
- `gdiplus!GdipDeleteRegion` at `0x1800a51ff`
- `gdiplus!GdipDeleteRegion` at `0x1800a51ff`
- `gdiplus!GdipCreateRegion` at `0x1800a50d2`
- `gdiplus!GdipCreateRegion` at `0x1800a50d2`
- `gdiplus!GdipGetClip` at `0x1800a50ec`
- `gdiplus!GdipGetClip` at `0x1800a50ec`
- `gdiplus!GdipResetWorldTransform` at `0x1800a538d`
- `gdiplus!GdipResetWorldTransform` at `0x1800a538d`
- `gdiplus!GdipDrawImageRectRectI` at `0x1800a51cc`
- `gdiplus!GdipDrawImageRectRectI` at `0x1800a548d`
- `gdiplus!GdipDrawImageRectRectI` at `0x1800a51cc`
- `gdiplus!GdipDrawImageRectRectI` at `0x1800a548d`
- `gdiplus!GdipSetPageUnit` at `0x1800a5376`
- `gdiplus!GdipSetPageUnit` at `0x1800a5376`
- `gdiplus!GdipSetInterpolationMode` at `0x1800a53c5`
- `gdiplus!GdipSetInterpolationMode` at `0x1800a53c5`
- `gdiplus!GdipDeleteGraphics` at `0x1800a4e71`
- `gdiplus!GdipDeleteGraphics` at `0x1800a4e94`
- `gdiplus!GdipDeleteGraphics` at `0x1800a54aa`
- `gdiplus!GdipDeleteGraphics` at `0x1800a4e71`
- `gdiplus!GdipDeleteGraphics` at `0x1800a4e94`
- `gdiplus!GdipDeleteGraphics` at `0x1800a54aa`
- `gdiplus!GdipCreateFromHDC` at `0x1800a4e00`
- `gdiplus!GdipCreateFromHDC` at `0x1800a535a`
- `gdiplus!GdipCreateFromHDC` at `0x1800a4e00`
- `gdiplus!GdipCreateFromHDC` at `0x1800a535a`
- `gdiplus!GdipDisposeImage` at `0x1800a54d3`
- `gdiplus!GdipDisposeImage` at `0x1800a54d3`
- `gdiplus!GdipSetSmoothingMode` at `0x1800a53a9`
- `gdiplus!GdipSetSmoothingMode` at `0x1800a53a9`

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
      v46 = *(_DWORD *)sub_1800A6848(&v77);
      v47 = (_DWORD *)sub_1800A6848(v76);
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
0x1800a4d60  mov     rax, rsp
0x1800a4d63  mov     [rax+10h], rbx
0x1800a4d67  mov     [rax+18h], rsi
0x1800a4d6b  mov     [rax+20h], rdi
0x1800a4d6f  push    rbp
0x1800a4d70  push    r12
0x1800a4d72  push    r13
0x1800a4d74  push    r14
0x1800a4d76  push    r15
0x1800a4d78  lea     rbp, [rax-0E8h]
0x1800a4d7f  sub     rsp, 1C0h
0x1800a4d86  movaps  xmmword ptr [rax-38h], xmm6
0x1800a4d8a  mov     rax, cs:__security_cookie
0x1800a4d91  xor     rax, rsp
0x1800a4d94  mov     [rbp+0E0h+var_38], rax
0x1800a4d9b  mov     [rbp+0E0h+var_150], dl
0x1800a4d9e  mov     rsi, rcx
0x1800a4da1  add     rcx, 18h; this
0x1800a4da5  call    ?FinishGDIRendering@BitmapBasedPrinter@GEL@@UEAAXXZ; GEL::BitmapBasedPrinter::FinishGDIRendering(void)
0x1800a4daa  lea     rcx, [rsi+0F8h]
0x1800a4db1  mov     r8, [rsi+40h]
0x1800a4db5  mov     edx, 1
0x1800a4dba  call    ?ReleaseGraphics@PrinterClipStack@GEL@@QEAAXW4SurfaceType@12@PEBVFrame@ITarget@Gfx@@@Z; GEL::PrinterClipStack::ReleaseGraphics(GEL::PrinterClipStack::SurfaceType,Gfx::ITarget::Frame const *)
0x1800a4dbf  lea     rcx, [rsi+240h]
0x1800a4dc6  call    ?Clear@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAXXZ; Mso::TCntPtr<GEL::GraphicsSurface>::Clear(void)
0x1800a4dcb  xor     r15d, r15d
0x1800a4dce  mov     [rbp+0E0h+var_148], r15
0x1800a4dd2  mov     [rbp+0E0h+var_160+8], r15
0x1800a4dd6  xor     ecx, ecx; hdc
0x1800a4dd8  call    cs:__imp_CreateCompatibleDC
0x1800a4dde  mov     rbx, rax
0x1800a4de1  mov     [rbp+0E0h+var_160], rax
0x1800a4de5  cmp     [rbp+0E0h+var_148], r15
0x1800a4de9  jz      short loc_1800A4DF9
0x1800a4deb  xor     edx, edx
0x1800a4ded  mov     ecx, 1E55E058h
0x1800a4df2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800a4df8  nop
0x1800a4df9  lea     rdx, [rbp+0E0h+var_148]
0x1800a4dfd  mov     rcx, rbx
0x1800a4e00  call    cs:__imp_GdipCreateFromHDC
0x1800a4e06  mov     r9d, 25118D1h
0x1800a4e0c  mov     ecx, eax
0x1800a4e0e  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a4e13  mov     [rbp+0E0h+var_120], 0
0x1800a4e1b  mov     [rsp+1E0h+var_170], r15b
0x1800a4e20  lea     rdi, [rsi+228h]
0x1800a4e27  mov     qword ptr [rsp+1E0h+var_1B8], r15
0x1800a4e2c  lea     rax, [rsp+1E0h+var_170]
0x1800a4e31  mov     [rsp+1E0h+var_1C0], rax
0x1800a4e36  lea     r9, ?AnalyzeMetafileForDrawing@BitmapBasedPrinter@GEL@@KAHW4EmfPlusRecordType@Gdiplus@@IIPEBEPEAX@Z; GEL::BitmapBasedPrinter::AnalyzeMetafileForDrawing(Gdiplus::EmfPlusRecordType,uint,uint,uchar const *,void *)
0x1800a4e3d  lea     r8, [rbp+0E0h+var_120]
0x1800a4e41  mov     rdx, [rdi]
0x1800a4e44  mov     rcx, [rbp+0E0h+var_148]
0x1800a4e48  call    cs:__imp_GdipEnumerateMetafileDestPoint
0x1800a4e4e  cmp     [rsp+1E0h+var_170], r15b
0x1800a4e53  jnz     short loc_1800A4E7C
0x1800a4e55  test    rbx, rbx
0x1800a4e58  jz      short loc_1800A4E64
0x1800a4e5a  mov     rcx, rbx; hdc
0x1800a4e5d  call    cs:__imp_DeleteDC
0x1800a4e63  nop
0x1800a4e64  mov     rcx, [rbp+0E0h+var_148]
0x1800a4e68  test    rcx, rcx
0x1800a4e6b  jz      loc_1800A54E7
0x1800a4e71  call    cs:__imp_GdipDeleteGraphics
0x1800a4e77  jmp     loc_1800A54E7
0x1800a4e7c  test    rbx, rbx
0x1800a4e7f  jz      short loc_1800A4E8B
0x1800a4e81  mov     rcx, rbx; hdc
0x1800a4e84  call    cs:__imp_DeleteDC
0x1800a4e8a  nop
0x1800a4e8b  mov     rcx, [rbp+0E0h+var_148]
0x1800a4e8f  test    rcx, rcx
0x1800a4e92  jz      short loc_1800A4E9A
0x1800a4e94  call    cs:__imp_GdipDeleteGraphics
0x1800a4e9a  mov     rbx, r15
0x1800a4e9d  mov     [rbp+0E0h+var_160+4], 1
0x1800a4ea5  mov     dword ptr [rbp+0E0h+var_160+0Ch], r15d
0x1800a4ea9  cmp     [rsi+248h], r15b
0x1800a4eb0  jnz     loc_1800A4FE6
0x1800a4eb6  mov     rcx, [rsi+220h]; hdc
0x1800a4ebd  call    cs:__imp_CloseEnhMetaFile
0x1800a4ec3  mov     rbx, rax
0x1800a4ec6  test    rax, rax
0x1800a4ec9  jnz     short loc_1800A4EE5
0x1800a4ecb  mov     rcx, rdi
0x1800a4ece  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800a4ed3  mov     [rsi+220h], r15
0x1800a4eda  mov     ecx, 2CA6D2h; unsigned int
0x1800a4edf  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x1800a4ee4  int     3; Trap to Debugger
0x1800a4ee5  mov     r14d, 6Ch ; 'l'
0x1800a4eeb  mov     r8d, r14d; Size
0x1800a4eee  xor     edx, edx; Val
0x1800a4ef0  lea     rcx, [rbp+0E0h+EnhMetaHeader]; void *
0x1800a4ef4  call    memset_0
0x1800a4ef9  lea     r8, [rbp+0E0h+EnhMetaHeader]; lpEnhMetaHeader
0x1800a4efd  mov     edx, r14d; nSize
0x1800a4f00  mov     rcx, rbx; hemf
0x1800a4f03  call    cs:__imp_GetEnhMetaFileHeader
0x1800a4f09  test    eax, eax
0x1800a4f0b  jnz     short loc_1800A4F30
0x1800a4f0d  mov     rcx, rbx; hmf
0x1800a4f10  call    cs:__imp_DeleteEnhMetaFile
0x1800a4f16  mov     rcx, rdi
0x1800a4f19  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800a4f1e  mov     [rsi+220h], r15
0x1800a4f25  mov     ecx, 2CA6D3h; unsigned int
0x1800a4f2a  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x1800a4f2f  int     3; Trap to Debugger
0x1800a4f30  mov     eax, [rbp+0E0h+EnhMetaHeader.rclBounds.left]
0x1800a4f33  mov     dword ptr [rbp+0E0h+var_160], eax
0x1800a4f36  mov     eax, [rbp+0E0h+EnhMetaHeader.rclBounds.right]
0x1800a4f39  inc     eax
0x1800a4f3b  mov     dword ptr [rbp+0E0h+var_160+4], eax
0x1800a4f3e  mov     eax, [rbp+0E0h+EnhMetaHeader.rclBounds.top]
0x1800a4f41  mov     dword ptr [rbp+0E0h+var_160+8], eax
0x1800a4f44  mov     eax, [rbp+0E0h+EnhMetaHeader.rclBounds.bottom]
0x1800a4f47  inc     eax
0x1800a4f49  mov     dword ptr [rbp+0E0h+var_160+0Ch], eax
0x1800a4f4c  movups  xmm0, xmmword ptr [rsi+144h]
0x1800a4f53  movdqu  [rbp+0E0h+var_110], xmm0
0x1800a4f58  lea     rdx, [rbp+0E0h+var_160]
0x1800a4f5c  lea     rcx, [rbp+0E0h+var_110]
0x1800a4f60  call    ??$IntersectWith@V?$TUnits@HUDevicePixels@Math@@@Math@@$0A@@?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@QEAAXAEBU01@@Z; Math::TRect<Math::TUnits<int,Math::DevicePixels>>::IntersectWith<Math::TUnits<int,Math::DevicePixels>,0>(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &)
0x1800a4f65  movaps  xmm6, [rbp+0E0h+var_110]
0x1800a4f69  movq    rax, xmm6
0x1800a4f6e  movdqa  xmm0, xmm6
0x1800a4f72  psrldq  xmm0, 8
0x1800a4f77  movq    rcx, xmm0
0x1800a4f7c  cmp     eax, ecx
0x1800a4f7e  jge     short loc_1800A4FC0
0x1800a4f80  shr     rax, 20h
0x1800a4f84  shr     rcx, 20h
0x1800a4f88  cmp     eax, ecx
0x1800a4f8a  jge     short loc_1800A4FC0
0x1800a4f8c  movdqa  xmm0, xmm6
0x1800a4f90  psrldq  xmm0, 0Ch
0x1800a4f95  movd    r13d, xmm0
0x1800a4f9a  movdqa  xmm1, xmm6
0x1800a4f9e  psrldq  xmm1, 8
0x1800a4fa3  movd    r12d, xmm1
0x1800a4fa8  movdqa  xmm0, xmm6
0x1800a4fac  psrldq  xmm0, 4
0x1800a4fb1  movd    r14d, xmm0
0x1800a4fb6  movd    r15d, xmm6
0x1800a4fbb  jmp     loc_1800A5041
0x1800a4fc0  cmp     [rsi+248h], r15b
0x1800a4fc7  jnz     short loc_1800A4FD2
0x1800a4fc9  mov     rcx, rbx; hmf
0x1800a4fcc  call    cs:__imp_DeleteEnhMetaFile
0x1800a4fd2  mov     rcx, rdi
0x1800a4fd5  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800a4fda  mov     [rsi+220h], r15
0x1800a4fe1  jmp     loc_1800A54E7
0x1800a4fe6  xor     edx, edx; Val
0x1800a4fe8  mov     r8d, 8Ch; Size
0x1800a4fee  lea     rcx, [rbp+0E0h+EnhMetaHeader]; void *
0x1800a4ff2  call    memset_0
0x1800a4ff7  lea     rdx, [rbp+0E0h+EnhMetaHeader]
0x1800a4ffb  mov     rcx, [rdi]
0x1800a4ffe  call    cs:__imp_GdipGetMetafileHeaderFromMetafile
0x1800a5004  mov     r9d, 25118D2h
0x1800a500a  mov     ecx, eax
0x1800a500c  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a5011  mov     r15d, [rbp+0E0h+EnhMetaHeader.rclFrame.left]
0x1800a5015  mov     dword ptr [rbp+0E0h+var_160], r15d
0x1800a5019  mov     r14d, [rbp+0E0h+EnhMetaHeader.rclFrame.top]
0x1800a501d  mov     dword ptr [rbp+0E0h+var_160+4], r14d
0x1800a5021  mov     r12d, [rbp+0E0h+EnhMetaHeader.rclFrame.right]
0x1800a5025  inc     r12d
0x1800a5028  add     r12d, r15d
0x1800a502b  mov     dword ptr [rbp+0E0h+var_160+8], r12d
0x1800a502f  mov     r13d, [rbp+0E0h+EnhMetaHeader.rclFrame.bottom]
0x1800a5033  inc     r13d
0x1800a5036  add     r13d, r14d
0x1800a5039  mov     dword ptr [rbp+0E0h+var_160+0Ch], r13d
0x1800a503d  movaps  xmm6, xmmword ptr [rbp+0E0h+var_160]
0x1800a5041  mov     rax, rsi
0x1800a5044  add     rax, 144h
0x1800a504a  mov     [rbp+0E0h+var_148], rax
0x1800a504e  mov     ecx, 600h
0x1800a5053  call    CodeMarker
0x1800a5058  nop
0x1800a5059  mov     [rbp+0E0h+var_130], 0
0x1800a5061  cmp     byte ptr [rsi+248h], 0
0x1800a5068  jnz     short loc_1800A5089
0x1800a506a  lea     r8, [rbp+0E0h+var_130]
0x1800a506e  mov     edx, 1
0x1800a5073  mov     rcx, rbx
0x1800a5076  call    cs:__imp_GdipCreateMetafileFromEmf
0x1800a507c  mov     r9d, 25118D3h
0x1800a5082  mov     ecx, eax
0x1800a5084  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a5089  lea     rcx, [rsi+138h]
0x1800a5090  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800a5095  mov     rcx, rax; this
0x1800a5098  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800a509d  mov     rbx, rax
0x1800a50a0  mov     [rbp+0E0h+var_160], 0
0x1800a50a8  mov     [rbp+0E0h+var_160+8], rax
0x1800a50ac  mov     rdx, rax; struct Gdiplus::GpGraphics *
0x1800a50af  lea     rcx, [rbp+0E0h+var_F0]; this
0x1800a50b3  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800a50b8  nop
0x1800a50b9  cmp     [rbp+0E0h+var_160], 0
0x1800a50be  jz      short loc_1800A50CE
0x1800a50c0  xor     edx, edx
0x1800a50c2  mov     ecx, 1E55E058h
0x1800a50c7  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800a50cd  nop
0x1800a50ce  lea     rcx, [rbp+0E0h+var_160]
0x1800a50d2  call    cs:__imp_GdipCreateRegion
0x1800a50d8  mov     r9d, 25454D8h
0x1800a50de  mov     ecx, eax
0x1800a50e0  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a50e5  mov     rdx, [rbp+0E0h+var_160]
0x1800a50e9  mov     rcx, rbx
0x1800a50ec  call    cs:__imp_GdipGetClip
0x1800a50f2  mov     r9d, 25454D9h
0x1800a50f8  mov     ecx, eax
0x1800a50fa  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a50ff  nop
0x1800a5100  lea     rcx, [rbp+0E0h+var_F0]; this
0x1800a5104  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x1800a5109  mov     rdx, rbx; struct Gdiplus::GpGraphics *
0x1800a510c  lea     rcx, [rbp+0E0h+var_110]; this
0x1800a5110  call    ??0GDIPixelModeRestorer@GEL@@QEAA@AEAVGpGraphics@Gdiplus@@@Z; GEL::GDIPixelModeRestorer::GDIPixelModeRestorer(Gdiplus::GpGraphics &)
0x1800a5115  mov     rdx, [rbp+0E0h+var_148]
0x1800a5119  mov     rcx, rbx
0x1800a511c  call    ?SetClipToBounds@Printer@GEL@@KAXPEAVGpGraphics@Gdiplus@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@@Z; GEL::Printer::SetClipToBounds(Gdiplus::GpGraphics *,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &)
0x1800a5121  mov     rcx, rsi; this
0x1800a5124  call    ?SendBitmapToPrinter@BitmapBasedPrinter@GEL@@IEAAXXZ; GEL::BitmapBasedPrinter::SendBitmapToPrinter(void)
0x1800a5129  cmp     r15d, r12d
0x1800a512c  jg      short loc_1800A513B
0x1800a512e  cmp     r14d, r13d
0x1800a5131  jg      short loc_1800A513B
0x1800a5133  mov     r8d, r13d
0x1800a5136  sub     r8d, r14d
0x1800a5139  jmp     short loc_1800A513E
0x1800a513b  xor     r8d, r8d
0x1800a513e  cmp     r15d, r12d
0x1800a5141  jg      short loc_1800A5150
0x1800a5143  cmp     r14d, r13d
0x1800a5146  jg      short loc_1800A5150
0x1800a5148  mov     edx, r12d
0x1800a514b  sub     edx, r15d
0x1800a514e  jmp     short loc_1800A5152
0x1800a5150  xor     edx, edx
0x1800a5152  cmp     r15d, r12d
0x1800a5155  jg      short loc_1800A5164
0x1800a5157  cmp     r14d, r13d
0x1800a515a  jg      short loc_1800A5164
0x1800a515c  mov     ecx, r13d
0x1800a515f  sub     ecx, r14d
0x1800a5162  jmp     short loc_1800A5166
0x1800a5164  xor     ecx, ecx
0x1800a5166  cmp     r15d, r12d
0x1800a5169  jg      short loc_1800A5178
0x1800a516b  cmp     r14d, r13d
0x1800a516e  jg      short loc_1800A5178
0x1800a5170  mov     eax, r12d
0x1800a5173  sub     eax, r15d
0x1800a5176  jmp     short loc_1800A517A
0x1800a5178  xor     eax, eax
0x1800a517a  cmp     byte ptr [rsi+248h], 0
0x1800a5181  jz      short loc_1800A5188
0x1800a5183  mov     r10, [rdi]
0x1800a5186  jmp     short loc_1800A518C
0x1800a5188  mov     r10, [rbp+0E0h+var_130]
0x1800a518c  xor     edi, edi
0x1800a518e  mov     qword ptr [rsp+1E0h+var_178], rdi
0x1800a5193  mov     [rsp+1E0h+var_180], rdi
0x1800a5198  mov     [rsp+1E0h+var_188], rdi
0x1800a519d  mov     dword ptr [rsp+1E0h+var_190], 2
0x1800a51a5  mov     [rsp+1E0h+var_198], r8d
0x1800a51aa  mov     [rsp+1E0h+var_1A0], edx
0x1800a51ae  mov     [rsp+1E0h+var_1A8], r14d
0x1800a51b3  mov     [rsp+1E0h+var_1B0], r15d
0x1800a51b8  mov     [rsp+1E0h+var_1B8], ecx
0x1800a51bc  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x1800a51c0  mov     r9d, r14d
0x1800a51c3  mov     r8d, r15d
0x1800a51c6  mov     rdx, r10
0x1800a51c9  mov     rcx, rbx
0x1800a51cc  call    cs:__imp_GdipDrawImageRectRectI
0x1800a51d2  mov     r9d, 25118D4h
0x1800a51d8  mov     ecx, eax
0x1800a51da  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a51df  nop
0x1800a51e0  lea     rcx, [rbp+0E0h+var_110]; this
0x1800a51e4  call    ??1GDIPixelModeRestorer@GEL@@QEAA@XZ; GEL::GDIPixelModeRestorer::~GDIPixelModeRestorer(void)
0x1800a51e9  mov     rdx, [rbp+0E0h+var_160+8]; struct Gdiplus::GpGraphics *
0x1800a51ed  lea     rcx, [rbp+0E0h+var_160]; this
0x1800a51f1  call    ?Unapply@GDIClip@GEL@@QEAAXAEAVGpGraphics@Gdiplus@@@Z; GEL::GDIClip::Unapply(Gdiplus::GpGraphics &)
0x1800a51f6  mov     rcx, [rbp+0E0h+var_160]
0x1800a51fa  test    rcx, rcx
0x1800a51fd  jz      short loc_1800A5205
0x1800a51ff  call    cs:__imp_GdipDeleteRegion
  ... truncated ...
```
