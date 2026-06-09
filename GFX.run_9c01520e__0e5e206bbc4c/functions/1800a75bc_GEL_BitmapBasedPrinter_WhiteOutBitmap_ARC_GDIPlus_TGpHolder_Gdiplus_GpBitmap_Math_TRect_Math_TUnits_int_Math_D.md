# GEL::BitmapBasedPrinter::WhiteOutBitmap(ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap> &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,bool)

- ea: `0x1800a75bc`
- end: `0x1800a76b1`
- name: `?WhiteOutBitmap@BitmapBasedPrinter@GEL@@KAXAEAV?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_N@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a6e80`

## callees

- `0x180052528`
- `0x18007f754`
- `0x1800a75bc`

## import_xrefs

- `gdiplus!GdipSetCompositingMode` at `0x1800a75f3`
- `gdiplus!GdipSetCompositingMode` at `0x1800a75f3`
- `gdiplus!GdipFillRectangleI` at `0x1800a766e`
- `gdiplus!GdipFillRectangleI` at `0x1800a766e`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1800a75d6`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1800a75d6`
- `gdiplus!GdipCreateSolidFill` at `0x1800a7617`
- `gdiplus!GdipCreateSolidFill` at `0x1800a7617`
- `gdiplus!GdipDeleteBrush` at `0x1800a768c`
- `gdiplus!GdipDeleteBrush` at `0x1800a768c`
- `gdiplus!GdipDeleteGraphics` at `0x1800a76a5`
- `gdiplus!GdipDeleteGraphics` at `0x1800a76a5`

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
0x1800a75bc  push    rbx
0x1800a75be  sub     rsp, 40h
0x1800a75c2  mov     rbx, rdx
0x1800a75c5  mov     [rsp+48h+var_18], 0
0x1800a75ce  lea     rdx, [rsp+48h+var_18]
0x1800a75d3  mov     rcx, [rcx]
0x1800a75d6  call    cs:__imp_GdipGetImageGraphicsContext
0x1800a75dc  mov     r9d, 25118C8h
0x1800a75e2  mov     ecx, eax
0x1800a75e4  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a75e9  mov     edx, 1
0x1800a75ee  mov     rcx, [rsp+48h+var_18]
0x1800a75f3  call    cs:__imp_GdipSetCompositingMode
0x1800a75f9  mov     r9d, 25118C9h
0x1800a75ff  mov     ecx, eax
0x1800a7601  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a7606  mov     [rsp+48h+arg_18], 0
0x1800a760f  lea     rdx, [rsp+48h+arg_18]
0x1800a7614  or      ecx, 0FFFFFFFFh
0x1800a7617  call    cs:__imp_GdipCreateSolidFill
0x1800a761d  mov     r9d, 25118CAh
0x1800a7623  mov     ecx, eax
0x1800a7625  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a762a  mov     r9d, [rbx+4]
0x1800a762e  mov     rcx, rbx
0x1800a7631  call    ?IsDegenerate@?$TRect@H@Math@@QEBA_NXZ; Math::TRect<int>::IsDegenerate(void)
0x1800a7636  test    al, al
0x1800a7638  jnz     short loc_1800A7642
0x1800a763a  mov     edx, [rbx+0Ch]
0x1800a763d  sub     edx, r9d
0x1800a7640  jmp     short loc_1800A7644
0x1800a7642  xor     edx, edx
0x1800a7644  mov     rcx, rbx
0x1800a7647  call    ?IsDegenerate@?$TRect@H@Math@@QEBA_NXZ; Math::TRect<int>::IsDegenerate(void)
0x1800a764c  test    al, al
0x1800a764e  jnz     short loc_1800A7657
0x1800a7650  mov     eax, [rbx+8]
0x1800a7653  sub     eax, [rbx]
0x1800a7655  jmp     short loc_1800A7659
0x1800a7657  xor     eax, eax
0x1800a7659  mov     [rsp+48h+var_20], edx
0x1800a765d  mov     [rsp+48h+var_28], eax
0x1800a7661  mov     r8d, [rbx]
0x1800a7664  mov     rdx, [rsp+48h+arg_18]
0x1800a7669  mov     rcx, [rsp+48h+var_18]
0x1800a766e  call    cs:__imp_GdipFillRectangleI
0x1800a7674  mov     r9d, 25118CBh
0x1800a767a  mov     ecx, eax
0x1800a767c  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a7681  nop
0x1800a7682  mov     rcx, [rsp+48h+arg_18]
0x1800a7687  test    rcx, rcx
0x1800a768a  jz      short loc_1800A769B
0x1800a768c  call    cs:__imp_GdipDeleteBrush
0x1800a7692  mov     [rsp+48h+arg_18], 0
0x1800a769b  mov     rcx, [rsp+48h+var_18]
0x1800a76a0  test    rcx, rcx
0x1800a76a3  jz      short loc_1800A76AB
0x1800a76a5  call    cs:__imp_GdipDeleteGraphics
0x1800a76ab  add     rsp, 40h
0x1800a76af  pop     rbx
0x1800a76b0  retn
```
