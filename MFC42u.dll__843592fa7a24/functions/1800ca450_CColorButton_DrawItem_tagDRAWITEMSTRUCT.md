# CColorButton::DrawItem(tagDRAWITEMSTRUCT *)

- ea: `0x1800ca450`
- end: `0x1800ca674`
- name: `?DrawItem@CColorButton@@MEAAXPEAUtagDRAWITEMSTRUCT@@@Z`
- size: `548`
- prototype: `void __fastcall(CColorButton *__hidden this, struct tagDRAWITEMSTRUCT *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000ce50`
- `0x1800166a0`
- `0x18001dbd0`
- `0x18005d190`
- `0x18005e240`
- `0x1800ca450`
- `0x1800cae24`
- `0x1800cb020`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `USER32!SendMessageW` at `0x1800ca4d6`
- `USER32!SendMessageW` at `0x1800ca632`
- `USER32!SendMessageW` at `0x1800ca4d6`
- `USER32!SendMessageW` at `0x1800ca632`
- `USER32!CopyRect` at `0x1800ca4fa`
- `USER32!CopyRect` at `0x1800ca61d`
- `USER32!CopyRect` at `0x1800ca4fa`
- `USER32!CopyRect` at `0x1800ca61d`
- `USER32!GetSysColor` at `0x1800ca525`
- `USER32!GetSysColor` at `0x1800ca532`
- `USER32!GetSysColor` at `0x1800ca569`
- `USER32!GetSysColor` at `0x1800ca576`
- `USER32!GetSysColor` at `0x1800ca525`
- `USER32!GetSysColor` at `0x1800ca532`
- `USER32!GetSysColor` at `0x1800ca569`
- `USER32!GetSysColor` at `0x1800ca576`
- `USER32!InflateRect` at `0x1800ca50c`
- `USER32!InflateRect` at `0x1800ca55e`
- `USER32!InflateRect` at `0x1800ca5a2`
- `USER32!InflateRect` at `0x1800ca50c`
- `USER32!InflateRect` at `0x1800ca55e`
- `USER32!InflateRect` at `0x1800ca5a2`
- `USER32!FillRect` at `0x1800ca5f6`
- `USER32!FillRect` at `0x1800ca5f6`
- `GDI32!GetNearestColor` at `0x1800ca5c9`
- `GDI32!GetNearestColor` at `0x1800ca5c9`
- `GDI32!RealizePalette` at `0x1800ca4a6`
- `GDI32!RealizePalette` at `0x1800ca4a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CColorButton::DrawItem(CColorButton *this, struct tagDRAWITEMSTRUCT *a2)
{
  struct CPalette *v4; // rbx
  HDC *v5; // rsi
  DWORD SysColor; // ebx
  DWORD v7; // eax
  DWORD v8; // ebx
  DWORD v9; // eax
  CBrush *v10; // rbx
  COLORREF NearestColor; // eax
  CBrush *v12; // rbx
  HBRUSH v13; // r8
  char v14; // al
  struct tagRECT v15; // [rsp+20h] [rbp-30h] BYREF
  struct tagRECT rcDst; // [rsp+30h] [rbp-20h] BYREF

  v4 = CGdiObject::FromHandle(hPal);
  v5 = (HDC *)CDC::FromHandle(a2->hDC);
  CDC::SelectPalette((CDC *)v5, v4, 0);
  RealizePalette(v5[1]);
  if ( a2->itemAction == 1 )
  {
    CopyRect(&rcDst, &a2->rcItem);
    InflateRect(&rcDst, -2, -2);
    if ( *((_DWORD *)this + 32) )
    {
      SysColor = GetSysColor(20);
      v7 = GetSysColor(16);
      v15 = rcDst;
      ((void (__fastcall *)(HDC *, struct tagRECT *, _QWORD, _QWORD))_AfxDraw3DFrame)(v5, &v15, v7, SysColor);
      InflateRect(&rcDst, -1, -1);
      v8 = GetSysColor(20);
      v9 = GetSysColor(16);
      v15 = rcDst;
      ((void (__fastcall *)(HDC *, struct tagRECT *, _QWORD, _QWORD))_AfxDraw3DFrame)(v5, &v15, v9, v8);
      InflateRect(&rcDst, -1, -1);
    }
    v10 = (CBrush *)operator new(0x10u);
    *(_QWORD *)&v15.left = v10;
    if ( v10 )
    {
      NearestColor = GetNearestColor(v5[2], *((_DWORD *)this + 33));
      v12 = CBrush::CBrush(v10, NearestColor);
    }
    else
    {
      v12 = 0;
    }
    if ( v12 )
      v13 = (HBRUSH)*((_QWORD *)v12 + 1);
    else
      v13 = 0;
    FillRect(v5[1], &rcDst, v13);
    if ( v12 )
      (*(void (__fastcall **)(CBrush *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 1);
    goto LABEL_17;
  }
  if ( a2->itemAction != 2 )
  {
    if ( a2->itemAction != 4 )
      return;
LABEL_17:
    CopyRect(&rcDst, &a2->rcItem);
    v14 = SendMessageW(*((HWND *)this + 8), 0xF2u, 0, 0);
    v15 = rcDst;
    _AfxDraw3DButtonFrame(v5, &v15, v14 & 8);
    return;
  }
  if ( (SendMessageW(*((HWND *)this + 8), 0xF2u, 0, 0) & 4) != 0 )
    CColorButton::idClicked = a2->CtlID;
}

```

## disassembly

```asm
0x1800ca450  mov     [rsp-18h+arg_10], rbx
0x1800ca455  mov     [rsp-18h+arg_18], rsi
0x1800ca45a  push    rbp
0x1800ca45b  push    rdi
0x1800ca45c  push    r14
0x1800ca45e  mov     rbp, rsp
0x1800ca461  sub     rsp, 50h
0x1800ca465  mov     rax, cs:__security_cookie
0x1800ca46c  xor     rax, rsp
0x1800ca46f  mov     [rbp+var_10], rax
0x1800ca473  mov     rdi, rdx
0x1800ca476  mov     r14, rcx
0x1800ca479  mov     rcx, cs:?hPal@@3PEAUHPALETTE__@@EA; void *
0x1800ca480  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1800ca485  mov     rbx, rax
0x1800ca488  mov     rcx, [rdi+20h]; HDC
0x1800ca48c  call    ?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x1800ca491  mov     rsi, rax
0x1800ca494  xor     r8d, r8d; int
0x1800ca497  mov     rdx, rbx; struct CPalette *
0x1800ca49a  mov     rcx, rax; this
0x1800ca49d  call    ?SelectPalette@CDC@@QEAAPEAVCPalette@@PEAV2@H@Z; CDC::SelectPalette(CPalette *,int)
0x1800ca4a2  mov     rcx, [rsi+8]; hdc
0x1800ca4a6  call    cs:__imp_RealizePalette
0x1800ca4ac  mov     edx, [rdi+0Ch]
0x1800ca4af  sub     edx, 1
0x1800ca4b2  jz      short loc_1800CA4F2
0x1800ca4b4  sub     edx, 1
0x1800ca4b7  jz      short loc_1800CA4C7
0x1800ca4b9  cmp     edx, 2
0x1800ca4bc  jz      loc_1800CA615
0x1800ca4c2  jmp     loc_1800CA653
0x1800ca4c7  xor     r9d, r9d; lParam
0x1800ca4ca  xor     r8d, r8d; wParam
0x1800ca4cd  mov     edx, 0F2h; Msg
0x1800ca4d2  mov     rcx, [r14+40h]; hWnd
0x1800ca4d6  call    cs:__imp_SendMessageW
0x1800ca4dc  test    al, 4
0x1800ca4de  jz      loc_1800CA653
0x1800ca4e4  mov     eax, [rdi+4]
0x1800ca4e7  mov     cs:?idClicked@CColorButton@@2IA, eax; uint CColorButton::idClicked
0x1800ca4ed  jmp     loc_1800CA653
0x1800ca4f2  lea     rdx, [rdi+28h]; lprcSrc
0x1800ca4f6  lea     rcx, [rbp+rcDst]; lprcDst
0x1800ca4fa  call    cs:__imp_CopyRect
0x1800ca500  mov     edx, 0FFFFFFFEh; dx
0x1800ca505  mov     r8d, edx; dy
0x1800ca508  lea     rcx, [rbp+rcDst]; lprc
0x1800ca50c  call    cs:__imp_InflateRect
0x1800ca512  cmp     dword ptr [r14+80h], 0
0x1800ca51a  jz      loc_1800CA5A8
0x1800ca520  mov     ecx, 14h; nIndex
0x1800ca525  call    cs:__imp_GetSysColor
0x1800ca52b  mov     ebx, eax
0x1800ca52d  mov     ecx, 10h; nIndex
0x1800ca532  call    cs:__imp_GetSysColor
0x1800ca538  movaps  xmm0, xmmword ptr [rbp+rcDst.left]
0x1800ca53c  movdqa  [rbp+var_30], xmm0
0x1800ca541  mov     r9d, ebx
0x1800ca544  mov     r8d, eax
0x1800ca547  lea     rdx, [rbp+var_30]
0x1800ca54b  mov     rcx, rsi
0x1800ca54e  call    ?_AfxDraw3DFrame@@YAXPEAVCDC@@VCRect@@KK@Z; _AfxDraw3DFrame(CDC *,CRect,ulong,ulong)
0x1800ca553  or      r8d, 0FFFFFFFFh; dy
0x1800ca557  or      edx, r8d; dx
0x1800ca55a  lea     rcx, [rbp+rcDst]; lprc
0x1800ca55e  call    cs:__imp_InflateRect
0x1800ca564  mov     ecx, 14h; nIndex
0x1800ca569  call    cs:__imp_GetSysColor
0x1800ca56f  mov     ebx, eax
0x1800ca571  mov     ecx, 10h; nIndex
0x1800ca576  call    cs:__imp_GetSysColor
0x1800ca57c  movaps  xmm0, xmmword ptr [rbp+rcDst.left]
0x1800ca580  movdqa  [rbp+var_30], xmm0
0x1800ca585  mov     r9d, ebx
0x1800ca588  mov     r8d, eax
0x1800ca58b  lea     rdx, [rbp+var_30]
0x1800ca58f  mov     rcx, rsi
0x1800ca592  call    ?_AfxDraw3DFrame@@YAXPEAVCDC@@VCRect@@KK@Z; _AfxDraw3DFrame(CDC *,CRect,ulong,ulong)
0x1800ca597  or      r8d, 0FFFFFFFFh; dy
0x1800ca59b  or      edx, r8d; dx
0x1800ca59e  lea     rcx, [rbp+rcDst]; lprc
0x1800ca5a2  call    cs:__imp_InflateRect
0x1800ca5a8  mov     ecx, 10h; Size
0x1800ca5ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ca5b2  mov     rbx, rax
0x1800ca5b5  mov     qword ptr [rbp+var_30], rax
0x1800ca5b9  test    rax, rax
0x1800ca5bc  jz      short loc_1800CA5DE
0x1800ca5be  mov     edx, [r14+84h]; color
0x1800ca5c5  mov     rcx, [rsi+10h]; hdc
0x1800ca5c9  call    cs:__imp_GetNearestColor
0x1800ca5cf  mov     edx, eax; color
0x1800ca5d1  mov     rcx, rbx; this
0x1800ca5d4  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x1800ca5d9  mov     rbx, rax
0x1800ca5dc  jmp     short loc_1800CA5E0
0x1800ca5de  xor     ebx, ebx
0x1800ca5e0  test    rbx, rbx
0x1800ca5e3  jnz     short loc_1800CA5EA
0x1800ca5e5  xor     r8d, r8d
0x1800ca5e8  jmp     short loc_1800CA5EE
0x1800ca5ea  mov     r8, [rbx+8]; hbr
0x1800ca5ee  lea     rdx, [rbp+rcDst]; lprc
0x1800ca5f2  mov     rcx, [rsi+8]; hDC
0x1800ca5f6  call    cs:__imp_FillRect
0x1800ca5fc  test    rbx, rbx
0x1800ca5ff  jz      short loc_1800CA615
0x1800ca601  mov     rax, [rbx]
0x1800ca604  mov     edx, 1
0x1800ca609  mov     rcx, rbx
0x1800ca60c  mov     rax, [rax+8]
0x1800ca610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca615  lea     rdx, [rdi+28h]; lprcSrc
0x1800ca619  lea     rcx, [rbp+rcDst]; lprcDst
0x1800ca61d  call    cs:__imp_CopyRect
0x1800ca623  xor     r9d, r9d; lParam
0x1800ca626  xor     r8d, r8d; wParam
0x1800ca629  mov     edx, 0F2h; Msg
0x1800ca62e  mov     rcx, [r14+40h]; hWnd
0x1800ca632  call    cs:__imp_SendMessageW
0x1800ca638  and     eax, 8
0x1800ca63b  movaps  xmm0, xmmword ptr [rbp+rcDst.left]
0x1800ca63f  movdqa  [rbp+var_30], xmm0
0x1800ca644  mov     r8d, eax
0x1800ca647  lea     rdx, [rbp+var_30]
0x1800ca64b  mov     rcx, rsi
0x1800ca64e  call    ?_AfxDraw3DButtonFrame@@YAXPEAVCDC@@VCRect@@H@Z; _AfxDraw3DButtonFrame(CDC *,CRect,int)
0x1800ca653  mov     rcx, [rbp+var_10]
0x1800ca657  xor     rcx, rsp; StackCookie
0x1800ca65a  call    __security_check_cookie
0x1800ca65f  lea     r11, [rsp+50h+var_s0]
0x1800ca664  mov     rbx, [r11+30h]
0x1800ca668  mov     rsi, [r11+38h]
0x1800ca66c  mov     rsp, r11
0x1800ca66f  pop     r14
0x1800ca671  pop     rdi
0x1800ca672  pop     rbp
0x1800ca673  retn
```
