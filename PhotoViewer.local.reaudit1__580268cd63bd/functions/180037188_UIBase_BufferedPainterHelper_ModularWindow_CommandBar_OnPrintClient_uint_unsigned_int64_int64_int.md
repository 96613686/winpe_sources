# UIBase::BufferedPainterHelper<ModularWindow::CommandBar>::OnPrintClient(uint,unsigned __int64,__int64,int &)

- ea: `0x180037188`
- end: `0x18003724e`
- name: `?OnPrintClient@?$BufferedPainterHelper@VCommandBar@ModularWindow@@@UIBase@@QEAA_JI_K_JAEAH@Z`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007ef0`

## callees

- `0x1800072d0`
- `0x1800269d8`
- `0x180037188`
- `0x18003f800`

## import_xrefs

- `USER32!GetClientRect` at `0x1800371fb`
- `USER32!GetClientRect` at `0x1800371fb`
- `USER32!IsWindowVisible` at `0x1800371d3`
- `USER32!IsWindowVisible` at `0x1800371d3`
- `gdiplus!GdipDeleteGraphics` at `0x180037224`
- `gdiplus!GdipDeleteGraphics` at `0x180037224`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UIBase::BufferedPainterHelper<ModularWindow::CommandBar>::OnPrintClient(
        __int64 a1,
        __int64 a2,
        HDC a3,
        char a4)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  ModularWindow::CommandBar *v8; // rcx
  _QWORD v10[2]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v11[16]; // [rsp+30h] [rbp-38h] BYREF
  struct tagRECT Rect; // [rsp+40h] [rbp-28h] BYREF

  if ( a3 && (a4 & 4) != 0 )
  {
    if ( (a4 & 1) == 0 )
      goto LABEL_7;
    v6 = a1 - 176;
    if ( !a1 )
      v6 = 8;
    if ( IsWindowVisible(*(HWND *)v6) )
    {
LABEL_7:
      Rect = 0;
      v7 = a1 - 176;
      if ( !a1 )
        v7 = 8;
      GetClientRect(*(HWND *)v7, &Rect);
      Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)v10, a3);
      try
      {
        ModularWindow::CommandBar::PaintBackground(v8, (struct Gdiplus::Graphics *)v10, &Rect);
        GdipDeleteGraphics(v10[0]);
      }
      catch ( Base::Exception v11 )
      {
        Base::Exception::~Exception((Base::Exception *)v11);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180037188  mov     [rsp+arg_8], rbx
0x18003718d  mov     [rsp+arg_18], rsi
0x180037192  push    rdi
0x180037193  sub     rsp, 60h
0x180037197  mov     rax, cs:__security_cookie
0x18003719e  xor     rax, rsp
0x1800371a1  mov     [rsp+68h+var_18], rax
0x1800371a6  mov     rsi, r8
0x1800371a9  mov     rdi, rcx
0x1800371ac  test    r8, r8
0x1800371af  jz      short loc_18003722B
0x1800371b1  test    r9b, 4
0x1800371b5  jz      short loc_18003722B
0x1800371b7  mov     ebx, 8
0x1800371bc  test    r9b, 1
0x1800371c0  jz      short loc_1800371DD
0x1800371c2  add     rcx, 0FFFFFFFFFFFFFF50h
0x1800371c9  test    rdi, rdi
0x1800371cc  cmovz   rcx, rbx
0x1800371d0  mov     rcx, [rcx]; hWnd
0x1800371d3  call    cs:__imp_IsWindowVisible
0x1800371d9  test    eax, eax
0x1800371db  jz      short loc_18003722B
0x1800371dd  xorps   xmm0, xmm0
0x1800371e0  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x1800371e5  lea     rcx, [rdi-0B0h]
0x1800371ec  test    rdi, rdi
0x1800371ef  cmovz   rcx, rbx
0x1800371f3  lea     rdx, [rsp+68h+Rect]; lpRect
0x1800371f8  mov     rcx, [rcx]; hWnd
0x1800371fb  call    cs:__imp_GetClientRect
0x180037201  mov     rdx, rsi; HDC
0x180037204  lea     rcx, [rsp+68h+var_48]; this
0x180037209  call    ??0Graphics@Gdiplus@@QEAA@PEAUHDC__@@@Z; Gdiplus::Graphics::Graphics(HDC__ *)
0x18003720e  nop
0x18003720f  lea     r8, [rsp+68h+Rect]; struct tagRECT *
0x180037214  lea     rdx, [rsp+68h+var_48]; struct Gdiplus::Graphics *
0x180037219  call    ?PaintBackground@CommandBar@ModularWindow@@AEAAXPEAVGraphics@Gdiplus@@AEBUtagRECT@@@Z; ModularWindow::CommandBar::PaintBackground(Gdiplus::Graphics *,tagRECT const &)
0x18003721e  nop
0x18003721f  mov     rcx, [rsp+68h+var_48]
0x180037224  call    cs:__imp_GdipDeleteGraphics
0x18003722a  nop
0x18003722b  jmp     short $+2
0x18003722d  xor     eax, eax
0x18003722f  mov     rcx, [rsp+68h+var_18]
0x180037234  xor     rcx, rsp; StackCookie
0x180037237  call    __security_check_cookie
0x18003723c  lea     r11, [rsp+68h+var_8]
0x180037241  mov     rbx, [r11+18h]
0x180037245  mov     rsi, [r11+28h]
0x180037249  mov     rsp, r11
0x18003724c  pop     rdi
0x18003724d  retn
```
