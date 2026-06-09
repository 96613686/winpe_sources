# GEL::Window::EnsureGraphicsSurface(void)

- ea: `0x1801f8820`
- end: `0x1801f8945`
- name: `?EnsureGraphicsSurface@Window@GEL@@EEAAAEAVGraphicsSurface@2@XZ`
- size: `293`
- prototype: `struct GEL::GraphicsSurface *__fastcall(GEL::Window *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x1800573f0`
- `0x180062394`
- `0x180064854`
- `0x180064bb8`
- `0x180064e30`
- `0x1800650d8`
- `0x1800786fc`
- `0x18014284c`
- `0x1801f83a0`
- `0x1801f8820`

## import_xrefs

- `gdiplus!GdipCreateFromHWND` at `0x1801f8867`
- `gdiplus!GdipCreateFromHWND` at `0x1801f8867`
- `gdiplus!GdipSetPageUnit` at `0x1801f8884`
- `gdiplus!GdipSetPageUnit` at `0x1801f8884`
- `gdiplus!GdipDeleteGraphics` at `0x1801f892e`
- `gdiplus!GdipDeleteGraphics` at `0x1801f892e`

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
0x1801f8820  mov     [rsp+arg_10], rbx
0x1801f8825  push    rsi
0x1801f8826  push    rdi
0x1801f8827  push    r14
0x1801f8829  sub     rsp, 20h
0x1801f882d  mov     rsi, rcx
0x1801f8830  lea     r14, [rcx-18h]
0x1801f8834  cmp     qword ptr [r14+138h], 0
0x1801f883c  jz      short loc_1801F884A
0x1801f883e  lea     rdi, [rcx+120h]
0x1801f8845  jmp     loc_1801F8934
0x1801f884a  mov     rcx, r14; this
0x1801f884d  call    ?DeleteWindowDC@Window@GEL@@AEAAXXZ; GEL::Window::DeleteWindowDC(void)
0x1801f8852  mov     [rsp+38h+arg_0], 0
0x1801f885b  lea     rdx, [rsp+38h+arg_0]
0x1801f8860  mov     rcx, [rsi+108h]
0x1801f8867  call    cs:__imp_GdipCreateFromHWND
0x1801f886d  mov     r9d, 2512004h
0x1801f8873  mov     ecx, eax
0x1801f8875  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801f887a  mov     edx, 2
0x1801f887f  mov     rcx, [rsp+38h+arg_0]
0x1801f8884  call    cs:__imp_GdipSetPageUnit
0x1801f888a  mov     r9d, 2512005h
0x1801f8890  mov     ecx, eax
0x1801f8892  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801f8897  mov     ecx, 60h ; '`'; this
0x1801f889c  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801f88a1  mov     rbx, rax
0x1801f88a4  mov     [rsp+38h+arg_8], rax
0x1801f88a9  test    rax, rax
0x1801f88ac  jz      short loc_1801F88D6
0x1801f88ae  mov     rax, [r14]
0x1801f88b1  mov     rcx, r14
0x1801f88b4  mov     rax, [rax+28h]
0x1801f88b8  call    cs:__guard_dispatch_icall_fptr
0x1801f88be  lea     r8, [rsi+110h]
0x1801f88c5  mov     r9d, eax
0x1801f88c8  lea     rdx, [rsp+38h+arg_0]
0x1801f88cd  mov     rcx, rbx
0x1801f88d0  call    ??0GraphicsSurface@GEL@@QEAA@AEAV?$TGpHolder@VGpGraphics@Gdiplus@@@GDIPlus@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@W4AlphaMode@4@@Z; GEL::GraphicsSurface::GraphicsSurface(ARC::GDIPlus::TGpHolder<Gdiplus::GpGraphics> &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,ARC::AlphaMode)
0x1801f88d5  nop
0x1801f88d6  lea     rdi, [rsi+120h]
0x1801f88dd  mov     rdx, rax
0x1801f88e0  mov     rcx, rdi
0x1801f88e3  call    ??$?4VGraphicsSurface@GEL@@X@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAAEAV01@PEAVGraphicsSurface@GEL@@@Z; Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>(GEL::GraphicsSurface *)
0x1801f88e8  mov     rcx, rdi
0x1801f88eb  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1801f88f0  mov     rcx, rax; this
0x1801f88f3  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1801f88f8  mov     rbx, rax
0x1801f88fb  mov     rax, [r14]
0x1801f88fe  mov     rcx, r14
0x1801f8901  mov     rax, [rax+100h]
0x1801f8908  call    cs:__guard_dispatch_icall_fptr
0x1801f890e  lea     rcx, [rsi+0E0h]; this
0x1801f8915  xor     r9d, r9d; bool
0x1801f8918  mov     r8, rbx; struct Gdiplus::GpGraphics *
0x1801f891b  mov     rdx, rax; struct Frame *
0x1801f891e  call    ?SetGraphics@GDIPlusClipStack@Gfx@@QEAAXPEBVFrame@ITarget@2@AEAVGpGraphics@Gdiplus@@_N@Z; Gfx::GDIPlusClipStack::SetGraphics(Gfx::ITarget::Frame const *,Gdiplus::GpGraphics &,bool)
0x1801f8923  nop
0x1801f8924  mov     rcx, [rsp+38h+arg_0]
0x1801f8929  test    rcx, rcx
0x1801f892c  jz      short loc_1801F8934
0x1801f892e  call    cs:__imp_GdipDeleteGraphics
0x1801f8934  mov     rax, [rdi]
0x1801f8937  mov     rbx, [rsp+38h+arg_10]
0x1801f893c  add     rsp, 20h
0x1801f8940  pop     r14
0x1801f8942  pop     rdi
0x1801f8943  pop     rsi
0x1801f8944  retn
```
