# GEL::BitmapBasedPrinter::WhiteOutBitmap(ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap> &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,bool)

- ea: `0x1800c0860`
- end: `0x1800c0955`
- name: `?WhiteOutBitmap@BitmapBasedPrinter@GEL@@KAXAEAV?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_N@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800c1010`

## callees

- `0x1800502bc`
- `0x180062394`
- `0x1800c0860`

## import_xrefs

- `gdiplus!GdipSetCompositingMode` at `0x1800c0897`
- `gdiplus!GdipSetCompositingMode` at `0x1800c0897`
- `gdiplus!GdipFillRectangleI` at `0x1800c0912`
- `gdiplus!GdipFillRectangleI` at `0x1800c0912`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1800c087a`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1800c087a`
- `gdiplus!GdipCreateSolidFill` at `0x1800c08bb`
- `gdiplus!GdipCreateSolidFill` at `0x1800c08bb`
- `gdiplus!GdipDeleteBrush` at `0x1800c0930`
- `gdiplus!GdipDeleteBrush` at `0x1800c0930`
- `gdiplus!GdipDeleteGraphics` at `0x1800c0949`
- `gdiplus!GdipDeleteGraphics` at `0x1800c0949`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GEL::BitmapBasedPrinter::WhiteOutBitmap(_QWORD *a1, unsigned int *a2)
{
  unsigned int ImageGraphicsContext; // eax
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // edx
  __int64 v13; // r9
  char v14; // al
  int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  _QWORD v20[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v21; // [rsp+68h] [rbp+20h] BYREF

  v20[0] = 0;
  ImageGraphicsContext = GdipGetImageGraphicsContext(*a1, v20);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(ImageGraphicsContext, v4, v5, 38869192);
  v6 = GdipSetCompositingMode(v20[0], 1);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v6, v7, v8, 38869193);
  v21 = 0;
  GdipCreateSolidFill(0xFFFFFFFFLL, &v21);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v9, v10, v11, 38869194);
  Math::TRect<int>::IsDegenerate(a2);
  Math::TRect<int>::IsDegenerate(a2);
  if ( v14 )
    v15 = 0;
  else
    v15 = a2[2] - *a2;
  v16 = GdipFillRectangleI(v20[0], v21, *a2, v13, v15, v12);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(v16, v17, v18, 38869195);
  if ( v21 )
  {
    GdipDeleteBrush(v21, v19);
    v21 = 0;
  }
  if ( v20[0] )
    GdipDeleteGraphics();
}

```

## disassembly

```asm
0x1800c0860  push    rbx
0x1800c0862  sub     rsp, 40h
0x1800c0866  mov     rbx, rdx
0x1800c0869  mov     [rsp+48h+var_18], 0
0x1800c0872  lea     rdx, [rsp+48h+var_18]
0x1800c0877  mov     rcx, [rcx]
0x1800c087a  call    cs:__imp_GdipGetImageGraphicsContext
0x1800c0880  mov     r9d, 25118C8h
0x1800c0886  mov     ecx, eax
0x1800c0888  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c088d  mov     edx, 1
0x1800c0892  mov     rcx, [rsp+48h+var_18]
0x1800c0897  call    cs:__imp_GdipSetCompositingMode
0x1800c089d  mov     r9d, 25118C9h
0x1800c08a3  mov     ecx, eax
0x1800c08a5  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c08aa  mov     [rsp+48h+arg_18], 0
0x1800c08b3  lea     rdx, [rsp+48h+arg_18]
0x1800c08b8  or      ecx, 0FFFFFFFFh
0x1800c08bb  call    cs:__imp_GdipCreateSolidFill
0x1800c08c1  mov     r9d, 25118CAh
0x1800c08c7  mov     ecx, eax
0x1800c08c9  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c08ce  mov     r9d, [rbx+4]
0x1800c08d2  mov     rcx, rbx
0x1800c08d5  call    ?IsDegenerate@?$TRect@H@Math@@QEBA_NXZ; Math::TRect<int>::IsDegenerate(void)
0x1800c08da  test    al, al
0x1800c08dc  jnz     short loc_1800C08E6
0x1800c08de  mov     edx, [rbx+0Ch]
0x1800c08e1  sub     edx, r9d
0x1800c08e4  jmp     short loc_1800C08E8
0x1800c08e6  xor     edx, edx
0x1800c08e8  mov     rcx, rbx
0x1800c08eb  call    ?IsDegenerate@?$TRect@H@Math@@QEBA_NXZ; Math::TRect<int>::IsDegenerate(void)
0x1800c08f0  test    al, al
0x1800c08f2  jnz     short loc_1800C08FB
0x1800c08f4  mov     eax, [rbx+8]
0x1800c08f7  sub     eax, [rbx]
0x1800c08f9  jmp     short loc_1800C08FD
0x1800c08fb  xor     eax, eax
0x1800c08fd  mov     [rsp+48h+var_20], edx
0x1800c0901  mov     [rsp+48h+var_28], eax
0x1800c0905  mov     r8d, [rbx]
0x1800c0908  mov     rdx, [rsp+48h+arg_18]
0x1800c090d  mov     rcx, [rsp+48h+var_18]
0x1800c0912  call    cs:__imp_GdipFillRectangleI
0x1800c0918  mov     r9d, 25118CBh
0x1800c091e  mov     ecx, eax
0x1800c0920  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c0925  nop
0x1800c0926  mov     rcx, [rsp+48h+arg_18]
0x1800c092b  test    rcx, rcx
0x1800c092e  jz      short loc_1800C093F
0x1800c0930  call    cs:__imp_GdipDeleteBrush
0x1800c0936  mov     [rsp+48h+arg_18], 0
0x1800c093f  mov     rcx, [rsp+48h+var_18]
0x1800c0944  test    rcx, rcx
0x1800c0947  jz      short loc_1800C094F
0x1800c0949  call    cs:__imp_GdipDeleteGraphics
0x1800c094f  add     rsp, 40h
0x1800c0953  pop     rbx
0x1800c0954  retn
```
