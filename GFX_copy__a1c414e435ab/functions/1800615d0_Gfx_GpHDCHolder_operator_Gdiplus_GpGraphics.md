# Gfx::GpHDCHolder::operator=(Gdiplus::GpGraphics &)

- ea: `0x1800615d0`
- end: `0x180061792`
- name: `??4GpHDCHolder@Gfx@@QEAAXAEAVGpGraphics@Gdiplus@@@Z`
- size: `450`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x1800b2b5c`
- `0x1800d34cc`
- `0x1800dc6f0`
- `0x180140c48`
- `0x18015a6c8`
- `0x180161470`
- `0x180173490`
- `0x18017c450`
- `0x18017e040`

## callees

- `0x180056ee0`
- `0x1800615d0`
- `0x180061fe8`
- `0x180062394`
- `0x180064c50`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006178b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006178b`
- `GDI32!ModifyWorldTransform` at `0x180061722`
- `GDI32!ModifyWorldTransform` at `0x180061722`
- `GDI32!SetMetaRgn` at `0x1800616f5`
- `GDI32!SetMetaRgn` at `0x1800616f5`
- `GDI32!SaveDC` at `0x1800616e9`
- `GDI32!SaveDC` at `0x1800616e9`
- `GDI32!SelectClipRgn` at `0x180061702`
- `GDI32!SelectClipRgn` at `0x180061702`
- `GDI32!DeleteObject` at `0x180061760`
- `GDI32!DeleteObject` at `0x180061760`
- `GDI32!SetGraphicsMode` at `0x180061712`
- `GDI32!SetGraphicsMode` at `0x180061712`
- `gdiplus!GdipGetRegionHRgn` at `0x180061653`
- `gdiplus!GdipGetRegionHRgn` at `0x180061653`
- `gdiplus!GdipDeleteRegion` at `0x180061749`
- `gdiplus!GdipDeleteRegion` at `0x180061749`
- `gdiplus!GdipCreateRegion` at `0x18006160f`
- `gdiplus!GdipCreateRegion` at `0x18006160f`
- `gdiplus!GdipGetClip` at `0x180061629`
- `gdiplus!GdipGetClip` at `0x180061629`
- `gdiplus!GdipGetWorldTransform` at `0x18006169b`
- `gdiplus!GdipGetWorldTransform` at `0x18006169b`
- `gdiplus!GdipGetDC` at `0x1800616d3`
- `gdiplus!GdipGetDC` at `0x1800616d3`
- `gdiplus!GdipGetMatrixElements` at `0x1800616b6`
- `gdiplus!GdipGetMatrixElements` at `0x1800616b6`
- `gdiplus!GdipDeleteMatrix` at `0x180061732`
- `gdiplus!GdipDeleteMatrix` at `0x180061732`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int __fastcall Gfx::GpHDCHolder::operator=(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int Clip; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int RegionHRgn; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int WorldTransform; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int MatrixElements; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned int DC; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  int result; // eax
  __int64 v23; // rdx
  __int64 v24; // [rsp+20h] [rbp-50h] BYREF
  __int64 v25; // [rsp+28h] [rbp-48h] BYREF
  HRGN hrgn; // [rsp+30h] [rbp-40h] BYREF
  __m128i si128; // [rsp+38h] [rbp-38h] BYREF
  __int64 v28; // [rsp+48h] [rbp-28h]
  XFORM xf; // [rsp+50h] [rbp-20h] BYREF

  Gfx::GpHDCHolder::Empty((Gfx::GpHDCHolder *)a1);
  hrgn = 0;
  v25 = 0;
  v4 = GdipCreateRegion(&v25);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v4, v5, v6, 38897216);
  Clip = GdipGetClip(a2, v25);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(Clip, v8, v9, 38897217);
  if ( hrgn )
  {
    CrashWithRecovery(0x1E3CF50Bu, 0);
    JUMPOUT(0x180061791LL);
  }
  RegionHRgn = GdipGetRegionHRgn(v25, a2, &hrgn);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(RegionHRgn, v11, v12, 38897218);
  memset(&xf, 0, sizeof(xf));
  v24 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v28 = 0;
  Gfx::GpMatrixHolder::operator=(&v24, &si128);
  WorldTransform = GdipGetWorldTransform(a2, v24);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(WorldTransform, v14, v15, 38897219);
  MatrixElements = GdipGetMatrixElements(v24, &xf);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(MatrixElements, v17, v18, 38897220);
  *(_QWORD *)(a1 + 8) = a2;
  DC = GdipGetDC(a2, a1);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(DC, v20, v21, 38897221);
  *(_DWORD *)(a1 + 16) = SaveDC(*(HDC *)a1);
  SetMetaRgn(*(HDC *)a1);
  SelectClipRgn(*(HDC *)a1, hrgn);
  SetGraphicsMode(*(HDC *)a1, 2);
  result = ModifyWorldTransform(*(HDC *)a1, &xf, 2u);
  if ( v24 )
  {
    result = GdipDeleteMatrix();
    v24 = 0;
  }
  if ( v25 )
  {
    result = GdipDeleteRegion(v25, v23);
    v25 = 0;
  }
  if ( hrgn )
    return DeleteObject(hrgn);
  return result;
}

```

## disassembly

```asm
0x1800615d0  mov     [rsp-8+arg_10], rbx
0x1800615d5  mov     [rsp-8+arg_18], rdi
0x1800615da  push    rbp
0x1800615db  mov     rbp, rsp
0x1800615de  sub     rsp, 70h
0x1800615e2  mov     rax, cs:__security_cookie
0x1800615e9  xor     rax, rsp
0x1800615ec  mov     [rbp+var_8], rax
0x1800615f0  mov     rdi, rdx
0x1800615f3  mov     rbx, rcx
0x1800615f6  call    ?Empty@GpHDCHolder@Gfx@@QEAAXXZ; Gfx::GpHDCHolder::Empty(void)
0x1800615fb  mov     [rbp+hrgn], 0
0x180061603  mov     [rbp+var_48], 0
0x18006160b  lea     rcx, [rbp+var_48]
0x18006160f  call    cs:__imp_GdipCreateRegion
0x180061615  mov     r9d, 2518640h
0x18006161b  mov     ecx, eax
0x18006161d  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180061622  mov     rdx, [rbp+var_48]
0x180061626  mov     rcx, rdi
0x180061629  call    cs:__imp_GdipGetClip
0x18006162f  mov     r9d, 2518641h
0x180061635  mov     ecx, eax
0x180061637  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18006163c  nop
0x18006163d  cmp     [rbp+hrgn], 0
0x180061642  jnz     loc_180061784
0x180061648  lea     r8, [rbp+hrgn]
0x18006164c  mov     rdx, rdi
0x18006164f  mov     rcx, [rbp+var_48]
0x180061653  call    cs:__imp_GdipGetRegionHRgn
0x180061659  mov     r9d, 2518642h
0x18006165f  mov     ecx, eax
0x180061661  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180061666  xorps   xmm0, xmm0
0x180061669  xor     eax, eax
0x18006166b  movups  xmmword ptr [rbp+xf.eM11], xmm0
0x18006166f  mov     qword ptr [rbp+xf.eDx], rax
0x180061673  mov     [rbp+var_50], rax
0x180061677  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x18006167f  movups  [rbp+var_38], xmm0
0x180061683  mov     [rbp+var_28], rax
0x180061687  lea     rdx, [rbp+var_38]
0x18006168b  lea     rcx, [rbp+var_50]
0x18006168f  call    ??4GpMatrixHolder@Gfx@@QEAAXAEBU?$TAffine3x3@M@Math@@@Z; Gfx::GpMatrixHolder::operator=(Math::TAffine3x3<float> const &)
0x180061694  mov     rdx, [rbp+var_50]
0x180061698  mov     rcx, rdi
0x18006169b  call    cs:__imp_GdipGetWorldTransform
0x1800616a1  mov     r9d, 2518643h
0x1800616a7  mov     ecx, eax
0x1800616a9  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800616ae  lea     rdx, [rbp+xf]
0x1800616b2  mov     rcx, [rbp+var_50]
0x1800616b6  call    cs:__imp_GdipGetMatrixElements
0x1800616bc  mov     r9d, 2518644h
0x1800616c2  mov     ecx, eax
0x1800616c4  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800616c9  mov     [rbx+8], rdi
0x1800616cd  mov     rdx, rbx
0x1800616d0  mov     rcx, rdi
0x1800616d3  call    cs:__imp_GdipGetDC
0x1800616d9  mov     r9d, 2518645h
0x1800616df  mov     ecx, eax
0x1800616e1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800616e6  mov     rcx, [rbx]; hdc
0x1800616e9  call    cs:__imp_SaveDC
0x1800616ef  mov     [rbx+10h], eax
0x1800616f2  mov     rcx, [rbx]; hdc
0x1800616f5  call    cs:__imp_SetMetaRgn
0x1800616fb  mov     rdx, [rbp+hrgn]; hrgn
0x1800616ff  mov     rcx, [rbx]; hdc
0x180061702  call    cs:__imp_SelectClipRgn
0x180061708  mov     edi, 2
0x18006170d  mov     edx, edi; iMode
0x18006170f  mov     rcx, [rbx]; hdc
0x180061712  call    cs:__imp_SetGraphicsMode
0x180061718  mov     r8d, edi; mode
0x18006171b  lea     rdx, [rbp+xf]; lpxf
0x18006171f  mov     rcx, [rbx]; hdc
0x180061722  call    cs:__imp_ModifyWorldTransform
0x180061728  nop
0x180061729  mov     rcx, [rbp+var_50]
0x18006172d  test    rcx, rcx
0x180061730  jz      short loc_180061740
0x180061732  call    cs:__imp_GdipDeleteMatrix
0x180061738  mov     [rbp+var_50], 0
0x180061740  mov     rcx, [rbp+var_48]
0x180061744  test    rcx, rcx
0x180061747  jz      short loc_180061757
0x180061749  call    cs:__imp_GdipDeleteRegion
0x18006174f  mov     [rbp+var_48], 0
0x180061757  mov     rcx, [rbp+hrgn]; ho
0x18006175b  test    rcx, rcx
0x18006175e  jz      short loc_180061766
0x180061760  call    cs:__imp_DeleteObject
0x180061766  mov     rcx, [rbp+var_8]
0x18006176a  xor     rcx, rsp; StackCookie
0x18006176d  call    __security_check_cookie
0x180061772  lea     r11, [rsp+70h+var_s0]
0x180061777  mov     rbx, [r11+20h]
0x18006177b  mov     rdi, [r11+28h]
0x18006177f  mov     rsp, r11
0x180061782  pop     rbp
0x180061783  retn
0x180061784  xor     edx, edx
0x180061786  mov     ecx, 1E3CF50Bh
0x18006178b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
