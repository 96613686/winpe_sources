# ModularWindow::CommandBar::CreateButton(UIControls::ButtonExTransparentBack<CommandBarButton> *,uint,uint,uint,uint,uint,uint,UIControls::SplitButtonEx::SplitMode,int,bool)

- ea: `0x18002c184`
- end: `0x18002c3c8`
- name: `?CreateButton@CommandBar@ModularWindow@@AEAAXPEAV?$ButtonExTransparentBack@VCommandBarButton@@@UIControls@@IIIIIIW4SplitMode@SplitButtonEx@4@H_N@Z`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180027bd0`

## callees

- `0x1800026fc`
- `0x1800037d8`
- `0x180004080`
- `0x180004500`
- `0x18000461c`
- `0x1800046b8`
- `0x180004908`
- `0x18002c184`
- `0x18002c454`
- `0x18002c994`
- `0x180033d0c`
- `0x18003f800`
- `0x18005bcb4`
- `0x18007b000`

## import_xrefs

- `USER32!SetWindowPos` at `0x18002c38f`
- `USER32!SetWindowPos` at `0x18002c38f`
- `USER32!IsWindow` at `0x18002c2b4`
- `USER32!IsWindow` at `0x18002c2b4`
- `USER32!InvalidateRect` at `0x18002c2c7`
- `USER32!InvalidateRect` at `0x18002c2c7`
- `USER32!SetWindowTextW` at `0x18002c25a`
- `USER32!SetWindowTextW` at `0x18002c25a`
- `gdiplus!GdipCreateFromHWND` at `0x18002c320`
- `gdiplus!GdipCreateFromHWND` at `0x18002c320`
- `gdiplus!GdipDeleteGraphics` at `0x18002c3a4`
- `gdiplus!GdipDeleteGraphics` at `0x18002c3a4`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002c399`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002c399`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ModularWindow::CommandBar::CreateButton(
        UIBase *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        int a10,
        char a11)
{
  UIBase::ThemedImageResource *v15; // r15
  UIBase *v16; // rcx
  struct Gdiplus::Bitmap *v17; // rax
  unsigned __int16 Id; // ax
  const unsigned __int16 *v19; // r8
  const unsigned __int16 *v20; // r9
  int v21; // r9d
  LPCWSTR *v22; // rax
  const unsigned __int16 **v23; // rax
  int v24; // eax
  Base *v25; // rcx
  __int64 v27; // [rsp+40h] [rbp-49h] BYREF
  struct tagSIZE cy; // [rsp+48h] [rbp-41h] BYREF
  __int64 v29; // [rsp+50h] [rbp-39h] BYREF
  int v30; // [rsp+58h] [rbp-31h]
  _BYTE pExceptionObject[24]; // [rsp+60h] [rbp-29h] BYREF
  __m128i si128; // [rsp+78h] [rbp-11h] BYREF

  v15 = (UIBase::ThemedImageResource *)(a2 + 524);
  *(_DWORD *)(a2 + 524) = a5;
  *(_DWORD *)(a2 + 528) = a5;
  *(_DWORD *)(a2 + 532) = a5;
  *(_BYTE *)(a2 + 536) = UIBase::IsHighContrastOn(a1);
  *(_BYTE *)(a2 + 537) = UIBase::IsForegroundWindowColorDarker(v16);
  if ( a5 )
  {
    Id = UIBase::ThemedImageResource::GetId(v15);
    v17 = GdipUtil::GdiplusBitmapFromResourceEx((GdipUtil *)hInstance, (HINSTANCE)Id, v19, v20);
  }
  else
  {
    v17 = 0;
  }
  UIControls::ButtonEx::SetImageInternal(a2, v17, 2, 0);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  ATL::CWindowImpl<UIControls::ButtonEx,ATL::CWindow,ATL::CWinTraits<1409351680,0>>::Create(
    a2,
    *((_QWORD *)a1 + 1),
    (unsigned int)&si128,
    v21,
    1409384448);
  if ( a3 )
  {
    v22 = (LPCWSTR *)Base::ResourceString::ResourceString((Base::ResourceString *)&v27, a3);
    SetWindowTextW(*(HWND *)(a2 + 8), *v22);
    Base::String::~String((Base::String *)&v27);
  }
  if ( a4 )
  {
    v23 = (const unsigned __int16 **)Base::ResourceString::ResourceString((Base::ResourceString *)&v27, a4);
    UIControls::ButtonEx::SetToolTip((UIControls::ButtonEx *)a2, *v23);
    Base::String::~String((Base::String *)&v27);
  }
  *(_DWORD *)(a2 + 604) = a9;
  if ( a9 == 2 )
  {
    if ( *(_DWORD *)(a2 + 612) )
    {
      *(_DWORD *)(a2 + 612) = 0;
      if ( IsWindow(*(HWND *)(a2 + 8)) )
        InvalidateRect(*(HWND *)(a2 + 8), 0, 0);
    }
  }
  else
  {
    *(_DWORD *)(a2 + 612) = -1;
  }
  *(_DWORD *)(a2 + 608) = a10;
  *(_QWORD *)(a2 + 624) = (char *)a1 + 176;
  *(_BYTE *)(a2 + 602) = a11;
  *(_BYTE *)(a2 + 520) = 0;
  *(_DWORD *)(a2 + 616) = 1;
  v27 = 0;
  v24 = GdipCreateFromHWND(*((_QWORD *)a1 + 1), &v27);
  v29 = v27;
  v30 = 0;
  if ( v24 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v24);
    throw (Base::GdiException *)pExceptionObject;
  }
  cy = 0;
  UIControls::ButtonEx::Measure((UIControls::ButtonEx *)a2, (const struct Gdiplus::Graphics *)&v29, &cy);
  if ( !SetWindowPos(*(HWND *)(a2 + 8), 0, 0, 0, cy.cx, cy.cy, 0x16u) )
    Base::ThrowLastError(v25);
  return GdipDeleteGraphics(v29);
}

```

## disassembly

```asm
0x18002c184  push    rbp
0x18002c186  push    rbx
0x18002c187  push    rsi
0x18002c188  push    rdi
0x18002c189  push    r12
0x18002c18b  push    r14
0x18002c18d  push    r15
0x18002c18f  lea     rbp, [rsp-7]
0x18002c194  sub     rsp, 90h
0x18002c19b  mov     rax, cs:__security_cookie
0x18002c1a2  xor     rax, rsp
0x18002c1a5  mov     [rbp+37h+var_38], rax
0x18002c1a9  mov     esi, r9d
0x18002c1ac  mov     r12d, r8d
0x18002c1af  mov     rdi, rdx
0x18002c1b2  mov     r14, rcx
0x18002c1b5  lea     r15, [rdx+20Ch]
0x18002c1bc  mov     ebx, [rbp+37h+arg_20]
0x18002c1bf  mov     [r15], ebx
0x18002c1c2  mov     [rdx+210h], ebx
0x18002c1c8  mov     [rdx+214h], ebx
0x18002c1ce  call    ?IsHighContrastOn@UIBase@@YA_NXZ; UIBase::IsHighContrastOn(void)
0x18002c1d3  mov     [rdi+218h], al
0x18002c1d9  call    ?IsForegroundWindowColorDarker@UIBase@@YA_NXZ; UIBase::IsForegroundWindowColorDarker(void)
0x18002c1de  mov     [rdi+219h], al
0x18002c1e4  test    ebx, ebx
0x18002c1e6  jnz     short loc_18002C1EC
0x18002c1e8  xor     eax, eax
0x18002c1ea  jmp     short loc_18002C203
0x18002c1ec  mov     rcx, r15; this
0x18002c1ef  call    ?GetId@ThemedImageResource@UIBase@@QEBAIXZ; UIBase::ThemedImageResource::GetId(void)
0x18002c1f4  movzx   edx, ax; HINSTANCE
0x18002c1f7  mov     rcx, cs:hInstance; this
0x18002c1fe  call    ?GdiplusBitmapFromResourceEx@GdipUtil@@YAPEAVBitmap@Gdiplus@@PEAUHINSTANCE__@@PEBG1@Z; GdipUtil::GdiplusBitmapFromResourceEx(HINSTANCE__ *,ushort const *,ushort const *)
0x18002c203  xor     r9d, r9d
0x18002c206  lea     r8d, [r9+2]
0x18002c20a  mov     rdx, rax
0x18002c20d  mov     rcx, rdi
0x18002c210  call    ?SetImageInternal@ButtonEx@UIControls@@AEAAXPEAVImage@Gdiplus@@W4EImagePlacement@12@H@Z; UIControls::ButtonEx::SetImageInternal(Gdiplus::Image *,UIControls::ButtonEx::EImagePlacement,int)
0x18002c215  movdqa  xmm0, cs:__xmm@00000001000000010000000000000000
0x18002c21d  movdqu  [rbp+37h+var_48], xmm0
0x18002c222  mov     eax, [rbp+37h+arg_38]
0x18002c225  mov     qword ptr [rsp+0C0h+uFlags], rax
0x18002c22a  mov     [rsp+0C0h+var_A0], 54018000h
0x18002c232  lea     r8, [rbp+37h+var_48]
0x18002c236  mov     rdx, [r14+8]
0x18002c23a  mov     rcx, rdi
0x18002c23d  call    ?Create@?$CWindowImpl@VButtonEx@UIControls@@VCWindow@ATL@@V?$CWinTraits@$0FEABAAAA@$0A@@4@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@PEAX@Z; ATL::CWindowImpl<UIControls::ButtonEx,ATL::CWindow,ATL::CWinTraits<1409351680,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,void *)
0x18002c242  test    r12d, r12d
0x18002c245  jz      short loc_18002C269
0x18002c247  mov     edx, r12d; unsigned int
0x18002c24a  lea     rcx, [rbp+37h+var_80]; this
0x18002c24e  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x18002c253  mov     rdx, [rax]; lpString
0x18002c256  mov     rcx, [rdi+8]; hWnd
0x18002c25a  call    cs:__imp_SetWindowTextW
0x18002c260  lea     rcx, [rbp+37h+var_80]; this
0x18002c264  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002c269  test    esi, esi
0x18002c26b  jz      short loc_18002C28C
0x18002c26d  mov     edx, esi; unsigned int
0x18002c26f  lea     rcx, [rbp+37h+var_80]; this
0x18002c273  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x18002c278  mov     rdx, [rax]; unsigned __int16 *
0x18002c27b  mov     rcx, rdi; this
0x18002c27e  call    ?SetToolTip@ButtonEx@UIControls@@QEAAXPEBG@Z; UIControls::ButtonEx::SetToolTip(ushort const *)
0x18002c283  lea     rcx, [rbp+37h+var_80]; this
0x18002c287  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002c28c  mov     eax, [rbp+37h+arg_40]
0x18002c292  mov     [rdi+25Ch], eax
0x18002c298  cmp     eax, 2
0x18002c29b  jnz     short loc_18002C2CF
0x18002c29d  cmp     dword ptr [rdi+264h], 0
0x18002c2a4  jz      short loc_18002C2D9
0x18002c2a6  mov     dword ptr [rdi+264h], 0
0x18002c2b0  mov     rcx, [rdi+8]; hWnd
0x18002c2b4  call    cs:__imp_IsWindow
0x18002c2ba  test    eax, eax
0x18002c2bc  jz      short loc_18002C2D9
0x18002c2be  xor     r8d, r8d; bErase
0x18002c2c1  xor     edx, edx; lpRect
0x18002c2c3  mov     rcx, [rdi+8]; hWnd
0x18002c2c7  call    cs:__imp_InvalidateRect
0x18002c2cd  jmp     short loc_18002C2D9
0x18002c2cf  mov     dword ptr [rdi+264h], 0FFFFFFFFh
0x18002c2d9  mov     eax, [rbp+37h+arg_48]
0x18002c2df  mov     [rdi+260h], eax
0x18002c2e5  lea     rax, [r14+0B0h]
0x18002c2ec  mov     [rdi+270h], rax
0x18002c2f3  mov     al, [rbp+37h+arg_50]
0x18002c2f9  mov     [rdi+25Ah], al
0x18002c2ff  mov     byte ptr [rdi+208h], 0
0x18002c306  mov     dword ptr [rdi+268h], 1
0x18002c310  mov     [rbp+37h+var_80], 0
0x18002c318  lea     rdx, [rbp+37h+var_80]
0x18002c31c  mov     rcx, [r14+8]
0x18002c320  call    cs:__imp_GdipCreateFromHWND
0x18002c326  mov     rcx, [rbp+37h+var_80]
0x18002c32a  mov     [rbp+37h+var_70], rcx
0x18002c32e  mov     [rbp+37h+var_68], 0
0x18002c335  test    eax, eax
0x18002c337  jz      short loc_18002C355
0x18002c339  mov     edx, eax; int
0x18002c33b  lea     rcx, [rbp+37h+pExceptionObject]; this
0x18002c33f  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x18002c344  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x18002c34b  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x18002c34f  call    _CxxThrowException_0
0x18002c355  mov     qword ptr [rbp+37h+var_78.cx], 0
0x18002c35d  lea     r8, [rbp+37h+var_78]; struct tagSIZE *
0x18002c361  lea     rdx, [rbp+37h+var_70]; struct Gdiplus::Graphics *
0x18002c365  mov     rcx, rdi; this
0x18002c368  call    ?Measure@ButtonEx@UIControls@@QEAAXAEBVGraphics@Gdiplus@@AEAUtagSIZE@@@Z; UIControls::ButtonEx::Measure(Gdiplus::Graphics const &,tagSIZE &)
0x18002c36d  mov     eax, [rbp+37h+var_78.cy]
0x18002c370  mov     edx, [rbp+37h+var_78.cx]
0x18002c373  mov     [rsp+0C0h+uFlags], 16h; uFlags
0x18002c37b  mov     [rsp+0C0h+cy], eax; cy
0x18002c37f  mov     [rsp+0C0h+var_A0], edx; cx
0x18002c383  xor     r9d, r9d; Y
0x18002c386  xor     r8d, r8d; X
0x18002c389  xor     edx, edx; hWndInsertAfter
0x18002c38b  mov     rcx, [rdi+8]; hWnd
0x18002c38f  call    cs:__imp_SetWindowPos
0x18002c395  test    eax, eax
0x18002c397  jnz     short loc_18002C3A0
0x18002c399  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18002c39f  nop
0x18002c3a0  mov     rcx, [rbp+37h+var_70]
0x18002c3a4  call    cs:__imp_GdipDeleteGraphics
0x18002c3aa  mov     rcx, [rbp+37h+var_38]
0x18002c3ae  xor     rcx, rsp; StackCookie
0x18002c3b1  call    __security_check_cookie
0x18002c3b6  add     rsp, 90h
0x18002c3bd  pop     r15
0x18002c3bf  pop     r14
0x18002c3c1  pop     r12
0x18002c3c3  pop     rdi
0x18002c3c4  pop     rsi
0x18002c3c5  pop     rbx
0x18002c3c6  pop     rbp
0x18002c3c7  retn
```
