# WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x180027544`
- end: `0x180027900`
- name: `?ProcessWindowMessage@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `956`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180027910`

## callees

- `0x180022558`
- `0x180024878`
- `0x1800249a0`
- `0x18002522c`
- `0x180027544`
- `0x1800288a0`
- `0x180029664`

## import_xrefs

- `USER32!GetWindowLongW` at `0x1800275a8`
- `USER32!GetWindowLongW` at `0x1800278b1`
- `USER32!GetWindowLongW` at `0x1800275a8`
- `USER32!GetWindowLongW` at `0x1800278b1`
- `USER32!ReleaseCapture` at `0x1800277d0`
- `USER32!ReleaseCapture` at `0x1800277d0`
- `USER32!SetCapture` at `0x18002779c`
- `USER32!SetCapture` at `0x18002779c`
- `USER32!ScreenToClient` at `0x180027664`
- `USER32!ScreenToClient` at `0x180027664`
- `USER32!SetFocus` at `0x180027862`
- `USER32!SetFocus` at `0x180027862`
- `USER32!SetCursor` at `0x1800277a9`
- `USER32!SetCursor` at `0x1800277a9`
- `USER32!UpdateWindow` at `0x180027839`
- `USER32!UpdateWindow` at `0x180027839`
- `USER32!GetSystemMetrics` at `0x180027587`
- `USER32!GetSystemMetrics` at `0x1800275b7`
- `USER32!GetSystemMetrics` at `0x1800275cd`
- `USER32!GetSystemMetrics` at `0x180027898`
- `USER32!GetSystemMetrics` at `0x1800278c0`
- `USER32!GetSystemMetrics` at `0x1800278d6`
- `USER32!GetSystemMetrics` at `0x180027587`
- `USER32!GetSystemMetrics` at `0x1800275b7`
- `USER32!GetSystemMetrics` at `0x1800275cd`
- `USER32!GetSystemMetrics` at `0x180027898`
- `USER32!GetSystemMetrics` at `0x1800278c0`
- `USER32!GetSystemMetrics` at `0x1800278d6`
- `USER32!SystemParametersInfoW` at `0x1800275e4`
- `USER32!SystemParametersInfoW` at `0x1800278ed`
- `USER32!SystemParametersInfoW` at `0x1800275e4`
- `USER32!SystemParametersInfoW` at `0x1800278ed`
- `USER32!GetMessagePos` at `0x180027647`
- `USER32!GetMessagePos` at `0x180027647`

## pseudocode

```c
_BOOL8 __fastcall WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::ProcessWindowMessage(
        __int64 a1,
        struct tagPOINT a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        int a7)
{
  __int64 *v7; // r14
  int v9; // edi
  __int64 v10; // rbx
  __int64 v11; // rsi
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rax
  int v16; // edi
  DWORD MessagePos; // eax
  HWND v18; // rcx
  int v19; // edx
  LONG *v20; // rax
  __int64 v21; // rax
  bool v22; // zf
  int v23; // edx
  _DWORD *v24; // r15
  int v25; // edi
  __int64 v26; // rcx
  int v27; // eax
  struct tagPOINT Point; // [rsp+68h] [rbp+10h] BYREF

  Point = a2;
  v7 = a6;
  v9 = a3;
  v10 = a1;
  if ( (_DWORD)a3 == 1 )
  {
    *(_DWORD *)(a1 + 40) = GetSystemMetrics(33);
    v11 = v10 - 64;
    v12 = v10 - 64;
    if ( !v10 )
      v12 = 8;
    if ( (GetWindowLongW(*(HWND *)v12, -20) & 0x200) != 0 )
    {
      *(_DWORD *)(v10 + 48) = 2 * GetSystemMetrics(46);
      v13 = 0;
    }
    else
    {
      *(_DWORD *)(v10 + 48) = 0;
      v13 = 2 * GetSystemMetrics(46);
    }
    *(_DWORD *)(v10 + 44) = v13;
    SystemParametersInfoW(0x26u, 0, (PVOID)(v10 + 52), 0);
    *v7 = 1;
  }
  else
  {
    if ( (_DWORD)a3 == 15 || (_DWORD)a3 == 792 )
    {
      v14 = WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::OnPaint();
      goto LABEL_10;
    }
    v11 = a1 - 64;
  }
  if ( (*(_BYTE *)(v10 + 68) & 2) != 0 )
  {
LABEL_66:
    if ( v9 == 7 )
    {
      if ( *(_DWORD *)(v10 + 72) == -1 )
      {
        if ( *(_DWORD *)(v10 + 36) > 1u )
          goto LABEL_55;
        v26 = *(int *)(v10 + 36);
      }
      else
      {
        v26 = *(int *)(v10 + 72);
      }
      SetFocus(*(HWND *)(v10 + 8 * v26));
      goto LABEL_55;
    }
    if ( v9 != 33 )
    {
      if ( v9 != 26 )
        return 0;
      *(_DWORD *)(v10 + 40) = GetSystemMetrics(33);
      if ( !v10 )
        v11 = 8;
      if ( (GetWindowLongW(*(HWND *)v11, -20) & 0x200) != 0 )
      {
        *(_DWORD *)(v10 + 48) = 2 * GetSystemMetrics(46);
        v27 = 0;
      }
      else
      {
        *(_DWORD *)(v10 + 48) = 0;
        v27 = 2 * GetSystemMetrics(46);
      }
      *(_DWORD *)(v10 + 44) = v27;
      SystemParametersInfoW(0x26u, 0, (PVOID)(v10 + 52), 0);
      WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::UpdateSplitterLayout(v10);
      goto LABEL_60;
    }
    v14 = WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::OnMouseActivate(v10, 33, a4, a5);
LABEL_10:
    *v7 = v14;
    return 1;
  }
  if ( v9 != 32 )
  {
    switch ( v9 )
    {
      case 512:
        a7 = 1;
        v21 = WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::OnMouseMove(v10, a2.x, a4, a5, (__int64)&a7);
        v22 = a7 == 0;
        goto LABEL_35;
      case 513:
        if ( *(_DWORD *)(v10 + 72) == -1 )
        {
          v23 = *(_DWORD *)(v10 + 32);
          if ( v23 != -1
            && ((_WORD)a5 == 0xFFFF || (__int16)a5 >= *(_DWORD *)(v10 + 16) && (__int16)a5 <= *(_DWORD *)(v10 + 24)) )
          {
            v24 = (_DWORD *)(v10 + 20);
            v25 = SWORD1(a5);
            if ( (SWORD1(a5) == -1 || SWORD1(a5) >= *v24 && SWORD1(a5) <= *(_DWORD *)(v10 + 28))
              && SWORD1(a5) >= *v24 + v23
              && SWORD1(a5) < v23 + *v24 + *(_DWORD *)(v10 + 40) + *(_DWORD *)(v10 + 48) )
            {
              if ( !v10 )
                v11 = 8;
              SetCapture(*(HWND *)v11);
              SetCursor(WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::m_hCursor);
              if ( !*(_BYTE *)(v10 + 52) )
                WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawGhostBar((_DWORD *)v10);
              *(_DWORD *)(v10 + 56) = v25 - *(_DWORD *)(v10 + 32) - *v24;
            }
          }
        }
        goto LABEL_55;
      case 514:
        ReleaseCapture();
LABEL_55:
        *v7 = 1;
        return 0;
      case 515:
        LOBYTE(a3) = 1;
        if ( !v10 )
          v10 = 72;
        WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::SetSplitterPos(v10, 0xFFFFFFFFLL, a3);
LABEL_60:
        *v7 = 0;
        return 1;
      case 533:
        if ( !*(_BYTE *)(v10 + 52) )
        {
          WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawGhostBar((_DWORD *)v10);
          WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::UpdateSplitterLayout(v10);
          if ( !v10 )
            v11 = 8;
          UpdateWindow(*(HWND *)v11);
        }
        goto LABEL_60;
    }
    goto LABEL_66;
  }
  v16 = 1;
  if ( !v10 )
    v11 = 8;
  if ( a4 == *(_QWORD *)v11
    && (_WORD)a5 == 1
    && (MessagePos = GetMessagePos(),
        v18 = *(HWND *)v11,
        Point.x = (__int16)MessagePos,
        Point.y = SHIWORD(MessagePos),
        ScreenToClient(v18, &Point),
        *(_DWORD *)(v10 + 72) == -1)
    && (v19 = *(_DWORD *)(v10 + 32), v19 != -1)
    && (Point.x == -1 || Point.x >= *(_DWORD *)(v10 + 16) && Point.x <= *(_DWORD *)(v10 + 24))
    && ((v20 = (LONG *)(v10 + 20), Point.y == -1) || Point.y >= *v20 && Point.y <= *(_DWORD *)(v10 + 28))
    && Point.y >= *v20 + v19
    && Point.y < v19 + *v20 + *(_DWORD *)(v10 + 40) + *(_DWORD *)(v10 + 48) )
  {
    v21 = 1;
  }
  else
  {
    v16 = 0;
    v21 = 0;
  }
  v22 = v16 == 0;
LABEL_35:
  *v7 = v21;
  return !v22;
}

```

## disassembly

```asm
0x180027544  mov     [rsp+arg_0], rbx
0x180027549  mov     [rsp+arg_10], rbp
0x18002754e  mov     qword ptr [rsp+Point.x], rdx
0x180027553  push    rsi
0x180027554  push    rdi
0x180027555  push    r13
0x180027557  push    r14
0x180027559  push    r15
0x18002755b  sub     rsp, 30h
0x18002755f  mov     r14, [rsp+58h+arg_28]
0x180027567  mov     rbp, r9
0x18002756a  mov     r9d, 8
0x180027570  mov     edi, r8d
0x180027573  mov     rbx, rcx
0x180027576  lea     r13d, [r9-7]
0x18002757a  lea     r15d, [r9+26h]
0x18002757e  cmp     r8d, r13d
0x180027581  jnz     short loc_1800275F5
0x180027583  lea     ecx, [r9+19h]; nIndex
0x180027587  call    cs:__imp_GetSystemMetrics
0x18002758d  mov     [rbx+28h], eax
0x180027590  lea     rsi, [rbx-40h]
0x180027594  lea     eax, [r15-26h]
0x180027598  test    rbx, rbx
0x18002759b  mov     rcx, rsi
0x18002759e  cmovz   rcx, rax
0x1800275a2  lea     edx, [rax-1Ch]; nIndex
0x1800275a5  mov     rcx, [rcx]; hWnd
0x1800275a8  call    cs:__imp_GetWindowLongW
0x1800275ae  mov     ecx, r15d; nIndex
0x1800275b1  bt      eax, 9
0x1800275b5  jnb     short loc_1800275C6
0x1800275b7  call    cs:__imp_GetSystemMetrics
0x1800275bd  add     eax, eax
0x1800275bf  mov     [rbx+30h], eax
0x1800275c2  xor     eax, eax
0x1800275c4  jmp     short loc_1800275D5
0x1800275c6  mov     dword ptr [rbx+30h], 0
0x1800275cd  call    cs:__imp_GetSystemMetrics
0x1800275d3  add     eax, eax
0x1800275d5  xor     edx, edx; uiParam
0x1800275d7  mov     [rbx+2Ch], eax
0x1800275da  lea     r8, [rbx+34h]; pvParam
0x1800275de  xor     r9d, r9d; fWinIni
0x1800275e1  lea     ecx, [rdx+26h]; uiAction
0x1800275e4  call    cs:__imp_SystemParametersInfoW
0x1800275ea  mov     r9d, 8
0x1800275f0  mov     [r14], r13
0x1800275f3  jmp     short loc_180027616
0x1800275f5  cmp     edi, 0Fh
0x1800275f8  jnz     short loc_18002760A
0x1800275fa  call    ?OnPaint@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAA_JI_K_JAEAH@Z; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::OnPaint(uint,unsigned __int64,__int64,int &)
0x1800275ff  mov     [r14], rax
0x180027602  mov     eax, r13d
0x180027605  jmp     loc_18002770A
0x18002760a  cmp     edi, 318h
0x180027610  jz      short loc_1800275FA
0x180027612  lea     rsi, [rcx-40h]
0x180027616  test    byte ptr [rbx+44h], 2
0x18002761a  jnz     loc_180027841
0x180027620  cmp     edi, 20h ; ' '
0x180027623  jnz     loc_1800276C7
0x180027629  test    rbx, rbx
0x18002762c  mov     edi, r13d
0x18002762f  cmovz   rsi, r9
0x180027633  cmp     rbp, [rsi]
0x180027636  jnz     loc_1800276BF
0x18002763c  cmp     word ptr [rsp+58h+arg_20], r13w
0x180027645  jnz     short loc_1800276BF
0x180027647  call    cs:__imp_GetMessagePos
0x18002764d  mov     rcx, [rsi]; hWnd
0x180027650  movsx   edx, ax
0x180027653  shr     eax, 10h
0x180027656  cwde
0x180027657  mov     [rsp+58h+Point.x], edx
0x18002765b  lea     rdx, [rsp+58h+Point]; lpPoint
0x180027660  mov     [rsp+58h+Point.y], eax
0x180027664  call    cs:__imp_ScreenToClient
0x18002766a  or      eax, 0FFFFFFFFh
0x18002766d  cmp     [rbx+48h], eax
0x180027670  jnz     short loc_1800276BF
0x180027672  mov     edx, [rbx+20h]
0x180027675  cmp     edx, eax
0x180027677  jz      short loc_1800276BF
0x180027679  mov     ecx, [rsp+58h+Point.x]
0x18002767d  cmp     ecx, eax
0x18002767f  jz      short loc_18002768B
0x180027681  cmp     ecx, [rbx+10h]
0x180027684  jl      short loc_1800276BF
0x180027686  cmp     ecx, [rbx+18h]
0x180027689  jg      short loc_1800276BF
0x18002768b  mov     ecx, [rsp+58h+Point.y]
0x18002768f  cmp     ecx, eax
0x180027691  lea     rax, [rbx+14h]
0x180027695  jz      short loc_1800276A0
0x180027697  cmp     ecx, [rax]
0x180027699  jl      short loc_1800276BF
0x18002769b  cmp     ecx, [rbx+1Ch]
0x18002769e  jg      short loc_1800276BF
0x1800276a0  mov     r8d, [rax]
0x1800276a3  lea     eax, [r8+rdx]
0x1800276a7  cmp     ecx, eax
0x1800276a9  jl      short loc_1800276BF
0x1800276ab  mov     eax, [rbx+30h]
0x1800276ae  add     eax, [rbx+28h]
0x1800276b1  add     eax, r8d
0x1800276b4  add     eax, edx
0x1800276b6  cmp     ecx, eax
0x1800276b8  jge     short loc_1800276BF
0x1800276ba  mov     rax, r13
0x1800276bd  jmp     short loc_1800276C3
0x1800276bf  xor     edi, edi
0x1800276c1  xor     eax, eax
0x1800276c3  test    edi, edi
0x1800276c5  jmp     short loc_1800276FF
0x1800276c7  cmp     edi, 200h
0x1800276cd  jnz     short loc_180027721
0x1800276cf  mov     r9, [rsp+58h+arg_20]
0x1800276d7  lea     rax, [rsp+58h+arg_30]
0x1800276df  mov     r8, rbp
0x1800276e2  mov     [rsp+58h+var_38], rax
0x1800276e7  mov     rcx, rbx
0x1800276ea  mov     [rsp+58h+arg_30], r13d
0x1800276f2  call    ?OnMouseMove@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAA_JI_K_JAEAH@Z; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::OnMouseMove(uint,unsigned __int64,__int64,int &)
0x1800276f7  cmp     [rsp+58h+arg_30], 0
0x1800276ff  mov     [r14], rax
0x180027702  jnz     loc_180027602
0x180027708  xor     eax, eax
0x18002770a  mov     rbx, [rsp+58h+arg_0]
0x18002770f  mov     rbp, [rsp+58h+arg_10]
0x180027714  add     rsp, 30h
0x180027718  pop     r15
0x18002771a  pop     r14
0x18002771c  pop     r13
0x18002771e  pop     rdi
0x18002771f  pop     rsi
0x180027720  retn
0x180027721  cmp     edi, 201h
0x180027727  jnz     loc_1800277C8
0x18002772d  or      eax, 0FFFFFFFFh
0x180027730  cmp     [rbx+48h], eax
0x180027733  jnz     loc_1800277D6
0x180027739  mov     edx, [rbx+20h]
0x18002773c  cmp     edx, eax
0x18002773e  jz      loc_1800277D6
0x180027744  mov     rcx, [rsp+58h+arg_20]
0x18002774c  cmp     cx, ax
0x18002774f  jz      short loc_180027761
0x180027751  movsx   r8d, cx
0x180027755  cmp     r8d, [rbx+10h]
0x180027759  jl      short loc_1800277D6
0x18002775b  cmp     r8d, [rbx+18h]
0x18002775f  jg      short loc_1800277D6
0x180027761  shr     rcx, 10h
0x180027765  lea     r15, [rbx+14h]
0x180027769  movsx   edi, cx
0x18002776c  cmp     edi, eax
0x18002776e  jz      short loc_18002777A
0x180027770  cmp     edi, [r15]
0x180027773  jl      short loc_1800277D6
0x180027775  cmp     edi, [rbx+1Ch]
0x180027778  jg      short loc_1800277D6
0x18002777a  mov     ecx, [r15]
0x18002777d  lea     eax, [rcx+rdx]
0x180027780  cmp     edi, eax
0x180027782  jl      short loc_1800277D6
0x180027784  mov     eax, [rbx+30h]
0x180027787  add     eax, [rbx+28h]
0x18002778a  add     eax, ecx
0x18002778c  add     eax, edx
0x18002778e  cmp     edi, eax
0x180027790  jge     short loc_1800277D6
0x180027792  test    rbx, rbx
0x180027795  cmovz   rsi, r9
0x180027799  mov     rcx, [rsi]; hWnd
0x18002779c  call    cs:__imp_SetCapture
0x1800277a2  mov     rcx, cs:?m_hCursor@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@2PEAUHICON__@@EA; hCursor
0x1800277a9  call    cs:__imp_SetCursor
0x1800277af  cmp     byte ptr [rbx+34h], 0
0x1800277b3  jnz     short loc_1800277BD
0x1800277b5  mov     rcx, rbx
0x1800277b8  call    ?DrawGhostBar@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAXXZ; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawGhostBar(void)
0x1800277bd  sub     edi, [rbx+20h]
0x1800277c0  sub     edi, [r15]
0x1800277c3  mov     [rbx+38h], edi
0x1800277c6  jmp     short loc_1800277D6
0x1800277c8  cmp     edi, 202h
0x1800277ce  jnz     short loc_1800277DE
0x1800277d0  call    cs:__imp_ReleaseCapture
0x1800277d6  mov     [r14], r13
0x1800277d9  jmp     loc_180027708
0x1800277de  cmp     edi, 203h
0x1800277e4  jnz     short loc_18002780C
0x1800277e6  test    rbx, rbx
0x1800277e9  mov     eax, 48h ; 'H'
0x1800277ee  mov     r8b, r13b
0x1800277f1  cmovz   rbx, rax
0x1800277f5  or      edx, 0FFFFFFFFh
0x1800277f8  mov     rcx, rbx
0x1800277fb  call    ?SetSplitterPos@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAA_NH_N@Z; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::SetSplitterPos(int,bool)
0x180027800  mov     qword ptr [r14], 0
0x180027807  jmp     loc_180027602
0x18002780c  cmp     edi, 215h
0x180027812  jnz     short loc_180027841
0x180027814  cmp     byte ptr [rbx+34h], 0
0x180027818  jnz     short loc_180027800
0x18002781a  mov     rcx, rbx
0x18002781d  call    ?DrawGhostBar@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAXXZ; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::DrawGhostBar(void)
0x180027822  mov     rcx, rbx
0x180027825  call    ?UpdateSplitterLayout@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAXXZ; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::UpdateSplitterLayout(void)
0x18002782a  test    rbx, rbx
0x18002782d  mov     eax, 8
0x180027832  cmovz   rsi, rax
0x180027836  mov     rcx, [rsi]; hWnd
0x180027839  call    cs:__imp_UpdateWindow
0x18002783f  jmp     short loc_180027800
0x180027841  cmp     edi, 7
0x180027844  jnz     short loc_18002786D
0x180027846  or      eax, 0FFFFFFFFh
0x180027849  cmp     [rbx+48h], eax
0x18002784c  jnz     short loc_18002785A
0x18002784e  cmp     [rbx+24h], r13d
0x180027852  ja      short loc_1800277D6
0x180027854  movsxd  rcx, dword ptr [rbx+24h]
0x180027858  jmp     short loc_18002785E
0x18002785a  movsxd  rcx, dword ptr [rbx+48h]
0x18002785e  mov     rcx, [rbx+rcx*8]; hWnd
0x180027862  call    cs:__imp_SetFocus
0x180027868  jmp     loc_1800277D6
0x18002786d  cmp     edi, 21h ; '!'
0x180027870  jnz     short loc_18002788C
0x180027872  mov     r9, [rsp+58h+arg_20]
0x18002787a  mov     r8, rbp
0x18002787d  mov     edx, edi
0x18002787f  mov     rcx, rbx
0x180027882  call    ?OnMouseActivate@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAA_JI_K_JAEAH@Z; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::OnMouseActivate(uint,unsigned __int64,__int64,int &)
0x180027887  jmp     loc_1800275FF
0x18002788c  cmp     edi, 1Ah
0x18002788f  jnz     loc_180027708
0x180027895  lea     ecx, [rdi+7]; nIndex
0x180027898  call    cs:__imp_GetSystemMetrics
0x18002789e  mov     [rbx+28h], eax
0x1800278a1  test    rbx, rbx
0x1800278a4  lea     edx, [rdi-2Eh]; nIndex
0x1800278a7  lea     eax, [rdi-12h]
0x1800278aa  cmovz   rsi, rax
0x1800278ae  mov     rcx, [rsi]; hWnd
0x1800278b1  call    cs:__imp_GetWindowLongW
0x1800278b7  mov     ecx, r15d; nIndex
0x1800278ba  bt      eax, 9
0x1800278be  jnb     short loc_1800278CF
0x1800278c0  call    cs:__imp_GetSystemMetrics
0x1800278c6  add     eax, eax
0x1800278c8  mov     [rbx+30h], eax
0x1800278cb  xor     eax, eax
0x1800278cd  jmp     short loc_1800278DE
0x1800278cf  mov     dword ptr [rbx+30h], 0
0x1800278d6  call    cs:__imp_GetSystemMetrics
0x1800278dc  add     eax, eax
0x1800278de  xor     edx, edx; uiParam
0x1800278e0  mov     [rbx+2Ch], eax
0x1800278e3  lea     r8, [rbx+34h]; pvParam
0x1800278e7  xor     r9d, r9d; fWinIni
0x1800278ea  lea     ecx, [rdx+26h]; uiAction
0x1800278ed  call    cs:__imp_SystemParametersInfoW
0x1800278f3  mov     rcx, rbx
0x1800278f6  call    ?UpdateSplitterLayout@?$CSplitterImpl@V?$CF12SplitterWindowT@$0A@@@$0A@@WTL@@QEAAXXZ; WTL::CSplitterImpl<CF12SplitterWindowT<0>,0>::UpdateSplitterLayout(void)
0x1800278fb  jmp     loc_180027800
```
