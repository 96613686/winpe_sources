# ATL::CAxHostWindow::ReleaseDC(HDC__ *)

- ea: `0x180010b30`
- end: `0x180010bf4`
- name: `?ReleaseDC@CAxHostWindow@ATL@@UEAAJPEAUHDC__@@@Z`
- size: `196`
- prototype: `int(ATL::CAxHostWindow *__hidden this, HDC)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001800`
- `0x180010b30`

## import_xrefs

- `GDI32!DeleteDC` at `0x180010bbc`
- `GDI32!DeleteDC` at `0x180010bbc`
- `GDI32!BitBlt` at `0x180010bb3`
- `GDI32!BitBlt` at `0x180010bb3`
- `USER32!ReleaseDC` at `0x180010bcd`
- `USER32!ReleaseDC` at `0x180010bcd`
- `USER32!GetClientRect` at `0x180010b70`
- `USER32!GetClientRect` at `0x180010b70`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::ReleaseDC(ATL::CAxHostWindow *this, HDC a2)
{
  bool v2; // zf
  HWND v5; // rcx
  struct tagRECT Rect; // [rsp+50h] [rbp-28h] BYREF

  v2 = *((_QWORD *)this + 11) == 0;
  *((_BYTE *)this + 96) = 1;
  if ( !v2 )
  {
    v5 = (HWND)*((_QWORD *)this - 10);
    Rect = 0;
    GetClientRect(v5, &Rect);
    BitBlt(
      *((HDC *)this + 11),
      Rect.left,
      Rect.top,
      Rect.right - Rect.left,
      Rect.bottom - Rect.top,
      a2,
      0,
      0,
      0xCC0020u);
    DeleteDC(a2);
    a2 = (HDC)*((_QWORD *)this + 11);
  }
  ReleaseDC(*((HWND *)this - 10), a2);
  return 0;
}

```

## disassembly

```asm
0x180010b30  mov     [rsp+arg_10], rbx
0x180010b35  mov     [rsp+arg_18], rsi
0x180010b3a  push    rdi
0x180010b3b  sub     rsp, 70h
0x180010b3f  mov     rax, cs:__security_cookie
0x180010b46  xor     rax, rsp
0x180010b49  mov     [rsp+78h+var_18], rax
0x180010b4e  cmp     qword ptr [rcx+58h], 0
0x180010b53  mov     rsi, rdx
0x180010b56  mov     rdi, rcx
0x180010b59  mov     byte ptr [rcx+60h], 1
0x180010b5d  jz      short loc_180010BC6
0x180010b5f  mov     rcx, [rcx-50h]; hWnd
0x180010b63  lea     rdx, [rsp+78h+Rect]; lpRect
0x180010b68  xorps   xmm0, xmm0
0x180010b6b  movups  xmmword ptr [rsp+78h+Rect.left], xmm0
0x180010b70  call    cs:__imp_GetClientRect
0x180010b76  mov     eax, [rsp+78h+Rect.bottom]
0x180010b7a  mov     r8d, [rsp+78h+Rect.top]; y
0x180010b7f  sub     eax, r8d
0x180010b82  mov     r9d, [rsp+78h+Rect.right]
0x180010b87  mov     edx, [rsp+78h+Rect.left]; x
0x180010b8b  sub     r9d, edx; cx
0x180010b8e  mov     rcx, [rdi+58h]; hdc
0x180010b92  mov     [rsp+78h+rop], 0CC0020h; rop
0x180010b9a  mov     [rsp+78h+y1], 0; y1
0x180010ba2  mov     [rsp+78h+x1], 0; x1
0x180010baa  mov     [rsp+78h+hdcSrc], rsi; hdcSrc
0x180010baf  mov     [rsp+78h+cy], eax; cy
0x180010bb3  call    cs:__imp_BitBlt
0x180010bb9  mov     rcx, rsi; hdc
0x180010bbc  call    cs:__imp_DeleteDC
0x180010bc2  mov     rsi, [rdi+58h]
0x180010bc6  mov     rcx, [rdi-50h]; hWnd
0x180010bca  mov     rdx, rsi; hDC
0x180010bcd  call    cs:__imp_ReleaseDC
0x180010bd3  xor     eax, eax
0x180010bd5  mov     rcx, [rsp+78h+var_18]
0x180010bda  xor     rcx, rsp; StackCookie
0x180010bdd  call    __security_check_cookie
0x180010be2  lea     r11, [rsp+78h+var_8]
0x180010be7  mov     rbx, [r11+20h]
0x180010beb  mov     rsi, [r11+28h]
0x180010bef  mov     rsp, r11
0x180010bf2  pop     rdi
0x180010bf3  retn
```
