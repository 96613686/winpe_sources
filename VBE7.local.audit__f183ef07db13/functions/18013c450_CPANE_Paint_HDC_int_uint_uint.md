# CPANE::Paint(HDC__ *,int,uint,uint)

- ea: `0x18013c450`
- end: `0x18013c896`
- name: `?Paint@CPANE@@QEAAXPEAUHDC__@@HII@Z`
- size: `1094`
- prototype: `void __fastcall(CPANE *__hidden this, HDC, int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18013beb0`
- `0x18013c408`

## callees

- `0x1800e6178`
- `0x1800fa5c4`
- `0x18013c0c8`
- `0x18013c450`
- `0x18013d578`
- `0x18013e474`
- `0x18013e4c0`
- `0x18013e670`
- `0x18013e7d0`
- `0x1801f45b8`
- `0x1801f4654`
- `0x180379520`

## import_xrefs

- `USER32!HideCaret` at `0x18013c4ba`
- `USER32!HideCaret` at `0x18013c4ba`
- `USER32!ShowCaret` at `0x18013c87b`
- `USER32!ShowCaret` at `0x18013c87b`
- `USER32!ValidateRect` at `0x18013c784`
- `USER32!ValidateRect` at `0x18013c846`
- `USER32!ValidateRect` at `0x18013c784`
- `USER32!ValidateRect` at `0x18013c846`
- `USER32!IsIconic` at `0x18013c496`
- `USER32!IsIconic` at `0x18013c496`
- `GDI32!GetClipBox` at `0x18013c4ce`
- `GDI32!GetClipBox` at `0x18013c4ce`
- `GDI32!InvertRgn` at `0x18013c6b8`
- `GDI32!InvertRgn` at `0x18013c741`
- `GDI32!InvertRgn` at `0x18013c6b8`
- `GDI32!InvertRgn` at `0x18013c741`
- `GDI32!CombineRgn` at `0x18013c732`
- `GDI32!CombineRgn` at `0x18013c732`
- `GDI32!SelectClipRgn` at `0x18013c500`
- `GDI32!SelectClipRgn` at `0x18013c500`
- `GDI32!CreateRectRgnIndirect` at `0x18013c70c`
- `GDI32!CreateRectRgnIndirect` at `0x18013c70c`
- `GDI32!ExtTextOutA` at `0x18013c5cf`
- `GDI32!ExtTextOutA` at `0x18013c674`
- `GDI32!ExtTextOutA` at `0x18013c5cf`
- `GDI32!ExtTextOutA` at `0x18013c674`
- `GDI32!SetBkColor` at `0x18013c596`
- `GDI32!SetBkColor` at `0x18013c63b`
- `GDI32!SetBkColor` at `0x18013c596`
- `GDI32!SetBkColor` at `0x18013c63b`
- `GDI32!DeleteObject` at `0x18013c74c`
- `GDI32!DeleteObject` at `0x18013c74c`

## pseudocode

```c
void __fastcall CPANE::Paint(CPANE *this, HDC a2, int a3, unsigned int a4, unsigned int a5)
{
  COLORREF ItemBackColor; // eax
  COLORREF v6; // eax
  EBAPP *v7; // rax
  unsigned int v8; // [rsp+40h] [rbp-80h]
  unsigned int v9; // [rsp+44h] [rbp-7Ch]
  LONG v10; // [rsp+48h] [rbp-78h]
  LONG v11; // [rsp+4Ch] [rbp-74h]
  HRGN hrgnDst; // [rsp+50h] [rbp-70h]
  RECT lprect; // [rsp+78h] [rbp-48h] BYREF
  RECT Rect; // [rsp+88h] [rbp-38h] BYREF
  RECT v15; // [rsp+98h] [rbp-28h] BYREF
  struct tagRECT rect; // [rsp+A8h] [rbp-18h] BYREF

  if ( !g_isParsing && !IsIconic(*((HWND *)this + 35)) )
  {
    if ( *((_DWORD *)this + 18) == 1 )
      HideCaret(*((HWND *)this + 35));
    if ( a3 )
    {
      GetClipBox(a2, &rect);
      v8 = CPANE::LnFromY(this, rect.top);
      v9 = CPANE::LnFromY(this, rect.bottom - 1);
    }
    else
    {
      SelectClipRgn(a2, 0);
      v8 = a4;
      v9 = a5;
    }
    if ( v9 < v8 )
      v9 = v8;
    if ( a3 )
    {
      lprect.top = *((_DWORD *)this + 20);
      lprect.bottom = *((_DWORD *)this + 24);
      lprect.left = *((_DWORD *)this + 19);
      if ( (unsigned int)CPANE::M_FMarginWidgets(this) )
        DrawMarginWidgetBarBackground(a2, &lprect);
      lprect.left = *((_DWORD *)this + 19) + CPANE::M_CxMarginWidgetBar(this);
      lprect.right = *((_DWORD *)this + 21);
      ItemBackColor = GetItemBackColor(0);
      SetBkColor(a2, ItemBackColor);
      ExtTextOutA(a2, 0, 0, 2u, &lprect, 0, 0, 0);
      lprect.top = *((_DWORD *)this + 26);
      lprect.bottom = *((_DWORD *)this + 22);
      lprect.left = *((_DWORD *)this + 19);
      if ( (unsigned int)CPANE::M_FMarginWidgets(this) )
        DrawMarginWidgetBarBackground(a2, &lprect);
      lprect.left = *((_DWORD *)this + 19) + CPANE::M_CxMarginWidgetBar(this);
      lprect.right = *((_DWORD *)this + 21);
      v6 = GetItemBackColor(0);
      SetBkColor(a2, v6);
      ExtTextOutA(a2, 0, 0, 2u, &lprect, 0, 0, 0);
    }
    CPANE::PaintLines(this, a2, v8, v9);
    if ( *((_QWORD *)this + 20) )
    {
      if ( a3 )
      {
        InvertRgn(a2, *((HRGN *)this + 20));
      }
      else
      {
        v15 = *(RECT *)((char *)this + 92);
        v15.top = CPANE::YFromLn(this, v8);
        v15.bottom = CPANE::YFromLn(this, v9 + 1);
        hrgnDst = CreateRectRgnIndirect(&v15);
        CombineRgn(hrgnDst, hrgnDst, *((HRGN *)this + 20), 1);
        InvertRgn(a2, hrgnDst);
        DeleteObject(hrgnDst);
      }
    }
    if ( a3 )
    {
      if ( *((_QWORD *)this + 8) )
        ValidateRect(*(HWND *)(*((_QWORD *)this + 8) + 32LL), (const RECT *)((char *)this + 76));
    }
    else
    {
      Rect.left = *((_DWORD *)this + 19);
      Rect.right = *((_DWORD *)this + 25);
      if ( (int)CPANE::YFromLn(this, v8) <= *((_DWORD *)this + 24) )
        v10 = *((_DWORD *)this + 24);
      else
        v10 = CPANE::YFromLn(this, v8);
      Rect.top = v10;
      if ( (int)CPANE::YFromLn(this, v9 + 1) >= *((_DWORD *)this + 26) )
        v11 = *((_DWORD *)this + 26);
      else
        v11 = CPANE::YFromLn(this, v9 + 1);
      Rect.bottom = v11;
      if ( *((_QWORD *)this + 8) )
        ValidateRect(*(HWND *)(*((_QWORD *)this + 8) + 32LL), &Rect);
    }
    if ( *((_DWORD *)this + 18) == 1 )
    {
      v7 = PebappCur();
      if ( (unsigned int)EBAPP::FIsBiDi(v7) )
        CPANE::RefreshCursorPos(this);
      ShowCaret(*((HWND *)this + 35));
    }
  }
}

```

## disassembly

```asm
0x18013c450  mov     [rsp-8+arg_18], r9d
0x18013c455  mov     [rsp-8+arg_10], r8d
0x18013c45a  mov     [rsp-8+hdc], rdx
0x18013c45f  mov     [rsp-8+arg_0], rcx
0x18013c464  push    rbp
0x18013c465  mov     rbp, rsp
0x18013c468  sub     rsp, 0C0h
0x18013c46f  mov     rax, cs:__security_cookie
0x18013c476  xor     rax, rsp
0x18013c479  mov     [rbp+var_8], rax
0x18013c47d  cmp     cs:?g_isParsing@@3HA, 0; int g_isParsing
0x18013c484  jz      short loc_18013C48B
0x18013c486  jmp     loc_18013C881
0x18013c48b  mov     rax, [rbp+arg_0]
0x18013c48f  mov     rcx, [rax+118h]; hWnd
0x18013c496  call    cs:__imp_IsIconic
0x18013c49c  test    eax, eax
0x18013c49e  jz      short loc_18013C4A5
0x18013c4a0  jmp     loc_18013C881
0x18013c4a5  mov     rax, [rbp+arg_0]
0x18013c4a9  cmp     dword ptr [rax+48h], 1
0x18013c4ad  jnz     short loc_18013C4C0
0x18013c4af  mov     rax, [rbp+arg_0]
0x18013c4b3  mov     rcx, [rax+118h]; hWnd
0x18013c4ba  call    cs:__imp_HideCaret
0x18013c4c0  cmp     [rbp+arg_10], 0
0x18013c4c4  jz      short loc_18013C4FA
0x18013c4c6  lea     rdx, [rbp+rect]; lprect
0x18013c4ca  mov     rcx, [rbp+hdc]; hdc
0x18013c4ce  call    cs:__imp_GetClipBox
0x18013c4d4  mov     edx, [rbp+rect.top]; int
0x18013c4d7  mov     rcx, [rbp+arg_0]; this
0x18013c4db  call    ?LnFromY@CPANE@@QEAAIH@Z; CPANE::LnFromY(int)
0x18013c4e0  mov     [rsp+0C0h+var_80], eax
0x18013c4e4  mov     eax, [rbp+rect.bottom]
0x18013c4e7  dec     eax
0x18013c4e9  mov     edx, eax; int
0x18013c4eb  mov     rcx, [rbp+arg_0]; this
0x18013c4ef  call    ?LnFromY@CPANE@@QEAAIH@Z; CPANE::LnFromY(int)
0x18013c4f4  mov     [rsp+0C0h+var_7C], eax
0x18013c4f8  jmp     short loc_18013C514
0x18013c4fa  xor     edx, edx; hrgn
0x18013c4fc  mov     rcx, [rbp+hdc]; hdc
0x18013c500  call    cs:__imp_SelectClipRgn
0x18013c506  mov     eax, [rbp+arg_18]
0x18013c509  mov     [rsp+0C0h+var_80], eax
0x18013c50d  mov     eax, [rbp+arg_20]
0x18013c510  mov     [rsp+0C0h+var_7C], eax
0x18013c514  mov     eax, [rsp+0C0h+var_80]
0x18013c518  cmp     [rsp+0C0h+var_7C], eax
0x18013c51c  jnb     short loc_18013C526
0x18013c51e  mov     eax, [rsp+0C0h+var_80]
0x18013c522  mov     [rsp+0C0h+var_7C], eax
0x18013c526  cmp     [rbp+arg_10], 0
0x18013c52a  jz      loc_18013C67A
0x18013c530  mov     rax, [rbp+arg_0]
0x18013c534  mov     eax, [rax+50h]
0x18013c537  mov     [rsp+0C0h+var_48.top], eax
0x18013c53b  mov     rax, [rbp+arg_0]
0x18013c53f  mov     eax, [rax+60h]
0x18013c542  mov     [rbp+var_48.bottom], eax
0x18013c545  mov     rax, [rbp+arg_0]
0x18013c549  mov     eax, [rax+4Ch]
0x18013c54c  mov     [rsp+0C0h+var_48.left], eax
0x18013c550  mov     rcx, [rbp+arg_0]; this
0x18013c554  call    ?M_FMarginWidgets@CPANE@@QEAAHXZ; CPANE::M_FMarginWidgets(void)
0x18013c559  test    eax, eax
0x18013c55b  jz      short loc_18013C56B
0x18013c55d  lea     rdx, [rsp+0C0h+var_48]; struct tagRECT *
0x18013c562  mov     rcx, [rbp+hdc]; HDC
0x18013c566  call    ?DrawMarginWidgetBarBackground@@YAXPEAUHDC__@@PEAUtagRECT@@@Z; DrawMarginWidgetBarBackground(HDC__ *,tagRECT *)
0x18013c56b  mov     rcx, [rbp+arg_0]; this
0x18013c56f  call    ?M_CxMarginWidgetBar@CPANE@@QEAAHXZ; CPANE::M_CxMarginWidgetBar(void)
0x18013c574  mov     rcx, [rbp+arg_0]
0x18013c578  add     eax, [rcx+4Ch]
0x18013c57b  mov     [rsp+0C0h+var_48.left], eax
0x18013c57f  mov     rax, [rbp+arg_0]
0x18013c583  mov     eax, [rax+54h]
0x18013c586  mov     [rbp+var_48.right], eax
0x18013c589  xor     ecx, ecx
0x18013c58b  call    GetItemBackColor
0x18013c590  mov     edx, eax; color
0x18013c592  mov     rcx, [rbp+hdc]; hdc
0x18013c596  call    cs:__imp_SetBkColor
0x18013c59c  mov     [rsp+0C0h+lpDx], 0; lpDx
0x18013c5a5  mov     [rsp+0C0h+c], 0; c
0x18013c5ad  mov     [rsp+0C0h+lpString], 0; lpString
0x18013c5b6  lea     rax, [rsp+0C0h+var_48]
0x18013c5bb  mov     [rsp+0C0h+lprect], rax; lprect
0x18013c5c0  mov     r9d, 2; options
0x18013c5c6  xor     r8d, r8d; y
0x18013c5c9  xor     edx, edx; x
0x18013c5cb  mov     rcx, [rbp+hdc]; hdc
0x18013c5cf  call    cs:__imp_ExtTextOutA
0x18013c5d5  mov     rax, [rbp+arg_0]
0x18013c5d9  mov     eax, [rax+68h]
0x18013c5dc  mov     [rsp+0C0h+var_48.top], eax
0x18013c5e0  mov     rax, [rbp+arg_0]
0x18013c5e4  mov     eax, [rax+58h]
0x18013c5e7  mov     [rbp+var_48.bottom], eax
0x18013c5ea  mov     rax, [rbp+arg_0]
0x18013c5ee  mov     eax, [rax+4Ch]
0x18013c5f1  mov     [rsp+0C0h+var_48.left], eax
0x18013c5f5  mov     rcx, [rbp+arg_0]; this
0x18013c5f9  call    ?M_FMarginWidgets@CPANE@@QEAAHXZ; CPANE::M_FMarginWidgets(void)
0x18013c5fe  test    eax, eax
0x18013c600  jz      short loc_18013C610
0x18013c602  lea     rdx, [rsp+0C0h+var_48]; struct tagRECT *
0x18013c607  mov     rcx, [rbp+hdc]; HDC
0x18013c60b  call    ?DrawMarginWidgetBarBackground@@YAXPEAUHDC__@@PEAUtagRECT@@@Z; DrawMarginWidgetBarBackground(HDC__ *,tagRECT *)
0x18013c610  mov     rcx, [rbp+arg_0]; this
0x18013c614  call    ?M_CxMarginWidgetBar@CPANE@@QEAAHXZ; CPANE::M_CxMarginWidgetBar(void)
0x18013c619  mov     rcx, [rbp+arg_0]
0x18013c61d  add     eax, [rcx+4Ch]
0x18013c620  mov     [rsp+0C0h+var_48.left], eax
0x18013c624  mov     rax, [rbp+arg_0]
0x18013c628  mov     eax, [rax+54h]
0x18013c62b  mov     [rbp+var_48.right], eax
0x18013c62e  xor     ecx, ecx
0x18013c630  call    GetItemBackColor
0x18013c635  mov     edx, eax; color
0x18013c637  mov     rcx, [rbp+hdc]; hdc
0x18013c63b  call    cs:__imp_SetBkColor
0x18013c641  mov     [rsp+0C0h+lpDx], 0; lpDx
0x18013c64a  mov     [rsp+0C0h+c], 0; c
0x18013c652  mov     [rsp+0C0h+lpString], 0; lpString
0x18013c65b  lea     rax, [rsp+0C0h+var_48]
0x18013c660  mov     [rsp+0C0h+lprect], rax; lprect
0x18013c665  mov     r9d, 2; options
0x18013c66b  xor     r8d, r8d; y
0x18013c66e  xor     edx, edx; x
0x18013c670  mov     rcx, [rbp+hdc]; hdc
0x18013c674  call    cs:__imp_ExtTextOutA
0x18013c67a  mov     r9d, [rsp+0C0h+var_7C]; unsigned int
0x18013c67f  mov     r8d, [rsp+0C0h+var_80]; unsigned int
0x18013c684  mov     rdx, [rbp+hdc]; HDC
0x18013c688  mov     rcx, [rbp+arg_0]; this
0x18013c68c  call    ?PaintLines@CPANE@@QEAAXPEAUHDC__@@II@Z; CPANE::PaintLines(HDC__ *,uint,uint)
0x18013c691  mov     rax, [rbp+arg_0]
0x18013c695  cmp     qword ptr [rax+0A0h], 0
0x18013c69d  jz      loc_18013C752
0x18013c6a3  cmp     [rbp+arg_10], 0
0x18013c6a7  jz      short loc_18013C6C3
0x18013c6a9  mov     rax, [rbp+arg_0]
0x18013c6ad  mov     rdx, [rax+0A0h]; hrgn
0x18013c6b4  mov     rcx, [rbp+hdc]; hdc
0x18013c6b8  call    cs:__imp_InvertRgn
0x18013c6be  jmp     loc_18013C752
0x18013c6c3  mov     rax, [rbp+arg_0]
0x18013c6c7  movups  xmm0, xmmword ptr [rax+5Ch]
0x18013c6cb  movdqu  [rsp+0C0h+var_58], xmm0
0x18013c6d1  movups  xmm0, [rsp+0C0h+var_58]
0x18013c6d6  movdqu  xmmword ptr [rbp+var_28.left], xmm0
0x18013c6db  mov     [rsp+0C0h+hrgnDst], 0
0x18013c6e4  mov     edx, [rsp+0C0h+var_80]; unsigned int
0x18013c6e8  mov     rcx, [rbp+arg_0]; this
0x18013c6ec  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x18013c6f1  mov     [rbp+var_28.top], eax
0x18013c6f4  mov     eax, [rsp+0C0h+var_7C]
0x18013c6f8  inc     eax
0x18013c6fa  mov     edx, eax; unsigned int
0x18013c6fc  mov     rcx, [rbp+arg_0]; this
0x18013c700  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x18013c705  mov     [rbp+var_28.bottom], eax
0x18013c708  lea     rcx, [rbp+var_28]; lprect
0x18013c70c  call    cs:__imp_CreateRectRgnIndirect
0x18013c712  mov     [rsp+0C0h+hrgnDst], rax
0x18013c717  mov     r9d, 1; iMode
0x18013c71d  mov     rax, [rbp+arg_0]
0x18013c721  mov     r8, [rax+0A0h]; hrgnSrc2
0x18013c728  mov     rdx, [rsp+0C0h+hrgnDst]; hrgnSrc1
0x18013c72d  mov     rcx, [rsp+0C0h+hrgnDst]; hrgnDst
0x18013c732  call    cs:__imp_CombineRgn
0x18013c738  mov     rdx, [rsp+0C0h+hrgnDst]; hrgn
0x18013c73d  mov     rcx, [rbp+hdc]; hdc
0x18013c741  call    cs:__imp_InvertRgn
0x18013c747  mov     rcx, [rsp+0C0h+hrgnDst]; ho
0x18013c74c  call    cs:__imp_DeleteObject
0x18013c752  cmp     [rbp+arg_10], 0
0x18013c756  jz      short loc_18013C78F
0x18013c758  mov     rax, [rbp+arg_0]
0x18013c75c  cmp     qword ptr [rax+40h], 0
0x18013c761  jz      short loc_18013C78A
0x18013c763  mov     rax, [rbp+arg_0]
0x18013c767  mov     rax, [rax+40h]
0x18013c76b  mov     [rsp+0C0h+var_68], rax
0x18013c770  mov     rax, [rbp+arg_0]
0x18013c774  add     rax, 4Ch ; 'L'
0x18013c778  mov     rdx, rax; lpRect
0x18013c77b  mov     rax, [rsp+0C0h+var_68]
0x18013c780  mov     rcx, [rax+20h]; hWnd
0x18013c784  call    cs:__imp_ValidateRect
0x18013c78a  jmp     loc_18013C84C
0x18013c78f  mov     rax, [rbp+arg_0]
0x18013c793  mov     eax, [rax+4Ch]
0x18013c796  mov     [rbp+Rect.left], eax
0x18013c799  mov     rax, [rbp+arg_0]
0x18013c79d  mov     eax, [rax+64h]
0x18013c7a0  mov     [rbp+Rect.right], eax
0x18013c7a3  mov     edx, [rsp+0C0h+var_80]; unsigned int
0x18013c7a7  mov     rcx, [rbp+arg_0]; this
0x18013c7ab  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x18013c7b0  mov     rcx, [rbp+arg_0]
0x18013c7b4  cmp     eax, [rcx+60h]
0x18013c7b7  jle     short loc_18013C7CC
0x18013c7b9  mov     edx, [rsp+0C0h+var_80]; unsigned int
0x18013c7bd  mov     rcx, [rbp+arg_0]; this
0x18013c7c1  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x18013c7c6  mov     [rsp+0C0h+var_78], eax
0x18013c7ca  jmp     short loc_18013C7D7
0x18013c7cc  mov     rax, [rbp+arg_0]
0x18013c7d0  mov     eax, [rax+60h]
0x18013c7d3  mov     [rsp+0C0h+var_78], eax
0x18013c7d7  mov     eax, [rsp+0C0h+var_78]
0x18013c7db  mov     [rbp+Rect.top], eax
0x18013c7de  mov     eax, [rsp+0C0h+var_7C]
0x18013c7e2  inc     eax
0x18013c7e4  mov     edx, eax; unsigned int
0x18013c7e6  mov     rcx, [rbp+arg_0]; this
0x18013c7ea  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x18013c7ef  mov     rcx, [rbp+arg_0]
0x18013c7f3  cmp     eax, [rcx+68h]
0x18013c7f6  jge     short loc_18013C80F
0x18013c7f8  mov     eax, [rsp+0C0h+var_7C]
0x18013c7fc  inc     eax
0x18013c7fe  mov     edx, eax; unsigned int
0x18013c800  mov     rcx, [rbp+arg_0]; this
0x18013c804  call    ?YFromLn@CPANE@@QEAAHI@Z; CPANE::YFromLn(uint)
0x18013c809  mov     [rsp+0C0h+var_74], eax
0x18013c80d  jmp     short loc_18013C81A
0x18013c80f  mov     rax, [rbp+arg_0]
0x18013c813  mov     eax, [rax+68h]
0x18013c816  mov     [rsp+0C0h+var_74], eax
0x18013c81a  mov     eax, [rsp+0C0h+var_74]
0x18013c81e  mov     [rbp+Rect.bottom], eax
0x18013c821  mov     rax, [rbp+arg_0]
0x18013c825  cmp     qword ptr [rax+40h], 0
0x18013c82a  jz      short loc_18013C84C
0x18013c82c  mov     rax, [rbp+arg_0]
0x18013c830  mov     rax, [rax+40h]
0x18013c834  mov     [rsp+0C0h+var_60], rax
0x18013c839  lea     rdx, [rbp+Rect]; lpRect
0x18013c83d  mov     rax, [rsp+0C0h+var_60]
0x18013c842  mov     rcx, [rax+20h]; hWnd
0x18013c846  call    cs:__imp_ValidateRect
0x18013c84c  mov     rax, [rbp+arg_0]
0x18013c850  cmp     dword ptr [rax+48h], 1
0x18013c854  jnz     short loc_18013C881
0x18013c856  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18013c85b  mov     rcx, rax; this
0x18013c85e  call    ?FIsBiDi@EBAPP@@QEAAHXZ; EBAPP::FIsBiDi(void)
0x18013c863  test    eax, eax
0x18013c865  jz      short loc_18013C870
0x18013c867  mov     rcx, [rbp+arg_0]; this
0x18013c86b  call    ?RefreshCursorPos@CPANE@@QEAAXXZ; CPANE::RefreshCursorPos(void)
0x18013c870  mov     rax, [rbp+arg_0]
0x18013c874  mov     rcx, [rax+118h]; hWnd
0x18013c87b  call    cs:__imp_ShowCaret
0x18013c881  mov     rcx, [rbp+var_8]
0x18013c885  xor     rcx, rsp; StackCookie
0x18013c888  call    __security_check_cookie
0x18013c88d  add     rsp, 0C0h
0x18013c894  pop     rbp
0x18013c895  retn
```
