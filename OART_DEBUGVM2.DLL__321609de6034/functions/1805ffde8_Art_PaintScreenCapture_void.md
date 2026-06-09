# Art::PaintScreenCapture(void)

- ea: `0x1805ffde8`
- end: `0x180600051`
- name: `?PaintScreenCapture@Art@@YAXXZ`
- size: `617`
- prototype: `void __fastcall(Art *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180521700`

## callees

- `0x1800ef520`
- `0x180276a71`
- `0x180279030`
- `0x1805ffde8`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x1805fff32`
- `GDI32!CreateSolidBrush` at `0x1805fff32`
- `GDI32!BitBlt` at `0x1805ffeb1`
- `GDI32!BitBlt` at `0x1805fff14`
- `GDI32!BitBlt` at `0x180600014`
- `GDI32!BitBlt` at `0x1805ffeb1`
- `GDI32!BitBlt` at `0x1805fff14`
- `GDI32!BitBlt` at `0x180600014`
- `GDI32!SelectObject` at `0x1805ffe74`
- `GDI32!SelectObject` at `0x1805ffe74`
- `GDI32!DeleteObject` at `0x1805fffb9`
- `GDI32!DeleteObject` at `0x1805fffb9`
- `GDI32!CreateCompatibleDC` at `0x1805ffe37`
- `GDI32!CreateCompatibleDC` at `0x1805ffe37`
- `GDI32!CreateCompatibleBitmap` at `0x1805ffe5d`
- `GDI32!CreateCompatibleBitmap` at `0x1805ffe5d`
- `USER32!EndPaint` at `0x180600026`
- `USER32!EndPaint` at `0x180600026`
- `USER32!InflateRect` at `0x1805fff74`
- `USER32!InflateRect` at `0x1805fff9b`
- `USER32!InflateRect` at `0x1805fff74`
- `USER32!InflateRect` at `0x1805fff9b`
- `USER32!FrameRect` at `0x1805fff4c`
- `USER32!FrameRect` at `0x1805fff89`
- `USER32!FrameRect` at `0x1805fffb0`
- `USER32!FrameRect` at `0x1805fff4c`
- `USER32!FrameRect` at `0x1805fff89`
- `USER32!FrameRect` at `0x1805fffb0`
- `USER32!BeginPaint` at `0x1805fffdb`
- `USER32!BeginPaint` at `0x1805fffdb`
- `USER32!IsRectEmpty` at `0x1805ffebe`
- `USER32!IsRectEmpty` at `0x1805ffebe`
- `USER32!GetSysColorBrush` at `0x1805fff28`
- `USER32!GetSysColorBrush` at `0x1805fff28`

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
0x1805ffde8  mov     [rsp+arg_0], rbx
0x1805ffded  mov     [rsp+arg_8], rsi
0x1805ffdf2  push    rdi
0x1805ffdf3  sub     rsp, 0C0h
0x1805ffdfa  mov     rax, cs:__security_cookie
0x1805ffe01  xor     rax, rsp
0x1805ffe04  mov     [rsp+0C8h+var_18], rax
0x1805ffe0c  mov     ebx, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.right; tagRECT Art::g_rcScreenCapture ...
0x1805ffe12  mov     edi, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.bottom; tagRECT Art::g_rcScreenCapture ...
0x1805ffe18  sub     ebx, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.left; tagRECT Art::g_rcScreenCapture ...
0x1805ffe1e  sub     edi, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.top; tagRECT Art::g_rcScreenCapture ...
0x1805ffe24  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcOffScreen
0x1805ffe2b  test    rcx, rcx
0x1805ffe2e  jnz     short loc_1805FFE47
0x1805ffe30  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; hdc
0x1805ffe37  call    cs:__imp_CreateCompatibleDC
0x1805ffe3d  mov     rcx, rax
0x1805ffe40  mov     cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA, rax; HDC__ * Art::g_hdcOffScreen
0x1805ffe47  cmp     cs:?g_bmpOffScreen@Art@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * Art::g_bmpOffScreen
0x1805ffe4f  jnz     short loc_1805FFE81
0x1805ffe51  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; hdc
0x1805ffe58  mov     r8d, edi; cy
0x1805ffe5b  mov     edx, ebx; cx
0x1805ffe5d  call    cs:__imp_CreateCompatibleBitmap
0x1805ffe63  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; hdc
0x1805ffe6a  mov     rdx, rax; h
0x1805ffe6d  mov     cs:?g_bmpOffScreen@Art@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * Art::g_bmpOffScreen
0x1805ffe74  call    cs:__imp_SelectObject
0x1805ffe7a  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; hdc
0x1805ffe81  mov     rax, cs:?g_hdcScreenCaptureBlended@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcScreenCaptureBlended
0x1805ffe88  mov     r9d, ebx; cx
0x1805ffe8b  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1805ffe93  xor     r8d, r8d; y
0x1805ffe96  mov     [rsp+0C8h+y1], 0; y1
0x1805ffe9e  xor     edx, edx; x
0x1805ffea0  mov     [rsp+0C8h+x1], 0; x1
0x1805ffea8  mov     [rsp+0C8h+hdcSrc], rax; hdcSrc
0x1805ffead  mov     [rsp+0C8h+cy], edi; cy
0x1805ffeb1  call    cs:__imp_BitBlt
0x1805ffeb7  lea     rcx, ?g_rcCaptureRect@Art@@3UtagRECT@@A; lprc
0x1805ffebe  call    cs:__imp_IsRectEmpty
0x1805ffec4  test    eax, eax
0x1805ffec6  jnz     loc_1805FFFBF
0x1805ffecc  mov     ecx, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.bottom; tagRECT Art::g_rcCaptureRect ...
0x1805ffed2  mov     r8d, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.top; y
0x1805ffed9  sub     ecx, r8d
0x1805ffedc  mov     edx, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.left; x
0x1805ffee2  mov     rax, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcScreenCapture
0x1805ffee9  mov     r9d, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.right; tagRECT Art::g_rcCaptureRect ...
0x1805ffef0  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1805ffef8  sub     r9d, edx; cx
0x1805ffefb  mov     [rsp+0C8h+y1], r8d; y1
0x1805fff00  mov     [rsp+0C8h+x1], edx; x1
0x1805fff04  mov     [rsp+0C8h+hdcSrc], rax; hdcSrc
0x1805fff09  mov     [rsp+0C8h+cy], ecx; cy
0x1805fff0d  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; hdc
0x1805fff14  call    cs:__imp_BitBlt
0x1805fff1a  call    ?FInHighContrastMode@Art@@YA_NXZ; Art::FInHighContrastMode(void)
0x1805fff1f  test    al, al
0x1805fff21  jz      short loc_1805FFF30
0x1805fff23  mov     ecx, 8; nIndex
0x1805fff28  call    cs:__imp_GetSysColorBrush
0x1805fff2e  jmp     short loc_1805FFF38
0x1805fff30  xor     ecx, ecx; color
0x1805fff32  call    cs:__imp_CreateSolidBrush
0x1805fff38  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; hDC
0x1805fff3f  lea     rdx, ?g_rcCaptureRect@Art@@3UtagRECT@@A; lprc
0x1805fff46  mov     r8, rax; hbr
0x1805fff49  mov     rsi, rax
0x1805fff4c  call    cs:__imp_FrameRect
0x1805fff52  call    ?FInHighContrastMode@Art@@YA_NXZ; Art::FInHighContrastMode(void)
0x1805fff57  test    al, al
0x1805fff59  jz      short loc_1805FFFB6
0x1805fff5b  movups  xmm0, xmmword ptr cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.left; tagRECT Art::g_rcCaptureRect ...
0x1805fff62  or      r8d, 0FFFFFFFFh; dy
0x1805fff66  lea     rcx, [rsp+0C8h+rc]; lprc
0x1805fff6b  or      edx, r8d; dx
0x1805fff6e  movdqu  xmmword ptr [rsp+0C8h+rc.left], xmm0
0x1805fff74  call    cs:__imp_InflateRect
0x1805fff7a  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; hDC
0x1805fff81  lea     rdx, [rsp+0C8h+rc]; lprc
0x1805fff86  mov     r8, rsi; hbr
0x1805fff89  call    cs:__imp_FrameRect
0x1805fff8f  or      r8d, 0FFFFFFFFh; dy
0x1805fff93  lea     rcx, [rsp+0C8h+rc]; lprc
0x1805fff98  or      edx, r8d; dx
0x1805fff9b  call    cs:__imp_InflateRect
0x1805fffa1  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; hDC
0x1805fffa8  lea     rdx, [rsp+0C8h+rc]; lprc
0x1805fffad  mov     r8, rsi; hbr
0x1805fffb0  call    cs:__imp_FrameRect
0x1805fffb6  mov     rcx, rsi; ho
0x1805fffb9  call    cs:__imp_DeleteObject
0x1805fffbf  xor     edx, edx; Val
0x1805fffc1  lea     rcx, [rsp+0C8h+Paint]; void *
0x1805fffc6  lea     r8d, [rdx+48h]; Size
0x1805fffca  call    memset_0
0x1805fffcf  mov     rcx, cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA; hWnd
0x1805fffd6  lea     rdx, [rsp+0C8h+Paint]; lpPaint
0x1805fffdb  call    cs:__imp_BeginPaint
0x1805fffe1  mov     rcx, cs:?g_hdcOffScreen@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcOffScreen
0x1805fffe8  mov     r9d, ebx; cx
0x1805fffeb  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1805ffff3  xor     r8d, r8d; y
0x1805ffff6  mov     [rsp+0C8h+y1], 0; y1
0x1805ffffe  xor     edx, edx; x
0x180600000  mov     [rsp+0C8h+x1], 0; x1
0x180600008  mov     [rsp+0C8h+hdcSrc], rcx; hdcSrc
0x18060000d  mov     rcx, rax; hdc
0x180600010  mov     [rsp+0C8h+cy], edi; cy
0x180600014  call    cs:__imp_BitBlt
0x18060001a  mov     rcx, cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA; hWnd
0x180600021  lea     rdx, [rsp+0C8h+Paint]; lpPaint
0x180600026  call    cs:__imp_EndPaint
0x18060002c  mov     rcx, [rsp+0C8h+var_18]
0x180600034  xor     rcx, rsp; StackCookie
0x180600037  call    __security_check_cookie
0x18060003c  lea     r11, [rsp+0C8h+var_8]
0x180600044  mov     rbx, [r11+10h]
0x180600048  mov     rsi, [r11+18h]
0x18060004c  mov     rsp, r11
0x18060004f  pop     rdi
0x180600050  retn
```
