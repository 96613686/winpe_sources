# SimpleSlideshowDisplay::PaintBitmap(HDC__ *)

- ea: `0x18002a138`
- end: `0x18002a422`
- name: `?PaintBitmap@SimpleSlideshowDisplay@@AEAAXPEAUHDC__@@@Z`
- size: `746`
- prototype: `void(SimpleSlideshowDisplay *__hidden this, HDC)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x180059280`
- `0x180059340`

## callees

- `0x180001f30`
- `0x180001f6c`
- `0x180009ee0`
- `0x1800259e4`
- `0x18002a138`
- `0x18002abe0`
- `0x18002b548`
- `0x18003f800`
- `0x1800587e8`

## import_xrefs

- `USER32!GetClientRect` at `0x18002a17a`
- `USER32!GetClientRect` at `0x18002a17a`
- `USER32!FillRect` at `0x18002a3f5`
- `USER32!FillRect` at `0x18002a3f5`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x18002a37c`
- `gdiplus!GdipSetImageAttributesWrapMode` at `0x18002a37c`
- `gdiplus!GdipDisposeImageAttributes` at `0x18002a3bb`
- `gdiplus!GdipDisposeImageAttributes` at `0x18002a3bb`
- `gdiplus!GdipCreateImageAttributes` at `0x18002a360`
- `gdiplus!GdipCreateImageAttributes` at `0x18002a360`
- `gdiplus!GdipFillRectangle` at `0x18002a206`
- `gdiplus!GdipFillRectangle` at `0x18002a206`
- `gdiplus!GdipDeleteBrush` at `0x18002a3c5`
- `gdiplus!GdipDeleteBrush` at `0x18002a3cf`
- `gdiplus!GdipDeleteBrush` at `0x18002a3c5`
- `gdiplus!GdipDeleteBrush` at `0x18002a3cf`
- `GDI32!GetStockObject` at `0x18002a3e5`
- `GDI32!GetStockObject` at `0x18002a3e5`
- `GDI32!GetLayout` at `0x18002a331`
- `GDI32!GetLayout` at `0x18002a331`

## pseudocode

```c
void __fastcall SimpleSlideshowDisplay::PaintBitmap(SimpleSlideshowDisplay *this, HDC a2)
{
  HWND v4; // rcx
  unsigned int v5; // r13d
  __int64 v6; // rbx
  int v7; // eax
  int Width; // edi
  int Height; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r14d
  int v13; // esi
  int v14; // r8d
  unsigned int v15; // eax
  unsigned int v16; // ecx
  int v17; // eax
  int v18; // edx
  HBRUSH StockObject; // rax
  unsigned int v20; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  int v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+78h] [rbp-88h]
  _BYTE v25[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+88h] [rbp-78h]
  _BYTE v27[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v28; // [rsp+A0h] [rbp-60h]
  struct tagRECT Rect; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v30[32]; // [rsp+C0h] [rbp-40h] BYREF
  int v31; // [rsp+E0h] [rbp-20h]
  __int64 v32; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v33; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v34; // [rsp+118h] [rbp+18h]
  int v35; // [rsp+120h] [rbp+20h]
  unsigned int v36; // [rsp+124h] [rbp+24h]

  v4 = (HWND)*((_QWORD *)this + 29);
  Rect = 0;
  GetClientRect(v4, &Rect);
  v5 = 0;
  if ( *((_QWORD *)this + 37) )
  {
    GdipUtil::BufferedPainter::BufferedPainter((GdipUtil::BufferedPainter *)v30, a2, &Rect);
    if ( v31 )
    {
LABEL_19:
      GdipUtil::BufferedPainter::~BufferedPainter((GdipUtil::BufferedPainter *)v30);
      return;
    }
    v6 = v32;
    v24 = v32;
    v20 = -16777216;
    Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v27, (const struct Gdiplus::Color *)&v20);
    v7 = GdipFillRectangle(*(_QWORD *)v6, v28);
    if ( v7 )
      *(_DWORD *)(v6 + 8) = v7;
    Width = Gdiplus::Image::GetWidth(*((Gdiplus::Image **)this + 37));
    Height = Gdiplus::Image::GetHeight(*((Gdiplus::Image **)this + 37));
    v10 = Rect.right - Rect.left;
    v11 = Rect.bottom - Rect.top;
    if ( Width > Rect.right - Rect.left
      || Height > v11
      || (v12 = 3 * Width, 3 * Width > v10)
      || (v13 = 3 * Height, 3 * Height > v11) )
    {
      v12 = Rect.right - Rect.left;
      v13 = Rect.bottom - Rect.top;
      if ( (float)((float)Width / (float)v10) <= (float)((float)Height / (float)v11) )
      {
        v20 = 0;
        v12 = Width * v11 / Height;
        v5 = (v10 - v12) / 2;
        goto LABEL_14;
      }
      v13 = Height * v10 / Width;
      v14 = v11 - v13;
    }
    else
    {
      v14 = v11 - v13;
      v5 = (v10 - v12) / 2;
    }
    v20 = v14 / 2;
LABEL_14:
    v21 = -1;
    Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v25, (const struct Gdiplus::Color *)&v21);
    Gdiplus::Graphics::FillRectangle(v24, v25, v5, v20, v12, v13);
    LODWORD(v34) = v12 + v5;
    HIDWORD(v34) = v20;
    v33 = __PAIR64__(v20, v5);
    v36 = v13 + v20;
    v35 = v5;
    if ( (GetLayout(a2) & 1) != 0 )
    {
      v15 = v33;
      v16 = HIDWORD(v33);
      v33 = v34;
      v35 = v34;
      v34 = __PAIR64__(v16, v15);
    }
    v22 = 0;
    v23 = GdipCreateImageAttributes(&v22);
    v17 = GdipSetImageAttributesWrapMode(v22, 3, 4278190080LL);
    v18 = v23;
    if ( v17 )
      v18 = v17;
    v23 = v18;
    Gdiplus::Graphics::DrawImage(v24, *((_QWORD *)this + 37), &v33);
    GdipDisposeImageAttributes(v22);
    GdipDeleteBrush(v26);
    GdipDeleteBrush(v28);
    goto LABEL_19;
  }
  StockObject = (HBRUSH)GetStockObject(4);
  FillRect(a2, &Rect, StockObject);
}

```

## disassembly

```asm
0x18002a138  mov     [rsp-8+arg_10], rbx
0x18002a13d  push    rbp
0x18002a13e  push    rsi
0x18002a13f  push    rdi
0x18002a140  push    r12
0x18002a142  push    r13
0x18002a144  push    r14
0x18002a146  push    r15
0x18002a148  lea     rbp, [rsp-30h]
0x18002a14d  sub     rsp, 130h
0x18002a154  mov     rax, cs:__security_cookie
0x18002a15b  xor     rax, rsp
0x18002a15e  mov     [rbp+60h+var_38], rax
0x18002a162  mov     r12, rdx
0x18002a165  mov     r15, rcx
0x18002a168  mov     rcx, [rcx+0E8h]; hWnd
0x18002a16f  lea     rdx, [rbp+60h+Rect]; lpRect
0x18002a173  xorps   xmm0, xmm0
0x18002a176  movups  xmmword ptr [rbp+60h+Rect.left], xmm0
0x18002a17a  call    cs:__imp_GetClientRect
0x18002a180  xor     r13d, r13d
0x18002a183  cmp     [r15+128h], r13
0x18002a18a  jz      loc_18002A3E0
0x18002a190  lea     r8, [rbp+60h+Rect]; struct tagRECT *
0x18002a194  mov     rdx, r12; HDC
0x18002a197  lea     rcx, [rbp+60h+var_A0]; this
0x18002a19b  call    ??0BufferedPainter@GdipUtil@@QEAA@PEAUHDC__@@AEBUtagRECT@@@Z; GdipUtil::BufferedPainter::BufferedPainter(HDC__ *,tagRECT const &)
0x18002a1a0  cmp     [rbp+60h+var_80], r13d
0x18002a1a4  jnz     loc_18002A3D5
0x18002a1aa  mov     rbx, [rbp+60h+var_78]
0x18002a1ae  lea     rdx, [rsp+160h+var_100]; struct Gdiplus::Color *
0x18002a1b3  lea     rcx, [rbp+60h+var_C8]; this
0x18002a1b7  mov     [rsp+160h+var_E8], rbx
0x18002a1bc  mov     [rsp+160h+var_100], 0FF000000h
0x18002a1c4  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x18002a1c9  mov     eax, [rbp+60h+Rect.bottom]
0x18002a1cc  sub     eax, [rbp+60h+Rect.top]
0x18002a1cf  movd    xmm3, [rbp+60h+Rect.top]
0x18002a1d4  movd    xmm2, [rbp+60h+Rect.left]
0x18002a1d9  mov     rdx, [rbp+60h+var_C0]
0x18002a1dd  mov     rcx, [rbx]
0x18002a1e0  movd    xmm1, eax
0x18002a1e4  mov     eax, [rbp+60h+Rect.right]
0x18002a1e7  sub     eax, [rbp+60h+Rect.left]
0x18002a1ea  cvtdq2ps xmm1, xmm1
0x18002a1ed  movd    xmm0, eax
0x18002a1f1  cvtdq2ps xmm0, xmm0
0x18002a1f4  movss   [rsp+160h+var_138], xmm1
0x18002a1fa  cvtdq2ps xmm3, xmm3
0x18002a1fd  cvtdq2ps xmm2, xmm2
0x18002a200  movss   [rsp+160h+var_140], xmm0
0x18002a206  call    cs:__imp_GdipFillRectangle
0x18002a20c  test    eax, eax
0x18002a20e  jz      short loc_18002A213
0x18002a210  mov     [rbx+8], eax
0x18002a213  mov     rcx, [r15+128h]; this
0x18002a21a  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x18002a21f  mov     rcx, [r15+128h]; this
0x18002a226  mov     edi, eax
0x18002a228  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x18002a22d  mov     ecx, [rbp+60h+Rect.right]
0x18002a230  mov     ebx, eax
0x18002a232  mov     r8d, [rbp+60h+Rect.bottom]
0x18002a236  sub     ecx, [rbp+60h+Rect.left]
0x18002a239  sub     r8d, [rbp+60h+Rect.top]
0x18002a23d  cmp     edi, ecx
0x18002a23f  jg      short loc_18002A26C
0x18002a241  cmp     eax, r8d
0x18002a244  jg      short loc_18002A26C
0x18002a246  lea     r14d, [rdi+rdi*2]
0x18002a24a  cmp     r14d, ecx
0x18002a24d  jg      short loc_18002A26C
0x18002a24f  lea     esi, [rax+rax*2]
0x18002a252  cmp     esi, r8d
0x18002a255  jg      short loc_18002A26C
0x18002a257  sub     ecx, r14d
0x18002a25a  mov     eax, ecx
0x18002a25c  mov     ecx, 2
0x18002a261  cdq
0x18002a262  idiv    ecx
0x18002a264  sub     r8d, esi
0x18002a267  mov     r13d, eax
0x18002a26a  jmp     short loc_18002A2AE
0x18002a26c  movd    xmm3, edi
0x18002a270  mov     r14d, ecx
0x18002a273  movd    xmm0, ecx
0x18002a277  mov     esi, r8d
0x18002a27a  movd    xmm2, ebx
0x18002a27e  movd    xmm1, r8d
0x18002a283  cvtdq2ps xmm3, xmm3
0x18002a286  cvtdq2ps xmm0, xmm0
0x18002a289  cvtdq2ps xmm2, xmm2
0x18002a28c  cvtdq2ps xmm1, xmm1
0x18002a28f  divss   xmm3, xmm0
0x18002a293  divss   xmm2, xmm1
0x18002a297  comiss  xmm3, xmm2
0x18002a29a  jbe     short loc_18002A2BA
0x18002a29c  imul    ecx, ebx
0x18002a29f  mov     eax, ecx
0x18002a2a1  mov     ecx, 2
0x18002a2a6  cdq
0x18002a2a7  idiv    edi
0x18002a2a9  mov     esi, eax
0x18002a2ab  sub     r8d, eax
0x18002a2ae  mov     eax, r8d
0x18002a2b1  cdq
0x18002a2b2  idiv    ecx
0x18002a2b4  mov     [rsp+160h+var_100], eax
0x18002a2b8  jmp     short loc_18002A2DA
0x18002a2ba  mov     eax, r8d
0x18002a2bd  mov     [rsp+160h+var_100], r13d
0x18002a2c2  imul    eax, edi
0x18002a2c5  cdq
0x18002a2c6  idiv    ebx
0x18002a2c8  sub     ecx, eax
0x18002a2ca  mov     r14d, eax
0x18002a2cd  mov     eax, ecx
0x18002a2cf  mov     ecx, 2
0x18002a2d4  cdq
0x18002a2d5  idiv    ecx
0x18002a2d7  mov     r13d, eax
0x18002a2da  lea     rdx, [rsp+160h+var_FC]; struct Gdiplus::Color *
0x18002a2df  mov     [rsp+160h+var_FC], 0FFFFFFFFh
0x18002a2e7  lea     rcx, [rbp+60h+var_E0]; this
0x18002a2eb  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x18002a2f0  mov     r9d, [rsp+160h+var_100]
0x18002a2f5  lea     rdx, [rbp+60h+var_E0]
0x18002a2f9  mov     rcx, [rsp+160h+var_E8]
0x18002a2fe  mov     r8d, r13d
0x18002a301  mov     [rsp+160h+var_138], esi
0x18002a305  mov     [rsp+160h+var_140], r14d
0x18002a30a  call    ?FillRectangle@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@HHHH@Z; Gdiplus::Graphics::FillRectangle(Gdiplus::Brush const *,int,int,int,int)
0x18002a30f  mov     ecx, [rsp+160h+var_100]
0x18002a313  lea     eax, [r14+r13]
0x18002a317  mov     dword ptr [rbp+60h+var_48], eax
0x18002a31a  mov     dword ptr [rbp+60h+var_50+4], ecx
0x18002a31d  mov     dword ptr [rbp+60h+var_48+4], ecx
0x18002a320  lea     eax, [rsi+rcx]
0x18002a323  mov     dword ptr [rbp+60h+var_50], r13d
0x18002a327  mov     rcx, r12; hdc
0x18002a32a  mov     [rbp+60h+var_3C], eax
0x18002a32d  mov     [rbp+60h+var_40], r13d
0x18002a331  call    cs:__imp_GetLayout
0x18002a337  test    al, 1
0x18002a339  jz      short loc_18002A352
0x18002a33b  mov     rdx, [rbp+60h+var_48]
0x18002a33f  mov     eax, dword ptr [rbp+60h+var_50]
0x18002a342  mov     ecx, dword ptr [rbp+60h+var_50+4]
0x18002a345  mov     [rbp+60h+var_50], rdx
0x18002a349  mov     [rbp+60h+var_40], edx
0x18002a34c  mov     dword ptr [rbp+60h+var_48], eax
0x18002a34f  mov     dword ptr [rbp+60h+var_48+4], ecx
0x18002a352  lea     rcx, [rsp+160h+var_F8]
0x18002a357  mov     [rsp+160h+var_F8], 0
0x18002a360  call    cs:__imp_GdipCreateImageAttributes
0x18002a366  mov     rcx, [rsp+160h+var_F8]
0x18002a36b  xor     r9d, r9d
0x18002a36e  mov     r8d, 0FF000000h
0x18002a374  mov     [rsp+160h+var_F0], eax
0x18002a378  lea     edx, [r9+3]
0x18002a37c  call    cs:__imp_GdipSetImageAttributesWrapMode
0x18002a382  mov     edx, [rsp+160h+var_F0]
0x18002a386  lea     r8, [rbp+60h+var_50]
0x18002a38a  mov     rcx, [rsp+160h+var_E8]
0x18002a38f  test    eax, eax
0x18002a391  cmovnz  edx, eax
0x18002a394  lea     rax, [rsp+160h+var_F8]
0x18002a399  mov     [rsp+160h+var_118], rax
0x18002a39e  mov     [rsp+160h+var_F0], edx
0x18002a3a2  mov     rdx, [r15+128h]
0x18002a3a9  mov     [rsp+160h+var_128], ebx
0x18002a3ad  mov     [rsp+160h+var_130], edi
0x18002a3b1  call    ?DrawImage@Graphics@Gdiplus@@QEAA?AW4Status@2@PEAVImage@2@PEBVPoint@2@HHHHHW4Unit@2@PEBVImageAttributes@2@P6AHPEAX@Z4@Z; Gdiplus::Graphics::DrawImage(Gdiplus::Image *,Gdiplus::Point const *,int,int,int,int,int,Gdiplus::Unit,Gdiplus::ImageAttributes const *,int (*)(void *),void *)
0x18002a3b6  mov     rcx, [rsp+160h+var_F8]
0x18002a3bb  call    cs:__imp_GdipDisposeImageAttributes
0x18002a3c1  mov     rcx, [rbp+60h+var_D8]
0x18002a3c5  call    cs:__imp_GdipDeleteBrush
0x18002a3cb  mov     rcx, [rbp+60h+var_C0]
0x18002a3cf  call    cs:__imp_GdipDeleteBrush
0x18002a3d5  lea     rcx, [rbp+60h+var_A0]; this
0x18002a3d9  call    ??1BufferedPainter@GdipUtil@@QEAA@XZ; GdipUtil::BufferedPainter::~BufferedPainter(void)
0x18002a3de  jmp     short loc_18002A3FB
0x18002a3e0  mov     ecx, 4; i
0x18002a3e5  call    cs:__imp_GetStockObject
0x18002a3eb  lea     rdx, [rbp+60h+Rect]; lprc
0x18002a3ef  mov     rcx, r12; hDC
0x18002a3f2  mov     r8, rax; hbr
0x18002a3f5  call    cs:__imp_FillRect
0x18002a3fb  mov     rcx, [rbp+60h+var_38]
0x18002a3ff  xor     rcx, rsp; StackCookie
0x18002a402  call    __security_check_cookie
0x18002a407  mov     rbx, [rsp+160h+arg_10]
0x18002a40f  add     rsp, 130h
0x18002a416  pop     r15
0x18002a418  pop     r14
0x18002a41a  pop     r13
0x18002a41c  pop     r12
0x18002a41e  pop     rdi
0x18002a41f  pop     rsi
0x18002a420  pop     rbp
0x18002a421  retn
```
