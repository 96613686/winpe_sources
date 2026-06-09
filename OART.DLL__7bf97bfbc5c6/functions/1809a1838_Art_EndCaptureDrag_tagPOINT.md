# Art::EndCaptureDrag(tagPOINT)

- ea: `0x1809a1838`
- end: `0x1809a1966`
- name: `?EndCaptureDrag@Art@@YAXUtagPOINT@@@Z`
- size: `302`
- prototype: `void __fastcall(Art *__hidden this, struct tagPOINT)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1804e6480`

## callees

- `0x180677cf8`
- `0x1809a1838`
- `0x1809a279c`

## import_xrefs

- `GDI32!BitBlt` at `0x1809a18f8`
- `GDI32!BitBlt` at `0x1809a18f8`
- `GDI32!SelectObject` at `0x1809a18b7`
- `GDI32!SelectObject` at `0x1809a1904`
- `GDI32!SelectObject` at `0x1809a18b7`
- `GDI32!SelectObject` at `0x1809a1904`
- `GDI32!DeleteObject` at `0x1809a191c`
- `GDI32!DeleteObject` at `0x1809a191c`
- `GDI32!CreateCompatibleDC` at `0x1809a1896`
- `GDI32!CreateCompatibleDC` at `0x1809a1896`
- `GDI32!DeleteDC` at `0x1809a1925`
- `GDI32!DeleteDC` at `0x1809a1925`
- `GDI32!CreateCompatibleBitmap` at `0x1809a18a8`
- `GDI32!CreateCompatibleBitmap` at `0x1809a18a8`
- `USER32!GetDC` at `0x1809a188a`
- `USER32!GetDC` at `0x1809a188a`
- `USER32!ReleaseDC` at `0x1809a1930`
- `USER32!ReleaseDC` at `0x1809a1930`
- `USER32!ShowWindow` at `0x1809a1946`
- `USER32!ShowWindow` at `0x1809a1946`

## pseudocode

```c
void __fastcall Art::EndCaptureDrag(Art *this, struct tagPOINT a2)
{
  int v2; // r15d
  int cy; // r14d
  HDC DC; // rbp
  HDC CompatibleDC; // rsi
  HBITMAP CompatibleBitmap; // rdi
  HGDIOBJ v7; // rbx
  HPALETTE v8; // rdx

  Art::MouseMoveCaptureDrag(this, a2);
  v2 = Art::g_rcCaptureRect.right - Art::g_rcCaptureRect.left;
  cy = Art::g_rcCaptureRect.bottom - Art::g_rcCaptureRect.top;
  Art::g_fInDrag = 0;
  if ( Art::g_rcCaptureRect.right - Art::g_rcCaptureRect.left >= 5 || cy >= 5 )
  {
    DC = GetDC(0);
    CompatibleDC = CreateCompatibleDC(DC);
    CompatibleBitmap = CreateCompatibleBitmap(DC, v2, cy);
    v7 = SelectObject(CompatibleDC, CompatibleBitmap);
    BitBlt(
      CompatibleDC,
      0,
      0,
      v2,
      cy,
      Art::g_hdcScreenCapture,
      Art::g_rcCaptureRect.left,
      Art::g_rcCaptureRect.top,
      0xCC0020u);
    SelectObject(CompatibleDC, v7);
    Art::g_pBitmapClip = Gdiplus::Bitmap::FromHBITMAP(CompatibleBitmap, v8);
    DeleteObject(CompatibleBitmap);
    DeleteDC(CompatibleDC);
    ReleaseDC(0, DC);
    Art::g_fExitOnDeactivate = 0;
    ShowWindow(Art::g_hwndScreenCapture, 0);
  }
}

```

## disassembly

```asm
0x1809a1838  mov     [rsp+arg_0], rbx
0x1809a183d  mov     [rsp+arg_8], rbp
0x1809a1842  mov     [rsp+arg_10], rsi
0x1809a1847  push    rdi
0x1809a1848  push    r14
0x1809a184a  push    r15
0x1809a184c  sub     rsp, 50h
0x1809a1850  call    ?MouseMoveCaptureDrag@Art@@YAXUtagPOINT@@@Z; Art::MouseMoveCaptureDrag(tagPOINT)
0x1809a1855  mov     r15d, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.right; tagRECT Art::g_rcCaptureRect ...
0x1809a185c  mov     r14d, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.bottom; tagRECT Art::g_rcCaptureRect ...
0x1809a1863  sub     r15d, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.left; tagRECT Art::g_rcCaptureRect ...
0x1809a186a  sub     r14d, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.top; tagRECT Art::g_rcCaptureRect ...
0x1809a1871  mov     cs:?g_fInDrag@Art@@3_NA, 0; bool Art::g_fInDrag
0x1809a1878  cmp     r15d, 5
0x1809a187c  jge     short loc_1809A1888
0x1809a187e  cmp     r14d, 5
0x1809a1882  jl      loc_1809A194C
0x1809a1888  xor     ecx, ecx; hWnd
0x1809a188a  call    cs:__imp_GetDC
0x1809a1890  mov     rcx, rax; hdc
0x1809a1893  mov     rbp, rax
0x1809a1896  call    cs:__imp_CreateCompatibleDC
0x1809a189c  mov     r8d, r14d; cy
0x1809a189f  mov     edx, r15d; cx
0x1809a18a2  mov     rcx, rbp; hdc
0x1809a18a5  mov     rsi, rax
0x1809a18a8  call    cs:__imp_CreateCompatibleBitmap
0x1809a18ae  mov     rdx, rax; h
0x1809a18b1  mov     rcx, rsi; hdc
0x1809a18b4  mov     rdi, rax
0x1809a18b7  call    cs:__imp_SelectObject
0x1809a18bd  mov     ecx, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.top; tagRECT Art::g_rcCaptureRect ...
0x1809a18c3  mov     r9d, r15d; cx
0x1809a18c6  mov     [rsp+68h+rop], 0CC0020h; rop
0x1809a18ce  xor     r8d, r8d; y
0x1809a18d1  mov     [rsp+68h+y1], ecx; y1
0x1809a18d5  xor     edx, edx; x
0x1809a18d7  mov     ecx, cs:?g_rcCaptureRect@Art@@3UtagRECT@@A.left; tagRECT Art::g_rcCaptureRect ...
0x1809a18dd  mov     rbx, rax
0x1809a18e0  mov     [rsp+68h+x1], ecx; x1
0x1809a18e4  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcScreenCapture
0x1809a18eb  mov     [rsp+68h+hdcSrc], rcx; hdcSrc
0x1809a18f0  mov     rcx, rsi; hdc
0x1809a18f3  mov     [rsp+68h+cy], r14d; cy
0x1809a18f8  call    cs:__imp_BitBlt
0x1809a18fe  mov     rdx, rbx; h
0x1809a1901  mov     rcx, rsi; hdc
0x1809a1904  call    cs:__imp_SelectObject
0x1809a190a  mov     rcx, rdi; HBITMAP
0x1809a190d  call    ?FromHBITMAP@Bitmap@Gdiplus@@SAPEAV12@PEAUHBITMAP__@@PEAUHPALETTE__@@@Z; Gdiplus::Bitmap::FromHBITMAP(HBITMAP__ *,HPALETTE__ *)
0x1809a1912  mov     rcx, rdi; ho
0x1809a1915  mov     cs:?g_pBitmapClip@Art@@3PEAVBitmap@Gdiplus@@EA, rax; Gdiplus::Bitmap * Art::g_pBitmapClip
0x1809a191c  call    cs:__imp_DeleteObject
0x1809a1922  mov     rcx, rsi; hdc
0x1809a1925  call    cs:__imp_DeleteDC
0x1809a192b  mov     rdx, rbp; hDC
0x1809a192e  xor     ecx, ecx; hWnd
0x1809a1930  call    cs:__imp_ReleaseDC
0x1809a1936  mov     rcx, cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA; hWnd
0x1809a193d  xor     edx, edx; nCmdShow
0x1809a193f  mov     cs:?g_fExitOnDeactivate@Art@@3_NA, 0; bool Art::g_fExitOnDeactivate
0x1809a1946  call    cs:__imp_ShowWindow
0x1809a194c  lea     r11, [rsp+68h+var_18]
0x1809a1951  mov     rbx, [r11+20h]
0x1809a1955  mov     rbp, [r11+28h]
0x1809a1959  mov     rsi, [r11+30h]
0x1809a195d  mov     rsp, r11
0x1809a1960  pop     r15
0x1809a1962  pop     r14
0x1809a1964  pop     rdi
0x1809a1965  retn
```
