# Gfx::GDITargetBase::GetGraphics(void)

- ea: `0x180080738`
- end: `0x180080849`
- name: `?GetGraphics@GDITargetBase@Gfx@@AEAAAEAVGpGraphics@Gdiplus@@XZ`
- size: `273`
- prototype: `struct Gdiplus::GpGraphics *__fastcall(Gfx::GDITargetBase *__hidden this)`
- caller_count: `5`
- callee_count: `8`
- tags: ``

## callers

- `0x180081060`
- `0x1800ca654`
- `0x18016f540`
- `0x1801f9c30`
- `0x1801f9cd4`

## callees

- `0x18007376c`
- `0x18007f348`
- `0x18007f754`
- `0x18007fc0c`
- `0x180080738`
- `0x180081290`
- `0x180081368`
- `0x180081c40`

## import_xrefs

- `gdiplus!GdipSetWorldTransform` at `0x1800807fc`
- `gdiplus!GdipSetWorldTransform` at `0x1800807fc`
- `gdiplus!GdipDeleteMatrix` at `0x18008081a`
- `gdiplus!GdipDeleteMatrix` at `0x18008081a`
- `gdiplus!GdipSetPageUnit` at `0x1800807b9`
- `gdiplus!GdipSetPageUnit` at `0x1800807b9`
- `gdiplus!GdipSetPixelOffsetMode` at `0x1800807d4`
- `gdiplus!GdipSetPixelOffsetMode` at `0x1800807d4`
- `gdiplus!GdipCreateFromHDC` at `0x18008079e`
- `gdiplus!GdipCreateFromHDC` at `0x18008079e`

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
    v5 = ARC::GDIPlus::TGpHolder<Gdiplus::GpPath>::operator&((char *)this + 160);
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
0x180080738  mov     [rsp+arg_8], rbx
0x18008073d  mov     [rsp+arg_10], rsi
0x180080742  push    rdi
0x180080743  sub     rsp, 20h
0x180080747  mov     rbx, rcx
0x18008074a  call    ?FinishArc2DRendering@GDITargetBase@Gfx@@AEAAXXZ; Gfx::GDITargetBase::FinishArc2DRendering(void)
0x18008074f  lea     rdi, [rbx+0A0h]
0x180080756  cmp     qword ptr [rdi], 0
0x18008075a  jz      short loc_18008076F
0x18008075c  mov     rax, [rdi]
0x18008075f  mov     rbx, [rsp+28h+arg_8]
0x180080764  mov     rsi, [rsp+28h+arg_10]
0x180080769  add     rsp, 20h
0x18008076d  pop     rdi
0x18008076e  retn
0x18008076f  cmp     qword ptr [rbx+0A8h], 0
0x180080777  jz      loc_18008083E
0x18008077d  mov     rsi, [rbx+10h]
0x180080781  mov     rdx, rsi; struct Frame *
0x180080784  mov     rcx, rbx; this
0x180080787  call    ?FinishGDIRendering@GDITargetBase@Gfx@@AEAAXAEBVFrame@ITarget@2@@Z; Gfx::GDITargetBase::FinishGDIRendering(Gfx::ITarget::Frame const &)
0x18008078c  mov     rcx, rdi
0x18008078f  call    ??I?$TGpHolder@VGpPath@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVGpPath@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpPath>::operator&(void)
0x180080794  mov     rdx, rax
0x180080797  mov     rcx, [rbx+0A8h]
0x18008079e  call    cs:__imp_GdipCreateFromHDC
0x1800807a4  mov     r9d, 248C213h
0x1800807aa  mov     ecx, eax
0x1800807ac  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800807b1  mov     edx, 2
0x1800807b6  mov     rcx, [rdi]
0x1800807b9  call    cs:__imp_GdipSetPageUnit
0x1800807bf  mov     r9d, 1E5477A2h
0x1800807c5  mov     ecx, eax
0x1800807c7  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800807cc  mov     edx, 4
0x1800807d1  mov     rcx, [rdi]
0x1800807d4  call    cs:__imp_GdipSetPixelOffsetMode
0x1800807da  mov     r9d, 1E390623h
0x1800807e0  mov     ecx, eax
0x1800807e2  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800807e7  lea     rdx, [rsi+60h]
0x1800807eb  lea     rcx, [rsp+28h+arg_0]
0x1800807f0  call    ??$?0U?$TAffine3x3@N@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::TAffine3x3<double> const &)
0x1800807f5  nop
0x1800807f6  mov     rdx, [rax]
0x1800807f9  mov     rcx, [rdi]
0x1800807fc  call    cs:__imp_GdipSetWorldTransform
0x180080802  mov     r9d, 2519653h
0x180080808  mov     ecx, eax
0x18008080a  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18008080f  nop
0x180080810  mov     rcx, [rsp+28h+arg_0]
0x180080815  test    rcx, rcx
0x180080818  jz      short loc_180080820
0x18008081a  call    cs:__imp_GdipDeleteMatrix
0x180080820  lea     rcx, [rbx+0B0h]; this
0x180080827  mov     r9b, [rbx+0E0h]; bool
0x18008082e  mov     r8, [rdi]; struct Gdiplus::GpGraphics *
0x180080831  mov     rdx, rsi; struct Frame *
0x180080834  call    ?SetGraphics@GDIPlusClipStack@Gfx@@QEAAXPEBVFrame@ITarget@2@AEAVGpGraphics@Gdiplus@@_N@Z; Gfx::GDIPlusClipStack::SetGraphics(Gfx::ITarget::Frame const *,Gdiplus::GpGraphics &,bool)
0x180080839  jmp     loc_18008075C
0x18008083e  mov     ecx, 356842h; unsigned int
0x180080843  call    ?ThrowTag@CInvalidOperationException@Ofc@@SAXK@Z; Ofc::CInvalidOperationException::ThrowTag(ulong)
0x180080848  int     3; Trap to Debugger
```
