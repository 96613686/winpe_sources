# CDockBar::CalcFixedLayout(int,int)

- ea: `0x180024640`
- end: `0x180024b79`
- name: `?CalcFixedLayout@CDockBar@@UEAA?AVCSize@@HH@Z`
- size: `1337`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation`

## callees

- `0x180011e80`
- `0x180020710`
- `0x180024640`
- `0x180024b80`
- `0x18002c3b0`
- `0x18002de30`
- `0x18003b4b0`
- `0x180049fc0`
- `0x18004a0b0`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!GetWindowRect` at `0x1800247c6`
- `USER32!GetWindowRect` at `0x1800247c6`
- `USER32!OffsetRect` at `0x1800247fe`
- `USER32!OffsetRect` at `0x180024832`
- `USER32!OffsetRect` at `0x18002485d`
- `USER32!OffsetRect` at `0x18002493c`
- `USER32!OffsetRect` at `0x180024977`
- `USER32!OffsetRect` at `0x1800249a3`
- `USER32!OffsetRect` at `0x1800247fe`
- `USER32!OffsetRect` at `0x180024832`
- `USER32!OffsetRect` at `0x18002485d`
- `USER32!OffsetRect` at `0x18002493c`
- `USER32!OffsetRect` at `0x180024977`
- `USER32!OffsetRect` at `0x1800249a3`
- `USER32!GetClientRect` at `0x1800246b3`
- `USER32!GetClientRect` at `0x1800246b3`
- `USER32!BeginDeferWindowPos` at `0x1800246ef`
- `USER32!BeginDeferWindowPos` at `0x1800246ef`
- `USER32!EndDeferWindowPos` at `0x180024a82`
- `USER32!EndDeferWindowPos` at `0x180024a82`
- `USER32!EqualRect` at `0x18002486b`
- `USER32!EqualRect` at `0x1800249df`
- `USER32!EqualRect` at `0x18002486b`
- `USER32!EqualRect` at `0x1800249df`
- `USER32!SetRectEmpty` at `0x180024a8c`
- `USER32!SetRectEmpty` at `0x180024a8c`
- `USER32!IsRectEmpty` at `0x18002468a`
- `USER32!IsRectEmpty` at `0x18002468a`

## pseudocode

```c
LONG *__fastcall CDockBar::CalcFixedLayout(__int64 a1, LONG *a2, __int64 a3, __int64 a4)
{
  int v4; // r15d
  LONG v7; // r13d
  int v8; // eax
  struct CFrameWnd *ParentFrame; // rax
  HDWP v10; // rax
  int v11; // r12d
  int v12; // ecx
  LONG v13; // edi
  LONG v14; // esi
  struct CControlBar *DockedControlBar; // r15
  void **v16; // rax
  __int64 v17; // r9
  HWND v18; // rcx
  LONG left; // ecx
  LONG v20; // edx
  LONG top; // edx
  LONG v22; // eax
  int v23; // r8d
  int v24; // ecx
  LONG v25; // ecx
  LONG v27; // eax
  LONG v28; // eax
  LONG v29; // eax
  int v30; // [rsp+30h] [rbp-59h]
  int v31; // [rsp+34h] [rbp-55h]
  int v32; // [rsp+38h] [rbp-51h]
  int v33; // [rsp+40h] [rbp-49h] BYREF
  int v34; // [rsp+44h] [rbp-45h]
  LONG v35; // [rsp+48h] [rbp-41h]
  int v36; // [rsp+4Ch] [rbp-3Dh]
  HDWP hWinPosInfo[2]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v38; // [rsp+60h] [rbp-29h]
  __int64 v39; // [rsp+70h] [rbp-19h]
  struct tagRECT rc; // [rsp+78h] [rbp-11h] BYREF
  struct tagRECT Rect; // [rsp+88h] [rbp-1h] BYREF
  struct tagRECT v42; // [rsp+98h] [rbp+Fh] BYREF

  v4 = a4;
  v32 = a4;
  v36 = a3;
  CControlBar::CalcFixedLayout(a1, a2, a3, a4);
  if ( IsRectEmpty((const RECT *)(a1 + 260)) )
  {
    ParentFrame = CWnd::GetParentFrame((CWnd *)a1);
    GetClientRect(*((HWND *)ParentFrame + 8), &Rect);
    v7 = Rect.right - Rect.left;
    v8 = Rect.bottom - Rect.top;
  }
  else
  {
    v7 = *(_DWORD *)(a1 + 268) - *(_DWORD *)(a1 + 260);
    v8 = *(_DWORD *)(a1 + 272) - *(_DWORD *)(a1 + 264);
  }
  v35 = v8;
  *(_OWORD *)hWinPosInfo = 0;
  v39 = 0;
  v38 = 0;
  if ( *(_DWORD *)(a1 + 256) )
  {
    v10 = hWinPosInfo[0];
  }
  else
  {
    v10 = BeginDeferWindowPos(*(_DWORD *)(a1 + 232));
    hWinPosInfo[0] = v10;
  }
  v11 = 0;
  v12 = 0;
  v13 = -dword_1801319D0;
  v30 = 0;
  v14 = -dy;
  v31 = 0;
  if ( *(__int64 *)(a1 + 232) > 0 )
  {
    while ( 1 )
    {
      DockedControlBar = CDockBar::GetDockedControlBar((CDockBar *)a1, v12);
      v16 = CPtrArray::ElementAt((CPtrArray *)(a1 + 216), v31);
      if ( DockedControlBar )
      {
        if ( (*(unsigned int (__fastcall **)(struct CControlBar *))(*(_QWORD *)DockedControlBar + 416LL))(DockedControlBar) )
        {
          if ( (*((_BYTE *)DockedControlBar + 172) & 5) == 5 )
            v17 = 6;
          else
            v17 = (*((_DWORD *)DockedControlBar + 43) & 0xA000) != 0 ? 10 : 16;
          (*(void (__fastcall **)(struct CControlBar *, int *, __int64, __int64))(*(_QWORD *)DockedControlBar + 392LL))(
            DockedControlBar,
            &v33,
            0xFFFFFFFFLL,
            v17);
          rc.left = v13;
          rc.right = v13 + v33;
          rc.top = v14;
          v18 = (HWND)*((_QWORD *)DockedControlBar + 8);
          rc.bottom = v14 + v34;
          GetWindowRect(v18, &Rect);
          CWnd::ScreenToClient((CWnd *)a1, &Rect);
          if ( v32 )
          {
            left = rc.left;
            if ( Rect.left > rc.left && !*(_DWORD *)(a1 + 208) )
            {
              OffsetRect(&rc, Rect.left - rc.left, 0);
              left = rc.left;
            }
            if ( rc.right > v7 && !*(_DWORD *)(a1 + 208) )
            {
              v20 = left + dword_1801319D0 + v7 - rc.right;
              if ( v20 <= v13 )
                v20 = v13;
              OffsetRect(&rc, v20 - left, 0);
              left = rc.left;
            }
            if ( v30 )
            {
              v30 = 0;
              OffsetRect(&rc, -(left + dword_1801319D0), 0);
            }
            else if ( left >= v7 - dword_1801319D0
                   && v31 > 0
                   && *CPtrArray::ElementAt((CPtrArray *)(a1 + 216), v31 - 1LL) )
            {
              goto LABEL_34;
            }
            if ( !EqualRect(&rc, &Rect) )
            {
              if ( !*(_DWORD *)(a1 + 256) && (*((_BYTE *)DockedControlBar + 172) & 1) == 0 )
                *(struct tagRECT *)(*((_QWORD *)DockedControlBar + 25) + 172LL) = rc;
              AfxRepositionWindow((struct AFX_SIZEPARENTPARAMS *)hWinPosInfo, *((HWND *)DockedControlBar + 8), &rc);
            }
            v13 = rc.left + v33 - dword_1801319D0;
            if ( v11 <= v34 )
              v11 = v34;
LABEL_56:
            (*(void (__fastcall **)(struct CControlBar *, HDWP *))(*(_QWORD *)DockedControlBar + 424LL))(
              DockedControlBar,
              hWinPosInfo);
            goto LABEL_57;
          }
          top = rc.top;
          if ( Rect.top > rc.top && !*(_DWORD *)(a1 + 208) )
          {
            OffsetRect(&rc, 0, Rect.top - rc.top);
            top = rc.top;
          }
          v22 = v35;
          if ( rc.bottom > v35 && !*(_DWORD *)(a1 + 208) )
          {
            v23 = dy + top + v35 - rc.bottom;
            if ( v23 <= v14 )
              v23 = v14;
            OffsetRect(&rc, 0, v23 - top);
            top = rc.top;
            v22 = v35;
          }
          if ( v30 )
          {
            v30 = 0;
            OffsetRect(&rc, 0, -(top + dy));
          }
          else if ( top >= v22 - dy && v31 > 0 && *CPtrArray::ElementAt((CPtrArray *)(a1 + 216), v31 - 1LL) )
          {
LABEL_34:
            CPtrArray::InsertAt((CPtrArray *)(a1 + 216), v31, 0, 1);
            v30 = 1;
LABEL_73:
            v4 = v32;
            if ( v11 )
            {
              v27 = *a2;
              if ( v32 )
              {
                v14 += v11 - dy;
                if ( v27 <= v13 )
                  v27 = v13;
                *a2 = v27;
                v28 = a2[1];
                if ( v28 <= v14 )
                  v28 = v14;
                a2[1] = v28;
                v13 = -dword_1801319D0;
              }
              else
              {
                v13 += v11 - dword_1801319D0;
                if ( v27 <= v13 )
                  v27 = v13;
                *a2 = v27;
                v29 = a2[1];
                if ( v29 <= v14 )
                  v29 = v14;
                a2[1] = v29;
                v14 = -dy;
              }
              v11 = 0;
            }
            goto LABEL_58;
          }
          if ( !EqualRect(&rc, &Rect) )
          {
            if ( !*(_DWORD *)(a1 + 256) && (*((_BYTE *)DockedControlBar + 172) & 1) == 0 )
              *(struct tagRECT *)(*((_QWORD *)DockedControlBar + 25) + 172LL) = rc;
            AfxRepositionWindow((struct AFX_SIZEPARENTPARAMS *)hWinPosInfo, *((HWND *)DockedControlBar + 8), &rc);
          }
          v14 = v34 + rc.top - dy;
          if ( v11 > v33 )
            goto LABEL_56;
          v11 = v33;
        }
        if ( !v30 )
          goto LABEL_56;
      }
      else if ( !*v16 )
      {
        goto LABEL_73;
      }
LABEL_57:
      v4 = v32;
LABEL_58:
      v12 = ++v31;
      if ( v31 >= *(_QWORD *)(a1 + 232) )
      {
        v10 = hWinPosInfo[0];
        break;
      }
    }
  }
  if ( !*(_DWORD *)(a1 + 256) && v10 )
    EndDeferWindowPos(v10);
  SetRectEmpty(&v42);
  CControlBar::CalcInsideRect((CControlBar *)a1, (struct CRect *)&v42, v4);
  v24 = v36;
  if ( v36 && v4 )
    goto LABEL_69;
  if ( *a2 )
    *a2 = v42.left + *a2 - v42.right;
  if ( !v24 || v4 )
  {
LABEL_69:
    v25 = a2[1];
    if ( v25 )
      a2[1] = v42.top + v25 - v42.bottom;
  }
  return a2;
}

```

## disassembly

```asm
0x180024640  mov     [rsp-8+arg_10], rbx
0x180024645  push    rbp
0x180024646  push    rsi
0x180024647  push    rdi
0x180024648  push    r12
0x18002464a  push    r13
0x18002464c  push    r14
0x18002464e  push    r15
0x180024650  lea     rbp, [rsp-27h]
0x180024655  sub     rsp, 0B0h
0x18002465c  mov     rax, cs:__security_cookie
0x180024663  xor     rax, rsp
0x180024666  mov     [rbp+57h+var_38], rax
0x18002466a  mov     r15d, r9d
0x18002466d  mov     [rbp+57h+var_A8], r9d
0x180024671  mov     [rbp+57h+var_94], r8d
0x180024675  mov     r14, rdx
0x180024678  mov     rbx, rcx
0x18002467b  call    ?CalcFixedLayout@CControlBar@@UEAA?AVCSize@@HH@Z; CControlBar::CalcFixedLayout(int,int)
0x180024680  lea     rdi, [rbx+104h]
0x180024687  mov     rcx, rdi; lprc
0x18002468a  call    cs:__imp_IsRectEmpty
0x180024690  test    eax, eax
0x180024692  jnz     short loc_1800246A3
0x180024694  mov     r13d, [rdi+8]
0x180024698  sub     r13d, [rdi]
0x18002469b  mov     eax, [rdi+0Ch]
0x18002469e  sub     eax, [rdi+4]
0x1800246a1  jmp     short loc_1800246C7
0x1800246a3  mov     rcx, rbx; this
0x1800246a6  call    ?GetParentFrame@CWnd@@QEBAPEAVCFrameWnd@@XZ; CWnd::GetParentFrame(void)
0x1800246ab  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800246af  mov     rcx, [rax+40h]; hWnd
0x1800246b3  call    cs:__imp_GetClientRect
0x1800246b9  mov     r13d, [rbp+57h+Rect.right]
0x1800246bd  sub     r13d, [rbp+57h+Rect.left]
0x1800246c1  mov     eax, [rbp+57h+Rect.bottom]
0x1800246c4  sub     eax, [rbp+57h+Rect.top]
0x1800246c7  xorps   xmm0, xmm0
0x1800246ca  mov     [rbp+57h+var_98], eax
0x1800246cd  xor     eax, eax
0x1800246cf  movups  xmmword ptr [rbp+57h+hWinPosInfo], xmm0
0x1800246d3  mov     [rbp+57h+var_70], rax
0x1800246d7  movups  [rbp+57h+var_80], xmm0
0x1800246db  cmp     [rbx+100h], eax
0x1800246e1  jz      short loc_1800246E9
0x1800246e3  mov     rax, [rbp+57h+hWinPosInfo]
0x1800246e7  jmp     short loc_1800246F9
0x1800246e9  mov     ecx, [rbx+0E8h]; nNumWindows
0x1800246ef  call    cs:__imp_BeginDeferWindowPos
0x1800246f5  mov     [rbp+57h+hWinPosInfo], rax
0x1800246f9  mov     edi, cs:dword_1801319D0
0x1800246ff  xor     r12d, r12d
0x180024702  mov     esi, cs:dy
0x180024708  xor     ecx, ecx
0x18002470a  neg     edi
0x18002470c  mov     [rbp+57h+var_B0], r12d
0x180024710  neg     esi
0x180024712  mov     [rbp+57h+var_AC], ecx
0x180024715  cmp     [rbx+0E8h], rcx
0x18002471c  jle     loc_180024A71
0x180024722  mov     edx, ecx; int
0x180024724  mov     rcx, rbx; this
0x180024727  call    ?GetDockedControlBar@CDockBar@@IEBAPEAVCControlBar@@H@Z; CDockBar::GetDockedControlBar(int)
0x18002472c  movsxd  rdx, [rbp+57h+var_AC]; __int64
0x180024730  lea     rcx, [rbx+0D8h]; this
0x180024737  mov     r15, rax
0x18002473a  call    ?ElementAt@CPtrArray@@QEAAAEAPEAX_J@Z; CPtrArray::ElementAt(__int64)
0x18002473f  test    r15, r15
0x180024742  jz      loc_180024B02
0x180024748  mov     rax, [r15]
0x18002474b  mov     rcx, r15
0x18002474e  mov     rax, [rax+1A0h]
0x180024755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002475a  test    eax, eax
0x18002475c  jz      loc_180024A35
0x180024762  mov     ecx, [r15+0ACh]
0x180024769  mov     eax, ecx
0x18002476b  and     eax, 5
0x18002476e  cmp     al, 5
0x180024770  jnz     short loc_18002477A
0x180024772  mov     r9d, 6
0x180024778  jmp     short loc_18002478D
0x18002477a  and     ecx, 0A000h
0x180024780  neg     ecx
0x180024782  sbb     r9d, r9d
0x180024785  and     r9d, 0FFFFFFFAh
0x180024789  add     r9d, 10h
0x18002478d  mov     rax, [r15]
0x180024790  lea     rdx, [rbp+57h+var_A0]
0x180024794  or      r8d, 0FFFFFFFFh
0x180024798  mov     rcx, r15
0x18002479b  mov     rax, [rax+188h]
0x1800247a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247a7  mov     ecx, [rbp+57h+var_9C]
0x1800247aa  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800247ae  mov     eax, [rbp+57h+var_A0]
0x1800247b1  add     eax, edi
0x1800247b3  mov     [rbp+57h+rc.left], edi
0x1800247b6  mov     [rbp+57h+rc.right], eax
0x1800247b9  lea     eax, [rsi+rcx]
0x1800247bc  mov     [rbp+57h+rc.top], esi
0x1800247bf  mov     rcx, [r15+40h]; hWnd
0x1800247c3  mov     [rbp+57h+rc.bottom], eax
0x1800247c6  call    cs:__imp_GetWindowRect
0x1800247cc  lea     rdx, [rbp+57h+Rect]; struct tagRECT *
0x1800247d0  mov     rcx, rbx; this
0x1800247d3  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x1800247d8  cmp     [rbp+57h+var_A8], 0
0x1800247dc  jz      loc_18002491E
0x1800247e2  mov     edx, [rbp+57h+Rect.left]
0x1800247e5  mov     ecx, [rbp+57h+rc.left]
0x1800247e8  cmp     edx, ecx
0x1800247ea  jle     short loc_180024807
0x1800247ec  cmp     dword ptr [rbx+0D0h], 0
0x1800247f3  jnz     short loc_180024807
0x1800247f5  sub     edx, ecx; dx
0x1800247f7  xor     r8d, r8d; dy
0x1800247fa  lea     rcx, [rbp+57h+rc]; lprc
0x1800247fe  call    cs:__imp_OffsetRect
0x180024804  mov     ecx, [rbp+57h+rc.left]
0x180024807  cmp     [rbp+57h+rc.right], r13d
0x18002480b  jle     short loc_18002483B
0x18002480d  cmp     dword ptr [rbx+0D0h], 0
0x180024814  jnz     short loc_18002483B
0x180024816  mov     edx, r13d
0x180024819  sub     edx, [rbp+57h+rc.right]
0x18002481c  add     edx, cs:dword_1801319D0
0x180024822  add     edx, ecx
0x180024824  cmp     edx, edi
0x180024826  cmovle  edx, edi
0x180024829  xor     r8d, r8d; dy
0x18002482c  sub     edx, ecx; dx
0x18002482e  lea     rcx, [rbp+57h+rc]; lprc
0x180024832  call    cs:__imp_OffsetRect
0x180024838  mov     ecx, [rbp+57h+rc.left]
0x18002483b  cmp     [rbp+57h+var_B0], 0
0x18002483f  jz      loc_1800248CA
0x180024845  mov     edx, cs:dword_1801319D0
0x18002484b  xor     r8d, r8d; dy
0x18002484e  add     edx, ecx
0x180024850  mov     [rbp+57h+var_B0], 0
0x180024857  neg     edx; dx
0x180024859  lea     rcx, [rbp+57h+rc]; lprc
0x18002485d  call    cs:__imp_OffsetRect
0x180024863  lea     rdx, [rbp+57h+Rect]; lprc2
0x180024867  lea     rcx, [rbp+57h+rc]; lprc1
0x18002486b  call    cs:__imp_EqualRect
0x180024871  test    eax, eax
0x180024873  jnz     short loc_1800248AB
0x180024875  cmp     [rbx+100h], eax
0x18002487b  jnz     short loc_18002489A
0x18002487d  test    byte ptr [r15+0ACh], 1
0x180024885  jnz     short loc_18002489A
0x180024887  mov     rax, [r15+0C8h]
0x18002488e  movups  xmm0, xmmword ptr [rbp+57h+rc.left]
0x180024892  movdqu  xmmword ptr [rax+0ACh], xmm0
0x18002489a  mov     rdx, [r15+40h]; HWND
0x18002489e  lea     r8, [rbp+57h+rc]; struct tagRECT *
0x1800248a2  lea     rcx, [rbp+57h+hWinPosInfo]; struct AFX_SIZEPARENTPARAMS *
0x1800248a6  call    ?AfxRepositionWindow@@YAXPEAUAFX_SIZEPARENTPARAMS@@PEAUHWND__@@PEBUtagRECT@@@Z; AfxRepositionWindow(AFX_SIZEPARENTPARAMS *,HWND__ *,tagRECT const *)
0x1800248ab  mov     edi, [rbp+57h+var_A0]
0x1800248ae  sub     edi, cs:dword_1801319D0
0x1800248b4  add     edi, [rbp+57h+rc.left]
0x1800248b7  cmp     r12d, [rbp+57h+var_9C]
0x1800248bb  jg      loc_180024A3B
0x1800248c1  mov     r12d, [rbp+57h+var_9C]
0x1800248c5  jmp     loc_180024A3B
0x1800248ca  mov     eax, r13d
0x1800248cd  sub     eax, cs:dword_1801319D0
0x1800248d3  cmp     ecx, eax
0x1800248d5  jl      short loc_180024863
0x1800248d7  movsxd  rax, [rbp+57h+var_AC]
0x1800248db  test    eax, eax
0x1800248dd  jle     short loc_180024863
0x1800248df  lea     rdx, [rax-1]; __int64
0x1800248e3  lea     rcx, [rbx+0D8h]; this
0x1800248ea  call    ?ElementAt@CPtrArray@@QEAAAEAPEAX_J@Z; CPtrArray::ElementAt(__int64)
0x1800248ef  cmp     qword ptr [rax], 0
0x1800248f3  jz      loc_180024863
0x1800248f9  movsxd  rdx, [rbp+57h+var_AC]; __int64
0x1800248fd  lea     rcx, [rbx+0D8h]; this
0x180024904  mov     r15d, 1
0x18002490a  xor     r8d, r8d; void *
0x18002490d  mov     r9d, r15d; __int64
0x180024910  call    ?InsertAt@CPtrArray@@QEAAX_JPEAX0@Z; CPtrArray::InsertAt(__int64,void *,__int64)
0x180024915  mov     [rbp+57h+var_B0], r15d
0x180024919  jmp     loc_180024B0C
0x18002491e  mov     r8d, [rbp+57h+Rect.top]
0x180024922  mov     edx, [rbp+57h+rc.top]
0x180024925  cmp     r8d, edx
0x180024928  jle     short loc_180024945
0x18002492a  cmp     dword ptr [rbx+0D0h], 0
0x180024931  jnz     short loc_180024945
0x180024933  sub     r8d, edx; dy
0x180024936  lea     rcx, [rbp+57h+rc]; lprc
0x18002493a  xor     edx, edx; dx
0x18002493c  call    cs:__imp_OffsetRect
0x180024942  mov     edx, [rbp+57h+rc.top]
0x180024945  mov     eax, [rbp+57h+var_98]
0x180024948  cmp     [rbp+57h+rc.bottom], eax
0x18002494b  jle     short loc_180024983
0x18002494d  cmp     dword ptr [rbx+0D0h], 0
0x180024954  jnz     short loc_180024983
0x180024956  mov     r8d, eax
0x180024959  lea     rcx, [rbp+57h+rc]; lprc
0x18002495d  sub     r8d, [rbp+57h+rc.bottom]
0x180024961  add     r8d, edx
0x180024964  add     r8d, cs:dy
0x18002496b  cmp     r8d, esi
0x18002496e  cmovle  r8d, esi
0x180024972  sub     r8d, edx; dy
0x180024975  xor     edx, edx; dx
0x180024977  call    cs:__imp_OffsetRect
0x18002497d  mov     edx, [rbp+57h+rc.top]
0x180024980  mov     eax, [rbp+57h+var_98]
0x180024983  cmp     [rbp+57h+var_B0], 0
0x180024987  jz      short loc_1800249AB
0x180024989  mov     r8d, cs:dy
0x180024990  lea     rcx, [rbp+57h+rc]; lprc
0x180024994  add     r8d, edx
0x180024997  mov     [rbp+57h+var_B0], 0
0x18002499e  neg     r8d; dy
0x1800249a1  xor     edx, edx; dx
0x1800249a3  call    cs:__imp_OffsetRect
0x1800249a9  jmp     short loc_1800249D7
0x1800249ab  sub     eax, cs:dy
0x1800249b1  cmp     edx, eax
0x1800249b3  jl      short loc_1800249D7
0x1800249b5  movsxd  rcx, [rbp+57h+var_AC]
0x1800249b9  test    ecx, ecx
0x1800249bb  jle     short loc_1800249D7
0x1800249bd  lea     rdx, [rcx-1]; __int64
0x1800249c1  lea     rcx, [rbx+0D8h]; this
0x1800249c8  call    ?ElementAt@CPtrArray@@QEAAAEAPEAX_J@Z; CPtrArray::ElementAt(__int64)
0x1800249cd  cmp     qword ptr [rax], 0
0x1800249d1  jnz     loc_1800248F9
0x1800249d7  lea     rdx, [rbp+57h+Rect]; lprc2
0x1800249db  lea     rcx, [rbp+57h+rc]; lprc1
0x1800249df  call    cs:__imp_EqualRect
0x1800249e5  test    eax, eax
0x1800249e7  jnz     short loc_180024A1F
0x1800249e9  cmp     [rbx+100h], eax
0x1800249ef  jnz     short loc_180024A0E
0x1800249f1  test    byte ptr [r15+0ACh], 1
0x1800249f9  jnz     short loc_180024A0E
0x1800249fb  mov     rax, [r15+0C8h]
0x180024a02  movups  xmm0, xmmword ptr [rbp+57h+rc.left]
0x180024a06  movdqu  xmmword ptr [rax+0ACh], xmm0
0x180024a0e  mov     rdx, [r15+40h]; HWND
0x180024a12  lea     r8, [rbp+57h+rc]; struct tagRECT *
0x180024a16  lea     rcx, [rbp+57h+hWinPosInfo]; struct AFX_SIZEPARENTPARAMS *
0x180024a1a  call    ?AfxRepositionWindow@@YAXPEAUAFX_SIZEPARENTPARAMS@@PEAUHWND__@@PEBUtagRECT@@@Z; AfxRepositionWindow(AFX_SIZEPARENTPARAMS *,HWND__ *,tagRECT const *)
0x180024a1f  mov     esi, [rbp+57h+rc.top]
0x180024a22  sub     esi, cs:dy
0x180024a28  add     esi, [rbp+57h+var_9C]
0x180024a2b  cmp     r12d, [rbp+57h+var_A0]
0x180024a2f  jg      short loc_180024A3B
0x180024a31  mov     r12d, [rbp+57h+var_A0]
0x180024a35  cmp     [rbp+57h+var_B0], 0
0x180024a39  jnz     short loc_180024A51
0x180024a3b  mov     rax, [r15]
0x180024a3e  lea     rdx, [rbp+57h+hWinPosInfo]
0x180024a42  mov     rcx, r15
0x180024a45  mov     rax, [rax+1A8h]
0x180024a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a51  mov     r15d, [rbp+57h+var_A8]
0x180024a55  mov     ecx, [rbp+57h+var_AC]
0x180024a58  inc     ecx
0x180024a5a  movsxd  rax, ecx
0x180024a5d  mov     [rbp+57h+var_AC], ecx
0x180024a60  cmp     rax, [rbx+0E8h]
0x180024a67  jl      loc_180024722
0x180024a6d  mov     rax, [rbp+57h+hWinPosInfo]
0x180024a71  cmp     dword ptr [rbx+100h], 0
0x180024a78  jnz     short loc_180024A88
0x180024a7a  test    rax, rax
0x180024a7d  jz      short loc_180024A88
0x180024a7f  mov     rcx, rax; hWinPosInfo
0x180024a82  call    cs:__imp_EndDeferWindowPos
0x180024a88  lea     rcx, [rbp+57h+var_48]; lprc
0x180024a8c  call    cs:__imp_SetRectEmpty
0x180024a92  mov     r8d, r15d; int
0x180024a95  lea     rdx, [rbp+57h+var_48]; struct CRect *
0x180024a99  mov     rcx, rbx; this
0x180024a9c  call    ?CalcInsideRect@CControlBar@@QEBAXAEAVCRect@@H@Z; CControlBar::CalcInsideRect(CRect &,int)
0x180024aa1  mov     ecx, [rbp+57h+var_94]
0x180024aa4  test    ecx, ecx
0x180024aa6  jz      short loc_180024AAD
0x180024aa8  test    r15d, r15d
0x180024aab  jnz     short loc_180024AC6
0x180024aad  mov     eax, [r14]
0x180024ab0  test    eax, eax
0x180024ab2  jz      short loc_180024ABD
0x180024ab4  sub     eax, [rbp+57h+var_48.right]
0x180024ab7  add     eax, [rbp+57h+var_48.left]
0x180024aba  mov     [r14], eax
0x180024abd  test    ecx, ecx
0x180024abf  jz      short loc_180024AC6
0x180024ac1  test    r15d, r15d
  ... truncated ...
```
