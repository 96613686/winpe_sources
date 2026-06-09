# GEL::DC::EnsureGraphicsSurface(void)

- ea: `0x1800646c0`
- end: `0x1800647a0`
- name: `?EnsureGraphicsSurface@DC@GEL@@EEAAAEAVGraphicsSurface@2@XZ`
- size: `224`
- prototype: `struct GEL::GraphicsSurface *__fastcall(GEL::DC *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180062394`
- `0x1800646c0`
- `0x180064854`
- `0x180064bb8`
- `0x180064e30`
- `0x1800650d8`
- `0x1800786fc`
- `0x18014284c`

## import_xrefs

- `gdiplus!GdipSetPageUnit` at `0x180064710`
- `gdiplus!GdipSetPageUnit` at `0x180064710`
- `gdiplus!GdipDeleteGraphics` at `0x18006478c`
- `gdiplus!GdipDeleteGraphics` at `0x18006478c`
- `gdiplus!GdipCreateFromHDC` at `0x1800646f3`
- `gdiplus!GdipCreateFromHDC` at `0x1800646f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct GEL::GraphicsSurface *__fastcall GEL::DC::EnsureGraphicsSurface(GEL::DC *this)
{
  char *v2; // rdi
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
  struct Gdiplus::GpGraphics *GpGraphics; // rax
  __int64 v15; // [rsp+30h] [rbp+8h] BYREF
  void *v16; // [rsp+38h] [rbp+10h]

  v2 = (char *)this + 288;
  if ( !*((_QWORD *)this + 36) )
  {
    v15 = 0;
    v3 = GdipCreateFromHDC(*((_QWORD *)this + 33), &v15);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v3, v4, v5, 38871046);
    v6 = GdipSetPageUnit(v15, 2);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v6, v7, v8, 38871047);
    v11 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x60, v9, v10);
    v16 = v11;
    if ( v11 )
      v11 = (void *)GEL::GraphicsSurface::GraphicsSurface(v11, &v15, (char *)this + 272, *((unsigned int *)this + 15));
    Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>(v2, v11);
    v12 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->(v2);
    GpGraphics = GEL::GraphicsSurface::GetGpGraphics(v12);
    Gfx::GDIPlusClipStack::SetGraphics(
      (GEL::DC *)((char *)this + 224),
      *((const struct Frame **)this + 5),
      GpGraphics,
      1);
    if ( v15 )
      GdipDeleteGraphics();
  }
  return *(struct GEL::GraphicsSurface **)v2;
}

```

## disassembly

```asm
0x1800646c0  mov     [rsp+arg_10], rbx
0x1800646c5  push    rdi
0x1800646c6  sub     rsp, 20h
0x1800646ca  mov     rbx, rcx
0x1800646cd  lea     rdi, [rcx+120h]
0x1800646d4  cmp     qword ptr [rdi], 0
0x1800646d8  jnz     loc_180064792
0x1800646de  mov     [rsp+28h+arg_0], 0
0x1800646e7  lea     rdx, [rsp+28h+arg_0]
0x1800646ec  mov     rcx, [rcx+108h]
0x1800646f3  call    cs:__imp_GdipCreateFromHDC
0x1800646f9  mov     r9d, 2512006h
0x1800646ff  mov     ecx, eax
0x180064701  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180064706  mov     edx, 2
0x18006470b  mov     rcx, [rsp+28h+arg_0]
0x180064710  call    cs:__imp_GdipSetPageUnit
0x180064716  mov     r9d, 2512007h
0x18006471c  mov     ecx, eax
0x18006471e  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180064723  mov     ecx, 60h ; '`'; this
0x180064728  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18006472d  mov     [rsp+28h+arg_8], rax
0x180064732  test    rax, rax
0x180064735  jz      short loc_180064750
0x180064737  lea     r8, [rbx+110h]
0x18006473e  mov     r9d, [rbx+3Ch]
0x180064742  lea     rdx, [rsp+28h+arg_0]
0x180064747  mov     rcx, rax
0x18006474a  call    ??0GraphicsSurface@GEL@@QEAA@AEAV?$TGpHolder@VGpGraphics@Gdiplus@@@GDIPlus@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@W4AlphaMode@4@@Z; GEL::GraphicsSurface::GraphicsSurface(ARC::GDIPlus::TGpHolder<Gdiplus::GpGraphics> &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,ARC::AlphaMode)
0x18006474f  nop
0x180064750  mov     rdx, rax
0x180064753  mov     rcx, rdi
0x180064756  call    ??$?4VGraphicsSurface@GEL@@X@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAAEAV01@PEAVGraphicsSurface@GEL@@@Z; Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>(GEL::GraphicsSurface *)
0x18006475b  mov     rcx, rdi
0x18006475e  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x180064763  mov     rcx, rax; this
0x180064766  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x18006476b  lea     rcx, [rbx+0E0h]; this
0x180064772  mov     r9b, 1; bool
0x180064775  mov     r8, rax; struct Gdiplus::GpGraphics *
0x180064778  mov     rdx, [rbx+28h]; struct Frame *
0x18006477c  call    ?SetGraphics@GDIPlusClipStack@Gfx@@QEAAXPEBVFrame@ITarget@2@AEAVGpGraphics@Gdiplus@@_N@Z; Gfx::GDIPlusClipStack::SetGraphics(Gfx::ITarget::Frame const *,Gdiplus::GpGraphics &,bool)
0x180064781  nop
0x180064782  mov     rcx, [rsp+28h+arg_0]
0x180064787  test    rcx, rcx
0x18006478a  jz      short loc_180064792
0x18006478c  call    cs:__imp_GdipDeleteGraphics
0x180064792  mov     rax, [rdi]
0x180064795  mov     rbx, [rsp+28h+arg_10]
0x18006479a  add     rsp, 20h
0x18006479e  pop     rdi
0x18006479f  retn
```
