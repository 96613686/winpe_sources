# GEL::Offscreen::EnsureGraphicsSurface(void)

- ea: `0x18015ab00`
- end: `0x18015aca2`
- name: `?EnsureGraphicsSurface@Offscreen@GEL@@EEAAAEAVGraphicsSurface@2@XZ`
- size: `418`
- prototype: `struct GEL::GraphicsSurface *__fastcall(GEL::Offscreen *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180057e70`
- `0x180072d00`
- `0x18007f754`
- `0x180081c40`
- `0x180082564`
- `0x1800828c8`
- `0x180090490`
- `0x180092a58`
- `0x18015ab00`

## import_xrefs

- `gdiplus!GdipSetPageUnit` at `0x18015ab54`
- `gdiplus!GdipSetPageUnit` at `0x18015ab54`
- `gdiplus!GdipDeleteGraphics` at `0x18015ac5d`
- `gdiplus!GdipDeleteGraphics` at `0x18015ac5d`
- `gdiplus!GdipCreateFromHDC` at `0x18015ab38`
- `gdiplus!GdipCreateFromHDC` at `0x18015ab38`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
struct GEL::GraphicsSurface *__fastcall GEL::Offscreen::EnsureGraphicsSurface(GEL::Offscreen *this)
{
  char *v2; // r14
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // ebx
  int v10; // edi
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  _DWORD *v13; // rsi
  unsigned int v14; // eax
  char *v15; // rdi
  GEL::GraphicsSurface *v16; // rax
  struct Gdiplus::GpGraphics *GpGraphics; // rbx
  const struct Frame *v18; // rax
  __int64 v20; // [rsp+50h] [rbp+8h] BYREF
  _DWORD *v21; // [rsp+58h] [rbp+10h]

  v2 = (char *)this - 24;
  if ( *((_QWORD *)this + 37) )
  {
    v15 = (char *)this + 296;
    return *(struct GEL::GraphicsSurface **)v15;
  }
  v20 = 0;
  v3 = GdipCreateFromHDC(*((_QWORD *)this + 34), &v20);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v3, v4, v5, 38871061);
  v6 = GdipSetPageUnit(v20, 2);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v6, v7, v8, 38871062);
  v9 = *((_DWORD *)this + 71);
  v10 = *((_DWORD *)this + 70);
  v13 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x60, v11, v12);
  v21 = v13;
  if ( v13 )
  {
    v14 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 40LL))(v2);
    v13[2] = 0;
    v13[2] = 0;
    *(_QWORD *)v13 = &GEL::GraphicsSurface::`vftable';
    *((_QWORD *)v13 + 2) = 0;
    *((_QWORD *)v13 + 3) = 0;
    *((_QWORD *)v13 + 4) = 0;
    *((_QWORD *)v13 + 5) = 0;
    *((_QWORD *)v13 + 6) = 0;
    v13[14] = 0;
    *((_QWORD *)v13 + 8) = 0;
    v13[18] = v10;
    v13[19] = v9;
    *((_QWORD *)v13 + 10) = v14;
    *((_WORD *)v13 + 44) = 0;
    if ( v20 )
    {
      if ( v10 <= 0 || v9 <= 0 )
      {
        Ofc::CInvalidParamException::ThrowTag(0x2CA65Du);
        __debugbreak();
      }
      *((_QWORD *)v13 + 4) = v20;
      v20 = 0;
      goto LABEL_7;
    }
    Ofc::CInvalidParamException::ThrowTag(0x2CA65Bu);
  }
  v13 = 0;
LABEL_7:
  v15 = (char *)this + 296;
  Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>((char *)this + 296, v13);
  v16 = (GEL::GraphicsSurface *)Mso::TCntPtr<IWICImagingFactory>::operator->((char *)this + 296);
  GpGraphics = GEL::GraphicsSurface::GetGpGraphics(v16);
  v18 = (const struct Frame *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 256LL))(v2);
  Gfx::GDIPlusClipStack::SetGraphics((GEL::Offscreen *)((char *)this + 224), v18, GpGraphics, 0);
  if ( v20 )
    GdipDeleteGraphics();
  return *(struct GEL::GraphicsSurface **)v15;
}

```

## disassembly

```asm
0x18015ab00  mov     [rsp+arg_10], rbx
0x18015ab05  push    rbp
0x18015ab06  push    rsi
0x18015ab07  push    rdi
0x18015ab08  push    r14
0x18015ab0a  push    r15
0x18015ab0c  sub     rsp, 20h
0x18015ab10  mov     rbp, rcx
0x18015ab13  lea     r14, [rcx-18h]
0x18015ab17  xor     r15d, r15d
0x18015ab1a  cmp     [r14+140h], r15
0x18015ab21  jnz     loc_18015AC77
0x18015ab27  mov     [rsp+48h+arg_0], r15
0x18015ab2c  lea     rdx, [rsp+48h+arg_0]
0x18015ab31  mov     rcx, [rcx+110h]
0x18015ab38  call    cs:__imp_GdipCreateFromHDC
0x18015ab3e  mov     r9d, 2512015h
0x18015ab44  mov     ecx, eax
0x18015ab46  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18015ab4b  lea     edx, [r15+2]
0x18015ab4f  mov     rcx, [rsp+48h+arg_0]
0x18015ab54  call    cs:__imp_GdipSetPageUnit
0x18015ab5a  mov     r9d, 2512016h
0x18015ab60  mov     ecx, eax
0x18015ab62  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18015ab67  mov     ebx, [rbp+11Ch]
0x18015ab6d  mov     edi, [rbp+118h]
0x18015ab73  lea     ecx, [r15+60h]; this
0x18015ab77  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18015ab7c  mov     rsi, rax
0x18015ab7f  mov     [rsp+48h+arg_8], rax
0x18015ab84  test    rax, rax
0x18015ab87  jz      loc_18015AC99
0x18015ab8d  mov     rax, [r14]
0x18015ab90  mov     rcx, r14
0x18015ab93  mov     rax, [rax+28h]
0x18015ab97  call    cs:__guard_dispatch_icall_fptr
0x18015ab9d  xor     ecx, ecx
0x18015ab9f  mov     [rsi+8], ecx
0x18015aba2  mov     [rsi+8], r15d
0x18015aba6  lea     rcx, ??_7GraphicsSurface@GEL@@6B@; const GEL::GraphicsSurface::`vftable'
0x18015abad  mov     [rsi], rcx
0x18015abb0  mov     [rsi+10h], r15
0x18015abb4  mov     [rsi+18h], r15
0x18015abb8  mov     [rsi+20h], r15
0x18015abbc  mov     [rsi+28h], r15
0x18015abc0  mov     [rsi+30h], r15
0x18015abc4  mov     [rsi+38h], r15d
0x18015abc8  mov     [rsi+40h], r15
0x18015abcc  mov     [rsi+48h], edi
0x18015abcf  mov     [rsi+4Ch], ebx
0x18015abd2  mov     [rsi+50h], eax
0x18015abd5  mov     [rsi+54h], r15d
0x18015abd9  mov     [rsi+58h], r15w
0x18015abde  mov     rax, [rsp+48h+arg_0]
0x18015abe3  test    rax, rax
0x18015abe6  jz      loc_18015AC8B
0x18015abec  test    edi, edi
0x18015abee  jle     loc_18015AC80
0x18015abf4  test    ebx, ebx
0x18015abf6  jle     loc_18015AC80
0x18015abfc  mov     [rsi+20h], rax
0x18015ac00  mov     [rsp+48h+arg_0], r15
0x18015ac05  lea     rdi, [rbp+128h]
0x18015ac0c  mov     rdx, rsi
0x18015ac0f  mov     rcx, rdi
0x18015ac12  call    ??$?4VGraphicsSurface@GEL@@X@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAAEAV01@PEAVGraphicsSurface@GEL@@@Z; Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>(GEL::GraphicsSurface *)
0x18015ac17  mov     rcx, rdi
0x18015ac1a  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x18015ac1f  mov     rcx, rax; this
0x18015ac22  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x18015ac27  mov     rbx, rax
0x18015ac2a  mov     rax, [r14]
0x18015ac2d  mov     rcx, r14
0x18015ac30  mov     rax, [rax+100h]
0x18015ac37  call    cs:__guard_dispatch_icall_fptr
0x18015ac3d  lea     rcx, [rbp+0E0h]; this
0x18015ac44  xor     r9d, r9d; bool
0x18015ac47  mov     r8, rbx; struct Gdiplus::GpGraphics *
0x18015ac4a  mov     rdx, rax; struct Frame *
0x18015ac4d  call    ?SetGraphics@GDIPlusClipStack@Gfx@@QEAAXPEBVFrame@ITarget@2@AEAVGpGraphics@Gdiplus@@_N@Z; Gfx::GDIPlusClipStack::SetGraphics(Gfx::ITarget::Frame const *,Gdiplus::GpGraphics &,bool)
0x18015ac52  nop
0x18015ac53  mov     rcx, [rsp+48h+arg_0]
0x18015ac58  test    rcx, rcx
0x18015ac5b  jz      short loc_18015AC63
0x18015ac5d  call    cs:__imp_GdipDeleteGraphics
0x18015ac63  mov     rax, [rdi]
0x18015ac66  mov     rbx, [rsp+48h+arg_10]
0x18015ac6b  add     rsp, 20h
0x18015ac6f  pop     r15
0x18015ac71  pop     r14
0x18015ac73  pop     rdi
0x18015ac74  pop     rsi
0x18015ac75  pop     rbp
0x18015ac76  retn
0x18015ac77  lea     rdi, [rcx+128h]
0x18015ac7e  jmp     short loc_18015AC63
0x18015ac80  mov     ecx, 2CA65Dh; unsigned int
0x18015ac85  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18015ac8a  int     3; Trap to Debugger
0x18015ac8b  mov     ecx, 2CA65Bh; unsigned int
0x18015ac90  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18015ac95  nop
0x18015ac96  jmp     short $+2
0x18015ac98  nop
0x18015ac99  mov     rsi, r15
0x18015ac9c  jmp     loc_18015AC05
```
