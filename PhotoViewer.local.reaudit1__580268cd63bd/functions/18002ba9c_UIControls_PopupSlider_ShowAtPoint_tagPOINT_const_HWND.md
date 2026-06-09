# UIControls::PopupSlider::ShowAtPoint(tagPOINT const &,HWND__ *)

- ea: `0x18002ba9c`
- end: `0x18002bc9c`
- name: `?ShowAtPoint@PopupSlider@UIControls@@QEAAXAEBUtagPOINT@@PEAUHWND__@@@Z`
- size: `512`
- prototype: `void __fastcall(UIControls::PopupSlider *__hidden this, const struct tagPOINT *, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180070d64`

## callees

- `0x18002ba9c`
- `0x18002bed0`
- `0x18002c820`
- `0x18003f800`

## import_xrefs

- `USER32!MoveWindow` at `0x18002bbb2`
- `USER32!MoveWindow` at `0x18002bbb2`
- `USER32!PtInRect` at `0x18002bc2a`
- `USER32!PtInRect` at `0x18002bc2a`
- `USER32!SendMessageW` at `0x18002baf0`
- `USER32!SendMessageW` at `0x18002bbfb`
- `USER32!SendMessageW` at `0x18002bc50`
- `USER32!SendMessageW` at `0x18002bc65`
- `USER32!SendMessageW` at `0x18002baf0`
- `USER32!SendMessageW` at `0x18002bbfb`
- `USER32!SendMessageW` at `0x18002bc50`
- `USER32!SendMessageW` at `0x18002bc65`
- `USER32!GetWindowRect` at `0x18002bb27`
- `USER32!GetWindowRect` at `0x18002bb27`
- `USER32!ShowWindow` at `0x18002bbc7`
- `USER32!ShowWindow` at `0x18002bbc7`
- `USER32!SetFocus` at `0x18002bbd1`
- `USER32!SetFocus` at `0x18002bbd1`
- `USER32!GetKeyState` at `0x18002bbd9`
- `USER32!GetKeyState` at `0x18002bbd9`
- `USER32!MapWindowPoints` at `0x18002bb12`
- `USER32!MapWindowPoints` at `0x18002bc1c`
- `USER32!MapWindowPoints` at `0x18002bb12`
- `USER32!MapWindowPoints` at `0x18002bc1c`
- `USER32!GetCursorPos` at `0x18002bc09`
- `USER32!GetCursorPos` at `0x18002bc09`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002bc95`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002bc95`

## pseudocode

```c
void __fastcall UIControls::PopupSlider::ShowAtPoint(HWND *this, const struct tagPOINT *a2, HWND a3)
{
  HWND v6; // rcx
  HWND v7; // rcx
  HWND v8; // rcx
  Base *v9; // rcx
  int v10; // r11d
  int v11; // r9d
  LONG y; // ecx
  UIControls::PopupSlider *v13; // rcx
  HWND v14; // rcx
  struct tagPOINT Point; // [rsp+30h] [rbp-19h] BYREF
  struct tagRECT Rect; // [rsp+38h] [rbp-11h] BYREF
  struct tagPOINT Points[2]; // [rsp+50h] [rbp+7h] BYREF
  LPARAM lParam[2]; // [rsp+60h] [rbp+17h] BYREF
  LPARAM v19[2]; // [rsp+70h] [rbp+27h] BYREF

  UIControls::PopupSlider::EnsureCreation((UIControls::PopupSlider *)this);
  this[21] = a3;
  v6 = this[10];
  *(_OWORD *)lParam = 0;
  SendMessageW(v6, 0x419u, 0, (LPARAM)lParam);
  v7 = this[10];
  *(_OWORD *)&Points[0].x = *(_OWORD *)lParam;
  MapWindowPoints(v7, 0, Points, 2u);
  v8 = this[1];
  Rect = 0;
  if ( !GetWindowRect(v8, &Rect) )
    goto LABEL_7;
  v10 = Rect.right - Rect.left;
  v11 = Rect.bottom - Rect.top;
  y = a2->y;
  Rect.left += a2->x - (Points[0].x + Points[1].x) / 2;
  v13 = (UIControls::PopupSlider *)(unsigned int)(y - (Points[0].y + Points[1].y) / 2);
  Rect.right = Rect.left + v10;
  Rect.top += (int)v13;
  Rect.bottom = Rect.top + v11;
  UIControls::PopupSlider::ConstrainRectToMonitor(v13, &Rect);
  if ( !MoveWindow(this[1], Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 1) )
  {
LABEL_7:
    Base::ThrowLastError(v9);
    JUMPOUT(0x18002BC9BLL);
  }
  ShowWindow(this[1], 5);
  SetFocus(this[10]);
  if ( GetKeyState(1) < 0 )
  {
    v14 = this[10];
    *(_OWORD *)v19 = 0;
    SendMessageW(v14, 0x419u, 0, (LPARAM)v19);
    Point = 0;
    GetCursorPos(&Point);
    MapWindowPoints(0, this[10], &Point, 1u);
    if ( PtInRect((const RECT *)v19, Point) )
      SendMessageW(this[10], 0x201u, 0, LOWORD(Point.x) | (unsigned __int64)(LOWORD(Point.y) << 16));
  }
  *((_DWORD *)this + 36) = SendMessageW(this[10], 0x400u, 0, 0);
}

```

## disassembly

```asm
0x18002ba9c  mov     [rsp-8+arg_10], rbx
0x18002baa1  mov     [rsp-8+arg_18], rsi
0x18002baa6  push    rbp
0x18002baa7  push    rdi
0x18002baa8  push    r15
0x18002baaa  lea     rbp, [rsp-47h]
0x18002baaf  sub     rsp, 90h
0x18002bab6  mov     rax, cs:__security_cookie
0x18002babd  xor     rax, rsp
0x18002bac0  mov     [rbp+57h+var_20], rax
0x18002bac4  mov     rbx, r8
0x18002bac7  mov     rsi, rdx
0x18002baca  mov     rdi, rcx
0x18002bacd  call    ?EnsureCreation@PopupSlider@UIControls@@QEAAXXZ; UIControls::PopupSlider::EnsureCreation(void)
0x18002bad2  xorps   xmm0, xmm0
0x18002bad5  mov     [rdi+0A8h], rbx
0x18002badc  mov     rcx, [rdi+50h]; hWnd
0x18002bae0  lea     r9, [rbp+57h+lParam]; lParam
0x18002bae4  xor     r8d, r8d; wParam
0x18002bae7  mov     edx, 419h; Msg
0x18002baec  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x18002baf0  call    cs:__imp_SendMessageW
0x18002baf6  movaps  xmm0, xmmword ptr [rbp+57h+lParam]
0x18002bafa  lea     r8, [rbp+57h+Points]; lpPoints
0x18002bafe  mov     rcx, [rdi+50h]; hWndFrom
0x18002bb02  mov     r15d, 2
0x18002bb08  mov     r9d, r15d; cPoints
0x18002bb0b  movdqa  xmmword ptr [rbp+57h+Points.x], xmm0
0x18002bb10  xor     edx, edx; hWndTo
0x18002bb12  call    cs:__imp_MapWindowPoints
0x18002bb18  mov     rcx, [rdi+8]; hWnd
0x18002bb1c  lea     rdx, [rbp+57h+Rect]; lpRect
0x18002bb20  xorps   xmm0, xmm0
0x18002bb23  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18002bb27  call    cs:__imp_GetWindowRect
0x18002bb2d  xor     ebx, ebx
0x18002bb2f  test    eax, eax
0x18002bb31  jz      loc_18002BC95
0x18002bb37  mov     eax, [rbp+57h+Points.x+8]
0x18002bb3a  add     eax, [rbp+57h+Points.x]
0x18002bb3d  mov     r10d, [rbp+57h+Rect.left]
0x18002bb41  cdq
0x18002bb42  mov     ecx, [rsi]
0x18002bb44  mov     r8d, [rbp+57h+Rect.top]
0x18002bb48  mov     r11d, [rbp+57h+Rect.right]
0x18002bb4c  mov     r9d, [rbp+57h+Rect.bottom]
0x18002bb50  sub     r11d, r10d
0x18002bb53  idiv    r15d
0x18002bb56  sub     r9d, r8d
0x18002bb59  sub     ecx, eax
0x18002bb5b  mov     eax, [rbp+57h+Points.y+8]
0x18002bb5e  add     eax, [rbp+57h+Points.y]
0x18002bb61  add     r10d, ecx
0x18002bb64  mov     ecx, [rsi+4]
0x18002bb67  cdq
0x18002bb68  idiv    r15d
0x18002bb6b  lea     rdx, [rbp+57h+Rect]; struct tagRECT *
0x18002bb6f  mov     [rbp+57h+Rect.left], r10d
0x18002bb73  sub     ecx, eax; this
0x18002bb75  lea     eax, [r10+r11]
0x18002bb79  add     r8d, ecx
0x18002bb7c  mov     [rbp+57h+Rect.right], eax
0x18002bb7f  mov     [rbp+57h+Rect.top], r8d
0x18002bb83  lea     eax, [r8+r9]
0x18002bb87  mov     [rbp+57h+Rect.bottom], eax
0x18002bb8a  call    ?ConstrainRectToMonitor@PopupSlider@UIControls@@AEAAXPEAUtagRECT@@@Z; UIControls::PopupSlider::ConstrainRectToMonitor(tagRECT *)
0x18002bb8f  mov     eax, [rbp+57h+Rect.bottom]
0x18002bb92  lea     esi, [rbx+1]
0x18002bb95  mov     r8d, [rbp+57h+Rect.top]; Y
0x18002bb99  sub     eax, r8d
0x18002bb9c  mov     r9d, [rbp+57h+Rect.right]
0x18002bba0  mov     edx, [rbp+57h+Rect.left]; X
0x18002bba3  sub     r9d, edx; nWidth
0x18002bba6  mov     rcx, [rdi+8]; hWnd
0x18002bbaa  mov     [rsp+0A0h+bRepaint], esi; bRepaint
0x18002bbae  mov     [rsp+0A0h+nHeight], eax; nHeight
0x18002bbb2  call    cs:__imp_MoveWindow
0x18002bbb8  test    eax, eax
0x18002bbba  jz      loc_18002BC95
0x18002bbc0  mov     rcx, [rdi+8]; hWnd
0x18002bbc4  lea     edx, [rbx+5]; nCmdShow
0x18002bbc7  call    cs:__imp_ShowWindow
0x18002bbcd  mov     rcx, [rdi+50h]; hWnd
0x18002bbd1  call    cs:__imp_SetFocus
0x18002bbd7  mov     ecx, esi; nVirtKey
0x18002bbd9  call    cs:__imp_GetKeyState
0x18002bbdf  test    ax, ax
0x18002bbe2  jns     short loc_18002BC56
0x18002bbe4  mov     rcx, [rdi+50h]; hWnd
0x18002bbe8  lea     r9, [rbp+57h+var_30]; lParam
0x18002bbec  xorps   xmm0, xmm0
0x18002bbef  xor     r8d, r8d; wParam
0x18002bbf2  mov     edx, 419h; Msg
0x18002bbf7  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x18002bbfb  call    cs:__imp_SendMessageW
0x18002bc01  lea     rcx, [rbp+57h+Point]; lpPoint
0x18002bc05  mov     qword ptr [rbp+57h+Point.x], rbx
0x18002bc09  call    cs:__imp_GetCursorPos
0x18002bc0f  mov     rdx, [rdi+50h]; hWndTo
0x18002bc13  lea     r8, [rbp+57h+Point]; lpPoints
0x18002bc17  mov     r9d, esi; cPoints
0x18002bc1a  xor     ecx, ecx; hWndFrom
0x18002bc1c  call    cs:__imp_MapWindowPoints
0x18002bc22  mov     rdx, qword ptr [rbp+57h+Point.x]; pt
0x18002bc26  lea     rcx, [rbp+57h+var_30]; lprc
0x18002bc2a  call    cs:__imp_PtInRect
0x18002bc30  test    eax, eax
0x18002bc32  jz      short loc_18002BC56
0x18002bc34  movzx   r9d, word ptr [rbp+57h+Point.y]
0x18002bc39  xor     r8d, r8d; wParam
0x18002bc3c  movzx   eax, word ptr [rbp+57h+Point.x]
0x18002bc40  mov     edx, 201h; Msg
0x18002bc45  mov     rcx, [rdi+50h]; hWnd
0x18002bc49  shl     r9d, 10h
0x18002bc4d  or      r9, rax; lParam
0x18002bc50  call    cs:__imp_SendMessageW
0x18002bc56  mov     rcx, [rdi+50h]; hWnd
0x18002bc5a  xor     r9d, r9d; lParam
0x18002bc5d  xor     r8d, r8d; wParam
0x18002bc60  mov     edx, 400h; Msg
0x18002bc65  call    cs:__imp_SendMessageW
0x18002bc6b  mov     [rdi+90h], eax
0x18002bc71  mov     rcx, [rbp+57h+var_20]
0x18002bc75  xor     rcx, rsp; StackCookie
0x18002bc78  call    __security_check_cookie
0x18002bc7d  lea     r11, [rsp+0A0h+var_10]
0x18002bc85  mov     rbx, [r11+30h]
0x18002bc89  mov     rsi, [r11+38h]
0x18002bc8d  mov     rsp, r11
0x18002bc90  pop     r15
0x18002bc92  pop     rdi
0x18002bc93  pop     rbp
0x18002bc94  retn
0x18002bc95  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
```
