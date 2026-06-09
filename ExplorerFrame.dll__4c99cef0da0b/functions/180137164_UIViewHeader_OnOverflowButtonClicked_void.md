# UIViewHeader::_OnOverflowButtonClicked(void)

- ea: `0x180137164`
- end: `0x180137453`
- name: `?_OnOverflowButtonClicked@UIViewHeader@@IEAAXXZ`
- size: `751`
- prototype: `void __fastcall(UIViewHeader *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x18009f780`

## callees

- `0x18009fcf4`
- `0x1800a9ce0`
- `0x1800a9d28`
- `0x1800b7b14`
- `0x1800c1cd4`
- `0x180137164`
- `0x18013745c`
- `0x180137530`
- `0x18013f7d0`
- `0x1801406ec`
- `0x1801f2714`
- `0x180207de0`
- `0x180210010`

## import_xrefs

- `USER32!InsertMenuItemW` at `0x1801372d6`
- `USER32!InsertMenuItemW` at `0x1801372d6`
- `USER32!GetSystemMetrics` at `0x180137385`
- `USER32!GetSystemMetrics` at `0x180137385`
- `USER32!MapWindowPoints` at `0x180137338`
- `USER32!MapWindowPoints` at `0x180137338`
- `USER32!CreatePopupMenu` at `0x18013718e`
- `USER32!CreatePopupMenu` at `0x18013718e`
- `USER32!DestroyMenu` at `0x18013742d`
- `USER32!DestroyMenu` at `0x18013742d`
- `USER32!TrackPopupMenu` at `0x1801373d3`
- `USER32!TrackPopupMenu` at `0x1801373d3`
- `GDI32!DeleteObject` at `0x180137408`
- `GDI32!DeleteObject` at `0x180137416`
- `GDI32!DeleteObject` at `0x180137424`
- `GDI32!DeleteObject` at `0x180137408`
- `GDI32!DeleteObject` at `0x180137416`
- `GDI32!DeleteObject` at `0x180137424`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18013734b`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18013735b`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18013734b`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x18013735b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1801372e5`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1801372e5`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180137233`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180137233`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall UIViewHeader::_OnOverflowButtonClicked(int **this)
{
  HMENU PopupMenu; // rax
  int v3; // edx
  HMENU v4; // r14
  HBITMAP ShellBitmapFromResourceIndex; // rdi
  HBITMAP v6; // r13
  HBITMAP v7; // r12
  int *v8; // rax
  unsigned int v9; // edi
  struct DirectUI::Element *ColumnHeader; // rax
  UIColumnHeader *v11; // rbx
  DirectUI::Value *NameValue; // r15
  int SortDirection; // eax
  HWND v14; // rax
  LONG x; // r15d
  bool IsRTL; // bl
  int SystemMetrics; // eax
  UINT v18; // edx
  BOOL v19; // eax
  UIColumnHeader *v20; // rax
  int y; // [rsp+40h] [rbp-79h]
  LONG ya; // [rsp+40h] [rbp-79h]
  struct tagPOINT v23; // [rsp+48h] [rbp-71h] BYREF
  HWND hWnd; // [rsp+50h] [rbp-69h]
  MENUITEMINFOW mi; // [rsp+60h] [rbp-59h] BYREF
  DirectUI::Value *v26; // [rsp+B0h] [rbp-9h]
  struct tagPOINT Points[2]; // [rsp+B8h] [rbp-1h] BYREF

  PopupMenu = CreatePopupMenu();
  v4 = PopupMenu;
  if ( PopupMenu )
  {
    SHEnableMenuCheckMarkOrBmp(PopupMenu, v3);
    ShellBitmapFromResourceIndex = UIViewHeader::_GetShellBitmapFromResourceIndex((UIViewHeader *)this, 16751);
    v23 = (struct tagPOINT)ShellBitmapFromResourceIndex;
    v6 = UIViewHeader::_GetShellBitmapFromResourceIndex((UIViewHeader *)this, 16749);
    v7 = UIViewHeader::_GetShellBitmapFromResourceIndex((UIViewHeader *)this, 16750);
    v8 = this[28];
    if ( v8 )
    {
      y = *v8;
      v9 = 0;
      if ( *v8 > 0 )
      {
        while ( 1 )
        {
          ColumnHeader = UIViewHeader::GetColumnHeader((UIViewHeader *)this, v9);
          v11 = ColumnHeader;
          if ( ColumnHeader )
          {
            if ( (unsigned int)DUI_IsElementExtentEmpty(ColumnHeader) )
              break;
          }
LABEL_21:
          if ( (int)++v9 >= y )
            goto LABEL_22;
        }
        NameValue = UIColumnHeader::GetNameValue(v11);
        v26 = NameValue;
        hWnd = (HWND)DirectUI::Value::GetString(NameValue);
        if ( !hWnd )
        {
LABEL_19:
          if ( NameValue )
            DirectUI::Value::Release(NameValue);
          goto LABEL_21;
        }
        mi.cbSize = 80;
        memset_0(&mi.fMask, 0, 0x4Cu);
        mi.fMask = 66;
        mi.wID = v9 + 1;
        mi.dwTypeData = (LPWSTR)hWnd;
        if ( *((_DWORD *)v11 + 65) )
        {
          if ( v23 )
          {
            mi.fMask = 194;
            mi.hbmpItem = (HBITMAP)v23;
          }
          goto LABEL_18;
        }
        if ( UIColumnHeader::GetSortedBy(v11) )
        {
          SortDirection = UIColumnHeader::GetSortDirection(v11);
          if ( SortDirection != -1 )
          {
            if ( SortDirection != 1 || !v6 )
              goto LABEL_18;
            mi.hbmpItem = v6;
            goto LABEL_17;
          }
          if ( v7 )
          {
            mi.hbmpItem = v7;
LABEL_17:
            mi.fMask |= 0x80u;
          }
        }
LABEL_18:
        InsertMenuItemW(v4, v9, 1, &mi);
        goto LABEL_19;
      }
LABEL_22:
      ShellBitmapFromResourceIndex = (HBITMAP)v23;
    }
    *(_OWORD *)&Points[0].x = 0;
    DUI_GetRootRelativeBounds(this, 1, Points);
    v14 = (HWND)(*(__int64 (__fastcall **)(int *))(*(_QWORD *)this[26] + 360LL))(this[26]);
    MapWindowPoints(v14, 0, Points, 2u);
    x = Points[1].x;
    ya = Points[0].y;
    if ( DirectUI::Element::IsRTL((DirectUI::Element *)this) )
      x = Points[0].x;
    IsRTL = DirectUI::Element::IsRTL((DirectUI::Element *)this);
    hWnd = (HWND)(*(__int64 (__fastcall **)(int *))(*(_QWORD *)this[26] + 360LL))(this[26]);
    SystemMetrics = GetSystemMetrics(40);
    if ( IsRTL )
      v18 = (SystemMetrics == 0 ? 8 : 0) | 0x8182;
    else
      v18 = SystemMetrics != 0 ? 394 : 386;
    v19 = TrackPopupMenu(v4, v18, x, ya, 0, hWnd, 0);
    if ( v19 )
    {
      v23.x = x;
      v23.y = ya;
      v20 = UIViewHeader::GetColumnHeader((UIViewHeader *)this, v19 - 1);
      if ( v20 )
        UIColumnHeader::DoColumnFilterMenu(v20, &v23);
    }
    if ( ShellBitmapFromResourceIndex )
      DeleteObject(ShellBitmapFromResourceIndex);
    if ( v6 )
      DeleteObject(v6);
    if ( v7 )
      DeleteObject(v7);
    DestroyMenu(v4);
  }
}

```

## disassembly

```asm
0x180137164  push    rbp
0x180137166  push    rbx
0x180137167  push    rsi
0x180137168  push    rdi
0x180137169  push    r12
0x18013716b  push    r13
0x18013716d  push    r14
0x18013716f  push    r15
0x180137171  lea     rbp, [rsp-1Fh]
0x180137176  sub     rsp, 0D8h
0x18013717d  mov     rax, cs:__security_cookie
0x180137184  xor     rax, rsp
0x180137187  mov     [rbp+57h+var_48], rax
0x18013718b  mov     rsi, rcx
0x18013718e  call    cs:__imp_CreatePopupMenu
0x180137194  mov     r14, rax
0x180137197  test    rax, rax
0x18013719a  jz      loc_180137433
0x1801371a0  mov     rcx, rax; HMENU
0x1801371a3  call    ?SHEnableMenuCheckMarkOrBmp@@YAHPEAUHMENU__@@H@Z; SHEnableMenuCheckMarkOrBmp(HMENU__ *,int)
0x1801371a8  mov     edx, 416Fh; int
0x1801371ad  mov     rcx, rsi; this
0x1801371b0  call    ?_GetShellBitmapFromResourceIndex@UIViewHeader@@IEAAPEAUHBITMAP__@@H@Z; UIViewHeader::_GetShellBitmapFromResourceIndex(int)
0x1801371b5  mov     rdi, rax
0x1801371b8  mov     qword ptr [rbp+57h+var_C8.x], rax
0x1801371bc  mov     edx, 416Dh; int
0x1801371c1  mov     rcx, rsi; this
0x1801371c4  call    ?_GetShellBitmapFromResourceIndex@UIViewHeader@@IEAAPEAUHBITMAP__@@H@Z; UIViewHeader::_GetShellBitmapFromResourceIndex(int)
0x1801371c9  mov     r13, rax
0x1801371cc  mov     edx, 416Eh; int
0x1801371d1  mov     rcx, rsi; this
0x1801371d4  call    ?_GetShellBitmapFromResourceIndex@UIViewHeader@@IEAAPEAUHBITMAP__@@H@Z; UIViewHeader::_GetShellBitmapFromResourceIndex(int)
0x1801371d9  mov     r12, rax
0x1801371dc  mov     rax, [rsi+0E0h]
0x1801371e3  test    rax, rax
0x1801371e6  jz      loc_1801372FB
0x1801371ec  mov     eax, [rax]
0x1801371ee  mov     [rbp+57h+y], eax
0x1801371f1  xor     edi, edi
0x1801371f3  test    eax, eax
0x1801371f5  jle     loc_1801372F7
0x1801371fb  mov     edx, edi; unsigned int
0x1801371fd  mov     rcx, rsi; this
0x180137200  call    ?GetColumnHeader@UIViewHeader@@QEAAPEAVUIColumnHeader@@I@Z; UIViewHeader::GetColumnHeader(uint)
0x180137205  mov     rbx, rax
0x180137208  test    rax, rax
0x18013720b  jz      loc_1801372EC
0x180137211  mov     rcx, rax; struct DirectUI::Element *
0x180137214  call    ?DUI_IsElementExtentEmpty@@YAHPEAVElement@DirectUI@@@Z; DUI_IsElementExtentEmpty(DirectUI::Element *)
0x180137219  test    eax, eax
0x18013721b  jz      loc_1801372EC
0x180137221  mov     rcx, rbx; this
0x180137224  call    ?GetNameValue@UIColumnHeader@@QEAAPEAVValue@DirectUI@@XZ; UIColumnHeader::GetNameValue(void)
0x180137229  mov     r15, rax
0x18013722c  mov     [rbp+57h+var_60], rax
0x180137230  mov     rcx, rax
0x180137233  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x180137239  mov     [rbp+57h+var_C0], rax
0x18013723d  test    rax, rax
0x180137240  jz      loc_1801372DD
0x180137246  mov     [rbp+57h+mi.cbSize], 50h ; 'P'
0x18013724d  xor     edx, edx; Val
0x18013724f  lea     r8d, [rdx+4Ch]; Size
0x180137253  lea     rcx, [rbp+57h+mi.fMask]; void *
0x180137257  call    memset_0
0x18013725c  mov     [rbp+57h+mi.fMask], 42h ; 'B'
0x180137263  lea     ecx, [rdi+1]
0x180137266  mov     [rbp+57h+mi.wID], ecx
0x180137269  mov     rax, [rbp+57h+var_C0]
0x18013726d  mov     [rbp+57h+mi.dwTypeData], rax
0x180137271  cmp     dword ptr [rbx+104h], 0
0x180137278  jz      short loc_180137290
0x18013727a  mov     rax, qword ptr [rbp+57h+var_C8.x]
0x18013727e  test    rax, rax
0x180137281  jz      short loc_1801372C7
0x180137283  mov     [rbp+57h+mi.fMask], 0C2h
0x18013728a  mov     [rbp+57h+mi.hbmpItem], rax
0x18013728e  jmp     short loc_1801372C7
0x180137290  mov     rcx, rbx; this
0x180137293  call    ?GetSortedBy@UIColumnHeader@@QEAA_NXZ; UIColumnHeader::GetSortedBy(void)
0x180137298  test    al, al
0x18013729a  jz      short loc_1801372C7
0x18013729c  mov     rcx, rbx; this
0x18013729f  call    ?GetSortDirection@UIColumnHeader@@QEAAHXZ; UIColumnHeader::GetSortDirection(void)
0x1801372a4  cmp     eax, 0FFFFFFFFh
0x1801372a7  jz      short loc_1801372B9
0x1801372a9  cmp     eax, 1
0x1801372ac  jnz     short loc_1801372C7
0x1801372ae  test    r13, r13
0x1801372b1  jz      short loc_1801372C7
0x1801372b3  mov     [rbp+57h+mi.hbmpItem], r13
0x1801372b7  jmp     short loc_1801372C2
0x1801372b9  test    r12, r12
0x1801372bc  jz      short loc_1801372C7
0x1801372be  mov     [rbp+57h+mi.hbmpItem], r12
0x1801372c2  bts     [rbp+57h+mi.fMask], 7
0x1801372c7  lea     r9, [rbp+57h+mi]; lpmi
0x1801372cb  mov     r8d, 1; fByPosition
0x1801372d1  mov     edx, edi; item
0x1801372d3  mov     rcx, r14; hmenu
0x1801372d6  call    cs:__imp_InsertMenuItemW
0x1801372dc  nop
0x1801372dd  test    r15, r15
0x1801372e0  jz      short loc_1801372EC
0x1801372e2  mov     rcx, r15
0x1801372e5  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1801372eb  nop
0x1801372ec  inc     edi
0x1801372ee  cmp     edi, [rbp+57h+y]
0x1801372f1  jl      loc_1801371FB
0x1801372f7  mov     rdi, qword ptr [rbp+57h+var_C8.x]
0x1801372fb  xorps   xmm0, xmm0
0x1801372fe  movups  xmmword ptr [rbp+57h+Points.x], xmm0
0x180137302  lea     r8, [rbp+57h+Points]
0x180137306  mov     edx, 1
0x18013730b  mov     rcx, rsi
0x18013730e  call    ?DUI_GetRootRelativeBounds@@YAJPEAVElement@DirectUI@@W4DUI_COORDINATES_SYSTEM@@PEAUtagRECT@@@Z; DUI_GetRootRelativeBounds(DirectUI::Element *,DUI_COORDINATES_SYSTEM,tagRECT *)
0x180137313  mov     rcx, [rsi+0D0h]
0x18013731a  mov     rax, [rcx]
0x18013731d  mov     rax, [rax+168h]
0x180137324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137329  mov     rcx, rax; hWndFrom
0x18013732c  mov     r9d, 2; cPoints
0x180137332  lea     r8, [rbp+57h+Points]; lpPoints
0x180137336  xor     edx, edx; hWndTo
0x180137338  call    cs:__imp_MapWindowPoints
0x18013733e  mov     r15d, [rbp+57h+Points.x+8]
0x180137342  mov     eax, [rbp+57h+Points.y]
0x180137345  mov     [rbp+57h+y], eax
0x180137348  mov     rcx, rsi
0x18013734b  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x180137351  test    al, al
0x180137353  cmovnz  r15d, [rbp+57h+Points.x]
0x180137358  mov     rcx, rsi
0x18013735b  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x180137361  mov     bl, al
0x180137363  mov     rdx, [rsi+0D0h]
0x18013736a  mov     rcx, [rdx]
0x18013736d  mov     rax, [rcx+168h]
0x180137374  mov     rcx, rdx
0x180137377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013737c  mov     [rbp+57h+var_C0], rax
0x180137380  mov     ecx, 28h ; '('; nIndex
0x180137385  call    cs:__imp_GetSystemMetrics
0x18013738b  test    bl, bl
0x18013738d  jz      short loc_1801373A0
0x18013738f  neg     eax
0x180137391  sbb     edx, edx
0x180137393  not     edx
0x180137395  and     edx, 8
0x180137398  or      edx, 8182h
0x18013739e  jmp     short loc_1801373AD
0x1801373a0  neg     eax
0x1801373a2  sbb     edx, edx
0x1801373a4  and     edx, 8
0x1801373a7  add     edx, 182h; uFlags
0x1801373ad  mov     [rsp+110h+prcRect], 0; prcRect
0x1801373b6  mov     rax, [rbp+57h+var_C0]
0x1801373ba  mov     [rsp+110h+hWnd], rax; hWnd
0x1801373bf  mov     [rsp+110h+nReserved], 0; nReserved
0x1801373c7  mov     ebx, [rbp+57h+y]
0x1801373ca  mov     r9d, ebx; y
0x1801373cd  mov     r8d, r15d; x
0x1801373d0  mov     rcx, r14; hMenu
0x1801373d3  call    cs:__imp_TrackPopupMenu
0x1801373d9  test    eax, eax
0x1801373db  jz      short loc_180137400
0x1801373dd  mov     [rbp+57h+var_C8.x], r15d
0x1801373e1  mov     [rbp+57h+var_C8.y], ebx
0x1801373e4  lea     edx, [rax-1]; unsigned int
0x1801373e7  mov     rcx, rsi; this
0x1801373ea  call    ?GetColumnHeader@UIViewHeader@@QEAAPEAVUIColumnHeader@@I@Z; UIViewHeader::GetColumnHeader(uint)
0x1801373ef  test    rax, rax
0x1801373f2  jz      short loc_180137400
0x1801373f4  lea     rdx, [rbp+57h+var_C8]; struct tagPOINT *
0x1801373f8  mov     rcx, rax; this
0x1801373fb  call    ?DoColumnFilterMenu@UIColumnHeader@@QEAAXPEBUtagPOINT@@@Z; UIColumnHeader::DoColumnFilterMenu(tagPOINT const *)
0x180137400  test    rdi, rdi
0x180137403  jz      short loc_18013740E
0x180137405  mov     rcx, rdi; ho
0x180137408  call    cs:__imp_DeleteObject
0x18013740e  test    r13, r13
0x180137411  jz      short loc_18013741C
0x180137413  mov     rcx, r13; ho
0x180137416  call    cs:__imp_DeleteObject
0x18013741c  test    r12, r12
0x18013741f  jz      short loc_18013742A
0x180137421  mov     rcx, r12; ho
0x180137424  call    cs:__imp_DeleteObject
0x18013742a  mov     rcx, r14; hMenu
0x18013742d  call    cs:__imp_DestroyMenu
0x180137433  mov     rcx, [rbp+57h+var_48]
0x180137437  xor     rcx, rsp; StackCookie
0x18013743a  call    __security_check_cookie
0x18013743f  add     rsp, 0D8h
0x180137446  pop     r15
0x180137448  pop     r14
0x18013744a  pop     r13
0x18013744c  pop     r12
0x18013744e  pop     rdi
0x18013744f  pop     rsi
0x180137450  pop     rbx
0x180137451  pop     rbp
0x180137452  retn
```
