# UIControls::ButtonEx::CreateButton(HWND__ *,uint,uint,uint,uint,uint,UIControls::ButtonEx::EImagePlacement,UIControls::ButtonEx::EHoverStyle,int,uint)

- ea: `0x180003d60`
- end: `0x180003f73`
- name: `?CreateButton@ButtonEx@UIControls@@QEAAXPEAUHWND__@@IIIIIW4EImagePlacement@12@W4EHoverStyle@12@HI@Z`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180002e0c`

## callees

- `0x1800026fc`
- `0x1800037d8`
- `0x180003d60`
- `0x180004080`
- `0x1800043a4`
- `0x180004500`
- `0x18000461c`
- `0x1800046b8`
- `0x180004908`
- `0x18002c4ec`
- `0x18002c994`
- `0x180033d0c`
- `0x18003f800`
- `0x18005bcb4`
- `0x18007b000`

## import_xrefs

- `USER32!SetWindowPos` at `0x180003f3e`
- `USER32!SetWindowPos` at `0x180003f3e`
- `USER32!IsWindow` at `0x180003ea7`
- `USER32!IsWindow` at `0x180003ea7`
- `USER32!InvalidateRect` at `0x180003eba`
- `USER32!InvalidateRect` at `0x180003eba`
- `gdiplus!GdipCreateFromHWND` at `0x180003ecf`
- `gdiplus!GdipCreateFromHWND` at `0x180003ecf`
- `gdiplus!GdipDeleteGraphics` at `0x180003f53`
- `gdiplus!GdipDeleteGraphics` at `0x180003f53`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180003e89`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180003e89`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180003f48`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180003f48`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UIControls::ButtonEx::CreateButton(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7)
{
  const unsigned __int16 **v10; // rax
  unsigned int v11; // ecx
  unsigned __int64 v12; // rcx
  UIBase *v13; // rcx
  struct Gdiplus::Bitmap *v14; // rax
  unsigned __int16 Id; // ax
  const unsigned __int16 *v16; // r8
  const unsigned __int16 *v17; // r9
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // edx
  int v21; // eax
  Base *v22; // rcx
  __int16 v24; // [rsp+38h] [rbp-61h]
  __int64 v25; // [rsp+50h] [rbp-49h] BYREF
  struct tagSIZE cy; // [rsp+58h] [rbp-41h] BYREF
  __int64 v27; // [rsp+60h] [rbp-39h] BYREF
  int v28; // [rsp+68h] [rbp-31h]
  _BYTE pExceptionObject[24]; // [rsp+70h] [rbp-29h] BYREF
  __m128i si128; // [rsp+88h] [rbp-11h] BYREF

  if ( a3 )
  {
    v10 = (const unsigned __int16 **)Base::ResourceString::ResourceString((Base::ResourceString *)&v25, a3);
    UIControls::ButtonEx::SetToolTip((UIControls::ButtonEx *)a1, *v10);
    Base::String::~String((Base::String *)&v25);
  }
  *(_DWORD *)(a1 + 524) = a4;
  v11 = a4;
  if ( a5 )
    v11 = a5;
  *(_DWORD *)(a1 + 528) = v11;
  v12 = a4;
  if ( a6 )
    v12 = a6;
  *(_DWORD *)(a1 + 532) = v12;
  *(_BYTE *)(a1 + 536) = UIBase::IsHighContrastOn((UIBase *)v12);
  *(_BYTE *)(a1 + 537) = UIBase::IsForegroundWindowColorDarker(v13);
  if ( a4 )
  {
    Id = UIBase::ThemedImageResource::GetId((UIBase::ThemedImageResource *)(a1 + 524));
    v14 = GdipUtil::GdiplusBitmapFromResourceEx((GdipUtil *)hInstance, (HINSTANCE)Id, v16, v17);
  }
  else
  {
    v14 = 0;
  }
  UIControls::ButtonEx::SetImageInternal(a1, v14, 0, 0);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( !qword_1800A32A0 )
    qword_1800A32A0 = 0;
  v24 = ATL::AtlModuleRegisterWndClassInfoT<ATL::AtlModuleRegisterWndClassInfoParamW>(
          v19,
          v18,
          &qword_1800A3250,
          a1 + 64);
  if ( !ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1409351680,0>>::Create(
          a1,
          a2,
          &si128,
          0,
          1409351680,
          0,
          a7,
          v24) )
  {
    Base::Throw((Base *)0x80004005LL, v20);
    __debugbreak();
  }
  if ( *(_DWORD *)(a1 + 184) != 1 )
  {
    *(_DWORD *)(a1 + 184) = 1;
    if ( IsWindow(*(HWND *)(a1 + 8)) )
      InvalidateRect(*(HWND *)(a1 + 8), 0, 0);
  }
  v25 = 0;
  v21 = GdipCreateFromHWND(a2, &v25);
  v27 = v25;
  v28 = 0;
  if ( v21 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v21);
    throw (Base::GdiException *)pExceptionObject;
  }
  cy = 0;
  UIControls::ButtonEx::Measure((UIControls::ButtonEx *)a1, (const struct Gdiplus::Graphics *)&v27, &cy);
  if ( !SetWindowPos(*(HWND *)(a1 + 8), 0, 0, 0, cy.cx, cy.cy, 0x16u) )
    Base::ThrowLastError(v22);
  return GdipDeleteGraphics(v27);
}

```

## disassembly

```asm
0x180003d60  push    rbp
0x180003d62  push    rbx
0x180003d63  push    rsi
0x180003d64  push    rdi
0x180003d65  push    r14
0x180003d67  lea     rbp, [rsp-7]
0x180003d6c  sub     rsp, 0A0h
0x180003d73  mov     rax, cs:__security_cookie
0x180003d7a  xor     rax, rsp
0x180003d7d  mov     [rbp+27h+var_28], rax
0x180003d81  mov     edi, r9d
0x180003d84  mov     r14, rdx
0x180003d87  mov     rbx, rcx
0x180003d8a  test    r8d, r8d
0x180003d8d  jz      short loc_180003DAF
0x180003d8f  mov     edx, r8d; unsigned int
0x180003d92  lea     rcx, [rbp+27h+var_70]; this
0x180003d96  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x180003d9b  mov     rdx, [rax]; unsigned __int16 *
0x180003d9e  mov     rcx, rbx; this
0x180003da1  call    ?SetToolTip@ButtonEx@UIControls@@QEAAXPEBG@Z; UIControls::ButtonEx::SetToolTip(ushort const *)
0x180003da6  lea     rcx, [rbp+27h+var_70]; this
0x180003daa  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x180003daf  lea     rsi, [rbx+20Ch]
0x180003db6  mov     [rsi], edi
0x180003db8  mov     ecx, edi
0x180003dba  mov     eax, [rbp+27h+arg_20]
0x180003dbd  test    eax, eax
0x180003dbf  cmovnz  ecx, eax
0x180003dc2  mov     [rbx+210h], ecx
0x180003dc8  mov     ecx, edi
0x180003dca  mov     eax, dword ptr [rbp+27h+arg_28]
0x180003dcd  test    eax, eax
0x180003dcf  cmovnz  ecx, eax; this
0x180003dd2  mov     [rbx+214h], ecx
0x180003dd8  call    ?IsHighContrastOn@UIBase@@YA_NXZ; UIBase::IsHighContrastOn(void)
0x180003ddd  mov     [rbx+218h], al
0x180003de3  call    ?IsForegroundWindowColorDarker@UIBase@@YA_NXZ; UIBase::IsForegroundWindowColorDarker(void)
0x180003de8  mov     [rbx+219h], al
0x180003dee  test    edi, edi
0x180003df0  jnz     short loc_180003DF6
0x180003df2  xor     eax, eax
0x180003df4  jmp     short loc_180003E0D
0x180003df6  mov     rcx, rsi; this
0x180003df9  call    ?GetId@ThemedImageResource@UIBase@@QEBAIXZ; UIBase::ThemedImageResource::GetId(void)
0x180003dfe  movzx   edx, ax; HINSTANCE
0x180003e01  mov     rcx, cs:hInstance; this
0x180003e08  call    ?GdiplusBitmapFromResourceEx@GdipUtil@@YAPEAVBitmap@Gdiplus@@PEAUHINSTANCE__@@PEBG1@Z; GdipUtil::GdiplusBitmapFromResourceEx(HINSTANCE__ *,ushort const *,ushort const *)
0x180003e0d  xor     r9d, r9d
0x180003e10  xor     r8d, r8d
0x180003e13  mov     rdx, rax
0x180003e16  mov     rcx, rbx
0x180003e19  call    ?SetImageInternal@ButtonEx@UIControls@@AEAAXPEAVImage@Gdiplus@@W4EImagePlacement@12@H@Z; UIControls::ButtonEx::SetImageInternal(Gdiplus::Image *,UIControls::ButtonEx::EImagePlacement,int)
0x180003e1e  movdqa  xmm0, cs:__xmm@00000001000000010000000000000000
0x180003e26  movdqu  [rbp+27h+var_38], xmm0
0x180003e2b  mov     edi, [rbp+27h+arg_30]
0x180003e2e  cmp     cs:qword_1800A32A0, 0
0x180003e36  jnz     short loc_180003E43
0x180003e38  mov     cs:qword_1800A32A0, 0
0x180003e43  lea     r9, [rbx+40h]
0x180003e47  lea     r8, qword_1800A3250
0x180003e4e  call    ??$AtlModuleRegisterWndClassInfoT@VAtlModuleRegisterWndClassInfoParamW@ATL@@@ATL@@YAGPEAU_ATL_BASE_MODULE70@0@PEAU_ATL_WIN_MODULE70@0@PEAU_ATL_WNDCLASSINFOW@0@PEAP6A_JPEAUHWND__@@I_K_J@ZVAtlModuleRegisterWndClassInfoParamW@0@@Z; ATL::AtlModuleRegisterWndClassInfoT<ATL::AtlModuleRegisterWndClassInfoParamW>(ATL::_ATL_BASE_MODULE70 *,ATL::_ATL_WIN_MODULE70 *,ATL::_ATL_WNDCLASSINFOW *,__int64 (**)(HWND__ *,uint,unsigned __int64,__int64),ATL::AtlModuleRegisterWndClassInfoParamW)
0x180003e53  mov     [rsp+0C0h+var_88], ax
0x180003e58  mov     qword ptr [rsp+0C0h+uFlags], rdi
0x180003e5d  mov     [rsp+0C0h+cy], 0
0x180003e65  mov     [rsp+0C0h+var_A0], 54010000h
0x180003e6d  xor     r9d, r9d
0x180003e70  lea     r8, [rbp+27h+var_38]
0x180003e74  mov     rdx, r14
0x180003e77  mov     rcx, rbx
0x180003e7a  call    ?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FEABAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z; ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1409351680,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)
0x180003e7f  test    rax, rax
0x180003e82  jnz     short loc_180003E90
0x180003e84  mov     ecx, 80004005h
0x180003e89  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180003e8f  int     3; Trap to Debugger
0x180003e90  cmp     dword ptr [rbx+0B8h], 1
0x180003e97  jz      short loc_180003EC0
0x180003e99  mov     dword ptr [rbx+0B8h], 1
0x180003ea3  mov     rcx, [rbx+8]; hWnd
0x180003ea7  call    cs:__imp_IsWindow
0x180003ead  test    eax, eax
0x180003eaf  jz      short loc_180003EC0
0x180003eb1  xor     r8d, r8d; bErase
0x180003eb4  xor     edx, edx; lpRect
0x180003eb6  mov     rcx, [rbx+8]; hWnd
0x180003eba  call    cs:__imp_InvalidateRect
0x180003ec0  mov     [rbp+27h+var_70], 0
0x180003ec8  lea     rdx, [rbp+27h+var_70]
0x180003ecc  mov     rcx, r14
0x180003ecf  call    cs:__imp_GdipCreateFromHWND
0x180003ed5  mov     rcx, [rbp+27h+var_70]
0x180003ed9  mov     [rbp+27h+var_60], rcx
0x180003edd  mov     [rbp+27h+var_58], 0
0x180003ee4  test    eax, eax
0x180003ee6  jz      short loc_180003F04
0x180003ee8  mov     edx, eax; int
0x180003eea  lea     rcx, [rbp+27h+pExceptionObject]; this
0x180003eee  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x180003ef3  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180003efa  lea     rcx, [rbp+27h+pExceptionObject]; pExceptionObject
0x180003efe  call    _CxxThrowException_0
0x180003f04  mov     qword ptr [rbp+27h+var_68.cx], 0
0x180003f0c  lea     r8, [rbp+27h+var_68]; struct tagSIZE *
0x180003f10  lea     rdx, [rbp+27h+var_60]; struct Gdiplus::Graphics *
0x180003f14  mov     rcx, rbx; this
0x180003f17  call    ?Measure@ButtonEx@UIControls@@QEAAXAEBVGraphics@Gdiplus@@AEAUtagSIZE@@@Z; UIControls::ButtonEx::Measure(Gdiplus::Graphics const &,tagSIZE &)
0x180003f1c  mov     eax, [rbp+27h+var_68.cy]
0x180003f1f  mov     edx, [rbp+27h+var_68.cx]
0x180003f22  mov     [rsp+0C0h+uFlags], 16h; uFlags
0x180003f2a  mov     [rsp+0C0h+cy], eax; cy
0x180003f2e  mov     [rsp+0C0h+var_A0], edx; cx
0x180003f32  xor     r9d, r9d; Y
0x180003f35  xor     r8d, r8d; X
0x180003f38  xor     edx, edx; hWndInsertAfter
0x180003f3a  mov     rcx, [rbx+8]; hWnd
0x180003f3e  call    cs:__imp_SetWindowPos
0x180003f44  test    eax, eax
0x180003f46  jnz     short loc_180003F4F
0x180003f48  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x180003f4e  nop
0x180003f4f  mov     rcx, [rbp+27h+var_60]
0x180003f53  call    cs:__imp_GdipDeleteGraphics
0x180003f59  mov     rcx, [rbp+27h+var_28]
0x180003f5d  xor     rcx, rsp; StackCookie
0x180003f60  call    __security_check_cookie
0x180003f65  add     rsp, 0A0h
0x180003f6c  pop     r14
0x180003f6e  pop     rdi
0x180003f6f  pop     rsi
0x180003f70  pop     rbx
0x180003f71  pop     rbp
0x180003f72  retn
```
