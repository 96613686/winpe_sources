# Art::PaintScreenCapture(void)

- ea: `0x1805e1fd8`
- end: `0x1805e2241`
- name: `?PaintScreenCapture@Art@@YAXXZ`
- size: `617`
- prototype: `void __fastcall(Art *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1804e6480`

## callees

- `0x180064914`
- `0x180070fe0`
- `0x18014bc30`
- `0x1805e1fd8`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x1805e2122`
- `GDI32!CreateSolidBrush` at `0x1805e2122`
- `GDI32!BitBlt` at `0x1805e20a1`
- `GDI32!BitBlt` at `0x1805e2104`
- `GDI32!BitBlt` at `0x1805e2204`
- `GDI32!BitBlt` at `0x1805e20a1`
- `GDI32!BitBlt` at `0x1805e2104`
- `GDI32!BitBlt` at `0x1805e2204`
- `GDI32!SelectObject` at `0x1805e2064`
- `GDI32!SelectObject` at `0x1805e2064`
- `GDI32!DeleteObject` at `0x1805e21a9`
- `GDI32!DeleteObject` at `0x1805e21a9`
- `GDI32!CreateCompatibleDC` at `0x1805e2027`
- `GDI32!CreateCompatibleDC` at `0x1805e2027`
- `GDI32!CreateCompatibleBitmap` at `0x1805e204d`
- `GDI32!CreateCompatibleBitmap` at `0x1805e204d`
- `USER32!EndPaint` at `0x1805e2216`
- `USER32!EndPaint` at `0x1805e2216`
- `USER32!InflateRect` at `0x1805e2164`
- `USER32!InflateRect` at `0x1805e218b`
- `USER32!InflateRect` at `0x1805e2164`
- `USER32!InflateRect` at `0x1805e218b`
- `USER32!FrameRect` at `0x1805e213c`
- `USER32!FrameRect` at `0x1805e2179`
- `USER32!FrameRect` at `0x1805e21a0`
- `USER32!FrameRect` at `0x1805e213c`
- `USER32!FrameRect` at `0x1805e2179`
- `USER32!FrameRect` at `0x1805e21a0`
- `USER32!BeginPaint` at `0x1805e21cb`
- `USER32!BeginPaint` at `0x1805e21cb`
- `USER32!IsRectEmpty` at `0x1805e20ae`
- `USER32!IsRectEmpty` at `0x1805e20ae`
- `USER32!GetSysColorBrush` at `0x1805e2118`
- `USER32!GetSysColorBrush` at `0x1805e2118`

## pseudocode

```c
void __fastcall Art::PaintScreenCapture(Art *this)
{
  int v1; // ebx
  int cy; // edi
  HDC CompatibleDC; // rcx
  Art *v4; // rcx
  HBRUSH SysColorBrush; // rax
  HBRUSH v6; // rsi
  Art *v7; // rcx
  HDC v8; // rax
  struct tagRECT rc; // [rsp+50h] [rbp-78h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+60h] [rbp-68h] BYREF

  v1 = Art::g_rcScreenCapture.right - Art::g_rcScreenCapture.left;
  cy = Art::g_rcScreenCapture.bottom - Art::g_rcScreenCapture.top;
  CompatibleDC = Art::g_hdcOffScreen;
  if ( !Art::g_hdcOffScreen )
  {
    CompatibleDC = CreateCompatibleDC(Art::g_hdcScreenCapture);
    Art::g_hdcOffScreen = CompatibleDC;
  }
  if ( !Art::g_bmpOffScreen )
  {
    Art::g_bmpOffScreen = CreateCompatibleBitmap(Art::g_hdcScreenCapture, v1, cy);
    SelectObject(Art::g_hdcOffScreen, Art::g_bmpOffScreen);
    CompatibleDC = Art::g_hdcOffScreen;
  }
  BitBlt(CompatibleDC, 0, 0, v1, cy, Art::g_hdcScreenCaptureBlended, 0, 0, 0xCC0020u);
  if ( !IsRectEmpty(&Art::g_rcCaptureRect) )
  {
    BitBlt(
      Art::g_hdcOffScreen,
      Art::g_rcCaptureRect.left,
      Art::g_rcCaptureRect.top,
      Art::g_rcCaptureRect.right - Art::g_rcCaptureRect.left,
      Art::g_rcCaptureRect.bottom - Art::g_rcCaptureRect.top,
      Art::g_hdcScreenCapture,
      Art::g_rcCaptureRect.left,
      Art::g_rcCaptureRect.top,
      0xCC0020u);
    if ( Art::FInHighContrastMode(v4) )
      SysColorBrush = GetSysColorBrush(8);
    else
      SysColorBrush = CreateSolidBrush(0);
    v6 = SysColorBrush;
    FrameRect(Art::g_hdcOffScreen, &Art::g_rcCaptureRect, SysColorBrush);
    if ( Art::FInHighContrastMode(v7) )
    {
      rc = Art::g_rcCaptureRect;
      InflateRect(&rc, -1, -1);
      FrameRect(Art::g_hdcOffScreen, &rc, v6);
      InflateRect(&rc, -1, -1);
      FrameRect(Art::g_hdcOffScreen, &rc, v6);
    }
    DeleteObject(v6);
  }
  memset_0(&Paint, 0, sizeof(Paint));
  v8 = BeginPaint(Art::g_hwndScreenCapture, &Paint);
  BitBlt(v8, 0, 0, v1, cy, Art::g_hdcOffScreen, 0, 0, 0xCC0020u);
  EndPaint(Art::g_hwndScreenCapture, &Paint);
}

```

## disassembly

```asm
0x1805e1fd8  mov     [rsp+arg_0], rbx
0x1805e1fdd  mov     [rsp+arg_8], rsi
0x1805e1fe2  push    rdi
0x1805e1fe3  sub     rsp, 0C0h
0x1805e1fea  mov     rax, cs:__security_cookie
0x1805e1ff1  xor     rax, rsp
0x1805e1ff4  mov     [rsp+0C8h+var_18], rax
0x1805e1ffc  mov     ebx, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.right; tagRECT Art::g_rcScreenCapture ...
0x1805e2002  mov     edi, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.bottom; tagRECT Art::g_rcScreenCapture ...
0x1805e2008  sub     ebx, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.left; tagRECT Art::g_rcScreenCapture ...
0x1805e200e  sub     edi, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.top; tagRECT Art::g_rcScreenCapture ...
0x1805e2014  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcOffScreen
0x1805e201b  test    rcx, rcx
0x1805e201e  jnz     short loc_1805E2037
0x1805e2020  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; hdc
0x1805e2027  call    cs:__imp_CreateCompatibleDC
0x1805e202d  mov     rcx, rax
0x1805e2030  mov     cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA, rax; HDC__ * Art::g_hdcOffScreen
0x1805e2037  cmp     cs:?g_bmpOffScreen@Art@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * Art::g_bmpOffScreen
0x1805e203f  jnz     short loc_1805E2071
0x1805e2041  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; hdc
0x1805e2048  mov     r8d, edi; cy
0x1805e204b  mov     edx, ebx; cx
0x1805e204d  call    cs:__imp_CreateCompatibleBitmap
0x1805e2053  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; hdc
0x1805e205a  mov     rdx, rax; h
0x1805e205d  mov     cs:?g_bmpOffScreen@Art@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * Art::g_bmpOffScreen
0x1805e2064  call    cs:__imp_SelectObject
0x1805e206a  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; hdc
0x1805e2071  mov     rax, cs:?g_hdcScreenCaptureBlended@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcScreenCaptureBlended
0x1805e2078  mov     r9d, ebx; cx
0x1805e207b  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1805e2083  xor     r8d, r8d; y
0x1805e2086  mov     [rsp+0C8h+y1], 0; y1
0x1805e208e  xor     edx, edx; x
0x1805e2090  mov     [rsp+0C8h+x1], 0; x1
0x1805e2098  mov     [rsp+0C8h+hdcSrc], rax; hdcSrc
0x1805e209d  mov     [rsp+0C8h+cy], edi; cy
0x1805e20a1  call    cs:__imp_BitBlt
0x1805e20a7  lea     rcx, ?g_rcCaptureRect@Art@@3UtagRECT@@A; lprc
0x1805e20ae  call    cs:__imp_IsRectEmpty
0x1805e20b4  test    eax, eax
0x1805e20b6  jnz     loc_1805E21AF
0x1805e20bc  mov     ecx, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.bottom; tagRECT Art::g_rcCaptureRect ...
0x1805e20c2  mov     r8d, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.top; y
0x1805e20c9  sub     ecx, r8d
0x1805e20cc  mov     edx, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.left; x
0x1805e20d2  mov     rax, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcScreenCapture
0x1805e20d9  mov     r9d, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.right; tagRECT Art::g_rcCaptureRect ...
0x1805e20e0  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1805e20e8  sub     r9d, edx; cx
0x1805e20eb  mov     [rsp+0C8h+y1], r8d; y1
0x1805e20f0  mov     [rsp+0C8h+x1], edx; x1
0x1805e20f4  mov     [rsp+0C8h+hdcSrc], rax; hdcSrc
0x1805e20f9  mov     [rsp+0C8h+cy], ecx; cy
0x1805e20fd  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; hdc
0x1805e2104  call    cs:__imp_BitBlt
0x1805e210a  call    ?FInHighContrastMode@Art@@YA_NXZ; Art::FInHighContrastMode(void)
0x1805e210f  test    al, al
0x1805e2111  jz      short loc_1805E2120
0x1805e2113  mov     ecx, 8; nIndex
0x1805e2118  call    cs:__imp_GetSysColorBrush
0x1805e211e  jmp     short loc_1805E2128
0x1805e2120  xor     ecx, ecx; color
0x1805e2122  call    cs:__imp_CreateSolidBrush
0x1805e2128  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; hDC
0x1805e212f  lea     rdx, ?g_rcCaptureRect@Art@@3UtagRECT@@A; lprc
0x1805e2136  mov     r8, rax; hbr
0x1805e2139  mov     rsi, rax
0x1805e213c  call    cs:__imp_FrameRect
0x1805e2142  call    ?FInHighContrastMode@Art@@YA_NXZ; Art::FInHighContrastMode(void)
0x1805e2147  test    al, al
0x1805e2149  jz      short loc_1805E21A6
0x1805e214b  movups  xmm0, xmmword ptr cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.left; tagRECT Art::g_rcCaptureRect ...
0x1805e2152  or      r8d, 0FFFFFFFFh; dy
0x1805e2156  lea     rcx, [rsp+0C8h+rc]; lprc
0x1805e215b  or      edx, r8d; dx
0x1805e215e  movdqu  xmmword ptr [rsp+0C8h+rc.left], xmm0
0x1805e2164  call    cs:__imp_InflateRect
0x1805e216a  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; hDC
0x1805e2171  lea     rdx, [rsp+0C8h+rc]; lprc
0x1805e2176  mov     r8, rsi; hbr
0x1805e2179  call    cs:__imp_FrameRect
0x1805e217f  or      r8d, 0FFFFFFFFh; dy
0x1805e2183  lea     rcx, [rsp+0C8h+rc]; lprc
0x1805e2188  or      edx, r8d; dx
0x1805e218b  call    cs:__imp_InflateRect
0x1805e2191  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; hDC
0x1805e2198  lea     rdx, [rsp+0C8h+rc]; lprc
0x1805e219d  mov     r8, rsi; hbr
0x1805e21a0  call    cs:__imp_FrameRect
0x1805e21a6  mov     rcx, rsi; ho
0x1805e21a9  call    cs:__imp_DeleteObject
0x1805e21af  xor     edx, edx; Val
0x1805e21b1  lea     rcx, [rsp+0C8h+Paint]; void *
0x1805e21b6  lea     r8d, [rdx+48h]; Size
0x1805e21ba  call    memset_0
0x1805e21bf  mov     rcx, cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA; hWnd
0x1805e21c6  lea     rdx, [rsp+0C8h+Paint]; lpPaint
0x1805e21cb  call    cs:__imp_BeginPaint
0x1805e21d1  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcOffScreen
0x1805e21d8  mov     r9d, ebx; cx
0x1805e21db  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1805e21e3  xor     r8d, r8d; y
0x1805e21e6  mov     [rsp+0C8h+y1], 0; y1
0x1805e21ee  xor     edx, edx; x
0x1805e21f0  mov     [rsp+0C8h+x1], 0; x1
0x1805e21f8  mov     [rsp+0C8h+hdcSrc], rcx; hdcSrc
0x1805e21fd  mov     rcx, rax; hdc
0x1805e2200  mov     [rsp+0C8h+cy], edi; cy
0x1805e2204  call    cs:__imp_BitBlt
0x1805e220a  mov     rcx, cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA; hWnd
0x1805e2211  lea     rdx, [rsp+0C8h+Paint]; lpPaint
0x1805e2216  call    cs:__imp_EndPaint
0x1805e221c  mov     rcx, [rsp+0C8h+var_18]
0x1805e2224  xor     rcx, rsp; StackCookie
0x1805e2227  call    __security_check_cookie
0x1805e222c  lea     r11, [rsp+0C8h+var_8]
0x1805e2234  mov     rbx, [r11+10h]
0x1805e2238  mov     rsi, [r11+18h]
0x1805e223c  mov     rsp, r11
0x1805e223f  pop     rdi
0x1805e2240  retn
```
