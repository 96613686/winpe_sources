# GEL::BitmapBasedPrinter::EnsureMetafileGraphicsSurface(void)

- ea: `0x1800a578c`
- end: `0x1800a597f`
- name: `?EnsureMetafileGraphicsSurface@BitmapBasedPrinter@GEL@@IEAAAEAVGraphicsSurface@2@XZ`
- size: `499`
- prototype: `struct GEL::GraphicsSurface *__fastcall(GEL::BitmapBasedPrinter *__hidden this)`
- caller_count: `4`
- callee_count: `14`
- tags: ``

## callers

- `0x1800a4278`
- `0x1800a46b0`
- `0x180147bc0`
- `0x1801fdbf0`

## callees

- `0x180072d00`
- `0x18007f754`
- `0x180082564`
- `0x180082598`
- `0x1800828c8`
- `0x180082fdc`
- `0x180092a58`
- `0x1800a4ab0`
- `0x1800a578c`
- `0x1800a5ac0`
- `0x1800a5c90`
- `0x1800a5f40`
- `0x1800a66b0`
- `0x1800dd460`

## import_xrefs

- `gdiplus!GdipGetImageGraphicsContext` at `0x1800a581e`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1800a581e`
- `gdiplus!GdipSetPageUnit` at `0x1800a5853`
- `gdiplus!GdipSetPageUnit` at `0x1800a5853`
- `gdiplus!GdipDeleteGraphics` at `0x1800a5918`
- `gdiplus!GdipDeleteGraphics` at `0x1800a5918`
- `gdiplus!GdipCreateFromHDC` at `0x1800a5837`
- `gdiplus!GdipCreateFromHDC` at `0x1800a5837`

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
0x1800a578c  mov     [rsp-18h+arg_10], rbx
0x1800a5791  push    rbp
0x1800a5792  push    rsi
0x1800a5793  push    rdi
0x1800a5794  mov     rbp, rsp
0x1800a5797  sub     rsp, 60h
0x1800a579b  mov     rbx, rcx
0x1800a579e  cmp     byte ptr [rcx+1C0h], 0
0x1800a57a5  jz      loc_1800A5949
0x1800a57ab  cmp     byte ptr [rcx+24Ah], 0
0x1800a57b2  jnz     loc_1800A5931
0x1800a57b8  call    ?InMetafileMode@BitmapBasedPrinter@GEL@@UEBA_NXZ; GEL::BitmapBasedPrinter::InMetafileMode(void)
0x1800a57bd  test    al, al
0x1800a57bf  jz      loc_1800A5954
0x1800a57c5  lea     rsi, [rbx+0F8h]
0x1800a57cc  mov     r8, [rbx+40h]
0x1800a57d0  mov     edx, 2
0x1800a57d5  mov     rcx, rsi
0x1800a57d8  call    ?ReleaseGraphics@PrinterClipStack@GEL@@QEAAXW4SurfaceType@12@PEBVFrame@ITarget@Gfx@@@Z; GEL::PrinterClipStack::ReleaseGraphics(GEL::PrinterClipStack::SurfaceType,Gfx::ITarget::Frame const *)
0x1800a57dd  lea     rcx, [rbx+1E8h]
0x1800a57e4  call    ?Clear@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAXXZ; Mso::TCntPtr<GEL::GraphicsSurface>::Clear(void)
0x1800a57e9  lea     rdi, [rbx+240h]
0x1800a57f0  cmp     qword ptr [rdi], 0
0x1800a57f4  jnz     loc_1800A591E
0x1800a57fa  mov     rcx, rbx; this
0x1800a57fd  call    ?CreateMetafile@BitmapBasedPrinter@GEL@@IEAAXXZ; GEL::BitmapBasedPrinter::CreateMetafile(void)
0x1800a5802  mov     [rbp+arg_0], 0
0x1800a580a  cmp     byte ptr [rbx+248h], 0
0x1800a5811  jz      short loc_1800A582C
0x1800a5813  lea     rdx, [rbp+arg_0]
0x1800a5817  mov     rcx, [rbx+228h]
0x1800a581e  call    cs:__imp_GdipGetImageGraphicsContext
0x1800a5824  mov     r9d, 25118DCh
0x1800a582a  jmp     short loc_1800A5843
0x1800a582c  lea     rdx, [rbp+arg_0]
0x1800a5830  mov     rcx, [rbx+220h]
0x1800a5837  call    cs:__imp_GdipCreateFromHDC
0x1800a583d  mov     r9d, 25118DBh
0x1800a5843  mov     ecx, eax
0x1800a5845  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a584a  mov     edx, 2
0x1800a584f  mov     rcx, [rbp+arg_0]
0x1800a5853  call    cs:__imp_GdipSetPageUnit
0x1800a5859  mov     r9d, 25118DDh
0x1800a585f  mov     ecx, eax
0x1800a5861  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a5866  lea     rdx, [rbp+var_30]
0x1800a586a  mov     rcx, rbx
0x1800a586d  call    ?GetPixelBounds@Printer@GEL@@UEBA?AV?$TConvertibleRectPx@H@Gfx@@XZ; GEL::Printer::GetPixelBounds(void)
0x1800a5872  movups  xmm0, xmmword ptr [rax]
0x1800a5875  movups  [rbp+var_30], xmm0
0x1800a5879  movq    rax, xmm0
0x1800a587e  psrldq  xmm0, 8
0x1800a5883  movq    rcx, xmm0
0x1800a5888  cmp     eax, ecx
0x1800a588a  jge     loc_1800A593A
0x1800a5890  shr     rcx, 20h
0x1800a5894  shr     rax, 20h
0x1800a5898  cmp     eax, ecx
0x1800a589a  jge     loc_1800A593A
0x1800a58a0  mov     ecx, 60h ; '`'; this
0x1800a58a5  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800a58aa  mov     [rbp+arg_8], rax
0x1800a58ae  test    rax, rax
0x1800a58b1  jnz     loc_1800A5963
0x1800a58b7  mov     rdx, rax
0x1800a58ba  mov     rcx, rdi
0x1800a58bd  call    ??$?4VGraphicsSurface@GEL@@X@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAAEAV01@PEAVGraphicsSurface@GEL@@@Z; Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>(GEL::GraphicsSurface *)
0x1800a58c2  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1800a58ca  movups  [rbp+var_30], xmm0
0x1800a58ce  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1800a58d6  movups  [rbp+var_20], xmm1
0x1800a58da  xorps   xmm0, xmm0
0x1800a58dd  movups  [rbp+var_10], xmm0
0x1800a58e1  mov     rcx, rdi
0x1800a58e4  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800a58e9  mov     rcx, rax; this
0x1800a58ec  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800a58f1  lea     rcx, [rbp+var_30]
0x1800a58f5  mov     [rsp+60h+var_40], rcx
0x1800a58fa  mov     r9, rax
0x1800a58fd  mov     r8, [rbx+40h]
0x1800a5901  mov     edx, 1
0x1800a5906  mov     rcx, rsi
0x1800a5909  call    ?SetGraphics@PrinterClipStack@GEL@@QEAAXW4SurfaceType@12@PEBVFrame@ITarget@Gfx@@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@_N@Z; GEL::PrinterClipStack::SetGraphics(GEL::PrinterClipStack::SurfaceType,Gfx::ITarget::Frame const *,Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &,bool)
0x1800a590e  nop
0x1800a590f  mov     rcx, [rbp+arg_0]
0x1800a5913  test    rcx, rcx
0x1800a5916  jz      short loc_1800A591E
0x1800a5918  call    cs:__imp_GdipDeleteGraphics
0x1800a591e  mov     rax, [rdi]
0x1800a5921  mov     rbx, [rsp+60h+arg_10]
0x1800a5929  add     rsp, 60h
0x1800a592d  pop     rdi
0x1800a592e  pop     rsi
0x1800a592f  pop     rbp
0x1800a5930  retn
0x1800a5931  mov     rax, [rcx+138h]
0x1800a5938  jmp     short loc_1800A5921
0x1800a593a  mov     ecx, 8591E3h; unsigned int
0x1800a593f  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800a5944  nop
0x1800a5945  jmp     short loc_1800A5948
0x1800a5948  nop
0x1800a5949  mov     ecx, 8591E1h; unsigned int
0x1800a594e  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800a5953  int     3; Trap to Debugger
0x1800a5954  mov     ecx, 8591E2h; unsigned int
0x1800a5959  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800a595e  nop
0x1800a595f  jmp     short loc_1800A5962
0x1800a5962  nop
0x1800a5963  mov     r9d, 1
0x1800a5969  lea     r8, [rbp+var_30]
0x1800a596d  lea     rdx, [rbp+arg_0]
0x1800a5971  mov     rcx, rax
0x1800a5974  call    ??0GraphicsSurface@GEL@@QEAA@AEAV?$TGpHolder@VGpGraphics@Gdiplus@@@GDIPlus@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@W4AlphaMode@4@@Z; GEL::GraphicsSurface::GraphicsSurface(ARC::GDIPlus::TGpHolder<Gdiplus::GpGraphics> &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,ARC::AlphaMode)
0x1800a5979  jmp     loc_1800A58B7
```
