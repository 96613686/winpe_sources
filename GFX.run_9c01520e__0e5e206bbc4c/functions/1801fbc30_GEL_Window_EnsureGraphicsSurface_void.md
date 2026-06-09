# GEL::Window::EnsureGraphicsSurface(void)

- ea: `0x1801fbc30`
- end: `0x1801fbd55`
- name: `?EnsureGraphicsSurface@Window@GEL@@EEAAAEAVGraphicsSurface@2@XZ`
- size: `293`
- prototype: `struct GEL::GraphicsSurface *__fastcall(GEL::Window *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180057e70`
- `0x180072d00`
- `0x18007f754`
- `0x180081c40`
- `0x180082564`
- `0x1800828c8`
- `0x180082fdc`
- `0x180092a58`
- `0x1801fb7b0`
- `0x1801fbc30`

## import_xrefs

- `gdiplus!GdipCreateFromHWND` at `0x1801fbc77`
- `gdiplus!GdipCreateFromHWND` at `0x1801fbc77`
- `gdiplus!GdipSetPageUnit` at `0x1801fbc94`
- `gdiplus!GdipSetPageUnit` at `0x1801fbc94`
- `gdiplus!GdipDeleteGraphics` at `0x1801fbd3e`
- `gdiplus!GdipDeleteGraphics` at `0x1801fbd3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct GEL::GraphicsSurface *__fastcall GEL::Window::EnsureGraphicsSurface(GEL::Window *this)
{
  char *v2; // r14
  char *v3; // rdi
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned __int64 v10; // rdx
  unsigned int v11; // r8d
  void *v12; // rax
  void *v13; // rbx
  unsigned int v14; // eax
  GEL::GraphicsSurface *v15; // rax
  struct Gdiplus::GpGraphics *GpGraphics; // rbx
  const struct Frame *v17; // rax
  __int64 v19; // [rsp+40h] [rbp+8h] BYREF
  void *v20; // [rsp+48h] [rbp+10h]

  v2 = (char *)this - 24;
  if ( *((_QWORD *)this + 36) )
  {
    v3 = (char *)this + 288;
  }
  else
  {
    GEL::Window::DeleteWindowDC((GEL::Window *)((char *)this - 24));
    v19 = 0;
    v4 = GdipCreateFromHWND(*((_QWORD *)this + 33), &v19);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v4, v5, v6, 38871044);
    v7 = GdipSetPageUnit(v19, 2);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v7, v8, v9, 38871045);
    v12 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x60, v10, v11);
    v13 = v12;
    v20 = v12;
    if ( v12 )
    {
      v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 40LL))(v2);
      v12 = (void *)GEL::GraphicsSurface::GraphicsSurface(v13, &v19, (char *)this + 272, v14);
    }
    v3 = (char *)this + 288;
    Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>((char *)this + 288, v12);
    v15 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->((char *)this + 288);
    GpGraphics = GEL::GraphicsSurface::GetGpGraphics(v15);
    v17 = (const struct Frame *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 256LL))(v2);
    Gfx::GDIPlusClipStack::SetGraphics((GEL::Window *)((char *)this + 224), v17, GpGraphics, 0);
    if ( v19 )
      GdipDeleteGraphics();
  }
  return *(struct GEL::GraphicsSurface **)v3;
}

```

## disassembly

```asm
0x1801fbc30  mov     [rsp+arg_10], rbx
0x1801fbc35  push    rsi
0x1801fbc36  push    rdi
0x1801fbc37  push    r14
0x1801fbc39  sub     rsp, 20h
0x1801fbc3d  mov     rsi, rcx
0x1801fbc40  lea     r14, [rcx-18h]
0x1801fbc44  cmp     qword ptr [r14+138h], 0
0x1801fbc4c  jz      short loc_1801FBC5A
0x1801fbc4e  lea     rdi, [rcx+120h]
0x1801fbc55  jmp     loc_1801FBD44
0x1801fbc5a  mov     rcx, r14; this
0x1801fbc5d  call    ?DeleteWindowDC@Window@GEL@@AEAAXXZ; GEL::Window::DeleteWindowDC(void)
0x1801fbc62  mov     [rsp+38h+arg_0], 0
0x1801fbc6b  lea     rdx, [rsp+38h+arg_0]
0x1801fbc70  mov     rcx, [rsi+108h]
0x1801fbc77  call    cs:__imp_GdipCreateFromHWND
0x1801fbc7d  mov     r9d, 2512004h
0x1801fbc83  mov     ecx, eax
0x1801fbc85  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801fbc8a  mov     edx, 2
0x1801fbc8f  mov     rcx, [rsp+38h+arg_0]
0x1801fbc94  call    cs:__imp_GdipSetPageUnit
0x1801fbc9a  mov     r9d, 2512005h
0x1801fbca0  mov     ecx, eax
0x1801fbca2  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801fbca7  mov     ecx, 60h ; '`'; this
0x1801fbcac  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801fbcb1  mov     rbx, rax
0x1801fbcb4  mov     [rsp+38h+arg_8], rax
0x1801fbcb9  test    rax, rax
0x1801fbcbc  jz      short loc_1801FBCE6
0x1801fbcbe  mov     rax, [r14]
0x1801fbcc1  mov     rcx, r14
0x1801fbcc4  mov     rax, [rax+28h]
0x1801fbcc8  call    cs:__guard_dispatch_icall_fptr
0x1801fbcce  lea     r8, [rsi+110h]
0x1801fbcd5  mov     r9d, eax
0x1801fbcd8  lea     rdx, [rsp+38h+arg_0]
0x1801fbcdd  mov     rcx, rbx
0x1801fbce0  call    ??0GraphicsSurface@GEL@@QEAA@AEAV?$TGpHolder@VGpGraphics@Gdiplus@@@GDIPlus@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@W4AlphaMode@4@@Z; GEL::GraphicsSurface::GraphicsSurface(ARC::GDIPlus::TGpHolder<Gdiplus::GpGraphics> &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,ARC::AlphaMode)
0x1801fbce5  nop
0x1801fbce6  lea     rdi, [rsi+120h]
0x1801fbced  mov     rdx, rax
0x1801fbcf0  mov     rcx, rdi
0x1801fbcf3  call    ??$?4VGraphicsSurface@GEL@@X@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAAEAV01@PEAVGraphicsSurface@GEL@@@Z; Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>(GEL::GraphicsSurface *)
0x1801fbcf8  mov     rcx, rdi
0x1801fbcfb  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1801fbd00  mov     rcx, rax; this
0x1801fbd03  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1801fbd08  mov     rbx, rax
0x1801fbd0b  mov     rax, [r14]
0x1801fbd0e  mov     rcx, r14
0x1801fbd11  mov     rax, [rax+100h]
0x1801fbd18  call    cs:__guard_dispatch_icall_fptr
0x1801fbd1e  lea     rcx, [rsi+0E0h]; this
0x1801fbd25  xor     r9d, r9d; bool
0x1801fbd28  mov     r8, rbx; struct Gdiplus::GpGraphics *
0x1801fbd2b  mov     rdx, rax; struct Frame *
0x1801fbd2e  call    ?SetGraphics@GDIPlusClipStack@Gfx@@QEAAXPEBVFrame@ITarget@2@AEAVGpGraphics@Gdiplus@@_N@Z; Gfx::GDIPlusClipStack::SetGraphics(Gfx::ITarget::Frame const *,Gdiplus::GpGraphics &,bool)
0x1801fbd33  nop
0x1801fbd34  mov     rcx, [rsp+38h+arg_0]
0x1801fbd39  test    rcx, rcx
0x1801fbd3c  jz      short loc_1801FBD44
0x1801fbd3e  call    cs:__imp_GdipDeleteGraphics
0x1801fbd44  mov     rax, [rdi]
0x1801fbd47  mov     rbx, [rsp+38h+arg_10]
0x1801fbd4c  add     rsp, 20h
0x1801fbd50  pop     r14
0x1801fbd52  pop     rdi
0x1801fbd53  pop     rsi
0x1801fbd54  retn
```
