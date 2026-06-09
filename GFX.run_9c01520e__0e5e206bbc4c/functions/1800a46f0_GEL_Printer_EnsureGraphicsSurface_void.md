# GEL::Printer::EnsureGraphicsSurface(void)

- ea: `0x1800a46f0`
- end: `0x1800a483b`
- name: `?EnsureGraphicsSurface@Printer@GEL@@MEAAAEAVGraphicsSurface@2@XZ`
- size: `331`
- prototype: `struct GEL::GraphicsSurface *__fastcall(GEL::Printer *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800a46b0`
- `0x1801fdfe0`

## callees

- `0x180057e70`
- `0x180072d00`
- `0x18007f754`
- `0x180082564`
- `0x1800828c8`
- `0x180082fdc`
- `0x180092a58`
- `0x1800a46f0`
- `0x1800a4ab0`

## import_xrefs

- `gdiplus!GdipSetPageUnit` at `0x1800a4751`
- `gdiplus!GdipSetPageUnit` at `0x1800a4751`
- `gdiplus!GdipDeleteGraphics` at `0x1800a4821`
- `gdiplus!GdipDeleteGraphics` at `0x1800a4821`
- `gdiplus!GdipCreateFromHDC` at `0x1800a4731`
- `gdiplus!GdipCreateFromHDC` at `0x1800a4731`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct GEL::GraphicsSurface *__fastcall GEL::Printer::EnsureGraphicsSurface(GEL::Printer *this)
{
  char *v2; // rsi
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned __int64 v9; // rdx
  unsigned int v10; // r8d
  void *v11; // rax
  GEL::GraphicsSurface *v12; // rax
  unsigned int GpGraphics; // ebx
  int v14; // eax
  _OWORD v16[4]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+80h] [rbp+8h] BYREF
  void *v18; // [rsp+88h] [rbp+10h]

  if ( *((_QWORD *)this + 36) )
  {
    v2 = (char *)this + 288;
  }
  else
  {
    v17 = 0;
    v3 = GdipCreateFromHDC(*((_QWORD *)this + 32), &v17);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v3, v4, v5, 38869155);
    v6 = GdipSetPageUnit(v17, 2);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v6, v7, v8, 38869184);
    v11 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x60, v9, v10);
    v18 = v11;
    if ( v11 )
      v11 = (void *)GEL::GraphicsSurface::GraphicsSurface(v11, &v17, (char *)this + 316, 3);
    v2 = (char *)this + 288;
    Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>((char *)this + 288, v11);
    v16[0] = _mm_load_si128((const __m128i *)&_xmm);
    v16[1] = _mm_load_si128((const __m128i *)&_xmm);
    v16[2] = 0;
    v12 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->((char *)this + 288);
    GpGraphics = (unsigned int)GEL::GraphicsSurface::GetGpGraphics(v12);
    v14 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this - 3) + 256LL))((char *)this - 24);
    GEL::PrinterClipStack::SetGraphics((_DWORD)this + 224, 0, v14, GpGraphics, (__int64)v16);
    if ( v17 )
      GdipDeleteGraphics();
  }
  return *(struct GEL::GraphicsSurface **)v2;
}

```

## disassembly

```asm
0x1800a46f0  mov     [rsp+arg_10], rbx
0x1800a46f5  push    rsi
0x1800a46f6  push    rdi
0x1800a46f7  push    r14
0x1800a46f9  sub     rsp, 60h
0x1800a46fd  mov     rdi, rcx
0x1800a4700  cmp     qword ptr [rcx+120h], 0
0x1800a4708  jz      short loc_1800A4716
0x1800a470a  lea     rsi, [rcx+120h]
0x1800a4711  jmp     loc_1800A4827
0x1800a4716  mov     [rsp+78h+arg_0], 0
0x1800a4722  lea     rdx, [rsp+78h+arg_0]
0x1800a472a  mov     rcx, [rcx+100h]
0x1800a4731  call    cs:__imp_GdipCreateFromHDC
0x1800a4737  mov     r9d, 25118A3h
0x1800a473d  mov     ecx, eax
0x1800a473f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a4744  mov     edx, 2
0x1800a4749  mov     rcx, [rsp+78h+arg_0]
0x1800a4751  call    cs:__imp_GdipSetPageUnit
0x1800a4757  mov     r9d, 25118C0h
0x1800a475d  mov     ecx, eax
0x1800a475f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a4764  mov     ecx, 60h ; '`'; this
0x1800a4769  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800a476e  mov     [rsp+78h+arg_8], rax
0x1800a4776  test    rax, rax
0x1800a4779  jz      short loc_1800A4799
0x1800a477b  lea     r8, [rdi+13Ch]
0x1800a4782  mov     r9d, 3
0x1800a4788  lea     rdx, [rsp+78h+arg_0]
0x1800a4790  mov     rcx, rax
0x1800a4793  call    ??0GraphicsSurface@GEL@@QEAA@AEAV?$TGpHolder@VGpGraphics@Gdiplus@@@GDIPlus@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@W4AlphaMode@4@@Z; GEL::GraphicsSurface::GraphicsSurface(ARC::GDIPlus::TGpHolder<Gdiplus::GpGraphics> &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,ARC::AlphaMode)
0x1800a4798  nop
0x1800a4799  lea     rsi, [rdi+120h]
0x1800a47a0  mov     rdx, rax
0x1800a47a3  mov     rcx, rsi
0x1800a47a6  call    ??$?4VGraphicsSurface@GEL@@X@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAAEAV01@PEAVGraphicsSurface@GEL@@@Z; Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>(GEL::GraphicsSurface *)
0x1800a47ab  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1800a47b3  movups  [rsp+78h+var_48], xmm0
0x1800a47b8  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1800a47c0  movups  [rsp+78h+var_38], xmm1
0x1800a47c5  xorps   xmm0, xmm0
0x1800a47c8  movups  [rsp+78h+var_28], xmm0
0x1800a47cd  mov     rcx, rsi
0x1800a47d0  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800a47d5  mov     rcx, rax; this
0x1800a47d8  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800a47dd  mov     rbx, rax
0x1800a47e0  mov     rax, [rdi-18h]
0x1800a47e4  lea     rcx, [rdi-18h]
0x1800a47e8  mov     rax, [rax+100h]
0x1800a47ef  call    cs:__guard_dispatch_icall_fptr
0x1800a47f5  lea     rcx, [rdi+0E0h]
0x1800a47fc  lea     rdx, [rsp+78h+var_48]
0x1800a4801  mov     [rsp+78h+var_58], rdx
0x1800a4806  mov     r9, rbx
0x1800a4809  mov     r8, rax
0x1800a480c  xor     edx, edx
0x1800a480e  call    ?SetGraphics@PrinterClipStack@GEL@@QEAAXW4SurfaceType@12@PEBVFrame@ITarget@Gfx@@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@_N@Z; GEL::PrinterClipStack::SetGraphics(GEL::PrinterClipStack::SurfaceType,Gfx::ITarget::Frame const *,Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &,bool)
0x1800a4813  nop
0x1800a4814  mov     rcx, [rsp+78h+arg_0]
0x1800a481c  test    rcx, rcx
0x1800a481f  jz      short loc_1800A4827
0x1800a4821  call    cs:__imp_GdipDeleteGraphics
0x1800a4827  mov     rax, [rsi]
0x1800a482a  mov     rbx, [rsp+78h+arg_10]
0x1800a4832  add     rsp, 60h
0x1800a4836  pop     r14
0x1800a4838  pop     rdi
0x1800a4839  pop     rsi
0x1800a483a  retn
```
