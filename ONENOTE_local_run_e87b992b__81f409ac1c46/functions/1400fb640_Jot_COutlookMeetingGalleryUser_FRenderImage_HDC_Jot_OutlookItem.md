# Jot::COutlookMeetingGalleryUser::FRenderImage(HDC__ *,Jot::OutlookItem *)

- ea: `0x1400fb640`
- end: `0x1400fbb0e`
- name: `?FRenderImage@COutlookMeetingGalleryUser@Jot@@AEAA_NPEAUHDC__@@PEAUOutlookItem@2@@Z`
- size: `1230`
- prototype: `bool(Jot::COutlookMeetingGalleryUser *__hidden this, HDC, struct Jot::OutlookItem *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x1400c6b60`

## callees

- `0x1400209a0`
- `0x140026d20`
- `0x140028f18`
- `0x14003b714`
- `0x14003f250`
- `0x1400478a8`
- `0x140056ac0`
- `0x140057580`
- `0x14008bfc4`
- `0x14008c058`
- `0x1400a2378`
- `0x1400a71b4`
- `0x1400a7280`
- `0x1400adddc`
- `0x1400bcd4c`
- `0x1400c14d4`
- `0x1400ca894`
- `0x1400fb640`

## import_xrefs

- `onmain!?UseColorMap@ColorMap@OneNote@@YAAEAUAColorMap@12@XZ` at `0x1400fb8f7`
- `onmain!?UseColorMap@ColorMap@OneNote@@YAAEAUAColorMap@12@XZ` at `0x1400fb8f7`
- `onmain!?CanvasShouldDisplayDarkMode@System@Jot@@YA_NXZ` at `0x1400fb8ed`
- `onmain!?CanvasShouldDisplayDarkMode@System@Jot@@YA_NXZ` at `0x1400fb8ed`
- `onmain!?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ` at `0x1400fb75f`
- `onmain!?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ` at `0x1400fb75f`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400fb791`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400fb9ce`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400fb9ef`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400fb791`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400fb9ce`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x1400fb9ef`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1400fb7c7`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1400fb7c7`
- `GDI32!SetTextColor` at `0x1400fb805`
- `GDI32!SetTextColor` at `0x1400fb924`
- `GDI32!SetTextColor` at `0x1400fb945`
- `GDI32!SetTextColor` at `0x1400fba9e`
- `GDI32!SetTextColor` at `0x1400fb805`
- `GDI32!SetTextColor` at `0x1400fb924`
- `GDI32!SetTextColor` at `0x1400fb945`
- `GDI32!SetTextColor` at `0x1400fba9e`
- `GDI32!SetBkColor` at `0x1400fb814`
- `GDI32!SetBkColor` at `0x1400fbaab`
- `GDI32!SetBkColor` at `0x1400fb814`
- `GDI32!SetBkColor` at `0x1400fbaab`
- `GDI32!EnumFontFamiliesExW` at `0x1400fb7ea`
- `GDI32!EnumFontFamiliesExW` at `0x1400fb7ea`
- `gdiplus!GdipDeleteGraphics` at `0x1400fbad7`
- `gdiplus!GdipDeleteGraphics` at `0x1400fbad7`
- `gdiplus!GdipDrawRectangleI` at `0x1400fba91`
- `gdiplus!GdipDrawRectangleI` at `0x1400fba91`
- `gdiplus!GdipDeletePen` at `0x1400fbab6`
- `gdiplus!GdipDeletePen` at `0x1400fbab6`
- `gdiplus!GdipFillRectangleI` at `0x1400fb71a`
- `gdiplus!GdipFillRectangleI` at `0x1400fb71a`
- `gdiplus!GdipDeleteBrush` at `0x1400fbacc`
- `gdiplus!GdipDeleteBrush` at `0x1400fbacc`
- `USER32!GetSysColor` at `0x1400fb90b`
- `USER32!GetSysColor` at `0x1400fb933`
- `USER32!GetSysColor` at `0x1400fb90b`
- `USER32!GetSysColor` at `0x1400fb933`
- `MSO!__imp_MsoDrawTextW` at `0x1400fb8ac`
- `MSO!__imp_MsoDrawTextW` at `0x1400fb98f`
- `MSO!__imp_MsoDrawTextW` at `0x1400fba17`
- `MSO!__imp_MsoDrawTextW` at `0x1400fb8ac`
- `MSO!__imp_MsoDrawTextW` at `0x1400fb98f`
- `MSO!__imp_MsoDrawTextW` at `0x1400fba17`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1400fb8e3`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1400fb8e3`
- `Mso20Win32Client!__imp_?MsoScaleForDPI@@YAHH@Z` at `0x1400fb680`
- `Mso20Win32Client!__imp_?MsoScaleForDPI@@YAHH@Z` at `0x1400fb68d`
- `Mso20Win32Client!__imp_?MsoScaleForDPI@@YAHH@Z` at `0x1400fb680`
- `Mso20Win32Client!__imp_?MsoScaleForDPI@@YAHH@Z` at `0x1400fb68d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall Jot::COutlookMeetingGalleryUser::FRenderImage(
        Jot::COutlookMeetingGalleryUser *this,
        HDC a2,
        struct Jot::OutlookItem *a3)
{
  int v5; // edi
  signed int v6; // esi
  COLORREF v7; // ebx
  int v8; // eax
  int v9; // ecx
  int v10; // r15d
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  const wchar_t *v14; // r8
  COLORREF v15; // eax
  int v16; // r12d
  __int64 v17; // rdx
  __int64 v18; // rsi
  __int64 v19; // r8
  int v20; // r15d
  Jot::System *v21; // rcx
  OneNote::ColorMap *v22; // rcx
  struct OneNote::ColorMap::AColorMap *v23; // rdi
  __int64 (__fastcall *v24)(struct OneNote::ColorMap::AColorMap *, _QWORD); // rbx
  DWORD v25; // eax
  COLORREF v26; // eax
  DWORD SysColor; // eax
  Jot::COutlookMeetingGalleryUser *v28; // rcx
  COLORREF v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rsi
  __int64 v33; // rax
  Jot *v34; // rcx
  unsigned int FrameColor; // eax
  BYTE lParam; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int lParam_4; // [rsp+3Ch] [rbp-CCh] BYREF
  unsigned int v39; // [rsp+40h] [rbp-C8h] BYREF
  int v40; // [rsp+44h] [rbp-C4h]
  int v41; // [rsp+48h] [rbp-C0h]
  COLORREF color; // [rsp+4Ch] [rbp-BCh]
  COLORREF v43[2]; // [rsp+50h] [rbp-B8h]
  __int64 v44; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v45[3]; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v46; // [rsp+78h] [rbp-90h]
  __int64 v47; // [rsp+80h] [rbp-88h] BYREF
  char v48[8]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v49; // [rsp+98h] [rbp-70h]
  int v50; // [rsp+A8h] [rbp-60h] BYREF
  int v51; // [rsp+ACh] [rbp-5Ch]
  int v52; // [rsp+B0h] [rbp-58h]
  int v53; // [rsp+B4h] [rbp-54h]
  struct tagLOGFONTW Logfont; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v55[368]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v56[368]; // [rsp+288h] [rbp+180h] BYREF

  v5 = MsoScaleForDPI(328);
  v6 = MsoScaleForDPI(42);
  v39 = v6;
  Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)&v44, a2);
  Gdiplus::Graphics::SetPageUnit(&v44);
  v41 = v5 - 1;
  v40 = v6 - 1;
  v7 = sub_14008BFC4();
  lParam_4 = v7 & 0xFF00 | BYTE2(v7) | ((v7 | 0xFFFFFF00) << 16);
  Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)v48, (const struct Gdiplus::Color *)&lParam_4);
  v8 = GdipFillRectangleI(v44, v49, 0, 0, v5 - 1, v6 - 1);
  v9 = v45[0];
  if ( v8 )
    v9 = v8;
  LODWORD(v45[0]) = v9;
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(
    v56,
    *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 62),
    2647113253LL);
  v10 = *(_DWORD *)(MsoCF::CLangConfig::Instance() + 8) & 0xF00000;
  memset_0(&Logfont, 0, sizeof(Logfont));
  Gdiplus::Graphics::GetDpiY((Gdiplus::Graphics *)&v44);
  v11 = Jot::CWzInBuffer::operator wchar_t *(v56);
  Logfont.lfHeight = -(int)Ofc::Round<int,float>(v13, v12, v11);
  *(_QWORD *)&Logfont.lfWidth = 0;
  Logfont.lfOrientation = 0;
  Logfont.lfWeight = 700;
  *(_QWORD *)&Logfont.lfItalic = 0x1000000;
  wcscpy_s(Logfont.lfFaceName, 0x20u, v14);
  lParam = 1;
  EnumFontFamiliesExW(a2, &Logfont, Jot::GetCharSetForFont, (LPARAM)&lParam, 0);
  Logfont.lfPitchAndFamily = 0;
  Logfont.lfCharSet = lParam;
  v15 = sub_14008C058();
  color = SetTextColor(a2, v15);
  v43[0] = SetBkColor(a2, v7);
  v16 = v5 - 4;
  lParam_4 = v6 / 2;
  v46 = 0;
  *(_OWORD *)&v45[1] = 0;
  Ofc::CHFont::Create((Ofc::CHFont *)&v45[1], a2, &Logfont);
  if ( a3 )
  {
    v50 = 3;
    v51 = 3;
    v52 = v5 - 4;
    v53 = v6 / 2 - 2;
    v17 = *((_QWORD *)a3 + 5);
    v18 = -1;
    if ( v17 )
    {
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)(v17 + 2 * v19) );
    }
    else
    {
      v19 = 0;
    }
    v20 = v10 != 0 ? 133154 : 2080;
    MsoDrawTextW(a2, v17, v19, &v50, v20);
    Ofc::CHFont::~CHFont((Ofc::CHFont *)&v45[1]);
    Logfont.lfWeight = 400;
    *(_OWORD *)&v45[1] = 0;
    v46 = 0;
    Ofc::CHFont::Create((Ofc::CHFont *)&v45[1], a2, &Logfont);
    if ( MsoFCbvHighContrast() || !Jot::System::CanvasShouldDisplayDarkMode(v21) )
    {
      SysColor = GetSysColor(8);
      v29 = Jot::COutlookMeetingGalleryUser::LightenColor(v28, SysColor);
      SetTextColor(a2, v29);
    }
    else
    {
      v23 = OneNote::ColorMap::UseColorMap(v22);
      v24 = **(__int64 (__fastcall ***)(struct OneNote::ColorMap::AColorMap *, _QWORD))v23;
      v25 = GetSysColor(8);
      v26 = v24(v23, v25);
      SetTextColor(a2, v26);
    }
    v50 = 15;
    v51 = lParam_4 + 1;
    v52 = v16;
    v53 = v39 - 3;
    v30 = *((_QWORD *)a3 + 1);
    if ( v30 )
    {
      do
        ++v18;
      while ( *(_WORD *)(v30 + 2 * v18) );
    }
    else
    {
      LODWORD(v18) = 0;
    }
    MsoDrawTextW(a2, v30, (unsigned int)v18, &v50, v20);
  }
  else
  {
    Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(
      v55,
      *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 62),
      4156275593LL);
    v50 = 3;
    v51 = 3;
    v52 = v5 - 4;
    v53 = v6 / 2 - 2;
    v31 = Jot::CWzInBuffer::operator wchar_t *(v55);
    if ( v31 )
    {
      v32 = -1;
      do
        ++v32;
      while ( *(_WORD *)(v31 + 2 * v32) );
    }
    else
    {
      LODWORD(v32) = 0;
    }
    v33 = Jot::CWzInBuffer::operator wchar_t *(v55);
    MsoDrawTextW(a2, v33, (unsigned int)v32, &v50, v10 != 0 ? 133154 : 2080);
    Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v55);
  }
  Ofc::CHFont::~CHFont((Ofc::CHFont *)&v45[1]);
  FrameColor = Jot::GetFrameColor(v34);
  v39 = FrameColor & 0xFF00 | BYTE2(FrameColor) | ((FrameColor | 0xFFFFFF00) << 16);
  Gdiplus::Pen::Pen((Gdiplus::Pen *)&v47, (const struct Gdiplus::Color *)&v39, 1.0);
  GdipDrawRectangleI(v44, v47, 0, 0, v41, v40);
  SetTextColor(a2, color);
  SetBkColor(a2, v43[0]);
  GdipDeletePen(v47);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v56);
  GdipDeleteBrush(v49);
  GdipDeleteGraphics(v44);
  return 1;
}

```

## disassembly

```asm
0x1400fb640  mov     rax, rsp
0x1400fb643  mov     [rax+8], rbx
0x1400fb647  push    rbp
0x1400fb648  push    rsi
0x1400fb649  push    rdi
0x1400fb64a  push    r12
0x1400fb64c  push    r13
0x1400fb64e  push    r14
0x1400fb650  push    r15
0x1400fb652  lea     rbp, [rax-348h]
0x1400fb659  sub     rsp, 410h
0x1400fb660  movaps  xmmword ptr [rax-48h], xmm6
0x1400fb664  mov     rax, cs:__security_cookie
0x1400fb66b  xor     rax, rsp
0x1400fb66e  mov     [rbp+340h+var_50], rax
0x1400fb675  mov     r13, r8
0x1400fb678  mov     r14, rdx
0x1400fb67b  mov     ecx, 148h
0x1400fb680  call    cs:__imp_?MsoScaleForDPI@@YAHH@Z; MsoScaleForDPI(int)
0x1400fb686  mov     edi, eax
0x1400fb688  mov     ecx, 2Ah ; '*'
0x1400fb68d  call    cs:__imp_?MsoScaleForDPI@@YAHH@Z; MsoScaleForDPI(int)
0x1400fb693  mov     esi, eax
0x1400fb695  mov     [rsp+440h+var_408], eax
0x1400fb699  mov     rdx, r14; HDC
0x1400fb69c  lea     rcx, [rsp+440h+var_3F0]; this
0x1400fb6a1  call    ??0Graphics@Gdiplus@@QEAA@PEAUHDC__@@@Z; Gdiplus::Graphics::Graphics(HDC__ *)
0x1400fb6a6  lea     rcx, [rsp+440h+var_3F0]
0x1400fb6ab  call    ?SetPageUnit@Graphics@Gdiplus@@QEAA?AW4Status@2@W4Unit@2@@Z; Gdiplus::Graphics::SetPageUnit(Gdiplus::Unit)
0x1400fb6b0  lea     r15d, [rdi-1]
0x1400fb6b4  mov     [rsp+440h+var_400], r15d
0x1400fb6b9  lea     r12d, [rsi-1]
0x1400fb6bd  mov     [rsp+440h+var_404], r12d
0x1400fb6c2  call    sub_14008BFC4
0x1400fb6c7  mov     ebx, eax
0x1400fb6c9  movzx   r8d, ax
0x1400fb6cd  movzx   r9d, al
0x1400fb6d1  mov     eax, 0FFFFFF00h
0x1400fb6d6  or      r9d, eax
0x1400fb6d9  shl     r9d, 10h
0x1400fb6dd  mov     ecx, ebx
0x1400fb6df  shr     ecx, 10h
0x1400fb6e2  movzx   edx, cl
0x1400fb6e5  or      r9d, edx
0x1400fb6e8  and     r8d, eax
0x1400fb6eb  or      r9d, r8d
0x1400fb6ee  mov     dword ptr [rsp+440h+lParam+4], r9d
0x1400fb6f3  lea     rdx, [rsp+440h+lParam+4]; struct Gdiplus::Color *
0x1400fb6f8  lea     rcx, [rbp+340h+var_3B8]; this
0x1400fb6fc  call    ??0SolidBrush@Gdiplus@@QEAA@AEBVColor@1@@Z; Gdiplus::SolidBrush::SolidBrush(Gdiplus::Color const &)
0x1400fb701  mov     dword ptr [rsp+440h+var_418], r12d
0x1400fb706  mov     [rsp+440h+dwFlags], r15d
0x1400fb70b  xor     r9d, r9d
0x1400fb70e  xor     r8d, r8d
0x1400fb711  mov     rdx, [rbp+340h+var_3B0]
0x1400fb715  mov     rcx, [rsp+440h+var_3F0]
0x1400fb71a  call    cs:__imp_GdipFillRectangleI
0x1400fb720  mov     ecx, dword ptr [rsp+440h+var_3E8]
0x1400fb724  xor     r12d, r12d
0x1400fb727  test    eax, eax
0x1400fb729  cmovnz  ecx, eax
0x1400fb72c  mov     dword ptr [rsp+440h+var_3E8], ecx
0x1400fb730  mov     r8d, 9DC7BE25h
0x1400fb736  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x1400fb73d  mov     rdx, [rdx+1F0h]
0x1400fb744  lea     rcx, [rbp+340h+var_1C0]
0x1400fb74b  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@PEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(HINSTANCE__ *,uint)
0x1400fb750  movd    xmm6, esi
0x1400fb754  cvtdq2ps xmm6, xmm6
0x1400fb757  divss   xmm6, cs:__real@40600000
0x1400fb75f  call    cs:__imp_?Instance@CLangConfig@MsoCF@@SAPEAV12@XZ; MsoCF::CLangConfig::Instance(void)
0x1400fb765  mov     r15d, [rax+8]
0x1400fb769  and     r15d, 0F00000h
0x1400fb770  xor     edx, edx; Val
0x1400fb772  lea     r8d, [r12+5Ch]; Size
0x1400fb777  lea     rcx, [rbp+340h+Logfont]; void *
0x1400fb77b  call    memset_0
0x1400fb780  lea     rcx, [rsp+440h+var_3F0]; this
0x1400fb785  call    ?GetDpiY@Graphics@Gdiplus@@QEBAMXZ; Gdiplus::Graphics::GetDpiY(void)
0x1400fb78a  lea     rcx, [rbp+340h+var_1C0]
0x1400fb791  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x1400fb797  mov     r8, rax
0x1400fb79a  movaps  xmm0, xmm6
0x1400fb79d  call    ??$Round@HM@Ofc@@YAHM@Z; Ofc::Round<int,float>(float)
0x1400fb7a2  neg     eax
0x1400fb7a4  mov     [rbp+340h+Logfont.lfHeight], eax
0x1400fb7a7  mov     qword ptr [rbp+340h+Logfont.lfWidth], r12
0x1400fb7ab  mov     [rbp+340h+Logfont.lfOrientation], r12d
0x1400fb7af  mov     [rbp+340h+Logfont.lfWeight], 2BCh
0x1400fb7b6  mov     qword ptr [rbp+340h+Logfont.lfItalic], 1000000h
0x1400fb7be  lea     edx, [r12+20h]; SizeInWords
0x1400fb7c3  lea     rcx, [rbp+340h+Logfont.lfFaceName]; Destination
0x1400fb7c7  call    cs:__imp_wcscpy_s
0x1400fb7cd  mov     byte ptr [rsp+440h+lParam], 1
0x1400fb7d2  mov     [rsp+440h+dwFlags], r12d; dwFlags
0x1400fb7d7  lea     r9, [rsp+440h+lParam]; lParam
0x1400fb7dc  lea     r8, ?GetCharSetForFont@Jot@@YAHPEAUtagENUMLOGFONTEXW@@PEAUtagNEWTEXTMETRICEXW@@K_J@Z; lpProc
0x1400fb7e3  lea     rdx, [rbp+340h+Logfont]; lpLogfont
0x1400fb7e7  mov     rcx, r14; hdc
0x1400fb7ea  call    cs:__imp_EnumFontFamiliesExW
0x1400fb7f0  mov     [rbp+340h+Logfont.lfPitchAndFamily], r12b
0x1400fb7f4  mov     al, byte ptr [rsp+440h+lParam]
0x1400fb7f8  mov     [rbp+340h+Logfont.lfCharSet], al
0x1400fb7fb  call    sub_14008C058
0x1400fb800  mov     edx, eax; color
0x1400fb802  mov     rcx, r14; hdc
0x1400fb805  call    cs:__imp_SetTextColor
0x1400fb80b  mov     [rsp+440h+color], eax
0x1400fb80f  mov     edx, ebx; color
0x1400fb811  mov     rcx, r14; hdc
0x1400fb814  call    cs:__imp_SetBkColor
0x1400fb81a  mov     [rsp+440h+var_3F8], eax
0x1400fb81e  lea     r12d, [rdi-4]
0x1400fb822  mov     eax, esi
0x1400fb824  cdq
0x1400fb825  mov     ecx, 2
0x1400fb82a  idiv    ecx
0x1400fb82c  mov     dword ptr [rsp+440h+lParam+4], eax
0x1400fb830  lea     ebx, [rax-2]
0x1400fb833  xor     edi, edi
0x1400fb835  xorps   xmm0, xmm0
0x1400fb838  mov     [rsp+440h+var_3D0], rdi
0x1400fb83d  lea     r8, [rbp+340h+Logfont]; struct tagLOGFONTW *
0x1400fb841  mov     rdx, r14; HDC
0x1400fb844  lea     rcx, [rsp+440h+var_3E8+8]; this
0x1400fb849  movdqu  xmmword ptr [rsp+440h+var_3E8+8], xmm0
0x1400fb84f  call    ?Create@CHFont@Ofc@@QEAAXPEAUHDC__@@AEBUtagLOGFONTW@@@Z; Ofc::CHFont::Create(HDC__ *,tagLOGFONTW const &)
0x1400fb854  test    r13, r13
0x1400fb857  jz      loc_1400FB99B
0x1400fb85d  lea     ecx, [rdi+3]
0x1400fb860  mov     [rbp+340h+var_3A0], ecx
0x1400fb863  mov     [rbp+340h+var_39C], ecx
0x1400fb866  mov     [rbp+340h+var_398], r12d
0x1400fb86a  mov     [rbp+340h+var_394], ebx
0x1400fb86d  mov     rdx, [r13+28h]
0x1400fb871  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400fb875  test    rdx, rdx
0x1400fb878  jz      short loc_1400FB889
0x1400fb87a  mov     r8, rsi
0x1400fb87d  inc     r8
0x1400fb880  cmp     [rdx+r8*2], di
0x1400fb885  jnz     short loc_1400FB87D
0x1400fb887  jmp     short loc_1400FB88C
0x1400fb889  mov     r8, rdi
0x1400fb88c  neg     r15d
0x1400fb88f  sbb     r15d, r15d
0x1400fb892  and     r15d, 20002h
0x1400fb899  add     r15d, 820h
0x1400fb8a0  mov     [rsp+440h+dwFlags], r15d
0x1400fb8a5  lea     r9, [rbp+340h+var_3A0]
0x1400fb8a9  mov     rcx, r14
0x1400fb8ac  call    cs:__imp_MsoDrawTextW
0x1400fb8b2  lea     rcx, [rsp+440h+var_3E8+8]; this
0x1400fb8b7  call    ??1CHFont@Ofc@@QEAA@XZ; Ofc::CHFont::~CHFont(void)
0x1400fb8bc  mov     [rbp+340h+Logfont.lfWeight], 190h
0x1400fb8c3  xorps   xmm0, xmm0
0x1400fb8c6  movdqu  xmmword ptr [rsp+440h+var_3E8+8], xmm0
0x1400fb8cc  mov     [rsp+440h+var_3D0], rdi
0x1400fb8d1  lea     r8, [rbp+340h+Logfont]; struct tagLOGFONTW *
0x1400fb8d5  mov     rdx, r14; HDC
0x1400fb8d8  lea     rcx, [rsp+440h+var_3E8+8]; this
0x1400fb8dd  call    ?Create@CHFont@Ofc@@QEAAXPEAUHDC__@@AEBUtagLOGFONTW@@@Z; Ofc::CHFont::Create(HDC__ *,tagLOGFONTW const &)
0x1400fb8e2  nop
0x1400fb8e3  call    cs:__imp_?MsoFCbvHighContrast@@YAHXZ; MsoFCbvHighContrast(void)
0x1400fb8e9  test    eax, eax
0x1400fb8eb  jnz     short loc_1400FB92E
0x1400fb8ed  call    cs:__imp_?CanvasShouldDisplayDarkMode@System@Jot@@YA_NXZ; Jot::System::CanvasShouldDisplayDarkMode(void)
0x1400fb8f3  test    al, al
0x1400fb8f5  jz      short loc_1400FB92E
0x1400fb8f7  call    cs:__imp_?UseColorMap@ColorMap@OneNote@@YAAEAUAColorMap@12@XZ; OneNote::ColorMap::UseColorMap(void)
0x1400fb8fd  mov     rdi, rax
0x1400fb900  mov     rcx, [rax]
0x1400fb903  mov     rbx, [rcx]
0x1400fb906  mov     ecx, 8; nIndex
0x1400fb90b  call    cs:__imp_GetSysColor
0x1400fb911  mov     edx, eax
0x1400fb913  mov     rcx, rdi
0x1400fb916  mov     rax, rbx
0x1400fb919  call    cs:__guard_dispatch_icall_fptr
0x1400fb91f  mov     edx, eax; color
0x1400fb921  mov     rcx, r14; hdc
0x1400fb924  call    cs:__imp_SetTextColor
0x1400fb92a  xor     edi, edi
0x1400fb92c  jmp     short loc_1400FB94B
0x1400fb92e  mov     ecx, 8; nIndex
0x1400fb933  call    cs:__imp_GetSysColor
0x1400fb939  mov     edx, eax; unsigned int
0x1400fb93b  call    ?LightenColor@COutlookMeetingGalleryUser@Jot@@AEAAKK@Z; Jot::COutlookMeetingGalleryUser::LightenColor(ulong)
0x1400fb940  mov     edx, eax; color
0x1400fb942  mov     rcx, r14; hdc
0x1400fb945  call    cs:__imp_SetTextColor
0x1400fb94b  mov     [rbp+340h+var_3A0], 0Fh
0x1400fb952  mov     eax, dword ptr [rsp+440h+lParam+4]
0x1400fb956  inc     eax
0x1400fb958  mov     [rbp+340h+var_39C], eax
0x1400fb95b  mov     [rbp+340h+var_398], r12d
0x1400fb95f  mov     eax, [rsp+440h+var_408]
0x1400fb963  add     eax, 0FFFFFFFDh
0x1400fb966  mov     [rbp+340h+var_394], eax
0x1400fb969  mov     rdx, [r13+8]
0x1400fb96d  test    rdx, rdx
0x1400fb970  jz      short loc_1400FB97D
0x1400fb972  inc     rsi
0x1400fb975  cmp     [rdx+rsi*2], di
0x1400fb979  jnz     short loc_1400FB972
0x1400fb97b  jmp     short loc_1400FB980
0x1400fb97d  mov     rsi, rdi
0x1400fb980  mov     [rsp+440h+dwFlags], r15d
0x1400fb985  lea     r9, [rbp+340h+var_3A0]
0x1400fb989  mov     r8d, esi
0x1400fb98c  mov     rcx, r14
0x1400fb98f  call    cs:__imp_MsoDrawTextW
0x1400fb995  nop
0x1400fb996  jmp     loc_1400FBA28
0x1400fb99b  mov     r8d, 0F7BBBB89h
0x1400fb9a1  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x1400fb9a8  mov     rdx, [rdx+1F0h]
0x1400fb9af  lea     rcx, [rbp+340h+var_330]
0x1400fb9b3  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@PEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(HINSTANCE__ *,uint)
0x1400fb9b8  mov     ecx, 3
0x1400fb9bd  mov     [rbp+340h+var_3A0], ecx
0x1400fb9c0  mov     [rbp+340h+var_39C], ecx
0x1400fb9c3  mov     [rbp+340h+var_398], r12d
0x1400fb9c7  mov     [rbp+340h+var_394], ebx
0x1400fb9ca  lea     rcx, [rbp+340h+var_330]
0x1400fb9ce  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x1400fb9d4  test    rax, rax
0x1400fb9d7  jz      short loc_1400FB9E8
0x1400fb9d9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400fb9dd  inc     rsi
0x1400fb9e0  cmp     [rax+rsi*2], di
0x1400fb9e4  jnz     short loc_1400FB9DD
0x1400fb9e6  jmp     short loc_1400FB9EB
0x1400fb9e8  mov     rsi, rdi
0x1400fb9eb  lea     rcx, [rbp+340h+var_330]
0x1400fb9ef  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x1400fb9f5  neg     r15d
0x1400fb9f8  sbb     ecx, ecx
0x1400fb9fa  and     ecx, 20002h
0x1400fba00  add     ecx, 820h
0x1400fba06  mov     [rsp+440h+dwFlags], ecx
0x1400fba0a  lea     r9, [rbp+340h+var_3A0]
0x1400fba0e  mov     r8d, esi
0x1400fba11  mov     rdx, rax
0x1400fba14  mov     rcx, r14
0x1400fba17  call    cs:__imp_MsoDrawTextW
0x1400fba1d  nop
0x1400fba1e  lea     rcx, [rbp+340h+var_330]
0x1400fba22  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x1400fba27  nop
0x1400fba28  lea     rcx, [rsp+440h+var_3E8+8]; this
0x1400fba2d  call    ??1CHFont@Ofc@@QEAA@XZ; Ofc::CHFont::~CHFont(void)
0x1400fba32  call    ?GetFrameColor@Jot@@YAKXZ; Jot::GetFrameColor(void)
0x1400fba37  movzx   ecx, ax
0x1400fba3a  movzx   edx, al
0x1400fba3d  mov     r8d, 0FFFFFF00h
0x1400fba43  or      edx, r8d
0x1400fba46  shl     edx, 10h
0x1400fba49  shr     eax, 10h
0x1400fba4c  movzx   eax, al
0x1400fba4f  or      edx, eax
0x1400fba51  and     ecx, r8d
0x1400fba54  or      edx, ecx
0x1400fba56  mov     [rsp+440h+var_408], edx
0x1400fba5a  movss   xmm2, cs:__real@3f800000; float
0x1400fba62  lea     rdx, [rsp+440h+var_408]; struct Gdiplus::Color *
0x1400fba67  lea     rcx, [rsp+440h+var_3C8]; this
0x1400fba6c  call    ??0Pen@Gdiplus@@QEAA@AEBVColor@1@M@Z; Gdiplus::Pen::Pen(Gdiplus::Color const &,float)
0x1400fba71  mov     eax, [rsp+440h+var_404]
0x1400fba75  mov     dword ptr [rsp+440h+var_418], eax
0x1400fba79  mov     eax, [rsp+440h+var_400]
0x1400fba7d  mov     [rsp+440h+dwFlags], eax
0x1400fba81  xor     r9d, r9d
0x1400fba84  xor     r8d, r8d
0x1400fba87  mov     rdx, [rsp+440h+var_3C8]
0x1400fba8c  mov     rcx, [rsp+440h+var_3F0]
0x1400fba91  call    cs:__imp_GdipDrawRectangleI
0x1400fba97  mov     edx, [rsp+440h+color]; color
0x1400fba9b  mov     rcx, r14; hdc
0x1400fba9e  call    cs:__imp_SetTextColor
0x1400fbaa4  mov     edx, [rsp+440h+var_3F8]; color
0x1400fbaa8  mov     rcx, r14; hdc
0x1400fbaab  call    cs:__imp_SetBkColor
0x1400fbab1  mov     rcx, [rsp+440h+var_3C8]
0x1400fbab6  call    cs:__imp_GdipDeletePen
0x1400fbabc  lea     rcx, [rbp+340h+var_1C0]
0x1400fbac3  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x1400fbac8  mov     rcx, [rbp+340h+var_3B0]
0x1400fbacc  call    cs:__imp_GdipDeleteBrush
0x1400fbad2  mov     rcx, [rsp+440h+var_3F0]
0x1400fbad7  call    cs:__imp_GdipDeleteGraphics
0x1400fbadd  mov     al, 1
0x1400fbadf  mov     rcx, [rbp+340h+var_50]
0x1400fbae6  xor     rcx, rsp; StackCookie
0x1400fbae9  call    __security_check_cookie
0x1400fbaee  lea     r11, [rsp+440h+var_30]
0x1400fbaf6  mov     rbx, [r11+40h]
0x1400fbafa  movaps  xmm6, xmmword ptr [r11-10h]
0x1400fbaff  mov     rsp, r11
0x1400fbb02  pop     r15
  ... truncated ...
```
