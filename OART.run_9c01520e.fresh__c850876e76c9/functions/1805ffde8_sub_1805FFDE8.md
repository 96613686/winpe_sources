# sub_1805FFDE8

- ea: `0x1805ffde8`
- end: `0x180600051`
- name: `sub_1805FFDE8`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180521700`

## callees

- `0x1800ef520`
- `0x180276c91`
- `0x180278e70`
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
BOOL sub_1805FFDE8()
{
  int v0; // ebx
  int cy; // edi
  HDC CompatibleDC; // rcx
  HBRUSH SysColorBrush; // rax
  HBRUSH v4; // rsi
  HDC v5; // rax
  struct tagRECT rc; // [rsp+50h] [rbp-78h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+60h] [rbp-68h] BYREF

  v0 = x1.right - x1.left;
  cy = x1.bottom - x1.top;
  CompatibleDC = hDC;
  if ( !hDC )
  {
    CompatibleDC = CreateCompatibleDC(hdcSrc);
    hDC = CompatibleDC;
  }
  if ( !ho )
  {
    ho = CreateCompatibleBitmap(hdcSrc, v0, cy);
    SelectObject(hDC, ho);
    CompatibleDC = hDC;
  }
  BitBlt(CompatibleDC, 0, 0, v0, cy, hdcDest, 0, 0, 0xCC0020u);
  if ( !IsRectEmpty(&Rect) )
  {
    BitBlt(
      hDC,
      Rect.left,
      Rect.top,
      Rect.right - Rect.left,
      Rect.bottom - Rect.top,
      hdcSrc,
      Rect.left,
      Rect.top,
      0xCC0020u);
    if ( (unsigned __int8)oart_55864() )
      SysColorBrush = GetSysColorBrush(8);
    else
      SysColorBrush = CreateSolidBrush(0);
    v4 = SysColorBrush;
    FrameRect(hDC, &Rect, SysColorBrush);
    if ( (unsigned __int8)oart_55864() )
    {
      rc = Rect;
      InflateRect(&rc, -1, -1);
      FrameRect(hDC, &rc, v4);
      InflateRect(&rc, -1, -1);
      FrameRect(hDC, &rc, v4);
    }
    DeleteObject(v4);
  }
  memset(&Paint, 0, sizeof(Paint));
  v5 = BeginPaint(hWnd, &Paint);
  BitBlt(v5, 0, 0, v0, cy, hDC, 0, 0, 0xCC0020u);
  return EndPaint(hWnd, &Paint);
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
0x1805ffe0c  mov     ebx, cs:x1.right
0x1805ffe12  mov     edi, cs:x1.bottom
0x1805ffe18  sub     ebx, cs:x1.left
0x1805ffe1e  sub     edi, cs:x1.top
0x1805ffe24  mov     rcx, cs:hDC
0x1805ffe2b  test    rcx, rcx
0x1805ffe2e  jnz     short loc_1805FFE47
0x1805ffe30  mov     rcx, cs:hdcSrc; hdc
0x1805ffe37  call    cs:CreateCompatibleDC
0x1805ffe3d  mov     rcx, rax
0x1805ffe40  mov     cs:hDC, rax
0x1805ffe47  cmp     cs:ho, 0
0x1805ffe4f  jnz     short loc_1805FFE81
0x1805ffe51  mov     rcx, cs:hdcSrc; hdc
0x1805ffe58  mov     r8d, edi; cy
0x1805ffe5b  mov     edx, ebx; cx
0x1805ffe5d  call    cs:CreateCompatibleBitmap
0x1805ffe63  mov     rcx, cs:hDC; hdc
0x1805ffe6a  mov     rdx, rax; h
0x1805ffe6d  mov     cs:ho, rax
0x1805ffe74  call    cs:SelectObject
0x1805ffe7a  mov     rcx, cs:hDC; hdc
0x1805ffe81  mov     rax, cs:hdcDest
0x1805ffe88  mov     r9d, ebx; cx
0x1805ffe8b  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1805ffe93  xor     r8d, r8d; y
0x1805ffe96  mov     [rsp+0C8h+y1], 0; y1
0x1805ffe9e  xor     edx, edx; x
0x1805ffea0  mov     [rsp+0C8h+x1], 0; x1
0x1805ffea8  mov     [rsp+0C8h+hdcSrc], rax; hdcSrc
0x1805ffead  mov     [rsp+0C8h+cy], edi; cy
0x1805ffeb1  call    cs:BitBlt
0x1805ffeb7  lea     rcx, Rect; lprc
0x1805ffebe  call    cs:IsRectEmpty
0x1805ffec4  test    eax, eax
0x1805ffec6  jnz     loc_1805FFFBF
0x1805ffecc  mov     ecx, cs:Rect.bottom
0x1805ffed2  mov     r8d, cs:Rect.top; y
0x1805ffed9  sub     ecx, r8d
0x1805ffedc  mov     edx, cs:Rect.left; x
0x1805ffee2  mov     rax, cs:hdcSrc
0x1805ffee9  mov     r9d, cs:Rect.right
0x1805ffef0  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1805ffef8  sub     r9d, edx; cx
0x1805ffefb  mov     [rsp+0C8h+y1], r8d; y1
0x1805fff00  mov     [rsp+0C8h+x1], edx; x1
0x1805fff04  mov     [rsp+0C8h+hdcSrc], rax; hdcSrc
0x1805fff09  mov     [rsp+0C8h+cy], ecx; cy
0x1805fff0d  mov     rcx, cs:hDC; hdc
0x1805fff14  call    cs:BitBlt
0x1805fff1a  call    oart_55864
0x1805fff1f  test    al, al
0x1805fff21  jz      short loc_1805FFF30
0x1805fff23  mov     ecx, 8; nIndex
0x1805fff28  call    cs:GetSysColorBrush
0x1805fff2e  jmp     short loc_1805FFF38
0x1805fff30  xor     ecx, ecx; color
0x1805fff32  call    cs:CreateSolidBrush
0x1805fff38  mov     rcx, cs:hDC; hDC
0x1805fff3f  lea     rdx, Rect; lprc
0x1805fff46  mov     r8, rax; hbr
0x1805fff49  mov     rsi, rax
0x1805fff4c  call    cs:FrameRect
0x1805fff52  call    oart_55864
0x1805fff57  test    al, al
0x1805fff59  jz      short loc_1805FFFB6
0x1805fff5b  movups  xmm0, xmmword ptr cs:Rect.left
0x1805fff62  or      r8d, 0FFFFFFFFh; dy
0x1805fff66  lea     rcx, [rsp+0C8h+rc]; lprc
0x1805fff6b  or      edx, r8d; dx
0x1805fff6e  movdqu  xmmword ptr [rsp+0C8h+rc.left], xmm0
0x1805fff74  call    cs:InflateRect
0x1805fff7a  mov     rcx, cs:hDC; hDC
0x1805fff81  lea     rdx, [rsp+0C8h+rc]; lprc
0x1805fff86  mov     r8, rsi; hbr
0x1805fff89  call    cs:FrameRect
0x1805fff8f  or      r8d, 0FFFFFFFFh; dy
0x1805fff93  lea     rcx, [rsp+0C8h+rc]; lprc
0x1805fff98  or      edx, r8d; dx
0x1805fff9b  call    cs:InflateRect
0x1805fffa1  mov     rcx, cs:hDC; hDC
0x1805fffa8  lea     rdx, [rsp+0C8h+rc]; lprc
0x1805fffad  mov     r8, rsi; hbr
0x1805fffb0  call    cs:FrameRect
0x1805fffb6  mov     rcx, rsi; ho
0x1805fffb9  call    cs:DeleteObject
0x1805fffbf  xor     edx, edx; Val
0x1805fffc1  lea     rcx, [rsp+0C8h+Paint]; void *
0x1805fffc6  lea     r8d, [rdx+48h]; Size
0x1805fffca  call    memset
0x1805fffcf  mov     rcx, cs:hWnd; hWnd
0x1805fffd6  lea     rdx, [rsp+0C8h+Paint]; lpPaint
0x1805fffdb  call    cs:BeginPaint
0x1805fffe1  mov     rcx, cs:hDC
0x1805fffe8  mov     r9d, ebx; cx
0x1805fffeb  mov     [rsp+0C8h+rop], 0CC0020h; rop
0x1805ffff3  xor     r8d, r8d; y
0x1805ffff6  mov     [rsp+0C8h+y1], 0; y1
0x1805ffffe  xor     edx, edx; x
0x180600000  mov     [rsp+0C8h+x1], 0; x1
0x180600008  mov     [rsp+0C8h+hdcSrc], rcx; hdcSrc
0x18060000d  mov     rcx, rax; hdc
0x180600010  mov     [rsp+0C8h+cy], edi; cy
0x180600014  call    cs:BitBlt
0x18060001a  mov     rcx, cs:hWnd; hWnd
0x180600021  lea     rdx, [rsp+0C8h+Paint]; lpPaint
0x180600026  call    cs:EndPaint
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
