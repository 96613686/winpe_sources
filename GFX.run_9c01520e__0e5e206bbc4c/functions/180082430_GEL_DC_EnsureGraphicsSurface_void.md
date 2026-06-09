# GEL::DC::EnsureGraphicsSurface(void)

- ea: `0x180082430`
- end: `0x180082510`
- name: `?EnsureGraphicsSurface@DC@GEL@@EEAAAEAVGraphicsSurface@2@XZ`
- size: `224`
- prototype: `struct GEL::GraphicsSurface *__fastcall(GEL::DC *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180072d00`
- `0x18007f754`
- `0x180081c40`
- `0x180082430`
- `0x180082564`
- `0x1800828c8`
- `0x180082fdc`
- `0x180092a58`

## import_xrefs

- `gdiplus!GdipSetPageUnit` at `0x180082480`
- `gdiplus!GdipSetPageUnit` at `0x180082480`
- `gdiplus!GdipDeleteGraphics` at `0x1800824fc`
- `gdiplus!GdipDeleteGraphics` at `0x1800824fc`
- `gdiplus!GdipCreateFromHDC` at `0x180082463`
- `gdiplus!GdipCreateFromHDC` at `0x180082463`

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
0x180082430  mov     [rsp+arg_10], rbx
0x180082435  push    rdi
0x180082436  sub     rsp, 20h
0x18008243a  mov     rbx, rcx
0x18008243d  lea     rdi, [rcx+120h]
0x180082444  cmp     qword ptr [rdi], 0
0x180082448  jnz     loc_180082502
0x18008244e  mov     [rsp+28h+arg_0], 0
0x180082457  lea     rdx, [rsp+28h+arg_0]
0x18008245c  mov     rcx, [rcx+108h]
0x180082463  call    cs:__imp_GdipCreateFromHDC
0x180082469  mov     r9d, 2512006h
0x18008246f  mov     ecx, eax
0x180082471  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180082476  mov     edx, 2
0x18008247b  mov     rcx, [rsp+28h+arg_0]
0x180082480  call    cs:__imp_GdipSetPageUnit
0x180082486  mov     r9d, 2512007h
0x18008248c  mov     ecx, eax
0x18008248e  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180082493  mov     ecx, 60h ; '`'; this
0x180082498  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18008249d  mov     [rsp+28h+arg_8], rax
0x1800824a2  test    rax, rax
0x1800824a5  jz      short loc_1800824C0
0x1800824a7  lea     r8, [rbx+110h]
0x1800824ae  mov     r9d, [rbx+3Ch]
0x1800824b2  lea     rdx, [rsp+28h+arg_0]
0x1800824b7  mov     rcx, rax
0x1800824ba  call    ??0GraphicsSurface@GEL@@QEAA@AEAV?$TGpHolder@VGpGraphics@Gdiplus@@@GDIPlus@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@W4AlphaMode@4@@Z; GEL::GraphicsSurface::GraphicsSurface(ARC::GDIPlus::TGpHolder<Gdiplus::GpGraphics> &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,ARC::AlphaMode)
0x1800824bf  nop
0x1800824c0  mov     rdx, rax
0x1800824c3  mov     rcx, rdi
0x1800824c6  call    ??$?4VGraphicsSurface@GEL@@X@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAAEAV01@PEAVGraphicsSurface@GEL@@@Z; Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>(GEL::GraphicsSurface *)
0x1800824cb  mov     rcx, rdi
0x1800824ce  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800824d3  mov     rcx, rax; this
0x1800824d6  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800824db  lea     rcx, [rbx+0E0h]; this
0x1800824e2  mov     r9b, 1; bool
0x1800824e5  mov     r8, rax; struct Gdiplus::GpGraphics *
0x1800824e8  mov     rdx, [rbx+28h]; struct Frame *
0x1800824ec  call    ?SetGraphics@GDIPlusClipStack@Gfx@@QEAAXPEBVFrame@ITarget@2@AEAVGpGraphics@Gdiplus@@_N@Z; Gfx::GDIPlusClipStack::SetGraphics(Gfx::ITarget::Frame const *,Gdiplus::GpGraphics &,bool)
0x1800824f1  nop
0x1800824f2  mov     rcx, [rsp+28h+arg_0]
0x1800824f7  test    rcx, rcx
0x1800824fa  jz      short loc_180082502
0x1800824fc  call    cs:__imp_GdipDeleteGraphics
0x180082502  mov     rax, [rdi]
0x180082505  mov     rbx, [rsp+28h+arg_10]
0x18008250a  add     rsp, 20h
0x18008250e  pop     rdi
0x18008250f  retn
```
