# UIControls::SplitButtonEx::PaintContent(Gdiplus::Graphics &,ulong,tagRECT const &,ulong)

- ea: `0x180005434`
- end: `0x180005d73`
- name: `?PaintContent@SplitButtonEx@UIControls@@IEAAXAEAVGraphics@Gdiplus@@KAEBUtagRECT@@K@Z`
- size: `2367`
- prototype: `void __usercall(UIControls::SplitButtonEx *__hidden this@<rcx>, struct Gdiplus::Graphics *@<rdx>, unsigned int@<r8d>, const struct tagRECT *@<r9>, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, installer_update`

## callers

- `0x180004f80`
- `0x180075f90`

## callees

- `0x180002de0`
- `0x1800041a4`
- `0x180005434`
- `0x180005f04`
- `0x180006144`
- `0x180025228`
- `0x180027a84`
- `0x180029b08`
- `0x18002b2f8`
- `0x18002b548`
- `0x18003156c`
- `0x180031688`
- `0x180035054`
- `0x18003f800`
- `0x18005d730`
- `0x180080010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1800055d3`
- `KERNEL32!MulDiv` at `0x180005602`
- `KERNEL32!MulDiv` at `0x1800055d3`
- `KERNEL32!MulDiv` at `0x180005602`
- `USER32!GetWindowTextW` at `0x18000591d`
- `USER32!GetWindowTextW` at `0x18000591d`
- `USER32!GetWindowTextLengthW` at `0x1800058d6`
- `USER32!GetWindowTextLengthW` at `0x1800058d6`
- `USER32!GetClientRect` at `0x1800054e3`
- `USER32!GetClientRect` at `0x1800054e3`
- `USER32!GetDC` at `0x180005576`
- `USER32!GetDC` at `0x180005576`
- `USER32!ReleaseDC` at `0x18000561f`
- `USER32!ReleaseDC` at `0x18000561f`
- `USER32!GetWindowLongW` at `0x1800056fd`
- `USER32!GetWindowLongW` at `0x1800056fd`
- `gdiplus!GdipSetPageUnit` at `0x180005558`
- `gdiplus!GdipSetPageUnit` at `0x1800057f2`
- `gdiplus!GdipSetPageUnit` at `0x180005558`
- `gdiplus!GdipSetPageUnit` at `0x1800057f2`
- `gdiplus!GdipGetPageUnit` at `0x18000553e`
- `gdiplus!GdipGetPageUnit` at `0x18000553e`
- `gdiplus!GdipDrawImageRectRectI` at `0x1800057db`
- `gdiplus!GdipDrawImageRectRectI` at `0x1800057db`
- `gdiplus!GdipSetInterpolationMode` at `0x1800054ef`
- `gdiplus!GdipSetInterpolationMode` at `0x1800054ef`
- `gdiplus!GdipDeleteBrush` at `0x180005bea`
- `gdiplus!GdipDeleteBrush` at `0x180005d37`
- `gdiplus!GdipDeleteBrush` at `0x180005bea`
- `gdiplus!GdipDeleteBrush` at `0x180005d37`
- `gdiplus!GdipCreateSolidFill` at `0x180005cb1`
- `gdiplus!GdipCreateSolidFill` at `0x180005cb1`
- `gdiplus!GdipGetPixelOffsetMode` at `0x180005cc8`
- `gdiplus!GdipGetPixelOffsetMode` at `0x180005cc8`
- `gdiplus!GdipSetPixelOffsetMode` at `0x180005cdf`
- `gdiplus!GdipSetPixelOffsetMode` at `0x180005d21`
- `gdiplus!GdipSetPixelOffsetMode` at `0x180005cdf`
- `gdiplus!GdipSetPixelOffsetMode` at `0x180005d21`
- `gdiplus!GdipFillPolygonI` at `0x180005d0b`
- `gdiplus!GdipFillPolygonI` at `0x180005d0b`
- `gdiplus!GdipGetFontHeight` at `0x180005845`
- `gdiplus!GdipGetFontHeight` at `0x180005845`
- `GDI32!GetDeviceCaps` at `0x1800055c2`
- `GDI32!GetDeviceCaps` at `0x1800055f0`
- `GDI32!GetDeviceCaps` at `0x1800055c2`
- `GDI32!GetDeviceCaps` at `0x1800055f0`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x1800058a0`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x1800058a0`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x1800058b3`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x180005951`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x1800058b3`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x180005951`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UIControls::SplitButtonEx::PaintContent(
        HWND *this,
        struct Gdiplus::Graphics *a2,
        int a3,
        struct tagRECT *a4,
        unsigned int a5)
{
  struct Gdiplus::Graphics *v5; // r12
  HWND *v6; // rsi
  HWND v7; // r15
  int v9; // eax
  int PageUnit; // eax
  int v11; // eax
  int v12; // r13d
  HDC v13; // rax
  int DeviceCaps; // eax
  int v15; // eax
  struct tagRECT *SplitAreaRect; // rax
  LONG top; // ebx
  LONG bottom; // r11d
  int v19; // r9d
  LONG v20; // r10d
  int v21; // eax
  int v22; // r14d
  int v23; // r14d
  int v24; // eax
  int v25; // eax
  int v26; // eax
  unsigned int v27; // r14d
  struct Gdiplus::Font *Font; // rax
  struct Gdiplus::Font *v29; // rbx
  __int64 v30; // rdx
  int FontHeight; // eax
  float v32; // xmm0_4
  __int64 BaseStringManager; // rax
  HWND v34; // rbx
  __int64 v35; // rdx
  __int64 v36; // r8
  int WindowTextW; // eax
  HWND v38; // r10
  int v39; // r9d
  struct Gdiplus::Font *v40; // rax
  int v41; // ecx
  LONG left; // r8d
  struct tagRECT *v43; // r13
  int v44; // r9d
  int v45; // r8d
  const unsigned __int16 *v46; // rax
  int ArrowTop; // r9d
  int v48; // ecx
  int PixelOffsetMode; // eax
  int v50; // eax
  int v51; // eax
  int v52; // eax
  struct Gdiplus::Font *v53; // [rsp+20h] [rbp-178h]
  const struct Gdiplus::Brush *v54; // [rsp+38h] [rbp-160h]
  unsigned int v55; // [rsp+70h] [rbp-128h] BYREF
  int nNumber; // [rsp+74h] [rbp-124h]
  int v57; // [rsp+78h] [rbp-120h]
  unsigned int v58; // [rsp+7Ch] [rbp-11Ch]
  HDC hdc; // [rsp+80h] [rbp-118h] BYREF
  __int64 v60; // [rsp+88h] [rbp-110h] BYREF
  int v61; // [rsp+90h] [rbp-108h]
  HWND hWnd; // [rsp+98h] [rbp-100h] BYREF
  unsigned int v63; // [rsp+A0h] [rbp-F8h]
  struct tagRECT *v64; // [rsp+A8h] [rbp-F0h]
  struct tagRECT *v65; // [rsp+B0h] [rbp-E8h]
  HWND v66; // [rsp+B8h] [rbp-E0h] BYREF
  LONG *p_right; // [rsp+C0h] [rbp-D8h]
  struct tagRECT v68; // [rsp+C8h] [rbp-D0h] BYREF
  LONG *v69; // [rsp+D8h] [rbp-C0h]
  struct Gdiplus::Graphics *v70; // [rsp+E0h] [rbp-B8h]
  struct tagRECT *v71; // [rsp+E8h] [rbp-B0h]
  HWND *v72; // [rsp+F0h] [rbp-A8h]
  char v73[8]; // [rsp+100h] [rbp-98h] BYREF
  __int64 v74; // [rsp+108h] [rbp-90h]
  struct tagRECT v75; // [rsp+118h] [rbp-80h] BYREF
  __int128 v76; // [rsp+128h] [rbp-70h] BYREF
  int v77; // [rsp+138h] [rbp-60h]
  int v78; // [rsp+13Ch] [rbp-5Ch]

  v65 = a4;
  v61 = a3;
  v5 = a2;
  v6 = this;
  v70 = a2;
  v71 = a4;
  v72 = this;
  v7 = (HWND)a2;
  v64 = a4;
  p_right = &a4->right;
  if ( a4->right - a4->left > 0 && a4->bottom - a4->top > 0 )
  {
    v69 = &a4->right;
    v75 = 0;
    GetClientRect(this[1], &v75);
    v9 = GdipSetInterpolationMode(*(_QWORD *)v7, 1);
    if ( v9 )
      *((_DWORD *)v7 + 2) = v9;
    v57 = 0;
    v60 = 0;
    UIControls::ButtonEx::UpdateImage((UIControls::ButtonEx *)v6);
    v66 = v6[24];
    *(_QWORD *)&v76 = v66;
    if ( v66 )
    {
      v55 = 0;
      PageUnit = GdipGetPageUnit(*(_QWORD *)v5, &v55);
      if ( PageUnit )
        *((_DWORD *)v5 + 2) = PageUnit;
      v11 = GdipSetPageUnit(*(_QWORD *)v5, 2);
      if ( v11 )
        *((_DWORD *)v5 + 2) = v11;
      hWnd = v6[1];
      hdc = GetDC(hWnd);
      UIControls::ButtonEx::UpdateImage((UIControls::ButtonEx *)v6);
      v12 = *((_DWORD *)v6 + 50);
      LODWORD(v60) = v12;
      UIControls::ButtonEx::UpdateImage((UIControls::ButtonEx *)v6);
      nNumber = *((_DWORD *)v6 + 51);
      v13 = hdc;
      if ( hdc )
      {
        DeviceCaps = GetDeviceCaps(hdc, 88);
        v12 = MulDiv(v12, DeviceCaps, 96);
        LODWORD(v60) = v12;
        v15 = GetDeviceCaps(hdc, 90);
        nNumber = MulDiv(nNumber, v15, 96);
        v13 = hdc;
      }
      ReleaseDC(hWnd, v13);
      if ( *((_DWORD *)v6 + 154) )
      {
        v57 = a4->left + *((_DWORD *)v6 + 140);
        v21 = a4->top + a4->bottom / 2 - nNumber / (*((_BYTE *)v6 + 601) != 0 ? 4 : 2);
      }
      else
      {
        SplitAreaRect = UIControls::SplitButtonEx::GetSplitAreaRect((UIControls::SplitButtonEx *)v6, &v68, v5, &v75);
        top = SplitAreaRect->top;
        bottom = SplitAreaRect->bottom;
        v19 = *((_DWORD *)v6 + 154);
        v20 = top;
        if ( !v19 )
          v20 = v75.top;
        v57 = (a4->left + a4->right - v12) / 2;
        if ( v19 )
          top = bottom;
        v21 = (v20 + top) / 2 - nNumber / (*((_BYTE *)v6 + 601) != 0 ? 4 : 2);
      }
      v63 = v21;
      v22 = v57;
      v58 = v57;
      if ( (GetWindowLongW(v6[1], -20) & 0x400000) != 0 && *((_DWORD *)v6 + 43) == 1 )
      {
        v58 = v22 + v12;
        v23 = -v12;
      }
      else
      {
        v23 = v12;
      }
      UIControls::ButtonEx::UpdateImage((UIControls::ButtonEx *)v6);
      LODWORD(hWnd) = *((_DWORD *)v6 + 51);
      UIControls::ButtonEx::UpdateImage((UIControls::ButtonEx *)v6);
      LODWORD(hdc) = *((_DWORD *)v6 + 50);
      UIControls::ButtonEx::UpdateImage((UIControls::ButtonEx *)v6);
      if ( (v61 & 0x20) != 0 )
      {
        v24 = *((_DWORD *)v6 + 50);
        if ( (v61 & 0x200) != 0 )
        {
          v24 *= 3;
        }
        else if ( (v61 & 0x100) != 0 )
        {
          v24 *= 2;
        }
      }
      else
      {
        v24 = 0;
      }
      LODWORD(v54) = 0;
      v25 = GdipDrawImageRectRectI(*(_QWORD *)v5, *((_QWORD *)v66 + 1), v58, v63, v23, nNumber, v24);
      if ( v25 )
        *((_DWORD *)v5 + 2) = v25;
      v26 = GdipSetPageUnit(*(_QWORD *)v5, v55);
      if ( v26 )
        *((_DWORD *)v5 + 2) = v26;
    }
    else
    {
      v12 = v60;
    }
    v27 = *((_DWORD *)v6 + 153);
    if ( v27 == -1 )
    {
      Font = UIControls::ButtonEx::GetFont((UIControls::ButtonEx *)v6);
      v29 = Font;
      if ( Font )
      {
        v55 = 0;
        if ( v5 )
          v30 = *(_QWORD *)v5;
        else
          v30 = 0;
        FontHeight = GdipGetFontHeight(*(_QWORD *)Font, v30, &v55);
        if ( FontHeight )
          *((_DWORD *)v29 + 2) = FontHeight;
        v32 = *(float *)&v55;
      }
      else
      {
        v32 = 0.0;
      }
      if ( v32 <= 0.0 || (v27 = (unsigned int)(int)(float)(v32 + 1.0) >> 2, v27 < 3) )
        v27 = 3;
    }
    nNumber = v27;
    UIControls::SplitButtonEx::GetSplitAreaRect((UIControls::SplitButtonEx *)v6, &v68, v5, &v75);
    BaseStringManager = Base::String::GetBaseStringManager();
    if ( !BaseStringManager )
    {
      ATL::BaseAtlThrow(-2147467259);
      __debugbreak();
    }
    v34 = (HWND)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)BaseStringManager + 24LL))(BaseStringManager) + 24);
    hWnd = v34;
    v35 = (unsigned int)(GetWindowTextLengthW(v6[1]) + 1);
    LODWORD(hdc) = v35;
    if ( (int)((*((_DWORD *)v34 - 3) - v35) | (1 - *((_DWORD *)v34 - 2))) < 0 )
    {
      try
      {
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&hWnd, v35, v36);
        v34 = hWnd;
        LODWORD(v35) = (_DWORD)hdc;
      }
      catch ( ... )
      {
        goto LABEL_55;
      }
    }
    WindowTextW = GetWindowTextW(v6[1], (LPWSTR)v34, v35);
    if ( WindowTextW == -1 )
      WindowTextW = ATL::CSimpleStringT<unsigned short,0>::StringLength(v34);
    if ( WindowTextW < 0 || WindowTextW > *((_DWORD *)v34 - 3) )
    {
      ATL::BaseAtlThrow(-2147024809);
LABEL_55:
      v61 = a3;
      v12 = v60;
      v34 = hWnd;
      p_right = v69;
      v27 = nNumber;
      v5 = v70;
      v65 = v71;
      v6 = v72;
      v7 = (HWND)v70;
      v38 = (HWND)v76;
    }
    else
    {
      *((_DWORD *)v34 - 4) = WindowTextW;
      *((_WORD *)v34 + WindowTextW) = 0;
      v38 = v66;
    }
    v39 = v57;
    LODWORD(v66) = 0;
    v58 = 0;
    if ( *((_DWORD *)v34 - 4) )
    {
      v76 = 0;
      if ( *((_DWORD *)v6 + 154) )
      {
        DWORD1(v76) = v64->top;
        HIDWORD(v76) = v64->bottom;
        v45 = *((_DWORD *)v6 + 142);
        v57 = v45;
        LODWORD(v76) = v45;
        v55 = v64->right - (v27 != 0 ? 4 : 0) - 2 * v27;
        DWORD2(v76) = v55;
        if ( v38 )
        {
          v57 = v12 + v39 + v45;
          LODWORD(v76) = v57;
        }
        v43 = v64;
      }
      else
      {
        v40 = UIControls::ButtonEx::GetFont((UIControls::ButtonEx *)v6);
        v53 = (struct Gdiplus::Font *)&v66;
        GdipUtil::MeasureStringHelper(v7, v40, v34);
        v41 = 2 * v27 + 6;
        if ( !v27 )
          v41 = 4;
        left = v65->left;
        v43 = v64;
        v44 = (int)v66;
        if ( (int)v66 >= v64->right - v41 - v65->left )
          v44 = v64->right - v41 - v65->left;
        if ( v44 <= 0 )
          v44 = 0;
        v58 = v41 + v44;
        HIDWORD(v76) = v68.bottom - (*((_BYTE *)v6 + 602) != 0 ? 3 : 0) - 1;
        v57 = (v64->right + left - (v41 + v44)) / 2 + 2;
        *(_QWORD *)&v76 = __PAIR64__(v68.top, v57);
        v55 = v44 + v57;
        DWORD2(v76) = v44 + v57;
      }
      Gdiplus::StringFormat::SetAlignment(v6 + 73, 1);
      Gdiplus::StringFormat::SetLineAlignment(v6 + 73, 1);
      Gdiplus::StringFormat::SetHotkeyPrefix(v6 + 73, 2 - (unsigned int)((v61 & 0x800) != 0));
      LODWORD(hdc) = a5;
      Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v73, (const struct Gdiplus::Color *)&hdc);
      if ( (int)v55 > v57 )
      {
        v46 = (const unsigned __int16 *)UIControls::ButtonEx::GetFont((UIControls::ButtonEx *)v6);
        UIBase::DrawTextHandleRTL(
          v6[1],
          v7,
          (wchar_t *)v34,
          v46,
          (const struct Gdiplus::Font *)&v76,
          (const struct tagRECT *)(v6 + 73),
          (struct Gdiplus::StringFormat *)v73,
          v54);
      }
      GdipDeleteBrush(v74);
    }
    else
    {
      v43 = v64;
    }
    if ( v27 )
    {
      ArrowTop = UIControls::SplitButtonEx::GetArrowTop(
                   (UIControls::SplitButtonEx *)v6,
                   (const struct Gdiplus::Graphics *)v7,
                   v43);
      if ( *((_DWORD *)v6 + 154) )
        v48 = v68.right - (*((_BYTE *)v6 + 602) != 0) - 3;
      else
        v48 = (int)(v58 + v65->left + *p_right) / 2 - 2;
      LODWORD(v76) = v48 - 2 * v27;
      DWORD1(v76) = ArrowTop;
      DWORD2(v76) = v48 - v27;
      HIDWORD(v76) = ArrowTop + v27;
      v77 = v48;
      v78 = ArrowTop;
      v60 = 0;
      GdipCreateSolidFill(a5, &v60);
      v55 = -1;
      PixelOffsetMode = GdipGetPixelOffsetMode(*(_QWORD *)v5, &v55);
      if ( PixelOffsetMode )
        *((_DWORD *)v7 + 2) = PixelOffsetMode;
      v50 = GdipSetPixelOffsetMode(*(_QWORD *)v5, 4);
      if ( v50 )
        *((_DWORD *)v7 + 2) = v50;
      LODWORD(v53) = 0;
      v51 = GdipFillPolygonI(*(_QWORD *)v5, v60, &v76, 3, v53);
      if ( v51 )
        *((_DWORD *)v7 + 2) = v51;
      v52 = GdipSetPixelOffsetMode(*(_QWORD *)v5, v55);
      if ( v52 )
        *((_DWORD *)v7 + 2) = v52;
      GdipDeleteBrush(v60);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v34 - 6));
  }
}

```

## disassembly

```asm
0x180005434  mov     r11, rsp
0x180005437  mov     [r11+18h], r8d
0x18000543b  push    rbx
0x18000543c  push    rsi
0x18000543d  push    rdi
0x18000543e  push    r12
0x180005440  push    r13
0x180005442  push    r14
0x180005444  push    r15
0x180005446  sub     rsp, 160h
0x18000544d  movaps  xmmword ptr [r11-48h], xmm6
0x180005452  mov     rax, cs:__security_cookie
0x180005459  xor     rax, rsp
0x18000545c  mov     [rsp+198h+var_58], rax
0x180005464  mov     [rsp+198h+var_E8], r9
0x18000546c  mov     [rsp+198h+var_108], r8d
0x180005474  mov     r12, rdx
0x180005477  mov     rsi, rcx
0x18000547a  mov     [rsp+198h+var_B8], rdx
0x180005482  mov     [rsp+198h+var_B0], r9
0x18000548a  mov     [rsp+198h+var_A8], rcx
0x180005492  mov     r15, rdx
0x180005495  mov     r14, r9
0x180005498  mov     [rsp+198h+var_F0], r9
0x1800054a0  lea     rcx, [r9+8]
0x1800054a4  mov     [rsp+198h+var_D8], rcx
0x1800054ac  mov     eax, [rcx]
0x1800054ae  sub     eax, [r9]
0x1800054b1  xor     edi, edi
0x1800054b3  test    eax, eax
0x1800054b5  jle     loc_180005D48
0x1800054bb  mov     eax, [r9+0Ch]
0x1800054bf  sub     eax, [r9+4]
0x1800054c3  test    eax, eax
0x1800054c5  jle     loc_180005D48
0x1800054cb  mov     [rsp+198h+var_C0], rcx
0x1800054d3  xorps   xmm0, xmm0
0x1800054d6  movups  xmmword ptr [r11-80h], xmm0
0x1800054db  lea     rdx, [r11-80h]; lpRect
0x1800054df  mov     rcx, [rsi+8]; hWnd
0x1800054e3  call    cs:__imp_GetClientRect
0x1800054e9  lea     edx, [rdi+1]
0x1800054ec  mov     rcx, [r15]
0x1800054ef  call    cs:__imp_GdipSetInterpolationMode
0x1800054f5  test    eax, eax
0x1800054f7  jz      short loc_1800054FD
0x1800054f9  mov     [r15+8], eax
0x1800054fd  mov     [rsp+198h+var_120], edi
0x180005501  mov     [rsp+198h+var_110], rdi
0x180005509  mov     rcx, rsi; this
0x18000550c  call    ?UpdateImage@ButtonEx@UIControls@@AEBAXXZ; UIControls::ButtonEx::UpdateImage(void)
0x180005511  mov     rax, [rsi+0C0h]
0x180005518  mov     [rsp+198h+var_E0], rax
0x180005520  mov     qword ptr [rsp+198h+var_70], rax
0x180005528  test    rax, rax
0x18000552b  jz      loc_180005803
0x180005531  mov     [rsp+198h+var_128], edi
0x180005535  lea     rdx, [rsp+198h+var_128]
0x18000553a  mov     rcx, [r12]
0x18000553e  call    cs:__imp_GdipGetPageUnit
0x180005544  test    eax, eax
0x180005546  jz      short loc_18000554D
0x180005548  mov     [r12+8], eax
0x18000554d  mov     ebx, 2
0x180005552  mov     edx, ebx
0x180005554  mov     rcx, [r12]
0x180005558  call    cs:__imp_GdipSetPageUnit
0x18000555e  test    eax, eax
0x180005560  jz      short loc_180005567
0x180005562  mov     [r12+8], eax
0x180005567  mov     rax, [rsi+8]
0x18000556b  mov     [rsp+198h+hWnd], rax
0x180005573  mov     rcx, rax; hWnd
0x180005576  call    cs:__imp_GetDC
0x18000557c  mov     [rsp+198h+hdc], rax
0x180005584  mov     rcx, rsi; this
0x180005587  call    ?UpdateImage@ButtonEx@UIControls@@AEBAXXZ; UIControls::ButtonEx::UpdateImage(void)
0x18000558c  mov     r13d, [rsi+0C8h]
0x180005593  mov     dword ptr [rsp+198h+var_110], r13d
0x18000559b  mov     rcx, rsi; this
0x18000559e  call    ?UpdateImage@ButtonEx@UIControls@@AEBAXXZ; UIControls::ButtonEx::UpdateImage(void)
0x1800055a3  mov     eax, [rsi+0CCh]
0x1800055a9  mov     [rsp+198h+nNumber], eax
0x1800055ad  mov     rax, [rsp+198h+hdc]
0x1800055b5  test    rax, rax
0x1800055b8  jz      short loc_180005614
0x1800055ba  mov     edx, 58h ; 'X'; index
0x1800055bf  mov     rcx, rax; hdc
0x1800055c2  call    cs:__imp_GetDeviceCaps
0x1800055c8  mov     r8d, 60h ; '`'; nDenominator
0x1800055ce  mov     edx, eax; nNumerator
0x1800055d0  mov     ecx, r13d; nNumber
0x1800055d3  call    cs:__imp_MulDiv
0x1800055d9  mov     r13d, eax
0x1800055dc  mov     dword ptr [rsp+198h+var_110], eax
0x1800055e3  mov     edx, 5Ah ; 'Z'; index
0x1800055e8  mov     rcx, [rsp+198h+hdc]; hdc
0x1800055f0  call    cs:__imp_GetDeviceCaps
0x1800055f6  mov     r8d, 60h ; '`'; nDenominator
0x1800055fc  mov     edx, eax; nNumerator
0x1800055fe  mov     ecx, [rsp+198h+nNumber]; nNumber
0x180005602  call    cs:__imp_MulDiv
0x180005608  mov     [rsp+198h+nNumber], eax
0x18000560c  mov     rax, [rsp+198h+hdc]
0x180005614  mov     rdx, rax; hDC
0x180005617  mov     rcx, [rsp+198h+hWnd]; hWnd
0x18000561f  call    cs:__imp_ReleaseDC
0x180005625  cmp     [rsi+268h], edi
0x18000562b  jnz     loc_1800056B2
0x180005631  lea     r9, [rsp+198h+var_80]; struct tagRECT *
0x180005639  mov     r8, r12; struct Gdiplus::Graphics *
0x18000563c  lea     rdx, [rsp+198h+var_D0]; retstr
0x180005644  mov     rcx, rsi; this
0x180005647  call    ?GetSplitAreaRect@SplitButtonEx@UIControls@@IEAA?AUtagRECT@@AEBVGraphics@Gdiplus@@AEBU3@@Z; UIControls::SplitButtonEx::GetSplitAreaRect(Gdiplus::Graphics const &,tagRECT const &)
0x18000564c  mov     ebx, [rax+4]
0x18000564f  mov     r11d, [rax+0Ch]
0x180005653  mov     r9d, [rsi+268h]
0x18000565a  mov     r10d, ebx
0x18000565d  test    r9d, r9d
0x180005660  cmovz   r10d, [rsp+198h+var_80.top]
0x180005669  mov     eax, [r14+8]
0x18000566d  sub     eax, r13d
0x180005670  add     eax, [r14]
0x180005673  cdq
0x180005674  mov     r14d, 2
0x18000567a  idiv    r14d
0x18000567d  mov     [rsp+198h+var_120], eax
0x180005681  mov     cl, [rsi+259h]
0x180005687  neg     cl
0x180005689  sbb     r8d, r8d
0x18000568c  and     r8d, r14d
0x18000568f  add     r8d, r14d
0x180005692  mov     eax, [rsp+198h+nNumber]
0x180005696  cdq
0x180005697  idiv    r8d
0x18000569a  mov     ecx, eax
0x18000569c  test    r9d, r9d
0x18000569f  cmovnz  ebx, r11d
0x1800056a3  lea     eax, [r10+rbx]
0x1800056a7  cdq
0x1800056a8  mov     ebx, r14d
0x1800056ab  idiv    r14d
0x1800056ae  sub     eax, ecx
0x1800056b0  jmp     short loc_1800056E3
0x1800056b2  mov     eax, [rsi+230h]
0x1800056b8  add     eax, [r14]
0x1800056bb  mov     [rsp+198h+var_120], eax
0x1800056bf  mov     al, [rsi+259h]
0x1800056c5  neg     al
0x1800056c7  sbb     ecx, ecx
0x1800056c9  and     ecx, ebx
0x1800056cb  add     ecx, ebx
0x1800056cd  mov     eax, [rsp+198h+nNumber]
0x1800056d1  cdq
0x1800056d2  idiv    ecx
0x1800056d4  mov     ecx, eax
0x1800056d6  mov     eax, [r14+0Ch]
0x1800056da  cdq
0x1800056db  idiv    ebx
0x1800056dd  sub     eax, ecx
0x1800056df  add     eax, [r14+4]
0x1800056e3  mov     [rsp+198h+var_F8], eax
0x1800056ea  mov     r14d, [rsp+198h+var_120]
0x1800056ef  mov     [rsp+198h+var_11C], r14d
0x1800056f4  mov     edx, 0FFFFFFECh; nIndex
0x1800056f9  mov     rcx, [rsi+8]; hWnd
0x1800056fd  call    cs:__imp_GetWindowLongW
0x180005703  bt      eax, 16h
0x180005707  jnb     short loc_180005722
0x180005709  cmp     dword ptr [rsi+0ACh], 1
0x180005710  jnz     short loc_180005722
0x180005712  lea     eax, [r14+r13]
0x180005716  mov     [rsp+198h+var_11C], eax
0x18000571a  mov     r14d, r13d
0x18000571d  neg     r14d
0x180005720  jmp     short loc_180005725
0x180005722  mov     r14d, r13d
0x180005725  mov     rcx, rsi; this
0x180005728  call    ?UpdateImage@ButtonEx@UIControls@@AEBAXXZ; UIControls::ButtonEx::UpdateImage(void)
0x18000572d  mov     eax, [rsi+0CCh]
0x180005733  mov     dword ptr [rsp+198h+hWnd], eax
0x18000573a  mov     rcx, rsi; this
0x18000573d  call    ?UpdateImage@ButtonEx@UIControls@@AEBAXXZ; UIControls::ButtonEx::UpdateImage(void)
0x180005742  mov     eax, [rsi+0C8h]
0x180005748  mov     dword ptr [rsp+198h+hdc], eax
0x18000574f  mov     rcx, rsi; this
0x180005752  call    ?UpdateImage@ButtonEx@UIControls@@AEBAXXZ; UIControls::ButtonEx::UpdateImage(void)
0x180005757  mov     ecx, [rsp+198h+var_108]
0x18000575e  test    cl, 20h
0x180005761  jnz     short loc_180005767
0x180005763  mov     eax, edi
0x180005765  jmp     short loc_180005780
0x180005767  mov     eax, [rsi+0C8h]
0x18000576d  bt      ecx, 9
0x180005771  jnb     short loc_180005778
0x180005773  lea     eax, [rax+rax*2]
0x180005776  jmp     short loc_180005780
0x180005778  bt      ecx, 8
0x18000577c  jnb     short loc_180005780
0x18000577e  add     eax, eax
0x180005780  mov     [rsp+198h+var_130], rdi
0x180005785  mov     [rsp+198h+var_138], rdi
0x18000578a  mov     [rsp+198h+var_140], rdi
0x18000578f  mov     [rsp+198h+var_148], ebx
0x180005793  mov     ecx, dword ptr [rsp+198h+hWnd]
0x18000579a  mov     [rsp+198h+var_150], ecx
0x18000579e  mov     ecx, dword ptr [rsp+198h+hdc]
0x1800057a5  mov     [rsp+198h+var_158], ecx
0x1800057a9  mov     dword ptr [rsp+198h+var_160], edi
0x1800057ad  mov     dword ptr [rsp+198h+var_168], eax
0x1800057b1  mov     eax, [rsp+198h+nNumber]
0x1800057b5  mov     dword ptr [rsp+198h+var_170], eax
0x1800057b9  mov     dword ptr [rsp+198h+var_178], r14d
0x1800057be  mov     r9d, [rsp+198h+var_F8]
0x1800057c6  mov     r8d, [rsp+198h+var_11C]
0x1800057cb  mov     rdx, [rsp+198h+var_E0]
0x1800057d3  mov     rdx, [rdx+8]
0x1800057d7  mov     rcx, [r12]
0x1800057db  call    cs:__imp_GdipDrawImageRectRectI
0x1800057e1  test    eax, eax
0x1800057e3  jz      short loc_1800057EA
0x1800057e5  mov     [r12+8], eax
0x1800057ea  mov     edx, [rsp+198h+var_128]
0x1800057ee  mov     rcx, [r12]
0x1800057f2  call    cs:__imp_GdipSetPageUnit
0x1800057f8  test    eax, eax
0x1800057fa  jz      short loc_18000580B
0x1800057fc  mov     [r12+8], eax
0x180005801  jmp     short loc_18000580B
0x180005803  mov     r13d, dword ptr [rsp+198h+var_110]
0x18000580b  mov     r14d, [rsi+264h]
0x180005812  cmp     r14d, 0FFFFFFFFh
0x180005816  jnz     short loc_18000587F
0x180005818  mov     rcx, rsi; this
0x18000581b  call    ?GetFont@ButtonEx@UIControls@@QEAAPEAVFont@Gdiplus@@XZ; UIControls::ButtonEx::GetFont(void)
0x180005820  mov     rbx, rax
0x180005823  xorps   xmm6, xmm6
0x180005826  test    rax, rax
0x180005829  jz      short loc_18000585A
0x18000582b  mov     [rsp+198h+var_128], edi
0x18000582f  test    r12, r12
0x180005832  jz      short loc_18000583A
0x180005834  mov     rdx, [r12]
0x180005838  jmp     short loc_18000583D
0x18000583a  mov     rdx, rdi
0x18000583d  lea     r8, [rsp+198h+var_128]
0x180005842  mov     rcx, [rax]
0x180005845  call    cs:__imp_GdipGetFontHeight
0x18000584b  test    eax, eax
0x18000584d  jz      short loc_180005852
0x18000584f  mov     [rbx+8], eax
0x180005852  movss   xmm0, [rsp+198h+var_128]
0x180005858  jmp     short loc_18000585D
0x18000585a  xorps   xmm0, xmm0
0x18000585d  comiss  xmm0, xmm6
0x180005860  jbe     short loc_180005879
0x180005862  addss   xmm0, cs:__real@3f800000
0x18000586a  cvttss2si r14, xmm0
0x18000586f  shr     r14d, 2
0x180005873  cmp     r14d, 3
0x180005877  jnb     short loc_18000587F
0x180005879  mov     r14d, 3
0x18000587f  mov     [rsp+198h+nNumber], r14d
0x180005884  lea     r9, [rsp+198h+var_80]; struct tagRECT *
0x18000588c  mov     r8, r12; struct Gdiplus::Graphics *
0x18000588f  lea     rdx, [rsp+198h+var_D0]; retstr
0x180005897  mov     rcx, rsi; this
0x18000589a  call    ?GetSplitAreaRect@SplitButtonEx@UIControls@@IEAA?AUtagRECT@@AEBVGraphics@Gdiplus@@AEBU3@@Z; UIControls::SplitButtonEx::GetSplitAreaRect(Gdiplus::Graphics const &,tagRECT const &)
0x18000589f  nop
0x1800058a0  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x1800058a6  mov     rcx, rax
0x1800058a9  test    rax, rax
0x1800058ac  jnz     short loc_1800058BA
0x1800058ae  mov     ecx, 80004005h
0x1800058b3  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1800058b9  int     3; Trap to Debugger
0x1800058ba  mov     rax, [rax]
0x1800058bd  mov     rax, [rax+18h]
0x1800058c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058c6  lea     rbx, [rax+18h]
0x1800058ca  mov     [rsp+198h+hWnd], rbx
0x1800058d2  mov     rcx, [rsi+8]; hWnd
0x1800058d6  call    cs:__imp_GetWindowTextLengthW
0x1800058dc  lea     edx, [rax+1]
0x1800058df  mov     dword ptr [rsp+198h+hdc], edx
0x1800058e6  mov     ecx, 1
0x1800058eb  sub     ecx, [rbx-8]
0x1800058ee  mov     eax, [rbx-0Ch]
0x1800058f1  sub     eax, edx
0x1800058f3  or      ecx, eax
0x1800058f5  jge     short loc_180005913
0x1800058f7  lea     rcx, [rsp+198h+hWnd]
0x1800058ff  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180005904  mov     rbx, [rsp+198h+hWnd]
0x18000590c  mov     edx, dword ptr [rsp+198h+hdc]
0x180005913  mov     r8d, edx; nMaxCount
0x180005916  mov     rdx, rbx; lpString
0x180005919  mov     rcx, [rsi+8]; hWnd
0x18000591d  call    cs:__imp_GetWindowTextW
0x180005923  cmp     eax, 0FFFFFFFFh
  ... truncated ...
```
