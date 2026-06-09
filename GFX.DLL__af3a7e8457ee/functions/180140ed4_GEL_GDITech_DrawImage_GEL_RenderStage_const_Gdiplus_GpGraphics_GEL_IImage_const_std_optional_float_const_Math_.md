# GEL::GDITech::DrawImage(GEL::RenderStage const &,Gdiplus::GpGraphics &,GEL::IImage const &,std::optional<float> const &,Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TRect<double> const &,GEL::WrapMode)

- ea: `0x180140ed4`
- end: `0x1801413d5`
- name: `?DrawImage@GDITech@GEL@@CAXAEBVRenderStage@2@AEAVGpGraphics@Gdiplus@@AEBUIImage@2@AEBV?$optional@M@std@@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@AEBU?$TRect@N@Math@@W4WrapMode@2@@Z`
- size: `1281`
- prototype: `__int64 __usercall@<rax>(GEL *this@<rcx>, Gfx::Rect *, __int64, char)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180140df0`

## callees

- `0x180014a30`
- `0x180024f30`
- `0x180024f60`
- `0x18004f244`
- `0x180053330`
- `0x1800573f0`
- `0x180062394`
- `0x180062b84`
- `0x1800786fc`
- `0x1800b2bec`
- `0x180140ed4`
- `0x180141444`
- `0x18014a560`

## import_xrefs

- `gdiplus!GdipAddPathRectangle` at `0x18014117d`
- `gdiplus!GdipAddPathRectangle` at `0x18014117d`
- `gdiplus!GdipStartPathFigure` at `0x1801410e3`
- `gdiplus!GdipStartPathFigure` at `0x1801410e3`
- `gdiplus!GdipClosePathFigure` at `0x180141198`
- `gdiplus!GdipClosePathFigure` at `0x180141198`
- `gdiplus!GdipDeletePath` at `0x18014136f`
- `gdiplus!GdipDeletePath` at `0x18014136f`
- `gdiplus!GdipCreatePath` at `0x1801410c8`
- `gdiplus!GdipCreatePath` at `0x1801410c8`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x180140f6c`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x180140f6c`
- `gdiplus!GdipCreateImageAttributes` at `0x180140f43`
- `gdiplus!GdipCreateImageAttributes` at `0x180140f43`
- `gdiplus!GdipDisposeImageAttributes` at `0x18014107e`
- `gdiplus!GdipDisposeImageAttributes` at `0x18014107e`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void GEL::GDITech::DrawImage(GEL *this, struct Gdiplus::GpGraphics *a2, const struct Image *a3, ...)
{
  Gfx::Rect *v6; // rdi
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  double v10; // xmm8_8
  double v11; // xmm9_8
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // xmm6_4
  int v15; // xmm7_4
  __int64 v16; // rdx
  __int64 v17; // rcx
  double *v18; // rcx
  double Width; // xmm0_8
  int v20; // xmm5_4
  int v21; // xmm3_4
  int v22; // xmm4_4
  int v23; // xmm2_4
  unsigned int v24; // edi
  char v25; // al
  __int64 v26; // rdx
  __int64 v27; // r8
  unsigned int Path; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  unsigned int started; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  float *v34; // rax
  _OWORD *v35; // r14
  double *v36; // rcx
  __int64 v37; // r8
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  unsigned int v41; // eax
  __int64 v42; // rdx
  __int64 v43; // r8
  __m128d v44; // xmm6
  __m128d v45; // xmm7
  int *v46; // rax
  unsigned __int64 v47; // rdx
  unsigned int v48; // r8d
  __m128d v49; // xmm6
  __m128d v50; // xmm4
  __m128d v51; // xmm7
  __m128d v52; // xmm3
  _OWORD *v53; // rax
  unsigned __int64 v54; // rdx
  unsigned int v55; // r8d
  __m128d *v56; // rax
  unsigned __int64 v57; // rdx
  unsigned int v58; // r8d
  __m128d *v59; // rcx
  __m128d *v60; // rax
  GEL::GDIImageBrushResource *v61; // rax
  GEL::GDIImageBrushResource *v62; // rdi
  struct Frame *CurrentFrame; // rax
  int v64; // eax
  int v65; // [rsp+58h] [rbp-D0h]
  int v66; // [rsp+60h] [rbp-C8h]
  GEL::GDIImageBrushResource *v67; // [rsp+70h] [rbp-B8h] BYREF
  const OException *v68; // [rsp+80h] [rbp-A8h] BYREF
  __int128 v69; // [rsp+90h] [rbp-98h] BYREF
  _OWORD *v70; // [rsp+A0h] [rbp-88h]
  char v71; // [rsp+A8h] [rbp-80h]
  __int128 v72; // [rsp+B0h] [rbp-78h]
  int *v73; // [rsp+C0h] [rbp-68h]
  int v74; // [rsp+C8h] [rbp-60h]
  __int64 v75; // [rsp+140h] [rbp+18h] BYREF
  __int64 v76; // [rsp+148h] [rbp+20h] BYREF
  va_list va; // [rsp+148h] [rbp+20h]
  Gfx::Rect *v78; // [rsp+150h] [rbp+28h]
  _OWORD *v79; // [rsp+158h] [rbp+30h]
  __int64 v80; // [rsp+160h] [rbp+38h]
  va_list va1; // [rsp+168h] [rbp+40h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v76 = va_arg(va1, _QWORD);
  v78 = va_arg(va1, Gfx::Rect *);
  v79 = va_arg(va1, _OWORD *);
  v80 = va_arg(va1, _QWORD);
  v6 = v78;
  if ( (*(unsigned int (__fastcall **)(const struct Image *))(*(_QWORD *)a3 + 176LL))(a3) == 15 )
  {
    v76 = 0;
    Path = GdipCreatePath(0, (__int64 *)va);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(Path, v29, v30, 38322451);
    started = GdipStartPathFigure(v76);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(started, v32, v33, 38322452);
    v34 = (float *)&v67;
    v35 = v79;
    v36 = (double *)v79;
    v37 = 4;
    do
    {
      *v34++ = *v36++;
      --v37;
    }
    while ( v37 );
    v38 = GdipAddPathRectangle(v76);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v38, v39, v40, 38322453);
    v41 = GdipClosePathFigure(v76);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v41, v42, v43, 38322454);
    v44 = 0;
    v45 = 0;
    v46 = (int *)(*(__int64 (__fastcall **)(const struct Image *, GEL::GDIImageBrushResource **))(*(_QWORD *)a3 + 56LL))(
                   a3,
                   &v67);
    if ( *v46 )
    {
      v47 = HIDWORD(*(_QWORD *)v46);
      if ( (_DWORD)v47 )
      {
        v49 = (__m128d)*(unsigned __int64 *)v6;
        v49.m128d_f64[0] = v49.m128d_f64[0] / (double)*v46;
        v50 = (__m128d)*(unsigned __int64 *)&DOUBLE_1_0;
        v51 = (__m128d)*(unsigned __int64 *)&DOUBLE_1_0;
        v51.m128d_f64[0] = 1.0 - *((double *)v6 + 2) / (double)*v46;
        v52 = (__m128d)*((unsigned __int64 *)v6 + 1);
        v52.m128d_f64[0] = v52.m128d_f64[0] / (double)(int)v47;
        v50.m128d_f64[0] = 1.0 - *((double *)v6 + 3) / (double)(int)v47;
        v45 = _mm_unpacklo_pd(v51, v50);
        v44 = _mm_unpacklo_pd(v49, v52);
      }
    }
    v69 = 0;
    v70 = 0;
    v71 = 0;
    v72 = 0;
    v73 = &dword_180485584;
    v74 = 0x1000000;
    v53 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x20, v47, v48);
    if ( v53 )
    {
      *v53 = *v35;
      v53[1] = v35[1];
      v70 = v53;
    }
    else
    {
      v70 = 0;
    }
    v71 = v80;
    v56 = (__m128d *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x20, v54, v55);
    v59 = v56;
    if ( v56 )
    {
      *v56 = v44;
      v56[1] = v45;
    }
    else
    {
      v59 = 0;
    }
    v60 = (__m128d *)v69;
    if ( v59 )
      v60 = v59;
    *(_QWORD *)&v69 = v60;
    v61 = (GEL::GDIImageBrushResource *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x68, v57, v58);
    v67 = v61;
    if ( v61 )
      v62 = (GEL::GDIImageBrushResource *)GEL::GDIImageBrushResource::GDIImageBrushResource(
                                            v61,
                                            (const struct GEL::ImageFillInfo *)&v69,
                                            a3);
    else
      v62 = 0;
    v67 = v62;
    CurrentFrame = GEL::RenderStage::GetCurrentFrame(this);
    GEL::GDITech::FillPathWithImage(
      this,
      a2,
      0,
      v76,
      (__int64)v35,
      1,
      (__int64)v62,
      (__int64)&CurrentFrame->lpVtbl->Minimize,
      0);
    if ( v62 )
      GEL::GDIImageBrushResource::`vector deleting destructor'(v62, 1u);
    GEL::ImageFillInfo::~ImageFillInfo((GEL::ImageFillInfo *)&v69);
    if ( v76 )
      GdipDeletePath();
  }
  else
  {
    v75 = 0;
    v7 = GdipCreateImageAttributes(&v75);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v7, v8, v9, 38322455);
    GdipSetImageAttributesWrapMode(v75, (unsigned __int8)v80, 0, 0);
    v10 = 0.0;
    if ( Gfx::Rect::FIsEmpty(v6) )
      v11 = 0.0;
    else
      v11 = *((double *)v6 + 3) - *((double *)v6 + 1);
    if ( !Gfx::Rect::FIsEmpty(v6) )
      v10 = *((double *)v6 + 2) - *(double *)v6;
    *(float *)&v14 = *(double *)(v13 + v12);
    *(float *)&v15 = *(double *)v6;
    Math::TRect<double>::GetHeight(v79, v12);
    Width = Math::TRect<double>::GetWidth(v17, v16);
    try
    {
      *(float *)&v21 = Width;
      *(float *)&v22 = v18[1];
      *(float *)&v23 = *v18;
      *(float *)&v66 = v11;
      *(float *)&v65 = v10;
      v24 = GEL::GDITech::DrawImageRectRect(this, 0, v23, v22, v21, v20, v15, v14, v65, v66);
      v25 = (*(__int64 (__fastcall **)(const struct Image *))(*(_QWORD *)a3 + 88LL))(a3);
    }
    catch ( const OException *v68 )
    {
      v64 = *((_DWORD *)v68 + 129);
      if ( v64 != -2147024882 && (unsigned int)(v64 + 2003292412) > 0x92 )
        throw;
      goto LABEL_9;
    }
    if ( v25 || v24 != 1 )
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v24, v26, v27, 38322456);
LABEL_9:
    if ( v75 )
      GdipDisposeImageAttributes();
  }
}

```

## disassembly

```asm
0x180140ed4  mov     rax, rsp
0x180140ed7  mov     [rax+8], rsi
0x180140edb  mov     [rax+10h], rdi
0x180140edf  mov     [rax+20h], r9
0x180140ee3  push    r12
0x180140ee5  push    r14
0x180140ee7  push    r15
0x180140ee9  sub     rsp, 110h
0x180140ef0  movaps  xmmword ptr [rax-28h], xmm6
0x180140ef4  movaps  xmmword ptr [rax-38h], xmm7
0x180140ef8  movaps  xmmword ptr [rax-48h], xmm8
0x180140efd  movaps  xmmword ptr [rax-58h], xmm9
0x180140f02  mov     rsi, r8
0x180140f05  mov     r12, rdx
0x180140f08  mov     r15, rcx
0x180140f0b  mov     rdi, [rsp+128h+arg_20]
0x180140f13  mov     rax, [r8]
0x180140f16  mov     rcx, r8
0x180140f19  mov     rax, [rax+0B0h]
0x180140f20  call    cs:__guard_dispatch_icall_fptr
0x180140f26  cmp     eax, 0Fh
0x180140f29  jz      loc_1801410B2
0x180140f2f  mov     [rsp+128h+arg_10], 0
0x180140f3b  lea     rcx, [rsp+128h+arg_10]
0x180140f43  call    cs:__imp_GdipCreateImageAttributes
0x180140f49  mov     r9d, 248C117h
0x180140f4f  mov     ecx, eax
0x180140f51  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180140f56  movzx   edx, byte ptr [rsp+128h+arg_30]
0x180140f5e  xor     r9d, r9d
0x180140f61  xor     r8d, r8d
0x180140f64  mov     rcx, [rsp+128h+arg_10]
0x180140f6c  call    cs:__imp_GdipSetImageAttributesWrapMode
0x180140f72  mov     rcx, rdi; this
0x180140f75  call    ?FIsEmpty@Rect@Gfx@@QEBA_NXZ; Gfx::Rect::FIsEmpty(void)
0x180140f7a  mov     r8, rdi
0x180140f7d  mov     edx, 8
0x180140f82  xorps   xmm8, xmm8
0x180140f86  test    al, al
0x180140f88  jnz     loc_1801413A9
0x180140f8e  movsd   xmm9, qword ptr [rdi+18h]
0x180140f94  subsd   xmm9, qword ptr [rdi+8]
0x180140f9a  mov     rcx, rdi; this
0x180140f9d  call    ?FIsEmpty@Rect@Gfx@@QEBA_NXZ; Gfx::Rect::FIsEmpty(void)
0x180140fa2  test    al, al
0x180140fa4  jnz     short loc_180140FB1
0x180140fa6  movsd   xmm8, qword ptr [rdi+10h]
0x180140fac  subsd   xmm8, qword ptr [rdi]
0x180140fb1  movsd   xmm6, qword ptr [r8+rdx]
0x180140fb7  cvtpd2ps xmm6, xmm6
0x180140fbb  movsd   xmm7, qword ptr [rdi]
0x180140fbf  cvtpd2ps xmm7, xmm7
0x180140fc3  mov     rcx, [rsp+128h+arg_28]
0x180140fcb  call    ?GetHeight@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetHeight(void)
0x180140fd0  xorps   xmm5, xmm5
0x180140fd3  cvtsd2ss xmm5, xmm0
0x180140fd7  call    ?GetWidth@?$TRect@N@Math@@QEBANXZ; Math::TRect<double>::GetWidth(void)
0x180140fdc  xorps   xmm3, xmm3
0x180140fdf  cvtsd2ss xmm3, xmm0
0x180140fe3  movsd   xmm4, qword ptr [rcx+8]
0x180140fe8  cvtpd2ps xmm4, xmm4
0x180140fec  movsd   xmm2, qword ptr [rcx]
0x180140ff0  cvtpd2ps xmm2, xmm2
0x180140ff4  cvtpd2ps xmm0, xmm9
0x180140ff9  cvtpd2ps xmm1, xmm8
0x180140ffe  movss   [rsp+128h+var_C8], xmm0; int
0x180141004  movss   [rsp+128h+var_D0], xmm1; int
0x18014100a  movss   [rsp+128h+var_D8], xmm6; int
0x180141010  movss   [rsp+128h+var_E0], xmm7; int
0x180141016  movss   [rsp+128h+var_E8], xmm5; int
0x18014101c  movss   [rsp+128h+var_F0], xmm3; int
0x180141022  movss   [rsp+128h+var_F8], xmm4; int
0x180141028  movss   [rsp+128h+var_100], xmm2; int
0x18014102e  mov     [rsp+128h+var_108], 0; char
0x180141033  lea     r9, [rsp+128h+arg_10]
0x18014103b  mov     r8, rsi
0x18014103e  mov     rdx, r12
0x180141041  mov     rcx, r15; this
0x180141044  call    ?DrawImageRectRect@GDITech@GEL@@CA?AW4Status@Gdiplus@@AEBVRenderStage@2@AEAVGpGraphics@4@AEBVImage@2@AEBV?$TGpHolder@VGpImageAttributes@Gdiplus@@@GDIPlus@ARC@@_NMMMMMMMM@Z; GEL::GDITech::DrawImageRectRect(GEL::RenderStage const &,Gdiplus::GpGraphics &,GEL::Image const &,ARC::GDIPlus::TGpHolder<Gdiplus::GpImageAttributes> const &,bool,float,float,float,float,float,float,float,float)
0x180141049  mov     edi, eax
0x18014104b  mov     rcx, [rsi]
0x18014104e  mov     rax, [rcx+58h]
0x180141052  mov     rcx, rsi
0x180141055  call    cs:__guard_dispatch_icall_fptr
0x18014105b  test    al, al
0x18014105d  jz      loc_1801413C1
0x180141063  mov     r9d, 248C118h
0x180141069  mov     ecx, edi
0x18014106b  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180141070  nop
0x180141071  mov     rcx, [rsp+128h+arg_10]
0x180141079  test    rcx, rcx
0x18014107c  jz      short loc_180141084
0x18014107e  call    cs:__imp_GdipDisposeImageAttributes
0x180141084  lea     r11, [rsp+128h+var_18]
0x18014108c  mov     rsi, [r11+20h]
0x180141090  mov     rdi, [r11+28h]
0x180141094  movaps  xmm6, xmmword ptr [r11-10h]
0x180141099  movaps  xmm7, xmmword ptr [r11-20h]
0x18014109e  movaps  xmm8, xmmword ptr [r11-30h]
0x1801410a3  movaps  xmm9, xmmword ptr [r11-40h]
0x1801410a8  mov     rsp, r11
0x1801410ab  pop     r15
0x1801410ad  pop     r14
0x1801410af  pop     r12
0x1801410b1  retn
0x1801410b2  mov     [rsp+128h+arg_18], 0
0x1801410be  lea     rdx, [rsp+128h+arg_18]
0x1801410c6  xor     ecx, ecx
0x1801410c8  call    cs:__imp_GdipCreatePath
0x1801410ce  mov     r9d, 248C113h
0x1801410d4  mov     ecx, eax
0x1801410d6  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801410db  mov     rcx, [rsp+128h+arg_18]
0x1801410e3  call    cs:__imp_GdipStartPathFigure
0x1801410e9  mov     r9d, 248C114h
0x1801410ef  mov     ecx, eax
0x1801410f1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801410f6  lea     rax, [rsp+128h+var_B8]
0x1801410fb  mov     r14, [rsp+128h+arg_28]
0x180141103  mov     rcx, r14
0x180141106  mov     edx, 8
0x18014110b  lea     r8d, [rdx-4]
0x18014110f  movsd   xmm0, qword ptr [rcx]
0x180141113  cvtpd2ps xmm0, xmm0
0x180141117  movss   dword ptr [rax], xmm0
0x18014111b  add     rcx, rdx
0x18014111e  lea     rax, [rax+4]
0x180141122  sub     r8, 1
0x180141126  jnz     short loc_18014110F
0x180141128  movss   xmm1, dword ptr [rsp+128h+var_B8]
0x18014112e  movss   xmm3, [rsp+128h+var_B0]
0x180141134  movss   xmm2, dword ptr [rsp+128h+var_B8+4]
0x18014113a  movss   xmm0, [rsp+128h+var_AC]
0x180141140  comiss  xmm1, xmm3
0x180141143  ja      loc_180141399
0x180141149  comiss  xmm2, xmm0
0x18014114c  ja      loc_180141399
0x180141152  movaps  xmm5, xmm0
0x180141155  subss   xmm5, xmm2
0x180141159  comiss  xmm1, xmm3
0x18014115c  ja      loc_1801413A1
0x180141162  comiss  xmm2, xmm0
0x180141165  ja      loc_1801413A1
0x18014116b  subss   xmm3, xmm1
0x18014116f  movss   dword ptr [rsp+128h+var_108], xmm5
0x180141175  mov     rcx, [rsp+128h+arg_18]
0x18014117d  call    cs:__imp_GdipAddPathRectangle
0x180141183  mov     r9d, 248C115h
0x180141189  mov     ecx, eax
0x18014118b  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180141190  mov     rcx, [rsp+128h+arg_18]
0x180141198  call    cs:__imp_GdipClosePathFigure
0x18014119e  mov     r9d, 248C116h
0x1801411a4  mov     ecx, eax
0x1801411a6  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801411ab  xorps   xmm6, xmm6
0x1801411ae  xorps   xmm7, xmm7
0x1801411b1  mov     rax, [rsi]
0x1801411b4  lea     rdx, [rsp+128h+var_B8]
0x1801411b9  mov     rcx, rsi
0x1801411bc  mov     rax, [rax+38h]
0x1801411c0  call    cs:__guard_dispatch_icall_fptr
0x1801411c6  cmp     dword ptr [rax], 0
0x1801411c9  jbe     short loc_180141226
0x1801411cb  mov     rdx, [rax]
0x1801411ce  shr     rdx, 20h; unsigned __int64
0x1801411d2  test    edx, edx
0x1801411d4  jz      short loc_180141226
0x1801411d6  movsd   xmm6, qword ptr [rdi]
0x1801411da  mov     ecx, [rax]
0x1801411dc  xorps   xmm1, xmm1
0x1801411df  cvtsi2sd xmm1, rcx
0x1801411e4  divsd   xmm6, xmm1
0x1801411e8  movsd   xmm0, qword ptr [rdi+10h]
0x1801411ed  divsd   xmm0, xmm1
0x1801411f1  movsd   xmm4, cs:__real@3ff0000000000000
0x1801411f9  movaps  xmm7, xmm4
0x1801411fc  subsd   xmm7, xmm0
0x180141200  movsd   xmm3, qword ptr [rdi+8]
0x180141205  xorps   xmm1, xmm1
0x180141208  cvtsi2sd xmm1, rdx
0x18014120d  divsd   xmm3, xmm1
0x180141211  movsd   xmm0, qword ptr [rdi+18h]
0x180141216  divsd   xmm0, xmm1
0x18014121a  subsd   xmm4, xmm0
0x18014121e  unpcklpd xmm7, xmm4
0x180141222  unpcklpd xmm6, xmm3
0x180141226  xorps   xmm0, xmm0
0x180141229  movdqa  [rsp+128h+var_98], xmm0
0x180141232  mov     [rsp+128h+var_88], 0
0x18014123e  mov     [rsp+128h+var_80], 0
0x180141246  movdqa  [rsp+128h+var_78], xmm0
0x18014124f  lea     rax, dword_180485584
0x180141256  mov     [rsp+128h+var_68], rax
0x18014125e  mov     [rsp+128h+var_60], 1000000h
0x180141269  mov     edi, 20h ; ' '
0x18014126e  mov     ecx, edi; this
0x180141270  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180141275  test    rax, rax
0x180141278  jz      loc_18014137A
0x18014127e  movups  xmm0, xmmword ptr [r14]
0x180141282  movups  xmmword ptr [rax], xmm0
0x180141285  movups  xmm1, xmmword ptr [r14+10h]
0x18014128a  movups  xmmword ptr [rax+10h], xmm1
0x18014128e  mov     [rsp+128h+var_88], rax
0x180141296  mov     al, byte ptr [rsp+128h+arg_30]
0x18014129d  mov     [rsp+128h+var_80], al
0x1801412a4  mov     rcx, rdi; this
0x1801412a7  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801412ac  mov     rcx, rax
0x1801412af  test    rax, rax
0x1801412b2  jz      loc_18014138B
0x1801412b8  movups  xmmword ptr [rax], xmm6
0x1801412bb  movups  xmmword ptr [rax+10h], xmm7
0x1801412bf  mov     rax, qword ptr [rsp+128h+var_98]
0x1801412c7  test    rcx, rcx
0x1801412ca  cmovnz  rax, rcx
0x1801412ce  mov     qword ptr [rsp+128h+var_98], rax
0x1801412d6  mov     ecx, 68h ; 'h'; this
0x1801412db  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801412e0  mov     [rsp+128h+var_B8], rax
0x1801412e5  test    rax, rax
0x1801412e8  jz      loc_180141392
0x1801412ee  mov     r8, rsi; struct Image *
0x1801412f1  lea     rdx, [rsp+128h+var_98]; struct GEL::ImageFillInfo *
0x1801412f9  mov     rcx, rax; this
0x1801412fc  call    ??0GDIImageBrushResource@GEL@@QEAA@AEBUImageFillInfo@1@AEBVImage@1@@Z; GEL::GDIImageBrushResource::GDIImageBrushResource(GEL::ImageFillInfo const &,GEL::Image const &)
0x180141301  mov     rdi, rax
0x180141304  mov     [rsp+128h+var_B8], rdi
0x180141309  mov     rcx, r15; this
0x18014130c  call    ?GetCurrentFrame@RenderStage@GEL@@QEAAAEAVFrame@12@XZ; GEL::RenderStage::GetCurrentFrame(void)
0x180141311  mov     rcx, [rax]
0x180141314  add     rcx, 40h ; '@'
0x180141318  mov     qword ptr [rsp+128h+var_E8], 0
0x180141321  mov     qword ptr [rsp+128h+var_F0], rcx
0x180141326  mov     qword ptr [rsp+128h+var_F8], rdi
0x18014132b  mov     byte ptr [rsp+128h+var_100], 1
0x180141330  mov     qword ptr [rsp+128h+var_108], r14
0x180141335  mov     r9, [rsp+128h+arg_18]
0x18014133d  xor     r8d, r8d
0x180141340  mov     rdx, r12
0x180141343  mov     rcx, r15
0x180141346  call    ?FillPathWithImage@GDITech@GEL@@CAXAEBVRenderStage@2@AEAVGpGraphics@Gdiplus@@PEAUIPostScriptSink@Gfx@@PEBVGpPath@5@AEBU?$TRect@N@Math@@_NAEBVGDIImageBrushResource@2@AEBU?$TAffine3x3@N@Math@@PEBU?$TAffine3x3@N@Math@@@Z; GEL::GDITech::FillPathWithImage(GEL::RenderStage const &,Gdiplus::GpGraphics &,Gfx::IPostScriptSink *,Gdiplus::GpPath const *,Math::TRect<double> const &,bool,GEL::GDIImageBrushResource const &,Math::TAffine3x3<double> const &,Math::TAffine3x3<double> const *)
0x18014134b  nop
0x18014134c  test    rdi, rdi
0x18014134f  jnz     short loc_1801413B2
0x180141351  lea     rcx, [rsp+128h+var_98]; this
0x180141359  call    ??1ImageFillInfo@GEL@@QEAA@XZ; GEL::ImageFillInfo::~ImageFillInfo(void)
0x18014135e  mov     rcx, [rsp+128h+arg_18]
0x180141366  test    rcx, rcx
0x180141369  jz      loc_180141084
0x18014136f  call    cs:__imp_GdipDeletePath
0x180141375  jmp     loc_180141084
0x18014137a  mov     [rsp+128h+var_88], 0
0x180141386  jmp     loc_180141296
0x18014138b  xor     ecx, ecx
0x18014138d  jmp     loc_1801412BF
0x180141392  xor     edi, edi
0x180141394  jmp     loc_180141304
0x180141399  xorps   xmm5, xmm5
0x18014139c  jmp     loc_180141159
0x1801413a1  xorps   xmm3, xmm3
0x1801413a4  jmp     loc_18014116F
0x1801413a9  xorps   xmm9, xmm9
0x1801413ad  jmp     loc_180140F9A
0x1801413b2  mov     edx, 1; unsigned int
0x1801413b7  mov     rcx, rdi; this
0x1801413ba  call    ??_EGDIImageBrushResource@GEL@@UEAAPEAXI@Z; GEL::GDIImageBrushResource::`vector deleting destructor'(uint)
0x1801413bf  jmp     short loc_180141351
0x1801413c1  cmp     edi, 1
0x1801413c4  jz      loc_180141071
0x1801413ca  jmp     loc_180141063
0x1801413cf  jmp     loc_180141071
```
