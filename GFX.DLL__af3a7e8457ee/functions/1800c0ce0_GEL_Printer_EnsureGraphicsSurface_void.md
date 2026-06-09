# GEL::Printer::EnsureGraphicsSurface(void)

- ea: `0x1800c0ce0`
- end: `0x1800c0e2b`
- name: `?EnsureGraphicsSurface@Printer@GEL@@MEAAAEAVGraphicsSurface@2@XZ`
- size: `331`
- prototype: `struct GEL::GraphicsSurface *__fastcall(GEL::Printer *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800c0ca0`
- `0x1801fac60`

## callees

- `0x1800573f0`
- `0x180062394`
- `0x180064854`
- `0x180064bb8`
- `0x180064e30`
- `0x1800786fc`
- `0x1800c0ce0`
- `0x1800c2420`
- `0x18014284c`

## import_xrefs

- `gdiplus!GdipSetPageUnit` at `0x1800c0d41`
- `gdiplus!GdipSetPageUnit` at `0x1800c0d41`
- `gdiplus!GdipDeleteGraphics` at `0x1800c0e11`
- `gdiplus!GdipDeleteGraphics` at `0x1800c0e11`
- `gdiplus!GdipCreateFromHDC` at `0x1800c0d21`
- `gdiplus!GdipCreateFromHDC` at `0x1800c0d21`

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
0x1800c0ce0  mov     [rsp+arg_10], rbx
0x1800c0ce5  push    rsi
0x1800c0ce6  push    rdi
0x1800c0ce7  push    r14
0x1800c0ce9  sub     rsp, 60h
0x1800c0ced  mov     rdi, rcx
0x1800c0cf0  cmp     qword ptr [rcx+120h], 0
0x1800c0cf8  jz      short loc_1800C0D06
0x1800c0cfa  lea     rsi, [rcx+120h]
0x1800c0d01  jmp     loc_1800C0E17
0x1800c0d06  mov     [rsp+78h+arg_0], 0
0x1800c0d12  lea     rdx, [rsp+78h+arg_0]
0x1800c0d1a  mov     rcx, [rcx+100h]
0x1800c0d21  call    cs:__imp_GdipCreateFromHDC
0x1800c0d27  mov     r9d, 25118A3h
0x1800c0d2d  mov     ecx, eax
0x1800c0d2f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c0d34  mov     edx, 2
0x1800c0d39  mov     rcx, [rsp+78h+arg_0]
0x1800c0d41  call    cs:__imp_GdipSetPageUnit
0x1800c0d47  mov     r9d, 25118C0h
0x1800c0d4d  mov     ecx, eax
0x1800c0d4f  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c0d54  mov     ecx, 60h ; '`'; this
0x1800c0d59  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800c0d5e  mov     [rsp+78h+arg_8], rax
0x1800c0d66  test    rax, rax
0x1800c0d69  jz      short loc_1800C0D89
0x1800c0d6b  lea     r8, [rdi+13Ch]
0x1800c0d72  mov     r9d, 3
0x1800c0d78  lea     rdx, [rsp+78h+arg_0]
0x1800c0d80  mov     rcx, rax
0x1800c0d83  call    ??0GraphicsSurface@GEL@@QEAA@AEAV?$TGpHolder@VGpGraphics@Gdiplus@@@GDIPlus@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@W4AlphaMode@4@@Z; GEL::GraphicsSurface::GraphicsSurface(ARC::GDIPlus::TGpHolder<Gdiplus::GpGraphics> &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,ARC::AlphaMode)
0x1800c0d88  nop
0x1800c0d89  lea     rsi, [rdi+120h]
0x1800c0d90  mov     rdx, rax
0x1800c0d93  mov     rcx, rsi
0x1800c0d96  call    ??$?4VGraphicsSurface@GEL@@X@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAAEAV01@PEAVGraphicsSurface@GEL@@@Z; Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>(GEL::GraphicsSurface *)
0x1800c0d9b  movdqa  xmm0, cs:__xmm@00000000000000003ff0000000000000
0x1800c0da3  movups  [rsp+78h+var_48], xmm0
0x1800c0da8  movdqa  xmm1, cs:__xmm@3ff00000000000000000000000000000
0x1800c0db0  movups  [rsp+78h+var_38], xmm1
0x1800c0db5  xorps   xmm0, xmm0
0x1800c0db8  movups  [rsp+78h+var_28], xmm0
0x1800c0dbd  mov     rcx, rsi
0x1800c0dc0  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1800c0dc5  mov     rcx, rax; this
0x1800c0dc8  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1800c0dcd  mov     rbx, rax
0x1800c0dd0  mov     rax, [rdi-18h]
0x1800c0dd4  lea     rcx, [rdi-18h]
0x1800c0dd8  mov     rax, [rax+100h]
0x1800c0ddf  call    cs:__guard_dispatch_icall_fptr
0x1800c0de5  lea     rcx, [rdi+0E0h]
0x1800c0dec  lea     rdx, [rsp+78h+var_48]
0x1800c0df1  mov     [rsp+78h+var_58], rdx
0x1800c0df6  mov     r9, rbx
0x1800c0df9  mov     r8, rax
0x1800c0dfc  xor     edx, edx
0x1800c0dfe  call    ?SetGraphics@PrinterClipStack@GEL@@QEAAXW4SurfaceType@12@PEBVFrame@ITarget@Gfx@@AEAVGpGraphics@Gdiplus@@AEBU?$TAffine3x3@N@Math@@_N@Z; GEL::PrinterClipStack::SetGraphics(GEL::PrinterClipStack::SurfaceType,Gfx::ITarget::Frame const *,Gdiplus::GpGraphics &,Math::TAffine3x3<double> const &,bool)
0x1800c0e03  nop
0x1800c0e04  mov     rcx, [rsp+78h+arg_0]
0x1800c0e0c  test    rcx, rcx
0x1800c0e0f  jz      short loc_1800C0E17
0x1800c0e11  call    cs:__imp_GdipDeleteGraphics
0x1800c0e17  mov     rax, [rsi]
0x1800c0e1a  mov     rbx, [rsp+78h+arg_10]
0x1800c0e22  add     rsp, 60h
0x1800c0e26  pop     r14
0x1800c0e28  pop     rdi
0x1800c0e29  pop     rsi
0x1800c0e2a  retn
```
