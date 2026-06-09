# DeskSizeClientRect(CTL *,HWND__ *,tagRECT *,int)

- ea: `0x1800120b8`
- end: `0x18001225a`
- name: `?DeskSizeClientRect@@YAHPEAUCTL@@PEAUHWND__@@PEAUtagRECT@@H@Z`
- size: `418`
- prototype: `__int64 __fastcall(struct CTL *, HWND, struct tagRECT *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180012f70`

## callees

- `0x1800019b8`
- `0x1800120b8`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `USER32!EqualRect` at `0x180012167`
- `USER32!EqualRect` at `0x180012167`
- `USER32!CopyRect` at `0x1800121cf`
- `USER32!CopyRect` at `0x1800121cf`
- `USER32!AdjustWindowRectEx` at `0x1800121e1`
- `USER32!AdjustWindowRectEx` at `0x1800121e1`
- `USER32!SetWindowPos` at `0x1800121a2`
- `USER32!SetWindowPos` at `0x180012236`
- `USER32!SetWindowPos` at `0x1800121a2`
- `USER32!SetWindowPos` at `0x180012236`
- `USER32!IsWindowVisible` at `0x180012178`
- `USER32!IsWindowVisible` at `0x180012178`
- `USER32!GetClientRect` at `0x180012110`
- `USER32!GetClientRect` at `0x180012110`
- `USER32!MapWindowPoints` at `0x180012125`
- `USER32!MapWindowPoints` at `0x180012125`
- `USER32!MoveWindow` at `0x180012209`
- `USER32!MoveWindow` at `0x180012209`
- `USER32!GetWindowLongA` at `0x1800121b0`
- `USER32!GetWindowLongA` at `0x1800121c0`
- `USER32!GetWindowLongA` at `0x1800121b0`
- `USER32!GetWindowLongA` at `0x1800121c0`

## pseudocode

```c
__int64 __fastcall DeskSizeClientRect(struct CTL *a1, HWND a2, struct tagRECT *a3, int a4)
{
  unsigned int v4; // r15d
  struct tagRECT *v6; // rsi
  LONG top; // eax
  int v10; // ecx
  int v11; // edx
  LONG left; // eax
  LONG WindowLongA; // edi
  LONG v14; // ebx
  struct tagRECT Rect; // [rsp+40h] [rbp-30h] BYREF
  struct tagRECT v17; // [rsp+50h] [rbp-20h] BYREF

  v4 = 0;
  v6 = a3;
  if ( !a3 )
  {
    v6 = &v17;
    PLOT::GetRECT((struct CTL *)((char *)a1 + 624), &v17);
  }
  GetClientRect(a2, &Rect);
  MapWindowPoints(a2, 0, (LPPOINT)&Rect, 2u);
  if ( ((*((_DWORD *)a1 + 160) >> 9) & 3) == 3 )
  {
    top = Rect.top;
    v10 = v6->bottom - v6->top;
    v11 = v6->right - v6->left;
    v6->top = Rect.top;
    v6->bottom = v10 + top;
    left = Rect.left;
    v6->left = Rect.left;
    v6->right = v11 + left;
  }
  if ( !EqualRect(&Rect, v6) )
  {
    v4 = IsWindowVisible(a2);
    if ( v4 )
      SetWindowPos(a2, 0, 0, 0, 0, 0, 0x87u);
    WindowLongA = GetWindowLongA(a2, -16);
    v14 = GetWindowLongA(a2, -20);
    CopyRect(&Rect, v6);
    AdjustWindowRectEx(&Rect, WindowLongA, 0, v14);
    MoveWindow(a2, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 0);
    if ( v4 && !a4 )
      SetWindowPos(a2, 0, 0, 0, 0, 0, 0x47u);
  }
  return v4;
}

```

## disassembly

```asm
0x1800120b8  push    rbp
0x1800120ba  push    rbx
0x1800120bb  push    rsi
0x1800120bc  push    rdi
0x1800120bd  push    r12
0x1800120bf  push    r14
0x1800120c1  push    r15
0x1800120c3  mov     rbp, rsp
0x1800120c6  mov     eax, 70h
0x1800120cb  call    _alloca_probe
0x1800120d0  sub     rsp, rax
0x1800120d3  mov     rax, cs:__security_cookie
0x1800120da  xor     rax, rsp
0x1800120dd  mov     [rbp+var_10], rax
0x1800120e1  xor     r15d, r15d
0x1800120e4  mov     r12d, r9d
0x1800120e7  mov     rsi, r8
0x1800120ea  mov     r14, rdx
0x1800120ed  mov     rbx, rcx
0x1800120f0  test    r8, r8
0x1800120f3  jnz     short loc_180012109
0x1800120f5  lea     rdx, [rbp+var_20]; struct tagRECT *
0x1800120f9  add     rcx, 270h; this
0x180012100  lea     rsi, [rbp+var_20]
0x180012104  call    ?GetRECT@PLOT@@QEAAXPEAUtagRECT@@@Z; PLOT::GetRECT(tagRECT *)
0x180012109  lea     rdx, [rbp+Rect]; lpRect
0x18001210d  mov     rcx, r14; hWnd
0x180012110  call    cs:__imp_GetClientRect
0x180012116  lea     r8, [rbp+Rect]; lpPoints
0x18001211a  mov     r9d, 2; cPoints
0x180012120  xor     edx, edx; hWndTo
0x180012122  mov     rcx, r14; hWndFrom
0x180012125  call    cs:__imp_MapWindowPoints
0x18001212b  mov     r11d, [rbx+280h]
0x180012132  shr     r11d, 9
0x180012136  and     r11b, 3
0x18001213a  cmp     r11b, 3
0x18001213e  jnz     short loc_180012160
0x180012140  mov     ecx, [rsi+0Ch]
0x180012143  mov     eax, [rbp+Rect.top]
0x180012146  mov     edx, [rsi+8]
0x180012149  sub     ecx, [rsi+4]
0x18001214c  sub     edx, [rsi]
0x18001214e  mov     [rsi+4], eax
0x180012151  add     eax, ecx
0x180012153  mov     [rsi+0Ch], eax
0x180012156  mov     eax, [rbp+Rect.left]
0x180012159  mov     [rsi], eax
0x18001215b  add     eax, edx
0x18001215d  mov     [rsi+8], eax
0x180012160  lea     rcx, [rbp+Rect]; lprc1
0x180012164  mov     rdx, rsi; lprc2
0x180012167  call    cs:__imp_EqualRect
0x18001216d  test    eax, eax
0x18001216f  jnz     loc_18001223C
0x180012175  mov     rcx, r14; hWnd
0x180012178  call    cs:__imp_IsWindowVisible
0x18001217e  mov     r15d, eax
0x180012181  test    eax, eax
0x180012183  jz      short loc_1800121A8
0x180012185  mov     [rsp+70h+uFlags], 87h; uFlags
0x18001218d  and     [rsp+70h+var_48], 0
0x180012192  and     [rsp+70h+nHeight], 0
0x180012197  xor     r9d, r9d; Y
0x18001219a  xor     r8d, r8d; X
0x18001219d  xor     edx, edx; hWndInsertAfter
0x18001219f  mov     rcx, r14; hWnd
0x1800121a2  call    cs:__imp_SetWindowPos
0x1800121a8  mov     edx, 0FFFFFFF0h; nIndex
0x1800121ad  mov     rcx, r14; hWnd
0x1800121b0  call    cs:__imp_GetWindowLongA
0x1800121b6  mov     edx, 0FFFFFFECh; nIndex
0x1800121bb  mov     rcx, r14; hWnd
0x1800121be  mov     edi, eax
0x1800121c0  call    cs:__imp_GetWindowLongA
0x1800121c6  lea     rcx, [rbp+Rect]; lprcDst
0x1800121ca  mov     rdx, rsi; lprcSrc
0x1800121cd  mov     ebx, eax
0x1800121cf  call    cs:__imp_CopyRect
0x1800121d5  lea     rcx, [rbp+Rect]; lpRect
0x1800121d9  mov     r9d, ebx; dwExStyle
0x1800121dc  xor     r8d, r8d; bMenu
0x1800121df  mov     edx, edi; dwStyle
0x1800121e1  call    cs:__imp_AdjustWindowRectEx
0x1800121e7  mov     r11d, [rbp+Rect.bottom]
0x1800121eb  mov     r8d, [rbp+Rect.top]; Y
0x1800121ef  mov     r9d, [rbp+Rect.right]
0x1800121f3  mov     edx, [rbp+Rect.left]; X
0x1800121f6  and     [rsp+70h+var_48], 0
0x1800121fb  sub     r11d, r8d
0x1800121fe  sub     r9d, edx; nWidth
0x180012201  mov     rcx, r14; hWnd
0x180012204  mov     [rsp+70h+nHeight], r11d; cx
0x180012209  call    cs:__imp_MoveWindow
0x18001220f  test    r15d, r15d
0x180012212  jz      short loc_18001223C
0x180012214  test    r12d, r12d
0x180012217  jnz     short loc_18001223C
0x180012219  mov     [rsp+70h+uFlags], 47h ; 'G'; uFlags
0x180012221  and     [rsp+70h+var_48], r12d
0x180012226  and     [rsp+70h+nHeight], r12d
0x18001222b  xor     r9d, r9d; Y
0x18001222e  xor     r8d, r8d; X
0x180012231  xor     edx, edx; hWndInsertAfter
0x180012233  mov     rcx, r14; hWnd
0x180012236  call    cs:__imp_SetWindowPos
0x18001223c  mov     eax, r15d
0x18001223f  mov     rcx, [rbp+var_10]
0x180012243  xor     rcx, rsp; StackCookie
0x180012246  call    __security_check_cookie
0x18001224b  add     rsp, 70h
0x18001224f  pop     r15
0x180012251  pop     r14
0x180012253  pop     r12
0x180012255  pop     rdi
0x180012256  pop     rsi
0x180012257  pop     rbx
0x180012258  pop     rbp
0x180012259  retn
```
