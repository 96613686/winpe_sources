# Gfx::GpHDCHolder::operator=(Gdiplus::GpGraphics &)

- ea: `0x18007fe30`
- end: `0x18007fff2`
- name: `??4GpHDCHolder@Gfx@@QEAAXAEAVGpGraphics@Gdiplus@@@Z`
- size: `450`
- prototype: ``
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x1800ba25c`
- `0x1800bee74`
- `0x1800dcfec`
- `0x18013f0d8`
- `0x18015c198`
- `0x180163180`
- `0x180177ae0`
- `0x180180ab0`
- `0x1801827c0`

## callees

- `0x1800578b0`
- `0x18007f398`
- `0x18007f754`
- `0x18007fe30`
- `0x180082960`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18007ffeb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18007ffeb`
- `GDI32!ModifyWorldTransform` at `0x18007ff82`
- `GDI32!ModifyWorldTransform` at `0x18007ff82`
- `GDI32!SetMetaRgn` at `0x18007ff55`
- `GDI32!SetMetaRgn` at `0x18007ff55`
- `GDI32!SaveDC` at `0x18007ff49`
- `GDI32!SaveDC` at `0x18007ff49`
- `GDI32!SelectClipRgn` at `0x18007ff62`
- `GDI32!SelectClipRgn` at `0x18007ff62`
- `GDI32!DeleteObject` at `0x18007ffc0`
- `GDI32!DeleteObject` at `0x18007ffc0`
- `GDI32!SetGraphicsMode` at `0x18007ff72`
- `GDI32!SetGraphicsMode` at `0x18007ff72`
- `gdiplus!GdipGetRegionHRgn` at `0x18007feb3`
- `gdiplus!GdipGetRegionHRgn` at `0x18007feb3`
- `gdiplus!GdipDeleteRegion` at `0x18007ffa9`
- `gdiplus!GdipDeleteRegion` at `0x18007ffa9`
- `gdiplus!GdipCreateRegion` at `0x18007fe6f`
- `gdiplus!GdipCreateRegion` at `0x18007fe6f`
- `gdiplus!GdipGetClip` at `0x18007fe89`
- `gdiplus!GdipGetClip` at `0x18007fe89`
- `gdiplus!GdipGetWorldTransform` at `0x18007fefb`
- `gdiplus!GdipGetWorldTransform` at `0x18007fefb`
- `gdiplus!GdipGetDC` at `0x18007ff33`
- `gdiplus!GdipGetDC` at `0x18007ff33`
- `gdiplus!GdipGetMatrixElements` at `0x18007ff16`
- `gdiplus!GdipGetMatrixElements` at `0x18007ff16`
- `gdiplus!GdipDeleteMatrix` at `0x18007ff92`
- `gdiplus!GdipDeleteMatrix` at `0x18007ff92`

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
    JUMPOUT(0x18007FFF1LL);
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
0x18007fe30  mov     [rsp-8+arg_10], rbx
0x18007fe35  mov     [rsp-8+arg_18], rdi
0x18007fe3a  push    rbp
0x18007fe3b  mov     rbp, rsp
0x18007fe3e  sub     rsp, 70h
0x18007fe42  mov     rax, cs:__security_cookie
0x18007fe49  xor     rax, rsp
0x18007fe4c  mov     [rbp+var_8], rax
0x18007fe50  mov     rdi, rdx
0x18007fe53  mov     rbx, rcx
0x18007fe56  call    ?Empty@GpHDCHolder@Gfx@@QEAAXXZ; Gfx::GpHDCHolder::Empty(void)
0x18007fe5b  mov     [rbp+hrgn], 0
0x18007fe63  mov     [rbp+var_48], 0
0x18007fe6b  lea     rcx, [rbp+var_48]
0x18007fe6f  call    cs:__imp_GdipCreateRegion
0x18007fe75  mov     r9d, 2518640h
0x18007fe7b  mov     ecx, eax
0x18007fe7d  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18007fe82  mov     rdx, [rbp+var_48]
0x18007fe86  mov     rcx, rdi
0x18007fe89  call    cs:__imp_GdipGetClip
0x18007fe8f  mov     r9d, 2518641h
0x18007fe95  mov     ecx, eax
0x18007fe97  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18007fe9c  nop
0x18007fe9d  cmp     [rbp+hrgn], 0
0x18007fea2  jnz     loc_18007FFE4
0x18007fea8  lea     r8, [rbp+hrgn]
0x18007feac  mov     rdx, rdi
0x18007feaf  mov     rcx, [rbp+var_48]
0x18007feb3  call    cs:__imp_GdipGetRegionHRgn
0x18007feb9  mov     r9d, 2518642h
0x18007febf  mov     ecx, eax
0x18007fec1  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18007fec6  xorps   xmm0, xmm0
0x18007fec9  xor     eax, eax
0x18007fecb  movups  xmmword ptr [rbp+xf.eM11], xmm0
0x18007fecf  mov     qword ptr [rbp+xf.eDx], rax
0x18007fed3  mov     [rbp+var_50], rax
0x18007fed7  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x18007fedf  movups  [rbp+var_38], xmm0
0x18007fee3  mov     [rbp+var_28], rax
0x18007fee7  lea     rdx, [rbp+var_38]
0x18007feeb  lea     rcx, [rbp+var_50]
0x18007feef  call    ??4GpMatrixHolder@Gfx@@QEAAXAEBU?$TAffine3x3@M@Math@@@Z; Gfx::GpMatrixHolder::operator=(Math::TAffine3x3<float> const &)
0x18007fef4  mov     rdx, [rbp+var_50]
0x18007fef8  mov     rcx, rdi
0x18007fefb  call    cs:__imp_GdipGetWorldTransform
0x18007ff01  mov     r9d, 2518643h
0x18007ff07  mov     ecx, eax
0x18007ff09  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18007ff0e  lea     rdx, [rbp+xf]
0x18007ff12  mov     rcx, [rbp+var_50]
0x18007ff16  call    cs:__imp_GdipGetMatrixElements
0x18007ff1c  mov     r9d, 2518644h
0x18007ff22  mov     ecx, eax
0x18007ff24  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18007ff29  mov     [rbx+8], rdi
0x18007ff2d  mov     rdx, rbx
0x18007ff30  mov     rcx, rdi
0x18007ff33  call    cs:__imp_GdipGetDC
0x18007ff39  mov     r9d, 2518645h
0x18007ff3f  mov     ecx, eax
0x18007ff41  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18007ff46  mov     rcx, [rbx]; hdc
0x18007ff49  call    cs:__imp_SaveDC
0x18007ff4f  mov     [rbx+10h], eax
0x18007ff52  mov     rcx, [rbx]; hdc
0x18007ff55  call    cs:__imp_SetMetaRgn
0x18007ff5b  mov     rdx, [rbp+hrgn]; hrgn
0x18007ff5f  mov     rcx, [rbx]; hdc
0x18007ff62  call    cs:__imp_SelectClipRgn
0x18007ff68  mov     edi, 2
0x18007ff6d  mov     edx, edi; iMode
0x18007ff6f  mov     rcx, [rbx]; hdc
0x18007ff72  call    cs:__imp_SetGraphicsMode
0x18007ff78  mov     r8d, edi; mode
0x18007ff7b  lea     rdx, [rbp+xf]; lpxf
0x18007ff7f  mov     rcx, [rbx]; hdc
0x18007ff82  call    cs:__imp_ModifyWorldTransform
0x18007ff88  nop
0x18007ff89  mov     rcx, [rbp+var_50]
0x18007ff8d  test    rcx, rcx
0x18007ff90  jz      short loc_18007FFA0
0x18007ff92  call    cs:__imp_GdipDeleteMatrix
0x18007ff98  mov     [rbp+var_50], 0
0x18007ffa0  mov     rcx, [rbp+var_48]
0x18007ffa4  test    rcx, rcx
0x18007ffa7  jz      short loc_18007FFB7
0x18007ffa9  call    cs:__imp_GdipDeleteRegion
0x18007ffaf  mov     [rbp+var_48], 0
0x18007ffb7  mov     rcx, [rbp+hrgn]; ho
0x18007ffbb  test    rcx, rcx
0x18007ffbe  jz      short loc_18007FFC6
0x18007ffc0  call    cs:__imp_DeleteObject
0x18007ffc6  mov     rcx, [rbp+var_8]
0x18007ffca  xor     rcx, rsp; StackCookie
0x18007ffcd  call    __security_check_cookie
0x18007ffd2  lea     r11, [rsp+70h+var_s0]
0x18007ffd7  mov     rbx, [r11+20h]
0x18007ffdb  mov     rdi, [r11+28h]
0x18007ffdf  mov     rsp, r11
0x18007ffe2  pop     rbp
0x18007ffe3  retn
0x18007ffe4  xor     edx, edx
0x18007ffe6  mov     ecx, 1E3CF50Bh
0x18007ffeb  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
