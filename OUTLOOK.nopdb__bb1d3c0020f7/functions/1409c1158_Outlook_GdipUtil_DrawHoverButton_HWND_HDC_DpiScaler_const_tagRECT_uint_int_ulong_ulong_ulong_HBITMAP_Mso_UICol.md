# Outlook::GdipUtil::DrawHoverButton(HWND__ *,HDC__ *,DpiScaler const &,tagRECT,uint,int,ulong,ulong,ulong,HBITMAP__ *,Mso::UIColor::ITPalette<Mso::UIColor::Swatch> *)

- ea: `0x1409c1158`
- end: `0x1409c1947`
- name: `?DrawHoverButton@GdipUtil@Outlook@@YA_NPEAUHWND__@@PEAUHDC__@@AEBVDpiScaler@@UtagRECT@@IHKKKPEAUHBITMAP__@@PEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@Mso@@@Z`
- size: `2031`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, HDC hdc@<rdx>, unsigned int, int, unsigned int, int, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1409c0040`

## callees

- `0x1401723a8`
- `0x1401a8fe0`
- `0x140256930`
- `0x1403137dc`
- `0x140503f00`
- `0x1405e5950`
- `0x1405e6d50`
- `0x1405e6dd0`
- `0x14085ae44`
- `0x1409c1158`
- `0x1409c1f5c`
- `0x1409c214c`
- `0x140a68684`
- `0x140ae76c4`
- `0x140c42f28`
- `0x140c5087c`
- `0x140c5c110`
- `0x140cafba8`
- `0x140cbc390`
- `0x140d80e00`
- `0x141196d48`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1409c169f`
- `KERNEL32!LeaveCriticalSection` at `0x1409c169f`
- `OLMAPI32!EtwTraceErrorTag` at `0x1409c178c`
- `OLMAPI32!EtwTraceErrorTag` at `0x1409c178c`
- `GDI32!SelectObject` at `0x1409c1834`
- `GDI32!SelectObject` at `0x1409c193b`
- `GDI32!SelectObject` at `0x1409c1834`
- `GDI32!SelectObject` at `0x1409c193b`
- `GDI32!BitBlt` at `0x1409c1653`
- `GDI32!BitBlt` at `0x1409c1653`
- `GDI32!SetTextColor` at `0x1409c15e1`
- `GDI32!SetTextColor` at `0x1409c16c2`
- `GDI32!SetTextColor` at `0x1409c15e1`
- `GDI32!SetTextColor` at `0x1409c16c2`
- `GDI32!SetBkMode` at `0x1409c11bf`
- `GDI32!SetBkMode` at `0x1409c16d0`
- `GDI32!SetBkMode` at `0x1409c11bf`
- `GDI32!SetBkMode` at `0x1409c16d0`
- `gdiplus!GdipSetSmoothingMode` at `0x1409c1395`
- `gdiplus!GdipSetSmoothingMode` at `0x1409c1395`
- `gdiplus!GdipDeleteGraphics` at `0x1409c14e7`
- `gdiplus!GdipDeleteGraphics` at `0x1409c14e7`
- `gdiplus!GdipDeleteBrush` at `0x1409c1473`
- `gdiplus!GdipDeleteBrush` at `0x1409c14c9`
- `gdiplus!GdipDeleteBrush` at `0x1409c1473`
- `gdiplus!GdipDeleteBrush` at `0x1409c14c9`
- `gdiplus!GdipCreateFromHDC` at `0x1409c12f5`
- `gdiplus!GdipCreateFromHDC` at `0x1409c12f5`
- `gdiplus!GdipCreateSolidFill` at `0x1409c1410`
- `gdiplus!GdipCreateSolidFill` at `0x1409c14a3`
- `gdiplus!GdipCreateSolidFill` at `0x1409c1410`
- `gdiplus!GdipCreateSolidFill` at `0x1409c14a3`
- `gdiplus!GdipSetPixelOffsetMode` at `0x1409c13a4`
- `gdiplus!GdipSetPixelOffsetMode` at `0x1409c13a4`
- `gdiplus!GdipFillPath` at `0x1409c1422`
- `gdiplus!GdipFillPath` at `0x1409c14bf`
- `gdiplus!GdipFillPath` at `0x1409c1422`
- `gdiplus!GdipFillPath` at `0x1409c14bf`
- `gdiplus!GdipCreatePath` at `0x1409c1311`
- `gdiplus!GdipCreatePath` at `0x1409c13b8`
- `gdiplus!GdipCreatePath` at `0x1409c1311`
- `gdiplus!GdipCreatePath` at `0x1409c13b8`
- `gdiplus!GdipDeletePath` at `0x1409c14d3`
- `gdiplus!GdipDeletePath` at `0x1409c14dd`
- `gdiplus!GdipDeletePath` at `0x1409c14d3`
- `gdiplus!GdipDeletePath` at `0x1409c14dd`
- `USER32!GetWindowLongPtrA` at `0x1409c1212`
- `USER32!GetWindowLongPtrA` at `0x1409c1212`
- `USER32!InflateRect` at `0x1409c15a7`
- `USER32!InflateRect` at `0x1409c15a7`
- `USER32!CopyRect` at `0x1409c1254`
- `USER32!CopyRect` at `0x1409c1254`
- `USER32!SendMessageA` at `0x1409c1826`
- `USER32!SendMessageA` at `0x1409c1826`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c151a`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c18fb`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c151a`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1409c18fb`

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
0x1409c1158  mov     rax, rsp
0x1409c115b  push    rbp
0x1409c115c  push    rbx
0x1409c115d  push    rsi
0x1409c115e  push    rdi
0x1409c115f  push    r12
0x1409c1161  push    r13
0x1409c1163  push    r14
0x1409c1165  push    r15
0x1409c1167  lea     rbp, [rax-2D8h]
0x1409c116e  sub     rsp, 398h
0x1409c1175  movaps  xmmword ptr [rax-58h], xmm6
0x1409c1179  mov     rax, cs:__security_cookie
0x1409c1180  xor     rax, rsp
0x1409c1183  mov     [rbp+2D0h+var_60], rax
0x1409c118a  mov     r12, r9
0x1409c118d  mov     [rbp+2D0h+var_330], r8
0x1409c1191  mov     rax, rdx
0x1409c1194  mov     rdi, rcx
0x1409c1197  mov     [rbp+2D0h+hWnd], rcx
0x1409c119b  mov     [rsp+3D0h+hdc], rdx
0x1409c11a0  mov     rcx, [rbp+2D0h+arg_48]
0x1409c11a7  mov     [rbp+2D0h+var_288], rcx
0x1409c11ab  mov     r15, [rbp+2D0h+arg_50]
0x1409c11b2  xor     esi, esi
0x1409c11b4  mov     [rbp+2D0h+var_310], esi
0x1409c11b7  lea     ebx, [rsi+2]
0x1409c11ba  mov     edx, ebx; mode
0x1409c11bc  mov     rcx, rax; hdc
0x1409c11bf  call    cs:__imp_SetBkMode
0x1409c11c5  mov     [rbp+2D0h+mode], eax
0x1409c11c8  mov     [rbp+2D0h+var_2B8], rsi
0x1409c11cc  mov     [rbp+2D0h+var_2A8], rsi
0x1409c11d0  mov     rcx, [rsp+3D0h+hdc]; HDC
0x1409c11d5  mov     [rbp+2D0h+var_2B0], rcx
0x1409c11d9  movaps  xmm0, xmmword ptr [r12]
0x1409c11de  movdqu  xmmword ptr [rbp+2D0h+y.left], xmm0
0x1409c11e3  lea     r8, [rbp+2D0h+var_2B8]; struct GfxBuffer **
0x1409c11e7  mov     rdx, r12; struct tagRECT *
0x1409c11ea  call    ?GetGfxBuffer@@YAJPEAUHDC__@@PEBUtagRECT@@PEAPEAVGfxBuffer@@@Z; GetGfxBuffer(HDC__ *,tagRECT const *,GfxBuffer * *)
0x1409c11ef  mov     r14, [rbp+2D0h+var_2B8]
0x1409c11f3  test    r14, r14
0x1409c11f6  jz      short loc_1409C120A
0x1409c11f8  mov     rax, [r14+10h]
0x1409c11fc  mov     [rsp+3D0h+hdc], rax
0x1409c1201  lea     rax, [rsp+3D0h+hdc]
0x1409c1206  mov     [rbp+2D0h+var_2A8], rax
0x1409c120a  mov     edx, 0FFFFFFF0h; nIndex
0x1409c120f  mov     rcx, rdi; hWnd
0x1409c1212  call    cs:__imp_GetWindowLongPtrA
0x1409c1218  mov     [rbp+2D0h+var_280], rax
0x1409c121c  mov     [rsp+3D0h+hdcSrc], rax; __int64
0x1409c1221  mov     eax, [rbp+2D0h+arg_40]
0x1409c1227  mov     [rsp+3D0h+cy], eax; unsigned int
0x1409c122b  mov     r9d, [rbp+2D0h+arg_30]; unsigned int
0x1409c1232  mov     r8d, [rbp+2D0h+arg_28]; int
0x1409c1239  mov     r13d, [rbp+2D0h+arg_20]
0x1409c1240  mov     edx, r13d; unsigned int
0x1409c1243  lea     rcx, [rsp+3D0h+var_360]; this
0x1409c1248  call    ??0HoverButtonBools@GdipUtil@Outlook@@QEAA@IHKK_J@Z; Outlook::GdipUtil::HoverButtonBools::HoverButtonBools(uint,int,ulong,ulong,__int64)
0x1409c124d  mov     rdx, r12; lprcSrc
0x1409c1250  lea     rcx, [rbp+2D0h+rcDst]; lprcDst
0x1409c1254  call    cs:__imp_CopyRect
0x1409c125a  mov     [rbp+2D0h+String], si
0x1409c125e  cmp     byte ptr [rsp+3D0h+var_360+3], sil
0x1409c1263  jnz     short loc_1409C1295
0x1409c1265  cmp     byte ptr [rsp+3D0h+var_360], sil
0x1409c126a  jnz     loc_1409C18C5
0x1409c1270  cmp     byte ptr [rsp+3D0h+var_360+1], sil
0x1409c1275  jnz     loc_1409C17FC
0x1409c127b  cmp     byte ptr [rsp+3D0h+var_360+2], sil
0x1409c1280  jnz     short loc_1409C128E
0x1409c1282  cmp     byte ptr [rsp+3D0h+var_360+4], sil
0x1409c1287  mov     esi, 1
0x1409c128c  jz      short loc_1409C129A
0x1409c128e  mov     esi, 5
0x1409c1293  jmp     short loc_1409C129A
0x1409c1295  mov     esi, 3
0x1409c129a  mov     edi, 21h ; '!'
0x1409c129f  cmp     [rsp+3D0h+var_356], 0
0x1409c12a4  jz      loc_1409C18CF
0x1409c12aa  mov     ebx, [rbp+2D0h+arg_38]
0x1409c12b0  mov     ecx, r13d
0x1409c12b3  test    r15, r15
0x1409c12b6  jz      loc_1409C14EF
0x1409c12bc  mov     rdx, r15
0x1409c12bf  call    ?GetIconColorFromState@GdiUtil@Outlook@@YAKIAEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@Mso@@@Z; Outlook::GdiUtil::GetIconColorFromState(uint,Mso::UIColor::ITPalette<Mso::UIColor::Swatch> &)
0x1409c12c4  mov     [rbp+2D0h+var_340], eax
0x1409c12c7  mov     edx, 0FFFFFF00h
0x1409c12cc  mov     dil, [rbp+2D0h+var_344]
0x1409c12d0  test    dil, dil
0x1409c12d3  jz      loc_1409C1525
0x1409c12d9  cmp     [rsp+3D0h+var_356], 0
0x1409c12de  jz      loc_1409C152B
0x1409c12e4  mov     [rbp+2D0h+var_2D8], 0
0x1409c12ec  lea     rdx, [rbp+2D0h+var_2D8]
0x1409c12f0  mov     rcx, [rsp+3D0h+hdc]
0x1409c12f5  call    cs:__imp_GdipCreateFromHDC
0x1409c12fb  mov     rax, [rbp+2D0h+var_2D8]
0x1409c12ff  mov     [rbp+2D0h+var_338], rax
0x1409c1303  mov     [rbp+2D0h+var_2D0], 0
0x1409c130b  lea     rdx, [rbp+2D0h+var_2D0]
0x1409c130f  xor     ecx, ecx
0x1409c1311  call    cs:__imp_GdipCreatePath
0x1409c1317  mov     [rbp+2D0h+var_2C8], eax
0x1409c131a  xor     ecx, ecx
0x1409c131c  mov     edx, ecx
0x1409c131e  cmp     [rsp+3D0h+var_356], cl
0x1409c1322  setnz   dl; int
0x1409c1325  neg     dil
0x1409c1328  sbb     eax, eax
0x1409c132a  not     eax
0x1409c132c  and     eax, 4
0x1409c132f  mov     [rsp+3D0h+var_370], eax
0x1409c1333  movaps  xmm6, xmmword ptr [r12]
0x1409c1338  movaps  [rbp+2D0h+var_300], xmm6
0x1409c133c  mov     ebx, ecx
0x1409c133e  lea     eax, [rcx+9]
0x1409c1341  cmp     [rbp+2D0h+var_346], cl
0x1409c1344  cmovnz  ebx, eax
0x1409c1347  cmp     [rbp+2D0h+var_347], cl
0x1409c134a  jz      short loc_1409C134F
0x1409c134c  or      ebx, 6
0x1409c134f  cmp     [rbp+2D0h+var_343], cl
0x1409c1352  jnz     loc_1409C1908
0x1409c1358  mov     rcx, [rbp+2D0h+var_330]; this
0x1409c135c  call    ?Scale@DpiScaler@@QEBAHH@Z; DpiScaler::Scale(int)
0x1409c1361  mov     edi, eax
0x1409c1363  mov     edx, [rsp+3D0h+var_370]; int
0x1409c1367  mov     rcx, [rbp+2D0h+var_330]; this
0x1409c136b  call    ?Scale@DpiScaler@@QEBAHH@Z; DpiScaler::Scale(int)
0x1409c1370  mov     [rsp+3D0h+var_370], eax
0x1409c1374  movdqa  [rbp+2D0h+var_2F0], xmm6
0x1409c1379  mov     r9d, ebx
0x1409c137c  mov     r8d, eax
0x1409c137f  lea     rdx, [rbp+2D0h+var_2F0]
0x1409c1383  lea     rcx, [rbp+2D0h+var_2D0]
0x1409c1387  call    ?GPCreateFluentFillPath_AccurateGeometry@@YA?AW4Status@Gdiplus@@PEAVGraphicsPath@2@UtagRECT@@KW4GDIPCorners@@@Z; GPCreateFluentFillPath_AccurateGeometry(Gdiplus::GraphicsPath *,tagRECT,ulong,GDIPCorners)
0x1409c138c  mov     edx, 4
0x1409c1391  mov     rcx, [rbp+2D0h+var_338]
0x1409c1395  call    cs:__imp_GdipSetSmoothingMode
0x1409c139b  mov     edx, 4
0x1409c13a0  mov     rcx, [rbp+2D0h+var_338]
0x1409c13a4  call    cs:__imp_GdipSetPixelOffsetMode
0x1409c13aa  mov     [rbp+2D0h+lpCriticalSection], 0
0x1409c13b2  lea     rdx, [rbp+2D0h+lpCriticalSection]
0x1409c13b6  xor     ecx, ecx
0x1409c13b8  call    cs:__imp_GdipCreatePath
0x1409c13be  mov     dword ptr [rbp+2D0h+lpCriticalSection+8], eax
0x1409c13c1  cmp     [rsp+3D0h+var_356], 0
0x1409c13c6  jz      loc_1409C17F2
0x1409c13cc  mov     ecx, esi; this
0x1409c13ce  test    r15, r15
0x1409c13d1  jz      loc_1409C17CD
0x1409c13d7  mov     r8, r15
0x1409c13da  mov     dl, byte ptr [rsp+3D0h+var_360+7]
0x1409c13de  call    ?GetBorderColorFromState@GdiUtil@Outlook@@YAKH_NAEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@Mso@@@Z; Outlook::GdiUtil::GetBorderColorFromState(int,bool,Mso::UIColor::ITPalette<Mso::UIColor::Swatch> &)
0x1409c13e3  movzx   ecx, ax
0x1409c13e6  movzx   r8d, al
0x1409c13ea  mov     esi, 0FFFFFF00h
0x1409c13ef  or      r8d, esi
0x1409c13f2  shl     r8d, 10h
0x1409c13f6  shr     eax, 10h
0x1409c13f9  movzx   eax, al
0x1409c13fc  or      r8d, eax
0x1409c13ff  and     ecx, esi
0x1409c1401  or      ecx, r8d
0x1409c1404  mov     qword ptr [rbp+2D0h+var_2F0], 0
0x1409c140c  lea     rdx, [rbp+2D0h+var_2F0]
0x1409c1410  call    cs:__imp_GdipCreateSolidFill
0x1409c1416  mov     r8, [rbp+2D0h+var_2D0]
0x1409c141a  mov     rdx, qword ptr [rbp+2D0h+var_2F0]
0x1409c141e  mov     rcx, [rbp+2D0h+var_338]
0x1409c1422  call    cs:__imp_GdipFillPath
0x1409c1428  mov     eax, 0Fh
0x1409c142d  cmp     byte ptr [rsp+3D0h+var_360+6], 0
0x1409c1432  jnz     loc_1409C18B3
0x1409c1438  test    al, 1
0x1409c143a  jnz     loc_1409C17C5
0x1409c1440  test    al, 4
0x1409c1442  jnz     loc_1409C1803
0x1409c1448  add     dword ptr [rbp+2D0h+var_300+4], edi
0x1409c144b  sub     dword ptr [rbp+2D0h+var_300+0Ch], edi
0x1409c144e  movaps  xmm0, [rbp+2D0h+var_300]
0x1409c1452  movdqa  [rbp+2D0h+var_300], xmm0
0x1409c1457  mov     r8d, [rsp+3D0h+var_370]
0x1409c145c  sub     r8d, edi
0x1409c145f  mov     r9d, ebx
0x1409c1462  lea     rdx, [rbp+2D0h+var_300]
0x1409c1466  lea     rcx, [rbp+2D0h+lpCriticalSection]
0x1409c146a  call    ?GPCreateFluentFillPath_AccurateGeometry@@YA?AW4Status@Gdiplus@@PEAVGraphicsPath@2@UtagRECT@@KW4GDIPCorners@@@Z; GPCreateFluentFillPath_AccurateGeometry(Gdiplus::GraphicsPath *,tagRECT,ulong,GDIPCorners)
0x1409c146f  mov     rcx, qword ptr [rbp+2D0h+var_2F0]
0x1409c1473  call    cs:__imp_GdipDeleteBrush
0x1409c1479  mov     eax, [rbp+2D0h+var_340]
0x1409c147c  movzx   edx, ax
0x1409c147f  movzx   r8d, al
0x1409c1483  or      r8d, esi
0x1409c1486  shl     r8d, 10h
0x1409c148a  shr     eax, 10h
0x1409c148d  movzx   ecx, al
0x1409c1490  or      ecx, r8d
0x1409c1493  and     edx, esi
0x1409c1495  or      ecx, edx
0x1409c1497  mov     qword ptr [rbp+2D0h+var_2F0], 0
0x1409c149f  lea     rdx, [rbp+2D0h+var_2F0]
0x1409c14a3  call    cs:__imp_GdipCreateSolidFill
0x1409c14a9  mov     r8, [rbp+2D0h+var_2D0]
0x1409c14ad  cmp     [rsp+3D0h+var_356], 0
0x1409c14b2  cmovnz  r8, [rbp+2D0h+lpCriticalSection]
0x1409c14b7  mov     rdx, qword ptr [rbp+2D0h+var_2F0]
0x1409c14bb  mov     rcx, [rbp+2D0h+var_338]
0x1409c14bf  call    cs:__imp_GdipFillPath
0x1409c14c5  mov     rcx, qword ptr [rbp+2D0h+var_2F0]
0x1409c14c9  call    cs:__imp_GdipDeleteBrush
0x1409c14cf  mov     rcx, [rbp+2D0h+lpCriticalSection]
0x1409c14d3  call    cs:__imp_GdipDeletePath
0x1409c14d9  mov     rcx, [rbp+2D0h+var_2D0]
0x1409c14dd  call    cs:__imp_GdipDeletePath
0x1409c14e3  mov     rcx, [rbp+2D0h+var_338]
0x1409c14e7  call    cs:__imp_GdipDeleteGraphics
0x1409c14ed  jmp     short loc_1409C1568
0x1409c14ef  and     ecx, 40h
0x1409c14f2  mov     edx, r13d
0x1409c14f5  and     edx, 10h
0x1409c14f8  mov     eax, r13d
0x1409c14fb  and     eax, 1
0x1409c14fe  test    r13b, 4
0x1409c1502  jnz     short loc_1409C1513
0x1409c1504  test    eax, eax
0x1409c1506  jz      loc_1409C17DC
0x1409c150c  mov     edi, 0A77h
0x1409c1511  jmp     short loc_1409C1518
0x1409c1513  mov     edi, 25h ; '%'
0x1409c1518  mov     ecx, edi
0x1409c151a  call    cs:__imp_MsoCrCbvGet
0x1409c1520  jmp     loc_1409C12C4
0x1409c1525  mov     ebx, [rbp+2D0h+arg_38]
0x1409c152b  movzx   ecx, bx
0x1409c152e  movzx   r8d, bl
0x1409c1532  or      r8d, edx
0x1409c1535  shl     r8d, 10h
0x1409c1539  shr     ebx, 10h
0x1409c153c  movzx   eax, bl
0x1409c153f  or      r8d, eax
0x1409c1542  and     ecx, edx
0x1409c1544  or      r8d, ecx
0x1409c1547  mov     rdx, r12
0x1409c154a  mov     rcx, [rsp+3D0h+hdc]
0x1409c154f  call    ?GdiplusFillRect@@YAXPEAUHDC__@@PEAUtagRECT@@VColor@Gdiplus@@@Z; GdiplusFillRect(HDC__ *,tagRECT *,Gdiplus::Color)
0x1409c1554  cmp     [rsp+3D0h+var_356], 0
0x1409c1559  jnz     loc_1409C12E4
0x1409c155f  test    dil, dil
0x1409c1562  jz      loc_1409C12E4
0x1409c1568  cmp     [rbp+2D0h+var_350], 0
0x1409c156c  jz      loc_1409C17B0
0x1409c1572  mov     esi, 2
0x1409c1577  mov     edx, 1; int
0x1409c157c  mov     rcx, [rbp+2D0h+var_330]; this
0x1409c1580  call    ?Scale@DpiScaler@@QEBAHH@Z; DpiScaler::Scale(int)
0x1409c1585  mov     ebx, eax
0x1409c1587  imul    ebx, esi
0x1409c158a  neg     ebx
0x1409c158c  mov     edx, 1; int
0x1409c1591  mov     rcx, [rbp+2D0h+var_330]; this
0x1409c1595  call    ?Scale@DpiScaler@@QEBAHH@Z; DpiScaler::Scale(int)
0x1409c159a  imul    eax, esi
0x1409c159d  neg     eax
0x1409c159f  mov     r8d, ebx; dy
0x1409c15a2  mov     edx, eax; dx
0x1409c15a4  mov     rcx, r12; lprc
0x1409c15a7  call    cs:__imp_InflateRect
0x1409c15ad  xor     esi, esi
0x1409c15af  mov     [rsp+3D0h+var_370], esi
0x1409c15b3  mov     dword ptr [rbp+2D0h+var_338], esi
0x1409c15b6  mov     dil, [rsp+3D0h+var_358]
0x1409c15bb  test    dil, dil
0x1409c15be  jnz     loc_1409C180B
0x1409c15c4  test    r15, r15
0x1409c15c7  jz      loc_1409C1797
0x1409c15cd  mov     rdx, r15
0x1409c15d0  mov     ecx, r13d
0x1409c15d3  call    ?GetTextColorForState@GdiUtil@Outlook@@YAKIAEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@Mso@@@Z; Outlook::GdiUtil::GetTextColorForState(uint,Mso::UIColor::ITPalette<Mso::UIColor::Swatch> &)
0x1409c15d8  mov     ebx, eax
0x1409c15da  mov     edx, eax; color
0x1409c15dc  mov     rcx, [rsp+3D0h+hdc]; hdc
0x1409c15e1  call    cs:__imp_SetTextColor
0x1409c15e7  mov     r13d, eax
0x1409c15ea  cmp     [rsp+3D0h+var_355], 0
0x1409c15ef  jnz     loc_1409C1715
0x1409c15f5  mov     rbx, [rbp+2D0h+var_330]
0x1409c15f9  cmp     [rsp+3D0h+var_353], 0
0x1409c15fe  jz      loc_1409C191D
0x1409c1604  test    dil, dil
0x1409c1607  jnz     loc_1409C1881
0x1409c160d  mov     edi, [rbp+2D0h+var_310]
0x1409c1610  test    r14, r14
0x1409c1613  jz      loc_1409C16B1
0x1409c1619  mov     r9d, [rbp+2D0h+y.right]
0x1409c161d  mov     rdx, qword ptr [rbp+2D0h+y.left]; x
0x1409c1621  sub     r9d, edx; cx
  ... truncated ...
```
