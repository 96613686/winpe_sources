# Outlook::GdipUtil::DrawHoverButton(HWND__ *,HDC__ *,DpiScaler const &,tagRECT,uint,int,ulong,ulong,ulong,HBITMAP__ *,Mso::UIColor::ITPalette<Mso::UIColor::Swatch> *)

- ea: `0x1409c12a8`
- end: `0x1409c1a97`
- name: `?DrawHoverButton@GdipUtil@Outlook@@YA_NPEAUHWND__@@PEAUHDC__@@AEBVDpiScaler@@UtagRECT@@IHKKKPEAUHBITMAP__@@PEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@Mso@@@Z`
- size: `2031`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, HDC hdc@<rdx>, unsigned int, int, unsigned int, int, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1409c0190`

## callees

- `0x1401723e8`
- `0x1401a9000`
- `0x140257140`
- `0x14031407c`
- `0x1405049f0`
- `0x1405e27b8`
- `0x1405e2c94`
- `0x1405e2d20`
- `0x14085ae34`
- `0x1409c12a8`
- `0x1409c20ac`
- `0x1409c229c`
- `0x140a687b4`
- `0x140ae77e4`
- `0x140c42fd8`
- `0x140c5092c`
- `0x140c5c1c0`
- `0x140cafc58`
- `0x140cbc440`
- `0x140d80eb0`
- `0x141196e08`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1409c17ef`
- `KERNEL32!LeaveCriticalSection` at `0x1409c17ef`
- `OLMAPI32!EtwTraceErrorTag` at `0x1409c18dc`
- `OLMAPI32!EtwTraceErrorTag` at `0x1409c18dc`
- `GDI32!SelectObject` at `0x1409c1984`
- `GDI32!SelectObject` at `0x1409c1a8b`
- `GDI32!SelectObject` at `0x1409c1984`
- `GDI32!SelectObject` at `0x1409c1a8b`
- `GDI32!BitBlt` at `0x1409c17a3`
- `GDI32!BitBlt` at `0x1409c17a3`
- `GDI32!SetTextColor` at `0x1409c1731`
- `GDI32!SetTextColor` at `0x1409c1812`
- `GDI32!SetTextColor` at `0x1409c1731`
- `GDI32!SetTextColor` at `0x1409c1812`
- `GDI32!SetBkMode` at `0x1409c130f`
- `GDI32!SetBkMode` at `0x1409c1820`
- `GDI32!SetBkMode` at `0x1409c130f`
- `GDI32!SetBkMode` at `0x1409c1820`
- `gdiplus!GdipSetSmoothingMode` at `0x1409c14e5`
- `gdiplus!GdipSetSmoothingMode` at `0x1409c14e5`
- `gdiplus!GdipDeleteGraphics` at `0x1409c1637`
- `gdiplus!GdipDeleteGraphics` at `0x1409c1637`
- `gdiplus!GdipDeleteBrush` at `0x1409c15c3`
- `gdiplus!GdipDeleteBrush` at `0x1409c1619`
- `gdiplus!GdipDeleteBrush` at `0x1409c15c3`
- `gdiplus!GdipDeleteBrush` at `0x1409c1619`
- `gdiplus!GdipCreateFromHDC` at `0x1409c1445`
- `gdiplus!GdipCreateFromHDC` at `0x1409c1445`
- `gdiplus!GdipCreateSolidFill` at `0x1409c1560`
- `gdiplus!GdipCreateSolidFill` at `0x1409c15f3`
- `gdiplus!GdipCreateSolidFill` at `0x1409c1560`
- `gdiplus!GdipCreateSolidFill` at `0x1409c15f3`
- `gdiplus!GdipSetPixelOffsetMode` at `0x1409c14f4`
- `gdiplus!GdipSetPixelOffsetMode` at `0x1409c14f4`
- `gdiplus!GdipFillPath` at `0x1409c1572`
- `gdiplus!GdipFillPath` at `0x1409c160f`
- `gdiplus!GdipFillPath` at `0x1409c1572`
- `gdiplus!GdipFillPath` at `0x1409c160f`
- `gdiplus!GdipCreatePath` at `0x1409c1461`
- `gdiplus!GdipCreatePath` at `0x1409c1508`
- `gdiplus!GdipCreatePath` at `0x1409c1461`
- `gdiplus!GdipCreatePath` at `0x1409c1508`
- `gdiplus!GdipDeletePath` at `0x1409c1623`
- `gdiplus!GdipDeletePath` at `0x1409c162d`
- `gdiplus!GdipDeletePath` at `0x1409c1623`
- `gdiplus!GdipDeletePath` at `0x1409c162d`
- `USER32!GetWindowLongPtrA` at `0x1409c1362`
- `USER32!GetWindowLongPtrA` at `0x1409c1362`
- `USER32!InflateRect` at `0x1409c16f7`
- `USER32!InflateRect` at `0x1409c16f7`
- `USER32!CopyRect` at `0x1409c13a4`
- `USER32!CopyRect` at `0x1409c13a4`
- `USER32!SendMessageA` at `0x1409c1976`
- `USER32!SendMessageA` at `0x1409c1976`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c166a`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c1a4b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c166a`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c1a4b`

## pseudocode

```c
bool __fastcall Outlook::GdipUtil::DrawHoverButton(
        HWND hWnd,
        HDC hdc,
        DpiScaler *a3,
        struct tagRECT *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        unsigned int a9,
        __int64 a10,
        __int64 a11)
{
  GfxBuffer *v13; // r14
  unsigned int v14; // esi
  unsigned int v15; // edi
  int v16; // ebx
  int IconColorFromState; // eax
  char v18; // di
  RECT v19; // xmm6
  unsigned int v20; // ebx
  int v21; // edi
  __int64 v22; // rdx
  const struct Outlook::GdipUtil::HoverButtonBools *v23; // r8
  __int64 BorderColorFromState; // rax
  int v25; // eax
  LPCRITICAL_SECTION v26; // r8
  int v27; // esi
  int v28; // ebx
  int v29; // eax
  const struct Outlook::GdipUtil::HoverButtonBools *v30; // rdx
  HGDIOBJ v31; // rsi
  char v32; // di
  COLORREF TextColorForState; // eax
  COLORREF v34; // ebx
  COLORREF v35; // r13d
  DpiScaler *v36; // rbx
  int v37; // edi
  HDC v38; // rbx
  unsigned int v39; // edx
  GfxBufferManager *v40; // rcx
  void *v42; // rax
  int *v43; // rax
  int ButtonColorFromState; // eax
  COLORREF v45; // [rsp+58h] [rbp-B0h]
  int v46; // [rsp+68h] [rbp-A0h]
  unsigned int v47; // [rsp+68h] [rbp-A0h]
  int v48; // [rsp+68h] [rbp-A0h]
  HDC hdca; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v50[6]; // [rsp+78h] [rbp-90h] BYREF
  char v51; // [rsp+7Eh] [rbp-8Ah]
  char v52; // [rsp+7Fh] [rbp-89h]
  char v53; // [rsp+80h] [rbp-88h]
  char v54; // [rsp+82h] [rbp-86h]
  char v55; // [rsp+83h] [rbp-85h]
  char v56; // [rsp+85h] [rbp-83h]
  char v57; // [rsp+88h] [rbp-80h]
  char v58; // [rsp+89h] [rbp-7Fh]
  char v59; // [rsp+8Eh] [rbp-7Ah]
  char v60; // [rsp+91h] [rbp-77h]
  char v61; // [rsp+92h] [rbp-76h]
  char v62; // [rsp+94h] [rbp-74h]
  char v63; // [rsp+95h] [rbp-73h]
  int v64; // [rsp+98h] [rbp-70h]
  __int64 v65; // [rsp+A0h] [rbp-68h]
  DpiScaler *v66; // [rsp+A8h] [rbp-60h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+B8h] [rbp-50h] BYREF
  int v68; // [rsp+C8h] [rbp-40h]
  RECT v69; // [rsp+D8h] [rbp-30h] BYREF
  RECT v70; // [rsp+E8h] [rbp-20h] BYREF
  int mode; // [rsp+F8h] [rbp-10h]
  __int64 v72; // [rsp+100h] [rbp-8h] BYREF
  struct _RTL_CRITICAL_SECTION *v73; // [rsp+108h] [rbp+0h] BYREF
  int v74; // [rsp+110h] [rbp+8h]
  HWND hWnda; // [rsp+118h] [rbp+10h]
  GfxBuffer *v76; // [rsp+120h] [rbp+18h] BYREF
  HDC v77; // [rsp+128h] [rbp+20h]
  HDC *p_hdca; // [rsp+130h] [rbp+28h]
  struct tagRECT y; // [rsp+138h] [rbp+30h]
  __int64 v80; // [rsp+150h] [rbp+48h]
  __int64 WindowLongPtrA; // [rsp+158h] [rbp+50h]
  struct tagRECT rcDst; // [rsp+168h] [rbp+60h] BYREF
  WCHAR String[256]; // [rsp+178h] [rbp+70h] BYREF

  v66 = a3;
  hWnda = hWnd;
  hdca = hdc;
  v80 = a10;
  v68 = 0;
  mode = SetBkMode(hdc, 2);
  v76 = 0;
  p_hdca = 0;
  v77 = hdca;
  y = *a4;
  GetGfxBuffer(hdca, a4, &v76);
  v13 = v76;
  if ( v76 )
  {
    hdca = (HDC)*((_QWORD *)v76 + 2);
    p_hdca = &hdca;
  }
  WindowLongPtrA = GetWindowLongPtrA(hWnd, -16);
  Outlook::GdipUtil::HoverButtonBools::HoverButtonBools(
    (Outlook::GdipUtil::HoverButtonBools *)v50,
    a5,
    a6,
    a7,
    a9,
    WindowLongPtrA);
  CopyRect(&rcDst, a4);
  String[0] = 0;
  if ( v50[3] )
  {
    v14 = 3;
  }
  else if ( v50[0] )
  {
    v14 = 4;
  }
  else if ( v50[1] )
  {
    v14 = 2;
  }
  else if ( v50[2] || (v14 = 1, v50[4]) )
  {
    v14 = 5;
  }
  v15 = 33;
  if ( v54 || v14 == 1 )
  {
    v16 = a8;
  }
  else
  {
    if ( a11 )
      ButtonColorFromState = Outlook::GdiUtil::GetButtonColorFromState(a5, a11);
    else
      ButtonColorFromState = MsoCrCbvGet((a5 & 0x51) != 0 ? 3217 : 33);
    v16 = ButtonColorFromState;
  }
  if ( a11 )
  {
    IconColorFromState = Outlook::GdiUtil::GetIconColorFromState(a5, a11);
  }
  else
  {
    if ( (a5 & 4) != 0 )
    {
      v15 = 37;
    }
    else if ( (a5 & 1) != 0 )
    {
      v15 = 2679;
    }
    else if ( (a5 & 0x40) != 0 || (a5 & 0x10) != 0 )
    {
      v15 = 2715;
    }
    IconColorFromState = MsoCrCbvGet(v15);
  }
  v64 = IconColorFromState;
  v18 = v62;
  if ( !v62 )
  {
    v16 = a8;
    goto LABEL_40;
  }
  if ( !v54 )
  {
LABEL_40:
    GdiplusFillRect(hdca, a4, v16 & 0xFF00 | BYTE2(v16) | ((v16 | 0xFFFFFF00) << 16));
    if ( !v54 && v18 )
      goto LABEL_42;
  }
  v72 = 0;
  GdipCreateFromHDC(hdca, &v72);
  v65 = v72;
  v73 = 0;
  v74 = GdipCreatePath(0, &v73);
  v46 = v18 == 0 ? 4 : 0;
  v19 = *a4;
  v69 = *a4;
  v20 = 0;
  if ( v61 )
    v20 = 9;
  if ( v60 )
    v20 |= 6u;
  if ( v63 )
  {
    if ( v58 )
      v20 &= 0xFFFFFFF3;
    else
      v20 &= 0xFFFFFFFC;
  }
  v21 = DpiScaler::Scale(v66, v54 != 0);
  v47 = DpiScaler::Scale(v66, v46);
  v70 = v19;
  GPCreateFluentFillPath_AccurateGeometry(&v73, &v70, v47, v20);
  GdipSetSmoothingMode(v65, 4);
  GdipSetPixelOffsetMode(v65, 4);
  lpCriticalSection[0] = 0;
  LODWORD(lpCriticalSection[1]) = GdipCreatePath(0, lpCriticalSection);
  if ( v54 )
  {
    if ( a11 )
    {
      LOBYTE(v22) = v52;
      BorderColorFromState = Outlook::GdiUtil::GetBorderColorFromState(v14, v22, a11);
    }
    else
    {
      LODWORD(BorderColorFromState) = Outlook::GdipUtil::GetBorderColorFromState(
                                        (Outlook::GdipUtil *)v14,
                                        (int)v50,
                                        v23);
    }
    *(_QWORD *)&v70.left = 0;
    GdipCreateSolidFill(
      BYTE2(BorderColorFromState)
    | (((unsigned __int8)BorderColorFromState | 0xFFFFFF00) << 16)
    | BorderColorFromState & 0xFF00,
      &v70);
    GdipFillPath(v65, *(_QWORD *)&v70.left, v73);
    LOBYTE(v25) = 15;
    if ( v51 )
      v25 = v59 != 0 ? 11 : 14;
    if ( (v25 & 1) != 0 )
      v69.left += v21;
    if ( (v25 & 4) != 0 )
      v69.right -= v21;
    v69.top += v21;
    v69.bottom -= v21;
    GPCreateFluentFillPath_AccurateGeometry(lpCriticalSection, &v69, v47 - v21, v20);
    GdipDeleteBrush(*(_QWORD *)&v70.left);
  }
  *(_QWORD *)&v70.left = 0;
  GdipCreateSolidFill(v64 & 0xFF00 | ((v64 | 0xFFFFFF00) << 16) | BYTE2(v64), &v70);
  v26 = v73;
  if ( v54 )
    v26 = lpCriticalSection[0];
  GdipFillPath(v65, *(_QWORD *)&v70.left, v26);
  GdipDeleteBrush(*(_QWORD *)&v70.left);
  GdipDeletePath(lpCriticalSection[0]);
  GdipDeletePath(v73);
  GdipDeleteGraphics(v65);
LABEL_42:
  if ( v57 || (v27 = 1, v51) )
    v27 = 2;
  v28 = -(v27 * DpiScaler::Scale(v66, 1));
  v29 = DpiScaler::Scale(v66, 1);
  InflateRect(a4, -(v27 * v29), v28);
  v31 = 0;
  v48 = 0;
  LODWORD(v65) = 0;
  v32 = v53;
  if ( v53 )
  {
    StringTemplate<wchar_t,FixedLengthBuffer<wchar_t,256>>::HrGetFromHwnd(String, hWnda);
    v42 = (void *)SendMessageA(hWnda, 0x31u, 0, 0);
    v31 = SelectObject(hdca, v42);
    *(struct tagRECT *)lpCriticalSection = *a4;
    v43 = (int *)Outlook::GdipUtil::MeasureTextHoverButton(&v72, hdca, v66, String, lpCriticalSection, v50);
    v48 = *v43;
    LODWORD(v65) = v43[1];
  }
  if ( a11 )
    TextColorForState = Outlook::GdiUtil::GetTextColorForState(a5, a11);
  else
    TextColorForState = Outlook::GdipUtil::GetTextColorForState((Outlook::GdipUtil *)v50, v30);
  v34 = TextColorForState;
  v35 = SetTextColor(hdca, TextColorForState);
  if ( v55 )
  {
    *(struct tagRECT *)lpCriticalSection = rcDst;
    v45 = v34;
    v36 = v66;
    if ( !(unsigned __int8)Outlook::GdipUtil::DrawIconHoverButton(
                             hdca,
                             v66,
                             a4,
                             a6,
                             v80,
                             lpCriticalSection,
                             v50,
                             v48,
                             v65,
                             v64,
                             v45,
                             a11 != 0) )
    {
      v37 = -2147467259;
      EtwTraceErrorTag(2147500037LL, 546046744);
      goto LABEL_54;
    }
    v32 = v53;
  }
  else
  {
    v36 = v66;
    if ( !v56 )
      a4->left += DpiScaler::Scale(v66, 4);
  }
  if ( v32 )
    Outlook::GdipUtil::DrawTextHoverButton(hWnda, hdca, v36, (__int64)v50, WindowLongPtrA, a4);
  v37 = v68;
LABEL_54:
  if ( v13 )
  {
    v38 = v77;
    BitBlt(v77, y.left, y.top, y.right - y.left, y.bottom - y.top, *((HDC *)v13 + 2), y.left, y.top, 0xCC0020u);
    AutoCriticalSection::AutoCriticalSection((AutoCriticalSection *)lpCriticalSection, &stru_1425F95A0);
    GfxBuffer::FreeGfxBuffer(v13, 0);
    if ( (*((_BYTE *)v13 + 52) & 1) != 0 )
    {
      *((_QWORD *)v13 + 7) = qword_1425F9570;
      qword_1425F9570 = v13;
      GfxBufferManager::CompactList(v40);
    }
    else
    {
      GfxBuffer::`scalar deleting destructor'(v13, v39);
    }
    if ( LOBYTE(lpCriticalSection[1]) )
      LeaveCriticalSection(lpCriticalSection[0]);
    if ( p_hdca )
      *p_hdca = v38;
  }
  if ( v31 )
    SelectObject(hdca, v31);
  SetTextColor(hdca, v35);
  SetBkMode(hdca, mode);
  return v37 >= 0;
}

```

## disassembly

```asm
0x1409c12a8  mov     rax, rsp
0x1409c12ab  push    rbp
0x1409c12ac  push    rbx
0x1409c12ad  push    rsi
0x1409c12ae  push    rdi
0x1409c12af  push    r12
0x1409c12b1  push    r13
0x1409c12b3  push    r14
0x1409c12b5  push    r15
0x1409c12b7  lea     rbp, [rax-2D8h]
0x1409c12be  sub     rsp, 398h
0x1409c12c5  movaps  xmmword ptr [rax-58h], xmm6
0x1409c12c9  mov     rax, cs:__security_cookie
0x1409c12d0  xor     rax, rsp
0x1409c12d3  mov     [rbp+2D0h+var_60], rax
0x1409c12da  mov     r12, r9
0x1409c12dd  mov     [rbp+2D0h+var_330], r8
0x1409c12e1  mov     rax, rdx
0x1409c12e4  mov     rdi, rcx
0x1409c12e7  mov     [rbp+2D0h+hWnd], rcx
0x1409c12eb  mov     [rsp+3D0h+hdc], rdx
0x1409c12f0  mov     rcx, [rbp+2D0h+arg_48]
0x1409c12f7  mov     [rbp+2D0h+var_288], rcx
0x1409c12fb  mov     r15, [rbp+2D0h+arg_50]
0x1409c1302  xor     esi, esi
0x1409c1304  mov     [rbp+2D0h+var_310], esi
0x1409c1307  lea     ebx, [rsi+2]
0x1409c130a  mov     edx, ebx; mode
0x1409c130c  mov     rcx, rax; hdc
0x1409c130f  call    cs:__imp_SetBkMode
0x1409c1315  mov     [rbp+2D0h+mode], eax
0x1409c1318  mov     [rbp+2D0h+var_2B8], rsi
0x1409c131c  mov     [rbp+2D0h+var_2A8], rsi
0x1409c1320  mov     rcx, [rsp+3D0h+hdc]; HDC
0x1409c1325  mov     [rbp+2D0h+var_2B0], rcx
0x1409c1329  movaps  xmm0, xmmword ptr [r12]
0x1409c132e  movdqu  xmmword ptr [rbp+2D0h+y.left], xmm0
0x1409c1333  lea     r8, [rbp+2D0h+var_2B8]; struct GfxBuffer **
0x1409c1337  mov     rdx, r12; struct tagRECT *
0x1409c133a  call    ?GetGfxBuffer@@YAJPEAUHDC__@@PEBUtagRECT@@PEAPEAVGfxBuffer@@@Z; GetGfxBuffer(HDC__ *,tagRECT const *,GfxBuffer * *)
0x1409c133f  mov     r14, [rbp+2D0h+var_2B8]
0x1409c1343  test    r14, r14
0x1409c1346  jz      short loc_1409C135A
0x1409c1348  mov     rax, [r14+10h]
0x1409c134c  mov     [rsp+3D0h+hdc], rax
0x1409c1351  lea     rax, [rsp+3D0h+hdc]
0x1409c1356  mov     [rbp+2D0h+var_2A8], rax
0x1409c135a  mov     edx, 0FFFFFFF0h; nIndex
0x1409c135f  mov     rcx, rdi; hWnd
0x1409c1362  call    cs:__imp_GetWindowLongPtrA
0x1409c1368  mov     [rbp+2D0h+var_280], rax
0x1409c136c  mov     [rsp+3D0h+hdcSrc], rax; __int64
0x1409c1371  mov     eax, [rbp+2D0h+arg_40]
0x1409c1377  mov     [rsp+3D0h+cy], eax; unsigned int
0x1409c137b  mov     r9d, [rbp+2D0h+arg_30]; unsigned int
0x1409c1382  mov     r8d, [rbp+2D0h+arg_28]; int
0x1409c1389  mov     r13d, [rbp+2D0h+arg_20]
0x1409c1390  mov     edx, r13d; unsigned int
0x1409c1393  lea     rcx, [rsp+3D0h+var_360]; this
0x1409c1398  call    ??0HoverButtonBools@GdipUtil@Outlook@@QEAA@IHKK_J@Z; Outlook::GdipUtil::HoverButtonBools::HoverButtonBools(uint,int,ulong,ulong,__int64)
0x1409c139d  mov     rdx, r12; lprcSrc
0x1409c13a0  lea     rcx, [rbp+2D0h+rcDst]; lprcDst
0x1409c13a4  call    cs:__imp_CopyRect
0x1409c13aa  mov     [rbp+2D0h+String], si
0x1409c13ae  cmp     byte ptr [rsp+3D0h+var_360+3], sil
0x1409c13b3  jnz     short loc_1409C13E5
0x1409c13b5  cmp     byte ptr [rsp+3D0h+var_360], sil
0x1409c13ba  jnz     loc_1409C1A15
0x1409c13c0  cmp     byte ptr [rsp+3D0h+var_360+1], sil
0x1409c13c5  jnz     loc_1409C194C
0x1409c13cb  cmp     byte ptr [rsp+3D0h+var_360+2], sil
0x1409c13d0  jnz     short loc_1409C13DE
0x1409c13d2  cmp     byte ptr [rsp+3D0h+var_360+4], sil
0x1409c13d7  mov     esi, 1
0x1409c13dc  jz      short loc_1409C13EA
0x1409c13de  mov     esi, 5
0x1409c13e3  jmp     short loc_1409C13EA
0x1409c13e5  mov     esi, 3
0x1409c13ea  mov     edi, 21h ; '!'
0x1409c13ef  cmp     [rsp+3D0h+var_356], 0
0x1409c13f4  jz      loc_1409C1A1F
0x1409c13fa  mov     ebx, [rbp+2D0h+arg_38]
0x1409c1400  mov     ecx, r13d
0x1409c1403  test    r15, r15
0x1409c1406  jz      loc_1409C163F
0x1409c140c  mov     rdx, r15
0x1409c140f  call    ?GetIconColorFromState@GdiUtil@Outlook@@YAKIAEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@Mso@@@Z; Outlook::GdiUtil::GetIconColorFromState(uint,Mso::UIColor::ITPalette<Mso::UIColor::Swatch> &)
0x1409c1414  mov     [rbp+2D0h+var_340], eax
0x1409c1417  mov     edx, 0FFFFFF00h
0x1409c141c  mov     dil, [rbp+2D0h+var_344]
0x1409c1420  test    dil, dil
0x1409c1423  jz      loc_1409C1675
0x1409c1429  cmp     [rsp+3D0h+var_356], 0
0x1409c142e  jz      loc_1409C167B
0x1409c1434  mov     [rbp+2D0h+var_2D8], 0
0x1409c143c  lea     rdx, [rbp+2D0h+var_2D8]
0x1409c1440  mov     rcx, [rsp+3D0h+hdc]
0x1409c1445  call    cs:__imp_GdipCreateFromHDC
0x1409c144b  mov     rax, [rbp+2D0h+var_2D8]
0x1409c144f  mov     [rbp+2D0h+var_338], rax
0x1409c1453  mov     [rbp+2D0h+var_2D0], 0
0x1409c145b  lea     rdx, [rbp+2D0h+var_2D0]
0x1409c145f  xor     ecx, ecx
0x1409c1461  call    cs:__imp_GdipCreatePath
0x1409c1467  mov     [rbp+2D0h+var_2C8], eax
0x1409c146a  xor     ecx, ecx
0x1409c146c  mov     edx, ecx
0x1409c146e  cmp     [rsp+3D0h+var_356], cl
0x1409c1472  setnz   dl; int
0x1409c1475  neg     dil
0x1409c1478  sbb     eax, eax
0x1409c147a  not     eax
0x1409c147c  and     eax, 4
0x1409c147f  mov     [rsp+3D0h+var_370], eax
0x1409c1483  movaps  xmm6, xmmword ptr [r12]
0x1409c1488  movaps  [rbp+2D0h+var_300], xmm6
0x1409c148c  mov     ebx, ecx
0x1409c148e  lea     eax, [rcx+9]
0x1409c1491  cmp     [rbp+2D0h+var_346], cl
0x1409c1494  cmovnz  ebx, eax
0x1409c1497  cmp     [rbp+2D0h+var_347], cl
0x1409c149a  jz      short loc_1409C149F
0x1409c149c  or      ebx, 6
0x1409c149f  cmp     [rbp+2D0h+var_343], cl
0x1409c14a2  jnz     loc_1409C1A58
0x1409c14a8  mov     rcx, [rbp+2D0h+var_330]; this
0x1409c14ac  call    ?Scale@DpiScaler@@QEBAHH@Z; DpiScaler::Scale(int)
0x1409c14b1  mov     edi, eax
0x1409c14b3  mov     edx, [rsp+3D0h+var_370]; int
0x1409c14b7  mov     rcx, [rbp+2D0h+var_330]; this
0x1409c14bb  call    ?Scale@DpiScaler@@QEBAHH@Z; DpiScaler::Scale(int)
0x1409c14c0  mov     [rsp+3D0h+var_370], eax
0x1409c14c4  movdqa  [rbp+2D0h+var_2F0], xmm6
0x1409c14c9  mov     r9d, ebx
0x1409c14cc  mov     r8d, eax
0x1409c14cf  lea     rdx, [rbp+2D0h+var_2F0]
0x1409c14d3  lea     rcx, [rbp+2D0h+var_2D0]
0x1409c14d7  call    ?GPCreateFluentFillPath_AccurateGeometry@@YA?AW4Status@Gdiplus@@PEAVGraphicsPath@2@UtagRECT@@KW4GDIPCorners@@@Z; GPCreateFluentFillPath_AccurateGeometry(Gdiplus::GraphicsPath *,tagRECT,ulong,GDIPCorners)
0x1409c14dc  mov     edx, 4
0x1409c14e1  mov     rcx, [rbp+2D0h+var_338]
0x1409c14e5  call    cs:__imp_GdipSetSmoothingMode
0x1409c14eb  mov     edx, 4
0x1409c14f0  mov     rcx, [rbp+2D0h+var_338]
0x1409c14f4  call    cs:__imp_GdipSetPixelOffsetMode
0x1409c14fa  mov     [rbp+2D0h+lpCriticalSection], 0
0x1409c1502  lea     rdx, [rbp+2D0h+lpCriticalSection]
0x1409c1506  xor     ecx, ecx
0x1409c1508  call    cs:__imp_GdipCreatePath
0x1409c150e  mov     dword ptr [rbp+2D0h+lpCriticalSection+8], eax
0x1409c1511  cmp     [rsp+3D0h+var_356], 0
0x1409c1516  jz      loc_1409C1942
0x1409c151c  mov     ecx, esi; this
0x1409c151e  test    r15, r15
0x1409c1521  jz      loc_1409C191D
0x1409c1527  mov     r8, r15
0x1409c152a  mov     dl, byte ptr [rsp+3D0h+var_360+7]
0x1409c152e  call    ?GetBorderColorFromState@GdiUtil@Outlook@@YAKH_NAEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@Mso@@@Z; Outlook::GdiUtil::GetBorderColorFromState(int,bool,Mso::UIColor::ITPalette<Mso::UIColor::Swatch> &)
0x1409c1533  movzx   ecx, ax
0x1409c1536  movzx   r8d, al
0x1409c153a  mov     esi, 0FFFFFF00h
0x1409c153f  or      r8d, esi
0x1409c1542  shl     r8d, 10h
0x1409c1546  shr     eax, 10h
0x1409c1549  movzx   eax, al
0x1409c154c  or      r8d, eax
0x1409c154f  and     ecx, esi
0x1409c1551  or      ecx, r8d
0x1409c1554  mov     qword ptr [rbp+2D0h+var_2F0], 0
0x1409c155c  lea     rdx, [rbp+2D0h+var_2F0]
0x1409c1560  call    cs:__imp_GdipCreateSolidFill
0x1409c1566  mov     r8, [rbp+2D0h+var_2D0]
0x1409c156a  mov     rdx, qword ptr [rbp+2D0h+var_2F0]
0x1409c156e  mov     rcx, [rbp+2D0h+var_338]
0x1409c1572  call    cs:__imp_GdipFillPath
0x1409c1578  mov     eax, 0Fh
0x1409c157d  cmp     byte ptr [rsp+3D0h+var_360+6], 0
0x1409c1582  jnz     loc_1409C1A03
0x1409c1588  test    al, 1
0x1409c158a  jnz     loc_1409C1915
0x1409c1590  test    al, 4
0x1409c1592  jnz     loc_1409C1953
0x1409c1598  add     dword ptr [rbp+2D0h+var_300+4], edi
0x1409c159b  sub     dword ptr [rbp+2D0h+var_300+0Ch], edi
0x1409c159e  movaps  xmm0, [rbp+2D0h+var_300]
0x1409c15a2  movdqa  [rbp+2D0h+var_300], xmm0
0x1409c15a7  mov     r8d, [rsp+3D0h+var_370]
0x1409c15ac  sub     r8d, edi
0x1409c15af  mov     r9d, ebx
0x1409c15b2  lea     rdx, [rbp+2D0h+var_300]
0x1409c15b6  lea     rcx, [rbp+2D0h+lpCriticalSection]
0x1409c15ba  call    ?GPCreateFluentFillPath_AccurateGeometry@@YA?AW4Status@Gdiplus@@PEAVGraphicsPath@2@UtagRECT@@KW4GDIPCorners@@@Z; GPCreateFluentFillPath_AccurateGeometry(Gdiplus::GraphicsPath *,tagRECT,ulong,GDIPCorners)
0x1409c15bf  mov     rcx, qword ptr [rbp+2D0h+var_2F0]
0x1409c15c3  call    cs:__imp_GdipDeleteBrush
0x1409c15c9  mov     eax, [rbp+2D0h+var_340]
0x1409c15cc  movzx   edx, ax
0x1409c15cf  movzx   r8d, al
0x1409c15d3  or      r8d, esi
0x1409c15d6  shl     r8d, 10h
0x1409c15da  shr     eax, 10h
0x1409c15dd  movzx   ecx, al
0x1409c15e0  or      ecx, r8d
0x1409c15e3  and     edx, esi
0x1409c15e5  or      ecx, edx
0x1409c15e7  mov     qword ptr [rbp+2D0h+var_2F0], 0
0x1409c15ef  lea     rdx, [rbp+2D0h+var_2F0]
0x1409c15f3  call    cs:__imp_GdipCreateSolidFill
0x1409c15f9  mov     r8, [rbp+2D0h+var_2D0]
0x1409c15fd  cmp     [rsp+3D0h+var_356], 0
0x1409c1602  cmovnz  r8, [rbp+2D0h+lpCriticalSection]
0x1409c1607  mov     rdx, qword ptr [rbp+2D0h+var_2F0]
0x1409c160b  mov     rcx, [rbp+2D0h+var_338]
0x1409c160f  call    cs:__imp_GdipFillPath
0x1409c1615  mov     rcx, qword ptr [rbp+2D0h+var_2F0]
0x1409c1619  call    cs:__imp_GdipDeleteBrush
0x1409c161f  mov     rcx, [rbp+2D0h+lpCriticalSection]
0x1409c1623  call    cs:__imp_GdipDeletePath
0x1409c1629  mov     rcx, [rbp+2D0h+var_2D0]
0x1409c162d  call    cs:__imp_GdipDeletePath
0x1409c1633  mov     rcx, [rbp+2D0h+var_338]
0x1409c1637  call    cs:__imp_GdipDeleteGraphics
0x1409c163d  jmp     short loc_1409C16B8
0x1409c163f  and     ecx, 40h
0x1409c1642  mov     edx, r13d
0x1409c1645  and     edx, 10h
0x1409c1648  mov     eax, r13d
0x1409c164b  and     eax, 1
0x1409c164e  test    r13b, 4
0x1409c1652  jnz     short loc_1409C1663
0x1409c1654  test    eax, eax
0x1409c1656  jz      loc_1409C192C
0x1409c165c  mov     edi, 0A77h
0x1409c1661  jmp     short loc_1409C1668
0x1409c1663  mov     edi, 25h ; '%'
0x1409c1668  mov     ecx, edi
0x1409c166a  call    cs:__imp_MsoCrCbvGet
0x1409c1670  jmp     loc_1409C1414
0x1409c1675  mov     ebx, [rbp+2D0h+arg_38]
0x1409c167b  movzx   ecx, bx
0x1409c167e  movzx   r8d, bl
0x1409c1682  or      r8d, edx
0x1409c1685  shl     r8d, 10h
0x1409c1689  shr     ebx, 10h
0x1409c168c  movzx   eax, bl
0x1409c168f  or      r8d, eax
0x1409c1692  and     ecx, edx
0x1409c1694  or      r8d, ecx
0x1409c1697  mov     rdx, r12
0x1409c169a  mov     rcx, [rsp+3D0h+hdc]
0x1409c169f  call    ?GdiplusFillRect@@YAXPEAUHDC__@@PEAUtagRECT@@VColor@Gdiplus@@@Z; GdiplusFillRect(HDC__ *,tagRECT *,Gdiplus::Color)
0x1409c16a4  cmp     [rsp+3D0h+var_356], 0
0x1409c16a9  jnz     loc_1409C1434
0x1409c16af  test    dil, dil
0x1409c16b2  jz      loc_1409C1434
0x1409c16b8  cmp     [rbp+2D0h+var_350], 0
0x1409c16bc  jz      loc_1409C1900
0x1409c16c2  mov     esi, 2
0x1409c16c7  mov     edx, 1; int
0x1409c16cc  mov     rcx, [rbp+2D0h+var_330]; this
0x1409c16d0  call    ?Scale@DpiScaler@@QEBAHH@Z; DpiScaler::Scale(int)
0x1409c16d5  mov     ebx, eax
0x1409c16d7  imul    ebx, esi
0x1409c16da  neg     ebx
0x1409c16dc  mov     edx, 1; int
0x1409c16e1  mov     rcx, [rbp+2D0h+var_330]; this
0x1409c16e5  call    ?Scale@DpiScaler@@QEBAHH@Z; DpiScaler::Scale(int)
0x1409c16ea  imul    eax, esi
0x1409c16ed  neg     eax
0x1409c16ef  mov     r8d, ebx; dy
0x1409c16f2  mov     edx, eax; dx
0x1409c16f4  mov     rcx, r12; lprc
0x1409c16f7  call    cs:__imp_InflateRect
0x1409c16fd  xor     esi, esi
0x1409c16ff  mov     [rsp+3D0h+var_370], esi
0x1409c1703  mov     dword ptr [rbp+2D0h+var_338], esi
0x1409c1706  mov     dil, [rsp+3D0h+var_358]
0x1409c170b  test    dil, dil
0x1409c170e  jnz     loc_1409C195B
0x1409c1714  test    r15, r15
0x1409c1717  jz      loc_1409C18E7
0x1409c171d  mov     rdx, r15
0x1409c1720  mov     ecx, r13d
0x1409c1723  call    ?GetTextColorForState@GdiUtil@Outlook@@YAKIAEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@Mso@@@Z; Outlook::GdiUtil::GetTextColorForState(uint,Mso::UIColor::ITPalette<Mso::UIColor::Swatch> &)
0x1409c1728  mov     ebx, eax
0x1409c172a  mov     edx, eax; color
0x1409c172c  mov     rcx, [rsp+3D0h+hdc]; hdc
0x1409c1731  call    cs:__imp_SetTextColor
0x1409c1737  mov     r13d, eax
0x1409c173a  cmp     [rsp+3D0h+var_355], 0
0x1409c173f  jnz     loc_1409C1865
0x1409c1745  mov     rbx, [rbp+2D0h+var_330]
0x1409c1749  cmp     [rsp+3D0h+var_353], 0
0x1409c174e  jz      loc_1409C1A6D
0x1409c1754  test    dil, dil
0x1409c1757  jnz     loc_1409C19D1
0x1409c175d  mov     edi, [rbp+2D0h+var_310]
0x1409c1760  test    r14, r14
0x1409c1763  jz      loc_1409C1801
0x1409c1769  mov     r9d, [rbp+2D0h+y.right]
0x1409c176d  mov     rdx, qword ptr [rbp+2D0h+y.left]; x
0x1409c1771  sub     r9d, edx; cx
  ... truncated ...
```
