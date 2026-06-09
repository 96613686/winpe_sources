# CToolBar::CalcLayout(ulong,int)

- ea: `0x180048180`
- end: `0x18004859b`
- name: `?CalcLayout@CToolBar@@IEAA?AVCSize@@KH@Z`
- size: `1051`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800480e0`
- `0x180048140`

## callees

- `0x18000ce50`
- `0x1800200f0`
- `0x1800206b0`
- `0x180022f20`
- `0x180023ea0`
- `0x180024b80`
- `0x180027800`
- `0x18002de30`
- `0x1800480a0`
- `0x180048180`
- `0x1800485b0`
- `0x180048e50`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `msvcrt!free` at `0x1800484ee`
- `msvcrt!free` at `0x180048509`
- `msvcrt!free` at `0x1800484ee`
- `msvcrt!free` at `0x180048509`
- `USER32!GetWindowRect` at `0x180048468`
- `USER32!GetWindowRect` at `0x180048468`
- `USER32!SetRectEmpty` at `0x180048272`
- `USER32!SetRectEmpty` at `0x180048513`
- `USER32!SetRectEmpty` at `0x180048272`
- `USER32!SetRectEmpty` at `0x180048513`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CToolBar::CalcLayout(CToolBar *a1, _QWORD *a2, int a3, int a4)
{
  char v5; // r15
  _QWORD *v6; // r13
  int v8; // eax
  int v9; // edi
  struct _TBBUTTON *v10; // rsi
  int v11; // ebx
  int v12; // eax
  int v13; // r9d
  int v14; // eax
  _DWORD *v15; // r12
  int v16; // r15d
  int i; // ecx
  __int64 v18; // rax
  _DWORD *v19; // rax
  int v20; // eax
  int j; // r13d
  __int64 v22; // rcx
  __int64 v23; // rbx
  int v24; // ebx
  int v25; // ebx
  __int64 v26; // r13
  struct CWnd *DlgItem; // rax
  __int64 v28; // rax
  int v29; // edi
  int v30; // ebx
  int v31; // esi
  int v32; // ebx
  int v33; // ecx
  int v34; // ecx
  int v36; // [rsp+40h] [rbp-40h]
  int v37; // [rsp+40h] [rbp-40h]
  _QWORD *v38; // [rsp+48h] [rbp-38h] BYREF
  int v39; // [rsp+50h] [rbp-30h]
  int v40; // [rsp+54h] [rbp-2Ch]
  struct tagRECT Rect; // [rsp+58h] [rbp-28h] BYREF
  struct tagRECT rc; // [rsp+68h] [rbp-18h] BYREF

  v5 = a3;
  v40 = a3;
  v6 = a2;
  v38 = a2;
  *a2 = 0;
  v8 = (*(__int64 (__fastcall **)(CToolBar *, __int64, _QWORD, _QWORD))(*(_QWORD *)a1 + 336LL))(a1, 1048, 0, 0);
  v9 = v8;
  if ( !v8 )
    goto LABEL_48;
  v10 = (struct _TBBUTTON *)operator new(saturated_mul(v8, 0x20u));
  v11 = 0;
  if ( v9 <= 0 )
    goto LABEL_48;
  do
  {
    CToolBar::_GetButton(a1, v11, &v10[v11]);
    ++v11;
  }
  while ( v11 < v9 );
  v12 = *((_DWORD *)a1 + 43);
  if ( (v12 & 2) == 0 )
  {
    if ( (v12 & 4) == 0 )
      goto LABEL_18;
    if ( (v5 & 4) == 0 )
    {
      if ( (v5 & 8) != 0 )
      {
        v13 = 0x7FFF;
        goto LABEL_19;
      }
      if ( (v5 & 0x10) != 0 )
      {
        v13 = 0;
        goto LABEL_19;
      }
      if ( a4 != -1 )
      {
        SetRectEmpty(&rc);
        CControlBar::CalcInsideRect(a1, (struct CRect *)&rc, v5 & 2);
        if ( (v5 & 0x20) != 0 )
          v14 = rc.bottom - rc.top;
        else
          v14 = rc.right - rc.left;
        CToolBar::SizeToolBar(a1, v10, v9, a4 + v14, v5 & 0x20);
        goto LABEL_20;
      }
      if ( (v12 & 1) == 0 )
      {
LABEL_18:
        v13 = (v5 & 2) != 0 ? 0x7FFF : 0;
        goto LABEL_19;
      }
    }
    v13 = *((_DWORD *)a1 + 38);
LABEL_19:
    CToolBar::SizeToolBar(a1, v10, v9, v13, 0);
  }
LABEL_20:
  *v6 = *(_QWORD *)CToolBar::CalcSize(a1, &rc, v10, (unsigned int)v9);
  if ( (v5 & 0x40) != 0 )
  {
    v15 = 0;
    v16 = 0;
    v39 = *((_DWORD *)a1 + 58);
    *((_DWORD *)a1 + 58) = 0;
    for ( i = 0; i < v9; ++i )
    {
      v18 = (unsigned int)i;
      if ( (v10[v18].fsStyle & 1) != 0 && v10[v18].idCommand )
        ++v16;
    }
    if ( v16 > 0 )
    {
      v19 = operator new(saturated_mul(v16, 0x18u));
      v15 = v19;
      *(_QWORD *)&rc.left = v19;
      if ( v19 )
        `vector constructor iterator'(v19, 0x18u, v16, (void *(*)(void *))IDropTarget::IDropTarget);
      else
        v15 = 0;
      v20 = v16;
      v36 = v16;
      v16 = 0;
      for ( j = 0; j < v9; ++j )
      {
        if ( v16 >= v20 )
          break;
        v22 = j;
        if ( (v10[v22].fsStyle & 1) != 0 && v10[v22].idCommand )
        {
          v23 = 3LL * v16;
          v15[2 * v23] = j;
          v15[2 * v23 + 1] = v10[v22].idCommand;
          (*(void (__fastcall **)(CToolBar *, _QWORD, struct tagRECT *))(*(_QWORD *)a1 + 464LL))(
            a1,
            (unsigned int)j,
            &Rect);
          CWnd::ClientToScreen(a1, &Rect);
          *(struct tagRECT *)&v15[6 * v16++ + 2] = Rect;
          v20 = v36;
        }
      }
      v6 = v38;
    }
    v24 = 0;
    if ( (*((_BYTE *)a1 + 172) & 5) == 5 )
      *((_DWORD *)a1 + 38) = *(_DWORD *)v6;
    do
    {
      CToolBar::_SetButton(a1, v24, &v10[v24]);
      ++v24;
    }
    while ( v24 < v9 );
    if ( v16 > 0 )
    {
      v25 = 0;
      v37 = 0;
      v26 = 0;
      do
      {
        DlgItem = CWnd::GetDlgItem(a1, v15[6 * v26 + 1]);
        *(_QWORD *)&rc.left = DlgItem;
        if ( DlgItem )
        {
          GetWindowRect(*((HWND *)DlgItem + 8), &Rect);
          v28 = *(_QWORD *)&v15[6 * v26 + 2];
          v29 = Rect.left - v28;
          v30 = Rect.top - HIDWORD(v28);
          (*(void (__fastcall **)(CToolBar *, _QWORD, struct tagRECT *))(*(_QWORD *)a1 + 464LL))(
            a1,
            (unsigned int)v15[6 * v26],
            &Rect);
          CWnd::SetWindowPos(*(CWnd **)&rc.left, 0, v29 + Rect.left, v30 + Rect.top, 0, 0, 0x15u);
          v25 = v37;
        }
        v37 = ++v25;
        ++v26;
      }
      while ( v25 < v16 );
      free(v15);
    }
    *((_DWORD *)a1 + 58) = v39;
    v5 = v40;
    v6 = v38;
  }
  free(v10);
LABEL_48:
  SetRectEmpty(&Rect);
  CControlBar::CalcInsideRect(a1, (struct CRect *)&Rect, v5 & 2);
  v31 = *((_DWORD *)v6 + 1) + Rect.top - Rect.bottom;
  v32 = *(_DWORD *)v6 + Rect.left - Rect.right;
  CControlBar::CalcFixedLayout(a1, &v38, v5 & 1, v5 & 2);
  v33 = (int)v38;
  if ( v32 > (int)v38 )
    v33 = v32;
  *(_DWORD *)v6 = v33;
  v34 = HIDWORD(v38);
  if ( v31 > SHIDWORD(v38) )
    v34 = v31;
  *((_DWORD *)v6 + 1) = v34;
  return v6;
}

```

## disassembly

```asm
0x180048180  mov     [rsp-38h+arg_10], rbx
0x180048185  push    rbp
0x180048186  push    rsi
0x180048187  push    rdi
0x180048188  push    r12
0x18004818a  push    r13
0x18004818c  push    r14
0x18004818e  push    r15
0x180048190  mov     rbp, rsp
0x180048193  sub     rsp, 80h
0x18004819a  mov     rax, cs:__security_cookie
0x1800481a1  xor     rax, rsp
0x1800481a4  mov     [rbp+var_8], rax
0x1800481a8  mov     r12d, r9d
0x1800481ab  mov     r15d, r8d
0x1800481ae  mov     [rbp+var_2C], r8d
0x1800481b2  mov     r13, rdx
0x1800481b5  mov     [rbp+var_38], rdx
0x1800481b9  mov     r14, rcx
0x1800481bc  mov     qword ptr [rdx], 0
0x1800481c3  mov     rax, [rcx]
0x1800481c6  xor     r9d, r9d
0x1800481c9  xor     r8d, r8d
0x1800481cc  mov     edx, 418h
0x1800481d1  mov     rax, [rax+150h]
0x1800481d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800481dd  mov     rdi, rax
0x1800481e0  test    eax, eax
0x1800481e2  jz      loc_18004850F
0x1800481e8  movsxd  rcx, edi
0x1800481eb  mov     eax, 20h ; ' '
0x1800481f0  mul     rcx
0x1800481f3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800481fa  cmovb   rax, rcx
0x1800481fe  mov     rcx, rax; Size
0x180048201  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048206  mov     rsi, rax
0x180048209  xor     ebx, ebx
0x18004820b  test    edi, edi
0x18004820d  jle     loc_18004850F
0x180048213  mov     r8d, ebx
0x180048216  shl     r8, 5
0x18004821a  add     r8, rsi; struct _TBBUTTON *
0x18004821d  mov     edx, ebx; int
0x18004821f  mov     rcx, r14; this
0x180048222  call    ?_GetButton@CToolBar@@IEBAXHPEAU_TBBUTTON@@@Z; CToolBar::_GetButton(int,_TBBUTTON *)
0x180048227  inc     ebx
0x180048229  cmp     ebx, edi
0x18004822b  jl      short loc_180048213
0x18004822d  mov     eax, [r14+0ACh]
0x180048234  test    al, 2
0x180048236  jnz     loc_1800482D6
0x18004823c  test    al, 4
0x18004823e  jz      short loc_1800482AF
0x180048240  test    r15b, 4
0x180048244  jz      short loc_18004824F
0x180048246  mov     r9d, [r14+98h]
0x18004824d  jmp     short loc_1800482C0
0x18004824f  test    r15b, 8
0x180048253  jz      short loc_18004825D
0x180048255  mov     r9d, 7FFFh
0x18004825b  jmp     short loc_1800482C0
0x18004825d  test    r15b, 10h
0x180048261  jz      short loc_180048268
0x180048263  xor     r9d, r9d
0x180048266  jmp     short loc_1800482C0
0x180048268  cmp     r12d, 0FFFFFFFFh
0x18004826c  jz      short loc_1800482AB
0x18004826e  lea     rcx, [rbp+rc]; lprc
0x180048272  call    cs:__imp_SetRectEmpty
0x180048278  mov     r8d, r15d
0x18004827b  and     r8d, 2; int
0x18004827f  lea     rdx, [rbp+rc]; struct CRect *
0x180048283  mov     rcx, r14; this
0x180048286  call    ?CalcInsideRect@CControlBar@@QEBAXAEAVCRect@@H@Z; CControlBar::CalcInsideRect(CRect &,int)
0x18004828b  mov     ecx, r15d
0x18004828e  and     ecx, 20h
0x180048291  jz      short loc_18004829B
0x180048293  mov     eax, [rbp+rc.bottom]
0x180048296  sub     eax, [rbp+rc.top]
0x180048299  jmp     short loc_1800482A1
0x18004829b  mov     eax, [rbp+rc.right]
0x18004829e  sub     eax, [rbp+rc.left]
0x1800482a1  lea     r9d, [r12+rax]
0x1800482a5  mov     [rsp+80h+var_60], ecx
0x1800482a9  jmp     short loc_1800482C8
0x1800482ab  test    al, 1
0x1800482ad  jnz     short loc_180048246
0x1800482af  mov     eax, r15d
0x1800482b2  and     al, 2
0x1800482b4  neg     al
0x1800482b6  sbb     r9d, r9d
0x1800482b9  and     r9d, 7FFFh; int
0x1800482c0  mov     [rsp+80h+var_60], 0; int
0x1800482c8  mov     r8d, edi; int
0x1800482cb  mov     rdx, rsi; struct _TBBUTTON *
0x1800482ce  mov     rcx, r14; this
0x1800482d1  call    ?SizeToolBar@CToolBar@@IEAAXPEAU_TBBUTTON@@HHH@Z; CToolBar::SizeToolBar(_TBBUTTON *,int,int,int)
0x1800482d6  mov     r9d, edi
0x1800482d9  mov     r8, rsi
0x1800482dc  lea     rdx, [rbp+rc]
0x1800482e0  mov     rcx, r14
0x1800482e3  call    ?CalcSize@CToolBar@@IEAA?AVCSize@@PEAU_TBBUTTON@@H@Z; CToolBar::CalcSize(_TBBUTTON *,int)
0x1800482e8  mov     rcx, [rax]
0x1800482eb  mov     [r13+0], rcx
0x1800482ef  test    r15b, 40h
0x1800482f3  jz      loc_180048506
0x1800482f9  xor     r12d, r12d
0x1800482fc  xor     r15d, r15d
0x1800482ff  mov     eax, [r14+0E8h]
0x180048306  mov     [rbp+var_30], eax
0x180048309  mov     [r14+0E8h], r12d
0x180048310  xor     ecx, ecx
0x180048312  mov     eax, ecx
0x180048314  shl     rax, 5
0x180048318  test    byte ptr [rax+rsi+9], 1
0x18004831d  jz      short loc_180048329
0x18004831f  cmp     [rax+rsi+4], r12d
0x180048324  jz      short loc_180048329
0x180048326  inc     r15d
0x180048329  inc     ecx
0x18004832b  cmp     ecx, edi
0x18004832d  jl      short loc_180048312
0x18004832f  test    r15d, r15d
0x180048332  jle     loc_1800483F9
0x180048338  movsxd  rbx, r15d
0x18004833b  mov     r13d, 18h
0x180048341  mov     eax, r13d
0x180048344  mul     rbx
0x180048347  lea     rcx, [r13-19h]
0x18004834b  cmovb   rax, rcx
0x18004834f  mov     rcx, rax; Size
0x180048352  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048357  mov     r12, rax
0x18004835a  mov     qword ptr [rbp+rc.left], rax
0x18004835e  test    rax, rax
0x180048361  jz      short loc_18004837A
0x180048363  lea     r9, ??0IDropTarget@@QEAA@XZ; void *(*)(void *)
0x18004836a  mov     r8, rbx; unsigned __int64
0x18004836d  mov     edx, r13d; unsigned __int64
0x180048370  mov     rcx, rax; void *
0x180048373  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180048378  jmp     short loc_18004837D
0x18004837a  xor     r12d, r12d
0x18004837d  mov     eax, r15d
0x180048380  mov     [rbp+var_40], eax
0x180048383  xor     r15d, r15d
0x180048386  xor     r13d, r13d
0x180048389  cmp     r15d, eax
0x18004838c  jge     short loc_1800483F5
0x18004838e  movsxd  rcx, r13d
0x180048391  shl     rcx, 5
0x180048395  test    byte ptr [rcx+rsi+9], 1
0x18004839a  jz      short loc_1800483ED
0x18004839c  cmp     dword ptr [rcx+rsi+4], 0
0x1800483a1  jz      short loc_1800483ED
0x1800483a3  movsxd  rax, r15d
0x1800483a6  lea     rbx, [rax+rax*2]
0x1800483aa  mov     [r12+rbx*8], r13d
0x1800483ae  mov     eax, [rcx+rsi+4]
0x1800483b2  mov     [r12+rbx*8+4], eax
0x1800483b7  mov     rax, [r14]
0x1800483ba  lea     r8, [rbp+Rect]
0x1800483be  mov     edx, r13d
0x1800483c1  mov     rcx, r14
0x1800483c4  mov     rax, [rax+1D0h]
0x1800483cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800483d0  lea     rdx, [rbp+Rect]; struct tagRECT *
0x1800483d4  mov     rcx, r14; this
0x1800483d7  call    ?ClientToScreen@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ClientToScreen(tagRECT *)
0x1800483dc  movups  xmm0, xmmword ptr [rbp+Rect.left]
0x1800483e0  movdqu  xmmword ptr [r12+rbx*8+8], xmm0
0x1800483e7  inc     r15d
0x1800483ea  mov     eax, [rbp+var_40]
0x1800483ed  inc     r13d
0x1800483f0  cmp     r13d, edi
0x1800483f3  jl      short loc_180048389
0x1800483f5  mov     r13, [rbp+var_38]
0x1800483f9  mov     eax, [r14+0ACh]
0x180048400  and     eax, 5
0x180048403  xor     ebx, ebx
0x180048405  cmp     al, 5
0x180048407  jnz     short loc_180048414
0x180048409  mov     eax, [r13+0]
0x18004840d  mov     [r14+98h], eax
0x180048414  movsxd  r8, ebx
0x180048417  shl     r8, 5
0x18004841b  add     r8, rsi; struct _TBBUTTON *
0x18004841e  mov     edx, ebx; int
0x180048420  mov     rcx, r14; this
0x180048423  call    ?_SetButton@CToolBar@@IEAAXHPEAU_TBBUTTON@@@Z; CToolBar::_SetButton(int,_TBBUTTON *)
0x180048428  inc     ebx
0x18004842a  cmp     ebx, edi
0x18004842c  jl      short loc_180048414
0x18004842e  test    r15d, r15d
0x180048431  jle     loc_1800484F4
0x180048437  xor     ebx, ebx
0x180048439  mov     [rbp+var_40], ebx
0x18004843c  xor     r13d, r13d
0x18004843f  lea     rdi, ds:0[r13*2]
0x180048447  add     rdi, r13
0x18004844a  mov     edx, [r12+rdi*8+4]; int
0x18004844f  mov     rcx, r14; this
0x180048452  call    ?GetDlgItem@CWnd@@QEBAPEAV1@H@Z; CWnd::GetDlgItem(int)
0x180048457  mov     qword ptr [rbp+rc.left], rax
0x18004845b  test    rax, rax
0x18004845e  jz      short loc_1800484DA
0x180048460  lea     rdx, [rbp+Rect]; lpRect
0x180048464  mov     rcx, [rax+40h]; hWnd
0x180048468  call    cs:__imp_GetWindowRect
0x18004846e  mov     rax, [r12+rdi*8+8]
0x180048473  mov     edi, [rbp+Rect.left]
0x180048476  sub     edi, eax
0x180048478  shr     rax, 20h
0x18004847c  mov     ebx, [rbp+Rect.top]
0x18004847f  sub     ebx, eax
0x180048481  mov     rax, [r14]
0x180048484  lea     r8, [rbp+Rect]
0x180048488  lea     rdx, ds:0[r13*2]
0x180048490  add     rdx, r13
0x180048493  mov     edx, [r12+rdx*8]
0x180048497  mov     rcx, r14
0x18004849a  mov     rax, [rax+1D0h]
0x1800484a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484a6  mov     r9d, [rbp+Rect.top]
0x1800484aa  add     r9d, ebx; int
0x1800484ad  mov     r8d, [rbp+Rect.left]
0x1800484b1  add     r8d, edi; int
0x1800484b4  mov     [rsp+80h+var_50], 15h; unsigned int
0x1800484bc  mov     [rsp+80h+var_58], 0; int
0x1800484c4  mov     [rsp+80h+var_60], 0; int
0x1800484cc  xor     edx, edx; struct CWnd *
0x1800484ce  mov     rcx, qword ptr [rbp+rc.left]; this
0x1800484d2  call    ?SetWindowPos@CWnd@@QEAAHPEBV1@HHHHI@Z; CWnd::SetWindowPos(CWnd const *,int,int,int,int,uint)
0x1800484d7  mov     ebx, [rbp+var_40]
0x1800484da  inc     ebx
0x1800484dc  mov     [rbp+var_40], ebx
0x1800484df  inc     r13
0x1800484e2  cmp     ebx, r15d
0x1800484e5  jl      loc_18004843F
0x1800484eb  mov     rcx, r12; Block
0x1800484ee  call    cs:__imp_free
0x1800484f4  mov     eax, [rbp+var_30]
0x1800484f7  mov     [r14+0E8h], eax
0x1800484fe  mov     r15d, [rbp+var_2C]
0x180048502  mov     r13, [rbp+var_38]
0x180048506  mov     rcx, rsi; Block
0x180048509  call    cs:__imp_free
0x18004850f  lea     rcx, [rbp+Rect]; lprc
0x180048513  call    cs:__imp_SetRectEmpty
0x180048519  mov     edi, r15d
0x18004851c  and     edi, 2
0x18004851f  mov     r8d, edi; int
0x180048522  lea     rdx, [rbp+Rect]; struct CRect *
0x180048526  mov     rcx, r14; this
0x180048529  call    ?CalcInsideRect@CControlBar@@QEBAXAEAVCRect@@H@Z; CControlBar::CalcInsideRect(CRect &,int)
0x18004852e  mov     esi, [rbp+Rect.top]
0x180048531  sub     esi, [rbp+Rect.bottom]
0x180048534  add     esi, [r13+4]
0x180048538  mov     ebx, [rbp+Rect.left]
0x18004853b  sub     ebx, [rbp+Rect.right]
0x18004853e  add     ebx, [r13+0]
0x180048542  and     r15d, 1
0x180048546  mov     r9d, edi
0x180048549  mov     r8d, r15d
0x18004854c  lea     rdx, [rbp+var_38]
0x180048550  mov     rcx, r14
0x180048553  call    ?CalcFixedLayout@CControlBar@@UEAA?AVCSize@@HH@Z; CControlBar::CalcFixedLayout(int,int)
0x180048558  mov     rcx, [rbp+var_38]
0x18004855c  cmp     ebx, ecx
0x18004855e  cmovg   ecx, ebx
0x180048561  mov     [r13+0], ecx
0x180048565  mov     ecx, dword ptr [rbp+var_38+4]
0x180048568  cmp     esi, ecx
0x18004856a  cmovg   ecx, esi
0x18004856d  mov     [r13+4], ecx
0x180048571  mov     rax, r13
0x180048574  mov     rcx, [rbp+var_8]
0x180048578  xor     rcx, rsp; StackCookie
0x18004857b  call    __security_check_cookie
0x180048580  mov     rbx, [rsp+80h+arg_10]
0x180048588  add     rsp, 80h
0x18004858f  pop     r15
0x180048591  pop     r14
0x180048593  pop     r13
0x180048595  pop     r12
0x180048597  pop     rdi
0x180048598  pop     rsi
0x180048599  pop     rbp
0x18004859a  retn
```
