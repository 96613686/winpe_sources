# LPANE::DrawTitle(HDC__ *)

- ea: `0x18023134c`
- end: `0x180231a41`
- name: `?DrawTitle@LPANE@@IEAAXPEAUHDC__@@@Z`
- size: `1781`
- prototype: `void __fastcall(LPANE *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18022fe6c`

## callees

- `0x18000465c`
- `0x1800e6178`
- `0x18023134c`
- `0x180379520`

## import_xrefs

- `USER32!FillRect` at `0x180231556`
- `USER32!FillRect` at `0x180231556`
- `USER32!GetSysColor` at `0x180231410`
- `USER32!GetSysColor` at `0x180231444`
- `USER32!GetSysColor` at `0x180231476`
- `USER32!GetSysColor` at `0x1802314a8`
- `USER32!GetSysColor` at `0x1802314da`
- `USER32!GetSysColor` at `0x1802315b0`
- `USER32!GetSysColor` at `0x180231410`
- `USER32!GetSysColor` at `0x180231444`
- `USER32!GetSysColor` at `0x180231476`
- `USER32!GetSysColor` at `0x1802314a8`
- `USER32!GetSysColor` at `0x1802314da`
- `USER32!GetSysColor` at `0x1802315b0`
- `GDI32!LineTo` at `0x1802315a5`
- `GDI32!LineTo` at `0x18023163b`
- `GDI32!LineTo` at `0x1802316f0`
- `GDI32!LineTo` at `0x180231767`
- `GDI32!LineTo` at `0x1802317de`
- `GDI32!LineTo` at `0x180231972`
- `GDI32!LineTo` at `0x1802315a5`
- `GDI32!LineTo` at `0x18023163b`
- `GDI32!LineTo` at `0x1802316f0`
- `GDI32!LineTo` at `0x180231767`
- `GDI32!LineTo` at `0x1802317de`
- `GDI32!LineTo` at `0x180231972`
- `GDI32!MoveToEx` at `0x180231590`
- `GDI32!MoveToEx` at `0x180231622`
- `GDI32!MoveToEx` at `0x1802316c7`
- `GDI32!MoveToEx` at `0x18023173c`
- `GDI32!MoveToEx` at `0x1802317b3`
- `GDI32!MoveToEx` at `0x18023195d`
- `GDI32!MoveToEx` at `0x180231590`
- `GDI32!MoveToEx` at `0x180231622`
- `GDI32!MoveToEx` at `0x1802316c7`
- `GDI32!MoveToEx` at `0x18023173c`
- `GDI32!MoveToEx` at `0x1802317b3`
- `GDI32!MoveToEx` at `0x18023195d`
- `GDI32!ExtTextOutA` at `0x180231928`
- `GDI32!ExtTextOutA` at `0x180231928`
- `GDI32!SetBkMode` at `0x1802313fc`
- `GDI32!SetBkMode` at `0x180231996`
- `GDI32!SetBkMode` at `0x1802313fc`
- `GDI32!SetBkMode` at `0x180231996`
- `GDI32!SelectObject` at `0x180231508`
- `GDI32!SelectObject` at `0x18023152c`
- `GDI32!SelectObject` at `0x180231565`
- `GDI32!SelectObject` at `0x1802315d1`
- `GDI32!SelectObject` at `0x1802315f7`
- `GDI32!SelectObject` at `0x180231687`
- `GDI32!SelectObject` at `0x1802316ff`
- `GDI32!SelectObject` at `0x180231776`
- `GDI32!SelectObject` at `0x18023193c`
- `GDI32!SelectObject` at `0x180231989`
- `GDI32!SelectObject` at `0x1802319ad`
- `GDI32!SelectObject` at `0x1802319c2`
- `GDI32!SelectObject` at `0x180231508`
- `GDI32!SelectObject` at `0x18023152c`
- `GDI32!SelectObject` at `0x180231565`
- `GDI32!SelectObject` at `0x1802315d1`
- `GDI32!SelectObject` at `0x1802315f7`
- `GDI32!SelectObject` at `0x180231687`
- `GDI32!SelectObject` at `0x1802316ff`
- `GDI32!SelectObject` at `0x180231776`
- `GDI32!SelectObject` at `0x18023193c`
- `GDI32!SelectObject` at `0x180231989`
- `GDI32!SelectObject` at `0x1802319ad`
- `GDI32!SelectObject` at `0x1802319c2`
- `GDI32!SetTextColor` at `0x1802315bc`
- `GDI32!SetTextColor` at `0x180231a26`
- `GDI32!SetTextColor` at `0x1802315bc`
- `GDI32!SetTextColor` at `0x180231a26`
- `GDI32!DeleteObject` at `0x1802319d5`
- `GDI32!DeleteObject` at `0x1802319e8`
- `GDI32!DeleteObject` at `0x1802319fb`
- `GDI32!DeleteObject` at `0x180231a0e`
- `GDI32!DeleteObject` at `0x1802319d5`
- `GDI32!DeleteObject` at `0x1802319e8`
- `GDI32!DeleteObject` at `0x1802319fb`
- `GDI32!DeleteObject` at `0x180231a0e`
- `GDI32!CreateSolidBrush` at `0x1802314e2`
- `GDI32!CreateSolidBrush` at `0x1802314e2`
- `GDI32!CreatePen` at `0x180231420`
- `GDI32!CreatePen` at `0x180231454`
- `GDI32!CreatePen` at `0x180231486`
- `GDI32!CreatePen` at `0x1802314b8`
- `GDI32!CreatePen` at `0x180231420`
- `GDI32!CreatePen` at `0x180231454`
- `GDI32!CreatePen` at `0x180231486`
- `GDI32!CreatePen` at `0x1802314b8`

## pseudocode

```c
void __fastcall LPANE::DrawTitle(LPANE *this, HDC a2)
{
  COLORREF SysColor; // eax
  COLORREF v3; // eax
  COLORREF v4; // eax
  COLORREF v5; // eax
  COLORREF v6; // eax
  COLORREF v7; // eax
  UINT c; // eax
  int i; // [rsp+40h] [rbp-90h]
  int j; // [rsp+44h] [rbp-8Ch]
  HPEN Pen; // [rsp+48h] [rbp-88h]
  COLORREF color; // [rsp+50h] [rbp-80h]
  HPEN h; // [rsp+58h] [rbp-78h]
  HBRUSH ho; // [rsp+60h] [rbp-70h]
  HPEN v15; // [rsp+68h] [rbp-68h]
  HGDIOBJ v16; // [rsp+70h] [rbp-60h]
  HGDIOBJ v17; // [rsp+78h] [rbp-58h]
  HGDIOBJ v18; // [rsp+80h] [rbp-50h]
  unsigned __int64 v19; // [rsp+88h] [rbp-48h]
  int mode; // [rsp+90h] [rbp-40h]
  int v21; // [rsp+98h] [rbp-38h]
  RECT rc; // [rsp+B8h] [rbp-18h] BYREF

  v16 = 0;
  h = 0;
  v15 = 0;
  v18 = 0;
  ho = 0;
  v17 = 0;
  color = 0x80000000;
  v21 = (*(_DWORD *)(*((_QWORD *)PebappCur() + 1) + 1072LL) >> 5) & 1;
  rc = *(RECT *)((char *)this + 44);
  rc.bottom = rc.top + LPANE::m_cyTitle - 1;
  mode = SetBkMode(a2, 1);
  if ( v21 )
  {
    SysColor = GetSysColor(21);
    Pen = CreatePen(0, 1, SysColor);
    if ( !Pen )
      goto LABEL_35;
  }
  else
  {
    v3 = GetSysColor(6);
    Pen = CreatePen(0, 1, v3);
    if ( !Pen )
      goto LABEL_35;
  }
  v4 = GetSysColor(16);
  h = CreatePen(0, 1, v4);
  if ( h )
  {
    v5 = GetSysColor(20);
    v15 = CreatePen(0, 1, v5);
    if ( v15 )
    {
      v6 = GetSysColor(15);
      ho = CreateSolidBrush(v6);
      if ( ho )
      {
        v18 = SelectObject(a2, h);
        if ( v18 )
        {
          v17 = SelectObject(a2, ho);
          if ( v17 )
          {
            FillRect(a2, &rc, ho);
            if ( SelectObject(a2, v15) )
            {
              MoveToEx(a2, *((_DWORD *)this + 11) + 1, rc.top, 0);
              LineTo(a2, *((_DWORD *)this + 13), rc.top);
              v7 = GetSysColor(18);
              color = SetTextColor(a2, v7);
              v16 = SelectObject(a2, g_hfontLPANETitle);
              if ( v16 )
              {
                if ( SelectObject(a2, h) )
                {
                  MoveToEx(a2, *((_DWORD *)this + 11), rc.bottom - 1, 0);
                  LineTo(a2, *((_DWORD *)this + 13), rc.bottom - 1);
                  for ( i = 0; i < *((__int16 *)this + 32); ++i )
                  {
                    if ( *((_DWORD *)this + i + 42) )
                    {
                      if ( !SelectObject(a2, h) )
                        goto LABEL_35;
                      MoveToEx(a2, *((_DWORD *)this + i + 37) + *((_DWORD *)this + 11), rc.top + 1, 0);
                      LineTo(a2, *((_DWORD *)this + i + 37) + *((_DWORD *)this + 11), rc.bottom);
                      if ( !SelectObject(a2, Pen) )
                        goto LABEL_35;
                      MoveToEx(a2, *((_DWORD *)this + 11) + *((_DWORD *)this + i + 37) + 1, rc.top, 0);
                      LineTo(a2, *((_DWORD *)this + 11) + *((_DWORD *)this + i + 37) + 1, rc.bottom);
                      if ( !SelectObject(a2, v15) )
                        goto LABEL_35;
                      MoveToEx(a2, *((_DWORD *)this + 11) + *((_DWORD *)this + i + 37) + 2, rc.top, 0);
                      LineTo(a2, *((_DWORD *)this + 11) + *((_DWORD *)this + i + 37) + 2, rc.bottom);
                      rc.left = *((_DWORD *)this + 11) + *((_DWORD *)this + i + 37) + 3;
                    }
                    else
                    {
                      rc.left = *((_DWORD *)this + i + 37) + *((_DWORD *)this + 11);
                    }
                    for ( j = i + 1; j < *((__int16 *)this + 32) && !*((_DWORD *)this + j + 42); ++j )
                      ;
                    if ( j >= *((__int16 *)this + 32) )
                      rc.right = *((_DWORD *)this + 13);
                    else
                      rc.right = *((_DWORD *)this + j + 37) + *((_DWORD *)this + 11);
                    if ( *((_QWORD *)this + i + 11) )
                    {
                      v19 = -1;
                      do
                        ++v19;
                      while ( *(_BYTE *)(*((_QWORD *)this + i + 11) + v19) );
                      c = UINT32FromUINT64(v19);
                      ExtTextOutA(a2, rc.left + 3, rc.top + 1, 4u, &rc, *((LPCSTR *)this + i + 11), c, 0);
                    }
                  }
                  if ( SelectObject(a2, Pen) )
                  {
                    MoveToEx(a2, *((_DWORD *)this + 11), rc.bottom, 0);
                    LineTo(a2, *((_DWORD *)this + 13), rc.bottom);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_35:
  if ( v16 )
    SelectObject(a2, v16);
  SetBkMode(a2, mode);
  if ( v17 )
    SelectObject(a2, v17);
  if ( v18 )
    SelectObject(a2, v18);
  if ( ho )
    DeleteObject(ho);
  if ( h )
    DeleteObject(h);
  if ( Pen )
    DeleteObject(Pen);
  if ( v15 )
    DeleteObject(v15);
  if ( color != 0x80000000 )
    SetTextColor(a2, color);
}

```

## disassembly

```asm
0x18023134c  mov     [rsp-8+hdc], rdx
0x180231351  mov     [rsp-8+arg_0], rcx
0x180231356  push    rbp
0x180231357  mov     rbp, rsp
0x18023135a  sub     rsp, 0D0h
0x180231361  mov     rax, cs:__security_cookie
0x180231368  xor     rax, rsp
0x18023136b  mov     [rbp+var_8], rax
0x18023136f  mov     [rsp+0D0h+var_60], 0
0x180231378  mov     [rsp+0D0h+h], 0
0x180231381  mov     [rsp+0D0h+var_88], 0
0x18023138a  mov     [rsp+0D0h+var_68], 0
0x180231393  mov     [rbp+var_50], 0
0x18023139b  mov     [rsp+0D0h+ho], 0
0x1802313a4  mov     [rsp+0D0h+var_58], 0
0x1802313ad  mov     [rsp+0D0h+color], 80000000h
0x1802313b5  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x1802313ba  mov     rax, [rax+8]
0x1802313be  mov     eax, [rax+430h]
0x1802313c4  shr     eax, 5
0x1802313c7  and     eax, 1
0x1802313ca  mov     [rbp+var_38], eax
0x1802313cd  mov     rax, [rbp+arg_0]
0x1802313d1  movups  xmm0, xmmword ptr [rax+2Ch]
0x1802313d5  movdqu  [rbp+var_28], xmm0
0x1802313da  movups  xmm0, [rbp+var_28]
0x1802313de  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x1802313e3  mov     eax, [rbp+rc.top]
0x1802313e6  mov     ecx, cs:?m_cyTitle@LPANE@@1HA; int LPANE::m_cyTitle
0x1802313ec  lea     eax, [rax+rcx-1]
0x1802313f0  mov     [rbp+rc.bottom], eax
0x1802313f3  mov     edx, 1; mode
0x1802313f8  mov     rcx, [rbp+hdc]; hdc
0x1802313fc  call    cs:__imp_SetBkMode
0x180231402  mov     [rbp+mode], eax
0x180231405  cmp     [rbp+var_38], 0
0x180231409  jz      short loc_18023143F
0x18023140b  mov     ecx, 15h; nIndex
0x180231410  call    cs:__imp_GetSysColor
0x180231416  mov     r8d, eax; color
0x180231419  mov     edx, 1; cWidth
0x18023141e  xor     ecx, ecx; iStyle
0x180231420  call    cs:__imp_CreatePen
0x180231426  mov     [rsp+0D0h+var_88], rax
0x18023142b  cmp     [rsp+0D0h+var_88], 0
0x180231431  jnz     short loc_18023143D
0x180231433  jmp     loc_180231978
0x180231438  jmp     loc_180231978
0x18023143d  jmp     short loc_180231471
0x18023143f  mov     ecx, 6; nIndex
0x180231444  call    cs:__imp_GetSysColor
0x18023144a  mov     r8d, eax; color
0x18023144d  mov     edx, 1; cWidth
0x180231452  xor     ecx, ecx; iStyle
0x180231454  call    cs:__imp_CreatePen
0x18023145a  mov     [rsp+0D0h+var_88], rax
0x18023145f  cmp     [rsp+0D0h+var_88], 0
0x180231465  jnz     short loc_180231471
0x180231467  jmp     loc_180231978
0x18023146c  jmp     loc_180231978
0x180231471  mov     ecx, 10h; nIndex
0x180231476  call    cs:__imp_GetSysColor
0x18023147c  mov     r8d, eax; color
0x18023147f  mov     edx, 1; cWidth
0x180231484  xor     ecx, ecx; iStyle
0x180231486  call    cs:__imp_CreatePen
0x18023148c  mov     [rsp+0D0h+h], rax
0x180231491  cmp     [rsp+0D0h+h], 0
0x180231497  jnz     short loc_1802314A3
0x180231499  jmp     loc_180231978
0x18023149e  jmp     loc_180231978
0x1802314a3  mov     ecx, 14h; nIndex
0x1802314a8  call    cs:__imp_GetSysColor
0x1802314ae  mov     r8d, eax; color
0x1802314b1  mov     edx, 1; cWidth
0x1802314b6  xor     ecx, ecx; iStyle
0x1802314b8  call    cs:__imp_CreatePen
0x1802314be  mov     [rsp+0D0h+var_68], rax
0x1802314c3  cmp     [rsp+0D0h+var_68], 0
0x1802314c9  jnz     short loc_1802314D5
0x1802314cb  jmp     loc_180231978
0x1802314d0  jmp     loc_180231978
0x1802314d5  mov     ecx, 0Fh; nIndex
0x1802314da  call    cs:__imp_GetSysColor
0x1802314e0  mov     ecx, eax; color
0x1802314e2  call    cs:__imp_CreateSolidBrush
0x1802314e8  mov     [rsp+0D0h+ho], rax
0x1802314ed  cmp     [rsp+0D0h+ho], 0
0x1802314f3  jnz     short loc_1802314FF
0x1802314f5  jmp     loc_180231978
0x1802314fa  jmp     loc_180231978
0x1802314ff  mov     rdx, [rsp+0D0h+h]; h
0x180231504  mov     rcx, [rbp+hdc]; hdc
0x180231508  call    cs:__imp_SelectObject
0x18023150e  mov     [rbp+var_50], rax
0x180231512  cmp     [rbp+var_50], 0
0x180231517  jnz     short loc_180231523
0x180231519  jmp     loc_180231978
0x18023151e  jmp     loc_180231978
0x180231523  mov     rdx, [rsp+0D0h+ho]; h
0x180231528  mov     rcx, [rbp+hdc]; hdc
0x18023152c  call    cs:__imp_SelectObject
0x180231532  mov     [rsp+0D0h+var_58], rax
0x180231537  cmp     [rsp+0D0h+var_58], 0
0x18023153d  jnz     short loc_180231549
0x18023153f  jmp     loc_180231978
0x180231544  jmp     loc_180231978
0x180231549  mov     r8, [rsp+0D0h+ho]; hbr
0x18023154e  lea     rdx, [rbp+rc]; lprc
0x180231552  mov     rcx, [rbp+hdc]; hDC
0x180231556  call    cs:__imp_FillRect
0x18023155c  mov     rdx, [rsp+0D0h+var_68]; h
0x180231561  mov     rcx, [rbp+hdc]; hdc
0x180231565  call    cs:__imp_SelectObject
0x18023156b  test    rax, rax
0x18023156e  jnz     short loc_18023157A
0x180231570  jmp     loc_180231978
0x180231575  jmp     loc_180231978
0x18023157a  mov     rax, [rbp+arg_0]
0x18023157e  mov     eax, [rax+2Ch]
0x180231581  inc     eax
0x180231583  xor     r9d, r9d; lppt
0x180231586  mov     r8d, [rbp+rc.top]; y
0x18023158a  mov     edx, eax; x
0x18023158c  mov     rcx, [rbp+hdc]; hdc
0x180231590  call    cs:__imp_MoveToEx
0x180231596  mov     r8d, [rbp+rc.top]; y
0x18023159a  mov     rax, [rbp+arg_0]
0x18023159e  mov     edx, [rax+34h]; x
0x1802315a1  mov     rcx, [rbp+hdc]; hdc
0x1802315a5  call    cs:__imp_LineTo
0x1802315ab  mov     ecx, 12h; nIndex
0x1802315b0  call    cs:__imp_GetSysColor
0x1802315b6  mov     edx, eax; color
0x1802315b8  mov     rcx, [rbp+hdc]; hdc
0x1802315bc  call    cs:__imp_SetTextColor
0x1802315c2  mov     [rsp+0D0h+color], eax
0x1802315c6  mov     rdx, cs:?g_hfontLPANETitle@@3PEAUHFONT__@@EA; h
0x1802315cd  mov     rcx, [rbp+hdc]; hdc
0x1802315d1  call    cs:__imp_SelectObject
0x1802315d7  mov     [rsp+0D0h+var_60], rax
0x1802315dc  cmp     [rsp+0D0h+var_60], 0
0x1802315e2  jnz     short loc_1802315EE
0x1802315e4  jmp     loc_180231978
0x1802315e9  jmp     loc_180231978
0x1802315ee  mov     rdx, [rsp+0D0h+h]; h
0x1802315f3  mov     rcx, [rbp+hdc]; hdc
0x1802315f7  call    cs:__imp_SelectObject
0x1802315fd  test    rax, rax
0x180231600  jnz     short loc_18023160C
0x180231602  jmp     loc_180231978
0x180231607  jmp     loc_180231978
0x18023160c  mov     eax, [rbp+rc.bottom]
0x18023160f  dec     eax
0x180231611  xor     r9d, r9d; lppt
0x180231614  mov     r8d, eax; y
0x180231617  mov     rax, [rbp+arg_0]
0x18023161b  mov     edx, [rax+2Ch]; x
0x18023161e  mov     rcx, [rbp+hdc]; hdc
0x180231622  call    cs:__imp_MoveToEx
0x180231628  mov     eax, [rbp+rc.bottom]
0x18023162b  dec     eax
0x18023162d  mov     r8d, eax; y
0x180231630  mov     rax, [rbp+arg_0]
0x180231634  mov     edx, [rax+34h]; x
0x180231637  mov     rcx, [rbp+hdc]; hdc
0x18023163b  call    cs:__imp_LineTo
0x180231641  mov     [rsp+0D0h+var_90], 0
0x180231649  jmp     short loc_180231655
0x18023164b  mov     eax, [rsp+0D0h+var_90]
0x18023164f  inc     eax
0x180231651  mov     [rsp+0D0h+var_90], eax
0x180231655  mov     rax, [rbp+arg_0]
0x180231659  movsx   eax, word ptr [rax+40h]
0x18023165d  cmp     [rsp+0D0h+var_90], eax
0x180231661  jge     loc_180231933
0x180231667  movsxd  rax, [rsp+0D0h+var_90]
0x18023166c  mov     rcx, [rbp+arg_0]
0x180231670  cmp     dword ptr [rcx+rax*4+0A8h], 0
0x180231678  jz      loc_180231804
0x18023167e  mov     rdx, [rsp+0D0h+h]; h
0x180231683  mov     rcx, [rbp+hdc]; hdc
0x180231687  call    cs:__imp_SelectObject
0x18023168d  test    rax, rax
0x180231690  jnz     short loc_18023169C
0x180231692  jmp     loc_180231978
0x180231697  jmp     loc_180231978
0x18023169c  mov     eax, [rbp+rc.top]
0x18023169f  inc     eax
0x1802316a1  movsxd  rcx, [rsp+0D0h+var_90]
0x1802316a6  mov     rdx, [rbp+arg_0]
0x1802316aa  mov     edx, [rdx+2Ch]
0x1802316ad  mov     r8, [rbp+arg_0]
0x1802316b1  add     edx, [r8+rcx*4+94h]
0x1802316b9  mov     ecx, edx
0x1802316bb  xor     r9d, r9d; lppt
0x1802316be  mov     r8d, eax; y
0x1802316c1  mov     edx, ecx; x
0x1802316c3  mov     rcx, [rbp+hdc]; hdc
0x1802316c7  call    cs:__imp_MoveToEx
0x1802316cd  movsxd  rax, [rsp+0D0h+var_90]
0x1802316d2  mov     rcx, [rbp+arg_0]
0x1802316d6  mov     ecx, [rcx+2Ch]
0x1802316d9  mov     rdx, [rbp+arg_0]
0x1802316dd  add     ecx, [rdx+rax*4+94h]
0x1802316e4  mov     eax, ecx
0x1802316e6  mov     r8d, [rbp+rc.bottom]; y
0x1802316ea  mov     edx, eax; x
0x1802316ec  mov     rcx, [rbp+hdc]; hdc
0x1802316f0  call    cs:__imp_LineTo
0x1802316f6  mov     rdx, [rsp+0D0h+var_88]; h
0x1802316fb  mov     rcx, [rbp+hdc]; hdc
0x1802316ff  call    cs:__imp_SelectObject
0x180231705  test    rax, rax
0x180231708  jnz     short loc_180231714
0x18023170a  jmp     loc_180231978
0x18023170f  jmp     loc_180231978
0x180231714  movsxd  rax, [rsp+0D0h+var_90]
0x180231719  mov     rcx, [rbp+arg_0]
0x18023171d  mov     ecx, [rcx+2Ch]
0x180231720  mov     rdx, [rbp+arg_0]
0x180231724  mov     eax, [rdx+rax*4+94h]
0x18023172b  lea     eax, [rcx+rax+1]
0x18023172f  xor     r9d, r9d; lppt
0x180231732  mov     r8d, [rbp+rc.top]; y
0x180231736  mov     edx, eax; x
0x180231738  mov     rcx, [rbp+hdc]; hdc
0x18023173c  call    cs:__imp_MoveToEx
0x180231742  movsxd  rax, [rsp+0D0h+var_90]
0x180231747  mov     rcx, [rbp+arg_0]
0x18023174b  mov     ecx, [rcx+2Ch]
0x18023174e  mov     rdx, [rbp+arg_0]
0x180231752  mov     eax, [rdx+rax*4+94h]
0x180231759  lea     eax, [rcx+rax+1]
0x18023175d  mov     r8d, [rbp+rc.bottom]; y
0x180231761  mov     edx, eax; x
0x180231763  mov     rcx, [rbp+hdc]; hdc
0x180231767  call    cs:__imp_LineTo
0x18023176d  mov     rdx, [rsp+0D0h+var_68]; h
0x180231772  mov     rcx, [rbp+hdc]; hdc
0x180231776  call    cs:__imp_SelectObject
0x18023177c  test    rax, rax
0x18023177f  jnz     short loc_18023178B
0x180231781  jmp     loc_180231978
0x180231786  jmp     loc_180231978
0x18023178b  movsxd  rax, [rsp+0D0h+var_90]
0x180231790  mov     rcx, [rbp+arg_0]
0x180231794  mov     ecx, [rcx+2Ch]
0x180231797  mov     rdx, [rbp+arg_0]
0x18023179b  mov     eax, [rdx+rax*4+94h]
0x1802317a2  lea     eax, [rcx+rax+2]
0x1802317a6  xor     r9d, r9d; lppt
0x1802317a9  mov     r8d, [rbp+rc.top]; y
0x1802317ad  mov     edx, eax; x
0x1802317af  mov     rcx, [rbp+hdc]; hdc
0x1802317b3  call    cs:__imp_MoveToEx
0x1802317b9  movsxd  rax, [rsp+0D0h+var_90]
0x1802317be  mov     rcx, [rbp+arg_0]
0x1802317c2  mov     ecx, [rcx+2Ch]
0x1802317c5  mov     rdx, [rbp+arg_0]
0x1802317c9  mov     eax, [rdx+rax*4+94h]
0x1802317d0  lea     eax, [rcx+rax+2]
0x1802317d4  mov     r8d, [rbp+rc.bottom]; y
0x1802317d8  mov     edx, eax; x
0x1802317da  mov     rcx, [rbp+hdc]; hdc
0x1802317de  call    cs:__imp_LineTo
0x1802317e4  movsxd  rax, [rsp+0D0h+var_90]
0x1802317e9  mov     rcx, [rbp+arg_0]
0x1802317ed  mov     ecx, [rcx+2Ch]
0x1802317f0  mov     rdx, [rbp+arg_0]
0x1802317f4  mov     eax, [rdx+rax*4+94h]
0x1802317fb  lea     eax, [rcx+rax+3]
0x1802317ff  mov     [rbp+rc.left], eax
0x180231802  jmp     short loc_180231820
0x180231804  movsxd  rax, [rsp+0D0h+var_90]
0x180231809  mov     rcx, [rbp+arg_0]
0x18023180d  mov     ecx, [rcx+2Ch]
0x180231810  mov     rdx, [rbp+arg_0]
0x180231814  add     ecx, [rdx+rax*4+94h]
0x18023181b  mov     eax, ecx
0x18023181d  mov     [rbp+rc.left], eax
0x180231820  mov     eax, [rsp+0D0h+var_90]
0x180231824  inc     eax
0x180231826  mov     [rsp+0D0h+var_8C], eax
0x18023182a  jmp     short loc_180231836
0x18023182c  mov     eax, [rsp+0D0h+var_8C]
0x180231830  inc     eax
0x180231832  mov     [rsp+0D0h+var_8C], eax
0x180231836  mov     rax, [rbp+arg_0]
0x18023183a  movsx   eax, word ptr [rax+40h]
0x18023183e  cmp     [rsp+0D0h+var_8C], eax
0x180231842  jge     short loc_180231859
0x180231844  movsxd  rax, [rsp+0D0h+var_8C]
0x180231849  mov     rcx, [rbp+arg_0]
0x18023184d  cmp     dword ptr [rcx+rax*4+0A8h], 0
0x180231855  jnz     short loc_180231859
0x180231857  jmp     short loc_18023182C
0x180231859  mov     rax, [rbp+arg_0]
0x18023185d  movsx   eax, word ptr [rax+40h]
0x180231861  cmp     [rsp+0D0h+var_8C], eax
  ... truncated ...
```
