# CNscTree::_OnCDNotify(tagNMCUSTOMDRAWINFO *)

- ea: `0x1800996f4`
- end: `0x180099e3f`
- name: `?_OnCDNotify@CNscTree@@AEAA_JPEAUtagNMCUSTOMDRAWINFO@@@Z`
- size: `1867`
- prototype: `__int64 __fastcall(CNscTree *__hidden this, struct tagNMCUSTOMDRAWINFO *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18003d858`

## callees

- `0x18002c6b0`
- `0x180047410`
- `0x180098e10`
- `0x180099660`
- `0x1800996f4`
- `0x180099fe4`
- `0x18009b8f8`
- `0x1800da674`
- `0x1800f552c`
- `0x18013f7d0`
- `0x1801406ec`
- `0x1801b8d3c`
- `0x1802086a0`
- `0x180210010`

## import_xrefs

- `USER32!SendMessageW` at `0x1800997ed`
- `USER32!SendMessageW` at `0x18009984d`
- `USER32!SendMessageW` at `0x18009986f`
- `USER32!SendMessageW` at `0x180099aa8`
- `USER32!SendMessageW` at `0x180099b0d`
- `USER32!SendMessageW` at `0x180099c2a`
- `USER32!SendMessageW` at `0x1800997ed`
- `USER32!SendMessageW` at `0x18009984d`
- `USER32!SendMessageW` at `0x18009986f`
- `USER32!SendMessageW` at `0x180099aa8`
- `USER32!SendMessageW` at `0x180099b0d`
- `USER32!SendMessageW` at `0x180099c2a`
- `USER32!GetSysColor` at `0x180099b6b`
- `USER32!GetSysColor` at `0x180099b87`
- `USER32!GetSysColor` at `0x180099cb0`
- `USER32!GetSysColor` at `0x180099cc0`
- `USER32!GetSysColor` at `0x180099cce`
- `USER32!GetSysColor` at `0x180099d75`
- `USER32!GetSysColor` at `0x180099d83`
- `USER32!GetSysColor` at `0x180099b6b`
- `USER32!GetSysColor` at `0x180099b87`
- `USER32!GetSysColor` at `0x180099cb0`
- `USER32!GetSysColor` at `0x180099cc0`
- `USER32!GetSysColor` at `0x180099cce`
- `USER32!GetSysColor` at `0x180099d75`
- `USER32!GetSysColor` at `0x180099d83`
- `USER32!IsRectEmpty` at `0x180099bcc`
- `USER32!IsRectEmpty` at `0x180099bcc`
- `GDI32!DeleteObject` at `0x180099a67`
- `GDI32!DeleteObject` at `0x180099a67`
- `GDI32!SelectObject` at `0x180099a5e`
- `GDI32!SelectObject` at `0x180099b59`
- `GDI32!SelectObject` at `0x180099a5e`
- `GDI32!SelectObject` at `0x180099b59`
- `GDI32!CreateFontIndirectW` at `0x180099b48`
- `GDI32!CreateFontIndirectW` at `0x180099b48`
- `GDI32!GetObjectW` at `0x180099b34`
- `GDI32!GetObjectW` at `0x180099b34`

## pseudocode

```c
__int64 __fastcall CNscTree::_OnCDNotify(CNscTree *this, struct tagNMCUSTOMDRAWINFO *a2, __int64 a3)
{
  HDC hdc; // r14
  DWORD dwDrawStage; // eax
  struct _TREEITEM *dwItemSpec; // r12
  __int64 v8; // rcx
  DWORD v9; // eax
  DWORD v10; // eax
  HWND v11; // rcx
  int v12; // eax
  HWND v13; // rcx
  LRESULT v14; // rax
  HWND v15; // rcx
  int v16; // eax
  RECT *p_rc; // r8
  __int64 *v18; // rax
  __int64 v19; // r10
  int v20; // edx
  CNscTree *v21; // rcx
  __int64 v22; // r8
  struct NSCITEMINFO *TreeItemInfo; // rax
  int v25; // ecx
  char v26; // al
  int v27; // edx
  void *v28; // rdx
  HGDIOBJ v29; // rax
  HWND v30; // rcx
  struct _TREEITEM *v31; // rax
  __int64 v32; // rcx
  char v33; // al
  void *v34; // rbx
  HFONT v35; // rax
  DWORD SysColor; // eax
  HWND v37; // rcx
  LPARAM lItemlParam; // rax
  int v39; // ebx
  unsigned int v40; // ecx
  DWORD hwndFrom; // r13d
  int v42; // ebx
  DWORD hwndFrom_high; // r15d
  UINT uItemState; // ecx
  int v45; // edx
  __int64 v46; // r9
  struct _TREEITEM **v47; // r14
  unsigned int v48; // ecx
  struct IShellItem **v49; // [rsp+20h] [rbp-E0h]
  __int64 v50; // [rsp+50h] [rbp-B0h] BYREF
  struct IShellItem *v51; // [rsp+58h] [rbp-A8h] BYREF
  LPARAM v52[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v53; // [rsp+70h] [rbp-90h]
  _QWORD v54[5]; // [rsp+78h] [rbp-88h] BYREF
  LOGFONTW lParam; // [rsp+A0h] [rbp-60h] BYREF
  struct IShellItem *v56[2]; // [rsp+100h] [rbp+0h] BYREF
  HDC v57; // [rsp+110h] [rbp+10h]
  unsigned __int16 v58[2088]; // [rsp+120h] [rbp+20h] BYREF

  hdc = a2->hdc;
  dwDrawStage = a2->dwDrawStage;
  dwItemSpec = (struct _TREEITEM *)a2->dwItemSpec;
  v50 = 0;
  v57 = hdc;
  if ( dwDrawStage == 1 )
  {
    if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    {
      v49 = v56;
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Shell_Core_Provider_Context,
        ShellTraceId_NamespaceControl_Rendering_Start,
        a3,
        1);
      dwDrawStage = a2->dwDrawStage;
    }
    else
    {
      dwDrawStage = 1;
    }
  }
  v8 = *((_QWORD *)this + 71);
  if ( v8 )
  {
    v9 = dwDrawStage - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 - 0xFFFF <= 1 )
        {
          v51 = 0;
          if ( (int)CNscTree::_ShellItemForTreeItem((HWND *)this, 0, dwItemSpec, &v51) >= 0 )
          {
            memset_0(&lParam, 0, 0x50u);
            v11 = (HWND)*((_QWORD *)this + 50);
            *(_QWORD *)&lParam.lfOutPrecision = v58;
            lParam.lfHeight = 539;
            *(_DWORD *)&lParam.lfItalic = 61480;
            *(_DWORD *)&lParam.lfFaceName[2] = 2084;
            *(_QWORD *)&lParam.lfEscapement = dwItemSpec;
            if ( (unsigned int)SendMessageW(v11, 0x113Eu, 0, (LPARAM)&lParam) )
            {
              v52[0] = (LPARAM)v51;
              LODWORD(v52[1]) = a2->uItemState;
              v53 = (__int64)v58;
              memset((char *)v54 + 4, 0, 20);
              if ( (lParam.lfWeight & 0x20) != 0 )
              {
                v12 = *(_DWORD *)&lParam.lfFaceName[22];
                HIDWORD(v52[1]) = 2;
              }
              else
              {
                v12 = *(_DWORD *)&lParam.lfFaceName[4];
                HIDWORD(v52[1]) = 0;
              }
              v13 = (HWND)*((_QWORD *)this + 50);
              LODWORD(v54[0]) = v12;
              v14 = SendMessageW(v13, 0x1108u, 0, 0);
              v15 = (HWND)*((_QWORD *)this + 50);
              v54[1] = v14;
              LODWORD(v54[2]) = a2[1].hdr.idFrom;
              v16 = SendMessageW(v15, 0x1106u, 0, 0);
              p_rc = &a2->rc;
              HIDWORD(v54[2]) = v16;
              v18 = (__int64 *)*((_QWORD *)this + 71);
              v19 = *v18;
              if ( a2->dwDrawStage == 65537 )
              {
                (*(void (__fastcall **)(__int64 *, HDC, RECT *, LPARAM *, struct tagNMCUSTOMDRAWINFO *, char *, __int64 *))(v19 + 40))(
                  v18,
                  hdc,
                  p_rc,
                  v52,
                  a2 + 1,
                  (char *)&a2[1].hdr.hwndFrom + 4,
                  &v50);
                v25 = v52[1];
                v26 = v52[1] & 0x11;
                a2->uItemState = v52[1];
                if ( v26 == 17 )
                  a2->uItemState = v25 | 0x41;
              }
              else
              {
                (*(void (__fastcall **)(_QWORD, HDC, RECT *, LPARAM *, struct IShellItem **))(v19 + 48))(
                  *((_QWORD *)this + 71),
                  hdc,
                  p_rc,
                  v52,
                  v49);
              }
            }
            ((void (__fastcall *)(struct IShellItem *))v51->lpVtbl->Release)(v51);
          }
        }
      }
      else
      {
        (*(void (__fastcall **)(__int64, HDC, RECT *))(*(_QWORD *)v8 + 32LL))(v8, hdc, &a2->rc);
      }
    }
    else
    {
      (*(void (__fastcall **)(__int64, HDC, RECT *, __int64 *, struct IShellItem **))(*(_QWORD *)v8 + 24LL))(
        v8,
        hdc,
        &a2->rc,
        &v50,
        v49);
    }
  }
  if ( a2->dwDrawStage == 1 )
    v50 |= 0x10uLL;
  if ( (unsigned int)CNscTree::_SupportsCustomNode(this) )
  {
    v27 = v20 - 65537;
    if ( v27 )
    {
      if ( v27 == 1 )
      {
        v28 = (void *)*((_QWORD *)this + 94);
        if ( v28 )
        {
          v29 = SelectObject(hdc, v28);
          DeleteObject(v29);
          *((_QWORD *)this + 94) = 0;
        }
      }
    }
    else if ( !CNscTree::_GetTreeItemIDList(v21, *((HWND *)this + 50), dwItemSpec) )
    {
      v30 = (HWND)*((_QWORD *)this + 50);
      v56[0] = 0;
      v31 = (struct _TREEITEM *)SendMessageW(v30, 0x110Au, 3u, (LPARAM)dwItemSpec);
      if ( (int)CNscTree::_ShellItemForTreeItem((HWND *)this, 0, v31, v56) >= 0 )
      {
        v32 = *((_QWORD *)this + 72);
        LODWORD(v51) = 0;
        if ( (*(int (__fastcall **)(__int64, struct IShellItem *, struct IShellItem **))(*(_QWORD *)v32 + 32LL))(
               v32,
               v56[0],
               &v51) >= 0 )
        {
          v33 = (char)v51;
          if ( ((unsigned __int8)v51 & 2) != 0 )
          {
            v34 = (void *)SendMessageW(*((HWND *)this + 50), 0x31u, 0, 0);
            memset_0(&lParam, 0, sizeof(lParam));
            GetObjectW(v34, 92, &lParam);
            lParam.lfUnderline = 1;
            v35 = CreateFontIndirectW(&lParam);
            if ( v35 )
              *((_QWORD *)this + 94) = SelectObject(hdc, v35);
            SysColor = GetSysColor(26);
            v50 |= 2uLL;
            LODWORD(a2[1].hdr.hwndFrom) = SysColor;
            v33 = (char)v51;
          }
          if ( (v33 & 4) != 0 )
            LODWORD(a2[1].hdr.hwndFrom) = GetSysColor(17);
        }
        ((void (__fastcall *)(struct IShellItem *))v56[0]->lpVtbl->Release)(v56[0]);
      }
    }
  }
  if ( (*((_DWORD *)this + 113) & 0xE0000000) != 0 && (v50 & 4) == 0 )
  {
    if ( a2->dwDrawStage == 1 )
    {
      v50 |= 0x20uLL;
    }
    else if ( a2->dwDrawStage == 65537 && !IsRectEmpty(&a2->rc) )
    {
      v37 = (HWND)*((_QWORD *)this + 50);
      v53 = 0xF02800000000LL;
      memset(&v54[1], 0, 24);
      v54[0] = v58;
      v52[0] = 25;
      LODWORD(v54[1]) = 2084;
      v52[1] = (LPARAM)dwItemSpec;
      if ( (unsigned int)SendMessageW(v37, 0x113Eu, 0, (LPARAM)v52) )
      {
        lItemlParam = a2->lItemlParam;
        v39 = 0;
        if ( lItemlParam && (*(_BYTE *)(lItemlParam + 12) & 1) == 0 )
          v39 = 0x2000;
        v40 = (*((_DWORD *)this + 110) & 0x40 | 0x20u) >> 5;
        if ( v52[1] == *((_QWORD *)this + 88) )
          v58[0] = 0;
        hwndFrom = (DWORD)a2[1].hdr.hwndFrom;
        v42 = v40 | v39;
        if ( (v53 & 0x20) != 0 )
          v42 |= 0x1000u;
        if ( (a2->uItemState & 1) != 0 || (v53 & 8) != 0 )
        {
          if ( (*((_DWORD *)this + 116) & 0x8000) != 0 || (v53 & 8) != 0 )
          {
            hwndFrom_high = GetSysColor(13);
            hwndFrom = GetSysColor(14);
          }
          else
          {
            hwndFrom_high = GetSysColor(15);
          }
        }
        else
        {
          hwndFrom_high = HIDWORD(a2[1].hdr.hwndFrom);
        }
        uItemState = a2->uItemState;
        if ( (uItemState & 0x40) != 0 )
        {
          v45 = *((_DWORD *)this + 113);
          if ( (v45 & 0xE0000000) != 0 )
          {
            if ( (v42 & 0x2000) != 0 || (v45 & 0x40000000) == 0 )
            {
              v46 = 0;
              if ( (v42 & 0x2000) == 0 && v45 < 0 )
                v46 = 2;
            }
            else
            {
              v46 = 1;
            }
            *(RECT *)v56 = a2->rc;
            CNscTree::_ShowFloater(this, v56, dwItemSpec, v46);
          }
          v47 = (struct _TREEITEM **)((char *)this + 848);
        }
        else
        {
          v47 = (struct _TREEITEM **)((char *)this + 848);
          if ( dwItemSpec == *((struct _TREEITEM **)this + 106) )
          {
            if ( (*((_DWORD *)this + 116) & 0x4000000) != 0 )
              a2->uItemState = uItemState | 0x40;
            else
              CNscTree::_HideFloater(this, 0);
          }
        }
        if ( (a2->uItemState & 0x40) != 0 )
        {
          v42 |= 4u;
          if ( (*((_DWORD *)this + 116) & 0x20000000) == 0 )
          {
            hwndFrom = GetSysColor(13);
            hwndFrom_high = GetSysColor(15);
          }
          *v47 = dwItemSpec;
        }
        hdc = v57;
        v48 = v42 | 0x200;
        if ( (v53 & 1) == 0 )
          v48 = v42;
        CNscTree::_DrawItem(this, dwItemSpec, v58, v57, &a2->rc, v48, a2[1].hdr.idFrom, hwndFrom_high, hwndFrom);
        v50 = 4;
      }
    }
  }
  if ( (*((_BYTE *)this + 460) & 0x20) != 0 && (*((_BYTE *)this + 456) & 8) != 0 )
  {
    switch ( a2->dwDrawStage )
    {
      case 1u:
        v50 |= 0x20uLL;
        break;
      case 0x10001u:
        v50 |= 0x10uLL;
        break;
      case 0x10002u:
        TreeItemInfo = CNscTree::_GetTreeItemInfo(
                         (CNscTree *)(a2->dwDrawStage - 65537),
                         *((HWND *)this + 50),
                         dwItemSpec);
        if ( TreeItemInfo )
        {
          if ( *((_BYTE *)TreeItemInfo + 52) )
            CNscTree::DrawDivider(this, hdc, dwItemSpec);
        }
        break;
    }
  }
  if ( a2->dwDrawStage == 2 && (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_NamespaceControl_Rendering_Stop,
      v22,
      1);
  return v50;
}

```

## disassembly

```asm
0x1800996f4  mov     [rsp-8+arg_10], rbx
0x1800996f9  push    rbp
0x1800996fa  push    rsi
0x1800996fb  push    rdi
0x1800996fc  push    r12
0x1800996fe  push    r13
0x180099700  push    r14
0x180099702  push    r15
0x180099704  lea     rbp, [rsp-1080h]
0x18009970c  mov     eax, 1180h
0x180099711  call    _alloca_probe
0x180099716  sub     rsp, rax
0x180099719  mov     rax, cs:__security_cookie
0x180099720  xor     rax, rsp
0x180099723  mov     [rbp+10B0h+var_40], rax
0x18009972a  mov     r14, [rdx+20h]
0x18009972e  xor     r13d, r13d
0x180099731  mov     eax, [rdx+18h]
0x180099734  mov     rdi, rdx
0x180099737  mov     r12, [rdx+38h]
0x18009973b  mov     rsi, rcx
0x18009973e  mov     [rsp+11B0h+var_1160], r13
0x180099743  lea     r15d, [r13+1]
0x180099747  mov     [rbp+10B0h+var_10A0], r14
0x18009974b  cmp     eax, r15d
0x18009974e  jz      loc_1800999E3
0x180099754  mov     rcx, [rsi+238h]
0x18009975b  mov     ebx, 10001h
0x180099760  test    rcx, rcx
0x180099763  jz      loc_1800998B4
0x180099769  sub     eax, r15d
0x18009976c  jz      loc_1800999C6
0x180099772  sub     eax, r15d
0x180099775  jz      loc_1800999F4
0x18009977b  sub     eax, 0FFFFh
0x180099780  jz      short loc_18009978B
0x180099782  cmp     eax, r15d
0x180099785  jnz     loc_1800998B4
0x18009978b  lea     r9, [rsp+11B0h+var_1158]; struct IShellItem **
0x180099790  mov     [rsp+11B0h+var_1158], r13
0x180099795  mov     r8, r12; struct _TREEITEM *
0x180099798  xor     edx, edx; int
0x18009979a  mov     rcx, rsi; this
0x18009979d  call    ?_ShellItemForTreeItem@CNscTree@@AEAAJHPEAU_TREEITEM@@PEAPEAUIShellItem@@@Z; CNscTree::_ShellItemForTreeItem(int,_TREEITEM *,IShellItem * *)
0x1800997a2  test    eax, eax
0x1800997a4  js      loc_1800998B4
0x1800997aa  xor     edx, edx; Val
0x1800997ac  lea     rcx, [rbp+10B0h+lParam]; void *
0x1800997b0  lea     r8d, [rdx+50h]; Size
0x1800997b4  call    memset_0
0x1800997b9  mov     rcx, [rsi+190h]; hWnd
0x1800997c0  lea     rax, [rbp+10B0h+var_1090]
0x1800997c4  lea     r9, [rbp+10B0h+lParam]; lParam
0x1800997c8  mov     [rbp+10B0h+var_10F8], rax
0x1800997cc  xor     r8d, r8d; wParam
0x1800997cf  mov     dword ptr [rbp+10B0h+lParam], 21Bh
0x1800997d6  mov     edx, 113Eh; Msg
0x1800997db  mov     [rbp+10B0h+var_10FC], 0F028h
0x1800997e2  mov     [rbp+10B0h+var_10F0], 824h
0x1800997e9  mov     [rbp+10B0h+var_1108], r12
0x1800997ed  call    cs:__imp_SendMessageW
0x1800997f3  test    eax, eax
0x1800997f5  jz      loc_1800998A3
0x1800997fb  test    [rbp+10B0h+var_1100], 20h
0x1800997ff  xorps   xmm0, xmm0
0x180099802  mov     rax, [rsp+11B0h+var_1158]
0x180099807  mov     [rsp+11B0h+var_1150], rax
0x18009980c  mov     eax, [rdi+40h]
0x18009980f  mov     dword ptr [rsp+11B0h+var_1150+8], eax
0x180099813  lea     rax, [rbp+10B0h+var_1090]
0x180099817  mov     qword ptr [rsp+11B0h+var_1140], rax
0x18009981c  movdqu  [rsp+11B0h+var_1140+0Ch], xmm0
0x180099822  mov     dword ptr [rbp+10B0h+var_1130+0Ch], r13d
0x180099826  jz      loc_180099962
0x18009982c  mov     eax, [rbp+10B0h+var_10C8]
0x18009982f  mov     dword ptr [rsp+11B0h+var_1150+0Ch], 2
0x180099837  mov     rcx, [rsi+190h]; hWnd
0x18009983e  xor     r9d, r9d; lParam
0x180099841  xor     r8d, r8d; wParam
0x180099844  mov     dword ptr [rsp+11B0h+var_1140+8], eax
0x180099848  mov     edx, 1108h; Msg
0x18009984d  call    cs:__imp_SendMessageW
0x180099853  mov     rcx, [rsi+190h]; hWnd
0x18009985a  xor     r9d, r9d; lParam
0x18009985d  mov     qword ptr [rbp+10B0h+var_1130], rax
0x180099861  xor     r8d, r8d; wParam
0x180099864  mov     eax, [rdi+58h]
0x180099867  mov     edx, 1106h; Msg
0x18009986c  mov     dword ptr [rbp+10B0h+var_1130+8], eax
0x18009986f  call    cs:__imp_SendMessageW
0x180099875  lea     r8, [rdi+28h]
0x180099879  mov     dword ptr [rbp+10B0h+var_1130+0Ch], eax
0x18009987c  mov     rax, [rsi+238h]
0x180099883  mov     r10, [rax]
0x180099886  cmp     [rdi+18h], ebx
0x180099889  jz      loc_180099977
0x18009988f  mov     rcx, rax
0x180099892  lea     r9, [rsp+11B0h+var_1150]
0x180099897  mov     rax, [r10+30h]
0x18009989b  mov     rdx, r14
0x18009989e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800998a3  mov     rcx, [rsp+11B0h+var_1158]
0x1800998a8  mov     rax, [rcx]
0x1800998ab  mov     rax, [rax+10h]
0x1800998af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800998b4  mov     edx, [rdi+18h]
0x1800998b7  cmp     edx, r15d
0x1800998ba  jz      loc_180099A33
0x1800998c0  mov     rcx, rsi; this
0x1800998c3  call    ?_SupportsCustomNode@CNscTree@@AEAAHXZ; CNscTree::_SupportsCustomNode(void)
0x1800998c8  test    eax, eax
0x1800998ca  jnz     loc_180099A3E
0x1800998d0  test    dword ptr [rsi+1C4h], 0E0000000h
0x1800998da  jnz     loc_180099BA5
0x1800998e0  test    byte ptr [rsi+1CCh], 20h
0x1800998e7  jz      short loc_180099929
0x1800998e9  test    byte ptr [rsi+1C8h], 8
0x1800998f0  jz      short loc_180099929
0x1800998f2  mov     ecx, [rdi+18h]
0x1800998f5  sub     ecx, 1
0x1800998f8  jz      loc_180099E00
0x1800998fe  sub     ecx, 10000h; this
0x180099904  jz      short loc_18009996F
0x180099906  cmp     ecx, 1
0x180099909  jnz     short loc_180099929
0x18009990b  mov     rdx, [rsi+190h]; HWND
0x180099912  mov     r8, r12; struct _TREEITEM *
0x180099915  call    ?_GetTreeItemInfo@CNscTree@@AEAAPEAUNSCITEMINFO@@PEAUHWND__@@PEAU_TREEITEM@@@Z; CNscTree::_GetTreeItemInfo(HWND__ *,_TREEITEM *)
0x18009991a  test    rax, rax
0x18009991d  jz      short loc_180099929
0x18009991f  cmp     [rax+34h], r13b
0x180099923  jnz     loc_180099DED
0x180099929  cmp     dword ptr [rdi+18h], 2
0x18009992d  jz      loc_180099E0B
0x180099933  mov     rax, [rsp+11B0h+var_1160]
0x180099938  mov     rcx, [rbp+10B0h+var_40]
0x18009993f  xor     rcx, rsp; StackCookie
0x180099942  call    __security_check_cookie
0x180099947  mov     rbx, [rsp+11B0h+arg_10]
0x18009994f  add     rsp, 1180h
0x180099956  pop     r15
0x180099958  pop     r14
0x18009995a  pop     r13
0x18009995c  pop     r12
0x18009995e  pop     rdi
0x18009995f  pop     rsi
0x180099960  pop     rbp
0x180099961  retn
0x180099962  mov     eax, [rbp+10B0h+var_10EC]
0x180099965  mov     dword ptr [rsp+11B0h+var_1150+0Ch], r13d
0x18009996a  jmp     loc_180099837
0x18009996f  or      [rsp+11B0h+var_1160], 10h
0x180099975  jmp     short loc_180099929
0x180099977  lea     r9, [rsp+11B0h+var_1160]
0x18009997c  mov     qword ptr [rsp+11B0h+var_1180], r9
0x180099981  lea     rcx, [rdi+54h]
0x180099985  mov     qword ptr [rsp+11B0h+var_1188], rcx
0x18009998a  lea     rdx, [rdi+50h]
0x18009998e  mov     [rsp+11B0h+var_1190], rdx
0x180099993  lea     r9, [rsp+11B0h+var_1150]
0x180099998  mov     rcx, rax
0x18009999b  mov     rdx, r14
0x18009999e  mov     rax, [r10+28h]
0x1800999a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800999a7  mov     ecx, dword ptr [rsp+11B0h+var_1150+8]
0x1800999ab  mov     eax, ecx
0x1800999ad  and     eax, 11h
0x1800999b0  mov     [rdi+40h], ecx
0x1800999b3  cmp     al, 11h
0x1800999b5  jnz     loc_1800998A3
0x1800999bb  or      ecx, 41h
0x1800999be  mov     [rdi+40h], ecx
0x1800999c1  jmp     loc_1800998A3
0x1800999c6  mov     rax, [rcx]
0x1800999c9  lea     r8, [rdi+28h]
0x1800999cd  lea     r9, [rsp+11B0h+var_1160]
0x1800999d2  mov     rdx, r14
0x1800999d5  mov     rax, [rax+18h]
0x1800999d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800999de  jmp     loc_1800998B4
0x1800999e3  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r15b
0x1800999ea  jnz     short loc_180099A0C
0x1800999ec  mov     eax, r15d
0x1800999ef  jmp     loc_180099754
0x1800999f4  mov     rax, [rcx]
0x1800999f7  lea     r8, [rdi+28h]
0x1800999fb  mov     rdx, r14
0x1800999fe  mov     rax, [rax+20h]
0x180099a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099a07  jmp     loc_1800998B4
0x180099a0c  lea     rax, [rbp+10B0h+var_10B0]
0x180099a10  mov     r9d, r15d
0x180099a13  lea     rdx, ShellTraceId_NamespaceControl_Rendering_Start
0x180099a1a  mov     [rsp+11B0h+var_1190], rax
0x180099a1f  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180099a26  call    McGenEventWrite_EventWriteTransfer
0x180099a2b  mov     eax, [rdi+18h]
0x180099a2e  jmp     loc_180099754
0x180099a33  or      [rsp+11B0h+var_1160], 10h
0x180099a39  jmp     loc_1800998C0
0x180099a3e  sub     edx, ebx
0x180099a40  jz      short loc_180099A79
0x180099a42  cmp     edx, r15d
0x180099a45  jnz     loc_1800998D0
0x180099a4b  mov     rdx, [rsi+2F0h]; h
0x180099a52  test    rdx, rdx
0x180099a55  jz      loc_1800998D0
0x180099a5b  mov     rcx, r14; hdc
0x180099a5e  call    cs:__imp_SelectObject
0x180099a64  mov     rcx, rax; ho
0x180099a67  call    cs:__imp_DeleteObject
0x180099a6d  mov     [rsi+2F0h], r13
0x180099a74  jmp     loc_1800998D0
0x180099a79  mov     rdx, [rsi+190h]; HWND
0x180099a80  mov     r8, r12; struct _TREEITEM *
0x180099a83  call    ?_GetTreeItemIDList@CNscTree@@AEAAPEFBU_ITEMIDLIST_RELATIVE@@PEAUHWND__@@PEAU_TREEITEM@@@Z; CNscTree::_GetTreeItemIDList(HWND__ *,_TREEITEM *)
0x180099a88  test    rax, rax
0x180099a8b  jnz     loc_1800998D0
0x180099a91  mov     rcx, [rsi+190h]; hWnd
0x180099a98  lea     r8d, [rax+3]; wParam
0x180099a9c  mov     r9, r12; lParam
0x180099a9f  mov     [rbp+10B0h+var_10B0], r13
0x180099aa3  mov     edx, 110Ah; Msg
0x180099aa8  call    cs:__imp_SendMessageW
0x180099aae  lea     r9, [rbp+10B0h+var_10B0]; struct IShellItem **
0x180099ab2  xor     edx, edx; int
0x180099ab4  mov     r8, rax; struct _TREEITEM *
0x180099ab7  mov     rcx, rsi; this
0x180099aba  call    ?_ShellItemForTreeItem@CNscTree@@AEAAJHPEAU_TREEITEM@@PEAPEAUIShellItem@@@Z; CNscTree::_ShellItemForTreeItem(int,_TREEITEM *,IShellItem * *)
0x180099abf  test    eax, eax
0x180099ac1  js      loc_1800998D0
0x180099ac7  mov     rcx, [rsi+240h]
0x180099ace  lea     r8, [rsp+11B0h+var_1158]
0x180099ad3  mov     rdx, [rbp+10B0h+var_10B0]
0x180099ad7  mov     dword ptr [rsp+11B0h+var_1158], r13d
0x180099adc  mov     rax, [rcx]
0x180099adf  mov     rax, [rax+20h]
0x180099ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099ae8  test    eax, eax
0x180099aea  js      loc_180099B90
0x180099af0  mov     eax, dword ptr [rsp+11B0h+var_1158]
0x180099af4  test    al, 2
0x180099af6  jz      loc_180099B7E
0x180099afc  mov     rcx, [rsi+190h]; hWnd
0x180099b03  xor     r9d, r9d; lParam
0x180099b06  xor     r8d, r8d; wParam
0x180099b09  lea     edx, [r9+31h]; Msg
0x180099b0d  call    cs:__imp_SendMessageW
0x180099b13  mov     r15d, 5Ch ; '\'
0x180099b19  lea     rcx, [rbp+10B0h+lParam]; void *
0x180099b1d  mov     r8d, r15d; Size
0x180099b20  xor     edx, edx; Val
0x180099b22  mov     rbx, rax
0x180099b25  call    memset_0
0x180099b2a  lea     r8, [rbp+10B0h+lParam]; pv
0x180099b2e  mov     edx, r15d; c
0x180099b31  mov     rcx, rbx; h
0x180099b34  call    cs:__imp_GetObjectW
0x180099b3a  mov     r15d, 1
0x180099b40  lea     rcx, [rbp+10B0h+lParam]; lplf
0x180099b44  mov     byte ptr [rbp+10B0h+var_10FC+1], r15b
0x180099b48  call    cs:__imp_CreateFontIndirectW
0x180099b4e  test    rax, rax
0x180099b51  jz      short loc_180099B66
0x180099b53  mov     rdx, rax; h
0x180099b56  mov     rcx, r14; hdc
0x180099b59  call    cs:__imp_SelectObject
0x180099b5f  mov     [rsi+2F0h], rax
0x180099b66  mov     ecx, 1Ah; nIndex
0x180099b6b  call    cs:__imp_GetSysColor
0x180099b71  or      [rsp+11B0h+var_1160], 2
0x180099b77  mov     [rdi+50h], eax
0x180099b7a  mov     eax, dword ptr [rsp+11B0h+var_1158]
0x180099b7e  test    al, 4
0x180099b80  jz      short loc_180099B90
0x180099b82  mov     ecx, 11h; nIndex
0x180099b87  call    cs:__imp_GetSysColor
0x180099b8d  mov     [rdi+50h], eax
0x180099b90  mov     rcx, [rbp+10B0h+var_10B0]
0x180099b94  mov     rax, [rcx]
0x180099b97  mov     rax, [rax+10h]
0x180099b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099ba0  jmp     loc_1800998D0
0x180099ba5  test    byte ptr [rsp+11B0h+var_1160], 4
0x180099baa  jnz     loc_1800998E0
0x180099bb0  mov     ecx, [rdi+18h]
0x180099bb3  sub     ecx, 1
0x180099bb6  jz      loc_180099DE2
0x180099bbc  cmp     ecx, 10000h
0x180099bc2  jnz     loc_1800998E0
0x180099bc8  lea     rcx, [rdi+28h]; lprc
0x180099bcc  call    cs:__imp_IsRectEmpty
0x180099bd2  test    eax, eax
0x180099bd4  jnz     loc_1800998E0
0x180099bda  mov     rcx, [rsi+190h]; hWnd
0x180099be1  lea     r9, [rsp+11B0h+var_1150]; lParam
0x180099be6  xorps   xmm0, xmm0
0x180099be9  xor     eax, eax
0x180099beb  movups  xmmword ptr [rsp+11B0h+var_1150], xmm0
0x180099bf0  mov     [rbp+10B0h+var_1120], rax
  ... truncated ...
```
