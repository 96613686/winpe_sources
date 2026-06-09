# UIControls::SplitButtonEx::PaintAdornment(Gdiplus::Graphics &,ulong,tagRECT const &,ulong,ulong,ulong,ulong)

- ea: `0x180075a00`
- end: `0x180075eb0`
- name: `?PaintAdornment@SplitButtonEx@UIControls@@IEAAXAEAVGraphics@Gdiplus@@KAEBUtagRECT@@KKKK@Z`
- size: `1200`
- prototype: `void __usercall(UIControls::SplitButtonEx *__hidden this@<rcx>, struct Gdiplus::Graphics *@<rdx>, unsigned int@<r8d>, const struct tagRECT *@<r9>, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x180075ec0`

## callees

- `0x18002479c`
- `0x18002b548`
- `0x180031620`
- `0x180031688`
- `0x1800332b4`
- `0x1800332f8`
- `0x180033364`
- `0x180033390`
- `0x1800333e8`
- `0x18003342c`
- `0x18003628c`
- `0x180036350`
- `0x180036720`
- `0x18003860c`
- `0x18003f800`
- `0x18005c71c`
- `0x18006e6a4`
- `0x18007472c`
- `0x180075a00`

## import_xrefs

- `USER32!InflateRect` at `0x180075be7`
- `USER32!InflateRect` at `0x180075be7`
- `USER32!GetClientRect` at `0x180075a64`
- `USER32!GetClientRect` at `0x180075a64`
- `gdiplus!GdipDrawLineI` at `0x180075cbf`
- `gdiplus!GdipDrawLineI` at `0x180075d48`
- `gdiplus!GdipDrawLineI` at `0x180075cbf`
- `gdiplus!GdipDrawLineI` at `0x180075d48`
- `gdiplus!GdipDeletePen` at `0x180075b83`
- `gdiplus!GdipDeletePen` at `0x180075d0b`
- `gdiplus!GdipDeletePen` at `0x180075d59`
- `gdiplus!GdipDeletePen` at `0x180075d64`
- `gdiplus!GdipDeletePen` at `0x180075da9`
- `gdiplus!GdipDeletePen` at `0x180075ddf`
- `gdiplus!GdipDeletePen` at `0x180075b83`
- `gdiplus!GdipDeletePen` at `0x180075d0b`
- `gdiplus!GdipDeletePen` at `0x180075d59`
- `gdiplus!GdipDeletePen` at `0x180075d64`
- `gdiplus!GdipDeletePen` at `0x180075da9`
- `gdiplus!GdipDeletePen` at `0x180075ddf`
- `gdiplus!GdipDeletePath` at `0x180075a99`
- `gdiplus!GdipDeletePath` at `0x180075df7`
- `gdiplus!GdipDeletePath` at `0x180075a99`
- `gdiplus!GdipDeletePath` at `0x180075df7`
- `gdiplus!GdipDeleteBrush` at `0x180075b3c`
- `gdiplus!GdipDeleteBrush` at `0x180075b3c`

## pseudocode

```c
void __fastcall UIControls::SplitButtonEx::PaintAdornment(
        UIControls::SplitButtonEx *this,
        struct Gdiplus::Graphics *a2,
        __int16 a3,
        const struct tagRECT *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  HWND v12; // rcx
  int v13; // eax
  __m128i v14; // xmm0
  LONG v15; // xmm1_4
  LONG v16; // xmm1_4
  int v17; // eax
  bool v18; // zf
  struct tagRECT *MainAreaRect; // rax
  LONG right; // r13d
  unsigned int left; // r12d
  __int64 v22; // r8
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  struct tagRECT *v27; // rax
  LONG v28; // r8d
  LONG top; // r9d
  int v30; // ecx
  int v31; // edx
  unsigned int SysGdiplusColor; // eax
  LONG v33; // [rsp+20h] [rbp-B9h]
  unsigned int v34; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v35; // [rsp+38h] [rbp-A1h] BYREF
  int v36; // [rsp+40h] [rbp-99h]
  int v37; // [rsp+44h] [rbp-95h]
  struct tagRECT v38; // [rsp+48h] [rbp-91h] BYREF
  __int64 v39; // [rsp+60h] [rbp-79h] BYREF
  int v40; // [rsp+68h] [rbp-71h]
  struct tagRECT v41; // [rsp+70h] [rbp-69h] BYREF
  __int64 v42; // [rsp+80h] [rbp-59h] BYREF
  int v43; // [rsp+88h] [rbp-51h]
  unsigned int v44; // [rsp+90h] [rbp-49h] BYREF
  _BYTE v45[24]; // [rsp+98h] [rbp-41h] BYREF
  struct tagRECT rc; // [rsp+B0h] [rbp-29h] BYREF
  struct tagRECT Rect; // [rsp+C0h] [rbp-19h] BYREF

  if ( a4->right - a4->left > 0 && a4->bottom - a4->top > 0 )
  {
    v12 = (HWND)*((_QWORD *)this + 1);
    Rect = 0;
    GetClientRect(v12, &Rect);
    if ( (a3 & 0x1000) != 0 )
    {
      GdipUtil::RoundRectPath::RoundRectPath((GdipUtil::RoundRectPath *)&v42, a4, 3u);
      v13 = v43;
      v43 = 0;
      if ( v13 )
      {
LABEL_5:
        GdipDeletePath(v42);
        return;
      }
      v34 = a6;
      if ( a6 == a7 )
      {
        Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)&v38, (const struct Gdiplus::Color *)&v34);
      }
      else
      {
        v14 = _mm_cvtsi32_si128(a4->top);
        *(float *)&v15 = (float)a4->left;
        v44 = a7;
        v41.left = v15;
        rc.left = v15;
        *(float *)&v16 = (float)a4->bottom;
        v41.top = _mm_cvtepi32_ps(v14).m128_u32[0];
        rc.top = v16;
        Gdiplus::LinearGradientBrush::LinearGradientBrush(
          (Gdiplus::LinearGradientBrush *)&v38,
          (const struct Gdiplus::PointF *)&v41,
          (const struct Gdiplus::PointF *)&rc,
          (const struct Gdiplus::Color *)&v34,
          (const struct Gdiplus::Color *)&v44);
        Gdiplus::LinearGradientBrush::SetBlendBellShape(&v38);
      }
      Gdiplus::Graphics::FillPath(a2, &v38, &v42);
      GdipDeleteBrush(*(_QWORD *)&v38.right);
      if ( (a3 & 0x100) != 0 )
      {
        v34 = a8;
        Gdiplus::Pen::Pen((Gdiplus::Pen *)&v35, (const struct Gdiplus::Color *)&v34, 2.0);
        v17 = v36;
        v36 = 0;
        if ( v17 )
        {
LABEL_11:
          GdipDeletePen(v35);
          goto LABEL_5;
        }
        v18 = *((_BYTE *)this + 577) == 0;
        rc = 0;
        if ( v18 )
          MainAreaRect = UIControls::SplitButtonEx::GetMainAreaRect(this, &v38, a2, &Rect);
        else
          MainAreaRect = UIControls::SplitButtonEx::GetSplitAreaRect(this, &v38, a2, &Rect);
        rc = *MainAreaRect;
        right = rc.right;
        left = rc.left;
        *(_QWORD *)&v41.left = HIDWORD(*(_QWORD *)&rc.right);
        InflateRect(&rc, -1, -1);
        GdipUtil::GetClipAndRestore::GetClipAndRestore((GdipUtil::GetClipAndRestore *)v45, a2);
        *(_QWORD *)&v38.left = *(_QWORD *)&rc.left;
        v38.right = rc.right - rc.left;
        v38.bottom = rc.bottom - rc.top;
        Gdiplus::Graphics::SetClip(a2, &v38);
        GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(&v38, a2, 4);
        Gdiplus::Pen::SetAlignment(&v35);
        Gdiplus::Graphics::DrawPath(a2, &v35, &v42);
        Gdiplus::Graphics::SetSmoothingMode(*(_QWORD *)&v38.left, (unsigned int)v38.right);
        GdipUtil::GetClipAndRestore::~GetClipAndRestore((GdipUtil::GetClipAndRestore *)v45);
        if ( *((_DWORD *)this + 154) )
        {
          v22 = left + 1;
          if ( !*((_BYTE *)this + 577) )
            v22 = (unsigned int)(right - 1);
        }
        else
        {
          v22 = left;
        }
        v23 = GdipDrawLineI(*(_QWORD *)a2, v35, v22);
        if ( v23 )
          *((_DWORD *)a2 + 2) = v23;
        UIControls::SplitButtonEx::GetSplitAreaRect(this, &v41, a2, &Rect);
        v34 = a5;
        Gdiplus::Pen::Pen((Gdiplus::Pen *)&v39, (const struct Gdiplus::Color *)&v34, 1.0);
        v24 = v40;
        v40 = 0;
        if ( v24 )
        {
          GdipDeletePen(v39);
          goto LABEL_11;
        }
        if ( *((_DWORD *)this + 154) )
          v33 = v41.left;
        else
          v33 = v41.right;
        v25 = GdipDrawLineI(*(_QWORD *)a2, v39, (unsigned int)v41.left);
        if ( v25 )
          *((_DWORD *)a2 + 2) = v25;
        GdipDeletePen(v39);
        GdipDeletePen(v35);
      }
      GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(&v38, a2, 4);
      v34 = a5;
      Gdiplus::Pen::Pen((Gdiplus::Pen *)&v39, (const struct Gdiplus::Color *)&v34, 1.0);
      v26 = v40;
      v40 = 0;
      if ( v26 )
      {
        GdipDeletePen(v39);
        Gdiplus::Graphics::SetSmoothingMode(*(_QWORD *)&v38.left, (unsigned int)v38.right);
        goto LABEL_5;
      }
      Gdiplus::Pen::SetAlignment(&v39);
      Gdiplus::Graphics::DrawPath(a2, &v39, &v42);
      GdipDeletePen(v39);
      Gdiplus::Graphics::SetSmoothingMode(*(_QWORD *)&v38.left, (unsigned int)v38.right);
      GdipDeletePath(v42);
    }
    if ( (a3 & 0x80u) != 0 )
    {
      v27 = UIControls::SplitButtonEx::GetMainAreaRect(this, &v38, a2, &Rect);
      v28 = v27->left;
      top = v27->top;
      v30 = v27->right - v27->left;
      v31 = v27->bottom - top;
      LODWORD(v35) = v27->left;
      HIDWORD(v35) = top;
      v36 = v30;
      v37 = v31;
      if ( (a3 & 0x40) == 0 )
      {
        LODWORD(v35) = v28 + 3;
        HIDWORD(v35) = top + 3;
        v36 = v30 - 6;
        v37 = v31 - 6;
      }
      LOBYTE(v31) = -1;
      SysGdiplusColor = GdipUtil::GetSysGdiplusColor((GdipUtil *)8, v31, v28);
      GdipUtil::DrawFocusRect(
        a2,
        (struct Gdiplus::Graphics *)&v35,
        (const struct Gdiplus::Rect *)SysGdiplusColor,
        SysGdiplusColor & 0xFFFFFF,
        v33);
    }
  }
}

```

## disassembly

```asm
0x180075a00  mov     [rsp-8+arg_10], rbx
0x180075a05  push    rbp
0x180075a06  push    rsi
0x180075a07  push    rdi
0x180075a08  push    r12
0x180075a0a  push    r13
0x180075a0c  push    r14
0x180075a0e  push    r15
0x180075a10  lea     rbp, [rsp-7]
0x180075a15  sub     rsp, 0E0h
0x180075a1c  mov     rax, cs:__security_cookie
0x180075a23  xor     rax, rsp
0x180075a26  mov     [rbp+37h+var_40], rax
0x180075a2a  mov     eax, [r9+8]
0x180075a2e  mov     rdi, r9
0x180075a31  sub     eax, [r9]
0x180075a34  mov     r14d, r8d
0x180075a37  mov     rbx, rdx
0x180075a3a  mov     rsi, rcx
0x180075a3d  test    eax, eax
0x180075a3f  jle     loc_180075E89
0x180075a45  mov     eax, [r9+0Ch]
0x180075a49  sub     eax, [r9+4]
0x180075a4d  test    eax, eax
0x180075a4f  jle     loc_180075E89
0x180075a55  mov     rcx, [rcx+8]; hWnd
0x180075a59  lea     rdx, [rbp+37h+Rect]; lpRect
0x180075a5d  xorps   xmm0, xmm0
0x180075a60  movups  xmmword ptr [rbp+37h+Rect.left], xmm0
0x180075a64  call    cs:__imp_GetClientRect
0x180075a6a  bt      r14d, 0Ch
0x180075a6f  jnb     loc_180075DFD
0x180075a75  mov     r8d, 3; unsigned int
0x180075a7b  lea     rcx, [rbp+37h+var_90]; this
0x180075a7f  mov     rdx, rdi; struct tagRECT *
0x180075a82  call    ??0RoundRectPath@GdipUtil@@QEAA@AEBUtagRECT@@I@Z; GdipUtil::RoundRectPath::RoundRectPath(tagRECT const &,uint)
0x180075a87  mov     eax, [rbp+37h+var_88]
0x180075a8a  mov     [rbp+37h+var_88], 0
0x180075a91  test    eax, eax
0x180075a93  jz      short loc_180075AA4
0x180075a95  mov     rcx, [rbp+37h+var_90]
0x180075a99  call    cs:__imp_GdipDeletePath
0x180075a9f  jmp     loc_180075E89
0x180075aa4  mov     eax, [rbp+37h+arg_28]
0x180075aa7  mov     ecx, [rbp+37h+arg_30]
0x180075aaa  mov     [rsp+110h+var_E0], eax
0x180075aae  cmp     eax, ecx
0x180075ab0  jz      short loc_180075B17
0x180075ab2  movd    xmm1, dword ptr [rdi]
0x180075ab6  lea     rax, [rbp+37h+var_80]
0x180075aba  movd    xmm0, dword ptr [rdi+4]
0x180075abf  lea     r9, [rsp+110h+var_E0]; struct Gdiplus::Color *
0x180075ac4  cvtdq2ps xmm1, xmm1
0x180075ac7  mov     [rbp+37h+var_80], ecx
0x180075aca  lea     r8, [rbp+37h+rc]; struct Gdiplus::PointF *
0x180075ace  lea     rdx, [rbp+37h+var_A0]; struct Gdiplus::PointF *
0x180075ad2  mov     [rsp+110h+var_F0], rax; struct Gdiplus::Color *
0x180075ad7  lea     rcx, [rsp+110h+var_C8]; this
0x180075adc  cvtdq2ps xmm0, xmm0
0x180075adf  movss   [rbp+37h+var_A0.left], xmm1
0x180075ae4  movss   [rbp+37h+rc.left], xmm1
0x180075ae9  movd    xmm1, dword ptr [rdi+0Ch]
0x180075aee  cvtdq2ps xmm1, xmm1
0x180075af1  movss   [rbp+37h+var_A0.top], xmm0
0x180075af6  movss   [rbp+37h+rc.top], xmm1
0x180075afb  call    ??0LinearGradientBrush@Gdiplus@@QEAA@AEBVPointF@1@0AEBVColor@1@1@Z; Gdiplus::LinearGradientBrush::LinearGradientBrush(Gdiplus::PointF const &,Gdiplus::PointF const &,Gdiplus::Color const &,Gdiplus::Color const &)
0x180075b00  movss   xmm2, cs:__real@3f800000
0x180075b08  lea     rcx, [rsp+110h+var_C8]
0x180075b0d  movaps  xmm1, xmm2
0x180075b10  call    ?SetBlendBellShape@LinearGradientBrush@Gdiplus@@QEAA?AW4Status@2@MM@Z; Gdiplus::LinearGradientBrush::SetBlendBellShape(float,float)
0x180075b15  jmp     short loc_180075B26
0x180075b17  lea     rdx, [rsp+110h+var_E0]; struct Gdiplus::Color *
0x180075b1c  lea     rcx, [rsp+110h+var_C8]; this
0x180075b21  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x180075b26  lea     r8, [rbp+37h+var_90]
0x180075b2a  mov     rcx, rbx
0x180075b2d  lea     rdx, [rsp+110h+var_C8]
0x180075b32  call    ?FillPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::FillPath(Gdiplus::Brush const *,Gdiplus::GraphicsPath const *)
0x180075b37  mov     rcx, qword ptr [rsp+110h+var_C8.right]
0x180075b3c  call    cs:__imp_GdipDeleteBrush
0x180075b42  mov     edi, [rbp+37h+arg_20]
0x180075b45  bt      r14d, 8
0x180075b4a  jnb     loc_180075D6A
0x180075b50  mov     eax, [rbp+37h+arg_38]
0x180075b53  lea     rdx, [rsp+110h+var_E0]; struct Gdiplus::Color *
0x180075b58  movss   xmm2, cs:__real@40000000; float
0x180075b60  lea     rcx, [rsp+110h+var_D8]; this
0x180075b65  mov     [rsp+110h+var_E0], eax
0x180075b69  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x180075b6e  mov     eax, [rsp+110h+var_D0]
0x180075b72  mov     [rsp+110h+var_D0], 0
0x180075b7a  test    eax, eax
0x180075b7c  jz      short loc_180075B8E
0x180075b7e  mov     rcx, [rsp+110h+var_D8]
0x180075b83  call    cs:__imp_GdipDeletePen
0x180075b89  jmp     loc_180075A95
0x180075b8e  cmp     byte ptr [rsi+241h], 0
0x180075b95  lea     r9, [rbp+37h+Rect]; struct tagRECT *
0x180075b99  xorps   xmm0, xmm0
0x180075b9c  lea     rdx, [rsp+110h+var_C8]; retstr
0x180075ba1  movups  xmmword ptr [rbp+37h+rc.left], xmm0
0x180075ba5  mov     r8, rbx; struct Gdiplus::Graphics *
0x180075ba8  mov     rcx, rsi; this
0x180075bab  jz      short loc_180075BB4
0x180075bad  call    ?GetSplitAreaRect@SplitButtonEx@UIControls@@IEAA?AUtagRECT@@AEBVGraphics@Gdiplus@@AEBU3@@Z; UIControls::SplitButtonEx::GetSplitAreaRect(Gdiplus::Graphics const &,tagRECT const &)
0x180075bb2  jmp     short loc_180075BB9
0x180075bb4  call    ?GetMainAreaRect@SplitButtonEx@UIControls@@IEAA?AUtagRECT@@AEBVGraphics@Gdiplus@@AEBU3@@Z; UIControls::SplitButtonEx::GetMainAreaRect(Gdiplus::Graphics const &,tagRECT const &)
0x180075bb9  movups  xmm0, xmmword ptr [rax]
0x180075bbc  lea     rcx, [rbp+37h+rc]; lprc
0x180075bc0  movdqu  xmmword ptr [rbp+37h+rc.left], xmm0
0x180075bc5  mov     r13, qword ptr [rbp+37h+rc.right]
0x180075bc9  mov     r12, qword ptr [rbp+37h+rc.left]
0x180075bcd  mov     rax, r13
0x180075bd0  shr     rax, 20h
0x180075bd4  mov     r15, r12
0x180075bd7  mov     qword ptr [rbp+37h+var_A0.left], rax
0x180075bdb  or      eax, 0FFFFFFFFh
0x180075bde  mov     r8d, eax; dy
0x180075be1  shr     r15, 20h
0x180075be5  mov     edx, eax; dx
0x180075be7  call    cs:__imp_InflateRect
0x180075bed  mov     rdx, rbx; struct Gdiplus::Graphics *
0x180075bf0  lea     rcx, [rbp+37h+var_78]; this
0x180075bf4  call    ??0GetClipAndRestore@GdipUtil@@QEAA@AEAVGraphics@Gdiplus@@@Z; GdipUtil::GetClipAndRestore::GetClipAndRestore(Gdiplus::Graphics &)
0x180075bf9  mov     rcx, qword ptr [rbp+37h+rc.left]
0x180075bfd  mov     edx, [rbp+37h+rc.top]
0x180075c00  mov     eax, [rbp+37h+rc.right]
0x180075c03  sub     eax, ecx
0x180075c05  mov     [rsp+110h+var_C8.left], ecx
0x180075c09  mov     [rsp+110h+var_C8.right], eax
0x180075c0d  mov     rcx, rbx
0x180075c10  mov     eax, [rbp+37h+rc.bottom]
0x180075c13  sub     eax, edx
0x180075c15  mov     [rsp+110h+var_C8.top], edx
0x180075c19  lea     rdx, [rsp+110h+var_C8]
0x180075c1e  mov     [rsp+110h+var_C8.bottom], eax
0x180075c22  call    ?SetClip@Graphics@Gdiplus@@QEAA?AW4Status@2@AEBVRect@2@W4CombineMode@2@@Z; Gdiplus::Graphics::SetClip(Gdiplus::Rect const &,Gdiplus::CombineMode)
0x180075c27  mov     r8d, 4
0x180075c2d  lea     rcx, [rsp+110h+var_C8]
0x180075c32  mov     rdx, rbx
0x180075c35  call    ??0SetSmoothingModeAndRestore@GdipUtil@@QEAA@AEAVGraphics@Gdiplus@@W4SmoothingMode@3@@Z; GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(Gdiplus::Graphics &,Gdiplus::SmoothingMode)
0x180075c3a  lea     rcx, [rsp+110h+var_D8]
0x180075c3f  call    ?SetAlignment@Pen@Gdiplus@@QEAA?AW4Status@2@W4PenAlignment@2@@Z; Gdiplus::Pen::SetAlignment(Gdiplus::PenAlignment)
0x180075c44  lea     r8, [rbp+37h+var_90]
0x180075c48  mov     rcx, rbx
0x180075c4b  lea     rdx, [rsp+110h+var_D8]
0x180075c50  call    ?DrawPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::DrawPath(Gdiplus::Pen const *,Gdiplus::GraphicsPath const *)
0x180075c55  mov     edx, [rsp+110h+var_C8.right]
0x180075c59  mov     rcx, qword ptr [rsp+110h+var_C8.left]
0x180075c5e  call    ?SetSmoothingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4SmoothingMode@2@@Z; Gdiplus::Graphics::SetSmoothingMode(Gdiplus::SmoothingMode)
0x180075c63  lea     rcx, [rbp+37h+var_78]; this
0x180075c67  call    ??1GetClipAndRestore@GdipUtil@@QEAA@XZ; GdipUtil::GetClipAndRestore::~GetClipAndRestore(void)
0x180075c6c  cmp     dword ptr [rsi+268h], 0
0x180075c73  mov     cl, [rsi+241h]
0x180075c79  mov     rdx, [rsp+110h+var_D8]
0x180075c7e  jnz     short loc_180075C9D
0x180075c80  neg     cl
0x180075c82  mov     r8d, r12d
0x180075c85  sbb     eax, eax
0x180075c87  and     eax, 2
0x180075c8a  lea     r9d, [rax-1]
0x180075c8e  add     r9d, r15d
0x180075c91  mov     [rsp+110h+var_E8], r9d
0x180075c96  mov     dword ptr [rsp+110h+var_F0], r13d
0x180075c9b  jmp     short loc_180075CBC
0x180075c9d  lea     eax, [r13-1]
0x180075ca1  test    cl, cl
0x180075ca3  lea     r8d, [r12+1]
0x180075ca8  mov     r9d, r15d
0x180075cab  cmovz   r8d, eax
0x180075caf  mov     rax, qword ptr [rbp+37h+var_A0.left]
0x180075cb3  mov     [rsp+110h+var_E8], eax
0x180075cb7  mov     dword ptr [rsp+110h+var_F0], r8d
0x180075cbc  mov     rcx, [rbx]
0x180075cbf  call    cs:__imp_GdipDrawLineI
0x180075cc5  test    eax, eax
0x180075cc7  jz      short loc_180075CCC
0x180075cc9  mov     [rbx+8], eax
0x180075ccc  lea     r9, [rbp+37h+Rect]; struct tagRECT *
0x180075cd0  mov     r8, rbx; struct Gdiplus::Graphics *
0x180075cd3  lea     rdx, [rbp+37h+var_A0]; retstr
0x180075cd7  mov     rcx, rsi; this
0x180075cda  call    ?GetSplitAreaRect@SplitButtonEx@UIControls@@IEAA?AUtagRECT@@AEBVGraphics@Gdiplus@@AEBU3@@Z; UIControls::SplitButtonEx::GetSplitAreaRect(Gdiplus::Graphics const &,tagRECT const &)
0x180075cdf  movss   xmm2, cs:__real@3f800000; float
0x180075ce7  lea     rdx, [rsp+110h+var_E0]; struct Gdiplus::Color *
0x180075cec  lea     rcx, [rbp+37h+var_B0]; this
0x180075cf0  mov     [rsp+110h+var_E0], edi
0x180075cf4  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x180075cf9  mov     eax, [rbp+37h+var_A8]
0x180075cfc  mov     [rbp+37h+var_A8], 0
0x180075d03  test    eax, eax
0x180075d05  jz      short loc_180075D16
0x180075d07  mov     rcx, [rbp+37h+var_B0]
0x180075d0b  call    cs:__imp_GdipDeletePen
0x180075d11  jmp     loc_180075B7E
0x180075d16  cmp     dword ptr [rsi+268h], 0
0x180075d1d  mov     r9d, [rbp+37h+var_A0.top]
0x180075d21  mov     r8d, [rbp+37h+var_A0.left]
0x180075d25  mov     rdx, [rbp+37h+var_B0]
0x180075d29  mov     rcx, [rbx]
0x180075d2c  jnz     short loc_180075D3C
0x180075d2e  mov     eax, [rbp+37h+var_A0.right]
0x180075d31  mov     [rsp+110h+var_E8], r9d
0x180075d36  mov     dword ptr [rsp+110h+var_F0], eax
0x180075d3a  jmp     short loc_180075D48
0x180075d3c  mov     eax, [rbp+37h+var_A0.bottom]
0x180075d3f  mov     [rsp+110h+var_E8], eax
0x180075d43  mov     dword ptr [rsp+110h+var_F0], r8d; unsigned int
0x180075d48  call    cs:__imp_GdipDrawLineI
0x180075d4e  test    eax, eax
0x180075d50  jz      short loc_180075D55
0x180075d52  mov     [rbx+8], eax
0x180075d55  mov     rcx, [rbp+37h+var_B0]
0x180075d59  call    cs:__imp_GdipDeletePen
0x180075d5f  mov     rcx, [rsp+110h+var_D8]
0x180075d64  call    cs:__imp_GdipDeletePen
0x180075d6a  mov     r8d, 4
0x180075d70  lea     rcx, [rsp+110h+var_C8]
0x180075d75  mov     rdx, rbx
0x180075d78  call    ??0SetSmoothingModeAndRestore@GdipUtil@@QEAA@AEAVGraphics@Gdiplus@@W4SmoothingMode@3@@Z; GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(Gdiplus::Graphics &,Gdiplus::SmoothingMode)
0x180075d7d  movss   xmm2, cs:__real@3f800000; float
0x180075d85  lea     rdx, [rsp+110h+var_E0]; struct Gdiplus::Color *
0x180075d8a  lea     rcx, [rbp+37h+var_B0]; this
0x180075d8e  mov     [rsp+110h+var_E0], edi
0x180075d92  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x180075d97  mov     eax, [rbp+37h+var_A8]
0x180075d9a  mov     [rbp+37h+var_A8], 0
0x180075da1  test    eax, eax
0x180075da3  jz      short loc_180075DC2
0x180075da5  mov     rcx, [rbp+37h+var_B0]
0x180075da9  call    cs:__imp_GdipDeletePen
0x180075daf  mov     edx, [rsp+110h+var_C8.right]
0x180075db3  mov     rcx, qword ptr [rsp+110h+var_C8.left]
0x180075db8  call    ?SetSmoothingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4SmoothingMode@2@@Z; Gdiplus::Graphics::SetSmoothingMode(Gdiplus::SmoothingMode)
0x180075dbd  jmp     loc_180075A95
0x180075dc2  lea     rcx, [rbp+37h+var_B0]
0x180075dc6  call    ?SetAlignment@Pen@Gdiplus@@QEAA?AW4Status@2@W4PenAlignment@2@@Z; Gdiplus::Pen::SetAlignment(Gdiplus::PenAlignment)
0x180075dcb  lea     r8, [rbp+37h+var_90]
0x180075dcf  mov     rcx, rbx
0x180075dd2  lea     rdx, [rbp+37h+var_B0]
0x180075dd6  call    ?DrawPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::DrawPath(Gdiplus::Pen const *,Gdiplus::GraphicsPath const *)
0x180075ddb  mov     rcx, [rbp+37h+var_B0]
0x180075ddf  call    cs:__imp_GdipDeletePen
0x180075de5  mov     edx, [rsp+110h+var_C8.right]
0x180075de9  mov     rcx, qword ptr [rsp+110h+var_C8.left]
0x180075dee  call    ?SetSmoothingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4SmoothingMode@2@@Z; Gdiplus::Graphics::SetSmoothingMode(Gdiplus::SmoothingMode)
0x180075df3  mov     rcx, [rbp+37h+var_90]
0x180075df7  call    cs:__imp_GdipDeletePath
0x180075dfd  test    r14b, r14b
0x180075e00  jns     loc_180075E89
0x180075e06  lea     r9, [rbp+37h+Rect]; struct tagRECT *
0x180075e0a  mov     r8, rbx; struct Gdiplus::Graphics *
0x180075e0d  lea     rdx, [rsp+110h+var_C8]; retstr
0x180075e12  mov     rcx, rsi; this
0x180075e15  call    ?GetMainAreaRect@SplitButtonEx@UIControls@@IEAA?AUtagRECT@@AEBVGraphics@Gdiplus@@AEBU3@@Z; UIControls::SplitButtonEx::GetMainAreaRect(Gdiplus::Graphics const &,tagRECT const &)
0x180075e1a  mov     r8d, [rax]; unsigned __int8
0x180075e1d  mov     r9d, [rax+4]
0x180075e21  mov     ecx, [rax+8]
0x180075e24  mov     edx, [rax+0Ch]
0x180075e27  sub     ecx, r8d
0x180075e2a  sub     edx, r9d
0x180075e2d  mov     dword ptr [rsp+110h+var_D8], r8d
0x180075e32  mov     dword ptr [rsp+110h+var_D8+4], r9d
0x180075e37  mov     [rsp+110h+var_D0], ecx
0x180075e3b  mov     [rsp+110h+var_CC], edx
0x180075e3f  test    r14b, 40h
0x180075e43  jnz     short loc_180075E63
0x180075e45  lea     eax, [r8+3]
0x180075e49  mov     dword ptr [rsp+110h+var_D8], eax
0x180075e4d  lea     eax, [r9+3]
0x180075e51  mov     dword ptr [rsp+110h+var_D8+4], eax
0x180075e55  lea     eax, [rcx-6]
0x180075e58  mov     [rsp+110h+var_D0], eax
0x180075e5c  lea     eax, [rdx-6]
0x180075e5f  mov     [rsp+110h+var_CC], eax
0x180075e63  mov     dl, 0FFh; int
0x180075e65  mov     ecx, 8; this
0x180075e6a  call    ?GetSysGdiplusColor@GdipUtil@@YAKHE@Z; GdipUtil::GetSysGdiplusColor(int,uchar)
0x180075e6f  mov     r9d, eax
0x180075e72  lea     rdx, [rsp+110h+var_D8]; struct Gdiplus::Graphics *
0x180075e77  and     r9d, 0FFFFFFh; unsigned int
0x180075e7e  mov     r8d, eax; struct Gdiplus::Rect *
0x180075e81  mov     rcx, rbx; this
0x180075e84  call    ?DrawFocusRect@GdipUtil@@YAXAEAVGraphics@Gdiplus@@AEBVRect@3@KK@Z; GdipUtil::DrawFocusRect(Gdiplus::Graphics &,Gdiplus::Rect const &,ulong,ulong)
0x180075e89  mov     rcx, [rbp+37h+var_40]
0x180075e8d  xor     rcx, rsp; StackCookie
0x180075e90  call    __security_check_cookie
0x180075e95  mov     rbx, [rsp+110h+arg_10]
0x180075e9d  add     rsp, 0E0h
0x180075ea4  pop     r15
0x180075ea6  pop     r14
0x180075ea8  pop     r13
0x180075eaa  pop     r12
0x180075eac  pop     rdi
0x180075ead  pop     rsi
0x180075eae  pop     rbp
0x180075eaf  retn
```
