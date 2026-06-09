# xgc::CDeviceContext::DrawImagePlus(uchar *,Gdiplus::WrapMode,Gdiplus::Point const (&)[4],Gdiplus::Rect const &,int,int,int,int,int)

- ea: `0x180025f30`
- end: `0x1800260fa`
- name: `?DrawImagePlus@CDeviceContext@xgc@@QEAAXPEAEW4WrapMode@Gdiplus@@AEAY03$$CBVPoint@4@AEBVRect@4@HHHHH@Z`
- size: `458`
- prototype: `void __high(unsigned __int8 *, enum Gdiplus::WrapMode, const struct Gdiplus::Point (*)[4], const struct Gdiplus::Rect *, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800255bc`

## callees

- `0x180011b0c`
- `0x180024440`
- `0x1800246a8`
- `0x180024998`
- `0x180024ad4`
- `0x180025f30`
- `0x180027724`

## import_xrefs

- `gdiplus!GdipDeleteMatrix` at `0x1800260ba`
- `gdiplus!GdipDeleteMatrix` at `0x1800260ba`
- `gdiplus!GdipSetTextureWrapMode` at `0x180026088`
- `gdiplus!GdipSetTextureWrapMode` at `0x180026088`
- `gdiplus!GdipFillRectangleI` at `0x180026078`
- `gdiplus!GdipFillRectangleI` at `0x180026078`
- `gdiplus!GdipSetTextureTransform` at `0x180026047`
- `gdiplus!GdipSetTextureTransform` at `0x180026047`
- `gdiplus!GdipDisposeImage` at `0x1800260cd`
- `gdiplus!GdipDisposeImage` at `0x1800260cd`
- `gdiplus!GdipDeleteBrush` at `0x1800260c3`
- `gdiplus!GdipDeleteBrush` at `0x1800260c3`
- `gdiplus!GdipFillPolygonI` at `0x1800260a9`
- `gdiplus!GdipFillPolygonI` at `0x1800260a9`

## pseudocode

```c
_UNKNOWN **__fastcall xgc::CDeviceContext::DrawImagePlus(
        __int64 a1,
        unsigned __int8 *a2,
        unsigned int a3,
        int *a4,
        unsigned int *a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9,
        int a10)
{
  _UNKNOWN **result; // rax
  __int64 v14; // rbx
  __int64 v15; // rdi
  int v16; // eax
  int v17; // [rsp+28h] [rbp-91h]
  _QWORD v18[2]; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v19[2]; // [rsp+58h] [rbp-61h] BYREF
  _BYTE v20[8]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v21; // [rsp+70h] [rbp-49h]
  _BYTE v22[8]; // [rsp+80h] [rbp-39h] BYREF
  __int64 v23; // [rsp+88h] [rbp-31h]
  _UNKNOWN *retaddr; // [rsp+F0h] [rbp+37h] BYREF

  result = &retaddr;
  if ( a8 > 0 && a9 > 0 )
  {
    xgc::GdiSurface::GdiSurface((xgc::GdiSurface *)v19, *(HDC *)(a1 + 32), (unsigned __int64 *)(a1 + 312));
    Gdiplus::Bitmap::Bitmap((Gdiplus::Bitmap *)v20, a8, a9, a10, v17, a2);
    Gdiplus::TextureBrush::TextureBrush(v22, v20, a3);
    Gdiplus::Matrix::Matrix(
      (Gdiplus::Matrix *)v18,
      (float)(a4[2] - *a4) / (float)a8,
      (float)(a4[3] - a4[1]) / (float)a8,
      (float)(a4[6] - *a4) / (float)a9,
      (float)(a4[7] - a4[1]) / (float)a9,
      (float)*a4,
      (float)a4[1]);
    Gdiplus::Matrix::Translate(v18);
    v14 = v23;
    GdipSetTextureTransform(v23, v18[0]);
    if ( a3 == 4 )
    {
      GdipSetTextureWrapMode(v14, 3);
      v15 = v19[0];
      v16 = GdipFillPolygonI(*(_QWORD *)v19[0], v14, a4, 4, 0);
    }
    else
    {
      v15 = v19[0];
      v16 = GdipFillRectangleI(*(_QWORD *)v19[0], v14, *a5, a5[1], a5[2], a5[3]);
    }
    if ( v16 )
      *(_DWORD *)(v15 + 8) = v16;
    GdipDeleteMatrix(v18[0]);
    GdipDeleteBrush(v14);
    GdipDisposeImage(v21);
    return (_UNKNOWN **)std::_Ptr_base<ID2D1RenderTarget>::_Decref(v19);
  }
  return result;
}

```

## disassembly

```asm
0x180025f30  mov     rax, rsp
0x180025f33  push    rbp
0x180025f34  push    rbx
0x180025f35  push    rsi
0x180025f36  push    rdi
0x180025f37  push    r14
0x180025f39  push    r15
0x180025f3b  lea     rbp, [rax-37h]
0x180025f3f  sub     rsp, 0B8h
0x180025f46  mov     edi, [rbp+2Fh+arg_38]
0x180025f49  mov     rsi, r9
0x180025f4c  movaps  xmmword ptr [rax-48h], xmm6
0x180025f50  mov     r14d, r8d
0x180025f53  movaps  xmmword ptr [rax-58h], xmm7
0x180025f57  mov     r15, rdx
0x180025f5a  test    edi, edi
0x180025f5c  jle     loc_1800260DC
0x180025f62  mov     ebx, [rbp+2Fh+arg_40]
0x180025f65  test    ebx, ebx
0x180025f67  jle     loc_1800260DC
0x180025f6d  mov     rdx, [rcx+20h]; HDC
0x180025f71  lea     r8, [rcx+138h]; unsigned __int64 *
0x180025f78  lea     rcx, [rbp+2Fh+var_90]; this
0x180025f7c  call    ??0GdiSurface@xgc@@QEAA@PEAUHDC__@@AEA_K@Z; xgc::GdiSurface::GdiSurface(HDC__ *,unsigned __int64 &)
0x180025f81  mov     r9d, [rbp+2Fh+arg_48]; int
0x180025f88  lea     rcx, [rbp+2Fh+var_80]; this
0x180025f8c  mov     r8d, ebx; int
0x180025f8f  mov     [rsp+0E0h+var_B8], r15; unsigned __int8 *
0x180025f94  mov     edx, edi; int
0x180025f96  call    ??0Bitmap@Gdiplus@@QEAA@HHHHPEAE@Z; Gdiplus::Bitmap::Bitmap(int,int,int,int,uchar *)
0x180025f9b  mov     r8d, r14d
0x180025f9e  mov     [rsp+0E0h+var_B0], ebx
0x180025fa2  lea     rdx, [rbp+2Fh+var_80]
0x180025fa6  mov     dword ptr [rsp+0E0h+var_B8], edi
0x180025faa  lea     rcx, [rbp+2Fh+var_68]
0x180025fae  call    ??0TextureBrush@Gdiplus@@QEAA@PEAVImage@1@W4WrapMode@1@HHHH@Z; Gdiplus::TextureBrush::TextureBrush(Gdiplus::Image *,Gdiplus::WrapMode,int,int,int,int)
0x180025fb3  mov     eax, [rsi+1Ch]
0x180025fb6  lea     rcx, [rbp+2Fh+var_A0]; this
0x180025fba  sub     eax, [rsi+4]
0x180025fbd  movd    xmm5, dword ptr [rsi+4]
0x180025fc2  movd    xmm6, dword ptr [rsi]
0x180025fc6  movd    xmm0, ebx
0x180025fca  movd    xmm4, eax
0x180025fce  mov     eax, [rsi+18h]
0x180025fd1  sub     eax, [rsi]
0x180025fd3  cvtdq2ps xmm0, xmm0
0x180025fd6  movd    xmm3, eax
0x180025fda  mov     eax, [rsi+0Ch]
0x180025fdd  sub     eax, [rsi+4]
0x180025fe0  cvtdq2ps xmm4, xmm4
0x180025fe3  movd    xmm2, eax
0x180025fe7  mov     eax, [rsi+8]
0x180025fea  sub     eax, [rsi]
0x180025fec  cvtdq2ps xmm3, xmm3
0x180025fef  movd    xmm1, eax
0x180025ff3  cvtdq2ps xmm1, xmm1
0x180025ff6  cvtdq2ps xmm2, xmm2
0x180025ff9  divss   xmm4, xmm0
0x180025ffd  movd    xmm7, edi
0x180026001  cvtdq2ps xmm7, xmm7
0x180026004  cvtdq2ps xmm5, xmm5
0x180026007  cvtdq2ps xmm6, xmm6
0x18002600a  movss   [rsp+0E0h+var_B0], xmm5; float
0x180026010  divss   xmm1, xmm7; float
0x180026014  divss   xmm3, xmm0; float
0x180026018  divss   xmm2, xmm7; float
0x18002601c  movss   dword ptr [rsp+0E0h+var_B8], xmm6; float
0x180026022  movss   [rsp+0E0h+var_C0], xmm4; float
0x180026028  call    ??0Matrix@Gdiplus@@QEAA@MMMMMM@Z; Gdiplus::Matrix::Matrix(float,float,float,float,float,float)
0x18002602d  xorps   xmm2, xmm2
0x180026030  lea     rcx, [rbp+2Fh+var_A0]
0x180026034  xorps   xmm1, xmm1
0x180026037  call    ?Translate@Matrix@Gdiplus@@QEAA?AW4Status@2@MMW4MatrixOrder@2@@Z; Gdiplus::Matrix::Translate(float,float,Gdiplus::MatrixOrder)
0x18002603c  mov     rbx, [rbp+2Fh+var_60]
0x180026040  mov     rdx, [rbp+2Fh+var_A0]
0x180026044  mov     rcx, rbx
0x180026047  call    cs:__imp_GdipSetTextureTransform
0x18002604d  cmp     r14d, 4
0x180026051  jz      short loc_180026080
0x180026053  mov     r8, [rbp+2Fh+arg_20]
0x180026057  mov     rdx, rbx
0x18002605a  mov     rdi, [rbp+2Fh+var_90]
0x18002605e  mov     eax, [r8+0Ch]
0x180026062  mov     r9d, [r8+4]
0x180026066  mov     rcx, [rdi]
0x180026069  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18002606d  mov     eax, [r8+8]
0x180026071  mov     r8d, [r8]
0x180026074  mov     [rsp+0E0h+var_C0], eax
0x180026078  call    cs:__imp_GdipFillRectangleI
0x18002607e  jmp     short loc_1800260AF
0x180026080  mov     edx, 3
0x180026085  mov     rcx, rbx
0x180026088  call    cs:__imp_GdipSetTextureWrapMode
0x18002608e  mov     rdi, [rbp+2Fh+var_90]
0x180026092  mov     r9d, 4
0x180026098  mov     r8, rsi
0x18002609b  mov     [rsp+0E0h+var_C0], 0
0x1800260a3  mov     rdx, rbx
0x1800260a6  mov     rcx, [rdi]
0x1800260a9  call    cs:__imp_GdipFillPolygonI
0x1800260af  test    eax, eax
0x1800260b1  jz      short loc_1800260B6
0x1800260b3  mov     [rdi+8], eax
0x1800260b6  mov     rcx, [rbp+2Fh+var_A0]
0x1800260ba  call    cs:__imp_GdipDeleteMatrix
0x1800260c0  mov     rcx, rbx
0x1800260c3  call    cs:__imp_GdipDeleteBrush
0x1800260c9  mov     rcx, [rbp+2Fh+var_78]
0x1800260cd  call    cs:__imp_GdipDisposeImage
0x1800260d3  lea     rcx, [rbp+2Fh+var_90]
0x1800260d7  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x1800260dc  lea     r11, [rsp+0E0h+var_28]
0x1800260e4  movaps  xmm6, xmmword ptr [r11-18h]
0x1800260e9  movaps  xmm7, xmmword ptr [r11-28h]
0x1800260ee  mov     rsp, r11
0x1800260f1  pop     r15
0x1800260f3  pop     r14
0x1800260f5  pop     rdi
0x1800260f6  pop     rsi
0x1800260f7  pop     rbx
0x1800260f8  pop     rbp
0x1800260f9  retn
```
