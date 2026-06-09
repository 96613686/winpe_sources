# UIControls::ButtonEx::CaptureClient(void)

- ea: `0x180037638`
- end: `0x180037769`
- name: `?CaptureClient@ButtonEx@UIControls@@AEAAPEAVBitmap@Gdiplus@@XZ`
- size: `305`
- prototype: `struct Gdiplus::Bitmap *__fastcall(UIControls::ButtonEx *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800260b4`
- `0x180074d9c`

## callees

- `0x1800035f8`
- `0x180024220`
- `0x1800261a8`
- `0x180026a18`
- `0x180037638`
- `0x18003f800`
- `0x18005bcb4`
- `0x18007b000`

## import_xrefs

- `USER32!IsWindow` at `0x180037658`
- `USER32!IsWindow` at `0x180037658`
- `USER32!GetClientRect` at `0x180037677`
- `USER32!GetClientRect` at `0x180037677`
- `gdiplus!GdipDeleteGraphics` at `0x180037721`
- `gdiplus!GdipDeleteGraphics` at `0x180037721`
- `gdiplus!GdipAlloc` at `0x180037698`
- `gdiplus!GdipAlloc` at `0x180037698`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct Gdiplus::Bitmap *__fastcall UIControls::ButtonEx::CaptureClient(HWND *this)
{
  Gdiplus::Bitmap *v2; // rax
  struct Image *v3; // rbx
  const struct tagRECT *v4; // r9
  int v5; // edx
  struct Gdiplus::Bitmap *result; // rax
  Gdiplus::Bitmap *v7; // [rsp+20h] [rbp-58h] BYREF
  __int64 v8; // [rsp+28h] [rbp-50h] BYREF
  int v9; // [rsp+30h] [rbp-48h]
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-40h] BYREF
  struct tagRECT Rect; // [rsp+50h] [rbp-28h] BYREF

  if ( !IsWindow(this[1]) )
    return 0;
  Rect = 0;
  GetClientRect(this[1], &Rect);
  if ( Rect.right <= 0 || Rect.bottom <= 0 )
    return 0;
  v2 = (Gdiplus::Bitmap *)GdipAlloc(24);
  v7 = v2;
  if ( v2 )
    v3 = (struct Image *)Gdiplus::Bitmap::Bitmap(v2, Rect.right, Rect.bottom, 2498570);
  else
    v3 = 0;
  v7 = v3;
  if ( !v3 )
  {
    Base::Ptr<Gdiplus::TextureBrush>::~Ptr<Gdiplus::TextureBrush>(&v7);
    return 0;
  }
  Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)&v8, v3);
  try
  {
    v5 = v9;
    v9 = 0;
    if ( v5 )
    {
      Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v5);
      throw (Base::GdiException *)pExceptionObject;
    }
    UIControls::ButtonEx::PaintClient((UIControls::ButtonEx *)this, (struct Gdiplus::Graphics *)&v8, &Rect, v4);
    GdipDeleteGraphics(v8);
    v7 = 0;
    Base::Ptr<Gdiplus::TextureBrush>::~Ptr<Gdiplus::TextureBrush>(&v7);
    result = v3;
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180037638  mov     [rsp+arg_8], rbx
0x18003763d  push    rdi
0x18003763e  sub     rsp, 70h
0x180037642  mov     rax, cs:__security_cookie
0x180037649  xor     rax, rsp
0x18003764c  mov     [rsp+78h+var_18], rax
0x180037651  mov     rdi, rcx
0x180037654  mov     rcx, [rcx+8]; hWnd
0x180037658  call    cs:__imp_IsWindow
0x18003765e  test    eax, eax
0x180037660  jz      loc_18003774A
0x180037666  xorps   xmm0, xmm0
0x180037669  movups  xmmword ptr [rsp+78h+Rect.left], xmm0
0x18003766e  lea     rdx, [rsp+78h+Rect]; lpRect
0x180037673  mov     rcx, [rdi+8]; hWnd
0x180037677  call    cs:__imp_GetClientRect
0x18003767d  cmp     [rsp+78h+Rect.right], 0
0x180037682  jle     loc_18003774A
0x180037688  cmp     [rsp+78h+Rect.bottom], 0
0x18003768d  jle     loc_18003774A
0x180037693  mov     ecx, 18h
0x180037698  call    cs:__imp_GdipAlloc
0x18003769e  mov     [rsp+78h+var_58], rax
0x1800376a3  test    rax, rax
0x1800376a6  jz      short loc_1800376C4
0x1800376a8  mov     r9d, 26200Ah; int
0x1800376ae  mov     r8d, [rsp+78h+Rect.bottom]; int
0x1800376b3  mov     edx, [rsp+78h+Rect.right]; int
0x1800376b7  mov     rcx, rax; this
0x1800376ba  call    ??0Bitmap@Gdiplus@@QEAA@HHH@Z; Gdiplus::Bitmap::Bitmap(int,int,int)
0x1800376bf  mov     rbx, rax
0x1800376c2  jmp     short loc_1800376C6
0x1800376c4  xor     ebx, ebx
0x1800376c6  mov     [rsp+78h+var_58], rbx
0x1800376cb  test    rbx, rbx
0x1800376ce  jz      short loc_18003773F
0x1800376d0  mov     rdx, rbx; struct Image *
0x1800376d3  lea     rcx, [rsp+78h+var_50]; this
0x1800376d8  call    ??0Graphics@Gdiplus@@QEAA@PEAVImage@1@@Z; Gdiplus::Graphics::Graphics(Gdiplus::Image *)
0x1800376dd  nop
0x1800376de  mov     edx, [rsp+78h+var_48]; int
0x1800376e2  mov     [rsp+78h+var_48], 0
0x1800376ea  test    edx, edx
0x1800376ec  jz      short loc_180037709
0x1800376ee  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800376f3  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x1800376f8  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x1800376ff  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180037704  call    _CxxThrowException_0
0x180037709  lea     r8, [rsp+78h+Rect]; struct tagRECT *
0x18003770e  lea     rdx, [rsp+78h+var_50]; struct Gdiplus::Graphics *
0x180037713  mov     rcx, rdi; this
0x180037716  call    ?PaintClient@ButtonEx@UIControls@@QEAAXPEAVGraphics@Gdiplus@@AEBUtagRECT@@1@Z; UIControls::ButtonEx::PaintClient(Gdiplus::Graphics *,tagRECT const &,tagRECT const &)
0x18003771b  nop
0x18003771c  mov     rcx, [rsp+78h+var_50]
0x180037721  call    cs:__imp_GdipDeleteGraphics
0x180037727  mov     [rsp+78h+var_58], 0
0x180037730  lea     rcx, [rsp+78h+var_58]
0x180037735  call    ??1?$Ptr@VTextureBrush@Gdiplus@@@Base@@QEAA@XZ; Base::Ptr<Gdiplus::TextureBrush>::~Ptr<Gdiplus::TextureBrush>(void)
0x18003773a  mov     rax, rbx
0x18003773d  jmp     short loc_18003774E
0x18003773f  lea     rcx, [rsp+78h+var_58]
0x180037744  call    ??1?$Ptr@VTextureBrush@Gdiplus@@@Base@@QEAA@XZ; Base::Ptr<Gdiplus::TextureBrush>::~Ptr<Gdiplus::TextureBrush>(void)
0x180037749  nop
0x18003774a  jmp     short $+2
0x18003774c  xor     eax, eax
0x18003774e  mov     rcx, [rsp+78h+var_18]
0x180037753  xor     rcx, rsp; StackCookie
0x180037756  call    __security_check_cookie
0x18003775b  mov     rbx, [rsp+78h+arg_8]
0x180037763  add     rsp, 70h
0x180037767  pop     rdi
0x180037768  retn
```
