# _DrawColorListBox(tagDRAWITEMSTRUCT *)

- ea: `0x1800c15f0`
- end: `0x1800c17f1`
- name: `?_DrawColorListBox@@YAXPEAUtagDRAWITEMSTRUCT@@@Z`
- size: `513`
- prototype: `void __fastcall(struct tagDRAWITEMSTRUCT *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800c05e8`

## callees

- `0x180001180`
- `0x1800187f0`
- `0x180026838`
- `0x180028ad0`
- `0x180028b00`
- `0x1800c15f0`
- `0x180379380`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x1800c16be`
- `KERNEL32!lstrlenA` at `0x1800c16be`
- `USER32!FillRect` at `0x1800c16a2`
- `USER32!FillRect` at `0x1800c16a2`
- `USER32!GetSysColor` at `0x1800c1648`
- `USER32!GetSysColor` at `0x1800c1662`
- `USER32!GetSysColor` at `0x1800c1648`
- `USER32!GetSysColor` at `0x1800c1662`
- `GDI32!GetBkColor` at `0x1800c1687`
- `GDI32!GetBkColor` at `0x1800c1687`
- `GDI32!GetNearestColor` at `0x1800c170f`
- `GDI32!GetNearestColor` at `0x1800c170f`
- `GDI32!Rectangle` at `0x1800c1782`
- `GDI32!Rectangle` at `0x1800c1782`
- `GDI32!GetTextColor` at `0x1800c1724`
- `GDI32!GetTextColor` at `0x1800c1724`
- `GDI32!ExtTextOutA` at `0x1800c16f2`
- `GDI32!ExtTextOutA` at `0x1800c16f2`
- `GDI32!SelectObject` at `0x1800c1624`
- `GDI32!SelectObject` at `0x1800c1744`
- `GDI32!SelectObject` at `0x1800c1754`
- `GDI32!SelectObject` at `0x1800c1624`
- `GDI32!SelectObject` at `0x1800c1744`
- `GDI32!SelectObject` at `0x1800c1754`
- `GDI32!SetTextColor` at `0x1800c1654`
- `GDI32!SetTextColor` at `0x1800c17c0`
- `GDI32!SetTextColor` at `0x1800c1654`
- `GDI32!SetTextColor` at `0x1800c17c0`
- `GDI32!SetBkColor` at `0x1800c166e`
- `GDI32!SetBkColor` at `0x1800c17cd`
- `GDI32!SetBkColor` at `0x1800c166e`
- `GDI32!SetBkColor` at `0x1800c17cd`
- `GDI32!DeleteObject` at `0x1800c17a3`
- `GDI32!DeleteObject` at `0x1800c17ac`
- `GDI32!DeleteObject` at `0x1800c17a3`
- `GDI32!DeleteObject` at `0x1800c17ac`
- `GDI32!CreateSolidBrush` at `0x1800c1717`
- `GDI32!CreateSolidBrush` at `0x1800c1717`
- `GDI32!CreatePen` at `0x1800c1734`
- `GDI32!CreatePen` at `0x1800c1734`

## pseudocode

```c
void __fastcall _DrawColorListBox(struct tagDRAWITEMSTRUCT *a1)
{
  HFONT v2; // rax
  COLORREF SysColor; // eax
  COLORREF v4; // r12d
  COLORREF v5; // eax
  COLORREF v6; // r13d
  COLORREF BkColor; // eax
  HBRUSH v8; // rax
  RECT *p_rcItem; // r15
  const CHAR *v10; // rax
  UINT c; // ebx
  const CHAR *lpString; // rax
  COLORREF NearestColor; // eax
  HBRUSH SolidBrush; // rbp
  COLORREF TextColor; // eax
  HPEN Pen; // rsi
  HBRUSH v17; // rdi
  HPEN v18; // rbx
  COLORREF v19; // [rsp+70h] [rbp+8h]

  v2 = HfontIdeLight();
  SelectObject(a1->hDC, v2);
  if ( a1->itemAction == 1 || a1->itemAction == 2 )
  {
    if ( (a1->itemState & 1) != 0 )
    {
      SysColor = GetSysColor(14);
      v4 = SetTextColor(a1->hDC, SysColor);
      v5 = GetSysColor(13);
      v6 = SetBkColor(a1->hDC, v5);
    }
    else
    {
      v4 = v19;
      v6 = v19;
    }
    BkColor = GetBkColor(a1->hDC);
    v8 = BrHbrushCreate(BkColor);
    p_rcItem = &a1->rcItem;
    FillRect(a1->hDC, &a1->rcItem, v8);
    if ( a1->itemID )
    {
      NearestColor = GetNearestColor(a1->hDC, *((_DWORD *)qword_1803B17C0 + a1->itemID));
      SolidBrush = CreateSolidBrush(NearestColor);
      TextColor = GetTextColor(a1->hDC);
      Pen = CreatePen(0, 1, TextColor);
      v17 = (HBRUSH)SelectObject(a1->hDC, SolidBrush);
      v18 = (HPEN)SelectObject(a1->hDC, Pen);
      Rectangle(a1->hDC, p_rcItem->left + 2, a1->rcItem.top + 3, a1->rcItem.right - 2, a1->rcItem.bottom - 3);
      RestoreBrush(a1->hDC, v17);
      RestorePen(a1->hDC, v18);
      DeleteObject(SolidBrush);
      DeleteObject(Pen);
    }
    else
    {
      v10 = IntlLpstrStringOfID(162);
      c = lstrlenA(v10);
      lpString = IntlLpstrStringOfID(162);
      ExtTextOutA(a1->hDC, p_rcItem->left, a1->rcItem.top, 2u, &a1->rcItem, lpString, c, 0);
    }
    if ( (a1->itemState & 1) != 0 )
    {
      SetTextColor(a1->hDC, v4);
      SetBkColor(a1->hDC, v6);
    }
  }
}

```

## disassembly

```asm
0x1800c15f0  mov     [rsp+arg_8], rbx
0x1800c15f5  mov     [rsp+arg_10], rbp
0x1800c15fa  mov     [rsp+arg_18], rsi
0x1800c15ff  push    rdi
0x1800c1600  push    r12
0x1800c1602  push    r13
0x1800c1604  push    r14
0x1800c1606  push    r15
0x1800c1608  mov     eax, 40h
0x1800c160d  call    _alloca_probe
0x1800c1612  sub     rsp, rax
0x1800c1615  mov     r14, rcx
0x1800c1618  call    ?HfontIdeLight@@YAPEAUHFONT__@@XZ; HfontIdeLight(void)
0x1800c161d  mov     rcx, [r14+20h]; hdc
0x1800c1621  mov     rdx, rax; h
0x1800c1624  call    cs:__imp_SelectObject
0x1800c162a  cmp     dword ptr [r14+0Ch], 1
0x1800c162f  jz      short loc_1800C163C
0x1800c1631  cmp     dword ptr [r14+0Ch], 2
0x1800c1636  jnz     loc_1800C17D3
0x1800c163c  test    byte ptr [r14+10h], 1
0x1800c1641  jz      short loc_1800C1679
0x1800c1643  mov     ecx, 0Eh; nIndex
0x1800c1648  call    cs:__imp_GetSysColor
0x1800c164e  mov     rcx, [r14+20h]; hdc
0x1800c1652  mov     edx, eax; color
0x1800c1654  call    cs:__imp_SetTextColor
0x1800c165a  mov     ecx, 0Dh; nIndex
0x1800c165f  mov     r12d, eax
0x1800c1662  call    cs:__imp_GetSysColor
0x1800c1668  mov     rcx, [r14+20h]; hdc
0x1800c166c  mov     edx, eax; color
0x1800c166e  call    cs:__imp_SetBkColor
0x1800c1674  mov     r13d, eax
0x1800c1677  jmp     short loc_1800C1683
0x1800c1679  mov     r12d, [rsp+68h+arg_0]
0x1800c167e  mov     r13d, [rsp+68h+arg_0]
0x1800c1683  mov     rcx, [r14+20h]; hdc
0x1800c1687  call    cs:__imp_GetBkColor
0x1800c168d  mov     ecx, eax; unsigned int
0x1800c168f  call    ?BrHbrushCreate@@YAPEAUHBRUSH__@@K@Z; BrHbrushCreate(ulong)
0x1800c1694  mov     rcx, [r14+20h]; hDC
0x1800c1698  lea     r15, [r14+28h]
0x1800c169c  mov     r8, rax; hbr
0x1800c169f  mov     rdx, r15; lprc
0x1800c16a2  call    cs:__imp_FillRect
0x1800c16a8  cmp     dword ptr [r14+8], 0
0x1800c16ad  jnz     short loc_1800C16FD
0x1800c16af  mov     edi, 0A2h
0x1800c16b4  mov     ecx, edi; int
0x1800c16b6  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x1800c16bb  mov     rcx, rax; lpString
0x1800c16be  call    cs:__imp_lstrlenA
0x1800c16c4  mov     ecx, edi; int
0x1800c16c6  mov     ebx, eax
0x1800c16c8  call    ?IntlLpstrStringOfID@@YAPEADH@Z; IntlLpstrStringOfID(int)
0x1800c16cd  and     [rsp+68h+var_30], 0
0x1800c16d3  mov     r8d, [r14+2Ch]; y
0x1800c16d7  mov     edx, [r15]; x
0x1800c16da  mov     rcx, [r14+20h]; hdc
0x1800c16de  mov     [rsp+68h+c], ebx; c
0x1800c16e2  mov     [rsp+68h+lpString], rax; lpString
0x1800c16e7  mov     r9d, 2; options
0x1800c16ed  mov     [rsp+68h+lprect], r15; lprect
0x1800c16f2  call    cs:__imp_ExtTextOutA
0x1800c16f8  jmp     loc_1800C17B2
0x1800c16fd  mov     eax, [r14+8]
0x1800c1701  lea     rcx, qword_1803B17C0
0x1800c1708  mov     edx, [rcx+rax*4]; color
0x1800c170b  mov     rcx, [r14+20h]; hdc
0x1800c170f  call    cs:__imp_GetNearestColor
0x1800c1715  mov     ecx, eax; color
0x1800c1717  call    cs:__imp_CreateSolidBrush
0x1800c171d  mov     rcx, [r14+20h]; hdc
0x1800c1721  mov     rbp, rax
0x1800c1724  call    cs:__imp_GetTextColor
0x1800c172a  mov     edx, 1; cWidth
0x1800c172f  mov     r8d, eax; color
0x1800c1732  xor     ecx, ecx; iStyle
0x1800c1734  call    cs:__imp_CreatePen
0x1800c173a  mov     rcx, [r14+20h]; hdc
0x1800c173e  mov     rdx, rbp; h
0x1800c1741  mov     rsi, rax
0x1800c1744  call    cs:__imp_SelectObject
0x1800c174a  mov     rcx, [r14+20h]; hdc
0x1800c174e  mov     rdx, rsi; h
0x1800c1751  mov     rdi, rax
0x1800c1754  call    cs:__imp_SelectObject
0x1800c175a  mov     ecx, [r14+34h]
0x1800c175e  mov     r9d, [r14+30h]
0x1800c1762  mov     r8d, [r14+2Ch]
0x1800c1766  mov     edx, [r15]
0x1800c1769  sub     ecx, 3
0x1800c176c  mov     dword ptr [rsp+68h+lprect], ecx; bottom
0x1800c1770  mov     rcx, [r14+20h]; hdc
0x1800c1774  sub     r9d, 2; right
0x1800c1778  add     r8d, 3; top
0x1800c177c  add     edx, 2; left
0x1800c177f  mov     rbx, rax
0x1800c1782  call    cs:__imp_Rectangle
0x1800c1788  mov     rcx, [r14+20h]; HDC
0x1800c178c  mov     rdx, rdi; HBRUSH
0x1800c178f  call    ?RestoreBrush@@YAXPEAUHDC__@@PEAUHBRUSH__@@@Z; RestoreBrush(HDC__ *,HBRUSH__ *)
0x1800c1794  mov     rcx, [r14+20h]; HDC
0x1800c1798  mov     rdx, rbx; HPEN
0x1800c179b  call    ?RestorePen@@YAXPEAUHDC__@@PEAUHPEN__@@@Z; RestorePen(HDC__ *,HPEN__ *)
0x1800c17a0  mov     rcx, rbp; ho
0x1800c17a3  call    cs:__imp_DeleteObject
0x1800c17a9  mov     rcx, rsi; ho
0x1800c17ac  call    cs:__imp_DeleteObject
0x1800c17b2  test    byte ptr [r14+10h], 1
0x1800c17b7  jz      short loc_1800C17D3
0x1800c17b9  mov     rcx, [r14+20h]; hdc
0x1800c17bd  mov     edx, r12d; color
0x1800c17c0  call    cs:__imp_SetTextColor
0x1800c17c6  mov     rcx, [r14+20h]; hdc
0x1800c17ca  mov     edx, r13d; color
0x1800c17cd  call    cs:__imp_SetBkColor
0x1800c17d3  lea     r11, [rsp+68h+var_28]
0x1800c17d8  mov     rbx, [r11+38h]
0x1800c17dc  mov     rbp, [r11+40h]
0x1800c17e0  mov     rsi, [r11+48h]
0x1800c17e4  mov     rsp, r11
0x1800c17e7  pop     r15
0x1800c17e9  pop     r14
0x1800c17eb  pop     r13
0x1800c17ed  pop     r12
0x1800c17ef  pop     rdi
0x1800c17f0  retn
```
