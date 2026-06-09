# Gfx::GDITargetBase::GetGraphics(void)

- ea: `0x180061368`
- end: `0x180061479`
- name: `?GetGraphics@GDITargetBase@Gfx@@AEAAAEAVGpGraphics@Gdiplus@@XZ`
- size: `273`
- prototype: `struct Gdiplus::GpGraphics *__fastcall(Gfx::GDITargetBase *__hidden this)`
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x180060a90`
- `0x1800c5354`
- `0x18016a970`
- `0x1801f6820`
- `0x1801f68c4`

## callees

- `0x18005f898`
- `0x180061368`
- `0x180061f98`
- `0x180062394`
- `0x1800627e4`
- `0x1800628bc`
- `0x1800650d8`
- `0x180076dfc`

## import_xrefs

- `gdiplus!GdipSetWorldTransform` at `0x18006142c`
- `gdiplus!GdipSetWorldTransform` at `0x18006142c`
- `gdiplus!GdipDeleteMatrix` at `0x18006144a`
- `gdiplus!GdipDeleteMatrix` at `0x18006144a`
- `gdiplus!GdipSetPageUnit` at `0x1800613e9`
- `gdiplus!GdipSetPageUnit` at `0x1800613e9`
- `gdiplus!GdipSetPixelOffsetMode` at `0x180061404`
- `gdiplus!GdipSetPixelOffsetMode` at `0x180061404`
- `gdiplus!GdipCreateFromHDC` at `0x1800613ce`
- `gdiplus!GdipCreateFromHDC` at `0x1800613ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Gdiplus::GpGraphics *__fastcall Gfx::GDITargetBase::GetGraphics(Gfx::GDITargetBase *this)
{
  struct Gdiplus::GpGraphics **v2; // rdi
  const struct Frame *v4; // rsi
  __int64 v5; // rax
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  _QWORD *v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // [rsp+30h] [rbp+8h] BYREF

  Gfx::GDITargetBase::FinishArc2DRendering(this);
  v2 = (struct Gdiplus::GpGraphics **)((char *)this + 160);
  if ( !*((_QWORD *)this + 20) )
  {
    if ( !*((_QWORD *)this + 21) )
    {
      Ofc::CInvalidOperationException::ThrowTag(0x356842u);
      __debugbreak();
    }
    v4 = (const struct Frame *)*((_QWORD *)this + 2);
    Gfx::GDITargetBase::FinishGDIRendering(this, v4);
    v5 = ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&((char *)this + 160);
    v6 = GdipCreateFromHDC(*((_QWORD *)this + 21), v5);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v6, v7, v8, 38322707);
    v9 = GdipSetPageUnit(*v2, 2);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v9, v10, v11, 508852130);
    v12 = GdipSetPixelOffsetMode(*v2, 4);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v12, v13, v14, 507053603);
    v15 = (_QWORD *)Gfx::GpMatrixHolder::GpMatrixHolder(&v19, &v4[12]);
    v16 = GdipSetWorldTransform(*v2, *v15);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v16, v17, v18, 38901331);
    if ( v19 )
      GdipDeleteMatrix(v19);
    Gfx::GDIPlusClipStack::SetGraphics((Gfx::GDITargetBase *)((char *)this + 176), v4, *v2, *((_BYTE *)this + 224));
  }
  return *v2;
}

```

## disassembly

```asm
0x180061368  mov     [rsp+arg_8], rbx
0x18006136d  mov     [rsp+arg_10], rsi
0x180061372  push    rdi
0x180061373  sub     rsp, 20h
0x180061377  mov     rbx, rcx
0x18006137a  call    ?FinishArc2DRendering@GDITargetBase@Gfx@@AEAAXXZ; Gfx::GDITargetBase::FinishArc2DRendering(void)
0x18006137f  lea     rdi, [rbx+0A0h]
0x180061386  cmp     qword ptr [rdi], 0
0x18006138a  jz      short loc_18006139F
0x18006138c  mov     rax, [rdi]
0x18006138f  mov     rbx, [rsp+28h+arg_8]
0x180061394  mov     rsi, [rsp+28h+arg_10]
0x180061399  add     rsp, 20h
0x18006139d  pop     rdi
0x18006139e  retn
0x18006139f  cmp     qword ptr [rbx+0A8h], 0
0x1800613a7  jz      loc_18006146E
0x1800613ad  mov     rsi, [rbx+10h]
0x1800613b1  mov     rdx, rsi; struct Frame *
0x1800613b4  mov     rcx, rbx; this
0x1800613b7  call    ?FinishGDIRendering@GDITargetBase@Gfx@@AEAAXAEBVFrame@ITarget@2@@Z; Gfx::GDITargetBase::FinishGDIRendering(Gfx::ITarget::Frame const &)
0x1800613bc  mov     rcx, rdi
0x1800613bf  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x1800613c4  mov     rdx, rax
0x1800613c7  mov     rcx, [rbx+0A8h]
0x1800613ce  call    cs:__imp_GdipCreateFromHDC
0x1800613d4  mov     r9d, 248C213h
0x1800613da  mov     ecx, eax
0x1800613dc  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800613e1  mov     edx, 2
0x1800613e6  mov     rcx, [rdi]
0x1800613e9  call    cs:__imp_GdipSetPageUnit
0x1800613ef  mov     r9d, 1E5477A2h
0x1800613f5  mov     ecx, eax
0x1800613f7  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800613fc  mov     edx, 4
0x180061401  mov     rcx, [rdi]
0x180061404  call    cs:__imp_GdipSetPixelOffsetMode
0x18006140a  mov     r9d, 1E390623h
0x180061410  mov     ecx, eax
0x180061412  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180061417  lea     rdx, [rsi+60h]
0x18006141b  lea     rcx, [rsp+28h+arg_0]
0x180061420  call    ??$?0U?$TAffine3x3@N@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::TAffine3x3<double> const &)
0x180061425  nop
0x180061426  mov     rdx, [rax]
0x180061429  mov     rcx, [rdi]
0x18006142c  call    cs:__imp_GdipSetWorldTransform
0x180061432  mov     r9d, 2519653h
0x180061438  mov     ecx, eax
0x18006143a  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006143f  nop
0x180061440  mov     rcx, [rsp+28h+arg_0]
0x180061445  test    rcx, rcx
0x180061448  jz      short loc_180061450
0x18006144a  call    cs:__imp_GdipDeleteMatrix
0x180061450  lea     rcx, [rbx+0B0h]; this
0x180061457  mov     r9b, [rbx+0E0h]; bool
0x18006145e  mov     r8, [rdi]; struct Gdiplus::GpGraphics *
0x180061461  mov     rdx, rsi; struct Frame *
0x180061464  call    ?SetGraphics@GDIPlusClipStack@Gfx@@QEAAXPEBVFrame@ITarget@2@AEAVGpGraphics@Gdiplus@@_N@Z; Gfx::GDIPlusClipStack::SetGraphics(Gfx::ITarget::Frame const *,Gdiplus::GpGraphics &,bool)
0x180061469  jmp     loc_18006138C
0x18006146e  mov     ecx, 356842h; unsigned int
0x180061473  call    ?ThrowTag@CInvalidOperationException@Ofc@@SAXK@Z; Ofc::CInvalidOperationException::ThrowTag(ulong)
0x180061478  int     3; Trap to Debugger
```
