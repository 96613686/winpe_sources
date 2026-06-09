# PagePane::CreateButton(UIControls::BitMapOnlyButtonTransparentBack *,uint,uint,uint,uint,uint)

- ea: `0x180071974`
- end: `0x180071ac8`
- name: `?CreateButton@PagePane@@AEAAXPEAVBitMapOnlyButtonTransparentBack@UIControls@@IIIII@Z`
- size: `340`
- prototype: `void(PagePane *__hidden this, struct UIControls::BitMapOnlyButtonTransparentBack *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180035fc4`

## callees

- `0x1800037d8`
- `0x180004080`
- `0x180004748`
- `0x180004908`
- `0x18002c454`
- `0x18002c8f8`
- `0x180032154`
- `0x180033d0c`
- `0x180037cf8`
- `0x18003f800`
- `0x18005bcb4`
- `0x180071974`
- `0x18007b000`

## import_xrefs

- `USER32!SetWindowPos` at `0x180071a8e`
- `USER32!SetWindowPos` at `0x180071a8e`
- `gdiplus!GdipDeleteGraphics` at `0x180071aa3`
- `gdiplus!GdipDeleteGraphics` at `0x180071aa3`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180071a98`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180071a98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PagePane::CreateButton(
        PagePane *this,
        HWND *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  const unsigned __int16 **v9; // rax
  int v10; // r9d
  int v11; // r8d
  int v12; // edx
  Base *v13; // rcx
  struct tagSIZE cy; // [rsp+40h] [rbp-21h] BYREF
  __int64 v15; // [rsp+48h] [rbp-19h] BYREF
  int v16; // [rsp+50h] [rbp-11h]
  _BYTE pExceptionObject[24]; // [rsp+58h] [rbp-9h] BYREF
  __m128i si128; // [rsp+70h] [rbp+Fh] BYREF

  v9 = (const unsigned __int16 **)Base::ResourceString::ResourceString((Base::ResourceString *)&cy, a3);
  UIControls::ButtonEx::SetToolTip((UIControls::ButtonEx *)a2, *v9);
  Base::String::~String((Base::String *)&cy);
  UIControls::ButtonEx::SetImage(a2, a4, a5, a6, 0, 0);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  ATL::CWindowImpl<UIControls::ButtonEx,ATL::CWindow,ATL::CWinTraits<1409351680,0>>::Create(
    (_DWORD)a2,
    *((_QWORD *)this + 1),
    (unsigned int)&si128,
    v10,
    0);
  UIControls::ButtonEx::ChangeHoverStyle(a2);
  UIControls::ButtonEx::ChangeImageMirroring(a2);
  Gdiplus::Graphics::Graphics((Gdiplus::Graphics *)&v15, *((HWND *)this + 1), v11);
  v12 = v16;
  v16 = 0;
  if ( v12 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v12);
    throw (Base::GdiException *)pExceptionObject;
  }
  cy = 0;
  UIControls::ButtonEx::Measure((UIControls::ButtonEx *)a2, (const struct Gdiplus::Graphics *)&v15, &cy);
  if ( !SetWindowPos(a2[1], 0, 0, 0, cy.cx, cy.cy, 0x16u) )
    Base::ThrowLastError(v13);
  GdipDeleteGraphics(v15);
}

```

## disassembly

```asm
0x180071974  mov     [rsp-8+arg_18], rbx
0x180071979  push    rbp
0x18007197a  push    rsi
0x18007197b  push    rdi
0x18007197c  lea     rbp, [rsp-2Fh]
0x180071981  sub     rsp, 90h
0x180071988  mov     rax, cs:__security_cookie
0x18007198f  xor     rax, rsp
0x180071992  mov     [rbp+3Fh+var_20], rax
0x180071996  mov     ebx, r9d
0x180071999  mov     rsi, rdx
0x18007199c  mov     rdi, rcx
0x18007199f  mov     edx, r8d; unsigned int
0x1800719a2  lea     rcx, [rbp+3Fh+var_60]; this
0x1800719a6  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x1800719ab  mov     rdx, [rax]; unsigned __int16 *
0x1800719ae  mov     rcx, rsi; this
0x1800719b1  call    ?SetToolTip@ButtonEx@UIControls@@QEAAXPEBG@Z; UIControls::ButtonEx::SetToolTip(ushort const *)
0x1800719b6  lea     rcx, [rbp+3Fh+var_60]; this
0x1800719ba  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x1800719bf  mov     [rsp+0A0h+cy], 0
0x1800719c7  mov     [rsp+0A0h+var_80], 0
0x1800719cf  mov     r9d, [rbp+3Fh+arg_28]
0x1800719d3  mov     r8d, [rbp+3Fh+arg_20]
0x1800719d7  mov     edx, ebx
0x1800719d9  mov     rcx, rsi
0x1800719dc  call    ?SetImage@ButtonEx@UIControls@@QEAAXIIIW4EImagePlacement@12@H@Z; UIControls::ButtonEx::SetImage(uint,uint,uint,UIControls::ButtonEx::EImagePlacement,int)
0x1800719e1  movdqa  xmm0, cs:__xmm@00000001000000010000000000000000
0x1800719e9  movdqu  [rbp+3Fh+var_30], xmm0
0x1800719ee  mov     eax, [rbp+3Fh+arg_30]
0x1800719f1  mov     qword ptr [rsp+0A0h+uFlags], rax
0x1800719f6  mov     [rsp+0A0h+var_80], 0
0x1800719fe  lea     r8, [rbp+3Fh+var_30]
0x180071a02  mov     rdx, [rdi+8]
0x180071a06  mov     rcx, rsi
0x180071a09  call    ?Create@?$CWindowImpl@VButtonEx@UIControls@@VCWindow@ATL@@V?$CWinTraits@$0FEABAAAA@$0A@@4@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@PEAX@Z; ATL::CWindowImpl<UIControls::ButtonEx,ATL::CWindow,ATL::CWinTraits<1409351680,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,void *)
0x180071a0e  mov     rcx, rsi
0x180071a11  call    ?ChangeHoverStyle@ButtonEx@UIControls@@QEAAXW4EHoverStyle@12@@Z; UIControls::ButtonEx::ChangeHoverStyle(UIControls::ButtonEx::EHoverStyle)
0x180071a16  mov     rcx, rsi
0x180071a19  call    ?ChangeImageMirroring@ButtonEx@UIControls@@QEAAXW4EImageMirroring@12@@Z; UIControls::ButtonEx::ChangeImageMirroring(UIControls::ButtonEx::EImageMirroring)
0x180071a1e  mov     rdx, [rdi+8]; HWND
0x180071a22  lea     rcx, [rbp+3Fh+var_58]; this
0x180071a26  call    ??0Graphics@Gdiplus@@QEAA@PEAUHWND__@@H@Z; Gdiplus::Graphics::Graphics(HWND__ *,int)
0x180071a2b  nop
0x180071a2c  mov     edx, [rbp+3Fh+var_50]; int
0x180071a2f  mov     [rbp+3Fh+var_50], 0
0x180071a36  test    edx, edx
0x180071a38  jz      short loc_180071A54
0x180071a3a  lea     rcx, [rbp+3Fh+pExceptionObject]; this
0x180071a3e  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180071a43  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180071a4a  lea     rcx, [rbp+3Fh+pExceptionObject]; pExceptionObject
0x180071a4e  call    _CxxThrowException_0
0x180071a54  mov     qword ptr [rbp+3Fh+var_60.cx], 0
0x180071a5c  lea     r8, [rbp+3Fh+var_60]; struct tagSIZE *
0x180071a60  lea     rdx, [rbp+3Fh+var_58]; struct Gdiplus::Graphics *
0x180071a64  mov     rcx, rsi; this
0x180071a67  call    ?Measure@ButtonEx@UIControls@@QEAAXAEBVGraphics@Gdiplus@@AEAUtagSIZE@@@Z; UIControls::ButtonEx::Measure(Gdiplus::Graphics const &,tagSIZE &)
0x180071a6c  mov     eax, [rbp+3Fh+var_60.cy]
0x180071a6f  mov     edx, [rbp+3Fh+var_60.cx]
0x180071a72  mov     [rsp+0A0h+uFlags], 16h; uFlags
0x180071a7a  mov     [rsp+0A0h+cy], eax; cy
0x180071a7e  mov     [rsp+0A0h+var_80], edx; cx
0x180071a82  xor     r9d, r9d; Y
0x180071a85  xor     r8d, r8d; X
0x180071a88  xor     edx, edx; hWndInsertAfter
0x180071a8a  mov     rcx, [rsi+8]; hWnd
0x180071a8e  call    cs:__imp_SetWindowPos
0x180071a94  test    eax, eax
0x180071a96  jnz     short loc_180071A9F
0x180071a98  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x180071a9e  nop
0x180071a9f  mov     rcx, [rbp+3Fh+var_58]
0x180071aa3  call    cs:__imp_GdipDeleteGraphics
0x180071aa9  mov     rcx, [rbp+3Fh+var_20]
0x180071aad  xor     rcx, rsp; StackCookie
0x180071ab0  call    __security_check_cookie
0x180071ab5  mov     rbx, [rsp+0A0h+arg_18]
0x180071abd  add     rsp, 90h
0x180071ac4  pop     rdi
0x180071ac5  pop     rsi
0x180071ac6  pop     rbp
0x180071ac7  retn
```
