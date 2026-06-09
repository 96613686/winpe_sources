# CSelectionRect::RenderAndSetDynamic(HWND__ *,HDC__ *,tagRECT &,int)

- ea: `0x1800e5160`
- end: `0x1800e5471`
- name: `?RenderAndSetDynamic@CSelectionRect@@QEAAHPEAUHWND__@@PEAUHDC__@@AEAUtagRECT@@H@Z`
- size: `785`
- prototype: `int(CSelectionRect *__hidden this, HWND, HDC, struct tagRECT *, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800d7fd0`
- `0x1800e0efc`
- `0x1800e6370`
- `0x1800f148c`

## callees

- `0x1800e4e5c`
- `0x1800e5160`
- `0x1800e5634`
- `0x180104f30`

## import_xrefs

- `USER32!InflateRect` at `0x1800e522c`
- `USER32!InflateRect` at `0x1800e526b`
- `USER32!InflateRect` at `0x1800e52e0`
- `USER32!InflateRect` at `0x1800e530f`
- `USER32!InflateRect` at `0x1800e53f4`
- `USER32!InflateRect` at `0x1800e542e`
- `USER32!InflateRect` at `0x1800e522c`
- `USER32!InflateRect` at `0x1800e526b`
- `USER32!InflateRect` at `0x1800e52e0`
- `USER32!InflateRect` at `0x1800e530f`
- `USER32!InflateRect` at `0x1800e53f4`
- `USER32!InflateRect` at `0x1800e542e`
- `USER32!CopyRect` at `0x1800e5377`
- `USER32!CopyRect` at `0x1800e540d`
- `USER32!CopyRect` at `0x1800e5377`
- `USER32!CopyRect` at `0x1800e540d`
- `USER32!DrawFocusRect` at `0x1800e5401`
- `USER32!DrawFocusRect` at `0x1800e543b`
- `USER32!DrawFocusRect` at `0x1800e5401`
- `USER32!DrawFocusRect` at `0x1800e543b`
- `USER32!EqualRect` at `0x1800e51db`
- `USER32!EqualRect` at `0x1800e51db`
- `GDI32!SetMapMode` at `0x1800e53a6`
- `GDI32!SetMapMode` at `0x1800e53a6`
- `GDI32!CombineRgn` at `0x1800e5297`
- `GDI32!CombineRgn` at `0x1800e533b`
- `GDI32!CombineRgn` at `0x1800e5297`
- `GDI32!CombineRgn` at `0x1800e533b`
- `GDI32!CreateRectRgn` at `0x1800e5240`
- `GDI32!CreateRectRgn` at `0x1800e527f`
- `GDI32!CreateRectRgn` at `0x1800e52f4`
- `GDI32!CreateRectRgn` at `0x1800e5323`
- `GDI32!CreateRectRgn` at `0x1800e5240`
- `GDI32!CreateRectRgn` at `0x1800e527f`
- `GDI32!CreateRectRgn` at `0x1800e52f4`
- `GDI32!CreateRectRgn` at `0x1800e5323`
- `GDI32!RestoreDC` at `0x1800e5449`
- `GDI32!RestoreDC` at `0x1800e5449`
- `GDI32!SetViewportOrgEx` at `0x1800e53b7`
- `GDI32!SetViewportOrgEx` at `0x1800e53b7`
- `GDI32!SetWindowOrgEx` at `0x1800e53c8`
- `GDI32!SetWindowOrgEx` at `0x1800e53c8`
- `GDI32!SaveDC` at `0x1800e5398`
- `GDI32!SaveDC` at `0x1800e5398`
- `GDI32!DeleteObject` at `0x1800e52bb`
- `GDI32!DeleteObject` at `0x1800e52c4`
- `GDI32!DeleteObject` at `0x1800e5360`
- `GDI32!DeleteObject` at `0x1800e5369`
- `GDI32!DeleteObject` at `0x1800e52bb`
- `GDI32!DeleteObject` at `0x1800e52c4`
- `GDI32!DeleteObject` at `0x1800e5360`
- `GDI32!DeleteObject` at `0x1800e5369`

## pseudocode

```c
__int64 __fastcall CSelectionRect::RenderAndSetDynamic(RECT *this, HWND a2, HDC a3, struct tagRECT *a4, int a5)
{
  LONG left; // r12d
  struct tagRECT *v6; // rdi
  unsigned int v7; // esi
  RECT *v11; // r9
  CSelectionRect *v12; // rcx
  __int64 v13; // kr00_8
  int v14; // edi
  int v15; // ebx
  int v16; // r15d
  HRGN RectRgn; // rax
  HRGN v18; // rsi
  int v19; // r14d
  int v20; // r13d
  HRGN v21; // rbx
  HRGN v22; // rdi
  HRGN v23; // rbx
  int v25; // r14d
  CSelectionRect *v26; // rcx
  CSelectionRect *v27; // rcx
  int v28; // [rsp+28h] [rbp-59h]
  int v29; // [rsp+28h] [rbp-59h]
  struct tagRECT *lprcDst; // [rsp+48h] [rbp-39h]
  struct tagRECT rc; // [rsp+50h] [rbp-31h] BYREF
  RECT rc2; // [rsp+60h] [rbp-21h] BYREF
  RECT rc1; // [rsp+70h] [rbp-11h] BYREF

  left = this[3].left;
  v6 = this + 1;
  v7 = 1;
  rc2 = this[1];
  this[3].left = 1;
  lprcDst = this + 1;
  CSelectionRect::NormalizeRect((CSelectionRect *)this, &rc2);
  rc1 = *v11;
  CSelectionRect::NormalizeRect(v12, &rc1);
  if ( !EqualRect(&rc1, &rc2) || a5 )
  {
    if ( this[4].bottom == 3 )
    {
      v13 = this[4].left + 1;
      rc = rc2;
      v14 = v13 / 2;
      v15 = (this[4].top + 1) / 2;
      v16 = v15 + 8;
      InflateRect(&rc, v14 + 8, v15 + 8);
      RectRgn = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom);
      rc = rc2;
      v18 = RectRgn;
      v19 = 8 - v15;
      v20 = 8 - v14;
      InflateRect(&rc, 8 - v14, 8 - v15);
      v21 = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom);
      CombineRgn(v18, v18, v21, 4);
      CSelectionRect::_InvalidateWindow((CSelectionRect *)this, a2, 0, v18, 0, v28);
      DeleteObject(v18);
      DeleteObject(v21);
      rc = *a4;
      InflateRect(&rc, v14 + 8, v16);
      v22 = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom);
      rc = *a4;
      InflateRect(&rc, v20, v19);
      v23 = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom);
      CombineRgn(v22, v22, v23, 4);
      v7 = 1;
      CSelectionRect::_InvalidateWindow((CSelectionRect *)this, a2, 0, v22, 1, v29);
      DeleteObject(v22);
      DeleteObject(v23);
      CopyRect(lprcDst, a4);
    }
    else
    {
      rc = 0;
      if ( !a3 )
        return 0;
      v25 = SaveDC(a3);
      SetMapMode(a3, 1);
      SetViewportOrgEx(a3, 0, 0, 0);
      SetWindowOrgEx(a3, 0, 0, 0);
      if ( left )
      {
        rc = *v6;
        CSelectionRect::NormalizeRect(v26, &rc);
        InflateRect(&rc, 8, 8);
        DrawFocusRect(a3, &rc);
      }
      CopyRect(v6, a4);
      rc = *v6;
      CSelectionRect::NormalizeRect(v27, &rc);
      InflateRect(&rc, 8, 8);
      v7 = DrawFocusRect(a3, &rc);
      RestoreDC(a3, v25);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800e5160  push    rbp
0x1800e5162  push    rbx
0x1800e5163  push    rsi
0x1800e5164  push    rdi
0x1800e5165  push    r12
0x1800e5167  push    r13
0x1800e5169  push    r14
0x1800e516b  push    r15
0x1800e516d  lea     rbp, [rsp-17h]
0x1800e5172  sub     rsp, 98h
0x1800e5179  mov     rax, cs:__security_cookie
0x1800e5180  xor     rax, rsp
0x1800e5183  mov     [rbp+4Fh+var_50], rax
0x1800e5187  mov     r12d, [rcx+30h]
0x1800e518b  lea     rdi, [rcx+10h]
0x1800e518f  movups  xmm0, xmmword ptr [rdi]
0x1800e5192  mov     [rbp+4Fh+var_A0], rdx
0x1800e5196  mov     esi, 1
0x1800e519b  lea     rdx, [rbp+4Fh+rc2]; struct tagRECT *
0x1800e519f  mov     [rbp+4Fh+lprcSrc], r9
0x1800e51a3  movdqu  xmmword ptr [rbp+4Fh+rc2.left], xmm0
0x1800e51a8  mov     r15, r9
0x1800e51ab  mov     [rbp+4Fh+var_98], rcx
0x1800e51af  mov     rbx, r8
0x1800e51b2  mov     [rcx+30h], esi
0x1800e51b5  mov     r14, rcx
0x1800e51b8  mov     [rbp+4Fh+lprcDst], rdi
0x1800e51bc  call    ?NormalizeRect@CSelectionRect@@QEAAXPEAUtagRECT@@@Z; CSelectionRect::NormalizeRect(tagRECT *)
0x1800e51c1  movups  xmm0, xmmword ptr [r9]
0x1800e51c5  lea     rdx, [rbp+4Fh+rc1]; struct tagRECT *
0x1800e51c9  movdqu  xmmword ptr [rbp+4Fh+rc1.left], xmm0
0x1800e51ce  call    ?NormalizeRect@CSelectionRect@@QEAAXPEAUtagRECT@@@Z; CSelectionRect::NormalizeRect(tagRECT *)
0x1800e51d3  lea     rcx, [rbp+4Fh+rc1]; lprc1
0x1800e51d7  lea     rdx, [rbp+4Fh+rc2]; lprc2
0x1800e51db  call    cs:__imp_EqualRect
0x1800e51e1  test    eax, eax
0x1800e51e3  jz      short loc_1800E51EF
0x1800e51e5  cmp     [rbp+4Fh+arg_20], 0
0x1800e51e9  jz      loc_1800E544F
0x1800e51ef  cmp     dword ptr [r14+4Ch], 3
0x1800e51f4  jnz     loc_1800E5382
0x1800e51fa  mov     eax, [r14+40h]
0x1800e51fe  mov     ecx, 2
0x1800e5203  movaps  xmm0, xmmword ptr [rbp+4Fh+rc2.left]
0x1800e5207  add     eax, esi
0x1800e5209  cdq
0x1800e520a  movdqa  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x1800e520f  idiv    ecx
0x1800e5211  mov     edi, eax
0x1800e5213  mov     eax, [r14+44h]
0x1800e5217  add     eax, esi
0x1800e5219  cdq
0x1800e521a  idiv    ecx
0x1800e521c  lea     edx, [rdi+8]; dx
0x1800e521f  lea     rcx, [rbp+4Fh+rc]; lprc
0x1800e5223  mov     ebx, eax
0x1800e5225  lea     r15d, [rax+8]
0x1800e5229  mov     r8d, r15d; dy
0x1800e522c  call    cs:__imp_InflateRect
0x1800e5232  mov     r9d, [rbp+4Fh+rc.bottom]; y2
0x1800e5236  mov     r8d, [rbp+4Fh+rc.right]; x2
0x1800e523a  mov     edx, [rbp+4Fh+rc.top]; y1
0x1800e523d  mov     ecx, [rbp+4Fh+rc.left]; x1
0x1800e5240  call    cs:__imp_CreateRectRgn
0x1800e5246  movaps  xmm0, xmmword ptr [rbp+4Fh+rc2.left]
0x1800e524a  lea     rcx, [rbp+4Fh+rc]; lprc
0x1800e524e  mov     r13d, 8
0x1800e5254  movdqa  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x1800e5259  mov     r14d, r13d
0x1800e525c  mov     rsi, rax
0x1800e525f  sub     r14d, ebx
0x1800e5262  sub     r13d, edi
0x1800e5265  mov     r8d, r14d; dy
0x1800e5268  mov     edx, r13d; dx
0x1800e526b  call    cs:__imp_InflateRect
0x1800e5271  mov     r9d, [rbp+4Fh+rc.bottom]; y2
0x1800e5275  mov     r8d, [rbp+4Fh+rc.right]; x2
0x1800e5279  mov     edx, [rbp+4Fh+rc.top]; y1
0x1800e527c  mov     ecx, [rbp+4Fh+rc.left]; x1
0x1800e527f  call    cs:__imp_CreateRectRgn
0x1800e5285  mov     r9d, 4; iMode
0x1800e528b  mov     rdx, rsi; hrgnSrc1
0x1800e528e  mov     r8, rax; hrgnSrc2
0x1800e5291  mov     rcx, rsi; hrgnDst
0x1800e5294  mov     rbx, rax
0x1800e5297  call    cs:__imp_CombineRgn
0x1800e529d  mov     rdx, [rbp+4Fh+var_A0]; HWND
0x1800e52a1  mov     r9, rsi; HRGN
0x1800e52a4  mov     rcx, [rbp+4Fh+var_98]; this
0x1800e52a8  xor     r8d, r8d; struct tagRECT *
0x1800e52ab  mov     [rsp+0D0h+var_B0], 0; int
0x1800e52b3  call    ?_InvalidateWindow@CSelectionRect@@AEAAHPEAUHWND__@@PEAUtagRECT@@PEAUHRGN__@@HH@Z; CSelectionRect::_InvalidateWindow(HWND__ *,tagRECT *,HRGN__ *,int,int)
0x1800e52b8  mov     rcx, rsi; ho
0x1800e52bb  call    cs:__imp_DeleteObject
0x1800e52c1  mov     rcx, rbx; ho
0x1800e52c4  call    cs:__imp_DeleteObject
0x1800e52ca  mov     rbx, [rbp+4Fh+lprcSrc]
0x1800e52ce  lea     edx, [rdi+8]; dx
0x1800e52d1  mov     r8d, r15d; dy
0x1800e52d4  lea     rcx, [rbp+4Fh+rc]; lprc
0x1800e52d8  movups  xmm0, xmmword ptr [rbx]
0x1800e52db  movdqu  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x1800e52e0  call    cs:__imp_InflateRect
0x1800e52e6  mov     r9d, [rbp+4Fh+rc.bottom]; y2
0x1800e52ea  mov     r8d, [rbp+4Fh+rc.right]; x2
0x1800e52ee  mov     edx, [rbp+4Fh+rc.top]; y1
0x1800e52f1  mov     ecx, [rbp+4Fh+rc.left]; x1
0x1800e52f4  call    cs:__imp_CreateRectRgn
0x1800e52fa  movups  xmm0, xmmword ptr [rbx]
0x1800e52fd  mov     r8d, r14d; dy
0x1800e5300  lea     rcx, [rbp+4Fh+rc]; lprc
0x1800e5304  mov     edx, r13d; dx
0x1800e5307  mov     rdi, rax
0x1800e530a  movdqu  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x1800e530f  call    cs:__imp_InflateRect
0x1800e5315  mov     r9d, [rbp+4Fh+rc.bottom]; y2
0x1800e5319  mov     r8d, [rbp+4Fh+rc.right]; x2
0x1800e531d  mov     edx, [rbp+4Fh+rc.top]; y1
0x1800e5320  mov     ecx, [rbp+4Fh+rc.left]; x1
0x1800e5323  call    cs:__imp_CreateRectRgn
0x1800e5329  mov     rbx, rax
0x1800e532c  mov     r9d, 4; iMode
0x1800e5332  mov     r8, rax; hrgnSrc2
0x1800e5335  mov     rdx, rdi; hrgnSrc1
0x1800e5338  mov     rcx, rdi; hrgnDst
0x1800e533b  call    cs:__imp_CombineRgn
0x1800e5341  mov     rdx, [rbp+4Fh+var_A0]; HWND
0x1800e5345  mov     esi, 1
0x1800e534a  mov     rcx, [rbp+4Fh+var_98]; this
0x1800e534e  mov     r9, rdi; HRGN
0x1800e5351  xor     r8d, r8d; struct tagRECT *
0x1800e5354  mov     [rsp+0D0h+var_B0], esi; int
0x1800e5358  call    ?_InvalidateWindow@CSelectionRect@@AEAAHPEAUHWND__@@PEAUtagRECT@@PEAUHRGN__@@HH@Z; CSelectionRect::_InvalidateWindow(HWND__ *,tagRECT *,HRGN__ *,int,int)
0x1800e535d  mov     rcx, rdi; ho
0x1800e5360  call    cs:__imp_DeleteObject
0x1800e5366  mov     rcx, rbx; ho
0x1800e5369  call    cs:__imp_DeleteObject
0x1800e536f  mov     rdx, [rbp+4Fh+lprcSrc]; lprcSrc
0x1800e5373  mov     rcx, [rbp+4Fh+lprcDst]; lprcDst
0x1800e5377  call    cs:__imp_CopyRect
0x1800e537d  jmp     loc_1800E544F
0x1800e5382  xorps   xmm0, xmm0
0x1800e5385  movups  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x1800e5389  test    rbx, rbx
0x1800e538c  jnz     short loc_1800E5395
0x1800e538e  xor     eax, eax
0x1800e5390  jmp     loc_1800E5451
0x1800e5395  mov     rcx, rbx; hdc
0x1800e5398  call    cs:__imp_SaveDC
0x1800e539e  mov     edx, esi; iMode
0x1800e53a0  mov     rcx, rbx; hdc
0x1800e53a3  mov     r14d, eax
0x1800e53a6  call    cs:__imp_SetMapMode
0x1800e53ac  xor     r9d, r9d; lppt
0x1800e53af  xor     r8d, r8d; y
0x1800e53b2  xor     edx, edx; x
0x1800e53b4  mov     rcx, rbx; hdc
0x1800e53b7  call    cs:__imp_SetViewportOrgEx
0x1800e53bd  xor     r9d, r9d; lppt
0x1800e53c0  xor     r8d, r8d; y
0x1800e53c3  xor     edx, edx; x
0x1800e53c5  mov     rcx, rbx; hdc
0x1800e53c8  call    cs:__imp_SetWindowOrgEx
0x1800e53ce  mov     r13d, 8
0x1800e53d4  test    r12d, r12d
0x1800e53d7  jz      short loc_1800E5407
0x1800e53d9  movups  xmm0, xmmword ptr [rdi]
0x1800e53dc  lea     rdx, [rbp+4Fh+rc]; struct tagRECT *
0x1800e53e0  movdqu  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x1800e53e5  call    ?NormalizeRect@CSelectionRect@@QEAAXPEAUtagRECT@@@Z; CSelectionRect::NormalizeRect(tagRECT *)
0x1800e53ea  lea     rcx, [rbp+4Fh+rc]; lprc
0x1800e53ee  mov     r8d, r13d; dy
0x1800e53f1  mov     edx, r13d; dx
0x1800e53f4  call    cs:__imp_InflateRect
0x1800e53fa  lea     rdx, [rbp+4Fh+rc]; lprc
0x1800e53fe  mov     rcx, rbx; hDC
0x1800e5401  call    cs:__imp_DrawFocusRect
0x1800e5407  mov     rdx, r15; lprcSrc
0x1800e540a  mov     rcx, rdi; lprcDst
0x1800e540d  call    cs:__imp_CopyRect
0x1800e5413  movups  xmm0, xmmword ptr [rdi]
0x1800e5416  lea     rdx, [rbp+4Fh+rc]; struct tagRECT *
0x1800e541a  movdqu  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x1800e541f  call    ?NormalizeRect@CSelectionRect@@QEAAXPEAUtagRECT@@@Z; CSelectionRect::NormalizeRect(tagRECT *)
0x1800e5424  lea     rcx, [rbp+4Fh+rc]; lprc
0x1800e5428  mov     r8d, r13d; dy
0x1800e542b  mov     edx, r13d; dx
0x1800e542e  call    cs:__imp_InflateRect
0x1800e5434  lea     rdx, [rbp+4Fh+rc]; lprc
0x1800e5438  mov     rcx, rbx; hDC
0x1800e543b  call    cs:__imp_DrawFocusRect
0x1800e5441  mov     edx, r14d; nSavedDC
0x1800e5444  mov     rcx, rbx; hdc
0x1800e5447  mov     esi, eax
0x1800e5449  call    cs:__imp_RestoreDC
0x1800e544f  mov     eax, esi
0x1800e5451  mov     rcx, [rbp+4Fh+var_50]
0x1800e5455  xor     rcx, rsp; StackCookie
0x1800e5458  call    __security_check_cookie
0x1800e545d  add     rsp, 98h
0x1800e5464  pop     r15
0x1800e5466  pop     r14
0x1800e5468  pop     r13
0x1800e546a  pop     r12
0x1800e546c  pop     rdi
0x1800e546d  pop     rsi
0x1800e546e  pop     rbx
0x1800e546f  pop     rbp
0x1800e5470  retn
```
