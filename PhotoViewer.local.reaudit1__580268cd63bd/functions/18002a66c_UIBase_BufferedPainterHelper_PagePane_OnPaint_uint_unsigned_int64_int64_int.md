# UIBase::BufferedPainterHelper<PagePane>::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x18002a66c`
- end: `0x18002a7a2`
- name: `?OnPaint@?$BufferedPainterHelper@VPagePane@@@UIBase@@QEAA_JI_K_JAEAH@Z`
- size: `310`
- prototype: `__int64 __fastcall(UIBase::ChildWindowCompositionHelper *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000a2b0`

## callees

- `0x180001800`
- `0x180009588`
- `0x18000986c`
- `0x180029780`
- `0x18002a66c`
- `0x18002a7a8`
- `0x18002a954`
- `0x18002ab5c`
- `0x18002abbc`
- `0x18003f800`

## import_xrefs

- `USER32!GetClientRect` at `0x18002a6b2`
- `USER32!GetClientRect` at `0x18002a6b2`
- `USER32!EndPaint` at `0x18002a776`
- `USER32!EndPaint` at `0x18002a776`
- `gdiplus!GdipDeleteGraphics` at `0x18002a760`
- `gdiplus!GdipDeleteGraphics` at `0x18002a760`

## pseudocode

```c
__int64 __fastcall UIBase::BufferedPainterHelper<PagePane>::OnPaint(UIBase::ChildWindowCompositionHelper *this)
{
  HWND *v2; // rbx
  HWND v3; // rdx
  const struct tagRECT *v4; // r9
  const struct tagRECT *v5; // r9
  const struct tagRECT *v6; // r9
  _BYTE v8[16]; // [rsp+20h] [rbp-158h] BYREF
  struct tagRECT Rect; // [rsp+30h] [rbp-148h] BYREF
  _BYTE v10[32]; // [rsp+40h] [rbp-138h] BYREF
  int v11; // [rsp+60h] [rbp-118h]
  struct Gdiplus::Graphics *v12; // [rsp+68h] [rbp-110h]
  _BYTE v13[8]; // [rsp+F0h] [rbp-88h] BYREF
  HWND hWnd; // [rsp+F8h] [rbp-80h]
  PAINTSTRUCT Paint; // [rsp+100h] [rbp-78h] BYREF
  __int64 v16; // [rsp+150h] [rbp-28h] BYREF

  v2 = (HWND *)(((unsigned __int64)this - 176) & -(__int64)(this != 0));
  Rect = 0;
  GetClientRect(v2[1], &Rect);
  if ( *((_BYTE *)this + 24) )
  {
    if ( UIBase::ChildWindowCompositionHelper::IsCompositionEnabledForWindow(this) )
    {
      GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainterOnGlass>::WmPaintBufferedPainter<GdipUtil::BufferedPainterOnGlass>(
        (GdipUtil::BufferedPainterOnGlass *)v10,
        v3);
      if ( !v11 )
      {
        GdipUtil::BufferedPainterOnGlass::Clear((GdipUtil::BufferedPainterOnGlass *)v10);
        PagePane::PaintClient(v2, v12, &Rect, v4);
      }
      GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainterOnGlass>::~WmPaintBufferedPainter<GdipUtil::BufferedPainterOnGlass>(v10);
    }
    else
    {
      GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainter>::WmPaintBufferedPainter<GdipUtil::BufferedPainter>(
        (GdipUtil::BufferedPainter *)v10,
        v3);
      if ( !v11 )
        PagePane::PaintClient(v2, v12, &Rect, v5);
      GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainter>::~WmPaintBufferedPainter<GdipUtil::BufferedPainter>(v10);
    }
  }
  else
  {
    try
    {
      GdipUtil::WmPaintGraphics::WmPaintGraphics((GdipUtil::WmPaintGraphics *)v13, v2[1]);
      PagePane::PaintClient(v2, (struct Gdiplus::Graphics *)&v16, &Rect, v6);
      GdipDeleteGraphics(v16);
      EndPaint(hWnd, &Paint);
    }
    catch ( Base::Exception v8 )
    {
      Base::Exception::~Exception((Base::Exception *)v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002a66c  mov     [rsp+arg_8], rbx
0x18002a671  push    rdi
0x18002a672  sub     rsp, 170h
0x18002a679  mov     rax, cs:__security_cookie
0x18002a680  xor     rax, rsp
0x18002a683  mov     [rsp+178h+var_18], rax
0x18002a68b  mov     rdi, rcx
0x18002a68e  mov     rax, rcx
0x18002a691  lea     rdx, [rcx-0B0h]
0x18002a698  neg     rax
0x18002a69b  sbb     rbx, rbx
0x18002a69e  and     rbx, rdx
0x18002a6a1  xorps   xmm0, xmm0
0x18002a6a4  movups  xmmword ptr [rsp+178h+Rect.left], xmm0
0x18002a6a9  lea     rdx, [rsp+178h+Rect]; lpRect
0x18002a6ae  mov     rcx, [rbx+8]; hWnd
0x18002a6b2  call    cs:__imp_GetClientRect
0x18002a6b8  mov     rdx, [rbx+8]; HWND
0x18002a6bc  cmp     byte ptr [rdi+18h], 0
0x18002a6c0  jz      short loc_18002A736
0x18002a6c2  mov     rcx, rdi; this
0x18002a6c5  call    ?IsCompositionEnabledForWindow@ChildWindowCompositionHelper@UIBase@@QEBA_NXZ; UIBase::ChildWindowCompositionHelper::IsCompositionEnabledForWindow(void)
0x18002a6ca  test    al, al
0x18002a6cc  jz      short loc_18002A707
0x18002a6ce  lea     rcx, [rsp+178h+var_138]; this
0x18002a6d3  call    ??0?$WmPaintBufferedPainter@VBufferedPainterOnGlass@GdipUtil@@@GdipUtil@@QEAA@PEAUHWND__@@@Z; GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainterOnGlass>::WmPaintBufferedPainter<GdipUtil::BufferedPainterOnGlass>(HWND__ *)
0x18002a6d8  cmp     [rsp+178h+var_118], 0
0x18002a6dd  jnz     short loc_18002A6FB
0x18002a6df  lea     rcx, [rsp+178h+var_138]; this
0x18002a6e4  call    ?Clear@BufferedPainterOnGlass@GdipUtil@@QEAAXXZ; GdipUtil::BufferedPainterOnGlass::Clear(void)
0x18002a6e9  lea     r8, [rsp+178h+Rect]; struct tagRECT *
0x18002a6ee  mov     rdx, [rsp+178h+var_110]; struct Gdiplus::Graphics *
0x18002a6f3  mov     rcx, rbx; this
0x18002a6f6  call    ?PaintClient@PagePane@@QEAAXPEAVGraphics@Gdiplus@@AEBUtagRECT@@1@Z; PagePane::PaintClient(Gdiplus::Graphics *,tagRECT const &,tagRECT const &)
0x18002a6fb  lea     rcx, [rsp+178h+var_138]
0x18002a700  call    ??1?$WmPaintBufferedPainter@VBufferedPainterOnGlass@GdipUtil@@@GdipUtil@@QEAA@XZ; GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainterOnGlass>::~WmPaintBufferedPainter<GdipUtil::BufferedPainterOnGlass>(void)
0x18002a705  jmp     short loc_18002A77D
0x18002a707  lea     rcx, [rsp+178h+var_138]; this
0x18002a70c  call    ??0?$WmPaintBufferedPainter@VBufferedPainter@GdipUtil@@@GdipUtil@@QEAA@PEAUHWND__@@@Z; GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainter>::WmPaintBufferedPainter<GdipUtil::BufferedPainter>(HWND__ *)
0x18002a711  cmp     [rsp+178h+var_118], 0
0x18002a716  jnz     short loc_18002A72A
0x18002a718  lea     r8, [rsp+178h+Rect]; struct tagRECT *
0x18002a71d  mov     rdx, [rsp+178h+var_110]; struct Gdiplus::Graphics *
0x18002a722  mov     rcx, rbx; this
0x18002a725  call    ?PaintClient@PagePane@@QEAAXPEAVGraphics@Gdiplus@@AEBUtagRECT@@1@Z; PagePane::PaintClient(Gdiplus::Graphics *,tagRECT const &,tagRECT const &)
0x18002a72a  lea     rcx, [rsp+178h+var_138]
0x18002a72f  call    ??1?$WmPaintBufferedPainter@VBufferedPainter@GdipUtil@@@GdipUtil@@QEAA@XZ; GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainter>::~WmPaintBufferedPainter<GdipUtil::BufferedPainter>(void)
0x18002a734  jmp     short loc_18002A77D
0x18002a736  lea     rcx, [rsp+178h+var_88]; this
0x18002a73e  call    ??0WmPaintGraphics@GdipUtil@@QEAA@PEAUHWND__@@@Z; GdipUtil::WmPaintGraphics::WmPaintGraphics(HWND__ *)
0x18002a743  lea     r8, [rsp+178h+Rect]; struct tagRECT *
0x18002a748  lea     rdx, [rsp+178h+var_28]; struct Gdiplus::Graphics *
0x18002a750  mov     rcx, rbx; this
0x18002a753  call    ?PaintClient@PagePane@@QEAAXPEAVGraphics@Gdiplus@@AEBUtagRECT@@1@Z; PagePane::PaintClient(Gdiplus::Graphics *,tagRECT const &,tagRECT const &)
0x18002a758  mov     rcx, [rsp+178h+var_28]
0x18002a760  call    cs:__imp_GdipDeleteGraphics
0x18002a766  lea     rdx, [rsp+178h+Paint]; lpPaint
0x18002a76e  mov     rcx, [rsp+178h+hWnd]; hWnd
0x18002a776  call    cs:__imp_EndPaint
0x18002a77c  nop
0x18002a77d  jmp     short $+2
0x18002a77f  xor     eax, eax
0x18002a781  mov     rcx, [rsp+178h+var_18]
0x18002a789  xor     rcx, rsp; StackCookie
0x18002a78c  call    __security_check_cookie
0x18002a791  mov     rbx, [rsp+178h+arg_8]
0x18002a799  add     rsp, 170h
0x18002a7a0  pop     rdi
0x18002a7a1  retn
```
