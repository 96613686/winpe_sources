# CSelectionRect::SetPosition(HWND__ *,tagRECT &,int)

- ea: `0x1800dd478`
- end: `0x1800dd598`
- name: `?SetPosition@CSelectionRect@@QEAAXPEAUHWND__@@AEAUtagRECT@@H@Z`
- size: `288`
- prototype: `void __fastcall(CSelectionRect *__hidden this, HWND, RECT *lprcSrc, int)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180037e68`
- `0x1800d8c30`
- `0x1800e2850`
- `0x1800e6fe0`
- `0x1800f2e2c`
- `0x1800f38a0`

## callees

- `0x1800dd478`
- `0x1800e5634`
- `0x180104f30`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800dd4df`
- `USER32!IsRectEmpty` at `0x1800dd53b`
- `USER32!IsRectEmpty` at `0x1800dd4df`
- `USER32!IsRectEmpty` at `0x1800dd53b`
- `USER32!SetRectEmpty` at `0x1800dd4b4`
- `USER32!SetRectEmpty` at `0x1800dd4b4`
- `USER32!InflateRect` at `0x1800dd510`
- `USER32!InflateRect` at `0x1800dd563`
- `USER32!InflateRect` at `0x1800dd510`
- `USER32!InflateRect` at `0x1800dd563`
- `USER32!CopyRect` at `0x1800dd4aa`
- `USER32!CopyRect` at `0x1800dd4aa`
- `USER32!IsWindow` at `0x1800dd4c4`
- `USER32!IsWindow` at `0x1800dd4c4`

## pseudocode

```c
void __fastcall CSelectionRect::SetPosition(struct tagRECT *this, HWND a2, RECT *lprcSrc, int a4)
{
  RECT rc; // [rsp+30h] [rbp-48h] BYREF

  rc = *this;
  CopyRect(this, lprcSrc);
  SetRectEmpty(this + 1);
  this[3].left = 0;
  if ( IsWindow(a2) && a4 )
  {
    if ( !IsRectEmpty(&rc) )
    {
      InflateRect(&rc, (this[4].left + 1) / 2 + 8, (this[4].top + 1) / 2 + 8);
      CSelectionRect::_InvalidateWindow((CSelectionRect *)this, a2, &rc, 0, 1);
    }
    rc = *lprcSrc;
    if ( !IsRectEmpty(&rc) )
    {
      InflateRect(&rc, (this[4].left + 1) / 2 + 8, (this[4].top + 1) / 2 + 8);
      CSelectionRect::_InvalidateWindow((CSelectionRect *)this, a2, &rc, 0, 1);
    }
  }
}

```

## disassembly

```asm
0x1800dd478  push    rbx
0x1800dd47a  push    rbp
0x1800dd47b  push    rsi
0x1800dd47c  push    rdi
0x1800dd47d  push    r14
0x1800dd47f  sub     rsp, 50h
0x1800dd483  mov     rax, cs:__security_cookie
0x1800dd48a  xor     rax, rsp
0x1800dd48d  mov     [rsp+78h+var_38], rax
0x1800dd492  movups  xmm0, xmmword ptr [rcx]
0x1800dd495  mov     rbp, rdx
0x1800dd498  mov     esi, r9d
0x1800dd49b  mov     rdx, r8; lprcSrc
0x1800dd49e  mov     rdi, r8
0x1800dd4a1  movdqu  xmmword ptr [rsp+78h+rc.left], xmm0
0x1800dd4a7  mov     rbx, rcx
0x1800dd4aa  call    cs:__imp_CopyRect
0x1800dd4b0  lea     rcx, [rbx+10h]; lprc
0x1800dd4b4  call    cs:__imp_SetRectEmpty
0x1800dd4ba  mov     rcx, rbp; hWnd
0x1800dd4bd  mov     dword ptr [rbx+30h], 0
0x1800dd4c4  call    cs:__imp_IsWindow
0x1800dd4ca  test    eax, eax
0x1800dd4cc  jz      loc_1800DD580
0x1800dd4d2  test    esi, esi
0x1800dd4d4  jz      loc_1800DD580
0x1800dd4da  lea     rcx, [rsp+78h+rc]; lprc
0x1800dd4df  call    cs:__imp_IsRectEmpty
0x1800dd4e5  mov     esi, 1
0x1800dd4ea  lea     r14d, [rsi+1]
0x1800dd4ee  test    eax, eax
0x1800dd4f0  jnz     short loc_1800DD52D
0x1800dd4f2  mov     eax, [rbx+44h]
0x1800dd4f5  lea     rcx, [rsp+78h+rc]; lprc
0x1800dd4fa  add     eax, esi
0x1800dd4fc  cdq
0x1800dd4fd  idiv    r14d
0x1800dd500  lea     r8d, [rax+8]; dy
0x1800dd504  mov     eax, [rbx+40h]
0x1800dd507  add     eax, esi
0x1800dd509  cdq
0x1800dd50a  idiv    r14d
0x1800dd50d  lea     edx, [rax+8]; dx
0x1800dd510  call    cs:__imp_InflateRect
0x1800dd516  xor     r9d, r9d; HRGN
0x1800dd519  mov     [rsp+78h+var_58], esi; int
0x1800dd51d  lea     r8, [rsp+78h+rc]; struct tagRECT *
0x1800dd522  mov     rdx, rbp; HWND
0x1800dd525  mov     rcx, rbx; this
0x1800dd528  call    ?_InvalidateWindow@CSelectionRect@@AEAAHPEAUHWND__@@PEAUtagRECT@@PEAUHRGN__@@HH@Z; CSelectionRect::_InvalidateWindow(HWND__ *,tagRECT *,HRGN__ *,int,int)
0x1800dd52d  movups  xmm0, xmmword ptr [rdi]
0x1800dd530  lea     rcx, [rsp+78h+rc]; lprc
0x1800dd535  movdqu  xmmword ptr [rsp+78h+rc.left], xmm0
0x1800dd53b  call    cs:__imp_IsRectEmpty
0x1800dd541  test    eax, eax
0x1800dd543  jnz     short loc_1800DD580
0x1800dd545  mov     eax, [rbx+44h]
0x1800dd548  lea     rcx, [rsp+78h+rc]; lprc
0x1800dd54d  add     eax, esi
0x1800dd54f  cdq
0x1800dd550  idiv    r14d
0x1800dd553  lea     r8d, [rax+8]; dy
0x1800dd557  mov     eax, [rbx+40h]
0x1800dd55a  add     eax, esi
0x1800dd55c  cdq
0x1800dd55d  idiv    r14d
0x1800dd560  lea     edx, [rax+8]; dx
0x1800dd563  call    cs:__imp_InflateRect
0x1800dd569  xor     r9d, r9d; HRGN
0x1800dd56c  mov     [rsp+78h+var_58], esi; int
0x1800dd570  lea     r8, [rsp+78h+rc]; struct tagRECT *
0x1800dd575  mov     rdx, rbp; HWND
0x1800dd578  mov     rcx, rbx; this
0x1800dd57b  call    ?_InvalidateWindow@CSelectionRect@@AEAAHPEAUHWND__@@PEAUtagRECT@@PEAUHRGN__@@HH@Z; CSelectionRect::_InvalidateWindow(HWND__ *,tagRECT *,HRGN__ *,int,int)
0x1800dd580  mov     rcx, [rsp+78h+var_38]
0x1800dd585  xor     rcx, rsp; StackCookie
0x1800dd588  call    __security_check_cookie
0x1800dd58d  add     rsp, 50h
0x1800dd591  pop     r14
0x1800dd593  pop     rdi
0x1800dd594  pop     rsi
0x1800dd595  pop     rbp
0x1800dd596  pop     rbx
0x1800dd597  retn
```
