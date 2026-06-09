# Art::ColorSchemePicker::DrawColorSchemeGraph(HDC__ *,Art::ColorScheme const &,Ofc::CRect const &,ulong &)

- ea: `0x180336b10`
- end: `0x180337089`
- name: `?DrawColorSchemeGraph@ColorSchemePicker@Art@@KAXPEAUHDC__@@AEBVColorScheme@2@AEBVCRect@Ofc@@AEAK@Z`
- size: `1401`
- prototype: `void __fastcall(HDC this, const struct Art::ColorScheme *, const struct Ofc::CRect *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1805f85c4`

## callees

- `0x180037550`
- `0x180037d30`
- `0x180070fe0`
- `0x180336b10`
- `0x1803374f0`
- `0x180337554`
- `0x180337dbc`
- `0x18060c7ac`
- `0x18060cb18`
- `0x180a12110`

## import_xrefs

- `GDI32!CreatePen` at `0x180336bcc`
- `GDI32!CreatePen` at `0x180336bcc`
- `GDI32!RestoreDC` at `0x180337064`
- `GDI32!RestoreDC` at `0x180337064`
- `GDI32!SaveDC` at `0x180336b46`
- `GDI32!SaveDC` at `0x180336b46`
- `GDI32!Rectangle` at `0x180336c3c`
- `GDI32!Rectangle` at `0x180336cac`
- `GDI32!Rectangle` at `0x180336d1d`
- `GDI32!Rectangle` at `0x180336d83`
- `GDI32!Rectangle` at `0x180336c3c`
- `GDI32!Rectangle` at `0x180336cac`
- `GDI32!Rectangle` at `0x180336d1d`
- `GDI32!Rectangle` at `0x180336d83`
- `GDI32!SelectObject` at `0x180336bf1`
- `GDI32!SelectObject` at `0x180336c4f`
- `GDI32!SelectObject` at `0x180336cbf`
- `GDI32!SelectObject` at `0x180336d30`
- `GDI32!SelectObject` at `0x180336d96`
- `GDI32!SelectObject` at `0x180336dca`
- `GDI32!SelectObject` at `0x180336bf1`
- `GDI32!SelectObject` at `0x180336c4f`
- `GDI32!SelectObject` at `0x180336cbf`
- `GDI32!SelectObject` at `0x180336d30`
- `GDI32!SelectObject` at `0x180336d96`
- `GDI32!SelectObject` at `0x180336dca`
- `GDI32!DeleteObject` at `0x180336c5e`
- `GDI32!DeleteObject` at `0x180336cce`
- `GDI32!DeleteObject` at `0x180336d3f`
- `GDI32!DeleteObject` at `0x180336da5`
- `GDI32!DeleteObject` at `0x180336ddd`
- `GDI32!DeleteObject` at `0x180336c5e`
- `GDI32!DeleteObject` at `0x180336cce`
- `GDI32!DeleteObject` at `0x180336d3f`
- `GDI32!DeleteObject` at `0x180336da5`
- `GDI32!DeleteObject` at `0x180336ddd`
- `USER32!GetSysColor` at `0x180336bad`
- `USER32!GetSysColor` at `0x180336bad`

## pseudocode

```c
void __fastcall Art::ColorSchemePicker::DrawColorSchemeGraph(
        HDC this,
        const struct Art::ColorScheme *a2,
        const struct Ofc::CRect *a3,
        unsigned int *a4)
{
  LONG v8; // r9d
  LONG v9; // r8d
  int v10; // ebx
  int v11; // r13d
  DWORD SysColor; // eax
  const struct tagRECT *v13; // r9
  HPEN Pen; // rax
  HGDIOBJ v15; // r12
  unsigned int COLORREF; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // r8d
  HDC v21; // rdx
  Art::Color *PresetSchemeColor; // rax
  unsigned int v23; // r12d
  Art::Color *v24; // rax
  unsigned int v25; // r13d
  Art::Color *v26; // rax
  Art::Color *v27; // rax
  Art::Color *v28; // rax
  Art::Color *v29; // rax
  Art::Color *v30; // rax
  unsigned int v31; // r10d
  unsigned int v32; // ecx
  unsigned int v33; // r15d
  LONG v34; // ecx
  LONG v35; // eax
  int v36; // ebx
  int v37; // r9d
  int v38; // r9d
  int v39; // r9d
  int v40; // r9d
  int v41; // r9d
  int v42; // r9d
  int v43; // r9d
  int v44; // r9d
  int bottom; // [rsp+20h] [rbp-59h]
  int bottoma; // [rsp+20h] [rbp-59h]
  int bottomb; // [rsp+20h] [rbp-59h]
  int bottomc; // [rsp+20h] [rbp-59h]
  int bottomd; // [rsp+20h] [rbp-59h]
  int bottome; // [rsp+20h] [rbp-59h]
  int bottomf; // [rsp+20h] [rbp-59h]
  int bottomg; // [rsp+20h] [rbp-59h]
  const struct tagRECT *v53; // [rsp+28h] [rbp-51h]
  unsigned int v54; // [rsp+30h] [rbp-49h]
  unsigned int v55; // [rsp+30h] [rbp-49h]
  unsigned int v56; // [rsp+34h] [rbp-45h]
  unsigned int v57; // [rsp+34h] [rbp-45h]
  int v58; // [rsp+38h] [rbp-41h]
  unsigned int v59; // [rsp+38h] [rbp-41h]
  unsigned int v60; // [rsp+3Ch] [rbp-3Dh]
  HGDIOBJ ho; // [rsp+40h] [rbp-39h] BYREF
  HDC hdc; // [rsp+48h] [rbp-31h]
  HGDIOBJ h; // [rsp+50h] [rbp-29h]
  unsigned int v64; // [rsp+58h] [rbp-21h]
  unsigned int v65; // [rsp+60h] [rbp-19h]
  HDC v66; // [rsp+68h] [rbp-11h]
  int nSavedDC; // [rsp+70h] [rbp-9h]
  RECT v68; // [rsp+78h] [rbp-1h] BYREF
  HGDIOBJ v69; // [rsp+88h] [rbp+Fh]

  v66 = this;
  nSavedDC = SaveDC(this);
  v8 = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
  v9 = *((_DWORD *)a3 + 2) - *(_DWORD *)a3;
  if ( v9 == v8 )
  {
    v10 = v9 / 32;
    v11 = v9 / 2;
    v56 = v9 / 2;
    v58 = v9 / 2 - v9 / 32;
    v54 = (v8 - 2 * (v9 / 32)) / 2;
    *(_QWORD *)&v68.left = 0;
    v68.right = v9;
    v68.bottom = v8;
    SysColor = GetSysColor(5);
    Ofc::FillRect(this, (HDC)SysColor, &v68, v13);
    Pen = CreatePen(5, 0, 0x2000000u);
    *(_QWORD *)&v68.left = Pen;
    *(_QWORD *)&v68.right = this;
    v15 = 0;
    v69 = 0;
    if ( Pen && this )
    {
      v15 = SelectObject(this, Pen);
      v69 = v15;
    }
    COLORREF = Art::Color::GetCOLORREF((const struct Art::ColorScheme *)((char *)a2 + 48));
    Ofc::CHBrush::CHBrush((Ofc::CHBrush *)&ho, this, COLORREF);
    Rectangle(
      this,
      *(_DWORD *)a3 + v10,
      *((_DWORD *)a3 + 1) + v10,
      v11 + *(_DWORD *)a3 + 1,
      v10 + *((_DWORD *)a3 + 1) + v54 + 1);
    if ( h )
      SelectObject(hdc, h);
    if ( ho )
      DeleteObject(ho);
    v17 = Art::Color::GetCOLORREF((const struct Art::ColorScheme *)((char *)a2 + 72));
    Ofc::CHBrush::CHBrush((Ofc::CHBrush *)&ho, this, v17);
    Rectangle(
      this,
      *(_DWORD *)a3 + v11,
      *((_DWORD *)a3 + 1) + v10,
      v10 + *(_DWORD *)a3 + 2 * v58 + 1,
      v10 + *((_DWORD *)a3 + 1) + v54 + 1);
    if ( h )
      SelectObject(hdc, h);
    if ( ho )
      DeleteObject(ho);
    v18 = Art::Color::GetCOLORREF((const struct Art::ColorScheme *)((char *)a2 + 96));
    Ofc::CHBrush::CHBrush((Ofc::CHBrush *)&ho, this, v18);
    Rectangle(
      this,
      v10 + *(_DWORD *)a3,
      v10 + v54 + *((_DWORD *)a3 + 1),
      *(_DWORD *)a3 + v56 + 1,
      1 - v10 + *((_DWORD *)a3 + 3));
    if ( h )
      SelectObject(hdc, h);
    if ( ho )
      DeleteObject(ho);
    v19 = Art::Color::GetCOLORREF((const struct Art::ColorScheme *)((char *)a2 + 120));
    Ofc::CHBrush::CHBrush((Ofc::CHBrush *)&ho, this, v19);
    Rectangle(
      this,
      *(_DWORD *)a3 + v56,
      v10 + v54 + *((_DWORD *)a3 + 1),
      1 - v10 + *((_DWORD *)a3 + 2),
      1 - v10 + *((_DWORD *)a3 + 3));
    v21 = (HDC)h;
    if ( h )
      SelectObject(hdc, h);
    if ( ho )
      DeleteObject(ho);
    Ofc::FrameRect(this, v21, v20, 8421504, (unsigned int)a3, v53);
    if ( v15 )
      SelectObject(this, v15);
    if ( *(_QWORD *)&v68.left )
      DeleteObject(*(HGDIOBJ *)&v68.left);
  }
  else
  {
    PresetSchemeColor = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 2);
    v23 = Art::Color::GetCOLORREF(PresetSchemeColor);
    v24 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 3);
    v25 = Art::Color::GetCOLORREF(v24);
    v26 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 4);
    v64 = Art::Color::GetCOLORREF(v26);
    v27 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 5);
    v57 = Art::Color::GetCOLORREF(v27);
    v55 = Art::Color::GetCOLORREF((const struct Art::ColorScheme *)((char *)a2 + 144));
    v28 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 7);
    v60 = Art::Color::GetCOLORREF(v28);
    v29 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 8);
    v59 = Art::Color::GetCOLORREF(v29);
    v30 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 9);
    v31 = Art::Color::GetCOLORREF(v30);
    v65 = v31;
    *a4 = 0;
    v32 = 0;
    v33 = v64;
    do
    {
      if ( v32 != v23 && v32 != v25 && v32 != v33 && v32 != v57 && v32 != v55 && v32 != v60 && v32 != v59 && v32 != v31 )
        break;
      *a4 = ++v32;
    }
    while ( v32 < 0xA );
    v34 = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    v35 = *((_DWORD *)a3 + 2) - *(_DWORD *)a3;
    *(_QWORD *)&v68.left = 0;
    v68.right = v35;
    v68.bottom = v34;
    Ofc::FillRect(this, (HDC)*a4, &v68, (const struct tagRECT *)v59);
    v36 = (*((_DWORD *)a3 + 2) - *(_DWORD *)a3) / 8;
    Ofc::CHPen::CHPen((Ofc::CHPen *)&ho, this, 0, 1, 0x868686u);
    bottom = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v23, *(_DWORD *)a3, v37, bottom, bottom);
    bottoma = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v25, v36 + *(_DWORD *)a3, v38, bottoma, bottoma);
    bottomb = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v33, *(_DWORD *)a3 + 2 * v36, v39, bottomb, bottomb);
    bottomc = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v57, *(_DWORD *)a3 + 3 * v36, v40, bottomc, bottomc);
    bottomd = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v55, *(_DWORD *)a3 + 4 * v36, v41, bottomd, bottomd);
    bottome = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v60, *(_DWORD *)a3 + 5 * v36, v42, bottome, bottome);
    bottomf = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v59, *(_DWORD *)a3 + 6 * v36, v43, bottomf, bottomf);
    bottomg = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v65, *(_DWORD *)a3 + 7 * v36, v44, bottomg, bottomg);
    Ofc::CHPen::~CHPen((Ofc::CHPen *)&ho);
  }
  if ( nSavedDC )
    RestoreDC(this, nSavedDC);
}

```

## disassembly

```asm
0x180336b10  push    rbp
0x180336b12  push    rbx
0x180336b13  push    rsi
0x180336b14  push    r12
0x180336b16  push    r13
0x180336b18  push    r14
0x180336b1a  push    r15
0x180336b1c  lea     rbp, [rsp-27h]
0x180336b21  sub     rsp, 0A0h
0x180336b28  mov     rax, cs:__security_cookie
0x180336b2f  xor     rax, rsp
0x180336b32  mov     [rbp+57h+var_40], rax
0x180336b36  mov     rbx, r9
0x180336b39  mov     r14, r8
0x180336b3c  mov     r15, rdx
0x180336b3f  mov     rsi, rcx
0x180336b42  mov     [rbp+57h+var_68], rcx
0x180336b46  call    cs:__imp_SaveDC
0x180336b4c  mov     [rbp+57h+nSavedDC], eax
0x180336b4f  mov     r9d, [r14+0Ch]
0x180336b53  sub     r9d, [r14+4]
0x180336b57  mov     r8d, [r14+8]
0x180336b5b  sub     r8d, [r14]
0x180336b5e  cmp     r8d, r9d
0x180336b61  jnz     loc_180336DE8
0x180336b67  mov     eax, r8d
0x180336b6a  cdq
0x180336b6b  mov     ecx, 20h ; ' '
0x180336b70  idiv    ecx
0x180336b72  mov     ebx, eax
0x180336b74  mov     eax, r8d
0x180336b77  cdq
0x180336b78  lea     r10d, [rcx-1Eh]
0x180336b7c  idiv    r10d
0x180336b7f  mov     r13d, eax
0x180336b82  mov     [rbp+57h+var_9C], eax
0x180336b85  sub     eax, ebx
0x180336b87  mov     dword ptr [rbp+57h+var_98], eax
0x180336b8a  lea     ecx, [rbx+rbx]
0x180336b8d  mov     eax, r9d
0x180336b90  sub     eax, ecx
0x180336b92  cdq
0x180336b93  idiv    r10d
0x180336b96  mov     [rbp+57h+var_A0], eax
0x180336b99  mov     [rbp+57h+var_58], 0
0x180336ba1  mov     dword ptr [rbp+57h+var_50], r8d
0x180336ba5  mov     dword ptr [rbp+57h+var_50+4], r9d
0x180336ba9  lea     ecx, [r10+3]; nIndex
0x180336bad  call    cs:__imp_GetSysColor
0x180336bb3  lea     r8, [rbp+57h+var_58]; lprc
0x180336bb7  mov     edx, eax; HDC
0x180336bb9  mov     rcx, rsi; this
0x180336bbc  call    ?FillRect@Ofc@@YAXPEAUHDC__@@KAEBUtagRECT@@@Z; Ofc::FillRect(HDC__ *,ulong,tagRECT const &)
0x180336bc1  xor     edx, edx; cWidth
0x180336bc3  lea     ecx, [rdx+5]; iStyle
0x180336bc6  mov     r8d, 2000000h; color
0x180336bcc  call    cs:__imp_CreatePen
0x180336bd2  mov     [rbp+57h+var_58], rax
0x180336bd6  mov     [rbp+57h+var_50], rsi
0x180336bda  xor     r12d, r12d
0x180336bdd  mov     [rbp+57h+var_48], r12
0x180336be1  test    rax, rax
0x180336be4  jz      short loc_180336BFE
0x180336be6  test    rsi, rsi
0x180336be9  jz      short loc_180336BFE
0x180336beb  mov     rdx, rax; h
0x180336bee  mov     rcx, rsi; hdc
0x180336bf1  call    cs:__imp_SelectObject
0x180336bf7  mov     r12, rax
0x180336bfa  mov     [rbp+57h+var_48], rax
0x180336bfe  lea     rcx, [r15+30h]; this
0x180336c02  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180336c07  mov     r8d, eax; unsigned int
0x180336c0a  mov     rdx, rsi; HDC
0x180336c0d  lea     rcx, [rbp+57h+ho]; this
0x180336c11  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x180336c16  mov     edx, [r14+4]
0x180336c1a  mov     r10d, [r14]
0x180336c1d  mov     ecx, [rbp+57h+var_A0]
0x180336c20  inc     ecx
0x180336c22  add     ecx, edx
0x180336c24  add     ecx, ebx
0x180336c26  lea     r9d, [r10+1]
0x180336c2a  add     r9d, r13d; right
0x180336c2d  lea     r8d, [rdx+rbx]; top
0x180336c31  lea     edx, [r10+rbx]; left
0x180336c35  mov     [rsp+0D0h+bottom], ecx; bottom
0x180336c39  mov     rcx, rsi; hdc
0x180336c3c  call    cs:__imp_Rectangle
0x180336c42  mov     rdx, [rbp+57h+h]; h
0x180336c46  test    rdx, rdx
0x180336c49  jz      short loc_180336C55
0x180336c4b  mov     rcx, [rbp+57h+hdc]; hdc
0x180336c4f  call    cs:__imp_SelectObject
0x180336c55  mov     rcx, [rbp+57h+ho]; ho
0x180336c59  test    rcx, rcx
0x180336c5c  jz      short loc_180336C64
0x180336c5e  call    cs:__imp_DeleteObject
0x180336c64  lea     rcx, [r15+48h]; this
0x180336c68  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180336c6d  mov     r8d, eax; unsigned int
0x180336c70  mov     rdx, rsi; HDC
0x180336c73  lea     rcx, [rbp+57h+ho]; this
0x180336c77  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x180336c7c  mov     edx, [r14+4]
0x180336c80  mov     r10d, [r14]
0x180336c83  mov     ecx, [rbp+57h+var_A0]
0x180336c86  inc     ecx
0x180336c88  add     ecx, edx
0x180336c8a  add     ecx, ebx
0x180336c8c  mov     eax, dword ptr [rbp+57h+var_98]
0x180336c8f  lea     r9d, ds:1[rax*2]
0x180336c97  add     r9d, r10d
0x180336c9a  add     r9d, ebx; right
0x180336c9d  lea     r8d, [rdx+rbx]; top
0x180336ca1  lea     edx, [r10+r13]; left
0x180336ca5  mov     [rsp+0D0h+bottom], ecx; bottom
0x180336ca9  mov     rcx, rsi; hdc
0x180336cac  call    cs:__imp_Rectangle
0x180336cb2  mov     rdx, [rbp+57h+h]; h
0x180336cb6  test    rdx, rdx
0x180336cb9  jz      short loc_180336CC5
0x180336cbb  mov     rcx, [rbp+57h+hdc]; hdc
0x180336cbf  call    cs:__imp_SelectObject
0x180336cc5  mov     rcx, [rbp+57h+ho]; ho
0x180336cc9  test    rcx, rcx
0x180336ccc  jz      short loc_180336CD4
0x180336cce  call    cs:__imp_DeleteObject
0x180336cd4  lea     rcx, [r15+60h]; this
0x180336cd8  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180336cdd  mov     r8d, eax; unsigned int
0x180336ce0  mov     rdx, rsi; HDC
0x180336ce3  lea     rcx, [rbp+57h+ho]; this
0x180336ce7  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x180336cec  mov     r13d, 1
0x180336cf2  sub     r13d, ebx
0x180336cf5  mov     edx, [r14]
0x180336cf8  mov     ecx, [r14+0Ch]
0x180336cfc  add     ecx, r13d
0x180336cff  mov     r9d, [rbp+57h+var_9C]
0x180336d03  inc     r9d
0x180336d06  add     r9d, edx; right
0x180336d09  mov     r8d, [r14+4]
0x180336d0d  add     r8d, [rbp+57h+var_A0]
0x180336d11  add     r8d, ebx; top
0x180336d14  add     edx, ebx; left
0x180336d16  mov     [rsp+0D0h+bottom], ecx; bottom
0x180336d1a  mov     rcx, rsi; hdc
0x180336d1d  call    cs:__imp_Rectangle
0x180336d23  mov     rdx, [rbp+57h+h]; h
0x180336d27  test    rdx, rdx
0x180336d2a  jz      short loc_180336D36
0x180336d2c  mov     rcx, [rbp+57h+hdc]; hdc
0x180336d30  call    cs:__imp_SelectObject
0x180336d36  mov     rcx, [rbp+57h+ho]; ho
0x180336d3a  test    rcx, rcx
0x180336d3d  jz      short loc_180336D45
0x180336d3f  call    cs:__imp_DeleteObject
0x180336d45  lea     rcx, [r15+78h]; this
0x180336d49  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180336d4e  mov     r8d, eax; unsigned int
0x180336d51  mov     rdx, rsi; HDC
0x180336d54  lea     rcx, [rbp+57h+ho]; this
0x180336d58  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x180336d5d  mov     ecx, [r14+0Ch]
0x180336d61  add     ecx, r13d
0x180336d64  mov     r9d, [r14+8]
0x180336d68  add     r9d, r13d; right
0x180336d6b  mov     r8d, [r14+4]
0x180336d6f  add     r8d, [rbp+57h+var_A0]
0x180336d73  add     r8d, ebx; top
0x180336d76  mov     edx, [rbp+57h+var_9C]
0x180336d79  add     edx, [r14]; left
0x180336d7c  mov     [rsp+0D0h+bottom], ecx; bottom
0x180336d80  mov     rcx, rsi; hdc
0x180336d83  call    cs:__imp_Rectangle
0x180336d89  mov     rdx, [rbp+57h+h]; h
0x180336d8d  test    rdx, rdx
0x180336d90  jz      short loc_180336D9C
0x180336d92  mov     rcx, [rbp+57h+hdc]; hdc
0x180336d96  call    cs:__imp_SelectObject
0x180336d9c  mov     rcx, [rbp+57h+ho]; ho
0x180336da0  test    rcx, rcx
0x180336da3  jz      short loc_180336DAB
0x180336da5  call    cs:__imp_DeleteObject
0x180336dab  mov     qword ptr [rsp+0D0h+bottom], r14; unsigned int
0x180336db0  mov     r9d, 808080h; int
0x180336db6  mov     rcx, rsi; this
0x180336db9  call    ?FrameRect@Ofc@@YAXPEAUHDC__@@HHKAEBUtagRECT@@@Z; Ofc::FrameRect(HDC__ *,int,int,ulong,tagRECT const &)
0x180336dbe  nop
0x180336dbf  test    r12, r12
0x180336dc2  jz      short loc_180336DD0
0x180336dc4  mov     rdx, r12; h
0x180336dc7  mov     rcx, rsi; hdc
0x180336dca  call    cs:__imp_SelectObject
0x180336dd0  mov     rcx, [rbp+57h+var_58]; ho
0x180336dd4  test    rcx, rcx
0x180336dd7  jz      loc_18033705A
0x180336ddd  call    cs:__imp_DeleteObject
0x180336de3  jmp     loc_18033705A
0x180336de8  mov     edx, 2
0x180336ded  mov     rcx, r15
0x180336df0  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x180336df5  mov     rcx, rax; this
0x180336df8  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180336dfd  mov     r12d, eax
0x180336e00  mov     edx, 3
0x180336e05  mov     rcx, r15
0x180336e08  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x180336e0d  mov     rcx, rax; this
0x180336e10  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180336e15  mov     r13d, eax
0x180336e18  mov     edx, 4
0x180336e1d  mov     rcx, r15
0x180336e20  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x180336e25  mov     rcx, rax; this
0x180336e28  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180336e2d  mov     [rbp+57h+var_78], eax
0x180336e30  mov     edx, 5
0x180336e35  mov     rcx, r15
0x180336e38  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x180336e3d  mov     rcx, rax; this
0x180336e40  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180336e45  mov     [rbp+57h+var_9C], eax
0x180336e48  lea     rcx, [r15+90h]; this
0x180336e4f  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180336e54  mov     [rbp+57h+var_A0], eax
0x180336e57  mov     edx, 7
0x180336e5c  mov     rcx, r15
0x180336e5f  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x180336e64  mov     rcx, rax; this
0x180336e67  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180336e6c  mov     dword ptr [rbp+57h+var_98+4], eax
0x180336e6f  mov     edx, 8
0x180336e74  mov     rcx, r15
0x180336e77  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x180336e7c  mov     rcx, rax; this
0x180336e7f  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180336e84  mov     dword ptr [rbp+57h+var_98], eax
0x180336e87  mov     edx, 9
0x180336e8c  mov     rcx, r15
0x180336e8f  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x180336e94  mov     rcx, rax; this
0x180336e97  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180336e9c  mov     r10d, eax
0x180336e9f  mov     [rbp+57h+var_70], eax
0x180336ea2  mov     dword ptr [rbx], 0
0x180336ea8  xor     ecx, ecx
0x180336eaa  mov     r15d, [rbp+57h+var_78]
0x180336eae  mov     eax, [rbp+57h+var_9C]
0x180336eb1  mov     edx, [rbp+57h+var_A0]
0x180336eb4  mov     r8d, dword ptr [rbp+57h+var_98+4]
0x180336eb8  mov     r9d, dword ptr [rbp+57h+var_98]; struct tagRECT *
0x180336ebc  cmp     ecx, r12d
0x180336ebf  jz      short loc_180336EE2
0x180336ec1  cmp     ecx, r13d
0x180336ec4  jz      short loc_180336EE2
0x180336ec6  cmp     ecx, r15d
0x180336ec9  jz      short loc_180336EE2
0x180336ecb  cmp     ecx, eax
0x180336ecd  jz      short loc_180336EE2
0x180336ecf  cmp     ecx, edx
0x180336ed1  jz      short loc_180336EE2
0x180336ed3  cmp     ecx, r8d
0x180336ed6  jz      short loc_180336EE2
0x180336ed8  cmp     ecx, r9d
0x180336edb  jz      short loc_180336EE2
0x180336edd  cmp     ecx, r10d
0x180336ee0  jnz     short loc_180336EEB
0x180336ee2  inc     ecx
0x180336ee4  mov     [rbx], ecx
0x180336ee6  cmp     ecx, 0Ah
0x180336ee9  jb      short loc_180336EBC
0x180336eeb  mov     ecx, [r14+0Ch]
0x180336eef  sub     ecx, [r14+4]
0x180336ef3  mov     eax, [r14+8]
0x180336ef7  sub     eax, [r14]
0x180336efa  mov     [rbp+57h+var_58], 0
0x180336f02  mov     dword ptr [rbp+57h+var_50], eax
0x180336f05  mov     dword ptr [rbp+57h+var_50+4], ecx
0x180336f08  lea     r8, [rbp+57h+var_58]; lprc
0x180336f0c  mov     edx, [rbx]; HDC
0x180336f0e  mov     rcx, rsi; this
0x180336f11  call    ?FillRect@Ofc@@YAXPEAUHDC__@@KAEBUtagRECT@@@Z; Ofc::FillRect(HDC__ *,ulong,tagRECT const &)
0x180336f16  mov     eax, [r14+8]
0x180336f1a  sub     eax, [r14]
0x180336f1d  cdq
0x180336f1e  mov     ecx, 8
0x180336f23  idiv    ecx
0x180336f25  mov     ebx, eax
0x180336f27  mov     [rsp+0D0h+bottom], 868686h; unsigned int
0x180336f2f  lea     r9d, [rcx-7]; int
0x180336f33  xor     r8d, r8d; int
0x180336f36  mov     rdx, rsi; HDC
0x180336f39  lea     rcx, [rbp+57h+ho]; this
0x180336f3d  call    ??0CHPen@Ofc@@QEAA@PEAUHDC__@@HHK@Z; Ofc::CHPen::CHPen(HDC__ *,int,int,ulong)
0x180336f42  mov     ecx, [r14+0Ch]
0x180336f46  sub     ecx, [r14+4]
0x180336f4a  mov     dword ptr [rsp+0D0h+var_A8], ecx; int
0x180336f4e  mov     [rsp+0D0h+bottom], ecx; int
  ... truncated ...
```
