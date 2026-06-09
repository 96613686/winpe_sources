# ModularWindow::CommandBar::LayoutControls(void)

- ea: `0x180033a94`
- end: `0x180033c0f`
- name: `?LayoutControls@CommandBar@ModularWindow@@AEAAXXZ`
- size: `379`
- prototype: `void __fastcall(ModularWindow::CommandBar *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006ce08`

## callees

- `0x18002751c`
- `0x180033a94`
- `0x18003f800`
- `0x18005bcb4`
- `0x18007b000`

## import_xrefs

- `USER32!BeginDeferWindowPos` at `0x180033b35`
- `USER32!BeginDeferWindowPos` at `0x180033b35`
- `USER32!IsWindow` at `0x180033b83`
- `USER32!IsWindow` at `0x180033b83`
- `USER32!EndDeferWindowPos` at `0x180033bde`
- `USER32!EndDeferWindowPos` at `0x180033bde`
- `USER32!GetClientRect` at `0x180033b12`
- `USER32!GetClientRect` at `0x180033b12`
- `USER32!DeferWindowPos` at `0x180033bc0`
- `USER32!DeferWindowPos` at `0x180033bc0`
- `gdiplus!GdipCreateFromHWND` at `0x180033ace`
- `gdiplus!GdipCreateFromHWND` at `0x180033ace`
- `gdiplus!GdipDeleteGraphics` at `0x180033be9`
- `gdiplus!GdipDeleteGraphics` at `0x180033be9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ModularWindow::CommandBar::LayoutControls(ModularWindow::CommandBar *this)
{
  int v2; // eax
  HDWP v3; // rbx
  __int64 i; // rdi
  LONG right; // r14d
  LONG bottom; // r15d
  int v7; // r13d
  HWND v8; // r12
  __int64 v9; // [rsp+40h] [rbp-39h] BYREF
  LONG top; // [rsp+48h] [rbp-31h]
  __int64 v11; // [rsp+50h] [rbp-29h] BYREF
  int v12; // [rsp+58h] [rbp-21h]
  _BYTE pExceptionObject[24]; // [rsp+60h] [rbp-19h] BYREF
  struct tagRECT Rect; // [rsp+78h] [rbp-1h] BYREF

  v9 = 0;
  v2 = GdipCreateFromHWND(*((_QWORD *)this + 1), &v9);
  v11 = v9;
  v12 = 0;
  if ( v2 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v2);
    throw (Base::GdiException *)pExceptionObject;
  }
  Rect = 0;
  GetClientRect(*((HWND *)this + 1), &Rect);
  if ( Rect.left < Rect.right && Rect.top < Rect.bottom )
  {
    v3 = BeginDeferWindowPos(7);
    ModularWindow::CommandBar::GetPadding(this, (struct Gdiplus::Graphics *)&v11, &Rect);
    for ( i = 0; i != 7; ++i )
    {
      top = Rect.top;
      right = Rect.right;
      bottom = Rect.bottom;
      v7 = *((_DWORD *)this + i + 1178);
      LODWORD(v9) = *((_DWORD *)this + i + 1185);
      v8 = (HWND)*((_QWORD *)this + 80 * i + 30);
      if ( IsWindow(v8) && v3 )
        v3 = DeferWindowPos(v3, v8, 0, v7, (int)v9 + top, right - v7, bottom - ((int)v9 + top), 0x15u);
    }
    if ( v3 )
      EndDeferWindowPos(v3);
  }
  GdipDeleteGraphics(v11);
}

```

## disassembly

```asm
0x180033a94  push    rbp
0x180033a96  push    rbx
0x180033a97  push    rsi
0x180033a98  push    rdi
0x180033a99  push    r12
0x180033a9b  push    r13
0x180033a9d  push    r14
0x180033a9f  push    r15
0x180033aa1  lea     rbp, [rsp-1Fh]
0x180033aa6  sub     rsp, 98h
0x180033aad  mov     rax, cs:__security_cookie
0x180033ab4  xor     rax, rsp
0x180033ab7  mov     [rbp+57h+var_48], rax
0x180033abb  mov     rsi, rcx
0x180033abe  mov     [rbp+57h+var_90], 0
0x180033ac6  lea     rdx, [rbp+57h+var_90]
0x180033aca  mov     rcx, [rcx+8]
0x180033ace  call    cs:__imp_GdipCreateFromHWND
0x180033ad4  mov     rcx, [rbp+57h+var_90]
0x180033ad8  mov     [rbp+57h+var_80], rcx
0x180033adc  mov     [rbp+57h+var_78], 0
0x180033ae3  test    eax, eax
0x180033ae5  jz      short loc_180033B03
0x180033ae7  mov     edx, eax; int
0x180033ae9  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180033aed  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180033af2  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180033af9  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180033afd  call    _CxxThrowException_0
0x180033b03  xorps   xmm0, xmm0
0x180033b06  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180033b0a  lea     rdx, [rbp+57h+Rect]; lpRect
0x180033b0e  mov     rcx, [rsi+8]; hWnd
0x180033b12  call    cs:__imp_GetClientRect
0x180033b18  mov     eax, [rbp+57h+Rect.right]
0x180033b1b  cmp     [rbp+57h+Rect.left], eax
0x180033b1e  jge     loc_180033BE5
0x180033b24  mov     eax, [rbp+57h+Rect.bottom]
0x180033b27  cmp     [rbp+57h+Rect.top], eax
0x180033b2a  jge     loc_180033BE5
0x180033b30  mov     ecx, 7; nNumWindows
0x180033b35  call    cs:__imp_BeginDeferWindowPos
0x180033b3b  mov     rbx, rax
0x180033b3e  lea     r8, [rbp+57h+Rect]; struct tagRECT *
0x180033b42  lea     rdx, [rbp+57h+var_80]; struct Gdiplus::Graphics *
0x180033b46  mov     rcx, rsi; this
0x180033b49  call    ?GetPadding@CommandBar@ModularWindow@@AEAAXAEAVGraphics@Gdiplus@@AEBUtagRECT@@@Z; ModularWindow::CommandBar::GetPadding(Gdiplus::Graphics &,tagRECT const &)
0x180033b4e  xor     edi, edi
0x180033b50  mov     eax, [rbp+57h+Rect.top]
0x180033b53  mov     [rbp+57h+var_88], eax
0x180033b56  mov     r14d, [rbp+57h+Rect.right]
0x180033b5a  mov     r15d, [rbp+57h+Rect.bottom]
0x180033b5e  mov     r13d, [rsi+rdi*4+1268h]
0x180033b66  mov     eax, [rsi+rdi*4+1284h]
0x180033b6d  mov     dword ptr [rbp+57h+var_90], eax
0x180033b70  lea     rax, [rdi+rdi*4]
0x180033b74  shl     rax, 7
0x180033b78  mov     r12, [rax+rsi+0F0h]
0x180033b80  mov     rcx, r12; hWnd
0x180033b83  call    cs:__imp_IsWindow
0x180033b89  test    eax, eax
0x180033b8b  jz      short loc_180033BC9
0x180033b8d  test    rbx, rbx
0x180033b90  jz      short loc_180033BC9
0x180033b92  mov     eax, [rbp+57h+var_88]
0x180033b95  add     eax, dword ptr [rbp+57h+var_90]
0x180033b98  sub     r15d, eax
0x180033b9b  sub     r14d, r13d
0x180033b9e  mov     [rsp+0D0h+uFlags], 15h; uFlags
0x180033ba6  mov     [rsp+0D0h+cy], r15d; cy
0x180033bab  mov     [rsp+0D0h+var_A8], r14d; cx
0x180033bb0  mov     [rsp+0D0h+y], eax; y
0x180033bb4  mov     r9d, r13d; x
0x180033bb7  xor     r8d, r8d; hWndInsertAfter
0x180033bba  mov     rdx, r12; hWnd
0x180033bbd  mov     rcx, rbx; hWinPosInfo
0x180033bc0  call    cs:__imp_DeferWindowPos
0x180033bc6  mov     rbx, rax
0x180033bc9  inc     rdi
0x180033bcc  cmp     rdi, 7
0x180033bd0  jnz     loc_180033B50
0x180033bd6  test    rbx, rbx
0x180033bd9  jz      short loc_180033BE5
0x180033bdb  mov     rcx, rbx; hWinPosInfo
0x180033bde  call    cs:__imp_EndDeferWindowPos
0x180033be4  nop
0x180033be5  mov     rcx, [rbp+57h+var_80]
0x180033be9  call    cs:__imp_GdipDeleteGraphics
0x180033bef  mov     rcx, [rbp+57h+var_48]
0x180033bf3  xor     rcx, rsp; StackCookie
0x180033bf6  call    __security_check_cookie
0x180033bfb  add     rsp, 98h
0x180033c02  pop     r15
0x180033c04  pop     r14
0x180033c06  pop     r13
0x180033c08  pop     r12
0x180033c0a  pop     rdi
0x180033c0b  pop     rsi
0x180033c0c  pop     rbx
0x180033c0d  pop     rbp
0x180033c0e  retn
```
