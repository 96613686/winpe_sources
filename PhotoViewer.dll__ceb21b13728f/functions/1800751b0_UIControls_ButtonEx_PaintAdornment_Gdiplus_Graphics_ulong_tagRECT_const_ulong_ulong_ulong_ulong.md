# UIControls::ButtonEx::PaintAdornment(Gdiplus::Graphics &,ulong,tagRECT const &,ulong,ulong,ulong,ulong)

- ea: `0x1800751b0`
- end: `0x1800754c1`
- name: `?PaintAdornment@ButtonEx@UIControls@@IEAAXAEAVGraphics@Gdiplus@@KAEBUtagRECT@@KKKK@Z`
- size: `785`
- prototype: `void(UIControls::ButtonEx *__hidden this, struct Gdiplus::Graphics *, unsigned int, const struct tagRECT *, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x1800754d0`
- `0x180075ec0`

## callees

- `0x18002479c`
- `0x1800259e4`
- `0x18002b548`
- `0x1800332f8`
- `0x180033364`
- `0x18003342c`
- `0x18003628c`
- `0x180036350`
- `0x180036720`
- `0x18003860c`
- `0x18005c71c`
- `0x18006e6a4`
- `0x18007472c`
- `0x1800751b0`

## import_xrefs

- `gdiplus!GdipDeletePen` at `0x180075380`
- `gdiplus!GdipDeletePen` at `0x1800753b4`
- `gdiplus!GdipDeletePen` at `0x18007541f`
- `gdiplus!GdipDeletePen` at `0x180075380`
- `gdiplus!GdipDeletePen` at `0x1800753b4`
- `gdiplus!GdipDeletePen` at `0x18007541f`
- `gdiplus!GdipDeletePath` at `0x18007520a`
- `gdiplus!GdipDeletePath` at `0x180075435`
- `gdiplus!GdipDeletePath` at `0x18007520a`
- `gdiplus!GdipDeletePath` at `0x180075435`
- `gdiplus!GdipDeleteBrush` at `0x180075305`
- `gdiplus!GdipDeleteBrush` at `0x18007532e`
- `gdiplus!GdipDeleteBrush` at `0x180075305`
- `gdiplus!GdipDeleteBrush` at `0x18007532e`

## pseudocode

```c
void __fastcall UIControls::ButtonEx::PaintAdornment(
        UIControls::ButtonEx *this,
        struct Gdiplus::Graphics *a2,
        __int16 a3,
        const struct tagRECT *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  int v11; // eax
  unsigned int v12; // r12d
  __m128i v13; // xmm1
  float top; // xmm0_4
  unsigned int v15; // xmm0_4
  LONG v16; // ecx
  int v17; // ebx
  unsigned int v18; // edi
  int v19; // eax
  int v20; // eax
  LONG left; // eax
  LONG v22; // r8d
  int v23; // ecx
  int v24; // edx
  unsigned int SysGdiplusColor; // eax
  unsigned int v26; // [rsp+28h] [rbp-59h]
  unsigned __int64 v27; // [rsp+38h] [rbp-49h] BYREF
  unsigned int v28; // [rsp+40h] [rbp-41h]
  __int64 v29; // [rsp+48h] [rbp-39h] BYREF
  int v30; // [rsp+50h] [rbp-31h]
  __int64 v31; // [rsp+58h] [rbp-29h] BYREF
  int v32; // [rsp+60h] [rbp-21h]
  int v33; // [rsp+64h] [rbp-1Dh]
  char v34[8]; // [rsp+68h] [rbp-19h] BYREF
  __int64 v35; // [rsp+70h] [rbp-11h]
  char v36[8]; // [rsp+80h] [rbp-1h] BYREF
  __int64 v37; // [rsp+88h] [rbp+7h]
  UIControls::ButtonEx *v38; // [rsp+C8h] [rbp+47h] BYREF
  unsigned int v39; // [rsp+D8h] [rbp+57h] BYREF

  v38 = this;
  if ( (a3 & 0x1000) != 0 )
  {
    GdipUtil::RoundRectPath::RoundRectPath((GdipUtil::RoundRectPath *)&v31, a4, 3u);
    v11 = v32;
    v32 = 0;
    if ( v11 )
    {
LABEL_3:
      GdipDeletePath(v31);
      return;
    }
    v12 = a6;
    if ( a6 == a7 )
    {
      v39 = a6;
      Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v36, (const struct Gdiplus::Color *)&v39);
      Gdiplus::Graphics::FillPath(a2, v36, &v31);
    }
    else
    {
      v13 = _mm_cvtsi32_si128(a4->left);
      top = (float)a4->top;
      v39 = a7;
      LODWORD(v38) = a6;
      *((float *)&v29 + 1) = top;
      *(float *)&v15 = (float)a4->bottom;
      LODWORD(v29) = _mm_cvtepi32_ps(v13).m128_u32[0];
      v27 = __PAIR64__(v15, v29);
      Gdiplus::LinearGradientBrush::LinearGradientBrush(
        (Gdiplus::LinearGradientBrush *)v36,
        (const struct Gdiplus::PointF *)&v29,
        (const struct Gdiplus::PointF *)&v27,
        (const struct Gdiplus::Color *)&v38,
        (const struct Gdiplus::Color *)&v39);
      Gdiplus::LinearGradientBrush::SetBlendBellShape(v36);
      Gdiplus::Graphics::FillPath(a2, v36, &v31);
      v16 = a4->top;
      v17 = a4->bottom - v16;
      v39 = v12;
      v17 -= 4;
      v18 = v16 + 2;
      Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v34, (const struct Gdiplus::Color *)&v39);
      Gdiplus::Graphics::FillRectangle(a2, v34, (unsigned int)(a4->left + 1), v18, 1, v17);
      Gdiplus::Graphics::FillRectangle(a2, v34, (unsigned int)(a4->right - 2), v18, 1, v17);
      GdipDeleteBrush(v35);
    }
    GdipDeleteBrush(v37);
    if ( (a3 & 0x100) != 0 )
    {
      GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(&v27, a2, 4);
      v39 = a8;
      Gdiplus::Pen::Pen((Gdiplus::Pen *)&v29, (const struct Gdiplus::Color *)&v39, 2.0);
      v19 = v30;
      v30 = 0;
      if ( v19 )
      {
LABEL_9:
        GdipDeletePen(v29);
        Gdiplus::Graphics::SetSmoothingMode(v27, v28);
        goto LABEL_3;
      }
      Gdiplus::Pen::SetAlignment(&v29);
      Gdiplus::Graphics::DrawPath(a2, &v29, &v31);
      GdipDeletePen(v29);
      Gdiplus::Graphics::SetSmoothingMode(v27, v28);
    }
    GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(&v27, a2, 4);
    v39 = a5;
    Gdiplus::Pen::Pen((Gdiplus::Pen *)&v29, (const struct Gdiplus::Color *)&v39, 1.0);
    v20 = v30;
    v30 = 0;
    if ( v20 )
      goto LABEL_9;
    Gdiplus::Pen::SetAlignment(&v29);
    Gdiplus::Graphics::DrawPath(a2, &v29, &v31);
    GdipDeletePen(v29);
    Gdiplus::Graphics::SetSmoothingMode(v27, v28);
    GdipDeletePath(v31);
  }
  if ( (a3 & 0x80u) != 0 )
  {
    left = a4->left;
    v22 = a4->top;
    v23 = a4->right - a4->left;
    v24 = a4->bottom - v22;
    LODWORD(v31) = a4->left;
    HIDWORD(v31) = v22;
    v32 = v23;
    v33 = v24;
    if ( (a3 & 0x40) == 0 )
    {
      LODWORD(v31) = left + 3;
      HIDWORD(v31) = v22 + 3;
      v32 = v23 - 6;
      v33 = v24 - 6;
    }
    LOBYTE(v24) = -1;
    SysGdiplusColor = GdipUtil::GetSysGdiplusColor((GdipUtil *)8, v24, v22);
    GdipUtil::DrawFocusRect(
      a2,
      (struct Gdiplus::Graphics *)&v31,
      (const struct Gdiplus::Rect *)SysGdiplusColor,
      SysGdiplusColor & 0xFFFFFF,
      v26);
  }
}

```

## disassembly

```asm
0x1800751b0  mov     rax, rsp
0x1800751b3  mov     [rax+10h], rbx
0x1800751b7  mov     [rax+20h], rsi
0x1800751bb  mov     [rax+8], rcx
0x1800751bf  push    rbp
0x1800751c0  push    rdi
0x1800751c1  push    r12
0x1800751c3  push    r14
0x1800751c5  push    r15
0x1800751c7  lea     rbp, [rax-3Fh]
0x1800751cb  sub     rsp, 90h
0x1800751d2  mov     r14, r9
0x1800751d5  mov     r15d, r8d
0x1800751d8  mov     rsi, rdx
0x1800751db  bt      r8d, 0Ch
0x1800751e0  jnb     loc_18007543B
0x1800751e6  mov     r8d, 3; unsigned int
0x1800751ec  lea     rcx, [rbp+37h+var_60]; this
0x1800751f0  mov     rdx, r9; struct tagRECT *
0x1800751f3  call    ??0RoundRectPath@GdipUtil@@QEAA@AEBUtagRECT@@I@Z; GdipUtil::RoundRectPath::RoundRectPath(tagRECT const &,uint)
0x1800751f8  mov     eax, [rbp+37h+var_58]
0x1800751fb  mov     [rbp+37h+var_58], 0
0x180075202  test    eax, eax
0x180075204  jz      short loc_180075215
0x180075206  mov     rcx, [rbp+37h+var_60]
0x18007520a  call    cs:__imp_GdipDeletePath
0x180075210  jmp     loc_1800754A5
0x180075215  mov     r12d, [rbp+37h+arg_28]
0x180075219  lea     rcx, [rbp+37h+var_38]; this
0x18007521d  mov     eax, [rbp+37h+arg_30]
0x180075220  cmp     r12d, eax
0x180075223  jz      loc_18007530D
0x180075229  movd    xmm0, dword ptr [r14+4]
0x18007522f  lea     r9, [rbp+37h+arg_0]; struct Gdiplus::Color *
0x180075233  movd    xmm1, dword ptr [r14]
0x180075238  lea     r8, [rbp+37h+var_80]; struct Gdiplus::PointF *
0x18007523c  cvtdq2ps xmm0, xmm0
0x18007523f  mov     [rbp+37h+arg_10], eax
0x180075242  lea     rax, [rbp+37h+arg_10]
0x180075246  lea     rdx, [rbp+37h+var_70]; struct Gdiplus::PointF *
0x18007524a  mov     dword ptr [rbp+37h+arg_0], r12d
0x18007524e  mov     [rsp+0B0h+var_90], rax; struct Gdiplus::Color *
0x180075253  cvtdq2ps xmm1, xmm1
0x180075256  movss   dword ptr [rbp+37h+var_70+4], xmm0
0x18007525b  movd    xmm0, dword ptr [r14+0Ch]
0x180075261  cvtdq2ps xmm0, xmm0
0x180075264  movss   dword ptr [rbp+37h+var_70], xmm1
0x180075269  movss   dword ptr [rbp+37h+var_80+4], xmm0
0x18007526e  movss   dword ptr [rbp+37h+var_80], xmm1
0x180075273  call    ??0LinearGradientBrush@Gdiplus@@QEAA@AEBVPointF@1@0AEBVColor@1@1@Z; Gdiplus::LinearGradientBrush::LinearGradientBrush(Gdiplus::PointF const &,Gdiplus::PointF const &,Gdiplus::Color const &,Gdiplus::Color const &)
0x180075278  movss   xmm2, cs:__real@3f800000
0x180075280  lea     rcx, [rbp+37h+var_38]
0x180075284  movaps  xmm1, xmm2
0x180075287  call    ?SetBlendBellShape@LinearGradientBrush@Gdiplus@@QEAA?AW4Status@2@MM@Z; Gdiplus::LinearGradientBrush::SetBlendBellShape(float,float)
0x18007528c  lea     r8, [rbp+37h+var_60]
0x180075290  mov     rcx, rsi
0x180075293  lea     rdx, [rbp+37h+var_38]
0x180075297  call    ?FillPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::FillPath(Gdiplus::Brush const *,Gdiplus::GraphicsPath const *)
0x18007529c  mov     ecx, [r14+4]
0x1800752a0  lea     rdx, [rbp+37h+arg_10]; struct Gdiplus::Color *
0x1800752a4  mov     ebx, [r14+0Ch]
0x1800752a8  sub     ebx, ecx
0x1800752aa  mov     [rbp+37h+arg_10], r12d
0x1800752ae  add     ebx, 0FFFFFFFCh
0x1800752b1  lea     edi, [rcx+2]
0x1800752b4  lea     rcx, [rbp+37h+var_50]; this
0x1800752b8  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x1800752bd  mov     r8d, [r14]
0x1800752c0  lea     rdx, [rbp+37h+var_50]
0x1800752c4  mov     r12d, 1
0x1800752ca  mov     [rsp+0B0h+var_88], ebx
0x1800752ce  add     r8d, r12d
0x1800752d1  mov     dword ptr [rsp+0B0h+var_90], r12d
0x1800752d6  mov     r9d, edi
0x1800752d9  mov     rcx, rsi
0x1800752dc  call    ?FillRectangle@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@HHHH@Z; Gdiplus::Graphics::FillRectangle(Gdiplus::Brush const *,int,int,int,int)
0x1800752e1  mov     r8d, [r14+8]
0x1800752e5  lea     rdx, [rbp+37h+var_50]
0x1800752e9  sub     r8d, 2
0x1800752ed  mov     [rsp+0B0h+var_88], ebx
0x1800752f1  mov     r9d, edi
0x1800752f4  mov     dword ptr [rsp+0B0h+var_90], r12d
0x1800752f9  mov     rcx, rsi
0x1800752fc  call    ?FillRectangle@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@HHHH@Z; Gdiplus::Graphics::FillRectangle(Gdiplus::Brush const *,int,int,int,int)
0x180075301  mov     rcx, [rbp+37h+var_48]
0x180075305  call    cs:__imp_GdipDeleteBrush
0x18007530b  jmp     short loc_18007532A
0x18007530d  lea     rdx, [rbp+37h+arg_10]; struct Gdiplus::Color *
0x180075311  mov     [rbp+37h+arg_10], r12d
0x180075315  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x18007531a  lea     r8, [rbp+37h+var_60]
0x18007531e  mov     rcx, rsi
0x180075321  lea     rdx, [rbp+37h+var_38]
0x180075325  call    ?FillPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::FillPath(Gdiplus::Brush const *,Gdiplus::GraphicsPath const *)
0x18007532a  mov     rcx, [rbp+37h+var_30]
0x18007532e  call    cs:__imp_GdipDeleteBrush
0x180075334  mov     ebx, 4
0x180075339  bt      r15d, 8
0x18007533e  jnb     loc_1800753C6
0x180075344  mov     r8d, ebx
0x180075347  lea     rcx, [rbp+37h+var_80]
0x18007534b  mov     rdx, rsi
0x18007534e  call    ??0SetSmoothingModeAndRestore@GdipUtil@@QEAA@AEAVGraphics@Gdiplus@@W4SmoothingMode@3@@Z; GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(Gdiplus::Graphics &,Gdiplus::SmoothingMode)
0x180075353  mov     eax, [rbp+37h+arg_38]
0x180075356  lea     rdx, [rbp+37h+arg_10]; struct Gdiplus::Color *
0x18007535a  movss   xmm2, cs:__real@40000000; float
0x180075362  lea     rcx, [rbp+37h+var_70]; this
0x180075366  mov     [rbp+37h+arg_10], eax
0x180075369  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x18007536e  mov     eax, [rbp+37h+var_68]
0x180075371  mov     [rbp+37h+var_68], 0
0x180075378  test    eax, eax
0x18007537a  jz      short loc_180075397
0x18007537c  mov     rcx, [rbp+37h+var_70]
0x180075380  call    cs:__imp_GdipDeletePen
0x180075386  mov     edx, [rbp+37h+var_78]
0x180075389  mov     rcx, [rbp+37h+var_80]
0x18007538d  call    ?SetSmoothingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4SmoothingMode@2@@Z; Gdiplus::Graphics::SetSmoothingMode(Gdiplus::SmoothingMode)
0x180075392  jmp     loc_180075206
0x180075397  lea     rcx, [rbp+37h+var_70]
0x18007539b  call    ?SetAlignment@Pen@Gdiplus@@QEAA?AW4Status@2@W4PenAlignment@2@@Z; Gdiplus::Pen::SetAlignment(Gdiplus::PenAlignment)
0x1800753a0  lea     r8, [rbp+37h+var_60]
0x1800753a4  mov     rcx, rsi
0x1800753a7  lea     rdx, [rbp+37h+var_70]
0x1800753ab  call    ?DrawPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::DrawPath(Gdiplus::Pen const *,Gdiplus::GraphicsPath const *)
0x1800753b0  mov     rcx, [rbp+37h+var_70]
0x1800753b4  call    cs:__imp_GdipDeletePen
0x1800753ba  mov     edx, [rbp+37h+var_78]
0x1800753bd  mov     rcx, [rbp+37h+var_80]
0x1800753c1  call    ?SetSmoothingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4SmoothingMode@2@@Z; Gdiplus::Graphics::SetSmoothingMode(Gdiplus::SmoothingMode)
0x1800753c6  mov     r8d, ebx
0x1800753c9  lea     rcx, [rbp+37h+var_80]
0x1800753cd  mov     rdx, rsi
0x1800753d0  call    ??0SetSmoothingModeAndRestore@GdipUtil@@QEAA@AEAVGraphics@Gdiplus@@W4SmoothingMode@3@@Z; GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(Gdiplus::Graphics &,Gdiplus::SmoothingMode)
0x1800753d5  mov     eax, [rbp+37h+arg_20]
0x1800753d8  lea     rdx, [rbp+37h+arg_10]; struct Gdiplus::Color *
0x1800753dc  movss   xmm2, cs:__real@3f800000; float
0x1800753e4  lea     rcx, [rbp+37h+var_70]; this
0x1800753e8  mov     [rbp+37h+arg_10], eax
0x1800753eb  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x1800753f0  mov     eax, [rbp+37h+var_68]
0x1800753f3  mov     [rbp+37h+var_68], 0
0x1800753fa  test    eax, eax
0x1800753fc  jnz     loc_18007537C
0x180075402  lea     rcx, [rbp+37h+var_70]
0x180075406  call    ?SetAlignment@Pen@Gdiplus@@QEAA?AW4Status@2@W4PenAlignment@2@@Z; Gdiplus::Pen::SetAlignment(Gdiplus::PenAlignment)
0x18007540b  lea     r8, [rbp+37h+var_60]
0x18007540f  mov     rcx, rsi
0x180075412  lea     rdx, [rbp+37h+var_70]
0x180075416  call    ?DrawPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::DrawPath(Gdiplus::Pen const *,Gdiplus::GraphicsPath const *)
0x18007541b  mov     rcx, [rbp+37h+var_70]
0x18007541f  call    cs:__imp_GdipDeletePen
0x180075425  mov     edx, [rbp+37h+var_78]
0x180075428  mov     rcx, [rbp+37h+var_80]
0x18007542c  call    ?SetSmoothingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4SmoothingMode@2@@Z; Gdiplus::Graphics::SetSmoothingMode(Gdiplus::SmoothingMode)
0x180075431  mov     rcx, [rbp+37h+var_60]
0x180075435  call    cs:__imp_GdipDeletePath
0x18007543b  test    r15b, r15b
0x18007543e  jns     short loc_1800754A5
0x180075440  mov     eax, [r14]
0x180075443  mov     r8d, [r14+4]; unsigned __int8
0x180075447  mov     ecx, [r14+8]
0x18007544b  mov     edx, [r14+0Ch]
0x18007544f  sub     ecx, eax
0x180075451  sub     edx, r8d
0x180075454  mov     dword ptr [rbp+37h+var_60], eax
0x180075457  mov     dword ptr [rbp+37h+var_60+4], r8d
0x18007545b  mov     [rbp+37h+var_58], ecx
0x18007545e  mov     [rbp+37h+var_54], edx
0x180075461  test    r15b, 40h
0x180075465  jnz     short loc_180075480
0x180075467  add     eax, 3
0x18007546a  mov     dword ptr [rbp+37h+var_60], eax
0x18007546d  lea     eax, [r8+3]
0x180075471  mov     dword ptr [rbp+37h+var_60+4], eax
0x180075474  lea     eax, [rcx-6]
0x180075477  mov     [rbp+37h+var_58], eax
0x18007547a  lea     eax, [rdx-6]
0x18007547d  mov     [rbp+37h+var_54], eax
0x180075480  mov     dl, 0FFh; int
0x180075482  mov     ecx, 8; this
0x180075487  call    ?GetSysGdiplusColor@GdipUtil@@YAKHE@Z; GdipUtil::GetSysGdiplusColor(int,uchar)
0x18007548c  mov     r9d, eax
0x18007548f  lea     rdx, [rbp+37h+var_60]; struct Gdiplus::Graphics *
0x180075493  and     r9d, 0FFFFFFh; unsigned int
0x18007549a  mov     r8d, eax; struct Gdiplus::Rect *
0x18007549d  mov     rcx, rsi; this
0x1800754a0  call    ?DrawFocusRect@GdipUtil@@YAXAEAVGraphics@Gdiplus@@AEBVRect@3@KK@Z; GdipUtil::DrawFocusRect(Gdiplus::Graphics &,Gdiplus::Rect const &,ulong,ulong)
0x1800754a5  lea     r11, [rsp+0B0h+var_20]
0x1800754ad  mov     rbx, [r11+38h]
0x1800754b1  mov     rsi, [r11+48h]
0x1800754b5  mov     rsp, r11
0x1800754b8  pop     r15
0x1800754ba  pop     r14
0x1800754bc  pop     r12
0x1800754be  pop     rdi
0x1800754bf  pop     rbp
0x1800754c0  retn
```
