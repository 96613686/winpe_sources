# Art::ColorSchemePicker::DrawColorSchemeGraph(HDC__ *,Art::ColorScheme const &,Ofc::CRect const &,ulong &)

- ea: `0x180434564`
- end: `0x180434ae6`
- name: `?DrawColorSchemeGraph@ColorSchemePicker@Art@@KAXPEAUHDC__@@AEBVColorScheme@2@AEBVCRect@Ofc@@AEAK@Z`
- size: `1410`
- prototype: `void __fastcall(HDC this, const struct Art::ColorScheme *, const struct Ofc::CRect *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180615454`

## callees

- `0x18001a180`
- `0x180026740`
- `0x180279030`
- `0x180434564`
- `0x180434ae8`
- `0x180434fb8`
- `0x1804360f8`
- `0x18062d3c8`
- `0x180630930`
- `0x180a1a4e0`

## import_xrefs

- `GDI32!CreatePen` at `0x180434620`
- `GDI32!CreatePen` at `0x180434620`
- `GDI32!RestoreDC` at `0x180434ac1`
- `GDI32!RestoreDC` at `0x180434ac1`
- `GDI32!SaveDC` at `0x18043459a`
- `GDI32!SaveDC` at `0x18043459a`
- `GDI32!Rectangle` at `0x180434690`
- `GDI32!Rectangle` at `0x180434700`
- `GDI32!Rectangle` at `0x180434771`
- `GDI32!Rectangle` at `0x1804347d7`
- `GDI32!Rectangle` at `0x180434690`
- `GDI32!Rectangle` at `0x180434700`
- `GDI32!Rectangle` at `0x180434771`
- `GDI32!Rectangle` at `0x1804347d7`
- `GDI32!SelectObject` at `0x180434645`
- `GDI32!SelectObject` at `0x1804346a3`
- `GDI32!SelectObject` at `0x180434713`
- `GDI32!SelectObject` at `0x180434784`
- `GDI32!SelectObject` at `0x1804347ea`
- `GDI32!SelectObject` at `0x18043481e`
- `GDI32!SelectObject` at `0x180434645`
- `GDI32!SelectObject` at `0x1804346a3`
- `GDI32!SelectObject` at `0x180434713`
- `GDI32!SelectObject` at `0x180434784`
- `GDI32!SelectObject` at `0x1804347ea`
- `GDI32!SelectObject` at `0x18043481e`
- `GDI32!DeleteObject` at `0x1804346b2`
- `GDI32!DeleteObject` at `0x180434722`
- `GDI32!DeleteObject` at `0x180434793`
- `GDI32!DeleteObject` at `0x1804347f9`
- `GDI32!DeleteObject` at `0x180434831`
- `GDI32!DeleteObject` at `0x1804346b2`
- `GDI32!DeleteObject` at `0x180434722`
- `GDI32!DeleteObject` at `0x180434793`
- `GDI32!DeleteObject` at `0x1804347f9`
- `GDI32!DeleteObject` at `0x180434831`
- `USER32!GetSysColor` at `0x180434601`
- `USER32!GetSysColor` at `0x180434601`

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
  Art::Color *v31; // rax
  unsigned int v32; // r10d
  unsigned int v33; // ecx
  unsigned int v34; // r15d
  LONG v35; // ecx
  LONG v36; // eax
  int v37; // ebx
  int v38; // r9d
  int v39; // r9d
  int v40; // r9d
  int v41; // r9d
  int v42; // r9d
  int v43; // r9d
  int v44; // r9d
  int v45; // r9d
  int bottom; // [rsp+20h] [rbp-59h]
  int bottoma; // [rsp+20h] [rbp-59h]
  int bottomb; // [rsp+20h] [rbp-59h]
  int bottomc; // [rsp+20h] [rbp-59h]
  int bottomd; // [rsp+20h] [rbp-59h]
  int bottome; // [rsp+20h] [rbp-59h]
  int bottomf; // [rsp+20h] [rbp-59h]
  int bottomg; // [rsp+20h] [rbp-59h]
  const struct tagRECT *v54; // [rsp+28h] [rbp-51h]
  unsigned int v55; // [rsp+30h] [rbp-49h]
  unsigned int v56; // [rsp+30h] [rbp-49h]
  unsigned int v57; // [rsp+34h] [rbp-45h]
  unsigned int v58; // [rsp+34h] [rbp-45h]
  int v59; // [rsp+38h] [rbp-41h]
  unsigned int v60; // [rsp+38h] [rbp-41h]
  unsigned int v61; // [rsp+3Ch] [rbp-3Dh]
  HGDIOBJ ho; // [rsp+40h] [rbp-39h] BYREF
  HDC hdc; // [rsp+48h] [rbp-31h]
  HGDIOBJ h; // [rsp+50h] [rbp-29h]
  unsigned int v65; // [rsp+58h] [rbp-21h]
  unsigned int v66; // [rsp+60h] [rbp-19h]
  HDC v67; // [rsp+68h] [rbp-11h]
  int nSavedDC; // [rsp+70h] [rbp-9h]
  RECT v69; // [rsp+78h] [rbp-1h] BYREF
  HGDIOBJ v70; // [rsp+88h] [rbp+Fh]

  v67 = this;
  nSavedDC = SaveDC(this);
  v8 = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
  v9 = *((_DWORD *)a3 + 2) - *(_DWORD *)a3;
  if ( v9 == v8 )
  {
    v10 = v9 / 32;
    v11 = v9 / 2;
    v57 = v9 / 2;
    v59 = v9 / 2 - v9 / 32;
    v55 = (v8 - 2 * (v9 / 32)) / 2;
    *(_QWORD *)&v69.left = 0;
    v69.right = v9;
    v69.bottom = v8;
    SysColor = GetSysColor(5);
    Ofc::FillRect(this, (HDC)SysColor, &v69, v13);
    Pen = CreatePen(5, 0, 0x2000000u);
    *(_QWORD *)&v69.left = Pen;
    *(_QWORD *)&v69.right = this;
    v15 = 0;
    v70 = 0;
    if ( Pen && this )
    {
      v15 = SelectObject(this, Pen);
      v70 = v15;
    }
    COLORREF = Art::Color::GetCOLORREF((const struct Art::ColorScheme *)((char *)a2 + 48));
    Ofc::CHBrush::CHBrush((Ofc::CHBrush *)&ho, this, COLORREF);
    Rectangle(
      this,
      *(_DWORD *)a3 + v10,
      *((_DWORD *)a3 + 1) + v10,
      v11 + *(_DWORD *)a3 + 1,
      v10 + *((_DWORD *)a3 + 1) + v55 + 1);
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
      v10 + *(_DWORD *)a3 + 2 * v59 + 1,
      v10 + *((_DWORD *)a3 + 1) + v55 + 1);
    if ( h )
      SelectObject(hdc, h);
    if ( ho )
      DeleteObject(ho);
    v18 = Art::Color::GetCOLORREF((const struct Art::ColorScheme *)((char *)a2 + 96));
    Ofc::CHBrush::CHBrush((Ofc::CHBrush *)&ho, this, v18);
    Rectangle(
      this,
      v10 + *(_DWORD *)a3,
      v10 + v55 + *((_DWORD *)a3 + 1),
      *(_DWORD *)a3 + v57 + 1,
      1 - v10 + *((_DWORD *)a3 + 3));
    if ( h )
      SelectObject(hdc, h);
    if ( ho )
      DeleteObject(ho);
    v19 = Art::Color::GetCOLORREF((const struct Art::ColorScheme *)((char *)a2 + 120));
    Ofc::CHBrush::CHBrush((Ofc::CHBrush *)&ho, this, v19);
    Rectangle(
      this,
      *(_DWORD *)a3 + v57,
      v10 + v55 + *((_DWORD *)a3 + 1),
      1 - v10 + *((_DWORD *)a3 + 2),
      1 - v10 + *((_DWORD *)a3 + 3));
    v21 = (HDC)h;
    if ( h )
      SelectObject(hdc, h);
    if ( ho )
      DeleteObject(ho);
    Ofc::FrameRect(this, v21, v20, 8421504, (unsigned int)a3, v54);
    if ( v15 )
      SelectObject(this, v15);
    if ( *(_QWORD *)&v69.left )
      DeleteObject(*(HGDIOBJ *)&v69.left);
  }
  else
  {
    PresetSchemeColor = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 2);
    v23 = Art::Color::GetCOLORREF(PresetSchemeColor);
    v24 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 3);
    v25 = Art::Color::GetCOLORREF(v24);
    v26 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 4);
    v65 = Art::Color::GetCOLORREF(v26);
    v27 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 5);
    v58 = Art::Color::GetCOLORREF(v27);
    v28 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 6);
    v56 = Art::Color::GetCOLORREF(v28);
    v29 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 7);
    v61 = Art::Color::GetCOLORREF(v29);
    v30 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 8);
    v60 = Art::Color::GetCOLORREF(v30);
    v31 = (Art::Color *)Art::ColorScheme::GetPresetSchemeColor(a2, 9);
    v32 = Art::Color::GetCOLORREF(v31);
    v66 = v32;
    *a4 = 0;
    v33 = 0;
    v34 = v65;
    do
    {
      if ( v33 != v23 && v33 != v25 && v33 != v34 && v33 != v58 && v33 != v56 && v33 != v61 && v33 != v60 && v33 != v32 )
        break;
      *a4 = ++v33;
    }
    while ( v33 < 0xA );
    v35 = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    v36 = *((_DWORD *)a3 + 2) - *(_DWORD *)a3;
    *(_QWORD *)&v69.left = 0;
    v69.right = v36;
    v69.bottom = v35;
    Ofc::FillRect(this, (HDC)*a4, &v69, (const struct tagRECT *)v60);
    v37 = (*((_DWORD *)a3 + 2) - *(_DWORD *)a3) / 8;
    Ofc::CHPen::CHPen((Ofc::CHPen *)&ho, this, 0, 1, 0x868686u);
    bottom = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v23, *(_DWORD *)a3, v38, bottom, bottom);
    bottoma = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v25, v37 + *(_DWORD *)a3, v39, bottoma, bottoma);
    bottomb = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v34, *(_DWORD *)a3 + 2 * v37, v40, bottomb, bottomb);
    bottomc = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v58, *(_DWORD *)a3 + 3 * v37, v41, bottomc, bottomc);
    bottomd = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v56, *(_DWORD *)a3 + 4 * v37, v42, bottomd, bottomd);
    bottome = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v61, *(_DWORD *)a3 + 5 * v37, v43, bottome, bottome);
    bottomf = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v60, *(_DWORD *)a3 + 6 * v37, v44, bottomf, bottomf);
    bottomg = *((_DWORD *)a3 + 3) - *((_DWORD *)a3 + 1);
    Art::ThemeThumbnailHelper::DrawSingleColor(this, v66, *(_DWORD *)a3 + 7 * v37, v45, bottomg, bottomg);
    Ofc::CHPen::~CHPen((Ofc::CHPen *)&ho);
  }
  if ( nSavedDC )
    RestoreDC(this, nSavedDC);
}

```

## disassembly

```asm
0x180434564  push    rbp
0x180434566  push    rbx
0x180434567  push    rsi
0x180434568  push    r12
0x18043456a  push    r13
0x18043456c  push    r14
0x18043456e  push    r15
0x180434570  lea     rbp, [rsp-27h]
0x180434575  sub     rsp, 0A0h
0x18043457c  mov     rax, cs:__security_cookie
0x180434583  xor     rax, rsp
0x180434586  mov     [rbp+57h+var_40], rax
0x18043458a  mov     rbx, r9
0x18043458d  mov     r14, r8
0x180434590  mov     r15, rdx
0x180434593  mov     rsi, rcx
0x180434596  mov     [rbp+57h+var_68], rcx
0x18043459a  call    cs:__imp_SaveDC
0x1804345a0  mov     [rbp+57h+nSavedDC], eax
0x1804345a3  mov     r9d, [r14+0Ch]
0x1804345a7  sub     r9d, [r14+4]
0x1804345ab  mov     r8d, [r14+8]
0x1804345af  sub     r8d, [r14]
0x1804345b2  cmp     r8d, r9d
0x1804345b5  jnz     loc_18043483C
0x1804345bb  mov     eax, r8d
0x1804345be  cdq
0x1804345bf  mov     ecx, 20h ; ' '
0x1804345c4  idiv    ecx
0x1804345c6  mov     ebx, eax
0x1804345c8  mov     eax, r8d
0x1804345cb  cdq
0x1804345cc  lea     r10d, [rcx-1Eh]
0x1804345d0  idiv    r10d
0x1804345d3  mov     r13d, eax
0x1804345d6  mov     [rbp+57h+var_9C], eax
0x1804345d9  sub     eax, ebx
0x1804345db  mov     dword ptr [rbp+57h+var_98], eax
0x1804345de  lea     ecx, [rbx+rbx]
0x1804345e1  mov     eax, r9d
0x1804345e4  sub     eax, ecx
0x1804345e6  cdq
0x1804345e7  idiv    r10d
0x1804345ea  mov     [rbp+57h+var_A0], eax
0x1804345ed  mov     [rbp+57h+var_58], 0
0x1804345f5  mov     dword ptr [rbp+57h+var_50], r8d
0x1804345f9  mov     dword ptr [rbp+57h+var_50+4], r9d
0x1804345fd  lea     ecx, [r10+3]; nIndex
0x180434601  call    cs:__imp_GetSysColor
0x180434607  lea     r8, [rbp+57h+var_58]; lprc
0x18043460b  mov     edx, eax; HDC
0x18043460d  mov     rcx, rsi; this
0x180434610  call    ?FillRect@Ofc@@YAXPEAUHDC__@@KAEBUtagRECT@@@Z; Ofc::FillRect(HDC__ *,ulong,tagRECT const &)
0x180434615  xor     edx, edx; cWidth
0x180434617  lea     ecx, [rdx+5]; iStyle
0x18043461a  mov     r8d, 2000000h; color
0x180434620  call    cs:__imp_CreatePen
0x180434626  mov     [rbp+57h+var_58], rax
0x18043462a  mov     [rbp+57h+var_50], rsi
0x18043462e  xor     r12d, r12d
0x180434631  mov     [rbp+57h+var_48], r12
0x180434635  test    rax, rax
0x180434638  jz      short loc_180434652
0x18043463a  test    rsi, rsi
0x18043463d  jz      short loc_180434652
0x18043463f  mov     rdx, rax; h
0x180434642  mov     rcx, rsi; hdc
0x180434645  call    cs:__imp_SelectObject
0x18043464b  mov     r12, rax
0x18043464e  mov     [rbp+57h+var_48], rax
0x180434652  lea     rcx, [r15+30h]; this
0x180434656  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x18043465b  mov     r8d, eax; unsigned int
0x18043465e  mov     rdx, rsi; HDC
0x180434661  lea     rcx, [rbp+57h+ho]; this
0x180434665  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x18043466a  mov     edx, [r14+4]
0x18043466e  mov     r10d, [r14]
0x180434671  mov     ecx, [rbp+57h+var_A0]
0x180434674  inc     ecx
0x180434676  add     ecx, edx
0x180434678  add     ecx, ebx
0x18043467a  lea     r9d, [r10+1]
0x18043467e  add     r9d, r13d; right
0x180434681  lea     r8d, [rdx+rbx]; top
0x180434685  lea     edx, [r10+rbx]; left
0x180434689  mov     [rsp+0D0h+bottom], ecx; bottom
0x18043468d  mov     rcx, rsi; hdc
0x180434690  call    cs:__imp_Rectangle
0x180434696  mov     rdx, [rbp+57h+h]; h
0x18043469a  test    rdx, rdx
0x18043469d  jz      short loc_1804346A9
0x18043469f  mov     rcx, [rbp+57h+hdc]; hdc
0x1804346a3  call    cs:__imp_SelectObject
0x1804346a9  mov     rcx, [rbp+57h+ho]; ho
0x1804346ad  test    rcx, rcx
0x1804346b0  jz      short loc_1804346B8
0x1804346b2  call    cs:__imp_DeleteObject
0x1804346b8  lea     rcx, [r15+48h]; this
0x1804346bc  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x1804346c1  mov     r8d, eax; unsigned int
0x1804346c4  mov     rdx, rsi; HDC
0x1804346c7  lea     rcx, [rbp+57h+ho]; this
0x1804346cb  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x1804346d0  mov     edx, [r14+4]
0x1804346d4  mov     r10d, [r14]
0x1804346d7  mov     ecx, [rbp+57h+var_A0]
0x1804346da  inc     ecx
0x1804346dc  add     ecx, edx
0x1804346de  add     ecx, ebx
0x1804346e0  mov     eax, dword ptr [rbp+57h+var_98]
0x1804346e3  lea     r9d, ds:1[rax*2]
0x1804346eb  add     r9d, r10d
0x1804346ee  add     r9d, ebx; right
0x1804346f1  lea     r8d, [rdx+rbx]; top
0x1804346f5  lea     edx, [r10+r13]; left
0x1804346f9  mov     [rsp+0D0h+bottom], ecx; bottom
0x1804346fd  mov     rcx, rsi; hdc
0x180434700  call    cs:__imp_Rectangle
0x180434706  mov     rdx, [rbp+57h+h]; h
0x18043470a  test    rdx, rdx
0x18043470d  jz      short loc_180434719
0x18043470f  mov     rcx, [rbp+57h+hdc]; hdc
0x180434713  call    cs:__imp_SelectObject
0x180434719  mov     rcx, [rbp+57h+ho]; ho
0x18043471d  test    rcx, rcx
0x180434720  jz      short loc_180434728
0x180434722  call    cs:__imp_DeleteObject
0x180434728  lea     rcx, [r15+60h]; this
0x18043472c  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180434731  mov     r8d, eax; unsigned int
0x180434734  mov     rdx, rsi; HDC
0x180434737  lea     rcx, [rbp+57h+ho]; this
0x18043473b  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x180434740  mov     r13d, 1
0x180434746  sub     r13d, ebx
0x180434749  mov     edx, [r14]
0x18043474c  mov     ecx, [r14+0Ch]
0x180434750  add     ecx, r13d
0x180434753  mov     r9d, [rbp+57h+var_9C]
0x180434757  inc     r9d
0x18043475a  add     r9d, edx; right
0x18043475d  mov     r8d, [r14+4]
0x180434761  add     r8d, [rbp+57h+var_A0]
0x180434765  add     r8d, ebx; top
0x180434768  add     edx, ebx; left
0x18043476a  mov     [rsp+0D0h+bottom], ecx; bottom
0x18043476e  mov     rcx, rsi; hdc
0x180434771  call    cs:__imp_Rectangle
0x180434777  mov     rdx, [rbp+57h+h]; h
0x18043477b  test    rdx, rdx
0x18043477e  jz      short loc_18043478A
0x180434780  mov     rcx, [rbp+57h+hdc]; hdc
0x180434784  call    cs:__imp_SelectObject
0x18043478a  mov     rcx, [rbp+57h+ho]; ho
0x18043478e  test    rcx, rcx
0x180434791  jz      short loc_180434799
0x180434793  call    cs:__imp_DeleteObject
0x180434799  lea     rcx, [r15+78h]; this
0x18043479d  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x1804347a2  mov     r8d, eax; unsigned int
0x1804347a5  mov     rdx, rsi; HDC
0x1804347a8  lea     rcx, [rbp+57h+ho]; this
0x1804347ac  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x1804347b1  mov     ecx, [r14+0Ch]
0x1804347b5  add     ecx, r13d
0x1804347b8  mov     r9d, [r14+8]
0x1804347bc  add     r9d, r13d; right
0x1804347bf  mov     r8d, [r14+4]
0x1804347c3  add     r8d, [rbp+57h+var_A0]
0x1804347c7  add     r8d, ebx; top
0x1804347ca  mov     edx, [rbp+57h+var_9C]
0x1804347cd  add     edx, [r14]; left
0x1804347d0  mov     [rsp+0D0h+bottom], ecx; bottom
0x1804347d4  mov     rcx, rsi; hdc
0x1804347d7  call    cs:__imp_Rectangle
0x1804347dd  mov     rdx, [rbp+57h+h]; h
0x1804347e1  test    rdx, rdx
0x1804347e4  jz      short loc_1804347F0
0x1804347e6  mov     rcx, [rbp+57h+hdc]; hdc
0x1804347ea  call    cs:__imp_SelectObject
0x1804347f0  mov     rcx, [rbp+57h+ho]; ho
0x1804347f4  test    rcx, rcx
0x1804347f7  jz      short loc_1804347FF
0x1804347f9  call    cs:__imp_DeleteObject
0x1804347ff  mov     qword ptr [rsp+0D0h+bottom], r14; unsigned int
0x180434804  mov     r9d, 808080h; int
0x18043480a  mov     rcx, rsi; this
0x18043480d  call    ?FrameRect@Ofc@@YAXPEAUHDC__@@HHKAEBUtagRECT@@@Z; Ofc::FrameRect(HDC__ *,int,int,ulong,tagRECT const &)
0x180434812  nop
0x180434813  test    r12, r12
0x180434816  jz      short loc_180434824
0x180434818  mov     rdx, r12; h
0x18043481b  mov     rcx, rsi; hdc
0x18043481e  call    cs:__imp_SelectObject
0x180434824  mov     rcx, [rbp+57h+var_58]; ho
0x180434828  test    rcx, rcx
0x18043482b  jz      loc_180434AB7
0x180434831  call    cs:__imp_DeleteObject
0x180434837  jmp     loc_180434AB7
0x18043483c  mov     edx, 2
0x180434841  mov     rcx, r15
0x180434844  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x180434849  mov     rcx, rax; this
0x18043484c  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180434851  mov     r12d, eax
0x180434854  mov     edx, 3
0x180434859  mov     rcx, r15
0x18043485c  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x180434861  mov     rcx, rax; this
0x180434864  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180434869  mov     r13d, eax
0x18043486c  mov     edx, 4
0x180434871  mov     rcx, r15
0x180434874  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x180434879  mov     rcx, rax; this
0x18043487c  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180434881  mov     [rbp+57h+var_78], eax
0x180434884  mov     edx, 5
0x180434889  mov     rcx, r15
0x18043488c  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x180434891  mov     rcx, rax; this
0x180434894  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x180434899  mov     [rbp+57h+var_9C], eax
0x18043489c  mov     edx, 6
0x1804348a1  mov     rcx, r15
0x1804348a4  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x1804348a9  mov     rcx, rax; this
0x1804348ac  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x1804348b1  mov     [rbp+57h+var_A0], eax
0x1804348b4  mov     edx, 7
0x1804348b9  mov     rcx, r15
0x1804348bc  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x1804348c1  mov     rcx, rax; this
0x1804348c4  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x1804348c9  mov     dword ptr [rbp+57h+var_98+4], eax
0x1804348cc  mov     edx, 8
0x1804348d1  mov     rcx, r15
0x1804348d4  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x1804348d9  mov     rcx, rax; this
0x1804348dc  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x1804348e1  mov     dword ptr [rbp+57h+var_98], eax
0x1804348e4  mov     edx, 9
0x1804348e9  mov     rcx, r15
0x1804348ec  call    ?GetPresetSchemeColor@ColorScheme@Art@@QEBAAEBVColor@2@W4ColorSchemeIndex@2@@Z; Art::ColorScheme::GetPresetSchemeColor(Art::ColorSchemeIndex)
0x1804348f1  mov     rcx, rax; this
0x1804348f4  call    ?GetCOLORREF@Color@Art@@QEBAKXZ; Art::Color::GetCOLORREF(void)
0x1804348f9  mov     r10d, eax
0x1804348fc  mov     [rbp+57h+var_70], eax
0x1804348ff  mov     dword ptr [rbx], 0
0x180434905  xor     ecx, ecx
0x180434907  mov     r15d, [rbp+57h+var_78]
0x18043490b  mov     eax, [rbp+57h+var_9C]
0x18043490e  mov     edx, [rbp+57h+var_A0]
0x180434911  mov     r8d, dword ptr [rbp+57h+var_98+4]
0x180434915  mov     r9d, dword ptr [rbp+57h+var_98]; struct tagRECT *
0x180434919  cmp     ecx, r12d
0x18043491c  jz      short loc_18043493F
0x18043491e  cmp     ecx, r13d
0x180434921  jz      short loc_18043493F
0x180434923  cmp     ecx, r15d
0x180434926  jz      short loc_18043493F
0x180434928  cmp     ecx, eax
0x18043492a  jz      short loc_18043493F
0x18043492c  cmp     ecx, edx
0x18043492e  jz      short loc_18043493F
0x180434930  cmp     ecx, r8d
0x180434933  jz      short loc_18043493F
0x180434935  cmp     ecx, r9d
0x180434938  jz      short loc_18043493F
0x18043493a  cmp     ecx, r10d
0x18043493d  jnz     short loc_180434948
0x18043493f  inc     ecx
0x180434941  mov     [rbx], ecx
0x180434943  cmp     ecx, 0Ah
0x180434946  jb      short loc_180434919
0x180434948  mov     ecx, [r14+0Ch]
0x18043494c  sub     ecx, [r14+4]
0x180434950  mov     eax, [r14+8]
0x180434954  sub     eax, [r14]
0x180434957  mov     [rbp+57h+var_58], 0
0x18043495f  mov     dword ptr [rbp+57h+var_50], eax
0x180434962  mov     dword ptr [rbp+57h+var_50+4], ecx
0x180434965  lea     r8, [rbp+57h+var_58]; lprc
0x180434969  mov     edx, [rbx]; HDC
0x18043496b  mov     rcx, rsi; this
0x18043496e  call    ?FillRect@Ofc@@YAXPEAUHDC__@@KAEBUtagRECT@@@Z; Ofc::FillRect(HDC__ *,ulong,tagRECT const &)
0x180434973  mov     eax, [r14+8]
0x180434977  sub     eax, [r14]
0x18043497a  cdq
0x18043497b  mov     ecx, 8
0x180434980  idiv    ecx
0x180434982  mov     ebx, eax
0x180434984  mov     [rsp+0D0h+bottom], 868686h; unsigned int
0x18043498c  lea     r9d, [rcx-7]; int
0x180434990  xor     r8d, r8d; int
0x180434993  mov     rdx, rsi; HDC
0x180434996  lea     rcx, [rbp+57h+ho]; this
0x18043499a  call    ??0CHPen@Ofc@@QEAA@PEAUHDC__@@HHK@Z; Ofc::CHPen::CHPen(HDC__ *,int,int,ulong)
0x18043499f  mov     ecx, [r14+0Ch]
  ... truncated ...
```
