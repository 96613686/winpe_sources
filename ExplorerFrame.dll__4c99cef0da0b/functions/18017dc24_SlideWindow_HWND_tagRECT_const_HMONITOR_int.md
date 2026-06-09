# SlideWindow(HWND__ *,tagRECT const *,HMONITOR__ *,int)

- ea: `0x18017dc24`
- end: `0x18017dd52`
- name: `?SlideWindow@@YAXPEAUHWND__@@PEBUtagRECT@@PEAUHMONITOR__@@H@Z`
- size: `302`
- prototype: `void __fastcall(HWND hWnd, RECT *lprcSrc2, HMONITOR, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18017f150`

## callees

- `0x18012c250`
- `0x18013f7d0`
- `0x18017dc24`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x18017dc6a`
- `USER32!GetSystemMetrics` at `0x18017dc6a`
- `USER32!GetParent` at `0x18017dc88`
- `USER32!GetParent` at `0x18017dc88`
- `USER32!OffsetRect` at `0x18017dcd4`
- `USER32!OffsetRect` at `0x18017dcd4`
- `USER32!MapWindowPoints` at `0x18017dc9c`
- `USER32!MapWindowPoints` at `0x18017dc9c`
- `USER32!MoveWindow` at `0x18017dd1d`
- `USER32!MoveWindow` at `0x18017dd1d`
- `USER32!SetRectEmpty` at `0x18017dc61`
- `USER32!SetRectEmpty` at `0x18017dc61`
- `USER32!IntersectRect` at `0x18017dcaf`
- `USER32!IntersectRect` at `0x18017dcaf`
- `USER32!IsRectEmpty` at `0x18017dcba`
- `USER32!IsRectEmpty` at `0x18017dcba`
- `USER32!SetWindowRgn` at `0x18017dcf1`
- `USER32!SetWindowRgn` at `0x18017dd34`
- `USER32!SetWindowRgn` at `0x18017dcf1`
- `USER32!SetWindowRgn` at `0x18017dd34`
- `GDI32!CreateRectRgnIndirect` at `0x18017dcdf`
- `GDI32!CreateRectRgnIndirect` at `0x18017dcdf`

## pseudocode

```c
void __fastcall SlideWindow(HWND hWnd, RECT *lprcSrc2, HMONITOR a3, int a4)
{
  int v8; // ebp
  HWND Parent; // rax
  HRGN v10; // rax
  struct tagRECT rc; // [rsp+30h] [rbp-58h] BYREF
  struct tagRECT rcDst; // [rsp+40h] [rbp-48h] BYREF

  rc = 0;
  rcDst = 0;
  v8 = 0;
  SetRectEmpty(&rc);
  if ( GetSystemMetrics(80) > 1 )
  {
    GetMonitorRects(a3, &rc, 0);
    Parent = GetParent(hWnd);
    MapWindowPoints(0, Parent, (LPPOINT)&rc, 2u);
  }
  IntersectRect(&rcDst, &rc, lprcSrc2);
  if ( !IsRectEmpty(&rcDst) )
  {
    OffsetRect(&rcDst, -lprcSrc2->left, -lprcSrc2->top);
    v10 = CreateRectRgnIndirect(&rcDst);
    v8 = SetWindowRgn(hWnd, v10, 1);
  }
  MoveWindow(hWnd, lprcSrc2->left, lprcSrc2->top, lprcSrc2->right - lprcSrc2->left, lprcSrc2->bottom - lprcSrc2->top, 1);
  if ( v8 )
  {
    if ( a4 )
      SetWindowRgn(hWnd, 0, 1);
  }
}

```

## disassembly

```asm
0x18017dc24  push    rbx
0x18017dc26  push    rbp
0x18017dc27  push    rsi
0x18017dc28  push    rdi
0x18017dc29  push    r14
0x18017dc2b  sub     rsp, 60h
0x18017dc2f  mov     rax, cs:__security_cookie
0x18017dc36  xor     rax, rsp
0x18017dc39  mov     [rsp+88h+var_38], rax
0x18017dc3e  mov     rdi, rcx
0x18017dc41  xorps   xmm0, xmm0
0x18017dc44  xorps   xmm1, xmm1
0x18017dc47  lea     rcx, [rsp+88h+rc]; lprc
0x18017dc4c  movups  xmmword ptr [rsp+88h+rc.left], xmm0
0x18017dc51  mov     esi, r9d
0x18017dc54  mov     r14, r8
0x18017dc57  movups  xmmword ptr [rsp+88h+rcDst.left], xmm1
0x18017dc5c  mov     rbx, rdx
0x18017dc5f  xor     ebp, ebp
0x18017dc61  call    cs:__imp_SetRectEmpty
0x18017dc67  lea     ecx, [rbp+50h]; nIndex
0x18017dc6a  call    cs:__imp_GetSystemMetrics
0x18017dc70  cmp     eax, 1
0x18017dc73  jle     short loc_18017DCA2
0x18017dc75  xor     r8d, r8d; int
0x18017dc78  lea     rdx, [rsp+88h+rc]; struct tagRECT *
0x18017dc7d  mov     rcx, r14; HMONITOR
0x18017dc80  call    ?GetMonitorRects@@YAHPEAUHMONITOR__@@PEAUtagRECT@@H@Z; GetMonitorRects(HMONITOR__ *,tagRECT *,int)
0x18017dc85  mov     rcx, rdi; hWnd
0x18017dc88  call    cs:__imp_GetParent
0x18017dc8e  lea     r9d, [rbp+2]; cPoints
0x18017dc92  xor     ecx, ecx; hWndFrom
0x18017dc94  mov     rdx, rax; hWndTo
0x18017dc97  lea     r8, [rsp+88h+rc]; lpPoints
0x18017dc9c  call    cs:__imp_MapWindowPoints
0x18017dca2  mov     r8, rbx; lprcSrc2
0x18017dca5  lea     rdx, [rsp+88h+rc]; lprcSrc1
0x18017dcaa  lea     rcx, [rsp+88h+rcDst]; lprcDst
0x18017dcaf  call    cs:__imp_IntersectRect
0x18017dcb5  lea     rcx, [rsp+88h+rcDst]; lprc
0x18017dcba  call    cs:__imp_IsRectEmpty
0x18017dcc0  test    eax, eax
0x18017dcc2  jnz     short loc_18017DCF9
0x18017dcc4  mov     r8d, [rbx+4]
0x18017dcc8  lea     rcx, [rsp+88h+rcDst]; lprc
0x18017dccd  mov     edx, [rbx]
0x18017dccf  neg     r8d; dy
0x18017dcd2  neg     edx; dx
0x18017dcd4  call    cs:__imp_OffsetRect
0x18017dcda  lea     rcx, [rsp+88h+rcDst]; lprect
0x18017dcdf  call    cs:__imp_CreateRectRgnIndirect
0x18017dce5  mov     r8d, 1; bRedraw
0x18017dceb  mov     rcx, rdi; hWnd
0x18017dcee  mov     rdx, rax; hRgn
0x18017dcf1  call    cs:__imp_SetWindowRgn
0x18017dcf7  mov     ebp, eax
0x18017dcf9  mov     r10d, [rbx+0Ch]
0x18017dcfd  mov     rcx, rdi; hWnd
0x18017dd00  mov     r8d, [rbx+4]; Y
0x18017dd04  sub     r10d, r8d
0x18017dd07  mov     r9d, [rbx+8]
0x18017dd0b  sub     r9d, [rbx]; nWidth
0x18017dd0e  mov     edx, [rbx]; X
0x18017dd10  mov     [rsp+88h+bRepaint], 1; bRepaint
0x18017dd18  mov     [rsp+88h+nHeight], r10d; nHeight
0x18017dd1d  call    cs:__imp_MoveWindow
0x18017dd23  test    ebp, ebp
0x18017dd25  jz      short loc_18017DD3A
0x18017dd27  test    esi, esi
0x18017dd29  jz      short loc_18017DD3A
0x18017dd2b  xor     edx, edx; hRgn
0x18017dd2d  mov     rcx, rdi; hWnd
0x18017dd30  lea     r8d, [rdx+1]; bRedraw
0x18017dd34  call    cs:__imp_SetWindowRgn
0x18017dd3a  mov     rcx, [rsp+88h+var_38]
0x18017dd3f  xor     rcx, rsp; StackCookie
0x18017dd42  call    __security_check_cookie
0x18017dd47  add     rsp, 60h
0x18017dd4b  pop     r14
0x18017dd4d  pop     rdi
0x18017dd4e  pop     rsi
0x18017dd4f  pop     rbp
0x18017dd50  pop     rbx
0x18017dd51  retn
```
