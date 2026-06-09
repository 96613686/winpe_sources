# ATL::CAxHostWindow::OnPosRectChange(tagRECT const *)

- ea: `0x18000f3c0`
- end: `0x18000f490`
- name: `?OnPosRectChange@CAxHostWindow@ATL@@UEAAJPEBUtagRECT@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001800`
- `0x18000f3c0`

## import_xrefs

- `USER32!MoveWindow` at `0x18000f470`
- `USER32!MoveWindow` at `0x18000f470`
- `USER32!ScreenToClient` at `0x18000f430`
- `USER32!ScreenToClient` at `0x18000f442`
- `USER32!ScreenToClient` at `0x18000f430`
- `USER32!ScreenToClient` at `0x18000f442`
- `USER32!GetParent` at `0x18000f41a`
- `USER32!GetParent` at `0x18000f41a`
- `USER32!ClientToScreen` at `0x18000f3fd`
- `USER32!ClientToScreen` at `0x18000f410`
- `USER32!ClientToScreen` at `0x18000f3fd`
- `USER32!ClientToScreen` at `0x18000f410`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::OnPosRectChange(ATL::CAxHostWindow *this, const struct tagRECT *a2)
{
  HWND v4; // rcx
  HWND Parent; // rax
  HWND v6; // rbx
  tagPOINT Point[2]; // [rsp+30h] [rbp-28h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v4 = (HWND)*((_QWORD *)this - 10);
  *(struct tagRECT *)&Point[0].x = *a2;
  if ( ClientToScreen(v4, Point) )
    ClientToScreen(*((HWND *)this - 10), &Point[1]);
  Parent = GetParent(*((HWND *)this - 10));
  v6 = Parent;
  if ( Parent )
  {
    if ( ScreenToClient(Parent, Point) )
      ScreenToClient(v6, &Point[1]);
  }
  MoveWindow(*((HWND *)this - 10), Point[0].x, Point[0].y, Point[1].x - Point[0].x, Point[1].y - Point[0].y, 1);
  return 0;
}

```

## disassembly

```asm
0x18000f3c0  mov     [rsp+arg_10], rbx
0x18000f3c5  push    rdi
0x18000f3c6  sub     rsp, 50h
0x18000f3ca  mov     rax, cs:__security_cookie
0x18000f3d1  xor     rax, rsp
0x18000f3d4  mov     [rsp+58h+var_18], rax
0x18000f3d9  mov     rdi, rcx
0x18000f3dc  test    rdx, rdx
0x18000f3df  jnz     short loc_18000F3EB
0x18000f3e1  mov     eax, 80004003h
0x18000f3e6  jmp     loc_18000F478
0x18000f3eb  movups  xmm0, xmmword ptr [rdx]
0x18000f3ee  mov     rcx, [rcx-50h]; hWnd
0x18000f3f2  lea     rdx, [rsp+58h+Point]; lpPoint
0x18000f3f7  movdqu  xmmword ptr [rsp+58h+Point.x], xmm0
0x18000f3fd  call    cs:__imp_ClientToScreen
0x18000f403  test    eax, eax
0x18000f405  jz      short loc_18000F416
0x18000f407  mov     rcx, [rdi-50h]; hWnd
0x18000f40b  lea     rdx, [rsp+58h+Point.x+8]; lpPoint
0x18000f410  call    cs:__imp_ClientToScreen
0x18000f416  mov     rcx, [rdi-50h]; hWnd
0x18000f41a  call    cs:__imp_GetParent
0x18000f420  mov     rbx, rax
0x18000f423  test    rax, rax
0x18000f426  jz      short loc_18000F448
0x18000f428  lea     rdx, [rsp+58h+Point]; lpPoint
0x18000f42d  mov     rcx, rax; hWnd
0x18000f430  call    cs:__imp_ScreenToClient
0x18000f436  test    eax, eax
0x18000f438  jz      short loc_18000F448
0x18000f43a  lea     rdx, [rsp+58h+Point.x+8]; lpPoint
0x18000f43f  mov     rcx, rbx; hWnd
0x18000f442  call    cs:__imp_ScreenToClient
0x18000f448  mov     eax, [rsp+58h+Point.y+8]
0x18000f44c  mov     r8d, [rsp+58h+Point.y]; Y
0x18000f451  sub     eax, r8d
0x18000f454  mov     r9d, [rsp+58h+Point.x+8]
0x18000f459  mov     edx, [rsp+58h+Point.x]; X
0x18000f45d  sub     r9d, edx; nWidth
0x18000f460  mov     rcx, [rdi-50h]; hWnd
0x18000f464  mov     [rsp+58h+bRepaint], 1; bRepaint
0x18000f46c  mov     [rsp+58h+nHeight], eax; nHeight
0x18000f470  call    cs:__imp_MoveWindow
0x18000f476  xor     eax, eax
0x18000f478  mov     rcx, [rsp+58h+var_18]
0x18000f47d  xor     rcx, rsp; StackCookie
0x18000f480  call    __security_check_cookie
0x18000f485  mov     rbx, [rsp+58h+arg_10]
0x18000f48a  add     rsp, 50h
0x18000f48e  pop     rdi
0x18000f48f  retn
```
