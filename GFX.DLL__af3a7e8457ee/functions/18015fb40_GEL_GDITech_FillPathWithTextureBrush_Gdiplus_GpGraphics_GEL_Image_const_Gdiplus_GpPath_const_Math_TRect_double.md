# GEL::GDITech::FillPathWithTextureBrush(Gdiplus::GpGraphics &,GEL::Image const &,Gdiplus::GpPath const *,Math::TRect<double> const &,Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Math::TAffine3x3<double> const &,Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &,Gdiplus::WrapMode)

- ea: `0x18015fb40`
- end: `0x18015fd77`
- name: `?FillPathWithTextureBrush@GDITech@GEL@@CA?AW4Status@Gdiplus@@AEAVGpGraphics@4@AEBVImage@2@PEBVGpPath@4@AEBU?$TRect@N@Math@@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@9@AEBU?$TAffine3x3@N@9@4W4WrapMode@4@@Z`
- size: `567`
- prototype: `__int64 __fastcall(int, int, int, int, Gfx::Rect *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180062b84`

## callees

- `0x180015000`
- `0x180015460`
- `0x1800154d0`
- `0x180053330`
- `0x180061f98`
- `0x180062490`
- `0x1800626b0`
- `0x18015fb40`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!round` at `0x18015fb87`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18015fb9d`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18015fbc8`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18015fbed`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18015fb87`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18015fb9d`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18015fbc8`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18015fbed`
- `gdiplus!GdipFillPath` at `0x18015fcb6`
- `gdiplus!GdipFillPath` at `0x18015fd6e`
- `gdiplus!GdipFillPath` at `0x18015fcb6`
- `gdiplus!GdipFillPath` at `0x18015fd6e`
- `gdiplus!GdipSetTextureTransform` at `0x18015fca6`
- `gdiplus!GdipSetTextureTransform` at `0x18015fca6`
- `gdiplus!GdipCreateTexture2I` at `0x18015fc4e`
- `gdiplus!GdipCreateTexture2I` at `0x18015fc4e`
- `gdiplus!GdipCreateSolidFill` at `0x18015fd17`
- `gdiplus!GdipCreateSolidFill` at `0x18015fd17`
- `gdiplus!GdipDeleteBrush` at `0x18015fcda`
- `gdiplus!GdipDeleteBrush` at `0x18015fd2a`
- `gdiplus!GdipDeleteBrush` at `0x18015fd3d`
- `gdiplus!GdipDeleteBrush` at `0x18015fcda`
- `gdiplus!GdipDeleteBrush` at `0x18015fd2a`
- `gdiplus!GdipDeleteBrush` at `0x18015fd3d`
- `gdiplus!GdipDeleteMatrix` at `0x18015fcc7`
- `gdiplus!GdipDeleteMatrix` at `0x18015fcc7`

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
0x18015fb40  mov     rax, rsp
0x18015fb43  mov     [rax+8], rbx
0x18015fb47  mov     [rax+20h], r9
0x18015fb4b  mov     [rax+10h], rdx
0x18015fb4f  push    rbp
0x18015fb50  push    rsi
0x18015fb51  push    rdi
0x18015fb52  push    r12
0x18015fb54  push    r13
0x18015fb56  push    r14
0x18015fb58  push    r15
0x18015fb5a  lea     rbp, [rax-3Fh]
0x18015fb5e  sub     rsp, 0A0h
0x18015fb65  mov     r15, r8
0x18015fb68  mov     r12, rcx
0x18015fb6b  mov     r8b, 1; unsigned __int8
0x18015fb6e  lea     rcx, [rbp+37h+var_80]; this
0x18015fb72  call    ??0GpImageLock@IImage@GEL@@QEAA@AEBU12@E@Z; GEL::IImage::GpImageLock::GpImageLock(GEL::IImage const &,uchar)
0x18015fb77  mov     rax, [rbp+37h+var_68]
0x18015fb7b  mov     [rbp+37h+var_90], rax
0x18015fb7f  mov     rbx, [rbp+37h+arg_20]
0x18015fb83  movsd   xmm0, qword ptr [rbx]; X
0x18015fb87  call    cs:__imp_round
0x18015fb8d  cvttsd2si esi, xmm0
0x18015fb91  xor     edi, edi
0x18015fb93  test    esi, esi
0x18015fb95  cmovle  esi, edi
0x18015fb98  movsd   xmm0, qword ptr [rbx+8]; X
0x18015fb9d  call    cs:__imp_round
0x18015fba3  cvttsd2si r14d, xmm0
0x18015fba8  test    r14d, r14d
0x18015fbab  cmovle  r14d, edi
0x18015fbaf  mov     rcx, rbx; this
0x18015fbb2  call    ?FIsEmpty@Rect@Gfx@@QEBA_NXZ; Gfx::Rect::FIsEmpty(void)
0x18015fbb7  test    al, al
0x18015fbb9  jnz     loc_18015FD54
0x18015fbbf  movsd   xmm0, qword ptr [rbx+10h]
0x18015fbc4  subsd   xmm0, qword ptr [rbx]; X
0x18015fbc8  call    cs:__imp_round
0x18015fbce  cvttsd2si r13d, xmm0
0x18015fbd3  mov     rcx, rbx; this
0x18015fbd6  call    ?FIsEmpty@Rect@Gfx@@QEBA_NXZ; Gfx::Rect::FIsEmpty(void)
0x18015fbdb  test    al, al
0x18015fbdd  jnz     loc_18015FD5C
0x18015fbe3  movsd   xmm0, qword ptr [rbx+18h]
0x18015fbe8  subsd   xmm0, qword ptr [rbx+8]; X
0x18015fbed  call    cs:__imp_round
0x18015fbf3  cvttsd2si edi, xmm0
0x18015fbf7  mov     rcx, [rbp+37h+arg_8]; this
0x18015fbfb  call    ?GetPixelWidth@Image@GEL@@UEBAHXZ; GEL::Image::GetPixelWidth(void)
0x18015fc00  mov     ebx, eax
0x18015fc02  mov     rcx, [rbp+37h+arg_8]; this
0x18015fc06  call    ?GetPixelHeight@Image@GEL@@UEBAHXZ; GEL::Image::GetPixelHeight(void)
0x18015fc0b  lea     ecx, [rsi+r13]
0x18015fc0f  mov     r8d, ebx
0x18015fc12  sub     r8d, esi
0x18015fc15  cmp     ecx, ebx
0x18015fc17  cmovle  r8d, r13d
0x18015fc1b  lea     ecx, [r14+rdi]
0x18015fc1f  mov     edx, eax
0x18015fc21  sub     edx, r14d
0x18015fc24  cmp     ecx, eax
0x18015fc26  cmovle  edx, edi
0x18015fc29  xor     edi, edi
0x18015fc2b  mov     [rbp+37h+arg_18], rdi
0x18015fc2f  lea     rax, [rbp+37h+arg_18]
0x18015fc33  mov     [rsp+30h], rax
0x18015fc38  mov     dword ptr [rsp+0D0h+var_A8], edx
0x18015fc3c  mov     [rsp+0D0h+var_B0], r8d
0x18015fc41  mov     r9d, r14d
0x18015fc44  mov     r8d, esi
0x18015fc47  mov     edx, [rbp+37h+arg_38]
0x18015fc4a  mov     rcx, [rbp+37h+var_90]
0x18015fc4e  call    cs:__imp_GdipCreateTexture2I
0x18015fc54  test    eax, eax
0x18015fc56  jnz     loc_18015FD0A
0x18015fc5c  cmp     [rbp+37h+arg_18], rdi
0x18015fc60  jz      loc_18015FD0A
0x18015fc66  movd    xmm0, esi
0x18015fc6a  cvtdq2pd xmm0, xmm0
0x18015fc6e  movsd   [rbp+37h+var_90], xmm0
0x18015fc73  movd    xmm1, r14d
0x18015fc78  cvtdq2pd xmm1, xmm1
0x18015fc7c  movsd   [rbp+37h+var_88], xmm1
0x18015fc81  mov     r8, [rbp+37h+arg_28]
0x18015fc85  lea     rdx, [rbp+37h+var_90]
0x18015fc89  lea     rcx, [rbp+37h+var_60]
0x18015fc8d  call    ??$?DNNN@Math@@YA?AU?$TAffine3x3@N@0@AEBU?$TTranslation2@N@0@AEBU10@@Z; Math::operator*<double,double,double>(Math::TTranslation2<double> const &,Math::TAffine3x3<double> const &)
0x18015fc92  mov     rdx, rax
0x18015fc95  lea     rcx, [rbp+37h+arg_30]
0x18015fc99  call    ??$?0U?$TAffine3x3@N@Math@@$0A@@GpMatrixHolder@Gfx@@QEAA@AEBU?$TAffine3x3@N@Math@@@Z; Gfx::GpMatrixHolder::GpMatrixHolder(Math::TAffine3x3<double> const &)
0x18015fc9e  mov     rdx, [rbp+37h+arg_30]
0x18015fca2  mov     rcx, [rbp+37h+arg_18]
0x18015fca6  call    cs:__imp_GdipSetTextureTransform
0x18015fcac  mov     r8, r15
0x18015fcaf  mov     rdx, [rbp+37h+arg_18]
0x18015fcb3  mov     rcx, r12
0x18015fcb6  call    cs:__imp_GdipFillPath
0x18015fcbc  mov     ebx, eax
0x18015fcbe  mov     rcx, [rbp+37h+arg_30]
0x18015fcc2  test    rcx, rcx
0x18015fcc5  jz      short loc_18015FCD1
0x18015fcc7  call    cs:__imp_GdipDeleteMatrix
0x18015fccd  mov     [rbp+37h+arg_30], rdi
0x18015fcd1  mov     rcx, [rbp+37h+arg_18]
0x18015fcd5  test    rcx, rcx
0x18015fcd8  jz      short loc_18015FCE4
0x18015fcda  call    cs:__imp_GdipDeleteBrush
0x18015fce0  mov     [rbp+37h+arg_18], rdi
0x18015fce4  lea     rcx, [rbp+37h+var_80]; this
0x18015fce8  call    ??1GpImageLock@IImage@GEL@@QEAA@XZ; GEL::IImage::GpImageLock::~GpImageLock(void)
0x18015fced  mov     eax, ebx
0x18015fcef  mov     rbx, [rsp+0D0h+arg_0]
0x18015fcf7  add     rsp, 0A0h
0x18015fcfe  pop     r15
0x18015fd00  pop     r14
0x18015fd02  pop     r13
0x18015fd04  pop     r12
0x18015fd06  pop     rdi
0x18015fd07  pop     rsi
0x18015fd08  pop     rbp
0x18015fd09  retn
0x18015fd0a  mov     [rbp+37h+arg_20], rdi
0x18015fd0e  lea     rdx, [rbp+37h+arg_20]
0x18015fd12  mov     ecx, 0FF0000FFh
0x18015fd17  call    cs:__imp_GdipCreateSolidFill
0x18015fd1d  test    eax, eax
0x18015fd1f  jz      short loc_18015FD64
0x18015fd21  mov     rcx, [rbp+37h+arg_20]
0x18015fd25  test    rcx, rcx
0x18015fd28  jz      short loc_18015FD34
0x18015fd2a  call    cs:__imp_GdipDeleteBrush
0x18015fd30  mov     [rbp+37h+arg_20], rdi
0x18015fd34  mov     rcx, [rbp+37h+arg_18]
0x18015fd38  test    rcx, rcx
0x18015fd3b  jz      short loc_18015FD47
0x18015fd3d  call    cs:__imp_GdipDeleteBrush
0x18015fd43  mov     [rbp+37h+arg_18], rdi
0x18015fd47  lea     rcx, [rbp+37h+var_80]; this
0x18015fd4b  call    ??1GpImageLock@IImage@GEL@@QEAA@XZ; GEL::IImage::GpImageLock::~GpImageLock(void)
0x18015fd50  xor     eax, eax
0x18015fd52  jmp     short loc_18015FCEF
0x18015fd54  xorps   xmm0, xmm0
0x18015fd57  jmp     loc_18015FBC8
0x18015fd5c  xorps   xmm0, xmm0
0x18015fd5f  jmp     loc_18015FBED
0x18015fd64  mov     r8, r15
0x18015fd67  mov     rdx, [rbp+37h+arg_20]
0x18015fd6b  mov     rcx, r12
0x18015fd6e  call    cs:__imp_GdipFillPath
0x18015fd74  jmp     short loc_18015FD21
```
