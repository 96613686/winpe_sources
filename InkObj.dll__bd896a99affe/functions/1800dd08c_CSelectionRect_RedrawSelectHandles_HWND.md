# CSelectionRect::RedrawSelectHandles(HWND__ *)

- ea: `0x1800dd08c`
- end: `0x1800dd1ce`
- name: `?RedrawSelectHandles@CSelectionRect@@QEAAXPEAUHWND__@@@Z`
- size: `322`
- prototype: `void __fastcall(CSelectionRect *__hidden this, HWND)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800e3354`
- `0x1800e4190`
- `0x1800e4730`
- `0x1800f4624`
- `0x1800f5fb0`
- `0x1800f6e40`

## callees

- `0x1800dd08c`
- `0x1800e5634`
- `0x180104f30`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800dd0d2`
- `USER32!IsRectEmpty` at `0x1800dd0d2`
- `USER32!InflateRect` at `0x1800dd100`
- `USER32!InflateRect` at `0x1800dd146`
- `USER32!InflateRect` at `0x1800dd100`
- `USER32!InflateRect` at `0x1800dd146`
- `USER32!IsWindow` at `0x1800dd0c0`
- `USER32!IsWindow` at `0x1800dd0c0`
- `GDI32!CombineRgn` at `0x1800dd17c`
- `GDI32!CombineRgn` at `0x1800dd17c`
- `GDI32!CreateRectRgn` at `0x1800dd114`
- `GDI32!CreateRectRgn` at `0x1800dd164`
- `GDI32!CreateRectRgn` at `0x1800dd114`
- `GDI32!CreateRectRgn` at `0x1800dd164`
- `GDI32!DeleteObject` at `0x1800dd185`
- `GDI32!DeleteObject` at `0x1800dd1a7`
- `GDI32!DeleteObject` at `0x1800dd185`
- `GDI32!DeleteObject` at `0x1800dd1a7`

## pseudocode

```c
void __fastcall CSelectionRect::RedrawSelectHandles(RECT *this, HWND a2)
{
  HRGN RectRgn; // rdi
  int v5; // eax
  HRGN v6; // rbx
  RECT rc; // [rsp+30h] [rbp-20h] BYREF

  rc = *this;
  if ( IsWindow(a2) && !IsRectEmpty(&rc) )
  {
    InflateRect(&rc, (this[4].left + 1) / 2 + 8, (this[4].top + 1) / 2 + 8);
    RectRgn = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom);
    v5 = (this[4].top + 1) / 2;
    rc = *this;
    InflateRect(&rc, -8 - (this[4].left + 1) / 2, -8 - v5);
    if ( rc.left < rc.right && rc.top < rc.bottom )
    {
      v6 = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom);
      CombineRgn(RectRgn, RectRgn, v6, 4);
      DeleteObject(v6);
    }
    CSelectionRect::_InvalidateWindow((CSelectionRect *)this, a2, 0, RectRgn, 1);
    DeleteObject(RectRgn);
  }
}

```

## disassembly

```asm
0x1800dd08c  mov     [rsp-18h+arg_10], rbx
0x1800dd091  mov     [rsp-18h+arg_18], rsi
0x1800dd096  push    rbp
0x1800dd097  push    rdi
0x1800dd098  push    r14
0x1800dd09a  mov     rbp, rsp
0x1800dd09d  sub     rsp, 50h
0x1800dd0a1  mov     rax, cs:__security_cookie
0x1800dd0a8  xor     rax, rsp
0x1800dd0ab  mov     [rbp+var_10], rax
0x1800dd0af  movups  xmm0, xmmword ptr [rcx]
0x1800dd0b2  mov     rsi, rcx
0x1800dd0b5  mov     r14, rdx
0x1800dd0b8  mov     rcx, rdx; hWnd
0x1800dd0bb  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x1800dd0c0  call    cs:__imp_IsWindow
0x1800dd0c6  test    eax, eax
0x1800dd0c8  jz      loc_1800DD1AD
0x1800dd0ce  lea     rcx, [rbp+rc]; lprc
0x1800dd0d2  call    cs:__imp_IsRectEmpty
0x1800dd0d8  test    eax, eax
0x1800dd0da  jnz     loc_1800DD1AD
0x1800dd0e0  mov     eax, [rsi+44h]
0x1800dd0e3  lea     rcx, [rbp+rc]; lprc
0x1800dd0e7  inc     eax
0x1800dd0e9  mov     ebx, 2
0x1800dd0ee  cdq
0x1800dd0ef  idiv    ebx
0x1800dd0f1  lea     r8d, [rax+8]; dy
0x1800dd0f5  mov     eax, [rsi+40h]
0x1800dd0f8  inc     eax
0x1800dd0fa  cdq
0x1800dd0fb  idiv    ebx
0x1800dd0fd  lea     edx, [rax+8]; dx
0x1800dd100  call    cs:__imp_InflateRect
0x1800dd106  mov     r9d, [rbp+rc.bottom]; y2
0x1800dd10a  mov     r8d, [rbp+rc.right]; x2
0x1800dd10e  mov     edx, [rbp+rc.top]; y1
0x1800dd111  mov     ecx, [rbp+rc.left]; x1
0x1800dd114  call    cs:__imp_CreateRectRgn
0x1800dd11a  movups  xmm0, xmmword ptr [rsi]
0x1800dd11d  mov     rdi, rax
0x1800dd120  lea     ecx, [rbx-0Ah]
0x1800dd123  mov     eax, [rsi+44h]
0x1800dd126  mov     r8d, ecx
0x1800dd129  inc     eax
0x1800dd12b  cdq
0x1800dd12c  idiv    ebx
0x1800dd12e  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x1800dd133  sub     r8d, eax; dy
0x1800dd136  mov     eax, [rsi+40h]
0x1800dd139  inc     eax
0x1800dd13b  cdq
0x1800dd13c  idiv    ebx
0x1800dd13e  sub     ecx, eax
0x1800dd140  mov     edx, ecx; dx
0x1800dd142  lea     rcx, [rbp+rc]; lprc
0x1800dd146  call    cs:__imp_InflateRect
0x1800dd14c  mov     ecx, [rbp+rc.left]; x1
0x1800dd14f  mov     r8d, [rbp+rc.right]; x2
0x1800dd153  cmp     ecx, r8d
0x1800dd156  jge     short loc_1800DD18B
0x1800dd158  mov     edx, [rbp+rc.top]; y1
0x1800dd15b  mov     r9d, [rbp+rc.bottom]; y2
0x1800dd15f  cmp     edx, r9d
0x1800dd162  jge     short loc_1800DD18B
0x1800dd164  call    cs:__imp_CreateRectRgn
0x1800dd16a  mov     r9d, 4; iMode
0x1800dd170  mov     rdx, rdi; hrgnSrc1
0x1800dd173  mov     r8, rax; hrgnSrc2
0x1800dd176  mov     rcx, rdi; hrgnDst
0x1800dd179  mov     rbx, rax
0x1800dd17c  call    cs:__imp_CombineRgn
0x1800dd182  mov     rcx, rbx; ho
0x1800dd185  call    cs:__imp_DeleteObject
0x1800dd18b  mov     r9, rdi; HRGN
0x1800dd18e  mov     [rsp+50h+var_30], 1; int
0x1800dd196  xor     r8d, r8d; struct tagRECT *
0x1800dd199  mov     rdx, r14; HWND
0x1800dd19c  mov     rcx, rsi; this
0x1800dd19f  call    ?_InvalidateWindow@CSelectionRect@@AEAAHPEAUHWND__@@PEAUtagRECT@@PEAUHRGN__@@HH@Z; CSelectionRect::_InvalidateWindow(HWND__ *,tagRECT *,HRGN__ *,int,int)
0x1800dd1a4  mov     rcx, rdi; ho
0x1800dd1a7  call    cs:__imp_DeleteObject
0x1800dd1ad  mov     rcx, [rbp+var_10]
0x1800dd1b1  xor     rcx, rsp; StackCookie
0x1800dd1b4  call    __security_check_cookie
0x1800dd1b9  lea     r11, [rsp+50h+var_s0]
0x1800dd1be  mov     rbx, [r11+30h]
0x1800dd1c2  mov     rsi, [r11+38h]
0x1800dd1c6  mov     rsp, r11
0x1800dd1c9  pop     r14
0x1800dd1cb  pop     rdi
0x1800dd1cc  pop     rbp
0x1800dd1cd  retn
```
