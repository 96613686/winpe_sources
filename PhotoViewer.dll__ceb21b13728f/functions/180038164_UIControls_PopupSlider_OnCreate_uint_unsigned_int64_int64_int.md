# UIControls::PopupSlider::OnCreate(uint,unsigned __int64,__int64,int &)

- ea: `0x180038164`
- end: `0x1800383fb`
- name: `?OnCreate@PopupSlider@UIControls@@AEAA_JI_K_JAEAH@Z`
- size: `663`
- prototype: `__int64 __fastcall(UIControls::PopupSlider *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180076630`

## callees

- `0x180021ae0`
- `0x18002790c`
- `0x18002b768`
- `0x18002c4ec`
- `0x180038164`
- `0x180038404`
- `0x18003f800`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1800381d4`
- `KERNEL32!MulDiv` at `0x1800381fd`
- `KERNEL32!MulDiv` at `0x1800381d4`
- `KERNEL32!MulDiv` at `0x1800381fd`
- `USER32!AdjustWindowRectEx` at `0x180038346`
- `USER32!AdjustWindowRectEx` at `0x180038346`
- `USER32!MoveWindow` at `0x18003838a`
- `USER32!MoveWindow` at `0x18003838a`
- `USER32!InflateRect` at `0x18003832a`
- `USER32!InflateRect` at `0x18003832a`
- `USER32!SendMessageW` at `0x180038314`
- `USER32!SendMessageW` at `0x1800383ac`
- `USER32!SendMessageW` at `0x1800383c4`
- `USER32!SendMessageW` at `0x180038314`
- `USER32!SendMessageW` at `0x1800383ac`
- `USER32!SendMessageW` at `0x1800383c4`
- `USER32!SetWindowTextW` at `0x180038294`
- `USER32!SetWindowTextW` at `0x180038294`
- `GDI32!GetDeviceCaps` at `0x1800381c1`
- `GDI32!GetDeviceCaps` at `0x1800381f0`
- `GDI32!GetDeviceCaps` at `0x1800381c1`
- `GDI32!GetDeviceCaps` at `0x1800381f0`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180038284`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x1800382fc`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180038350`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180038394`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180038284`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x1800382fc`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180038350`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x180038394`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UIControls::PopupSlider::OnCreate(UIControls::PopupSlider *this)
{
  int DeviceCaps; // eax
  int v3; // eax
  HWND Window; // rax
  Base *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  HWND v8; // r14
  unsigned __int16 v9; // ax
  Base *v10; // rcx
  Base *v11; // rcx
  Base *v12; // rcx
  __int64 result; // rax
  ULONG_PTR v14; // [rsp+58h] [rbp-70h]
  HDC hdc[2]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v16[16]; // [rsp+70h] [rbp-58h] BYREF
  struct tagRECT rc; // [rsp+80h] [rbp-48h] BYREF

  WTL::CClientDC::CClientDC((WTL::CClientDC *)hdc, *((HWND *)this + 1));
  *(_QWORD *)&rc.right = 0;
  rc.left = 2;
  rc.top = 2;
  DeviceCaps = GetDeviceCaps(hdc[0], 88);
  rc.right = rc.left + MulDiv(24, DeviceCaps, 96);
  v3 = GetDeviceCaps(hdc[0], 90);
  rc.bottom = rc.top + MulDiv(96, v3, 96);
  Window = (HWND)IsolationAwareCreateWindowExW(
                   0,
                   L"STATIC",
                   0,
                   0x40000000u,
                   ATL::CWindow::rcDefault,
                   dword_1800A3904,
                   dword_1800A3908 - ATL::CWindow::rcDefault,
                   dword_1800A390C - dword_1800A3904,
                   *((HWND *)this + 1),
                   0,
                   hModule,
                   v14);
  try
  {
    *((_QWORD *)this + 19) = Window;
    if ( !Window )
      Base::ThrowLastError(v5);
    SetWindowTextW(Window, *((LPCWSTR *)this + 23));
    v8 = (HWND)*((_QWORD *)this + 1);
    if ( !qword_1800A33A0 )
      qword_1800A33A0 = (__int64)L"msctls_trackbar32";
    v9 = ATL::AtlModuleRegisterWndClassInfoT<ATL::AtlModuleRegisterWndClassInfoParamW>(
           v7,
           v6,
           &`ATL::CWindowImpl<UIControlsPrivate::PopupSliderTrackBar,WTL::CTrackBarCtrlT<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>::GetWndClassInfo'::`2'::wc,
           (char *)this + 136);
    if ( !ATL::CWindowImplBaseT<WTL::CTrackBarCtrlT<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>::Create(
            (HMENU)this + 18,
            v8,
            &rc.left,
            0,
            0x50000612u,
            0,
            0,
            v9) )
      Base::ThrowLastError(v10);
    SendMessageW(*((HWND *)this + 10), 0x128u, 0x10001u, 0);
    InflateRect(&rc, 2, 2);
    if ( !AdjustWindowRectEx(&rc, 0x800000u, 0, 0x80u) )
      Base::ThrowLastError(v11);
    if ( !MoveWindow(*((HWND *)this + 1), rc.left, rc.top, rc.right - rc.left, rc.bottom - rc.top, 1) )
      Base::ThrowLastError(v12);
    SendMessageW(*((HWND *)this + 10), 0x417u, 0, 5);
    SendMessageW(*((HWND *)this + 10), 0x415u, 0, 25);
    WTL::CClientDC::~CClientDC((WTL::CClientDC *)hdc);
    result = 0;
  }
  catch ( Base::Exception v16 )
  {
    Base::Exception::~Exception((Base::Exception *)v16);
    return -1;
  }
  return result;
}

```

## disassembly

```asm
0x180038164  push    rbx
0x180038166  push    rsi
0x180038167  push    rdi
0x180038168  push    r14
0x18003816a  sub     rsp, 0A8h
0x180038171  mov     rax, cs:__security_cookie
0x180038178  xor     rax, rsp
0x18003817b  mov     [rsp+0C8h+var_38], rax
0x180038183  mov     rdi, rcx
0x180038186  mov     rdx, [rcx+8]; HWND
0x18003818a  lea     rcx, [rsp+0C8h+hdc]; this
0x18003818f  call    ??0CClientDC@WTL@@QEAA@PEAUHWND__@@@Z; WTL::CClientDC::CClientDC(HWND__ *)
0x180038194  nop
0x180038195  mov     qword ptr [rsp+0C8h+rc.right], 0
0x1800381a1  mov     [rsp+0C8h+rc.left], 2
0x1800381ac  mov     [rsp+0C8h+rc.top], 2
0x1800381b7  mov     edx, 58h ; 'X'; index
0x1800381bc  mov     rcx, [rsp+0C8h+hdc]; hdc
0x1800381c1  call    cs:__imp_GetDeviceCaps
0x1800381c7  mov     ebx, 60h ; '`'
0x1800381cc  mov     r8d, ebx; nDenominator
0x1800381cf  mov     edx, eax; nNumerator
0x1800381d1  lea     ecx, [rbx-48h]; nNumber
0x1800381d4  call    cs:__imp_MulDiv
0x1800381da  add     eax, [rsp+0C8h+rc.left]
0x1800381e1  mov     [rsp+0C8h+rc.right], eax
0x1800381e8  lea     edx, [rbx-6]; index
0x1800381eb  mov     rcx, [rsp+0C8h+hdc]; hdc
0x1800381f0  call    cs:__imp_GetDeviceCaps
0x1800381f6  mov     r8d, ebx; nDenominator
0x1800381f9  mov     edx, eax; nNumerator
0x1800381fb  mov     ecx, ebx; nNumber
0x1800381fd  call    cs:__imp_MulDiv
0x180038203  add     eax, [rsp+0C8h+rc.top]
0x18003820a  mov     [rsp+0C8h+rc.bottom], eax
0x180038211  mov     rax, cs:hModule
0x180038218  mov     r8d, cs:dword_1800A3904
0x18003821f  mov     r9d, cs:?rcDefault@CWindow@ATL@@2UtagRECT@@A; tagRECT ATL::CWindow::rcDefault
0x180038226  mov     edx, cs:dword_1800A390C
0x18003822c  sub     edx, r8d
0x18003822f  mov     ecx, cs:dword_1800A3908
0x180038235  sub     ecx, r9d
0x180038238  mov     [rsp+0C8h+var_78], rax; HINSTANCE
0x18003823d  mov     [rsp+0C8h+var_80], 0; HMENU
0x180038246  mov     rax, [rdi+8]
0x18003824a  mov     [rsp+0C8h+var_88], rax; HWND
0x18003824f  mov     [rsp+0C8h+var_90], edx; int
0x180038253  mov     [rsp+0C8h+var_98], ecx; int
0x180038257  mov     [rsp+0C8h+bRepaint], r8d; int
0x18003825c  mov     [rsp+0C8h+nHeight], r9d; int
0x180038261  mov     r9d, 40000000h; dwStyle
0x180038267  xor     r8d, r8d; lpWindowName
0x18003826a  lea     rdx, aStatic; "STATIC"
0x180038271  xor     ecx, ecx; dwExStyle
0x180038273  call    IsolationAwareCreateWindowExW
0x180038278  mov     [rdi+98h], rax
0x18003827f  test    rax, rax
0x180038282  jnz     short loc_18003828A
0x180038284  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18003828a  mov     rdx, [rdi+0B8h]; lpString
0x180038291  mov     rcx, rax; hWnd
0x180038294  call    cs:__imp_SetWindowTextW
0x18003829a  xor     ebx, ebx
0x18003829c  mov     r14, [rdi+8]
0x1800382a0  cmp     cs:qword_1800A33A0, rbx
0x1800382a7  jnz     short loc_1800382B7
0x1800382a9  lea     rax, aMsctlsTrackbar; "msctls_trackbar32"
0x1800382b0  mov     cs:qword_1800A33A0, rax
0x1800382b7  lea     r9, [rdi+88h]
0x1800382be  lea     r8, ?wc@?1??GetWndClassInfo@?$CWindowImpl@VPopupSliderTrackBar@UIControlsPrivate@@V?$CTrackBarCtrlT@VCWindow@ATL@@@WTL@@V?$CWinTraits@$0FGAAAAAA@$0A@@ATL@@@ATL@@SAAEAU_ATL_WNDCLASSINFOW@3@XZ@4U43@A; ATL::_ATL_WNDCLASSINFOW `ATL::CWindowImpl<UIControlsPrivate::PopupSliderTrackBar,WTL::CTrackBarCtrlT<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>::GetWndClassInfo(void)'::`2'::wc
0x1800382c5  call    ??$AtlModuleRegisterWndClassInfoT@VAtlModuleRegisterWndClassInfoParamW@ATL@@@ATL@@YAGPEAU_ATL_BASE_MODULE70@0@PEAU_ATL_WIN_MODULE70@0@PEAU_ATL_WNDCLASSINFOW@0@PEAP6A_JPEAUHWND__@@I_K_J@ZVAtlModuleRegisterWndClassInfoParamW@0@@Z; ATL::AtlModuleRegisterWndClassInfoT<ATL::AtlModuleRegisterWndClassInfoParamW>(ATL::_ATL_BASE_MODULE70 *,ATL::_ATL_WIN_MODULE70 *,ATL::_ATL_WNDCLASSINFOW *,__int64 (**)(HWND__ *,uint,unsigned __int64,__int64),ATL::AtlModuleRegisterWndClassInfoParamW)
0x1800382ca  mov     word ptr [rsp+0C8h+var_90], ax
0x1800382cf  mov     qword ptr [rsp+0C8h+var_98], rbx
0x1800382d4  mov     [rsp+0C8h+bRepaint], ebx
0x1800382d8  mov     [rsp+0C8h+nHeight], 50000612h
0x1800382e0  xor     r9d, r9d
0x1800382e3  lea     r8, [rsp+0C8h+rc]
0x1800382eb  mov     rdx, r14
0x1800382ee  lea     rcx, [rdi+48h]
0x1800382f2  call    ?Create@?$CWindowImplBaseT@V?$CTrackBarCtrlT@VCWindow@ATL@@@WTL@@V?$CWinTraits@$0FGAAAAAA@$0A@@ATL@@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z; ATL::CWindowImplBaseT<WTL::CTrackBarCtrlT<ATL::CWindow>,ATL::CWinTraits<1442840576,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)
0x1800382f7  test    rax, rax
0x1800382fa  jnz     short loc_180038302
0x1800382fc  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x180038302  xor     r9d, r9d; lParam
0x180038305  mov     edx, 128h; Msg
0x18003830a  mov     r8d, 10001h; wParam
0x180038310  mov     rcx, [rdi+50h]; hWnd
0x180038314  call    cs:__imp_SendMessageW
0x18003831a  mov     edx, 2; dx
0x18003831f  mov     r8d, edx; dy
0x180038322  lea     rcx, [rsp+0C8h+rc]; lprc
0x18003832a  call    cs:__imp_InflateRect
0x180038330  mov     r9d, 80h; dwExStyle
0x180038336  xor     r8d, r8d; bMenu
0x180038339  mov     edx, 800000h; dwStyle
0x18003833e  lea     rcx, [rsp+0C8h+rc]; lpRect
0x180038346  call    cs:__imp_AdjustWindowRectEx
0x18003834c  test    eax, eax
0x18003834e  jnz     short loc_180038356
0x180038350  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x180038356  mov     eax, [rsp+0C8h+rc.bottom]
0x18003835d  mov     r8d, [rsp+0C8h+rc.top]; Y
0x180038365  sub     eax, r8d
0x180038368  mov     r9d, [rsp+0C8h+rc.right]
0x180038370  mov     edx, [rsp+0C8h+rc.left]; X
0x180038377  sub     r9d, edx; nWidth
0x18003837a  mov     [rsp+0C8h+bRepaint], 1; bRepaint
0x180038382  mov     [rsp+0C8h+nHeight], eax; nHeight
0x180038386  mov     rcx, [rdi+8]; hWnd
0x18003838a  call    cs:__imp_MoveWindow
0x180038390  test    eax, eax
0x180038392  jnz     short loc_18003839A
0x180038394  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18003839a  mov     r9d, 5; lParam
0x1800383a0  xor     r8d, r8d; wParam
0x1800383a3  mov     edx, 417h; Msg
0x1800383a8  mov     rcx, [rdi+50h]; hWnd
0x1800383ac  call    cs:__imp_SendMessageW
0x1800383b2  mov     r9d, 19h; lParam
0x1800383b8  xor     r8d, r8d; wParam
0x1800383bb  mov     edx, 415h; Msg
0x1800383c0  mov     rcx, [rdi+50h]; hWnd
0x1800383c4  call    cs:__imp_SendMessageW
0x1800383ca  nop
0x1800383cb  lea     rcx, [rsp+0C8h+hdc]; this
0x1800383d0  call    ??1CClientDC@WTL@@QEAA@XZ; WTL::CClientDC::~CClientDC(void)
0x1800383d5  nop
0x1800383d6  xor     eax, eax
0x1800383d8  jmp     short loc_1800383DE
0x1800383da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800383de  mov     rcx, [rsp+0C8h+var_38]
0x1800383e6  xor     rcx, rsp; StackCookie
0x1800383e9  call    __security_check_cookie
0x1800383ee  add     rsp, 0A8h
0x1800383f5  pop     r14
0x1800383f7  pop     rdi
0x1800383f8  pop     rsi
0x1800383f9  pop     rbx
0x1800383fa  retn
```
