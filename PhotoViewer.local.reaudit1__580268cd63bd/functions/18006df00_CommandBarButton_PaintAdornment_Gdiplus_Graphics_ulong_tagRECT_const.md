# CommandBarButton::PaintAdornment(Gdiplus::Graphics &,ulong,tagRECT const &)

- ea: `0x18006df00`
- end: `0x18006e69d`
- name: `?PaintAdornment@CommandBarButton@@MEAAXAEAVGraphics@Gdiplus@@KAEBUtagRECT@@@Z`
- size: `1949`
- prototype: `void __fastcall(CommandBarButton *__hidden this, struct Gdiplus::Graphics *, unsigned int, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x1800046b8`
- `0x180025bc4`
- `0x180031620`
- `0x180031688`
- `0x180033108`
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
- `0x18006dea4`
- `0x18006df00`
- `0x18006e6a4`
- `0x18006e6d0`
- `0x180075ec0`

## import_xrefs

- `USER32!InflateRect` at `0x18006e09f`
- `USER32!InflateRect` at `0x18006e0fc`
- `USER32!InflateRect` at `0x18006e09f`
- `USER32!InflateRect` at `0x18006e0fc`
- `USER32!GetClientRect` at `0x18006e030`
- `USER32!GetClientRect` at `0x18006e030`
- `gdiplus!GdipDrawLineI` at `0x18006e624`
- `gdiplus!GdipDrawLineI` at `0x18006e624`
- `gdiplus!GdipSetPathGradientCenterPoint` at `0x18006e3a9`
- `gdiplus!GdipSetPathGradientCenterPoint` at `0x18006e3a9`
- `gdiplus!GdipSetPathGradientCenterColor` at `0x18006e370`
- `gdiplus!GdipSetPathGradientCenterColor` at `0x18006e370`
- `gdiplus!GdipAddPathEllipseI` at `0x18006e346`
- `gdiplus!GdipAddPathEllipseI` at `0x18006e346`
- `gdiplus!GdipStartPathFigure` at `0x18006e2f9`
- `gdiplus!GdipStartPathFigure` at `0x18006e2f9`
- `gdiplus!GdipCreatePath` at `0x18006e2ea`
- `gdiplus!GdipCreatePath` at `0x18006e2ea`
- `gdiplus!GdipDeletePen` at `0x18006e56f`
- `gdiplus!GdipDeletePen` at `0x18006e637`
- `gdiplus!GdipDeletePen` at `0x18006e641`
- `gdiplus!GdipDeletePen` at `0x18006e660`
- `gdiplus!GdipDeletePen` at `0x18006e56f`
- `gdiplus!GdipDeletePen` at `0x18006e637`
- `gdiplus!GdipDeletePen` at `0x18006e641`
- `gdiplus!GdipDeletePen` at `0x18006e660`
- `gdiplus!GdipDeletePath` at `0x18006e465`
- `gdiplus!GdipDeletePath` at `0x18006e64c`
- `gdiplus!GdipDeletePath` at `0x18006e656`
- `gdiplus!GdipDeletePath` at `0x18006e66a`
- `gdiplus!GdipDeletePath` at `0x18006e465`
- `gdiplus!GdipDeletePath` at `0x18006e64c`
- `gdiplus!GdipDeletePath` at `0x18006e656`
- `gdiplus!GdipDeletePath` at `0x18006e66a`
- `gdiplus!GdipDeleteBrush` at `0x18006e2cc`
- `gdiplus!GdipDeleteBrush` at `0x18006e45a`
- `gdiplus!GdipDeleteBrush` at `0x18006e2cc`
- `gdiplus!GdipDeleteBrush` at `0x18006e45a`

## pseudocode

```c
void __fastcall CommandBarButton::PaintAdornment(
        CommandBarButton *this,
        struct Gdiplus::Graphics *a2,
        unsigned int a3,
        const struct tagRECT *a4)
{
  int v8; // edi
  char v9; // si
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  LONG left; // r14d
  LONG right; // ebx
  LONG bottom; // edi
  struct tagRECT *SplitAreaRect; // rax
  LONG v18; // edi
  LONG v19; // r14d
  LONG v20; // ebx
  LONG v21; // esi
  int v22; // ebx
  int v23; // edi
  int started; // eax
  int v25; // ecx
  int v26; // eax
  int v27; // ecx
  int v28; // eax
  int v29; // ebx
  int v30; // eax
  int v31; // edi
  LONG v32; // esi
  LONG v33; // ebx
  LONG v34; // r14d
  LONG v35; // edi
  int v36; // eax
  int v37; // eax
  int v38; // esi
  int v39; // eax
  int v40; // eax
  __int64 v41; // r8
  int v42; // eax
  unsigned int v43; // [rsp+20h] [rbp-E0h]
  char v44; // [rsp+40h] [rbp-C0h]
  char v45; // [rsp+41h] [rbp-BFh]
  char v46; // [rsp+42h] [rbp-BEh]
  LONG top; // [rsp+44h] [rbp-BCh] BYREF
  int v48; // [rsp+48h] [rbp-B8h] BYREF
  struct tagRECT v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+60h] [rbp-A0h] BYREF
  int v51; // [rsp+68h] [rbp-98h]
  int v52; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v54; // [rsp+78h] [rbp-88h] BYREF
  int v55; // [rsp+80h] [rbp-80h]
  int v56; // [rsp+88h] [rbp-78h]
  int v57; // [rsp+8Ch] [rbp-74h]
  int v58; // [rsp+90h] [rbp-70h] BYREF
  __int64 v59; // [rsp+98h] [rbp-68h] BYREF
  int v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h] BYREF
  int v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h] BYREF
  int v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+C8h] [rbp-38h] BYREF
  int v66; // [rsp+D0h] [rbp-30h]
  _BYTE v67[8]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v68; // [rsp+E0h] [rbp-20h]
  int v69; // [rsp+E8h] [rbp-18h]
  float v70[2]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v71[24]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v72[24]; // [rsp+110h] [rbp+10h] BYREF
  struct tagRECT rc; // [rsp+128h] [rbp+28h] BYREF
  struct tagRECT Rect; // [rsp+138h] [rbp+38h] BYREF

  v8 = a3 & 0x20;
  if ( (a3 & 0x20) != 0 && (a3 & 0x80u) != 0 )
  {
    Rect.left = a4->left;
    Rect.top = a4->top;
    Rect.right = a4->right - Rect.left;
    Rect.bottom = a4->bottom - Rect.top;
    GdipUtil::DrawFocusRect(
      a2,
      (struct Gdiplus::Graphics *)&Rect,
      (const struct Gdiplus::Rect *)0xFFFFFFFFLL,
      0xFFFFFFu,
      v43);
  }
  if ( *((_BYTE *)this + 602) )
  {
    if ( a4->right - a4->left > 0 && a4->bottom - a4->top > 0 )
    {
      v52 = *((_DWORD *)this + 154);
      v58 = v52;
      if ( v8 )
      {
        v9 = *((_BYTE *)this + 600);
        v45 = v9;
        v56 = a3 & 0x200;
        if ( (a3 & 0x200) != 0 || (a3 & 0x100) != 0 || v9 )
        {
          v46 = *((_BYTE *)this + 577);
          v57 = *((_DWORD *)this + 151);
          if ( UIBase::IsHighContrastOn(this) )
          {
            UIControls::SplitButtonEx::PaintAdornment(this, a2, a3, a4);
            return;
          }
          Rect = 0;
          GetClientRect(*((HWND *)this + 1), &Rect);
          GdipUtil::RoundRectPath::RoundRectPath((GdipUtil::RoundRectPath *)&v61, a4, 4u);
          v10 = v62;
          v62 = 0;
          if ( v10 )
            goto LABEL_63;
          top = -4667430;
          Gdiplus::Pen::Pen((Gdiplus::Pen *)&v59, (const struct Gdiplus::Color *)&top, 1.0);
          v11 = v60;
          v60 = 0;
          if ( v11 )
          {
LABEL_62:
            GdipDeletePen(v59);
LABEL_63:
            GdipDeletePath(v61);
            return;
          }
          rc = *a4;
          InflateRect(&rc, -1, -1);
          GdipUtil::RoundRectPath::RoundRectPath((GdipUtil::RoundRectPath *)&v65, &rc, 3u);
          v12 = v66;
          v66 = 0;
          if ( v12 )
          {
LABEL_61:
            GdipDeletePath(v65);
            goto LABEL_62;
          }
          GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(&v49, a2, 4);
          Gdiplus::Graphics::DrawPath(a2, &v59, &v65);
          Gdiplus::Graphics::SetSmoothingMode(*(_QWORD *)&v49.left, (unsigned int)v49.right);
          InflateRect(&rc, -1, -1);
          GdipUtil::RoundRectPath::RoundRectPath((GdipUtil::RoundRectPath *)&v54, &rc, 2u);
          v13 = v55;
          v55 = 0;
          if ( v13 )
          {
LABEL_60:
            GdipDeletePath(v54);
            goto LABEL_61;
          }
          left = a4->left;
          top = a4->top;
          right = a4->right;
          bottom = a4->bottom;
          v44 = 1;
          if ( !v57 && !v9 )
          {
            if ( v46 )
            {
              if ( !v52 )
              {
                v44 = 0;
                goto LABEL_25;
              }
              SplitAreaRect = UIControls::SplitButtonEx::GetSplitAreaRect(this, &v49, a2, &Rect);
            }
            else
            {
              SplitAreaRect = UIControls::SplitButtonEx::GetMainAreaRect(this, &v49, a2, &Rect);
            }
            bottom = SplitAreaRect->bottom;
            right = SplitAreaRect->right;
            top = SplitAreaRect->top;
            left = SplitAreaRect->left;
          }
LABEL_25:
          GdipUtil::GetClipAndRestore::GetClipAndRestore((GdipUtil::GetClipAndRestore *)v72, a2);
          v49.left = left;
          v49.top = top;
          v49.right = right - left;
          v49.bottom = bottom - top;
          Gdiplus::Graphics::SetClip(a2, &v49);
          if ( !v9 && !v56 && v44 )
          {
            top = 0xFFFFFF;
            v53 = 1694498815;
            v49.left = rc.left;
            v49.top = rc.top;
            v49.right = rc.right - rc.left;
            v49.bottom = rc.bottom - rc.top;
            Gdiplus::LinearGradientBrush::LinearGradientBrush(v67, &v49, &v53, &top);
            Gdiplus::LinearGradientBrush::SetBlendBellShape(v67);
            if ( v52 )
            {
              Gdiplus::Graphics::FillPath(a2, v67, &v54);
            }
            else
            {
              v18 = rc.left;
              v19 = rc.top;
              v20 = rc.right;
              v21 = rc.bottom;
              GdipUtil::GetClipAndRestore::GetClipAndRestore((GdipUtil::GetClipAndRestore *)v71, a2);
              v49.left = v18;
              v49.top = v19;
              v49.right = v20 - v18;
              v49.bottom = v21 / 3 - v19;
              Gdiplus::Graphics::SetClip(a2, &v49);
              Gdiplus::Graphics::FillPath(a2, v67, &v54);
              GdipUtil::GetClipAndRestore::~GetClipAndRestore((GdipUtil::GetClipAndRestore *)v71);
            }
            GdipDeleteBrush(v68);
          }
          v22 = rc.bottom - rc.top;
          v23 = rc.right - rc.left;
          v50 = 0;
          v51 = GdipCreatePath(0, &v50);
          started = GdipStartPathFigure(v50);
          v25 = v51;
          if ( started )
            v25 = started;
          v51 = v25;
          v48 = v22 / 4;
          v26 = GdipAddPathEllipseI(
                  v50,
                  (unsigned int)(rc.left - 18),
                  (unsigned int)(v22 / 4 + rc.top),
                  (unsigned int)(rc.right - (rc.left - 18) + 18),
                  rc.bottom + v22 - (v22 / 4 + rc.top));
          v27 = v51;
          if ( v26 )
            v27 = v26;
          v51 = v27;
          Gdiplus::PathGradientBrush::PathGradientBrush(
            (Gdiplus::PathGradientBrush *)v67,
            (const struct Gdiplus::GraphicsPath *)&v50);
          v28 = GdipSetPathGradientCenterColor(v68, 4289379541LL);
          v29 = v69;
          if ( v28 )
            v29 = v28;
          v70[0] = (float)(v23 / 2);
          v70[1] = (float)rc.bottom;
          v30 = GdipSetPathGradientCenterPoint(v68, v70);
          if ( v30 )
            v29 = v30;
          v69 = v29;
          top = 12702695;
          v53 = 1;
          Gdiplus::PathGradientBrush::SetSurroundColors(v67, &top, &v53);
          v31 = v52;
          if ( v52 )
          {
            Gdiplus::Graphics::FillPath(a2, v67, &v50);
          }
          else
          {
            v32 = rc.left;
            v33 = rc.right;
            v34 = rc.bottom;
            v35 = rc.top + v48;
            GdipUtil::GetClipAndRestore::GetClipAndRestore((GdipUtil::GetClipAndRestore *)v71, a2);
            v49.left = v32;
            v49.top = v35;
            v49.right = v33 - v32;
            v49.bottom = v34 - v35;
            Gdiplus::Graphics::SetClip(a2, &v49);
            Gdiplus::Graphics::FillPath(a2, v67, &v50);
            GdipUtil::GetClipAndRestore::~GetClipAndRestore((GdipUtil::GetClipAndRestore *)v71);
            v31 = v52;
          }
          GdipDeleteBrush(v68);
          GdipDeletePath(v50);
          GdipUtil::GetClipAndRestore::~GetClipAndRestore((GdipUtil::GetClipAndRestore *)v72);
          if ( v56 || (v36 = 1275068415, v45) )
            v36 = -3549724;
          v48 = v36;
          Gdiplus::Pen::Pen((Gdiplus::Pen *)&v63, (const struct Gdiplus::Color *)&v48, 1.0);
          v37 = v64;
          v64 = 0;
          if ( v37 )
            goto LABEL_59;
          Gdiplus::Pen::SetAlignment(&v63);
          v38 = v57;
          if ( v57 || v45 )
          {
            GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(&v49, a2, 4);
            Gdiplus::Graphics::DrawPath(a2, &v63, &v54);
            Gdiplus::Graphics::SetSmoothingMode(*(_QWORD *)&v49.left, (unsigned int)v49.right);
            if ( v38 )
            {
LABEL_59:
              GdipDeletePen(v63);
              goto LABEL_60;
            }
          }
          else
          {
            v48 = 771751935;
            Gdiplus::Pen::Pen((Gdiplus::Pen *)&v50, (const struct Gdiplus::Color *)&v48, 1.0);
            v39 = v51;
            v51 = 0;
            if ( v39 )
            {
LABEL_58:
              GdipDeletePen(v50);
              goto LABEL_59;
            }
            CommandBarButton::PaintSplitButtonInnerGlowHelper(
              this,
              a2,
              a4,
              &Rect,
              v46 != 0,
              (struct Gdiplus::Pen *)&v63,
              (struct Gdiplus::GraphicsPath *)&v54,
              (const enum UIControls::SplitButtonEx::SplitArrowMode *)&v58);
            CommandBarButton::PaintSplitButtonInnerGlowHelper(
              this,
              a2,
              a4,
              &Rect,
              v46 == 0,
              (struct Gdiplus::Pen *)&v50,
              (struct Gdiplus::GraphicsPath *)&v54,
              (const enum UIControls::SplitButtonEx::SplitArrowMode *)&v58);
            GdipDeletePen(v50);
          }
          UIControls::SplitButtonEx::GetSplitAreaRect(this, &v49, a2, &Rect);
          v48 = -3549724;
          Gdiplus::Pen::Pen((Gdiplus::Pen *)&v50, (const struct Gdiplus::Color *)&v48, 1.0);
          v40 = v51;
          v51 = 0;
          if ( !v40 )
          {
            if ( v31 )
              v41 = (unsigned int)v49.left;
            else
              v41 = (unsigned int)rc.left;
            v42 = GdipDrawLineI(*(_QWORD *)a2, v50, v41);
            if ( v42 )
              *((_DWORD *)a2 + 2) = v42;
          }
          goto LABEL_58;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18006df00  mov     rax, rsp
0x18006df03  mov     [rax+18h], rbx
0x18006df07  push    rbp
0x18006df08  push    rsi
0x18006df09  push    rdi
0x18006df0a  push    r12
0x18006df0c  push    r13
0x18006df0e  push    r14
0x18006df10  push    r15
0x18006df12  lea     rbp, [rsp-60h]
0x18006df17  sub     rsp, 160h
0x18006df1e  movaps  xmmword ptr [rax-48h], xmm6
0x18006df22  mov     rax, cs:__security_cookie
0x18006df29  xor     rax, rsp
0x18006df2c  mov     [rbp+90h+var_48], rax
0x18006df30  mov     r12, r9
0x18006df33  mov     ebx, r8d
0x18006df36  mov     r15, rdx
0x18006df39  mov     r13, rcx
0x18006df3c  mov     edi, r8d
0x18006df3f  and     edi, 20h
0x18006df42  jz      short loc_18006DF7D
0x18006df44  test    bl, bl
0x18006df46  jns     short loc_18006DF7D
0x18006df48  mov     ecx, [r9]
0x18006df4b  mov     [rbp+90h+Rect.left], ecx
0x18006df4e  mov     edx, [r9+4]
0x18006df52  mov     [rbp+90h+Rect.top], edx
0x18006df55  mov     eax, [r9+8]
0x18006df59  sub     eax, ecx
0x18006df5b  mov     [rbp+90h+Rect.right], eax
0x18006df5e  mov     eax, [r9+0Ch]
0x18006df62  sub     eax, edx
0x18006df64  mov     [rbp+90h+Rect.bottom], eax
0x18006df67  mov     r9d, 0FFFFFFh; unsigned int
0x18006df6d  or      r8d, 0FFFFFFFFh; struct Gdiplus::Rect *
0x18006df71  lea     rdx, [rbp+90h+Rect]; struct Gdiplus::Graphics *
0x18006df75  mov     rcx, r15; this
0x18006df78  call    ?DrawFocusRect@GdipUtil@@YAXAEAVGraphics@Gdiplus@@AEBVRect@3@KK@Z; GdipUtil::DrawFocusRect(Gdiplus::Graphics &,Gdiplus::Rect const &,ulong,ulong)
0x18006df7d  xor     r14d, r14d
0x18006df80  cmp     [r13+25Ah], r14b
0x18006df87  jz      loc_18006E671
0x18006df8d  mov     eax, [r12+8]
0x18006df92  sub     eax, [r12]
0x18006df96  test    eax, eax
0x18006df98  jle     loc_18006E671
0x18006df9e  mov     eax, [r12+0Ch]
0x18006dfa3  sub     eax, [r12+4]
0x18006dfa8  test    eax, eax
0x18006dfaa  jle     loc_18006E671
0x18006dfb0  mov     eax, [r13+268h]
0x18006dfb7  mov     [rsp+190h+var_120], eax
0x18006dfbb  mov     [rbp+90h+var_100], eax
0x18006dfbe  test    edi, edi
0x18006dfc0  jz      loc_18006E671
0x18006dfc6  mov     sil, [r13+258h]
0x18006dfcd  mov     [rsp+190h+var_14F], sil
0x18006dfd2  mov     eax, ebx
0x18006dfd4  and     eax, 200h
0x18006dfd9  mov     [rbp+90h+var_108], eax
0x18006dfdc  jnz     short loc_18006DFED
0x18006dfde  bt      ebx, 8
0x18006dfe2  jb      short loc_18006DFED
0x18006dfe4  test    sil, sil
0x18006dfe7  jz      loc_18006E671
0x18006dfed  mov     al, [r13+241h]
0x18006dff4  mov     [rsp+190h+var_14E], al
0x18006dff8  mov     eax, [r13+25Ch]
0x18006dfff  mov     [rbp+90h+var_104], eax
0x18006e002  call    ?IsHighContrastOn@UIBase@@YA_NXZ; UIBase::IsHighContrastOn(void)
0x18006e007  test    al, al
0x18006e009  jz      short loc_18006E021
0x18006e00b  mov     r9, r12; struct tagRECT *
0x18006e00e  mov     r8d, ebx; unsigned int
0x18006e011  mov     rdx, r15; struct Gdiplus::Graphics *
0x18006e014  mov     rcx, r13; this
0x18006e017  call    ?PaintAdornment@SplitButtonEx@UIControls@@MEAAXAEAVGraphics@Gdiplus@@KAEBUtagRECT@@@Z; UIControls::SplitButtonEx::PaintAdornment(Gdiplus::Graphics &,ulong,tagRECT const &)
0x18006e01c  jmp     loc_18006E671
0x18006e021  xorps   xmm0, xmm0
0x18006e024  movups  xmmword ptr [rbp+90h+Rect.left], xmm0
0x18006e028  lea     rdx, [rbp+90h+Rect]; lpRect
0x18006e02c  mov     rcx, [r13+8]; hWnd
0x18006e030  call    cs:__imp_GetClientRect
0x18006e036  mov     edi, 4
0x18006e03b  mov     r8d, edi; unsigned int
0x18006e03e  mov     rdx, r12; struct tagRECT *
0x18006e041  lea     rcx, [rbp+90h+var_E8]; this
0x18006e045  call    ??0RoundRectPath@GdipUtil@@QEAA@AEBUtagRECT@@I@Z; GdipUtil::RoundRectPath::RoundRectPath(tagRECT const &,uint)
0x18006e04a  mov     eax, [rbp+90h+var_E0]
0x18006e04d  mov     [rbp+90h+var_E0], r14d
0x18006e051  test    eax, eax
0x18006e053  jnz     loc_18006E666
0x18006e059  mov     [rsp+190h+var_14C], 0FFB8C7DAh
0x18006e061  movss   xmm6, cs:__real@3f800000
0x18006e069  movaps  xmm2, xmm6; float
0x18006e06c  lea     rdx, [rsp+190h+var_14C]; struct Gdiplus::Color *
0x18006e071  lea     rcx, [rbp+90h+var_F8]; this
0x18006e075  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x18006e07a  mov     eax, [rbp+90h+var_F0]
0x18006e07d  mov     [rbp+90h+var_F0], r14d
0x18006e081  test    eax, eax
0x18006e083  jnz     loc_18006E65C
0x18006e089  movups  xmm0, xmmword ptr [r12]
0x18006e08e  movdqu  xmmword ptr [rbp+90h+rc.left], xmm0
0x18006e093  or      ebx, 0FFFFFFFFh
0x18006e096  mov     r8d, ebx; dy
0x18006e099  mov     edx, ebx; dx
0x18006e09b  lea     rcx, [rbp+90h+rc]; lprc
0x18006e09f  call    cs:__imp_InflateRect
0x18006e0a5  lea     r8d, [rdi-1]; unsigned int
0x18006e0a9  lea     rdx, [rbp+90h+rc]; struct tagRECT *
0x18006e0ad  lea     rcx, [rbp+90h+var_C8]; this
0x18006e0b1  call    ??0RoundRectPath@GdipUtil@@QEAA@AEBUtagRECT@@I@Z; GdipUtil::RoundRectPath::RoundRectPath(tagRECT const &,uint)
0x18006e0b6  mov     eax, [rbp+90h+var_C0]
0x18006e0b9  mov     [rbp+90h+var_C0], r14d
0x18006e0bd  test    eax, eax
0x18006e0bf  jnz     loc_18006E652
0x18006e0c5  mov     r8d, edi
0x18006e0c8  mov     rdx, r15
0x18006e0cb  lea     rcx, [rsp+190h+var_140]
0x18006e0d0  call    ??0SetSmoothingModeAndRestore@GdipUtil@@QEAA@AEAVGraphics@Gdiplus@@W4SmoothingMode@3@@Z; GdipUtil::SetSmoothingModeAndRestore::SetSmoothingModeAndRestore(Gdiplus::Graphics &,Gdiplus::SmoothingMode)
0x18006e0d5  lea     r8, [rbp+90h+var_C8]
0x18006e0d9  lea     rdx, [rbp+90h+var_F8]
0x18006e0dd  mov     rcx, r15
0x18006e0e0  call    ?DrawPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVPen@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::DrawPath(Gdiplus::Pen const *,Gdiplus::GraphicsPath const *)
0x18006e0e5  mov     edx, [rsp+190h+var_140.right]
0x18006e0e9  mov     rcx, qword ptr [rsp+190h+var_140.left]
0x18006e0ee  call    ?SetSmoothingMode@Graphics@Gdiplus@@QEAA?AW4Status@2@W4SmoothingMode@2@@Z; Gdiplus::Graphics::SetSmoothingMode(Gdiplus::SmoothingMode)
0x18006e0f3  mov     r8d, ebx; dy
0x18006e0f6  mov     edx, ebx; dx
0x18006e0f8  lea     rcx, [rbp+90h+rc]; lprc
0x18006e0fc  call    cs:__imp_InflateRect
0x18006e102  lea     r8d, [rdi-2]; unsigned int
0x18006e106  lea     rdx, [rbp+90h+rc]; struct tagRECT *
0x18006e10a  lea     rcx, [rsp+190h+var_118]; this
0x18006e10f  call    ??0RoundRectPath@GdipUtil@@QEAA@AEBUtagRECT@@I@Z; GdipUtil::RoundRectPath::RoundRectPath(tagRECT const &,uint)
0x18006e114  mov     eax, [rbp+90h+var_110]
0x18006e117  mov     [rbp+90h+var_110], r14d
0x18006e11b  test    eax, eax
0x18006e11d  jnz     loc_18006E647
0x18006e123  mov     r14d, [r12]
0x18006e127  mov     ecx, [r12+4]
0x18006e12c  mov     [rsp+190h+var_14C], ecx
0x18006e130  mov     ebx, [r12+8]
0x18006e135  mov     edi, [r12+0Ch]
0x18006e13a  mov     [rsp+190h+var_150], 1
0x18006e13f  xor     eax, eax
0x18006e141  cmp     [rbp+90h+var_104], eax
0x18006e144  jnz     short loc_18006E197
0x18006e146  test    sil, sil
0x18006e149  jnz     short loc_18006E197
0x18006e14b  cmp     [rsp+190h+var_14E], al
0x18006e14f  jz      short loc_18006E173
0x18006e151  cmp     [rsp+190h+var_120], eax
0x18006e155  jnz     short loc_18006E15D
0x18006e157  mov     [rsp+190h+var_150], al
0x18006e15b  jmp     short loc_18006E197
0x18006e15d  lea     r9, [rbp+90h+Rect]; struct tagRECT *
0x18006e161  mov     r8, r15; struct Gdiplus::Graphics *
0x18006e164  lea     rdx, [rsp+190h+var_140]; retstr
0x18006e169  mov     rcx, r13; this
0x18006e16c  call    ?GetSplitAreaRect@SplitButtonEx@UIControls@@IEAA?AUtagRECT@@AEBVGraphics@Gdiplus@@AEBU3@@Z; UIControls::SplitButtonEx::GetSplitAreaRect(Gdiplus::Graphics const &,tagRECT const &)
0x18006e171  jmp     short loc_18006E187
0x18006e173  lea     r9, [rbp+90h+Rect]; struct tagRECT *
0x18006e177  mov     r8, r15; struct Gdiplus::Graphics *
0x18006e17a  lea     rdx, [rsp+190h+var_140]; retstr
0x18006e17f  mov     rcx, r13; this
0x18006e182  call    ?GetMainAreaRect@SplitButtonEx@UIControls@@IEAA?AUtagRECT@@AEBVGraphics@Gdiplus@@AEBU3@@Z; UIControls::SplitButtonEx::GetMainAreaRect(Gdiplus::Graphics const &,tagRECT const &)
0x18006e187  mov     ecx, [rax+4]
0x18006e18a  mov     edi, [rax+0Ch]
0x18006e18d  mov     ebx, [rax+8]
0x18006e190  mov     [rsp+190h+var_14C], ecx
0x18006e194  mov     r14d, [rax]
0x18006e197  mov     rdx, r15; struct Gdiplus::Graphics *
0x18006e19a  lea     rcx, [rbp+90h+var_80]; this
0x18006e19e  call    ??0GetClipAndRestore@GdipUtil@@QEAA@AEAVGraphics@Gdiplus@@@Z; GdipUtil::GetClipAndRestore::GetClipAndRestore(Gdiplus::Graphics &)
0x18006e1a3  mov     [rsp+190h+var_140.left], r14d
0x18006e1a8  mov     eax, [rsp+190h+var_14C]
0x18006e1ac  mov     [rsp+190h+var_140.top], eax
0x18006e1b0  sub     ebx, r14d
0x18006e1b3  mov     [rsp+190h+var_140.right], ebx
0x18006e1b7  sub     edi, eax
0x18006e1b9  mov     [rsp+190h+var_140.bottom], edi
0x18006e1bd  lea     rdx, [rsp+190h+var_140]
0x18006e1c2  mov     rcx, r15
0x18006e1c5  call    ?SetClip@Graphics@Gdiplus@@QEAA?AW4Status@2@AEBVRect@2@W4CombineMode@2@@Z; Gdiplus::Graphics::SetClip(Gdiplus::Rect const &,Gdiplus::CombineMode)
0x18006e1ca  xor     r14d, r14d
0x18006e1cd  test    sil, sil
0x18006e1d0  jnz     loc_18006E2D2
0x18006e1d6  cmp     [rbp+90h+var_108], r14d
0x18006e1da  jnz     loc_18006E2D2
0x18006e1e0  cmp     [rsp+190h+var_150], r14b
0x18006e1e5  jz      loc_18006E2D2
0x18006e1eb  mov     [rsp+190h+var_14C], 0FFFFFFh
0x18006e1f3  mov     [rsp+190h+var_11C], 64FFFFFFh
0x18006e1fb  mov     ecx, [rbp+90h+rc.left]
0x18006e1fe  mov     [rsp+190h+var_140.left], ecx
0x18006e202  mov     edx, [rbp+90h+rc.top]
0x18006e205  mov     [rsp+190h+var_140.top], edx
0x18006e209  mov     eax, [rbp+90h+rc.right]
0x18006e20c  sub     eax, ecx
0x18006e20e  mov     [rsp+190h+var_140.right], eax
0x18006e212  mov     eax, [rbp+90h+rc.bottom]
0x18006e215  sub     eax, edx
0x18006e217  mov     [rsp+190h+var_140.bottom], eax
0x18006e21b  lea     r9, [rsp+190h+var_14C]
0x18006e220  lea     r8, [rsp+190h+var_11C]
0x18006e225  lea     rdx, [rsp+190h+var_140]
0x18006e22a  lea     rcx, [rbp+90h+var_B8]
0x18006e22e  call    ??0LinearGradientBrush@Gdiplus@@QEAA@AEBVRect@1@AEBVColor@1@1W4LinearGradientMode@1@@Z; Gdiplus::LinearGradientBrush::LinearGradientBrush(Gdiplus::Rect const &,Gdiplus::Color const &,Gdiplus::Color const &,Gdiplus::LinearGradientMode)
0x18006e233  movaps  xmm2, xmm6
0x18006e236  movss   xmm1, cs:__real@3f000000
0x18006e23e  lea     rcx, [rbp+90h+var_B8]
0x18006e242  call    ?SetBlendBellShape@LinearGradientBrush@Gdiplus@@QEAA?AW4Status@2@MM@Z; Gdiplus::LinearGradientBrush::SetBlendBellShape(float,float)
0x18006e247  cmp     [rsp+190h+var_120], r14d
0x18006e24c  jnz     short loc_18006E2B7
0x18006e24e  mov     edi, [rbp+90h+rc.left]
0x18006e251  mov     r14d, [rbp+90h+rc.top]
0x18006e255  mov     ebx, [rbp+90h+rc.right]
0x18006e258  mov     esi, [rbp+90h+rc.bottom]
0x18006e25b  mov     rdx, r15; struct Gdiplus::Graphics *
0x18006e25e  lea     rcx, [rbp+90h+var_98]; this
0x18006e262  call    ??0GetClipAndRestore@GdipUtil@@QEAA@AEAVGraphics@Gdiplus@@@Z; GdipUtil::GetClipAndRestore::GetClipAndRestore(Gdiplus::Graphics &)
0x18006e267  mov     [rsp+190h+var_140.left], edi
0x18006e26b  mov     [rsp+190h+var_140.top], r14d
0x18006e270  sub     ebx, edi
0x18006e272  mov     [rsp+190h+var_140.right], ebx
0x18006e276  mov     eax, 55555556h
0x18006e27b  imul    esi
0x18006e27d  mov     eax, edx
0x18006e27f  shr     eax, 1Fh
0x18006e282  add     edx, eax
0x18006e284  sub     edx, r14d
0x18006e287  mov     [rsp+190h+var_140.bottom], edx
0x18006e28b  lea     rdx, [rsp+190h+var_140]
0x18006e290  mov     rcx, r15
0x18006e293  call    ?SetClip@Graphics@Gdiplus@@QEAA?AW4Status@2@AEBVRect@2@W4CombineMode@2@@Z; Gdiplus::Graphics::SetClip(Gdiplus::Rect const &,Gdiplus::CombineMode)
0x18006e298  lea     r8, [rsp+190h+var_118]
0x18006e29d  lea     rdx, [rbp+90h+var_B8]
0x18006e2a1  mov     rcx, r15
0x18006e2a4  call    ?FillPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::FillPath(Gdiplus::Brush const *,Gdiplus::GraphicsPath const *)
0x18006e2a9  lea     rcx, [rbp+90h+var_98]; this
0x18006e2ad  call    ??1GetClipAndRestore@GdipUtil@@QEAA@XZ; GdipUtil::GetClipAndRestore::~GetClipAndRestore(void)
0x18006e2b2  xor     r14d, r14d
0x18006e2b5  jmp     short loc_18006E2C8
0x18006e2b7  lea     r8, [rsp+190h+var_118]
0x18006e2bc  lea     rdx, [rbp+90h+var_B8]
0x18006e2c0  mov     rcx, r15
0x18006e2c3  call    ?FillPath@Graphics@Gdiplus@@QEAA?AW4Status@2@PEBVBrush@2@PEBVGraphicsPath@2@@Z; Gdiplus::Graphics::FillPath(Gdiplus::Brush const *,Gdiplus::GraphicsPath const *)
0x18006e2c8  mov     rcx, [rbp+90h+var_B0]
0x18006e2cc  call    cs:__imp_GdipDeleteBrush
0x18006e2d2  mov     ebx, [rbp+90h+rc.bottom]
0x18006e2d5  sub     ebx, [rbp+90h+rc.top]
0x18006e2d8  mov     edi, [rbp+90h+rc.right]
0x18006e2db  sub     edi, [rbp+90h+rc.left]
0x18006e2de  mov     [rsp+190h+var_130], r14
0x18006e2e3  lea     rdx, [rsp+190h+var_130]
0x18006e2e8  xor     ecx, ecx
0x18006e2ea  call    cs:__imp_GdipCreatePath
0x18006e2f0  mov     [rsp+190h+var_128], eax
0x18006e2f4  mov     rcx, [rsp+190h+var_130]
0x18006e2f9  call    cs:__imp_GdipStartPathFigure
0x18006e2ff  mov     ecx, [rsp+190h+var_128]
0x18006e303  test    eax, eax
0x18006e305  cmovnz  ecx, eax
0x18006e308  mov     [rsp+190h+var_128], ecx
0x18006e30c  mov     r10d, [rbp+90h+rc.left]
0x18006e310  add     r10d, 0FFFFFFEEh
0x18006e314  mov     eax, ebx
0x18006e316  cdq
0x18006e317  mov     ecx, 4
0x18006e31c  idiv    ecx
0x18006e31e  mov     [rsp+190h+var_148], eax
0x18006e322  mov     r8d, [rbp+90h+rc.top]
0x18006e326  add     r8d, eax
0x18006e329  sub     ebx, r8d
0x18006e32c  add     ebx, [rbp+90h+rc.bottom]
0x18006e32f  mov     r9d, [rbp+90h+rc.right]
0x18006e333  sub     r9d, r10d
0x18006e336  add     r9d, 12h
0x18006e33a  mov     dword ptr [rsp+190h+var_170], ebx
0x18006e33e  mov     edx, r10d
0x18006e341  mov     rcx, [rsp+190h+var_130]
0x18006e346  call    cs:__imp_GdipAddPathEllipseI
0x18006e34c  mov     ecx, [rsp+190h+var_128]
0x18006e350  test    eax, eax
0x18006e352  cmovnz  ecx, eax
0x18006e355  mov     [rsp+190h+var_128], ecx
0x18006e359  lea     rdx, [rsp+190h+var_130]; struct Gdiplus::GraphicsPath *
0x18006e35e  lea     rcx, [rbp+90h+var_B8]; this
0x18006e362  call    ??0PathGradientBrush@Gdiplus@@QEAA@PEBVGraphicsPath@1@@Z; Gdiplus::PathGradientBrush::PathGradientBrush(Gdiplus::GraphicsPath const *)
0x18006e367  mov     edx, 0FFAABCD5h
0x18006e36c  mov     rcx, [rbp+90h+var_B0]
0x18006e370  call    cs:__imp_GdipSetPathGradientCenterColor
0x18006e376  mov     ebx, [rbp+90h+var_A8]
0x18006e379  test    eax, eax
0x18006e37b  cmovnz  ebx, eax
0x18006e37e  mov     eax, edi
0x18006e380  cdq
0x18006e381  mov     ecx, 2
  ... truncated ...
```
