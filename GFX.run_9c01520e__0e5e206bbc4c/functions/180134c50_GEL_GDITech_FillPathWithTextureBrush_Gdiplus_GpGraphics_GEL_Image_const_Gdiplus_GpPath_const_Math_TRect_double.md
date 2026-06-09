# GEL::GDITech::FillPathWithTextureBrush(Gdiplus::GpGraphics &,GEL::Image const &,Gdiplus::GpPath const *,Math::TRect<double> const &,Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TAffine3x3<double> const &,Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Gdiplus::WrapMode)

- ea: `0x180134c50`
- end: `0x180134e87`
- name: `?FillPathWithTextureBrush@GDITech@GEL@@CA?AW4Status@Gdiplus@@AEAVGpGraphics@4@AEBVImage@2@PEBVGpPath@4@AEBU?$TRect@N@Math@@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@9@AEBU?$TAffine3x3@N@9@4W4WrapMode@4@@Z`
- size: `567`
- prototype: `__int64 __fastcall(int, int, int, int, Gfx::Rect *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800bc38c`

## callees

- `0x180014490`
- `0x1800154a0`
- `0x180015ed0`
- `0x180054d70`
- `0x18007f348`
- `0x18007f850`
- `0x18007fa70`
- `0x180134c50`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!round` at `0x180134c97`
- `api-ms-win-crt-math-l1-1-0!round` at `0x180134cad`
- `api-ms-win-crt-math-l1-1-0!round` at `0x180134cd8`
- `api-ms-win-crt-math-l1-1-0!round` at `0x180134cfd`
- `api-ms-win-crt-math-l1-1-0!round` at `0x180134c97`
- `api-ms-win-crt-math-l1-1-0!round` at `0x180134cad`
- `api-ms-win-crt-math-l1-1-0!round` at `0x180134cd8`
- `api-ms-win-crt-math-l1-1-0!round` at `0x180134cfd`
- `gdiplus!GdipFillPath` at `0x180134dc6`
- `gdiplus!GdipFillPath` at `0x180134e7e`
- `gdiplus!GdipFillPath` at `0x180134dc6`
- `gdiplus!GdipFillPath` at `0x180134e7e`
- `gdiplus!GdipSetTextureTransform` at `0x180134db6`
- `gdiplus!GdipSetTextureTransform` at `0x180134db6`
- `gdiplus!GdipCreateTexture2I` at `0x180134d5e`
- `gdiplus!GdipCreateTexture2I` at `0x180134d5e`
- `gdiplus!GdipCreateSolidFill` at `0x180134e27`
- `gdiplus!GdipCreateSolidFill` at `0x180134e27`
- `gdiplus!GdipDeleteBrush` at `0x180134dea`
- `gdiplus!GdipDeleteBrush` at `0x180134e3a`
- `gdiplus!GdipDeleteBrush` at `0x180134e4d`
- `gdiplus!GdipDeleteBrush` at `0x180134dea`
- `gdiplus!GdipDeleteBrush` at `0x180134e3a`
- `gdiplus!GdipDeleteBrush` at `0x180134e4d`
- `gdiplus!GdipDeleteMatrix` at `0x180134dd7`
- `gdiplus!GdipDeleteMatrix` at `0x180134dd7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GEL::GDITech::FillPathWithTextureBrush(
        __int64 a1,
        const struct GEL::IImage *a2,
        __int64 a3,
        __int64 a4,
        Gfx::Rect *a5,
        __int64 a6,
        __int64 a7,
        unsigned int a8)
{
  double *v10; // rbx
  int v11; // esi
  int v12; // r14d
  double v13; // xmm0_8
  int v14; // r13d
  double v15; // xmm0_8
  int v16; // edi
  int PixelWidth; // ebx
  int PixelHeight; // eax
  int v19; // r8d
  int v20; // edx
  __int64 v21; // rax
  unsigned int v22; // ebx
  int v24; // eax
  double v25[2]; // [rsp+48h] [rbp-59h] BYREF
  _BYTE v26[24]; // [rsp+58h] [rbp-49h] BYREF
  double v27; // [rsp+70h] [rbp-31h]
  _BYTE v28[96]; // [rsp+78h] [rbp-29h] BYREF
  __int64 v30; // [rsp+100h] [rbp+5Fh] BYREF

  v30 = a4;
  GEL::IImage::GpImageLock::GpImageLock((GEL::IImage::GpImageLock *)v26, a2, 1u);
  v25[0] = v27;
  v10 = (double *)a5;
  v11 = (int)round(*(double *)a5);
  if ( v11 <= 0 )
    v11 = 0;
  v12 = (int)round(v10[1]);
  if ( v12 <= 0 )
    v12 = 0;
  if ( Gfx::Rect::FIsEmpty((Gfx::Rect *)v10) )
    v13 = 0.0;
  else
    v13 = v10[2] - *v10;
  v14 = (int)round(v13);
  if ( Gfx::Rect::FIsEmpty((Gfx::Rect *)v10) )
    v15 = 0.0;
  else
    v15 = v10[3] - v10[1];
  v16 = (int)round(v15);
  PixelWidth = GEL::Image::GetPixelWidth(a2);
  PixelHeight = GEL::Image::GetPixelHeight(a2);
  v19 = PixelWidth - v11;
  if ( v11 + v14 <= PixelWidth )
    v19 = v14;
  v20 = PixelHeight - v12;
  if ( v12 + v16 <= PixelHeight )
    v20 = v16;
  v30 = 0;
  if ( (unsigned int)GdipCreateTexture2I(*(_QWORD *)&v25[0], a8, (unsigned int)v11, (unsigned int)v12, v19, v20, &v30)
    || !v30 )
  {
    a5 = 0;
    GdipCreateSolidFill(4278190335LL, &a5);
    if ( !v24 )
      GdipFillPath(a1, a5, a3);
    if ( a5 )
    {
      GdipDeleteBrush();
      a5 = 0;
    }
    if ( v30 )
    {
      GdipDeleteBrush();
      v30 = 0;
    }
    GEL::IImage::GpImageLock::~GpImageLock((GEL::IImage::GpImageLock *)v26);
    return 0;
  }
  else
  {
    v25[0] = (double)v11;
    v25[1] = (double)v12;
    v21 = Math::operator*<double,double,double>(v28, v25, a6);
    Gfx::GpMatrixHolder::GpMatrixHolder(&a7, v21);
    GdipSetTextureTransform(v30, a7);
    v22 = GdipFillPath(a1, v30, a3);
    if ( a7 )
    {
      GdipDeleteMatrix();
      a7 = 0;
    }
    if ( v30 )
    {
      GdipDeleteBrush();
      v30 = 0;
    }
    GEL::IImage::GpImageLock::~GpImageLock((GEL::IImage::GpImageLock *)v26);
    return v22;
  }
}

```

## disassembly

```asm
0x180134c50  mov     rax, rsp
0x180134c53  mov     [rax+8], rbx
0x180134c57  mov     [rax+20h], r9
0x180134c5b  mov     [rax+10h], rdx
0x180134c5f  push    rbp
0x180134c60  push    rsi
0x180134c61  push    rdi
0x180134c62  push    r12
0x180134c64  push    r13
0x180134c66  push    r14
0x180134c68  push    r15
0x180134c6a  lea     rbp, [rax-3Fh]
0x180134c6e  sub     rsp, 0A0h
0x180134c75  mov     r15, r8
0x180134c78  mov     r12, rcx
0x180134c7b  mov     r8b, 1; unsigned __int8
0x180134c7e  lea     rcx, [rbp+37h+var_80]; this
0x180134c82  call    ??0GpImageLock@IImage@GEL@@QEAA@AEBU12@E@Z; GEL::IImage::GpImageLock::GpImageLock(GEL::IImage const &,uchar)
0x180134c87  mov     rax, [rbp+37h+var_68]
0x180134c8b  mov     [rbp+37h+var_90], rax
0x180134c8f  mov     rbx, [rbp+37h+arg_20]
0x180134c93  movsd   xmm0, qword ptr [rbx]; X
0x180134c97  call    cs:__imp_round
0x180134c9d  cvttsd2si esi, xmm0
0x180134ca1  xor     edi, edi
0x180134ca3  test    esi, esi
0x180134ca5  cmovle  esi, edi
0x180134ca8  movsd   xmm0, qword ptr [rbx+8]; X
0x180134cad  call    cs:__imp_round
0x180134cb3  cvttsd2si r14d, xmm0
0x180134cb8  test    r14d, r14d
0x180134cbb  cmovle  r14d, edi
0x180134cbf  mov     rcx, rbx; this
0x180134cc2  call    ?FIsEmpty@Rect@Gfx@@QEBA_NXZ; Gfx::Rect::FIsEmpty(void)
0x180134cc7  test    al, al
0x180134cc9  jnz     loc_180134E64
0x180134ccf  movsd   xmm0, qword ptr [rbx+10h]
0x180134cd4  subsd   xmm0, qword ptr [rbx]; X
0x180134cd8  call    cs:__imp_round
0x180134cde  cvttsd2si r13d, xmm0
0x180134ce3  mov     rcx, rbx; this
0x180134ce6  call    ?FIsEmpty@Rect@Gfx@@QEBA_NXZ; Gfx::Rect::FIsEmpty(void)
0x180134ceb  test    al, al
0x180134ced  jnz     loc_180134E6C
0x180134cf3  movsd   xmm0, qword ptr [rbx+18h]
0x180134cf8  subsd   xmm0, qword ptr [rbx+8]; X
0x180134cfd  call    cs:__imp_round
0x180134d03  cvttsd2si edi, xmm0
0x180134d07  mov     rcx, [rbp+37h+arg_8]; this
0x180134d0b  call    ?GetPixelWidth@Image@GEL@@UEBAHXZ; GEL::Image::GetPixelWidth(void)
0x180134d10  mov     ebx, eax
0x180134d12  mov     rcx, [rbp+37h+arg_8]; this
0x180134d16  call    ?GetPixelHeight@Image@GEL@@UEBAHXZ; GEL::Image::GetPixelHeight(void)
0x180134d1b  lea     ecx, [rsi+r13]
0x180134d1f  mov     r8d, ebx
0x180134d22  sub     r8d, esi
0x180134d25  cmp     ecx, ebx
0x180134d27  cmovle  r8d, r13d
0x180134d2b  lea     ecx, [r14+rdi]
0x180134d2f  mov     edx, eax
0x180134d31  sub     edx, r14d
0x180134d34  cmp     ecx, eax
0x180134d36  cmovle  edx, edi
0x180134d39  xor     edi, edi
0x180134d3b  mov     [rbp+37h+arg_18], rdi
0x180134d3f  lea     rax, [rbp+37h+arg_18]
0x180134d43  mov     [rsp+30h], rax
0x180134d48  mov     dword ptr [rsp+0D0h+var_A8], edx
0x180134d4c  mov     [rsp+0D0h+var_B0], r8d
0x180134d51  mov     r9d, r14d
0x180134d54  mov     r8d, esi
0x180134d57  mov     edx, [rbp+37h+arg_38]
0x180134d5a  mov     rcx, [rbp+37h+var_90]
0x180134d5e  call    cs:__imp_GdipCreateTexture2I
0x180134d64  test    eax, eax
0x180134d66  jnz     loc_180134E1A
0x180134d6c  cmp     [rbp+37h+arg_18], rdi
0x180134d70  jz      loc_180134E1A
0x180134d76  movd    xmm0, esi
0x180134d7a  cvtdq2pd xmm0, xmm0
0x180134d7e  movsd   [rbp+37h+var_90], xmm0
0x180134d83  movd    xmm1, r14d
0x180134d88  cvtdq2pd xmm1, xmm1
0x180134d8c  movsd   [rbp+37h+var_88], xmm1
0x180134d91  mov     r8, [rbp+37h+arg_28]
0x180134d95  lea     rdx, [rbp+37h+var_90]
0x180134d99  lea     rcx, [rbp+37h+var_60]
0x180134d9d  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU?$TTranslation2@N@0@AEBU10@@Z; Math::operator*<double,double,double>(Math::TTranslation2<double> const &,Math::TAffine3x3<double> const &)
0x180134da2  mov     rdx, rax
0x180134da5  lea     rcx, [rbp+37h+arg_30]
0x180134da9  call    ??$?0U?$TAffine3x3@N@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::TAffine3x3<double> const &)
0x180134dae  mov     rdx, [rbp+37h+arg_30]
0x180134db2  mov     rcx, [rbp+37h+arg_18]
0x180134db6  call    cs:__imp_GdipSetTextureTransform
0x180134dbc  mov     r8, r15
0x180134dbf  mov     rdx, [rbp+37h+arg_18]
0x180134dc3  mov     rcx, r12
0x180134dc6  call    cs:__imp_GdipFillPath
0x180134dcc  mov     ebx, eax
0x180134dce  mov     rcx, [rbp+37h+arg_30]
0x180134dd2  test    rcx, rcx
0x180134dd5  jz      short loc_180134DE1
0x180134dd7  call    cs:__imp_GdipDeleteMatrix
0x180134ddd  mov     [rbp+37h+arg_30], rdi
0x180134de1  mov     rcx, [rbp+37h+arg_18]
0x180134de5  test    rcx, rcx
0x180134de8  jz      short loc_180134DF4
0x180134dea  call    cs:__imp_GdipDeleteBrush
0x180134df0  mov     [rbp+37h+arg_18], rdi
0x180134df4  lea     rcx, [rbp+37h+var_80]; this
0x180134df8  call    ??1GpImageLock@IImage@GEL@@QEAA@XZ; GEL::IImage::GpImageLock::~GpImageLock(void)
0x180134dfd  mov     eax, ebx
0x180134dff  mov     rbx, [rsp+0D0h+arg_0]
0x180134e07  add     rsp, 0A0h
0x180134e0e  pop     r15
0x180134e10  pop     r14
0x180134e12  pop     r13
0x180134e14  pop     r12
0x180134e16  pop     rdi
0x180134e17  pop     rsi
0x180134e18  pop     rbp
0x180134e19  retn
0x180134e1a  mov     [rbp+37h+arg_20], rdi
0x180134e1e  lea     rdx, [rbp+37h+arg_20]
0x180134e22  mov     ecx, 0FF0000FFh
0x180134e27  call    cs:__imp_GdipCreateSolidFill
0x180134e2d  test    eax, eax
0x180134e2f  jz      short loc_180134E74
0x180134e31  mov     rcx, [rbp+37h+arg_20]
0x180134e35  test    rcx, rcx
0x180134e38  jz      short loc_180134E44
0x180134e3a  call    cs:__imp_GdipDeleteBrush
0x180134e40  mov     [rbp+37h+arg_20], rdi
0x180134e44  mov     rcx, [rbp+37h+arg_18]
0x180134e48  test    rcx, rcx
0x180134e4b  jz      short loc_180134E57
0x180134e4d  call    cs:__imp_GdipDeleteBrush
0x180134e53  mov     [rbp+37h+arg_18], rdi
0x180134e57  lea     rcx, [rbp+37h+var_80]; this
0x180134e5b  call    ??1GpImageLock@IImage@GEL@@QEAA@XZ; GEL::IImage::GpImageLock::~GpImageLock(void)
0x180134e60  xor     eax, eax
0x180134e62  jmp     short loc_180134DFF
0x180134e64  xorps   xmm0, xmm0
0x180134e67  jmp     loc_180134CD8
0x180134e6c  xorps   xmm0, xmm0
0x180134e6f  jmp     loc_180134CFD
0x180134e74  mov     r8, r15
0x180134e77  mov     rdx, [rbp+37h+arg_20]
0x180134e7b  mov     rcx, r12
0x180134e7e  call    cs:__imp_GdipFillPath
0x180134e84  jmp     short loc_180134E31
```
