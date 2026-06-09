# ModularWindow::CommandBar::PaintBackground(Gdiplus::Graphics *,tagRECT const &)

- ea: `0x1800072d0`
- end: `0x1800079b7`
- name: `?PaintBackground@CommandBar@ModularWindow@@AEAAXPEAVGraphics@Gdiplus@@AEBUtagRECT@@@Z`
- size: `1767`
- prototype: `void __fastcall(ModularWindow::CommandBar *__hidden this, struct Gdiplus::Graphics *, const struct tagRECT *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000815c`
- `0x1800093fc`
- `0x180037188`

## callees

- `0x1800072d0`
- `0x18003f800`
- `0x18005bcb4`
- `0x1800781a4`
- `0x18007b000`

## import_xrefs

- `USER32!InflateRect` at `0x180007436`
- `USER32!InflateRect` at `0x180007532`
- `USER32!InflateRect` at `0x180007436`
- `USER32!InflateRect` at `0x180007532`
- `USER32!SystemParametersInfoW` at `0x18000732a`
- `USER32!SystemParametersInfoW` at `0x18000732a`
- `USER32!GetSysColor` at `0x180007342`
- `USER32!GetSysColor` at `0x18000762d`
- `USER32!GetSysColor` at `0x180007342`
- `USER32!GetSysColor` at `0x18000762d`
- `gdiplus!GdipCreatePath` at `0x1800076da`
- `gdiplus!GdipCreatePath` at `0x1800076da`
- `gdiplus!GdipDrawPath` at `0x180007947`
- `gdiplus!GdipDrawPath` at `0x180007947`
- `gdiplus!GdipDeletePen` at `0x180007978`
- `gdiplus!GdipDeletePen` at `0x180007978`
- `gdiplus!GdipCreatePen1` at `0x180007667`
- `gdiplus!GdipCreatePen1` at `0x180007667`
- `gdiplus!GdipCreateLineBrushFromRectI` at `0x18000749c`
- `gdiplus!GdipCreateLineBrushFromRectI` at `0x18000758c`
- `gdiplus!GdipCreateLineBrushFromRectI` at `0x18000749c`
- `gdiplus!GdipCreateLineBrushFromRectI` at `0x18000758c`
- `gdiplus!GdipDeletePath` at `0x18000796d`
- `gdiplus!GdipDeletePath` at `0x18000796d`
- `gdiplus!GdipSetSmoothingMode` at `0x18000792e`
- `gdiplus!GdipSetSmoothingMode` at `0x18000795b`
- `gdiplus!GdipSetSmoothingMode` at `0x18000792e`
- `gdiplus!GdipSetSmoothingMode` at `0x18000795b`
- `gdiplus!GdipGetSmoothingMode` at `0x180007919`
- `gdiplus!GdipGetSmoothingMode` at `0x180007919`
- `gdiplus!GdipClosePathFigure` at `0x1800078d4`
- `gdiplus!GdipClosePathFigure` at `0x1800078d4`
- `gdiplus!GdipAddPathLineI` at `0x180007783`
- `gdiplus!GdipAddPathLineI` at `0x1800077f3`
- `gdiplus!GdipAddPathLineI` at `0x18000785b`
- `gdiplus!GdipAddPathLineI` at `0x1800078bc`
- `gdiplus!GdipAddPathLineI` at `0x180007783`
- `gdiplus!GdipAddPathLineI` at `0x1800077f3`
- `gdiplus!GdipAddPathLineI` at `0x18000785b`
- `gdiplus!GdipAddPathLineI` at `0x1800078bc`
- `gdiplus!GdipFillRectangleI` at `0x1800073eb`
- `gdiplus!GdipFillRectangleI` at `0x1800074f5`
- `gdiplus!GdipFillRectangleI` at `0x1800075e5`
- `gdiplus!GdipFillRectangleI` at `0x1800073eb`
- `gdiplus!GdipFillRectangleI` at `0x1800074f5`
- `gdiplus!GdipFillRectangleI` at `0x1800075e5`
- `gdiplus!GdipDeleteBrush` at `0x180007611`
- `gdiplus!GdipDeleteBrush` at `0x18000761b`
- `gdiplus!GdipDeleteBrush` at `0x180007982`
- `gdiplus!GdipDeleteBrush` at `0x180007611`
- `gdiplus!GdipDeleteBrush` at `0x18000761b`
- `gdiplus!GdipDeleteBrush` at `0x180007982`
- `gdiplus!GdipCreateSolidFill` at `0x180007391`
- `gdiplus!GdipCreateSolidFill` at `0x180007391`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ModularWindow::CommandBar::PaintBackground(
        ModularWindow::CommandBar *this,
        struct Gdiplus::Graphics *a2,
        const struct tagRECT *a3)
{
  char v5; // bl
  DWORD SysColor; // eax
  unsigned int v7; // r8d
  __int64 v8; // r12
  int v9; // edx
  int v10; // eax
  int v11; // r15d
  __int64 v12; // rdi
  int v13; // edx
  int v14; // eax
  __int64 v15; // rbx
  int v16; // edx
  int v17; // eax
  __int64 v18; // rdx
  DWORD v19; // eax
  int v20; // eax
  int v21; // edx
  unsigned int top; // r13d
  LONG right; // edi
  LONG bottom; // ebx
  unsigned int v25; // ecx
  int v26; // r14d
  int v27; // eax
  int v28; // edi
  unsigned int v29; // ebx
  int v30; // eax
  int v31; // ecx
  unsigned int v32; // edi
  int v33; // eax
  int v34; // ecx
  int v35; // eax
  int v36; // ecx
  int v37; // eax
  int v38; // ecx
  int v39; // eax
  int v40; // edx
  int SmoothingMode; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  unsigned int v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  int v47; // [rsp+50h] [rbp-B0h]
  __int64 v48; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v49; // [rsp+60h] [rbp-A0h]
  unsigned int left; // [rsp+64h] [rbp-9Ch]
  __int128 pvParam; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v52; // [rsp+78h] [rbp-88h]
  _QWORD pExceptionObject[2]; // [rsp+80h] [rbp-80h] BYREF
  int v54; // [rsp+90h] [rbp-70h]
  _BYTE v55[24]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-50h] BYREF
  int v57; // [rsp+B8h] [rbp-48h]
  void **v58; // [rsp+C0h] [rbp-40h]
  __int64 v59; // [rsp+C8h] [rbp-38h]
  int v60; // [rsp+D0h] [rbp-30h]
  void **v61; // [rsp+D8h] [rbp-28h]
  __int64 v62; // [rsp+E0h] [rbp-20h]
  int v63; // [rsp+E8h] [rbp-18h]
  tagRECT rc; // [rsp+F0h] [rbp-10h] BYREF
  struct tagRECT v65; // [rsp+100h] [rbp+0h] BYREF

  pvParam = 0;
  LODWORD(pvParam) = 16;
  if ( SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0) && (BYTE4(pvParam) & 1) != 0 )
  {
    v5 = 1;
    SysColor = GetSysColor(5);
    v7 = BYTE2(SysColor) | SysColor & 0xFF00 | ((SysColor | 0xFFFFFF00) << 16);
  }
  else
  {
    v5 = 0;
    v7 = -2562574;
  }
  v58 = &Gdiplus::LinearGradientBrush::`vftable';
  v48 = 0;
  v60 = GdipCreateSolidFill(v7, &v48);
  v8 = v48;
  v59 = v48;
  v9 = *((_DWORD *)a2 + 2);
  *((_DWORD *)a2 + 2) = 0;
  if ( v9 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v9);
    throw (Base::GdiException *)pExceptionObject;
  }
  v10 = GdipFillRectangleI(*(_QWORD *)a2, v8);
  if ( v10 )
  {
    *((_DWORD *)a2 + 2) = v10;
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v10);
    throw (Base::GdiException *)pExceptionObject;
  }
  v11 = 1;
  if ( v5 )
  {
    v19 = GetSysColor(6);
    v18 = BYTE2(v19) | v19 & 0xFF00 | ((v19 | 0xFFFFFF00) << 16);
  }
  else
  {
    rc = *a3;
    InflateRect(&rc, -1, -1);
    rc.bottom = (rc.bottom - rc.top) / 2;
    *(_QWORD *)&pvParam = *(_QWORD *)&rc.left;
    DWORD2(pvParam) = rc.right - rc.left;
    HIDWORD(pvParam) = rc.bottom - rc.top;
    v61 = &Gdiplus::LinearGradientBrush::`vftable';
    v48 = 0;
    v63 = GdipCreateLineBrushFromRectI(&pvParam, 4294245118LL, 4293127929LL, 1, 0, &v48);
    v12 = v48;
    v62 = v48;
    v13 = *((_DWORD *)a2 + 2);
    *((_DWORD *)a2 + 2) = 0;
    if ( v13 )
    {
      Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v13);
      throw (Base::GdiException *)pExceptionObject;
    }
    v14 = GdipFillRectangleI(*(_QWORD *)a2, v12);
    if ( v14 )
    {
      *((_DWORD *)a2 + 2) = v14;
      Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v14);
      throw (Base::GdiException *)pExceptionObject;
    }
    v65 = *a3;
    InflateRect(&v65, -1, -1);
    v65.top = v65.bottom - 7;
    LODWORD(pvParam) = v65.left;
    DWORD1(pvParam) = v65.bottom - 7;
    DWORD2(pvParam) = v65.right - v65.left;
    HIDWORD(pvParam) = 7;
    pExceptionObject[0] = &Gdiplus::LinearGradientBrush::`vftable';
    v48 = 0;
    v54 = GdipCreateLineBrushFromRectI(&pvParam, 4292404722LL, 4292470773LL, 1, 0, &v48);
    v15 = v48;
    pExceptionObject[1] = v48;
    v16 = *((_DWORD *)a2 + 2);
    *((_DWORD *)a2 + 2) = 0;
    if ( v16 )
    {
      Base::GdiException::GdiException((Base::GdiException *)v55, v16);
      throw (Base::GdiException *)v55;
    }
    v17 = GdipFillRectangleI(*(_QWORD *)a2, v15);
    if ( v17 )
    {
      *((_DWORD *)a2 + 2) = v17;
      Base::GdiException::GdiException((Base::GdiException *)v55, v17);
      throw (Base::GdiException *)v55;
    }
    GdipDeleteBrush(v15);
    GdipDeleteBrush(v12);
    v18 = 4288720835LL;
  }
  v56 = 0;
  v20 = GdipCreatePen1((unsigned int)v18, v18, 0, &v56);
  v57 = 0;
  if ( v20 )
  {
    Base::GdiException::GdiException((Base::GdiException *)v55, v20);
    throw (Base::GdiException *)v55;
  }
  v21 = *((_DWORD *)a2 + 2);
  *((_DWORD *)a2 + 2) = 0;
  if ( v21 )
  {
    Base::GdiException::GdiException((Base::GdiException *)v55, v21);
    throw (Base::GdiException *)v55;
  }
  left = a3->left;
  top = a3->top;
  right = a3->right;
  bottom = a3->bottom;
  v46 = 0;
  v47 = GdipCreatePath(0, &v46);
  v25 = left;
  v26 = 1;
  if ( (unsigned int)((int)(right - left) / 2) <= 1 )
    v26 = (int)(right - left) / 2;
  if ( (unsigned int)((int)(bottom - 1 - top) / 2) <= 1 )
    v11 = (int)(bottom - 1 - top) / 2;
  v27 = right - 1;
  v49 = right - 1;
  v28 = bottom - 2;
  v45 = bottom - 2;
  if ( v26 && v11 )
  {
    Gdiplus::GraphicsPath::AddArc(
      &v46,
      left,
      top,
      (unsigned int)(2 * v26),
      2 * v11,
      LODWORD(FLOAT_180_0),
      LODWORD(FLOAT_90_0));
    v25 = left;
    v27 = v49;
  }
  v29 = v27 - v26;
  v52 = v25 + v26;
  v30 = GdipAddPathLineI(v46, v25 + v26, top, (unsigned int)(v27 - v26), top);
  v31 = v47;
  if ( v30 )
    v31 = v30;
  v47 = v31;
  if ( v26 && v11 )
    Gdiplus::GraphicsPath::AddArc(
      &v46,
      v49 - 2 * v26,
      top,
      (unsigned int)(2 * v26),
      2 * v11,
      LODWORD(FLOAT_270_0),
      LODWORD(FLOAT_90_0));
  v32 = v28 - v11;
  LODWORD(v48) = v11 + top;
  v33 = GdipAddPathLineI(v46, v49, v11 + top, v49, v32);
  v34 = v47;
  if ( v33 )
    v34 = v33;
  v47 = v34;
  if ( v26 && v11 )
    Gdiplus::GraphicsPath::AddArc(
      &v46,
      v49 - 2 * v26,
      v45 - 2 * v11,
      (unsigned int)(2 * v26),
      2 * v11,
      0,
      LODWORD(FLOAT_90_0));
  v35 = GdipAddPathLineI(v46, v29, v45, v52, v45);
  v36 = v47;
  if ( v35 )
    v36 = v35;
  v47 = v36;
  if ( v26 && v11 )
    Gdiplus::GraphicsPath::AddArc(
      &v46,
      left,
      v45 - 2 * v11,
      (unsigned int)(2 * v26),
      2 * v11,
      LODWORD(FLOAT_90_0),
      LODWORD(FLOAT_90_0));
  v37 = GdipAddPathLineI(v46, left, v32, left, v48);
  v38 = v47;
  if ( v37 )
    v38 = v37;
  v47 = v38;
  v39 = GdipClosePathFigure(v46);
  v40 = v47;
  if ( v39 )
    v40 = v39;
  v47 = 0;
  if ( v40 )
  {
    Base::GdiException::GdiException((Base::GdiException *)v55, v40);
    throw (Base::GdiException *)v55;
  }
  v45 = -1;
  SmoothingMode = GdipGetSmoothingMode(*(_QWORD *)a2, &v45);
  if ( SmoothingMode )
    *((_DWORD *)a2 + 2) = SmoothingMode;
  v42 = GdipSetSmoothingMode(*(_QWORD *)a2, 4);
  if ( v42 )
    *((_DWORD *)a2 + 2) = v42;
  v43 = GdipDrawPath(*(_QWORD *)a2, v56, v46);
  if ( v43 )
    *((_DWORD *)a2 + 2) = v43;
  v44 = GdipSetSmoothingMode(*(_QWORD *)a2, v45);
  if ( v44 )
    *((_DWORD *)a2 + 2) = v44;
  GdipDeletePath(v46);
  GdipDeletePen(v56);
  GdipDeleteBrush(v8);
}

```

## disassembly

```asm
0x1800072d0  mov     [rsp-8+arg_0], rbx
0x1800072d5  push    rbp
0x1800072d6  push    rsi
0x1800072d7  push    rdi
0x1800072d8  push    r12
0x1800072da  push    r13
0x1800072dc  push    r14
0x1800072de  push    r15
0x1800072e0  lea     rbp, [rsp-30h]
0x1800072e5  sub     rsp, 130h
0x1800072ec  movaps  [rsp+160h+var_40], xmm6
0x1800072f4  mov     rax, cs:__security_cookie
0x1800072fb  xor     rax, rsp
0x1800072fe  mov     [rbp+60h+var_50], rax
0x180007302  mov     r14, r8
0x180007305  mov     rsi, rdx
0x180007308  xorps   xmm0, xmm0
0x18000730b  movups  [rsp+160h+pvParam], xmm0
0x180007310  mov     dword ptr [rsp+160h+pvParam], 10h
0x180007318  xor     r9d, r9d; fWinIni
0x18000731b  lea     r8, [rsp+160h+pvParam]; pvParam
0x180007320  mov     edx, 10h; uiParam
0x180007325  mov     ecx, 42h ; 'B'; uiAction
0x18000732a  call    cs:__imp_SystemParametersInfoW
0x180007330  test    eax, eax
0x180007332  jz      short loc_18000736E
0x180007334  test    byte ptr [rsp+160h+pvParam+4], 1
0x180007339  jz      short loc_18000736E
0x18000733b  mov     bl, 1
0x18000733d  mov     ecx, 5; nIndex
0x180007342  call    cs:__imp_GetSysColor
0x180007348  movzx   r8d, al
0x18000734c  or      r8d, 0FFFFFF00h
0x180007353  shl     r8d, 10h
0x180007357  movzx   ecx, ax
0x18000735a  and     ecx, 0FFFFFF00h
0x180007360  or      r8d, ecx
0x180007363  shr     eax, 10h
0x180007366  movzx   eax, al
0x180007369  or      r8d, eax
0x18000736c  jmp     short loc_180007376
0x18000736e  xor     bl, bl
0x180007370  mov     r8d, 0FFD8E5F2h
0x180007376  lea     rax, ??_7LinearGradientBrush@Gdiplus@@6B@; const Gdiplus::LinearGradientBrush::`vftable'
0x18000737d  mov     [rbp+60h+var_A0], rax
0x180007381  xor     r13d, r13d
0x180007384  mov     [rsp+160h+var_108], r13
0x180007389  lea     rdx, [rsp+160h+var_108]
0x18000738e  mov     ecx, r8d
0x180007391  call    cs:__imp_GdipCreateSolidFill
0x180007397  mov     [rbp+60h+var_90], eax
0x18000739a  mov     r12, [rsp+160h+var_108]
0x18000739f  mov     [rbp+60h+var_98], r12
0x1800073a3  mov     edx, [rsi+8]; int
0x1800073a6  mov     [rsi+8], r13d
0x1800073aa  test    edx, edx
0x1800073ac  jz      short loc_1800073C8
0x1800073ae  lea     rcx, [rbp+60h+pExceptionObject]; this
0x1800073b2  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x1800073b7  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x1800073be  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x1800073c2  call    _CxxThrowException_0
0x1800073c8  mov     r9d, [r14+4]
0x1800073cc  mov     r8d, [r14]
0x1800073cf  mov     ecx, [r14+0Ch]
0x1800073d3  sub     ecx, r9d
0x1800073d6  mov     eax, [r14+8]
0x1800073da  sub     eax, r8d
0x1800073dd  mov     dword ptr [rsp+160h+var_138], ecx
0x1800073e1  mov     [rsp+160h+var_140], eax
0x1800073e5  mov     rdx, r12
0x1800073e8  mov     rcx, [rsi]
0x1800073eb  call    cs:__imp_GdipFillRectangleI
0x1800073f1  test    eax, eax
0x1800073f3  jz      short loc_180007414
0x1800073f5  mov     [rsi+8], eax
0x1800073f8  mov     edx, eax; int
0x1800073fa  lea     rcx, [rbp+60h+pExceptionObject]; this
0x1800073fe  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180007403  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x18000740a  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18000740e  call    _CxxThrowException_0
0x180007414  mov     r15d, 1
0x18000741a  test    bl, bl
0x18000741c  jnz     loc_180007628
0x180007422  movups  xmm0, xmmword ptr [r14]
0x180007426  movups  xmmword ptr [rbp+60h+rc.left], xmm0
0x18000742a  mov     edx, 0FFFFFFFFh; dx
0x18000742f  mov     r8d, edx; dy
0x180007432  lea     rcx, [rbp+60h+rc]; lprc
0x180007436  call    cs:__imp_InflateRect
0x18000743c  mov     eax, [rbp+60h+rc.bottom]
0x18000743f  mov     r8d, [rbp+60h+rc.top]
0x180007443  sub     eax, r8d
0x180007446  cdq
0x180007447  sub     eax, edx
0x180007449  sar     eax, 1
0x18000744b  mov     [rbp+60h+rc.bottom], eax
0x18000744e  mov     edx, [rbp+60h+rc.left]
0x180007451  mov     dword ptr [rsp+160h+pvParam], edx
0x180007455  mov     dword ptr [rsp+160h+pvParam+4], r8d
0x18000745a  mov     ecx, [rbp+60h+rc.right]
0x18000745d  sub     ecx, edx
0x18000745f  mov     dword ptr [rsp+160h+pvParam+8], ecx
0x180007463  sub     eax, r8d
0x180007466  mov     dword ptr [rsp+160h+pvParam+0Ch], eax
0x18000746a  lea     rbx, ??_7LinearGradientBrush@Gdiplus@@6B@; const Gdiplus::LinearGradientBrush::`vftable'
0x180007471  mov     [rbp+60h+var_88], rbx
0x180007475  mov     [rsp+160h+var_108], r13
0x18000747a  lea     rax, [rsp+160h+var_108]
0x18000747f  mov     [rsp+160h+var_138], rax
0x180007484  mov     [rsp+160h+var_140], r13d
0x180007489  mov     r9d, r15d
0x18000748c  mov     edx, 0FFF4FAFEh
0x180007491  mov     r8d, 0FFE3EEF9h
0x180007497  lea     rcx, [rsp+160h+pvParam]
0x18000749c  call    cs:__imp_GdipCreateLineBrushFromRectI
0x1800074a2  mov     [rbp+60h+var_78], eax
0x1800074a5  mov     rdi, [rsp+160h+var_108]
0x1800074aa  mov     [rbp+60h+var_80], rdi
0x1800074ae  mov     edx, [rsi+8]; int
0x1800074b1  mov     [rsi+8], r13d
0x1800074b5  test    edx, edx
0x1800074b7  jz      short loc_1800074D3
0x1800074b9  lea     rcx, [rbp+60h+pExceptionObject]; this
0x1800074bd  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x1800074c2  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x1800074c9  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x1800074cd  call    _CxxThrowException_0
0x1800074d3  mov     r8d, [rbp+60h+rc.left]
0x1800074d7  mov     r9d, [rbp+60h+rc.top]
0x1800074db  mov     ecx, [rbp+60h+rc.bottom]
0x1800074de  sub     ecx, r9d
0x1800074e1  mov     eax, [rbp+60h+rc.right]
0x1800074e4  sub     eax, r8d
0x1800074e7  mov     dword ptr [rsp+160h+var_138], ecx
0x1800074eb  mov     [rsp+160h+var_140], eax
0x1800074ef  mov     rdx, rdi
0x1800074f2  mov     rcx, [rsi]
0x1800074f5  call    cs:__imp_GdipFillRectangleI
0x1800074fb  test    eax, eax
0x1800074fd  jz      short loc_18000751E
0x1800074ff  mov     [rsi+8], eax
0x180007502  mov     edx, eax; int
0x180007504  lea     rcx, [rbp+60h+pExceptionObject]; this
0x180007508  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x18000750d  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180007514  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x180007518  call    _CxxThrowException_0
0x18000751e  movups  xmm0, xmmword ptr [r14]
0x180007522  movups  xmmword ptr [rbp+60h+var_60.left], xmm0
0x180007526  mov     edx, 0FFFFFFFFh; dx
0x18000752b  mov     r8d, edx; dy
0x18000752e  lea     rcx, [rbp+60h+var_60]; lprc
0x180007532  call    cs:__imp_InflateRect
0x180007538  mov     r9d, [rbp+60h+var_60.bottom]
0x18000753c  lea     r8d, [r9-7]
0x180007540  mov     [rbp+60h+var_60.top], r8d
0x180007544  mov     ecx, [rbp+60h+var_60.left]
0x180007547  mov     dword ptr [rsp+160h+pvParam], ecx
0x18000754b  mov     dword ptr [rsp+160h+pvParam+4], r8d
0x180007550  mov     eax, [rbp+60h+var_60.right]
0x180007553  sub     eax, ecx
0x180007555  mov     dword ptr [rsp+160h+pvParam+8], eax
0x180007559  sub     r9d, r8d
0x18000755c  mov     dword ptr [rsp+160h+pvParam+0Ch], r9d
0x180007561  mov     [rbp+60h+pExceptionObject], rbx
0x180007565  mov     [rsp+160h+var_108], r13
0x18000756a  lea     rax, [rsp+160h+var_108]
0x18000756f  mov     [rsp+160h+var_138], rax
0x180007574  mov     [rsp+160h+var_140], r13d
0x180007579  mov     r9d, r15d
0x18000757c  mov     edx, 0FFD8E5F2h
0x180007581  mov     r8d, 0FFD9E7F5h
0x180007587  lea     rcx, [rsp+160h+pvParam]
0x18000758c  call    cs:__imp_GdipCreateLineBrushFromRectI
0x180007592  mov     [rbp+60h+var_D0], eax
0x180007595  mov     rbx, [rsp+160h+var_108]
0x18000759a  mov     [rbp+60h+var_D8], rbx
0x18000759e  mov     edx, [rsi+8]; int
0x1800075a1  mov     [rsi+8], r13d
0x1800075a5  test    edx, edx
0x1800075a7  jz      short loc_1800075C3
0x1800075a9  lea     rcx, [rbp+60h+var_C8]; this
0x1800075ad  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x1800075b2  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x1800075b9  lea     rcx, [rbp+60h+var_C8]; pExceptionObject
0x1800075bd  call    _CxxThrowException_0
0x1800075c3  mov     r8d, [rbp+60h+var_60.left]
0x1800075c7  mov     r9d, [rbp+60h+var_60.top]
0x1800075cb  mov     ecx, [rbp+60h+var_60.bottom]
0x1800075ce  sub     ecx, r9d
0x1800075d1  mov     eax, [rbp+60h+var_60.right]
0x1800075d4  sub     eax, r8d
0x1800075d7  mov     dword ptr [rsp+160h+var_138], ecx
0x1800075db  mov     [rsp+160h+var_140], eax
0x1800075df  mov     rdx, rbx
0x1800075e2  mov     rcx, [rsi]
0x1800075e5  call    cs:__imp_GdipFillRectangleI
0x1800075eb  test    eax, eax
0x1800075ed  jz      short loc_18000760E
0x1800075ef  mov     [rsi+8], eax
0x1800075f2  mov     edx, eax; int
0x1800075f4  lea     rcx, [rbp+60h+var_C8]; this
0x1800075f8  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x1800075fd  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180007604  lea     rcx, [rbp+60h+var_C8]; pExceptionObject
0x180007608  call    _CxxThrowException_0
0x18000760e  mov     rcx, rbx
0x180007611  call    cs:__imp_GdipDeleteBrush
0x180007617  nop
0x180007618  mov     rcx, rdi
0x18000761b  call    cs:__imp_GdipDeleteBrush
0x180007621  mov     edx, 0FFA0AFC3h
0x180007626  jmp     short loc_180007652
0x180007628  mov     ecx, 6; nIndex
0x18000762d  call    cs:__imp_GetSysColor
0x180007633  movzx   edx, al
0x180007636  or      edx, 0FFFFFF00h
0x18000763c  shl     edx, 10h
0x18000763f  movzx   ecx, ax
0x180007642  and     ecx, 0FFFFFF00h
0x180007648  or      edx, ecx
0x18000764a  shr     eax, 10h
0x18000764d  movzx   eax, al
0x180007650  or      edx, eax
0x180007652  mov     [rbp+60h+var_B0], r13
0x180007656  lea     r9, [rbp+60h+var_B0]
0x18000765a  xor     r8d, r8d
0x18000765d  movss   xmm1, cs:__real@3f800000
0x180007665  mov     ecx, edx
0x180007667  call    cs:__imp_GdipCreatePen1
0x18000766d  nop
0x18000766e  mov     [rbp+60h+var_A8], r13d
0x180007672  test    eax, eax
0x180007674  jz      short loc_180007692
0x180007676  mov     edx, eax; int
0x180007678  lea     rcx, [rbp+60h+var_C8]; this
0x18000767c  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180007681  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180007688  lea     rcx, [rbp+60h+var_C8]; pExceptionObject
0x18000768c  call    _CxxThrowException_0
0x180007692  mov     edx, [rsi+8]; int
0x180007695  mov     [rsi+8], r13d
0x180007699  test    edx, edx
0x18000769b  jz      short loc_1800076B7
0x18000769d  lea     rcx, [rbp+60h+var_C8]; this
0x1800076a1  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x1800076a6  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x1800076ad  lea     rcx, [rbp+60h+var_C8]; pExceptionObject
0x1800076b1  call    _CxxThrowException_0
0x1800076b7  mov     eax, [r14]
0x1800076ba  mov     [rsp+160h+var_FC], eax
0x1800076be  mov     r13d, [r14+4]
0x1800076c2  mov     edi, [r14+8]
0x1800076c6  mov     ebx, [r14+0Ch]
0x1800076ca  mov     [rsp+160h+var_118], 0
0x1800076d3  lea     rdx, [rsp+160h+var_118]
0x1800076d8  xor     ecx, ecx
0x1800076da  call    cs:__imp_GdipCreatePath
0x1800076e0  mov     [rsp+160h+var_110], eax
0x1800076e4  mov     eax, edi
0x1800076e6  mov     ecx, [rsp+160h+var_FC]
0x1800076ea  sub     eax, ecx
0x1800076ec  cdq
0x1800076ed  sub     eax, edx
0x1800076ef  sar     eax, 1
0x1800076f1  mov     r14d, r15d
0x1800076f4  cmp     eax, r15d
0x1800076f7  cmovbe  r14d, eax
0x1800076fb  lea     eax, [rbx-1]
0x1800076fe  sub     eax, r13d
0x180007701  cdq
0x180007702  sub     eax, edx
0x180007704  sar     eax, 1
0x180007706  cmp     eax, 1
0x180007709  cmovbe  r15d, eax
0x18000770d  lea     eax, [rdi-1]
0x180007710  mov     [rsp+160h+var_100], eax
0x180007714  lea     edi, [rbx-2]
0x180007717  mov     [rsp+160h+var_120], edi
0x18000771b  movss   xmm6, cs:__real@42b40000
0x180007723  test    r14d, r14d
0x180007726  jz      short loc_180007764
0x180007728  test    r15d, r15d
0x18000772b  jz      short loc_180007764
0x18000772d  lea     eax, [r15+r15]
0x180007731  lea     r9d, [r14+r14]
0x180007735  movss   [rsp+160h+var_130], xmm6
0x18000773b  movss   xmm0, cs:__real@43340000
0x180007743  movss   dword ptr [rsp+160h+var_138], xmm0
0x180007749  mov     [rsp+160h+var_140], eax
0x18000774d  mov     r8d, r13d
0x180007750  mov     edx, ecx
0x180007752  lea     rcx, [rsp+160h+var_118]
0x180007757  call    ?AddArc@GraphicsPath@Gdiplus@@QEAA?AW4Status@2@HHHHMM@Z; Gdiplus::GraphicsPath::AddArc(int,int,int,int,float,float)
0x18000775c  mov     ecx, [rsp+160h+var_FC]
0x180007760  mov     eax, [rsp+160h+var_100]
0x180007764  mov     ebx, eax
0x180007766  sub     ebx, r14d
  ... truncated ...
```
