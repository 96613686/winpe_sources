# GEL::GDITech::DrawImage(GEL::RenderStage const &,Gdiplus::GpGraphics &,GEL::IImage const &,std::optional<float> const &,Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TRect<double> const &,GEL::WrapMode)

- ea: `0x18006bfa8`
- end: `0x18006c465`
- name: `?DrawImage@GDITech@GEL@@CAXAEBVRenderStage@2@AEAVGpGraphics@Gdiplus@@AEBUIImage@2@AEBV?$optional@M@std@@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@AEBU?$TRect@N@Math@@W4WrapMode@2@@Z`
- size: `1213`
- prototype: `__int64 __usercall@<rax>(GEL::RenderStage *this@<rcx>, Gfx::Rect *, __int64, char)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18006c470`

## callees

- `0x180014730`
- `0x180025200`
- `0x180025360`
- `0x18004e674`
- `0x180054d70`
- `0x180057e70`
- `0x18006bfa8`
- `0x18007f754`
- `0x180092a58`
- `0x1800ba2ec`
- `0x1800bc38c`
- `0x1800ecc44`
- `0x180149b50`

## import_xrefs

- `gdiplus!GdipAddPathRectangle` at `0x18006c0c8`
- `gdiplus!GdipAddPathRectangle` at `0x18006c0c8`
- `gdiplus!GdipStartPathFigure` at `0x18006c034`
- `gdiplus!GdipStartPathFigure` at `0x18006c034`
- `gdiplus!GdipClosePathFigure` at `0x18006c0e3`
- `gdiplus!GdipClosePathFigure` at `0x18006c0e3`
- `gdiplus!GdipDeletePath` at `0x18006c2d2`
- `gdiplus!GdipDeletePath` at `0x18006c2d2`
- `gdiplus!GdipCreatePath` at `0x18006c019`
- `gdiplus!GdipCreatePath` at `0x18006c019`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x18006c31a`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x18006c31a`
- `gdiplus!GdipCreateImageAttributes` at `0x18006c2f1`
- `gdiplus!GdipCreateImageAttributes` at `0x18006c2f1`
- `gdiplus!GdipDisposeImageAttributes` at `0x18006c431`
- `gdiplus!GdipDisposeImageAttributes` at `0x18006c431`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void GEL::GDITech::DrawImage(GEL::RenderStage *this, struct Gdiplus::GpGraphics *a2, const struct Image *a3, ...)
{
  Gfx::Rect *v6; // rdi
  unsigned int Path; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int started; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  float *v13; // rax
  _OWORD *v14; // r14
  double *v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __m128d v23; // xmm6
  __m128d v24; // xmm7
  int *v25; // rax
  unsigned __int64 v26; // rdx
  unsigned int v27; // r8d
  __m128d v28; // xmm6
  __m128d v29; // xmm4
  __m128d v30; // xmm7
  __m128d v31; // xmm3
  _OWORD *v32; // rax
  unsigned __int64 v33; // rdx
  unsigned int v34; // r8d
  __m128d *v35; // rax
  unsigned __int64 v36; // rdx
  unsigned int v37; // r8d
  __m128d *v38; // rcx
  __m128d *v39; // rax
  GEL::GDIImageBrushResource *v40; // rax
  GEL::GDIImageBrushResource *v41; // rdi
  struct Frame *CurrentFrame; // rax
  unsigned int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  double v46; // xmm8_8
  double v47; // xmm9_8
  __int64 v48; // rdx
  __int64 v49; // r8
  int v50; // xmm6_4
  int v51; // xmm7_4
  __int64 v52; // rdx
  __int64 v53; // rcx
  double *v54; // rcx
  int v55; // xmm3_4
  int v56; // xmm5_4
  int v57; // xmm4_4
  int v58; // xmm2_4
  unsigned int v59; // edi
  __int64 v60; // rdx
  __int64 v61; // r8
  int v62; // eax
  int v63; // [rsp+58h] [rbp-D0h]
  int v64; // [rsp+60h] [rbp-C8h]
  GEL::GDIImageBrushResource *v65; // [rsp+70h] [rbp-B8h] BYREF
  const OException *v66; // [rsp+80h] [rbp-A8h] BYREF
  __int128 v67; // [rsp+90h] [rbp-98h] BYREF
  _OWORD *v68; // [rsp+A0h] [rbp-88h]
  char v69; // [rsp+A8h] [rbp-80h]
  __int128 v70; // [rsp+B0h] [rbp-78h]
  int *v71; // [rsp+C0h] [rbp-68h]
  int v72; // [rsp+C8h] [rbp-60h]
  __int64 v73; // [rsp+140h] [rbp+18h] BYREF
  __int64 v74; // [rsp+148h] [rbp+20h] BYREF
  va_list va; // [rsp+148h] [rbp+20h]
  Gfx::Rect *v76; // [rsp+150h] [rbp+28h]
  _OWORD *v77; // [rsp+158h] [rbp+30h]
  __int64 v78; // [rsp+160h] [rbp+38h]
  va_list va1; // [rsp+168h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v74 = va_arg(va1, _QWORD);
  v76 = va_arg(va1, Gfx::Rect *);
  v77 = va_arg(va1, _OWORD *);
  v78 = va_arg(va1, _QWORD);
  v6 = v76;
  if ( (*(unsigned int (__fastcall **)(const struct Image *))(*(_QWORD *)a3 + 176LL))(a3) == 15 )
  {
    v74 = 0;
    Path = GdipCreatePath(0, (__int64 *)va);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(Path, v8, v9, 38322451);
    started = GdipStartPathFigure(v74);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(started, v11, v12, 38322452);
    v13 = (float *)&v65;
    v14 = v77;
    v15 = (double *)v77;
    v16 = 4;
    do
    {
      *v13++ = *v15++;
      --v16;
    }
    while ( v16 );
    v17 = GdipAddPathRectangle(v74);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v17, v18, v19, 38322453);
    v20 = GdipClosePathFigure(v74);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v20, v21, v22, 38322454);
    v23 = 0;
    v24 = 0;
    v25 = (int *)(*(__int64 (__fastcall **)(const struct Image *, GEL::GDIImageBrushResource **))(*(_QWORD *)a3 + 56LL))(
                   a3,
                   &v65);
    if ( *v25 )
    {
      v26 = HIDWORD(*(_QWORD *)v25);
      if ( (_DWORD)v26 )
      {
        v28 = (__m128d)*(unsigned __int64 *)v6;
        v28.m128d_f64[0] = v28.m128d_f64[0] / (double)*v25;
        v29 = (__m128d)*(unsigned __int64 *)&DOUBLE_1_0;
        v30 = (__m128d)*(unsigned __int64 *)&DOUBLE_1_0;
        v30.m128d_f64[0] = 1.0 - *((double *)v6 + 2) / (double)*v25;
        v31 = (__m128d)*((unsigned __int64 *)v6 + 1);
        v31.m128d_f64[0] = v31.m128d_f64[0] / (double)(int)v26;
        v29.m128d_f64[0] = 1.0 - *((double *)v6 + 3) / (double)(int)v26;
        v24 = _mm_unpacklo_pd(v30, v29);
        v23 = _mm_unpacklo_pd(v28, v31);
      }
    }
    v67 = 0;
    v68 = 0;
    v69 = 0;
    v70 = 0;
    v71 = &dword_18048AEDC;
    v72 = 0x1000000;
    v32 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x20, v26, v27);
    if ( v32 )
    {
      *v32 = *v14;
      v32[1] = v14[1];
      v68 = v32;
    }
    else
    {
      v68 = 0;
    }
    v69 = v78;
    v35 = (__m128d *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x20, v33, v34);
    v38 = v35;
    if ( v35 )
    {
      *v35 = v23;
      v35[1] = v24;
    }
    else
    {
      v38 = 0;
    }
    v39 = (__m128d *)v67;
    if ( v38 )
      v39 = v38;
    *(_QWORD *)&v67 = v39;
    v40 = (GEL::GDIImageBrushResource *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x68, v36, v37);
    v65 = v40;
    if ( v40 )
      v41 = (GEL::GDIImageBrushResource *)GEL::GDIImageBrushResource::GDIImageBrushResource(
                                            v40,
                                            (const struct GEL::ImageFillInfo *)&v67,
                                            a3);
    else
      v41 = 0;
    v65 = v41;
    CurrentFrame = GEL::RenderStage::GetCurrentFrame(this);
    GEL::GDITech::FillPathWithImage(
      this,
      a2,
      0,
      v74,
      (__int64)v14,
      1,
      (__int64)v41,
      (__int64)&CurrentFrame->lpVtbl->Minimize,
      0);
    if ( v41 )
      GEL::GDIImageBrushResource::`vector deleting destructor'(v41, 1u);
    GEL::ImageFillInfo::~ImageFillInfo((GEL::ImageFillInfo *)&v67);
    if ( v74 )
      GdipDeletePath();
  }
  else
  {
    v73 = 0;
    v43 = GdipCreateImageAttributes(&v73);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v43, v44, v45, 38322455);
    GdipSetImageAttributesWrapMode(v73, (unsigned __int8)v78, 0, 0);
    v46 = 0.0;
    if ( Gfx::Rect::FIsEmpty(v6) )
      v47 = 0.0;
    else
      v47 = *((double *)v6 + 3) - *((double *)v6 + 1);
    if ( !Gfx::Rect::FIsEmpty(v6) )
      v46 = *((double *)v6 + 2) - *(double *)v6;
    *(float *)&v50 = *(double *)(v49 + v48);
    *(float *)&v51 = *(double *)v6;
    Math::TRect<double>::GetHeight(v77, v48);
    *(float *)&v55 = Math::TRect<double>::GetWidth(v53, v52);
    try
    {
      *(float *)&v63 = v46;
      *(float *)&v64 = v47;
      *(float *)&v58 = *v54;
      *(float *)&v57 = v54[1];
      v59 = GEL::GDITech::DrawImageRectRect(this, 0, v58, v57, v55, v56, v51, v50, v63, v64);
      if ( (*(unsigned __int8 (__fastcall **)(const struct Image *))(*(_QWORD *)a3 + 88LL))(a3) || v59 != 1 )
        Gfx::GdipStatus_ThrowOnFailureMessageTag(v59, v60, v61, 38322456);
    }
    catch ( const OException *v66 )
    {
      v62 = *((_DWORD *)v66 + 129);
      if ( v62 != -2147024882 && (unsigned int)(v62 + 2003292412) > 0x92 )
        throw;
    }
    if ( v73 )
      GdipDisposeImageAttributes();
  }
}

```

## disassembly

```asm
0x18006bfa8  mov     rax, rsp
0x18006bfab  mov     [rax+8], rsi
0x18006bfaf  mov     [rax+10h], rdi
0x18006bfb3  mov     [rax+20h], r9
0x18006bfb7  push    r12
0x18006bfb9  push    r14
0x18006bfbb  push    r15
0x18006bfbd  sub     rsp, 110h
0x18006bfc4  movaps  xmmword ptr [rax-28h], xmm6
0x18006bfc8  movaps  xmmword ptr [rax-38h], xmm7
0x18006bfcc  movaps  xmmword ptr [rax-48h], xmm8
0x18006bfd1  movaps  xmmword ptr [rax-58h], xmm9
0x18006bfd6  mov     rsi, r8
0x18006bfd9  mov     r12, rdx
0x18006bfdc  mov     r15, rcx
0x18006bfdf  mov     rdi, [rsp+128h+arg_20]
0x18006bfe7  mov     rax, [r8]
0x18006bfea  mov     rcx, r8
0x18006bfed  mov     rax, [rax+0B0h]
0x18006bff4  call    cs:__guard_dispatch_icall_fptr
0x18006bffa  cmp     eax, 0Fh
0x18006bffd  jnz     loc_18006C2DD
0x18006c003  mov     [rsp+128h+arg_18], 0
0x18006c00f  lea     rdx, [rsp+128h+arg_18]
0x18006c017  xor     ecx, ecx
0x18006c019  call    cs:__imp_GdipCreatePath
0x18006c01f  mov     r9d, 248C113h
0x18006c025  mov     ecx, eax
0x18006c027  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006c02c  mov     rcx, [rsp+128h+arg_18]
0x18006c034  call    cs:__imp_GdipStartPathFigure
0x18006c03a  mov     r9d, 248C114h
0x18006c040  mov     ecx, eax
0x18006c042  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006c047  lea     rax, [rsp+128h+var_B8]
0x18006c04c  mov     r14, [rsp+128h+arg_28]
0x18006c054  mov     rcx, r14
0x18006c057  mov     edx, 8
0x18006c05c  lea     r8d, [rdx-4]
0x18006c060  movsd   xmm0, qword ptr [rcx]
0x18006c064  cvtpd2ps xmm0, xmm0
0x18006c068  movss   dword ptr [rax], xmm0
0x18006c06c  add     rcx, rdx
0x18006c06f  lea     rax, [rax+4]
0x18006c073  sub     r8, 1
0x18006c077  jnz     short loc_18006C060
0x18006c079  movss   xmm1, dword ptr [rsp+128h+var_B8]
0x18006c07f  movss   xmm3, [rsp+128h+var_B0]
0x18006c085  movss   xmm2, dword ptr [rsp+128h+var_B8+4]
0x18006c08b  movss   xmm0, [rsp+128h+var_AC]
0x18006c091  comiss  xmm1, xmm3
0x18006c094  ja      short loc_18006C0A4
0x18006c096  comiss  xmm2, xmm0
0x18006c099  ja      short loc_18006C0A4
0x18006c09b  movaps  xmm5, xmm0
0x18006c09e  subss   xmm5, xmm2
0x18006c0a2  jmp     short loc_18006C0A7
0x18006c0a4  xorps   xmm5, xmm5
0x18006c0a7  comiss  xmm1, xmm3
0x18006c0aa  ja      short loc_18006C0B7
0x18006c0ac  comiss  xmm2, xmm0
0x18006c0af  ja      short loc_18006C0B7
0x18006c0b1  subss   xmm3, xmm1
0x18006c0b5  jmp     short loc_18006C0BA
0x18006c0b7  xorps   xmm3, xmm3
0x18006c0ba  movss   dword ptr [rsp+128h+var_108], xmm5
0x18006c0c0  mov     rcx, [rsp+128h+arg_18]
0x18006c0c8  call    cs:__imp_GdipAddPathRectangle
0x18006c0ce  mov     r9d, 248C115h
0x18006c0d4  mov     ecx, eax
0x18006c0d6  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006c0db  mov     rcx, [rsp+128h+arg_18]
0x18006c0e3  call    cs:__imp_GdipClosePathFigure
0x18006c0e9  mov     r9d, 248C116h
0x18006c0ef  mov     ecx, eax
0x18006c0f1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006c0f6  xorps   xmm6, xmm6
0x18006c0f9  xorps   xmm7, xmm7
0x18006c0fc  mov     rax, [rsi]
0x18006c0ff  lea     rdx, [rsp+128h+var_B8]
0x18006c104  mov     rcx, rsi
0x18006c107  mov     rax, [rax+38h]
0x18006c10b  call    cs:__guard_dispatch_icall_fptr
0x18006c111  cmp     dword ptr [rax], 0
0x18006c114  jbe     short loc_18006C171
0x18006c116  mov     rdx, [rax]
0x18006c119  shr     rdx, 20h; unsigned __int64
0x18006c11d  test    edx, edx
0x18006c11f  jz      short loc_18006C171
0x18006c121  movsd   xmm6, qword ptr [rdi]
0x18006c125  mov     ecx, [rax]
0x18006c127  xorps   xmm1, xmm1
0x18006c12a  cvtsi2sd xmm1, rcx
0x18006c12f  divsd   xmm6, xmm1
0x18006c133  movsd   xmm0, qword ptr [rdi+10h]
0x18006c138  divsd   xmm0, xmm1
0x18006c13c  movsd   xmm4, cs:__real@3ff0000000000000
0x18006c144  movaps  xmm7, xmm4
0x18006c147  subsd   xmm7, xmm0
0x18006c14b  movsd   xmm3, qword ptr [rdi+8]
0x18006c150  xorps   xmm1, xmm1
0x18006c153  cvtsi2sd xmm1, rdx
0x18006c158  divsd   xmm3, xmm1
0x18006c15c  movsd   xmm0, qword ptr [rdi+18h]
0x18006c161  divsd   xmm0, xmm1
0x18006c165  subsd   xmm4, xmm0
0x18006c169  unpcklpd xmm7, xmm4
0x18006c16d  unpcklpd xmm6, xmm3
0x18006c171  xorps   xmm0, xmm0
0x18006c174  movdqa  [rsp+128h+var_98], xmm0
0x18006c17d  mov     [rsp+128h+var_88], 0
0x18006c189  mov     [rsp+128h+var_80], 0
0x18006c191  movdqa  [rsp+128h+var_78], xmm0
0x18006c19a  lea     rax, dword_18048AEDC
0x18006c1a1  mov     [rsp+128h+var_68], rax
0x18006c1a9  mov     [rsp+128h+var_60], 1000000h
0x18006c1b4  mov     edi, 20h ; ' '
0x18006c1b9  mov     ecx, edi; this
0x18006c1bb  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18006c1c0  test    rax, rax
0x18006c1c3  jz      short loc_18006C1DF
0x18006c1c5  movups  xmm0, xmmword ptr [r14]
0x18006c1c9  movups  xmmword ptr [rax], xmm0
0x18006c1cc  movups  xmm1, xmmword ptr [r14+10h]
0x18006c1d1  movups  xmmword ptr [rax+10h], xmm1
0x18006c1d5  mov     [rsp+128h+var_88], rax
0x18006c1dd  jmp     short loc_18006C1EB
0x18006c1df  mov     [rsp+128h+var_88], 0
0x18006c1eb  mov     al, byte ptr [rsp+128h+arg_30]
0x18006c1f2  mov     [rsp+128h+var_80], al
0x18006c1f9  mov     rcx, rdi; this
0x18006c1fc  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18006c201  mov     rcx, rax
0x18006c204  test    rax, rax
0x18006c207  jz      short loc_18006C212
0x18006c209  movups  xmmword ptr [rax], xmm6
0x18006c20c  movups  xmmword ptr [rax+10h], xmm7
0x18006c210  jmp     short loc_18006C214
0x18006c212  xor     ecx, ecx
0x18006c214  mov     rax, qword ptr [rsp+128h+var_98]
0x18006c21c  test    rcx, rcx
0x18006c21f  cmovnz  rax, rcx
0x18006c223  mov     qword ptr [rsp+128h+var_98], rax
0x18006c22b  mov     ecx, 68h ; 'h'; this
0x18006c230  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18006c235  mov     [rsp+128h+var_B8], rax
0x18006c23a  test    rax, rax
0x18006c23d  jz      short loc_18006C257
0x18006c23f  mov     r8, rsi; struct Image *
0x18006c242  lea     rdx, [rsp+128h+var_98]; struct GEL::ImageFillInfo *
0x18006c24a  mov     rcx, rax; this
0x18006c24d  call    ??0GDIImageBrushResource@GEL@@QEAA@AEBUImageFillInfo@1@AEBVImage@1@@Z; GEL::GDIImageBrushResource::GDIImageBrushResource(GEL::ImageFillInfo const &,GEL::Image const &)
0x18006c252  mov     rdi, rax
0x18006c255  jmp     short loc_18006C259
0x18006c257  xor     edi, edi
0x18006c259  mov     [rsp+128h+var_B8], rdi
0x18006c25e  mov     rcx, r15; this
0x18006c261  call    ?GetCurrentFrame@RenderStage@GEL@@QEAAAEAVFrame@12@XZ; GEL::RenderStage::GetCurrentFrame(void)
0x18006c266  mov     rcx, [rax]
0x18006c269  add     rcx, 40h ; '@'
0x18006c26d  mov     qword ptr [rsp+128h+var_E8], 0
0x18006c276  mov     qword ptr [rsp+128h+var_F0], rcx
0x18006c27b  mov     qword ptr [rsp+128h+var_F8], rdi
0x18006c280  mov     byte ptr [rsp+128h+var_100], 1
0x18006c285  mov     qword ptr [rsp+128h+var_108], r14
0x18006c28a  mov     r9, [rsp+128h+arg_18]
0x18006c292  xor     r8d, r8d
0x18006c295  mov     rdx, r12
0x18006c298  mov     rcx, r15
0x18006c29b  call    ?FillPathWithImage@GDITech@GEL@@CAXAEBVRenderStage@2@AEAVGpGraphics@Gdiplus@@PEAUIPostScriptSink@Gfx@@PEBVGpPath@5@AEBU?$TRect@N@Math@@_NAEBVGDIImageBrushResource@2@AEBU?$TAffine3x3@N@Math@@PEBU?$TAffine3x3@N@Math@@@Z; GEL::GDITech::FillPathWithImage(GEL::RenderStage const &,Gdiplus::GpGraphics &,Gfx::IPostScriptSink *,Gdiplus::GpPath const *,Math::TRect<double> const &,bool,GEL::GDIImageBrushResource const &,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *)
0x18006c2a0  nop
0x18006c2a1  test    rdi, rdi
0x18006c2a4  jz      short loc_18006C2B4
0x18006c2a6  mov     edx, 1; unsigned int
0x18006c2ab  mov     rcx, rdi; this
0x18006c2ae  call    ??_EGDIImageBrushResource@GEL@@UEAAPEAXI@Z; GEL::GDIImageBrushResource::`vector deleting destructor'(uint)
0x18006c2b3  nop
0x18006c2b4  lea     rcx, [rsp+128h+var_98]; this
0x18006c2bc  call    ??1ImageFillInfo@GEL@@QEAA@XZ; GEL::ImageFillInfo::~ImageFillInfo(void)
0x18006c2c1  mov     rcx, [rsp+128h+arg_18]
0x18006c2c9  test    rcx, rcx
0x18006c2cc  jz      loc_18006C437
0x18006c2d2  call    cs:__imp_GdipDeletePath
0x18006c2d8  jmp     loc_18006C437
0x18006c2dd  mov     [rsp+128h+arg_10], 0
0x18006c2e9  lea     rcx, [rsp+128h+arg_10]
0x18006c2f1  call    cs:__imp_GdipCreateImageAttributes
0x18006c2f7  mov     r9d, 248C117h
0x18006c2fd  mov     ecx, eax
0x18006c2ff  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006c304  movzx   edx, byte ptr [rsp+128h+arg_30]
0x18006c30c  xor     r9d, r9d
0x18006c30f  xor     r8d, r8d
0x18006c312  mov     rcx, [rsp+128h+arg_10]
0x18006c31a  call    cs:__imp_GdipSetImageAttributesWrapMode
0x18006c320  mov     rcx, rdi; this
0x18006c323  call    ?FIsEmpty@Rect@Gfx@@QEBA_NXZ; Gfx::Rect::FIsEmpty(void)
0x18006c328  mov     r8, rdi
0x18006c32b  mov     edx, 8
0x18006c330  xorps   xmm8, xmm8
0x18006c334  test    al, al
0x18006c336  jnz     short loc_18006C346
0x18006c338  movsd   xmm9, qword ptr [rdi+18h]
0x18006c33e  subsd   xmm9, qword ptr [rdi+8]
0x18006c344  jmp     short loc_18006C34A
0x18006c346  xorps   xmm9, xmm9
0x18006c34a  mov     rcx, rdi; this
0x18006c34d  call    ?FIsEmpty@Rect@Gfx@@QEBA_NXZ; Gfx::Rect::FIsEmpty(void)
0x18006c352  test    al, al
0x18006c354  jnz     short loc_18006C361
0x18006c356  movsd   xmm8, qword ptr [rdi+10h]
0x18006c35c  subsd   xmm8, qword ptr [rdi]
0x18006c361  movsd   xmm6, qword ptr [r8+rdx]
0x18006c367  cvtpd2ps xmm6, xmm6
0x18006c36b  movsd   xmm7, qword ptr [rdi]
0x18006c36f  cvtpd2ps xmm7, xmm7
0x18006c373  mov     rcx, [rsp+128h+arg_28]
0x18006c37b  call    ?GetHeight@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetHeight(void)
0x18006c380  xorps   xmm5, xmm5
0x18006c383  cvtsd2ss xmm5, xmm0
0x18006c387  call    ?GetWidth@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetWidth(void)
0x18006c38c  xorps   xmm3, xmm3
0x18006c38f  cvtsd2ss xmm3, xmm0
0x18006c393  movsd   xmm4, qword ptr [rcx+8]
0x18006c398  cvtpd2ps xmm4, xmm4
0x18006c39c  movsd   xmm2, qword ptr [rcx]
0x18006c3a0  cvtpd2ps xmm2, xmm2
0x18006c3a4  cvtpd2ps xmm0, xmm9
0x18006c3a9  cvtpd2ps xmm1, xmm8
0x18006c3ae  movss   [rsp+128h+var_C8], xmm0; int
0x18006c3b4  movss   [rsp+128h+var_D0], xmm1; int
0x18006c3ba  movss   [rsp+128h+var_D8], xmm6; int
0x18006c3c0  movss   [rsp+128h+var_E0], xmm7; int
0x18006c3c6  movss   [rsp+128h+var_E8], xmm5; int
0x18006c3cc  movss   [rsp+128h+var_F0], xmm3; int
0x18006c3d2  movss   [rsp+128h+var_F8], xmm4; int
0x18006c3d8  movss   [rsp+128h+var_100], xmm2; int
0x18006c3de  mov     [rsp+128h+var_108], 0; char
0x18006c3e3  lea     r9, [rsp+128h+arg_10]
0x18006c3eb  mov     r8, rsi
0x18006c3ee  mov     rdx, r12
0x18006c3f1  mov     rcx, r15; this
0x18006c3f4  call    ?DrawImageRectRect@GDITech@GEL@@CA?AW4Status@Gdiplus@@AEBVRenderStage@2@AEAVGpGraphics@4@AEBVImage@2@AEBV?$TGpHolder@VGpImageAttributes@Gdiplus@@@GDIPlus@ARC@@_NMMMMMMMM@Z; GEL::GDITech::DrawImageRectRect(GEL::RenderStage const &,Gdiplus::GpGraphics &,GEL::Image const &,ARC::GDIPlus::TGpHolder<Gdiplus::GpImageAttributes> const &,bool,float,float,float,float,float,float,float,float)
0x18006c3f9  mov     edi, eax
0x18006c3fb  mov     rcx, [rsi]
0x18006c3fe  mov     rax, [rcx+58h]
0x18006c402  mov     rcx, rsi
0x18006c405  call    cs:__guard_dispatch_icall_fptr
0x18006c40b  test    al, al
0x18006c40d  jnz     short loc_18006C414
0x18006c40f  cmp     edi, 1
0x18006c412  jz      short loc_18006C422
0x18006c414  mov     r9d, 248C118h
0x18006c41a  mov     ecx, edi
0x18006c41c  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006c421  nop
0x18006c422  jmp     short $+2
0x18006c424  mov     rcx, [rsp+128h+arg_10]
0x18006c42c  test    rcx, rcx
0x18006c42f  jz      short loc_18006C437
0x18006c431  call    cs:__imp_GdipDisposeImageAttributes
0x18006c437  lea     r11, [rsp+128h+var_18]
0x18006c43f  mov     rsi, [r11+20h]
0x18006c443  mov     rdi, [r11+28h]
0x18006c447  movaps  xmm6, xmmword ptr [r11-10h]
0x18006c44c  movaps  xmm7, xmmword ptr [r11-20h]
0x18006c451  movaps  xmm8, xmmword ptr [r11-30h]
0x18006c456  movaps  xmm9, xmmword ptr [r11-40h]
0x18006c45b  mov     rsp, r11
0x18006c45e  pop     r15
0x18006c460  pop     r14
0x18006c462  pop     r12
0x18006c464  retn
```
