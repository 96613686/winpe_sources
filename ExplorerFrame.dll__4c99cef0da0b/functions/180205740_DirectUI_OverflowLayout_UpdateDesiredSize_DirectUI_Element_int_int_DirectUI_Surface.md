# DirectUI::OverflowLayout::UpdateDesiredSize(DirectUI::Element *,int,int,DirectUI::Surface *)

- ea: `0x180205740`
- end: `0x180205b71`
- name: `?UpdateDesiredSize@OverflowLayout@DirectUI@@UEAA?AUtagSIZE@@PEAVElement@2@HHPEAVSurface@2@@Z`
- size: `1073`
- prototype: `struct tagSIZE __fastcall(DirectUI::OverflowLayout *__hidden this, struct DirectUI::Element *, int, int, struct DirectUI::Surface *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180205740`

## import_xrefs

- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180205837`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180205a45`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180205837`
- `DUI70!?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180205a45`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x1802057ea`
- `DUI70!?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z` at `0x1802057ea`
- `DUI70!?GetLayoutChildCount@Layout@DirectUI@@QEAAIPEAVElement@2@@Z` at `0x18020577c`
- `DUI70!?GetLayoutChildCount@Layout@DirectUI@@QEAAIPEAVElement@2@@Z` at `0x18020577c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1802059c0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180205a9e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180205b36`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1802059c0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180205a9e`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180205b36`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1802057a9`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1802057a9`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180205843`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x180205843`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180205822`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180205a24`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180205b2c`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180205822`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180205a24`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180205b2c`

## pseudocode

```c
struct tagSIZE __fastcall DirectUI::OverflowLayout::UpdateDesiredSize(
        DirectUI::Element **this,
        struct DirectUI::Element *a2,
        struct DirectUI::Element *a3,
        int a4,
        struct DirectUI::Surface *a5,
        __int64 a6)
{
  LONG v9; // r15d
  unsigned int v10; // esi
  __int64 Children; // rax
  unsigned int v12; // edx
  char v13; // bl
  __int64 v14; // r8
  LONG right; // r12d
  LONG bottom; // edi
  DirectUI::Element **v17; // rcx
  DirectUI::Element *ChildFromLayoutIndex; // rax
  DirectUI::Element *v19; // r13
  const struct tagRECT *Margin; // rsi
  int LayoutPos; // eax
  int v22; // ecx
  LONG v23; // eax
  LONG v24; // eax
  LONG top; // eax
  int v26; // edx
  LONG v27; // eax
  LONG v28; // eax
  bool v29; // sf
  int v30; // esi
  LONG left; // eax
  int v32; // ecx
  LONG v33; // eax
  LONG v34; // eax
  int v35; // esi
  DirectUI::Element *v36; // rcx
  char v37; // si
  int v38; // r13d
  const struct tagRECT *v39; // rax
  bool v40; // zf
  LONG v41; // esi
  const struct tagRECT *v42; // rdx
  LONG v43; // ecx
  LONG v44; // eax
  LONG v45; // eax
  LONG v46; // eax
  char v47; // al
  int v48; // esi
  int v49; // edi
  DirectUI::Element *v50; // rcx
  int v51; // eax
  bool v52; // cc
  __int64 v54; // [rsp+20h] [rbp-50h]
  __int64 v55; // [rsp+30h] [rbp-40h] BYREF
  LONG v56; // [rsp+38h] [rbp-38h]
  int v57; // [rsp+3Ch] [rbp-34h]
  int v58; // [rsp+40h] [rbp-30h]
  int v59; // [rsp+44h] [rbp-2Ch]
  int v60; // [rsp+48h] [rbp-28h]
  unsigned int v61; // [rsp+4Ch] [rbp-24h]
  unsigned int LayoutChildCount; // [rsp+50h] [rbp-20h]
  struct DirectUI::Value *v63; // [rsp+58h] [rbp-18h] BYREF
  __int64 v64; // [rsp+60h] [rbp-10h] BYREF
  DirectUI::Value *v65; // [rsp+68h] [rbp-8h] BYREF

  *(_QWORD *)a2 = 0;
  v9 = 0;
  LayoutChildCount = DirectUI::Layout::GetLayoutChildCount((DirectUI::Layout *)this, a3);
  if ( !LayoutChildCount )
    return (struct tagSIZE)a2;
  v10 = (unsigned int)a5;
  v60 = (int)a5;
  v59 = a4;
  v55 = 0;
  v65 = 0;
  Children = DirectUI::Element::GetChildren(a3, &v65);
  v12 = 0;
  v56 = 0;
  v13 = 0;
  v64 = Children;
  v14 = Children;
  right = 0;
  bottom = 0;
  v61 = 0;
  v17 = this;
  v58 = 0;
  v57 = 0;
  do
  {
    ChildFromLayoutIndex = (DirectUI::Element *)DirectUI::Layout::GetChildFromLayoutIndex(v17, a3, v12, v14, v54);
    v17 = this;
    v19 = ChildFromLayoutIndex;
    if ( ChildFromLayoutIndex == this[5] || ChildFromLayoutIndex == this[4] )
      goto LABEL_63;
    v54 = a6;
    DirectUI::Element::_UpdateDesiredSize(ChildFromLayoutIndex, (unsigned int)&v55, a4, (struct DirectUI::Surface *)v10);
    v63 = 0;
    Margin = DirectUI::Element::GetMargin(v19, &v63);
    LayoutPos = DirectUI::Element::GetLayoutPos(v19);
    switch ( LayoutPos )
    {
      case 0:
        if ( (v13 & 1) != 0 )
        {
          left = Margin->left;
          if ( right > Margin->left )
            left = right;
          LODWORD(v55) = left + v55;
        }
        right = Margin->right;
        v13 |= 1u;
        goto LABEL_45;
      case 1:
        v22 = HIDWORD(v55);
        if ( (v13 & 2) != 0 )
        {
          top = Margin->top;
          if ( bottom > top )
            top = bottom;
          v22 = top + HIDWORD(v55);
          HIDWORD(v55) += top;
        }
        bottom = Margin->bottom;
        v13 |= 2u;
        break;
      case 2:
        if ( (v13 & 4) != 0 )
        {
          v24 = Margin->right;
          if ( v56 > v24 )
            v24 = v56;
          LODWORD(v55) = v24 + v55;
        }
        v13 |= 4u;
        v56 = Margin->left;
LABEL_45:
        v32 = HIDWORD(v55);
        if ( (v13 & 2) != 0 )
        {
          v33 = Margin->top;
          if ( bottom > v33 )
            v33 = bottom;
          v32 = v33 + HIDWORD(v55);
          HIDWORD(v55) += v33;
        }
        if ( (v13 & 8) != 0 )
        {
          v34 = Margin->bottom;
          if ( v9 > v34 )
            v34 = v9;
          v32 += v34;
          HIDWORD(v55) = v32;
        }
        if ( (int)v55 <= v59 )
        {
          v59 -= v55;
        }
        else
        {
          LODWORD(v55) = v59;
          v59 = 0;
        }
        v29 = v57 - (int)v55 < 0;
        v35 = v57 - v55;
        v57 -= v55;
        if ( v29 )
        {
          *(_DWORD *)a2 -= v35;
          v57 = 0;
        }
        if ( v32 - v58 > 0 )
        {
          *((_DWORD *)a2 + 1) += v32 - v58;
          v58 = v32;
        }
        goto LABEL_60;
      case 3:
        v22 = HIDWORD(v55);
        if ( (v13 & 8) != 0 )
        {
          v23 = Margin->bottom;
          if ( v9 > v23 )
            v23 = v9;
          v22 = v23 + HIDWORD(v55);
          HIDWORD(v55) += v23;
        }
        v9 = Margin->top;
        v13 |= 8u;
        break;
      default:
        v22 = HIDWORD(v55);
        break;
    }
    v26 = v55;
    if ( (v13 & 1) != 0 )
    {
      v27 = right;
      if ( right <= Margin->left )
        v27 = Margin->left;
      v26 = v27 + v55;
      LODWORD(v55) = v27 + v55;
    }
    if ( (v13 & 4) != 0 )
    {
      v28 = Margin->right;
      if ( v56 > v28 )
        v28 = v56;
      v26 += v28;
      LODWORD(v55) = v26;
    }
    if ( v22 <= v60 )
    {
      v60 -= v22;
    }
    else
    {
      v22 = v60;
      HIDWORD(v55) = v60;
      v60 = 0;
    }
    v29 = v58 - v22 < 0;
    v30 = v58 - v22;
    v58 -= v22;
    if ( v29 )
    {
      *((_DWORD *)a2 + 1) -= v30;
      v58 = 0;
    }
    if ( v26 - v57 > 0 )
    {
      *(_DWORD *)a2 += v26 - v57;
      v57 = v26;
    }
LABEL_60:
    DirectUI::Value::Release(v63);
    if ( !v59 && !v60 )
      goto LABEL_105;
    v17 = this;
    v10 = (unsigned int)a5;
LABEL_63:
    v14 = v64;
    v12 = v61 + 1;
    v61 = v12;
  }
  while ( v12 < LayoutChildCount );
  if ( v12 != LayoutChildCount )
  {
LABEL_105:
    v38 = a4;
    goto LABEL_106;
  }
  v36 = v17[5];
  v37 = v13 & 1;
  if ( v36 )
  {
    v38 = a4;
    v55 = **(_QWORD **)&DirectUI::Element::_UpdateDesiredSize(
                          v36,
                          (unsigned int)&v64,
                          a4,
                          (struct DirectUI::Surface *)(unsigned int)a5);
    v63 = 0;
    v39 = DirectUI::Element::GetMargin(this[5], &v63);
    v40 = v37 == 0;
    v41 = v55;
    v42 = v39;
    if ( !v40 )
    {
      v43 = v39->left;
      if ( right > v39->left )
        v43 = right;
      v41 = v43 + v55;
    }
    if ( (v13 & 2) != 0 )
    {
      v44 = v39->top;
      if ( bottom > v44 )
        v44 = bottom;
      bottom = v44 + HIDWORD(v55);
    }
    else
    {
      bottom = HIDWORD(v55);
    }
    if ( (v13 & 4) != 0 )
    {
      v45 = v42->right;
      if ( v56 > v45 )
        v45 = v56;
      v41 += v45;
    }
    if ( (v13 & 8) != 0 )
    {
      v46 = v42->bottom;
      if ( v9 > v46 )
        v46 = v9;
      bottom += v46;
    }
    DirectUI::Value::Release(v63);
    goto LABEL_101;
  }
  v47 = v13 & 4;
  if ( v37 )
  {
    if ( v47 )
    {
      v41 = v56;
      if ( right > v56 )
        v41 = right;
    }
    else
    {
      v41 = right;
    }
  }
  else if ( v47 )
  {
    v41 = v56;
  }
  else
  {
    v41 = 0;
  }
  if ( (v13 & 0xA) != 0 )
  {
    if ( (v13 & 0xA) == 0xA )
    {
      if ( bottom > v9 )
        goto LABEL_100;
    }
    else if ( (v13 & 2) != 0 )
    {
      goto LABEL_100;
    }
    bottom = v9;
    goto LABEL_100;
  }
  bottom = 0;
LABEL_100:
  v38 = a4;
LABEL_101:
  v48 = v41 - v57;
  if ( v48 > 0 )
    *(_DWORD *)a2 += v48;
  v49 = bottom - v58;
  if ( v49 > 0 )
    *((_DWORD *)a2 + 1) += v49;
LABEL_106:
  v50 = this[4];
  if ( v50 )
    DirectUI::Element::_UpdateDesiredSize(v50, (unsigned int)&v64, v38, (struct DirectUI::Surface *)(unsigned int)a5);
  DirectUI::Value::Release(v65);
  v51 = (int)a5;
  if ( *(_DWORD *)a2 < v38 )
    v38 = *(_DWORD *)a2;
  v52 = *((_DWORD *)a2 + 1) < (int)a5;
  *(_DWORD *)a2 = v38;
  if ( v52 )
    v51 = *((_DWORD *)a2 + 1);
  *((_DWORD *)a2 + 1) = v51;
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x180205740  mov     rax, rsp
0x180205743  mov     [rax+10h], rbx
0x180205747  mov     [rax+20h], r9d
0x18020574b  mov     [rax+18h], r8
0x18020574f  mov     [rax+8], rcx
0x180205753  push    rbp
0x180205754  push    rsi
0x180205755  push    rdi
0x180205756  push    r12
0x180205758  push    r13
0x18020575a  push    r14
0x18020575c  push    r15
0x18020575e  mov     rbp, rsp
0x180205761  sub     rsp, 70h
0x180205765  mov     rax, rcx
0x180205768  mov     r14, rdx
0x18020576b  xor     ecx, ecx
0x18020576d  mov     r13d, r9d
0x180205770  mov     [rdx], rcx
0x180205773  mov     rbx, r8
0x180205776  mov     rdx, r8
0x180205779  mov     rcx, rax
0x18020577c  call    cs:__imp_?GetLayoutChildCount@Layout@DirectUI@@QEAAIPEAVElement@2@@Z; DirectUI::Layout::GetLayoutChildCount(DirectUI::Element *)
0x180205782  xor     r15d, r15d
0x180205785  mov     [rbp+var_20], eax
0x180205788  test    eax, eax
0x18020578a  jz      loc_180205B56
0x180205790  mov     esi, dword ptr [rbp+arg_20]
0x180205793  lea     rdx, [rbp+var_8]
0x180205797  mov     rcx, rbx
0x18020579a  mov     [rbp+var_28], esi
0x18020579d  mov     [rbp+var_2C], r13d
0x1802057a1  mov     [rbp+var_40], r15
0x1802057a5  mov     [rbp+var_8], r15
0x1802057a9  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x1802057af  xor     edx, edx
0x1802057b1  mov     [rbp+var_38], r15d
0x1802057b5  xor     bl, bl
0x1802057b7  mov     [rbp+var_10], rax
0x1802057bb  mov     r8, rax
0x1802057be  mov     r12d, r15d
0x1802057c1  mov     edi, r15d
0x1802057c4  mov     [rbp+var_24], edx
0x1802057c7  cmp     [rbp+var_20], edx
0x1802057ca  jbe     loc_180205B0B
0x1802057d0  mov     eax, dword ptr [rbp+var_40+4]
0x1802057d3  mov     rcx, [rbp+arg_0]
0x1802057d7  mov     [rbp+var_30], eax
0x1802057da  mov     eax, r15d
0x1802057dd  mov     [rbp+var_34], eax
0x1802057e0  mov     r9, r8
0x1802057e3  mov     r8d, edx
0x1802057e6  mov     rdx, [rbp+arg_10]
0x1802057ea  call    cs:__imp_?GetChildFromLayoutIndex@Layout@DirectUI@@QEAAPEAVElement@2@PEAV32@HPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@@Z; DirectUI::Layout::GetChildFromLayoutIndex(DirectUI::Element *,int,DirectUI::DynamicArray<DirectUI::Element *,0> *)
0x1802057f0  mov     rcx, [rbp+arg_0]
0x1802057f4  mov     r13, rax
0x1802057f7  cmp     rax, [rcx+28h]
0x1802057fb  jz      loc_1802059DD
0x180205801  cmp     rax, [rcx+20h]
0x180205805  jz      loc_1802059DD
0x18020580b  mov     rax, [rbp+arg_28]
0x18020580f  lea     rdx, [rbp+var_40]
0x180205813  mov     r8d, [rbp+arg_18]
0x180205817  mov     r9d, esi
0x18020581a  mov     rcx, r13
0x18020581d  mov     [rsp+70h+var_50], rax
0x180205822  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x180205828  lea     rdx, [rbp+var_18]
0x18020582c  mov     [rbp+var_18], 0
0x180205834  mov     rcx, r13
0x180205837  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x18020583d  mov     rcx, r13
0x180205840  mov     rsi, rax
0x180205843  call    cs:__imp_?GetLayoutPos@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetLayoutPos(void)
0x180205849  mov     edx, eax
0x18020584b  test    eax, eax
0x18020584d  jz      loc_18020593E
0x180205853  sub     edx, 1
0x180205856  jz      short loc_1802058B7
0x180205858  sub     edx, 1
0x18020585b  jz      short loc_180205898
0x18020585d  cmp     edx, 1
0x180205860  jz      short loc_180205878
0x180205862  test    eax, eax
0x180205864  jz      loc_180205956
0x18020586a  cmp     eax, 2
0x18020586d  jz      loc_180205956
0x180205873  mov     ecx, dword ptr [rbp+var_40+4]
0x180205876  jmp     short loc_1802058D2
0x180205878  mov     ecx, dword ptr [rbp+var_40+4]
0x18020587b  test    bl, 8
0x18020587e  jz      short loc_18020588F
0x180205880  mov     eax, [rsi+0Ch]
0x180205883  cmp     r15d, eax
0x180205886  cmovg   eax, r15d
0x18020588a  add     ecx, eax
0x18020588c  mov     dword ptr [rbp+var_40+4], ecx
0x18020588f  mov     r15d, [rsi+4]
0x180205893  or      bl, 8
0x180205896  jmp     short loc_1802058D2
0x180205898  test    bl, 4
0x18020589b  jz      short loc_1802058AA
0x18020589d  mov     eax, [rsi+8]
0x1802058a0  cmp     [rbp+var_38], eax
0x1802058a3  cmovg   eax, [rbp+var_38]
0x1802058a7  add     dword ptr [rbp+var_40], eax
0x1802058aa  mov     eax, [rsi]
0x1802058ac  or      bl, 4
0x1802058af  mov     [rbp+var_38], eax
0x1802058b2  jmp     loc_180205956
0x1802058b7  mov     ecx, dword ptr [rbp+var_40+4]
0x1802058ba  test    bl, 2
0x1802058bd  jz      short loc_1802058CC
0x1802058bf  mov     eax, [rsi+4]
0x1802058c2  cmp     edi, eax
0x1802058c4  cmovg   eax, edi
0x1802058c7  add     ecx, eax
0x1802058c9  mov     dword ptr [rbp+var_40+4], ecx
0x1802058cc  mov     edi, [rsi+0Ch]
0x1802058cf  or      bl, 2
0x1802058d2  mov     edx, dword ptr [rbp+var_40]
0x1802058d5  test    bl, 1
0x1802058d8  jz      short loc_1802058E8
0x1802058da  cmp     r12d, [rsi]
0x1802058dd  mov     eax, r12d
0x1802058e0  cmovle  eax, [rsi]
0x1802058e3  add     edx, eax
0x1802058e5  mov     dword ptr [rbp+var_40], edx
0x1802058e8  test    bl, 4
0x1802058eb  jz      short loc_1802058FC
0x1802058ed  mov     eax, [rsi+8]
0x1802058f0  cmp     [rbp+var_38], eax
0x1802058f3  cmovg   eax, [rbp+var_38]
0x1802058f7  add     edx, eax
0x1802058f9  mov     dword ptr [rbp+var_40], edx
0x1802058fc  mov     eax, [rbp+var_28]
0x1802058ff  cmp     ecx, eax
0x180205901  jle     short loc_180205911
0x180205903  mov     ecx, eax
0x180205905  mov     dword ptr [rbp+var_40+4], eax
0x180205908  mov     [rbp+var_28], 0
0x18020590f  jmp     short loc_180205916
0x180205911  sub     eax, ecx
0x180205913  mov     [rbp+var_28], eax
0x180205916  mov     esi, [rbp+var_30]
0x180205919  sub     esi, ecx
0x18020591b  mov     [rbp+var_30], esi
0x18020591e  jns     short loc_180205929
0x180205920  sub     [r14+4], esi
0x180205924  xor     esi, esi
0x180205926  mov     [rbp+var_30], esi
0x180205929  mov     eax, edx
0x18020592b  sub     eax, [rbp+var_34]
0x18020592e  test    eax, eax
0x180205930  jle     loc_1802059BC
0x180205936  add     [r14], eax
0x180205939  mov     [rbp+var_34], edx
0x18020593c  jmp     short loc_1802059BC
0x18020593e  test    bl, 1
0x180205941  jz      short loc_18020594F
0x180205943  mov     eax, [rsi]
0x180205945  cmp     r12d, eax
0x180205948  cmovg   eax, r12d
0x18020594c  add     dword ptr [rbp+var_40], eax
0x18020594f  mov     r12d, [rsi+8]
0x180205953  or      bl, 1
0x180205956  mov     ecx, dword ptr [rbp+var_40+4]
0x180205959  test    bl, 2
0x18020595c  jz      short loc_18020596B
0x18020595e  mov     eax, [rsi+4]
0x180205961  cmp     edi, eax
0x180205963  cmovg   eax, edi
0x180205966  add     ecx, eax
0x180205968  mov     dword ptr [rbp+var_40+4], ecx
0x18020596b  test    bl, 8
0x18020596e  jz      short loc_18020597F
0x180205970  mov     eax, [rsi+0Ch]
0x180205973  cmp     r15d, eax
0x180205976  cmovg   eax, r15d
0x18020597a  add     ecx, eax
0x18020597c  mov     dword ptr [rbp+var_40+4], ecx
0x18020597f  mov     eax, [rbp+var_2C]
0x180205982  cmp     dword ptr [rbp+var_40], eax
0x180205985  jle     short loc_180205993
0x180205987  mov     dword ptr [rbp+var_40], eax
0x18020598a  mov     [rbp+var_2C], 0
0x180205991  jmp     short loc_180205999
0x180205993  sub     eax, dword ptr [rbp+var_40]
0x180205996  mov     [rbp+var_2C], eax
0x180205999  mov     esi, [rbp+var_34]
0x18020599c  sub     esi, dword ptr [rbp+var_40]
0x18020599f  mov     [rbp+var_34], esi
0x1802059a2  jns     short loc_1802059AC
0x1802059a4  sub     [r14], esi
0x1802059a7  xor     esi, esi
0x1802059a9  mov     [rbp+var_34], esi
0x1802059ac  mov     eax, ecx
0x1802059ae  sub     eax, [rbp+var_30]
0x1802059b1  test    eax, eax
0x1802059b3  jle     short loc_1802059BC
0x1802059b5  add     [r14+4], eax
0x1802059b9  mov     [rbp+var_30], ecx
0x1802059bc  mov     rcx, [rbp+var_18]
0x1802059c0  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1802059c6  cmp     [rbp+var_2C], 0
0x1802059ca  jnz     short loc_1802059D6
0x1802059cc  cmp     [rbp+var_28], 0
0x1802059d0  jz      loc_180205B07
0x1802059d6  mov     rcx, [rbp+arg_0]
0x1802059da  mov     esi, dword ptr [rbp+arg_20]
0x1802059dd  mov     edx, [rbp+var_24]
0x1802059e0  mov     r8, [rbp+var_10]
0x1802059e4  inc     edx
0x1802059e6  mov     [rbp+var_24], edx
0x1802059e9  cmp     edx, [rbp+var_20]
0x1802059ec  jb      loc_1802057E0
0x1802059f2  jnz     loc_180205B07
0x1802059f8  mov     rcx, [rcx+28h]
0x1802059fc  mov     sil, bl
0x1802059ff  and     sil, 1
0x180205a03  test    rcx, rcx
0x180205a06  jz      loc_180205AA6
0x180205a0c  mov     rax, [rbp+arg_28]
0x180205a10  lea     rdx, [rbp+var_10]
0x180205a14  mov     r13d, [rbp+arg_18]
0x180205a18  mov     r8d, r13d
0x180205a1b  mov     r9d, dword ptr [rbp+arg_20]
0x180205a1f  mov     [rsp+70h+var_50], rax
0x180205a24  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x180205a2a  lea     rdx, [rbp+var_18]
0x180205a2e  mov     rcx, [rax]
0x180205a31  mov     [rbp+var_40], rcx
0x180205a35  mov     rcx, [rbp+arg_0]
0x180205a39  mov     [rbp+var_18], 0
0x180205a41  mov     rcx, [rcx+28h]
0x180205a45  call    cs:__imp_?GetMargin@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetMargin(DirectUI::Value * *)
0x180205a4b  test    sil, sil
0x180205a4e  mov     esi, dword ptr [rbp+var_40]
0x180205a51  mov     rdx, rax
0x180205a54  jz      short loc_180205A61
0x180205a56  mov     ecx, [rax]
0x180205a58  cmp     r12d, ecx
0x180205a5b  cmovg   ecx, r12d
0x180205a5f  add     esi, ecx
0x180205a61  test    bl, 2
0x180205a64  jz      short loc_180205A75
0x180205a66  mov     eax, [rax+4]
0x180205a69  cmp     edi, eax
0x180205a6b  cmovg   eax, edi
0x180205a6e  mov     edi, dword ptr [rbp+var_40+4]
0x180205a71  add     edi, eax
0x180205a73  jmp     short loc_180205A78
0x180205a75  mov     edi, dword ptr [rbp+var_40+4]
0x180205a78  test    bl, 4
0x180205a7b  jz      short loc_180205A89
0x180205a7d  mov     eax, [rdx+8]
0x180205a80  cmp     [rbp+var_38], eax
0x180205a83  cmovg   eax, [rbp+var_38]
0x180205a87  add     esi, eax
0x180205a89  test    bl, 8
0x180205a8c  jz      short loc_180205A9A
0x180205a8e  mov     eax, [rdx+0Ch]
0x180205a91  cmp     r15d, eax
0x180205a94  cmovg   eax, r15d
0x180205a98  add     edi, eax
0x180205a9a  mov     rcx, [rbp+var_18]
0x180205a9e  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180205aa4  jmp     short loc_180205AF0
0x180205aa6  mov     al, bl
0x180205aa8  and     al, 4
0x180205aaa  test    sil, sil
0x180205aad  jnz     short loc_180205ABC
0x180205aaf  test    al, al
0x180205ab1  jnz     short loc_180205AB7
0x180205ab3  xor     esi, esi
0x180205ab5  jmp     short loc_180205ACF
0x180205ab7  mov     esi, [rbp+var_38]
0x180205aba  jmp     short loc_180205ACF
0x180205abc  test    al, al
0x180205abe  jz      short loc_180205ACC
0x180205ac0  mov     esi, [rbp+var_38]
0x180205ac3  cmp     r12d, esi
0x180205ac6  cmovg   esi, r12d
0x180205aca  jmp     short loc_180205ACF
0x180205acc  mov     esi, r12d
0x180205acf  mov     al, bl
0x180205ad1  and     al, 0Ah
0x180205ad3  jnz     short loc_180205AD9
0x180205ad5  xor     edi, edi
0x180205ad7  jmp     short loc_180205AEC
0x180205ad9  cmp     al, 0Ah
0x180205adb  jnz     short loc_180205AE4
0x180205add  cmp     edi, r15d
0x180205ae0  jg      short loc_180205AEC
0x180205ae2  jmp     short loc_180205AE9
0x180205ae4  test    bl, 2
0x180205ae7  jnz     short loc_180205AEC
0x180205ae9  mov     edi, r15d
0x180205aec  mov     r13d, [rbp+arg_18]
0x180205af0  sub     esi, [rbp+var_34]
  ... truncated ...
```
