# GEL::Offscreen::EnsureGraphicsSurface(void)

- ea: `0x1801591a0`
- end: `0x180159342`
- name: `?EnsureGraphicsSurface@Offscreen@GEL@@EEAAAEAVGraphicsSurface@2@XZ`
- size: `418`
- prototype: `struct GEL::GraphicsSurface *__fastcall(GEL::Offscreen *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800573f0`
- `0x180062394`
- `0x180064854`
- `0x180064bb8`
- `0x180064e30`
- `0x1800650d8`
- `0x1800786fc`
- `0x1800dc27c`
- `0x1801591a0`

## import_xrefs

- `gdiplus!GdipSetPageUnit` at `0x1801591f4`
- `gdiplus!GdipSetPageUnit` at `0x1801591f4`
- `gdiplus!GdipDeleteGraphics` at `0x1801592fd`
- `gdiplus!GdipDeleteGraphics` at `0x1801592fd`
- `gdiplus!GdipCreateFromHDC` at `0x1801591d8`
- `gdiplus!GdipCreateFromHDC` at `0x1801591d8`

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
0x1801591a0  mov     [rsp+arg_10], rbx
0x1801591a5  push    rbp
0x1801591a6  push    rsi
0x1801591a7  push    rdi
0x1801591a8  push    r14
0x1801591aa  push    r15
0x1801591ac  sub     rsp, 20h
0x1801591b0  mov     rbp, rcx
0x1801591b3  lea     r14, [rcx-18h]
0x1801591b7  xor     r15d, r15d
0x1801591ba  cmp     [r14+140h], r15
0x1801591c1  jnz     loc_180159317
0x1801591c7  mov     [rsp+48h+arg_0], r15
0x1801591cc  lea     rdx, [rsp+48h+arg_0]
0x1801591d1  mov     rcx, [rcx+110h]
0x1801591d8  call    cs:__imp_GdipCreateFromHDC
0x1801591de  mov     r9d, 2512015h
0x1801591e4  mov     ecx, eax
0x1801591e6  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801591eb  lea     edx, [r15+2]
0x1801591ef  mov     rcx, [rsp+48h+arg_0]
0x1801591f4  call    cs:__imp_GdipSetPageUnit
0x1801591fa  mov     r9d, 2512016h
0x180159200  mov     ecx, eax
0x180159202  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180159207  mov     ebx, [rbp+11Ch]
0x18015920d  mov     edi, [rbp+118h]
0x180159213  lea     ecx, [r15+60h]; this
0x180159217  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18015921c  mov     rsi, rax
0x18015921f  mov     [rsp+48h+arg_8], rax
0x180159224  test    rax, rax
0x180159227  jz      loc_180159339
0x18015922d  mov     rax, [r14]
0x180159230  mov     rcx, r14
0x180159233  mov     rax, [rax+28h]
0x180159237  call    cs:__guard_dispatch_icall_fptr
0x18015923d  xor     ecx, ecx
0x18015923f  mov     [rsi+8], ecx
0x180159242  mov     [rsi+8], r15d
0x180159246  lea     rcx, ??_7GraphicsSurface@GEL@@6B@; const GEL::GraphicsSurface::`vftable'
0x18015924d  mov     [rsi], rcx
0x180159250  mov     [rsi+10h], r15
0x180159254  mov     [rsi+18h], r15
0x180159258  mov     [rsi+20h], r15
0x18015925c  mov     [rsi+28h], r15
0x180159260  mov     [rsi+30h], r15
0x180159264  mov     [rsi+38h], r15d
0x180159268  mov     [rsi+40h], r15
0x18015926c  mov     [rsi+48h], edi
0x18015926f  mov     [rsi+4Ch], ebx
0x180159272  mov     [rsi+50h], eax
0x180159275  mov     [rsi+54h], r15d
0x180159279  mov     [rsi+58h], r15w
0x18015927e  mov     rax, [rsp+48h+arg_0]
0x180159283  test    rax, rax
0x180159286  jz      loc_18015932B
0x18015928c  test    edi, edi
0x18015928e  jle     loc_180159320
0x180159294  test    ebx, ebx
0x180159296  jle     loc_180159320
0x18015929c  mov     [rsi+20h], rax
0x1801592a0  mov     [rsp+48h+arg_0], r15
0x1801592a5  lea     rdi, [rbp+128h]
0x1801592ac  mov     rdx, rsi
0x1801592af  mov     rcx, rdi
0x1801592b2  call    ??$?4VGraphicsSurface@GEL@@X@?$TCntPtr@VGraphicsSurface@GEL@@@Mso@@QEAAAEAV01@PEAVGraphicsSurface@GEL@@@Z; Mso::TCntPtr<GEL::GraphicsSurface>::operator=<GEL::GraphicsSurface,void>(GEL::GraphicsSurface *)
0x1801592b7  mov     rcx, rdi
0x1801592ba  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x1801592bf  mov     rcx, rax; this
0x1801592c2  call    ?GetGpGraphics@GraphicsSurface@GEL@@QEAAAEAVGpGraphics@Gdiplus@@XZ; GEL::GraphicsSurface::GetGpGraphics(void)
0x1801592c7  mov     rbx, rax
0x1801592ca  mov     rax, [r14]
0x1801592cd  mov     rcx, r14
0x1801592d0  mov     rax, [rax+100h]
0x1801592d7  call    cs:__guard_dispatch_icall_fptr
0x1801592dd  lea     rcx, [rbp+0E0h]; this
0x1801592e4  xor     r9d, r9d; bool
0x1801592e7  mov     r8, rbx; struct Gdiplus::GpGraphics *
0x1801592ea  mov     rdx, rax; struct Frame *
0x1801592ed  call    ?SetGraphics@GDIPlusClipStack@Gfx@@QEAAXPEBVFrame@ITarget@2@AEAVGpGraphics@Gdiplus@@_N@Z; Gfx::GDIPlusClipStack::SetGraphics(Gfx::ITarget::Frame const *,Gdiplus::GpGraphics &,bool)
0x1801592f2  nop
0x1801592f3  mov     rcx, [rsp+48h+arg_0]
0x1801592f8  test    rcx, rcx
0x1801592fb  jz      short loc_180159303
0x1801592fd  call    cs:__imp_GdipDeleteGraphics
0x180159303  mov     rax, [rdi]
0x180159306  mov     rbx, [rsp+48h+arg_10]
0x18015930b  add     rsp, 20h
0x18015930f  pop     r15
0x180159311  pop     r14
0x180159313  pop     rdi
0x180159314  pop     rsi
0x180159315  pop     rbp
0x180159316  retn
0x180159317  lea     rdi, [rcx+128h]
0x18015931e  jmp     short loc_180159303
0x180159320  mov     ecx, 2CA65Dh; unsigned int
0x180159325  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18015932a  int     3; Trap to Debugger
0x18015932b  mov     ecx, 2CA65Bh; unsigned int
0x180159330  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x180159335  nop
0x180159336  jmp     short $+2
0x180159338  nop
0x180159339  mov     rsi, r15
0x18015933c  jmp     loc_1801592A5
```
