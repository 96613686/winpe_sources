# GEL::BitmapBasedPrinter::EnsureMetafileGraphicsSurface(void)

- ea: `0x1800c32b0`
- end: `0x1800c34a3`
- name: `?EnsureMetafileGraphicsSurface@BitmapBasedPrinter@GEL@@IEAAAEAVGraphicsSurface@2@XZ`
- size: `499`
- prototype: `struct GEL::GraphicsSurface *__fastcall(GEL::BitmapBasedPrinter *__hidden this)`
- caller_count: `4`
- callee_count: `14`
- tags: ``

## callers

- `0x1800c0ca0`
- `0x1800c3d3c`
- `0x1800c52b0`
- `0x1801fa870`

## callees

- `0x180062394`
- `0x180064854`
- `0x180064888`
- `0x180064bb8`
- `0x180064e30`
- `0x1800786fc`
- `0x1800a9b44`
- `0x1800c2420`
- `0x1800c32b0`
- `0x1800c35f0`
- `0x1800c39a4`
- `0x1800c3ce0`
- `0x1800c4740`
- `0x18014284c`

## import_xrefs

- `gdiplus!GdipGetImageGraphicsContext` at `0x1800c3342`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1800c3342`
- `gdiplus!GdipSetPageUnit` at `0x1800c3377`
- `gdiplus!GdipSetPageUnit` at `0x1800c3377`
- `gdiplus!GdipDeleteGraphics` at `0x1800c343c`
- `gdiplus!GdipDeleteGraphics` at `0x1800c343c`
- `gdiplus!GdipCreateFromHDC` at `0x1800c335b`
- `gdiplus!GdipCreateFromHDC` at `0x1800c335b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct GEL::GraphicsSurface *__fastcall GEL::BitmapBasedPrinter::EnsureMetafileGraphicsSurface(
        GEL::BitmapBasedPrinter *this)
{
  char *v1; // rdi
  int v2; // esi
  unsigned int ImageGraphicsContext; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  unsigned __int64 v13; // xmm0_8
  void *v14; // rax
  GEL::GraphicsSurface *v15; // rax
  unsigned int GpGraphics; // eax
  __m128i v18[3]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+80h] [rbp+20h] BYREF
  void *v20; // [rsp+88h] [rbp+28h]

  if ( !*((_BYTE *)this + 448) )
    goto LABEL_16;
  if ( !*((_BYTE *)this + 586) )
  {
    if ( !GEL::BitmapBasedPrinter::InMetafileMode(this) )
    {
      GEL::FailureException::ThrowTag(0x8591E2u);
LABEL_18:
      v14 = (void *)GEL::GraphicsSurface::GraphicsSurface(v14, &v19, v18, 1);
LABEL_11:
      Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>(v1, v14);
      v18[0] = _mm_load_si128((const __m128i *)&_xmm);
      v18[1] = _mm_load_si128((const __m128i *)&_xmm);
      v18[2] = 0;
      v15 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->(v1);
      GpGraphics = (unsigned int)GEL::GraphicsSurface::GetGpGraphics(v15);
      GEL::PrinterClipStack::SetGraphics(v2, 1, *((_QWORD *)this + 8), GpGraphics, (__int64)v18);
      if ( v19 )
        GdipDeleteGraphics();
      return *(struct GEL::GraphicsSurface **)v1;
    }
    v2 = (_DWORD)this + 248;
    GEL::PrinterClipStack::ReleaseGraphics((char *)this + 248, 2, *((_QWORD *)this + 8));
    Mso::TCntPtr<GEL::GraphicsSurface>::Clear((char *)this + 488);
    v1 = (char *)this + 576;
    if ( *((_QWORD *)this + 72) )
      return *(struct GEL::GraphicsSurface **)v1;
    GEL::BitmapBasedPrinter::CreateMetafile(this);
    v19 = 0;
    if ( *((_BYTE *)this + 584) )
    {
      ImageGraphicsContext = GdipGetImageGraphicsContext(*((_QWORD *)this + 69), &v19);
      v7 = 38869212;
    }
    else
    {
      ImageGraphicsContext = GdipCreateFromHDC(*((_QWORD *)this + 68), &v19);
      v7 = 38869211;
    }
    Gfx::GdipStatus_ThrowOnFailureMessageTag(ImageGraphicsContext, v5, v6, v7);
    v8 = GdipSetPageUnit(v19, 2);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v8, v9, v10, 38869213);
    v18[0] = *(__m128i *)GEL::Printer::GetPixelBounds(this, v18);
    v13 = _mm_srli_si128(v18[0], 8).m128i_u64[0];
    if ( v18[0].m128i_i32[0] < (int)v13 && v18[0].m128i_i32[1] < SHIDWORD(v13) )
    {
      v14 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x60, v11, v12);
      v20 = v14;
      if ( !v14 )
        goto LABEL_11;
      goto LABEL_18;
    }
    GEL::FailureException::ThrowTag(0x8591E3u);
LABEL_16:
    GEL::FailureException::ThrowTag(0x8591E1u);
    __debugbreak();
  }
  return (struct GEL::GraphicsSurface *)*((_QWORD *)this + 39);
}

```

## disassembly

```asm
0x1800c32b0  mov     [rsp-18h+arg_10], rbx
0x1800c32b5  push    rbp
0x1800c32b6  push    rsi
0x1800c32b7  push    rdi
0x1800c32b8  mov     rbp, rsp
0x1800c32bb  sub     rsp, 60h
0x1800c32bf  mov     rbx, rcx
0x1800c32c2  cmp     byte ptr [rcx+1C0h], 0
0x1800c32c9  jz      loc_1800C346D
0x1800c32cf  cmp     byte ptr [rcx+24Ah], 0
0x1800c32d6  jnz     loc_1800C3455
0x1800c32dc  call    ?InMetafileMode@BitmapBasedPrinter@GEL@@UEBA_NXZ; GEL::BitmapBasedPrinter::InMetafileMode(void)
0x1800c32e1  test    al, al
0x1800c32e3  jz      loc_1800C3478
0x1800c32e9  lea     rsi, [rbx+0F8h]
0x1800c32f0  mov     r8, [rbx+40h]
0x1800c32f4  mov     edx, 2
0x1800c32f9  mov     rcx, rsi
0x1800c32fc  call    ?ReleaseGraphics@PrinterClipStack@GEL@@QEAAXW4SurfaceType@12@PEBVFrame@ITarget@Gfx@@@Z; GEL::PrinterClipStack::ReleaseGraphics(GEL::PrinterClipStack::SurfaceType,Gfx::ITarget::Frame const *)
0x1800c3301  lea     rcx, [rbx+1E8h]
0x1800c3308  call    ?Clear@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAXXZ; Mso::TCntPtr<GEL::GraphicsSurface>::Clear(void)
0x1800c330d  lea     rdi, [rbx+240h]
0x1800c3314  cmp     qword ptr [rdi], 0
0x1800c3318  jnz     loc_1800C3442
0x1800c331e  mov     rcx, rbx; this
0x1800c3321  call    ?CreateMetafile@BitmapBasedPrinter@GEL@@IEAAXXZ; GEL::BitmapBasedPrinter::CreateMetafile(void)
0x1800c3326  mov     [rbp+arg_0], 0
0x1800c332e  cmp     byte ptr [rbx+248h], 0
0x1800c3335  jz      short loc_1800C3350
0x1800c3337  lea     rdx, [rbp+arg_0]
0x1800c333b  mov     rcx, [rbx+228h]
0x1800c3342  call    cs:__imp_GdipGetImageGraphicsContext
0x1800c3348  mov     r9d, 25118DCh
0x1800c334e  jmp     short loc_1800C3367
0x1800c3350  lea     rdx, [rbp+arg_0]
0x1800c3354  mov     rcx, [rbx+220h]
0x1800c335b  call    cs:__imp_GdipCreateFromHDC
0x1800c3361  mov     r9d, 25118DBh
0x1800c3367  mov     ecx, eax
0x1800c3369  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c336e  mov     edx, 2
0x1800c3373  mov     rcx, [rbp+arg_0]
0x1800c3377  call    cs:__imp_GdipSetPageUnit
0x1800c337d  mov     r9d, 25118DDh
0x1800c3383  mov     ecx, eax
0x1800c3385  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c338a  lea     rdx, [rbp+var_30]
0x1800c338e  mov     rcx, rbx
0x1800c3391  call    ?GetPixelBounds@Printer@GEL@@UEBA?AV?$TConvertibleRectPx@H@Gfx@@XZ; GEL::Printer::GetPixelBounds(void)
0x1800c3396  movups  xmm0, xmmword ptr [rax]
0x1800c3399  movups  [rbp+var_30], xmm0
0x1800c339d  movq    rax, xmm0
0x1800c33a2  psrldq  xmm0, 8
0x1800c33a7  movq    rcx, xmm0
0x1800c33ac  cmp     eax, ecx
0x1800c33ae  jge     loc_1800C345E
0x1800c33b4  shr     rcx, 20h
0x1800c33b8  shr     rax, 20h
0x1800c33bc  cmp     eax, ecx
0x1800c33be  jge     loc_1800C345E
0x1800c33c4  mov     ecx, 60h ; '`'; this
0x1800c33c9  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800c33ce  mov     [rbp+arg_8], rax
0x1800c33d2  test    rax, rax
0x1800c33d5  jnz     loc_1800C3487
0x1800c33db  mov     rdx, rax
0x1800c33de  mov     rcx, rdi
0x1800c33e1  call    ??$?4VGraphicsSurface@GEL@@X@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAAEAV01@PEAVGraphicsSurface@GEL@@@Z; Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>(GEL::GraphicsSurface *)
0x1800c33e6  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1800c33ee  movups  [rbp+var_30], xmm0
0x1800c33f2  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1800c33fa  movups  [rbp+var_20], xmm1
0x1800c33fe  xorps   xmm0, xmm0
0x1800c3401  movups  [rbp+var_10], xmm0
0x1800c3405  mov     rcx, rdi
0x1800c3408  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800c340d  mov     rcx, rax; this
0x1800c3410  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c3415  lea     rcx, [rbp+var_30]
0x1800c3419  mov     [rsp+60h+var_40], rcx
0x1800c341e  mov     r9, rax
0x1800c3421  mov     r8, [rbx+40h]
0x1800c3425  mov     edx, 1
0x1800c342a  mov     rcx, rsi
0x1800c342d  call    ?SetGraphics@PrinterClipStack@GEL@@QEAAXW4SurfaceType@12@PEBVFrame@ITarget@Gfx@@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@_N@Z; GEL::PrinterClipStack::SetGraphics(GEL::PrinterClipStack::SurfaceType,Gfx::ITarget::Frame const *,Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &,bool)
0x1800c3432  nop
0x1800c3433  mov     rcx, [rbp+arg_0]
0x1800c3437  test    rcx, rcx
0x1800c343a  jz      short loc_1800C3442
0x1800c343c  call    cs:__imp_GdipDeleteGraphics
0x1800c3442  mov     rax, [rdi]
0x1800c3445  mov     rbx, [rsp+60h+arg_10]
0x1800c344d  add     rsp, 60h
0x1800c3451  pop     rdi
0x1800c3452  pop     rsi
0x1800c3453  pop     rbp
0x1800c3454  retn
0x1800c3455  mov     rax, [rcx+138h]
0x1800c345c  jmp     short loc_1800C3445
0x1800c345e  mov     ecx, 8591E3h; unsigned int
0x1800c3463  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800c3468  nop
0x1800c3469  jmp     short loc_1800C346C
0x1800c346c  nop
0x1800c346d  mov     ecx, 8591E1h; unsigned int
0x1800c3472  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800c3477  int     3; Trap to Debugger
0x1800c3478  mov     ecx, 8591E2h; unsigned int
0x1800c347d  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800c3482  nop
0x1800c3483  jmp     short loc_1800C3486
0x1800c3486  nop
0x1800c3487  mov     r9d, 1
0x1800c348d  lea     r8, [rbp+var_30]
0x1800c3491  lea     rdx, [rbp+arg_0]
0x1800c3495  mov     rcx, rax
0x1800c3498  call    ??0GraphicsSurface@GEL@@QEAA@AEAV?$TGpHolder@VGpGraphics@Gdiplus@@@GDIPlus@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@W4AlphaMode@4@@Z; GEL::GraphicsSurface::GraphicsSurface(ARC::GDIPlus::TGpHolder<Gdiplus::GpGraphics> &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,ARC::AlphaMode)
0x1800c349d  jmp     loc_1800C33DB
```
