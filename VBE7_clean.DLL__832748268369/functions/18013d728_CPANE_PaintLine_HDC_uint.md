# CPANE::PaintLine(HDC__ *,uint)

- ea: `0x18013d728`
- end: `0x18013e24f`
- name: `?PaintLine@CPANE@@QEAAJPEAUHDC__@@I@Z`
- size: `2855`
- prototype: `__int64 __fastcall(CPANE *__hidden this, HDC, unsigned int)`
- caller_count: `1`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x18013d578`

## callees

- `0x1800e6178`
- `0x1800fa5c4`
- `0x18013bcbc`
- `0x18013d728`
- `0x18013e258`
- `0x18013e474`
- `0x18013e4c0`
- `0x18013e670`
- `0x18013e788`
- `0x18013e7d0`
- `0x18013e82c`
- `0x1801f43a8`
- `0x1801f4420`
- `0x1801f4654`
- `0x1801f4720`
- `0x1801f4838`
- `0x1801f4dcc`
- `0x1801f4e68`
- `0x180202d78`
- `0x1802252c8`
- `0x180246dd0`
- `0x180246e54`
- `0x1802480c4`
- `0x180285e7c`
- `0x180379520`

## import_xrefs

- `USER32!HideCaret` at `0x18013d7ce`
- `USER32!HideCaret` at `0x18013d7ce`
- `USER32!ShowCaret` at `0x18013e22e`
- `USER32!ShowCaret` at `0x18013e22e`
- `GDI32!MoveToEx` at `0x18013db85`
- `GDI32!MoveToEx` at `0x18013ddec`
- `GDI32!MoveToEx` at `0x18013de59`
- `GDI32!MoveToEx` at `0x18013db85`
- `GDI32!MoveToEx` at `0x18013ddec`
- `GDI32!MoveToEx` at `0x18013de59`
- `GDI32!GetCurrentPositionEx` at `0x18013dbe6`
- `GDI32!GetCurrentPositionEx` at `0x18013ddd2`
- `GDI32!GetCurrentPositionEx` at `0x18013de84`
- `GDI32!GetCurrentPositionEx` at `0x18013dbe6`
- `GDI32!GetCurrentPositionEx` at `0x18013ddd2`
- `GDI32!GetCurrentPositionEx` at `0x18013de84`
- `GDI32!SetTextAlign` at `0x18013db03`
- `GDI32!SetTextAlign` at `0x18013de90`
- `GDI32!SetTextAlign` at `0x18013db03`
- `GDI32!SetTextAlign` at `0x18013de90`
- `GDI32!ExtTextOutA` at `0x18013dda6`
- `GDI32!ExtTextOutA` at `0x18013de3d`
- `GDI32!ExtTextOutA` at `0x18013df3b`
- `GDI32!ExtTextOutA` at `0x18013dfd0`
- `GDI32!ExtTextOutA` at `0x18013e075`
- `GDI32!ExtTextOutA` at `0x18013dda6`
- `GDI32!ExtTextOutA` at `0x18013de3d`
- `GDI32!ExtTextOutA` at `0x18013df3b`
- `GDI32!ExtTextOutA` at `0x18013dfd0`
- `GDI32!ExtTextOutA` at `0x18013e075`
- `GDI32!SetBkMode` at `0x18013db12`
- `GDI32!SetBkMode` at `0x18013ddc0`
- `GDI32!SetBkMode` at `0x18013de68`
- `GDI32!SetBkMode` at `0x18013db12`
- `GDI32!SetBkMode` at `0x18013ddc0`
- `GDI32!SetBkMode` at `0x18013de68`
- `GDI32!SelectObject` at `0x18013e1c2`
- `GDI32!SelectObject` at `0x18013e203`
- `GDI32!SelectObject` at `0x18013e1c2`
- `GDI32!SelectObject` at `0x18013e203`
- `GDI32!SetTextColor` at `0x18013dd55`
- `GDI32!SetTextColor` at `0x18013e102`
- `GDI32!SetTextColor` at `0x18013dd55`
- `GDI32!SetTextColor` at `0x18013e102`
- `GDI32!SetBkColor` at `0x18013dd44`
- `GDI32!SetBkColor` at `0x18013dea3`
- `GDI32!SetBkColor` at `0x18013dffa`
- `GDI32!SetBkColor` at `0x18013e111`
- `GDI32!SetBkColor` at `0x18013dd44`
- `GDI32!SetBkColor` at `0x18013dea3`
- `GDI32!SetBkColor` at `0x18013dffa`
- `GDI32!SetBkColor` at `0x18013e111`
- `GDI32!DeleteObject` at `0x18013e211`
- `GDI32!DeleteObject` at `0x18013e211`
- `GDI32!CreateSolidBrush` at `0x18013e1a8`
- `GDI32!CreateSolidBrush` at `0x18013e1a8`

## pseudocode

```c
__int64 __fastcall CPANE::PaintLine(CPANE *this, HDC a2, unsigned int a3)
{
  EBAPP *v3; // rax
  unsigned int v4; // eax
  int v5; // eax
  COLORREF ItemBackColor; // eax
  COLORREF ItemIndicatorColor; // eax
  unsigned int v9; // [rsp+40h] [rbp-1A0h]
  unsigned int j; // [rsp+44h] [rbp-19Ch]
  int i; // [rsp+48h] [rbp-198h]
  int k; // [rsp+4Ch] [rbp-194h]
  unsigned __int8 *v13; // [rsp+50h] [rbp-190h]
  struct tagPOINT pt; // [rsp+58h] [rbp-188h] BYREF
  unsigned int v15; // [rsp+60h] [rbp-180h]
  unsigned int v16; // [rsp+64h] [rbp-17Ch] BYREF
  int SelectionOnLine; // [rsp+68h] [rbp-178h]
  unsigned int v18; // [rsp+6Ch] [rbp-174h]
  unsigned int v19; // [rsp+70h] [rbp-170h] BYREF
  int v20; // [rsp+74h] [rbp-16Ch]
  int v21; // [rsp+78h] [rbp-168h]
  unsigned int v22; // [rsp+7Ch] [rbp-164h] BYREF
  COLORREF color; // [rsp+80h] [rbp-160h]
  struct tagRECT x; // [rsp+88h] [rbp-158h] BYREF
  _DWORD v25[16]; // [rsp+A0h] [rbp-140h] BYREF
  COLORREF v26[16]; // [rsp+E0h] [rbp-100h] BYREF
  COLORREF ItemForeColor; // [rsp+120h] [rbp-C0h]
  LONG v28; // [rsp+124h] [rbp-BCh]
  unsigned int v29; // [rsp+128h] [rbp-B8h]
  unsigned int v30; // [rsp+12Ch] [rbp-B4h] BYREF
  int v31; // [rsp+130h] [rbp-B0h] BYREF
  int y; // [rsp+134h] [rbp-ACh]
  unsigned int v33; // [rsp+138h] [rbp-A8h]
  struct tagPOINT v34; // [rsp+140h] [rbp-A0h] BYREF
  HGDIOBJ v35; // [rsp+148h] [rbp-98h]
  HGDIOBJ h; // [rsp+150h] [rbp-90h]
  __int64 v37; // [rsp+158h] [rbp-88h]
  unsigned __int64 v38; // [rsp+160h] [rbp-80h]
  unsigned __int64 v39; // [rsp+168h] [rbp-78h]
  _QWORD v40[3]; // [rsp+170h] [rbp-70h] BYREF
  int v41; // [rsp+188h] [rbp-58h]
  unsigned __int8 *v42; // [rsp+190h] [rbp-50h]
  int v43; // [rsp+198h] [rbp-48h]
  int v44; // [rsp+19Ch] [rbp-44h]
  int v45; // [rsp+1A0h] [rbp-40h]
  int v46; // [rsp+1A4h] [rbp-3Ch]
  int v47; // [rsp+1A8h] [rbp-38h]
  unsigned int v48; // [rsp+1ACh] [rbp-34h]
  COLORREF *v49; // [rsp+1B0h] [rbp-30h]
  _DWORD *v50; // [rsp+1B8h] [rbp-28h]

  v15 = 0;
  v31 = 0;
  v20 = 0;
  v29 = 0;
  SelectionOnLine = CPANE::SetLdCur(this, a3);
  if ( SelectionOnLine >= 0 )
  {
    if ( *((_DWORD *)this + 33) == a3 && (*((_DWORD *)this + 18) == 1 || (unsigned int)IS_LEVEL3IME()) )
    {
      HideCaret(*((HWND *)this + 35));
      v20 = 1;
    }
    byte_18040057B = 32;
    byte_18040017B = 0;
    v16 = 0;
    v19 = 0;
    v13 = &byte_1803FFD7C;
    if ( *((_DWORD *)this + 18) )
    {
      SelectionOnLine = CPANE::GetSelectionOnLine(this, a3, &v16, &v19, &v31);
      if ( v16 || v19 )
      {
        qmemcpy(*(void **)(*((_QWORD *)this + 33) + 1648LL), &byte_1803FFD7C, 0x3FFu);
        v38 = v19 - v16;
        memset((void *)(*(_QWORD *)(*((_QWORD *)this + 33) + 1648LL) + v16), 1, v38);
        v13 = *(unsigned __int8 **)(*((_QWORD *)this + 33) + 1648LL);
      }
      else if ( (unsigned int)CPANE::GetIMECompositionOnLine(this, a3, &v22, &v30) )
      {
        qmemcpy(*(void **)(*((_QWORD *)this + 33) + 1648LL), &byte_1803FFD7C, 0x3FFu);
        v39 = v30 - v22;
        memset((void *)(*(_QWORD *)(*((_QWORD *)this + 33) + 1648LL) + v22), 12, v39);
        v13 = *(unsigned __int8 **)(*((_QWORD *)this + 33) + 1648LL);
      }
    }
    v15 = dword_1803FF974 & 1;
    if ( (dword_1803FF974 & 1) != 0 && *((_QWORD *)this + 7) == *(_QWORD *)(*((_QWORD *)this + 33) + 1656LL) )
    {
      v33 = *(_DWORD *)(*((_QWORD *)this + 33) + 1664LL);
      v37 = *((_QWORD *)this + 7);
      if ( a3 == LINEMGR::ScrlnOfLogln((LINEMGR *)(v37 + 24), v33) )
        v15 = 0;
    }
    v3 = PebappCur();
    if ( (unsigned int)EBAPP::FIsBiDi(v3) )
    {
      v40[0] = a2;
      v40[1] = *(_QWORD *)(*((_QWORD *)this + 33) + 248LL);
      v40[2] = byte_18040017C;
      v41 = dword_1803FF978;
      v43 = *((_DWORD *)this + 23);
      v42 = v13;
      v44 = CPANE::YFromLn(this, a3);
      v45 = *((_DWORD *)this + 31);
      v46 = *(_DWORD *)(*((_QWORD *)this + 33) + 256LL);
      v47 = *(_DWORD *)(*((_QWORD *)this + 33) + 260LL);
      v48 = v15;
      for ( i = 0; i < 16; ++i )
      {
        v26[i] = GetItemBackColor((unsigned int)i);
        v25[i] = GetItemForeColor((unsigned int)i);
      }
      v49 = v26;
      v50 = v25;
      v29 = BiVBAPaintLineCore((struct _PaintLineBidiInfo *)v40);
    }
    if ( !v29 )
    {
      SetTextAlign(a2, 1u);
      SetBkMode(a2, 2);
      v4 = CPANE::XLeft(this);
      v9 = CPANE::IchFromX(this, a3, v4, 0);
      if ( v9 )
        v9 = DEC_ICH(v9);
      y = CPANE::YFromLn(this, a3);
      v5 = CPANE::XFromIch(this, a3, v9, 0);
      MoveToEx(a2, v5, y, 0);
      if ( *((_DWORD *)this + 36) )
      {
        v18 = 1023;
      }
      else
      {
        if ( (unsigned int)(dword_1803FF978 + 1) <= 0x3FF )
          v21 = dword_1803FF978 + 1;
        else
          v21 = 1023;
        v18 = v21;
      }
      while ( v9 < v18 )
      {
        GetCurrentPositionEx(a2, &pt);
        if ( pt.x >= *((_DWORD *)this + 21) )
          break;
        if ( v13[v9] == 12 )
        {
          for ( j = v9 + 1; j < 0x3FF && v13[j] == 12; ++j )
            ;
          CPANE::PaintIMEComposition(this, a2, v9, j);
        }
        else
        {
          ItemForeColor = GetItemForeColor(v13[v9]);
          color = GetItemBackColor(v13[v9]);
          for ( j = v9 + 1;
                j < v18
             && (v13[j] == v13[v9]
              || (unsigned int)GetItemBackColor(v13[j]) == color
              && (byte_18040017C[j] == 32 || (unsigned int)GetItemForeColor(v13[j]) == ItemForeColor))
             && v13[j] != 12;
                ++j )
          {
            ;
          }
          SetBkColor(a2, color);
          SetTextColor(a2, ItemForeColor);
          ExtTextOutA(a2, 0, 0, 4u, (const RECT *)((char *)this + 92), &byte_18040017C[v9], j - v9, 0);
          if ( v15 )
          {
            SetBkMode(a2, 1);
            GetCurrentPositionEx(a2, &v34);
            MoveToEx(a2, pt.x + 1, pt.y, 0);
            ExtTextOutA(a2, 0, 0, 4u, (const RECT *)((char *)this + 92), &byte_18040017C[v9], j - v9, 0);
            MoveToEx(a2, v34.x, v34.y, 0);
            SetBkMode(a2, 2);
          }
        }
        v9 = j;
      }
    }
    GetCurrentPositionEx(a2, &pt);
    SetTextAlign(a2, 0);
    ItemBackColor = GetItemBackColor(0);
    SetBkColor(a2, ItemBackColor);
    x.top = pt.y;
    x.bottom = *(_DWORD *)(*((_QWORD *)this + 33) + 260LL) + pt.y;
    x.left = *((_DWORD *)this + 19) + CPANE::M_CxMarginWidgetBar(this);
    x.right = CPANE::XLeftEdgeOfText(this);
    ExtTextOutA(a2, x.left, x.top, 2u, &x, 0, 0, 0);
    if ( pt.x < *((_DWORD *)this + 21) )
    {
      if ( pt.x <= *((_DWORD *)this + 23) )
        v28 = *((_DWORD *)this + 23);
      else
        v28 = pt.x;
      x.left = v28;
      x.right = *((_DWORD *)this + 21);
      ExtTextOutA(a2, pt.x, pt.y, 2u, &x, 0, 0, 0);
    }
    byte_18040057B = 0;
    if ( (unsigned int)CPANE::FDrawSeparator(this, a3) )
    {
      SetBkColor(a2, 0x808080u);
      x.left = *((_DWORD *)this + 19) + CPANE::M_CxMarginWidgetBar(this);
      x.right = *((_DWORD *)this + 21);
      x.top = x.bottom - 1;
      ExtTextOutA(a2, x.left, x.bottom - 1, 2u, &x, 0, 0, 0);
    }
    if ( (unsigned int)CPANE::M_FMarginWidgets(this) )
    {
      x.left = *((_DWORD *)this + 19);
      x.right = *((_DWORD *)this + 19) + CPANE::M_CxMarginWidgetBar(this) - 1;
      x.top = CPANE::YFromLn(this, a3);
      x.bottom = *(_DWORD *)(*((_QWORD *)this + 33) + 260LL) + x.top;
      DrawMarginWidgetBarBackground(a2, &x);
      SetTextColor(a2, 0);
      SetBkColor(a2, 0xFFFFFFu);
      ++x.left;
      ++x.top;
      if ( a3 < *((_DWORD *)this + 29) + *((_DWORD *)this + 28) )
      {
        for ( k = 0; k < 4; ++k )
        {
          if ( (unsigned int)CPANE::FMarginWidgetOnLine(this, a3, (unsigned int)k) )
          {
            v35 = 0;
            ItemIndicatorColor = GetItemIndicatorColor(dword_1803F4580[k]);
            h = CreateSolidBrush(ItemIndicatorColor);
            v35 = SelectObject(a2, h);
            BltMarginWidgetHere(*((struct BLTTER **)&g_rgpBltterMarginWidget + k), a2, &x, 1);
            SelectObject(a2, v35);
            DeleteObject(h);
          }
        }
      }
    }
  }
  if ( v20 )
    ShowCaret(*((HWND *)this + 35));
  return (unsigned int)SelectionOnLine;
}

```

## disassembly

```asm
0x18013d728  mov     [rsp-8+arg_10], r8d
0x18013d72d  mov     [rsp-8+hdc], rdx
0x18013d732  mov     [rsp-8+arg_0], rcx
0x18013d737  push    rbp
0x18013d738  mov     rbp, rsp
0x18013d73b  push    rsi
0x18013d73c  push    rdi
0x18013d73d  sub     rsp, 1D0h
0x18013d744  mov     rax, cs:__security_cookie
0x18013d74b  xor     rax, rsp
0x18013d74e  mov     [rbp+var_20], rax
0x18013d752  mov     [rsp+1E0h+var_180], 0
0x18013d75a  mov     [rsp+1E0h+var_B0], 0
0x18013d765  mov     [rsp+1E0h+var_16C], 0
0x18013d76d  mov     [rsp+1E0h+var_178], 0
0x18013d775  mov     [rsp+1E0h+var_B8], 0
0x18013d780  mov     edx, [rbp+arg_10]; unsigned int
0x18013d783  mov     rcx, [rbp+arg_0]; this
0x18013d787  call    ?SetLdCur@CPANE@@QEAAJI@Z; CPANE::SetLdCur(uint)
0x18013d78c  mov     [rsp+1E0h+var_178], eax
0x18013d790  cmp     [rsp+1E0h+var_178], 0
0x18013d795  jge     short loc_18013D7A1
0x18013d797  jmp     loc_18013E21C
0x18013d79c  jmp     loc_18013E21C
0x18013d7a1  mov     rax, [rbp+arg_0]
0x18013d7a5  mov     ecx, [rbp+arg_10]
0x18013d7a8  cmp     [rax+84h], ecx
0x18013d7ae  jnz     short loc_18013D7DC
0x18013d7b0  mov     rax, [rbp+arg_0]
0x18013d7b4  cmp     dword ptr [rax+48h], 1
0x18013d7b8  jz      short loc_18013D7C3
0x18013d7ba  call    IS_LEVEL3IME
0x18013d7bf  test    eax, eax
0x18013d7c1  jz      short loc_18013D7DC
0x18013d7c3  mov     rax, [rbp+arg_0]
0x18013d7c7  mov     rcx, [rax+118h]; hWnd
0x18013d7ce  call    cs:__imp_HideCaret
0x18013d7d4  mov     [rsp+1E0h+var_16C], 1
0x18013d7dc  mov     cs:byte_18040057B, 20h ; ' '
0x18013d7e3  mov     cs:byte_18040017B, 0
0x18013d7ea  mov     [rsp+1E0h+var_17C], 0
0x18013d7f2  mov     [rsp+1E0h+var_170], 0
0x18013d7fa  lea     rax, byte_1803FFD7C
0x18013d801  mov     [rsp+1E0h+var_190], rax
0x18013d806  mov     rax, [rbp+arg_0]
0x18013d80a  cmp     dword ptr [rax+48h], 0
0x18013d80e  jz      loc_18013D95A
0x18013d814  lea     rax, [rsp+1E0h+var_B0]
0x18013d81c  mov     [rsp+1E0h+lprect], rax; int *
0x18013d821  lea     r9, [rsp+1E0h+var_170]; unsigned int *
0x18013d826  lea     r8, [rsp+1E0h+var_17C]; unsigned int *
0x18013d82b  mov     edx, [rbp+arg_10]; unsigned int
0x18013d82e  mov     rcx, [rbp+arg_0]; this
0x18013d832  call    ?GetSelectionOnLine@CPANE@@QEAAJIPEAI0PEAH@Z; CPANE::GetSelectionOnLine(uint,uint *,uint *,int *)
0x18013d837  mov     [rsp+1E0h+var_178], eax
0x18013d83b  cmp     [rsp+1E0h+var_17C], 0
0x18013d840  jnz     short loc_18013D849
0x18013d842  cmp     [rsp+1E0h+var_170], 0
0x18013d847  jz      short loc_18013D8C4
0x18013d849  mov     rax, [rbp+arg_0]
0x18013d84d  mov     rax, [rax+108h]
0x18013d854  mov     rax, [rax+670h]
0x18013d85b  lea     rcx, byte_1803FFD7C
0x18013d862  mov     rdi, rax
0x18013d865  mov     rsi, rcx
0x18013d868  mov     ecx, 3FFh
0x18013d86d  rep movsb
0x18013d86f  mov     eax, [rsp+1E0h+var_17C]
0x18013d873  mov     ecx, [rsp+1E0h+var_170]
0x18013d877  sub     ecx, eax
0x18013d879  mov     eax, ecx
0x18013d87b  mov     eax, eax
0x18013d87d  mov     [rbp+var_80], rax
0x18013d881  mov     rcx, [rbp+arg_0]
0x18013d885  mov     rcx, [rcx+108h]
0x18013d88c  mov     edx, [rsp+1E0h+var_17C]
0x18013d890  add     rdx, [rcx+670h]
0x18013d897  mov     rcx, rdx
0x18013d89a  mov     rdi, rcx
0x18013d89d  mov     eax, 1
0x18013d8a2  mov     rcx, [rbp+var_80]
0x18013d8a6  rep stosb
0x18013d8a8  mov     rax, [rbp+arg_0]
0x18013d8ac  mov     rax, [rax+108h]
0x18013d8b3  mov     rax, [rax+670h]
0x18013d8ba  mov     [rsp+1E0h+var_190], rax
0x18013d8bf  jmp     loc_18013D95A
0x18013d8c4  lea     r9, [rsp+1E0h+var_B4]; unsigned int *
0x18013d8cc  lea     r8, [rsp+1E0h+var_164]; unsigned int *
0x18013d8d1  mov     edx, [rbp+arg_10]; unsigned int
0x18013d8d4  mov     rcx, [rbp+arg_0]; this
0x18013d8d8  call    ?GetIMECompositionOnLine@CPANE@@QEAAHIPEAI0@Z; CPANE::GetIMECompositionOnLine(uint,uint *,uint *)
0x18013d8dd  test    eax, eax
0x18013d8df  jz      short loc_18013D95A
0x18013d8e1  mov     rax, [rbp+arg_0]
0x18013d8e5  mov     rax, [rax+108h]
0x18013d8ec  mov     rax, [rax+670h]
0x18013d8f3  lea     rcx, byte_1803FFD7C
0x18013d8fa  mov     rdi, rax
0x18013d8fd  mov     rsi, rcx
0x18013d900  mov     ecx, 3FFh
0x18013d905  rep movsb
0x18013d907  mov     eax, [rsp+1E0h+var_164]
0x18013d90b  mov     ecx, [rsp+1E0h+var_B4]
0x18013d912  sub     ecx, eax
0x18013d914  mov     eax, ecx
0x18013d916  mov     eax, eax
0x18013d918  mov     [rbp+var_78], rax
0x18013d91c  mov     rcx, [rbp+arg_0]
0x18013d920  mov     rcx, [rcx+108h]
0x18013d927  mov     edx, [rsp+1E0h+var_164]
0x18013d92b  add     rdx, [rcx+670h]
0x18013d932  mov     rcx, rdx
0x18013d935  mov     rdi, rcx
0x18013d938  mov     eax, 0Ch
0x18013d93d  mov     rcx, [rbp+var_78]
0x18013d941  rep stosb
0x18013d943  mov     rax, [rbp+arg_0]
0x18013d947  mov     rax, [rax+108h]
0x18013d94e  mov     rax, [rax+670h]
0x18013d955  mov     [rsp+1E0h+var_190], rax
0x18013d95a  mov     eax, cs:dword_1803FF974
0x18013d960  and     eax, 1
0x18013d963  mov     [rsp+1E0h+var_180], eax
0x18013d967  cmp     [rsp+1E0h+var_180], 0
0x18013d96c  jz      short loc_18013D9DA
0x18013d96e  mov     rax, [rbp+arg_0]
0x18013d972  mov     rax, [rax+108h]
0x18013d979  mov     rcx, [rbp+arg_0]
0x18013d97d  mov     rax, [rax+678h]
0x18013d984  cmp     [rcx+38h], rax
0x18013d988  jnz     short loc_18013D9DA
0x18013d98a  mov     rax, [rbp+arg_0]
0x18013d98e  mov     rax, [rax+108h]
0x18013d995  mov     eax, [rax+680h]
0x18013d99b  mov     [rsp+1E0h+var_A8], eax
0x18013d9a2  mov     rax, [rbp+arg_0]
0x18013d9a6  mov     rax, [rax+38h]
0x18013d9aa  mov     [rsp+1E0h+var_88], rax
0x18013d9b2  mov     rax, [rsp+1E0h+var_88]
0x18013d9ba  add     rax, 18h
0x18013d9be  mov     edx, [rsp+1E0h+var_A8]; unsigned int
0x18013d9c5  mov     rcx, rax; this
0x18013d9c8  call    ?ScrlnOfLogln@LINEMGR@@QEBAII@Z; LINEMGR::ScrlnOfLogln(uint)
0x18013d9cd  cmp     [rbp+arg_10], eax
0x18013d9d0  jnz     short loc_18013D9DA
0x18013d9d2  mov     [rsp+1E0h+var_180], 0
0x18013d9da  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18013d9df  mov     rcx, rax; this
0x18013d9e2  call    ?FIsBiDi@EBAPP@@QEAAHXZ; EBAPP::FIsBiDi(void)
0x18013d9e7  test    eax, eax
0x18013d9e9  jz      loc_18013DAEC
0x18013d9ef  mov     rax, [rbp+hdc]
0x18013d9f3  mov     [rbp+var_70], rax
0x18013d9f7  mov     rax, [rbp+arg_0]
0x18013d9fb  mov     rax, [rax+108h]
0x18013da02  mov     rax, [rax+0F8h]
0x18013da09  mov     [rbp+var_68], rax
0x18013da0d  lea     rax, byte_18040017C
0x18013da14  mov     [rbp+var_60], rax
0x18013da18  mov     eax, cs:dword_1803FF978
0x18013da1e  mov     [rbp+var_58], eax
0x18013da21  mov     rax, [rbp+arg_0]
0x18013da25  mov     eax, [rax+5Ch]
0x18013da28  mov     [rbp+var_48], eax
0x18013da2b  mov     rax, [rsp+1E0h+var_190]
0x18013da30  mov     [rbp+var_50], rax
0x18013da34  mov     edx, [rbp+arg_10]; unsigned int
0x18013da37  mov     rcx, [rbp+arg_0]; this
0x18013da3b  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x18013da40  mov     [rbp+var_44], eax
0x18013da43  mov     rax, [rbp+arg_0]
0x18013da47  mov     eax, [rax+7Ch]
0x18013da4a  mov     [rbp+var_40], eax
0x18013da4d  mov     rax, [rbp+arg_0]
0x18013da51  mov     rax, [rax+108h]
0x18013da58  mov     eax, [rax+100h]
0x18013da5e  mov     [rbp+var_3C], eax
0x18013da61  mov     rax, [rbp+arg_0]
0x18013da65  mov     rax, [rax+108h]
0x18013da6c  mov     eax, [rax+104h]
0x18013da72  mov     [rbp+var_38], eax
0x18013da75  mov     eax, [rsp+1E0h+var_180]
0x18013da79  mov     [rbp+var_34], eax
0x18013da7c  mov     [rsp+1E0h+var_198], 0
0x18013da84  jmp     short loc_18013DA90
0x18013da86  mov     eax, [rsp+1E0h+var_198]
0x18013da8a  inc     eax
0x18013da8c  mov     [rsp+1E0h+var_198], eax
0x18013da90  cmp     [rsp+1E0h+var_198], 10h
0x18013da95  jge     short loc_18013DAC3
0x18013da97  mov     ecx, [rsp+1E0h+var_198]
0x18013da9b  call    GetItemBackColor
0x18013daa0  movsxd  rcx, [rsp+1E0h+var_198]
0x18013daa5  mov     [rsp+rcx*4+1E0h+var_100], eax
0x18013daac  mov     ecx, [rsp+1E0h+var_198]
0x18013dab0  call    GetItemForeColor
0x18013dab5  movsxd  rcx, [rsp+1E0h+var_198]
0x18013daba  mov     [rsp+rcx*4+1E0h+var_140], eax
0x18013dac1  jmp     short loc_18013DA86
0x18013dac3  lea     rax, [rsp+1E0h+var_100]
0x18013dacb  mov     [rbp+var_30], rax
0x18013dacf  lea     rax, [rsp+1E0h+var_140]
0x18013dad7  mov     [rbp+var_28], rax
0x18013dadb  lea     rcx, [rbp+var_70]
0x18013dadf  call    cs:?BiVBAPaintLineCore@@3P6AIPEAU_PaintLineBidiInfo@@@ZEA; uint (*BiVBAPaintLineCore)(_PaintLineBidiInfo *)
0x18013dae5  mov     [rsp+1E0h+var_B8], eax
0x18013daec  cmp     [rsp+1E0h+var_B8], 0
0x18013daf4  jnz     loc_18013DE7B
0x18013dafa  mov     edx, 1; align
0x18013daff  mov     rcx, [rbp+hdc]; hdc
0x18013db03  call    cs:__imp_SetTextAlign
0x18013db09  mov     edx, 2; mode
0x18013db0e  mov     rcx, [rbp+hdc]; hdc
0x18013db12  call    cs:__imp_SetBkMode
0x18013db18  mov     rcx, [rbp+arg_0]; this
0x18013db1c  call    ?XLeft@CPANE@@QEAAHXZ; CPANE::XLeft(void)
0x18013db21  xor     r9d, r9d
0x18013db24  mov     r8d, eax
0x18013db27  mov     edx, [rbp+arg_10]
0x18013db2a  mov     rcx, [rbp+arg_0]
0x18013db2e  call    ?IchFromX@CPANE@@QEAAIIJW4SPACE_MODE@@@Z; CPANE::IchFromX(uint,long,SPACE_MODE)
0x18013db33  mov     [rsp+1E0h+var_1A0], eax
0x18013db37  cmp     [rsp+1E0h+var_1A0], 0
0x18013db3c  jbe     short loc_18013DB4B
0x18013db3e  mov     ecx, [rsp+1E0h+var_1A0]; unsigned int
0x18013db42  call    ?DEC_ICH@@YAII@Z; DEC_ICH(uint)
0x18013db47  mov     [rsp+1E0h+var_1A0], eax
0x18013db4b  mov     edx, [rbp+arg_10]; unsigned int
0x18013db4e  mov     rcx, [rbp+arg_0]; this
0x18013db52  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x18013db57  mov     [rsp+1E0h+y], eax
0x18013db5e  xor     r9d, r9d
0x18013db61  mov     r8d, [rsp+1E0h+var_1A0]
0x18013db66  mov     edx, [rbp+arg_10]
0x18013db69  mov     rcx, [rbp+arg_0]
0x18013db6d  call    ?XFromIch@CPANE@@QEAAHIIW4SPACE_MODE@@@Z; CPANE::XFromIch(uint,uint,SPACE_MODE)
0x18013db72  xor     r9d, r9d; lppt
0x18013db75  mov     ecx, [rsp+1E0h+y]
0x18013db7c  mov     r8d, ecx; y
0x18013db7f  mov     edx, eax; x
0x18013db81  mov     rcx, [rbp+hdc]; hdc
0x18013db85  call    cs:__imp_MoveToEx
0x18013db8b  mov     rax, [rbp+arg_0]
0x18013db8f  cmp     dword ptr [rax+90h], 0
0x18013db96  jz      short loc_18013DBA2
0x18013db98  mov     [rsp+1E0h+var_174], 3FFh
0x18013dba0  jmp     short loc_18013DBCF
0x18013dba2  mov     eax, cs:dword_1803FF978
0x18013dba8  inc     eax
0x18013dbaa  cmp     eax, 3FFh
0x18013dbaf  jbe     short loc_18013DBBB
0x18013dbb1  mov     [rsp+1E0h+var_168], 3FFh
0x18013dbb9  jmp     short loc_18013DBC7
0x18013dbbb  mov     eax, cs:dword_1803FF978
0x18013dbc1  inc     eax
0x18013dbc3  mov     [rsp+1E0h+var_168], eax
0x18013dbc7  mov     eax, [rsp+1E0h+var_168]
0x18013dbcb  mov     [rsp+1E0h+var_174], eax
0x18013dbcf  mov     eax, [rsp+1E0h+var_174]
0x18013dbd3  cmp     [rsp+1E0h+var_1A0], eax
0x18013dbd7  jnb     loc_18013DE7B
0x18013dbdd  lea     rdx, [rsp+1E0h+pt]; lppt
0x18013dbe2  mov     rcx, [rbp+hdc]; hdc
0x18013dbe6  call    cs:__imp_GetCurrentPositionEx
0x18013dbec  mov     rax, [rbp+arg_0]
0x18013dbf0  mov     eax, [rax+54h]
0x18013dbf3  cmp     [rsp+1E0h+pt.x], eax
0x18013dbf7  jl      short loc_18013DBFE
0x18013dbf9  jmp     loc_18013DE7B
0x18013dbfe  mov     eax, [rsp+1E0h+var_1A0]
0x18013dc02  mov     rcx, [rsp+1E0h+var_190]
0x18013dc07  movzx   eax, byte ptr [rcx+rax]
0x18013dc0b  cmp     eax, 0Ch
0x18013dc0e  jnz     short loc_18013DC5E
0x18013dc10  mov     eax, [rsp+1E0h+var_1A0]
0x18013dc14  inc     eax
0x18013dc16  mov     [rsp+1E0h+var_19C], eax
0x18013dc1a  cmp     [rsp+1E0h+var_19C], 3FFh
0x18013dc22  jnb     short loc_18013DC42
0x18013dc24  mov     eax, [rsp+1E0h+var_19C]
0x18013dc28  mov     rcx, [rsp+1E0h+var_190]
0x18013dc2d  movzx   eax, byte ptr [rcx+rax]
0x18013dc31  cmp     eax, 0Ch
0x18013dc34  jnz     short loc_18013DC42
0x18013dc36  mov     eax, [rsp+1E0h+var_19C]
0x18013dc3a  inc     eax
0x18013dc3c  mov     [rsp+1E0h+var_19C], eax
0x18013dc40  jmp     short loc_18013DC1A
0x18013dc42  mov     r9d, [rsp+1E0h+var_19C]; unsigned int
0x18013dc47  mov     r8d, [rsp+1E0h+var_1A0]; unsigned int
0x18013dc4c  mov     rdx, [rbp+hdc]; HDC
0x18013dc50  mov     rcx, [rbp+arg_0]; this
0x18013dc54  call    ?PaintIMEComposition@CPANE@@QEAAXPEAUHDC__@@II@Z; CPANE::PaintIMEComposition(HDC__ *,uint,uint)
0x18013dc59  jmp     loc_18013DE6E
0x18013dc5e  mov     eax, [rsp+1E0h+var_1A0]
0x18013dc62  mov     rcx, [rsp+1E0h+var_190]
0x18013dc67  movzx   eax, byte ptr [rcx+rax]
0x18013dc6b  mov     ecx, eax
0x18013dc6d  call    GetItemForeColor
  ... truncated ...
```
