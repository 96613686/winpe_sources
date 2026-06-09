# _PaintImeComposition(HWND__ *)

- ea: `0x1800bb0f0`
- end: `0x1800bb334`
- name: `?_PaintImeComposition@@YAXPEAUHWND__@@@Z`
- size: `580`
- prototype: `void __fastcall(HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b5264`

## callees

- `0x1800bb0f0`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!free` at `0x1800bb300`
- `MSVCR100!free` at `0x1800bb300`
- `MSVCR100!malloc` at `0x1800bb207`
- `MSVCR100!malloc` at `0x1800bb207`
- `USER32!GetDC` at `0x1800bb151`
- `USER32!GetDC` at `0x1800bb151`
- `USER32!ReleaseDC` at `0x1800bb2f2`
- `USER32!ReleaseDC` at `0x1800bb2f2`
- `USER32!GetClientRect` at `0x1800bb1a1`
- `USER32!GetClientRect` at `0x1800bb1a1`
- `USER32!GetSysColor` at `0x1800bb26f`
- `USER32!GetSysColor` at `0x1800bb28e`
- `USER32!GetSysColor` at `0x1800bb26f`
- `USER32!GetSysColor` at `0x1800bb28e`
- `USER32!SendMessageA` at `0x1800bb167`
- `USER32!SendMessageA` at `0x1800bb1cd`
- `USER32!SendMessageA` at `0x1800bb1f1`
- `USER32!SendMessageA` at `0x1800bb228`
- `USER32!SendMessageA` at `0x1800bb167`
- `USER32!SendMessageA` at `0x1800bb1cd`
- `USER32!SendMessageA` at `0x1800bb1f1`
- `USER32!SendMessageA` at `0x1800bb228`
- `GDI32!GetTextExtentPoint32A` at `0x1800bb256`
- `GDI32!GetTextExtentPoint32A` at `0x1800bb256`
- `GDI32!LineTo` at `0x1800bb2c9`
- `GDI32!LineTo` at `0x1800bb2c9`
- `GDI32!MoveToEx` at `0x1800bb2bb`
- `GDI32!MoveToEx` at `0x1800bb2bb`
- `GDI32!GetTextMetricsA` at `0x1800bb193`
- `GDI32!GetTextMetricsA` at `0x1800bb193`
- `GDI32!SelectObject` at `0x1800bb17b`
- `GDI32!SelectObject` at `0x1800bb2a5`
- `GDI32!SelectObject` at `0x1800bb2d5`
- `GDI32!SelectObject` at `0x1800bb2e6`
- `GDI32!SelectObject` at `0x1800bb17b`
- `GDI32!SelectObject` at `0x1800bb2a5`
- `GDI32!SelectObject` at `0x1800bb2d5`
- `GDI32!SelectObject` at `0x1800bb2e6`
- `GDI32!SetBkColor` at `0x1800bb299`
- `GDI32!SetBkColor` at `0x1800bb299`
- `GDI32!CreatePen` at `0x1800bb280`
- `GDI32!CreatePen` at `0x1800bb280`

## pseudocode

```c
void __fastcall _PaintImeComposition(HWND a1)
{
  HDC DC; // rbp
  void *v3; // rax
  void *v4; // r13
  HGDIOBJ v5; // r12
  LONG tmHeight; // r15d
  __int16 v7; // ax
  LONG left; // ebx
  __int16 v9; // ax
  __int64 v10; // rdi
  _BYTE *v11; // rax
  _BYTE *v12; // r14
  int v13; // edi
  COLORREF SysColor; // eax
  HPEN Pen; // rbx
  COLORREF v16; // eax
  HGDIOBJ v17; // rbx
  LONG x; // [rsp+20h] [rbp-88h]
  struct tagSIZE psizl; // [rsp+28h] [rbp-80h] BYREF
  struct tagRECT Rect; // [rsp+30h] [rbp-78h] BYREF
  struct tagTEXTMETRICA tm; // [rsp+40h] [rbp-68h] BYREF

  if ( dword_1803FB074 && dword_1803FB078 && Sys_WinVersion != 819 )
  {
    DC = GetDC(a1);
    v3 = (void *)SendMessageA(a1, 0x31u, 0, 0);
    v4 = v3;
    if ( v3 )
      v5 = SelectObject(DC, v3);
    else
      v5 = (HGDIOBJ)psizl;
    GetTextMetricsA(DC, &tm);
    GetClientRect(a1, &Rect);
    tmHeight = tm.tmHeight;
    if ( tm.tmHeight >= (unsigned int)Rect.bottom )
      tmHeight = Rect.bottom - 1;
    v7 = SendMessageA(a1, 0xD6u, (unsigned int)wParam, 0);
    left = Rect.left;
    x = Rect.left;
    if ( Rect.left <= v7 )
    {
      v9 = SendMessageA(a1, 0xD6u, (unsigned int)wParam, 0);
      left = v9;
      x = v9;
    }
    v10 = (unsigned int)dword_1803FB080;
    v11 = malloc((unsigned int)(dword_1803FB080 + 1));
    v12 = v11;
    if ( v11 )
    {
      SendMessageA(a1, 0xDu, v10 + 1, (LPARAM)v11);
      v12[dword_1803FB080] = 0;
      if ( GetTextExtentPoint32A(DC, &v12[(unsigned int)wParam], dword_1803FB080 - wParam, &psizl) )
      {
        v13 = left + psizl.cx;
        SysColor = GetSysColor(8);
        Pen = CreatePen(2, 1, SysColor);
        v16 = GetSysColor(5);
        SetBkColor(DC, v16);
        v17 = SelectObject(DC, Pen);
        MoveToEx(DC, x, tmHeight, 0);
        LineTo(DC, v13, tmHeight);
        SelectObject(DC, v17);
        if ( v4 )
          SelectObject(DC, v5);
      }
    }
    ReleaseDC(a1, DC);
    if ( v12 )
      free(v12);
  }
}

```

## disassembly

```asm
0x1800bb0f0  mov     [rsp+arg_8], rbx
0x1800bb0f5  mov     [rsp+arg_10], rbp
0x1800bb0fa  mov     [rsp+arg_18], rsi
0x1800bb0ff  push    rdi
0x1800bb100  push    r12
0x1800bb102  push    r13
0x1800bb104  push    r14
0x1800bb106  push    r15
0x1800bb108  mov     eax, 80h
0x1800bb10d  call    _alloca_probe
0x1800bb112  sub     rsp, rax
0x1800bb115  mov     rax, cs:__security_cookie
0x1800bb11c  xor     rax, rsp
0x1800bb11f  mov     [rsp+0A8h+var_30], rax
0x1800bb124  cmp     cs:dword_1803FB074, 0
0x1800bb12b  mov     rsi, rcx
0x1800bb12e  jz      loc_1800BB306
0x1800bb134  cmp     cs:dword_1803FB078, 0
0x1800bb13b  jz      loc_1800BB306
0x1800bb141  cmp     cs:?Sys_WinVersion@@3IA, 333h; uint Sys_WinVersion
0x1800bb14b  jz      loc_1800BB306
0x1800bb151  call    cs:__imp_GetDC
0x1800bb157  xor     r9d, r9d; lParam
0x1800bb15a  xor     r8d, r8d; wParam
0x1800bb15d  lea     edx, [r9+31h]; Msg
0x1800bb161  mov     rcx, rsi; hWnd
0x1800bb164  mov     rbp, rax
0x1800bb167  call    cs:__imp_SendMessageA
0x1800bb16d  mov     r13, rax
0x1800bb170  test    rax, rax
0x1800bb173  jz      short loc_1800BB186
0x1800bb175  mov     rdx, rax; h
0x1800bb178  mov     rcx, rbp; hdc
0x1800bb17b  call    cs:__imp_SelectObject
0x1800bb181  mov     r12, rax
0x1800bb184  jmp     short loc_1800BB18B
0x1800bb186  mov     r12, qword ptr [rsp+0A8h+psizl.cx]
0x1800bb18b  lea     rdx, [rsp+0A8h+tm]; lptm
0x1800bb190  mov     rcx, rbp; hdc
0x1800bb193  call    cs:__imp_GetTextMetricsA
0x1800bb199  lea     rdx, [rsp+0A8h+Rect]; lpRect
0x1800bb19e  mov     rcx, rsi; hWnd
0x1800bb1a1  call    cs:__imp_GetClientRect
0x1800bb1a7  mov     r15d, [rsp+0A8h+tm.tmHeight]
0x1800bb1ac  mov     eax, [rsp+0A8h+Rect.bottom]
0x1800bb1b0  cmp     r15d, eax
0x1800bb1b3  jb      short loc_1800BB1B9
0x1800bb1b5  lea     r15d, [rax-1]
0x1800bb1b9  mov     r8d, cs:wParam; wParam
0x1800bb1c0  mov     edi, 0D6h
0x1800bb1c5  xor     r9d, r9d; lParam
0x1800bb1c8  mov     edx, edi; Msg
0x1800bb1ca  mov     rcx, rsi; hWnd
0x1800bb1cd  call    cs:__imp_SendMessageA
0x1800bb1d3  mov     ebx, [rsp+0A8h+Rect.left]
0x1800bb1d7  movsx   ecx, ax
0x1800bb1da  mov     [rsp+0A8h+x], ebx
0x1800bb1de  cmp     ebx, ecx
0x1800bb1e0  jg      short loc_1800BB1FE
0x1800bb1e2  mov     r8d, cs:wParam; wParam
0x1800bb1e9  xor     r9d, r9d; lParam
0x1800bb1ec  mov     edx, edi; Msg
0x1800bb1ee  mov     rcx, rsi; hWnd
0x1800bb1f1  call    cs:__imp_SendMessageA
0x1800bb1f7  movsx   ebx, ax
0x1800bb1fa  mov     [rsp+0A8h+x], ebx
0x1800bb1fe  mov     edi, cs:dword_1803FB080
0x1800bb204  lea     ecx, [rdi+1]; Size
0x1800bb207  call    cs:__imp_malloc
0x1800bb20d  mov     r14, rax
0x1800bb210  test    rax, rax
0x1800bb213  jz      loc_1800BB2EC
0x1800bb219  lea     r8, [rdi+1]; wParam
0x1800bb21d  mov     r9, rax; lParam
0x1800bb220  mov     edx, 0Dh; Msg
0x1800bb225  mov     rcx, rsi; hWnd
0x1800bb228  call    cs:__imp_SendMessageA
0x1800bb22e  mov     r11d, cs:dword_1803FB080
0x1800bb235  lea     r9, [rsp+0A8h+psizl]; psizl
0x1800bb23a  mov     byte ptr [r11+r14], 0
0x1800bb23f  mov     eax, cs:wParam
0x1800bb245  mov     r8d, cs:dword_1803FB080
0x1800bb24c  lea     rdx, [r14+rax]; lpString
0x1800bb250  sub     r8d, eax; c
0x1800bb253  mov     rcx, rbp; hdc
0x1800bb256  call    cs:__imp_GetTextExtentPoint32A
0x1800bb25c  test    eax, eax
0x1800bb25e  jz      loc_1800BB2EC
0x1800bb264  mov     edi, [rsp+0A8h+psizl.cx]
0x1800bb268  mov     ecx, 8; nIndex
0x1800bb26d  add     edi, ebx
0x1800bb26f  call    cs:__imp_GetSysColor
0x1800bb275  mov     edx, 1; cWidth
0x1800bb27a  lea     ecx, [rdx+1]; iStyle
0x1800bb27d  mov     r8d, eax; color
0x1800bb280  call    cs:__imp_CreatePen
0x1800bb286  mov     ecx, 5; nIndex
0x1800bb28b  mov     rbx, rax
0x1800bb28e  call    cs:__imp_GetSysColor
0x1800bb294  mov     rcx, rbp; hdc
0x1800bb297  mov     edx, eax; color
0x1800bb299  call    cs:__imp_SetBkColor
0x1800bb29f  mov     rdx, rbx; h
0x1800bb2a2  mov     rcx, rbp; hdc
0x1800bb2a5  call    cs:__imp_SelectObject
0x1800bb2ab  mov     edx, [rsp+0A8h+x]; x
0x1800bb2af  xor     r9d, r9d; lppt
0x1800bb2b2  mov     r8d, r15d; y
0x1800bb2b5  mov     rcx, rbp; hdc
0x1800bb2b8  mov     rbx, rax
0x1800bb2bb  call    cs:__imp_MoveToEx
0x1800bb2c1  mov     r8d, r15d; y
0x1800bb2c4  mov     edx, edi; x
0x1800bb2c6  mov     rcx, rbp; hdc
0x1800bb2c9  call    cs:__imp_LineTo
0x1800bb2cf  mov     rdx, rbx; h
0x1800bb2d2  mov     rcx, rbp; hdc
0x1800bb2d5  call    cs:__imp_SelectObject
0x1800bb2db  test    r13, r13
0x1800bb2de  jz      short loc_1800BB2EC
0x1800bb2e0  mov     rdx, r12; h
0x1800bb2e3  mov     rcx, rbp; hdc
0x1800bb2e6  call    cs:__imp_SelectObject
0x1800bb2ec  mov     rdx, rbp; hDC
0x1800bb2ef  mov     rcx, rsi; hWnd
0x1800bb2f2  call    cs:__imp_ReleaseDC
0x1800bb2f8  test    r14, r14
0x1800bb2fb  jz      short loc_1800BB306
0x1800bb2fd  mov     rcx, r14; Block
0x1800bb300  call    cs:__imp_free
0x1800bb306  mov     rcx, [rsp+0A8h+var_30]
0x1800bb30b  xor     rcx, rsp; StackCookie
0x1800bb30e  call    __security_check_cookie
0x1800bb313  lea     r11, [rsp+0A8h+var_28]
0x1800bb31b  mov     rbx, [r11+38h]
0x1800bb31f  mov     rbp, [r11+40h]
0x1800bb323  mov     rsi, [r11+48h]
0x1800bb327  mov     rsp, r11
0x1800bb32a  pop     r15
0x1800bb32c  pop     r14
0x1800bb32e  pop     r13
0x1800bb330  pop     r12
0x1800bb332  pop     rdi
0x1800bb333  retn
```
