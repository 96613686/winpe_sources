# Art::FStartScreenCapture(Ofc::TWeakPtr<Art::UserInterface> const &,Art::ScreenCaptureSetting const &)

- ea: `0x180520d60`
- end: `0x1805214ac`
- name: `?FStartScreenCapture@Art@@YA_NAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@AEBUScreenCaptureSetting@1@@Z`
- size: `1868`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180520d38`

## callees

- `0x18000f840`
- `0x180028b00`
- `0x18002a690`
- `0x1800ef520`
- `0x18011eb20`
- `0x1801281f0`
- `0x180276a71`
- `0x1802770a0`
- `0x180279030`
- `0x180279050`
- `0x1803a6b10`
- `0x1803a77c0`
- `0x1804c0cd0`
- `0x180520d60`
- `0x1805214b0`
- `0x1805215d8`
- `0x1805216a0`
- `0x180521890`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806d19bc`
- `0x1807720f0`
- `0x180947f98`
- `0x1809aca74`
- `0x1809acb2c`
- `0x1809acec0`
- `0x1809acee8`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x180521221`
- `KERNEL32!GetTickCount64` at `0x180521253`
- `KERNEL32!GetTickCount64` at `0x1805212bf`
- `KERNEL32!GetTickCount64` at `0x180521305`
- `KERNEL32!GetTickCount64` at `0x180521221`
- `KERNEL32!GetTickCount64` at `0x180521253`
- `KERNEL32!GetTickCount64` at `0x1805212bf`
- `KERNEL32!GetTickCount64` at `0x180521305`
- `KERNEL32!Sleep` at `0x180521206`
- `KERNEL32!Sleep` at `0x180521206`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x180520e3d`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x180520e3d`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18052137e`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18052137e`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18052136b`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18052136b`
- `GDI32!CreateSolidBrush` at `0x180520fd0`
- `GDI32!CreateSolidBrush` at `0x180520fd0`
- `GDI32!BitBlt` at `0x180520f6b`
- `GDI32!BitBlt` at `0x180520f6b`
- `GDI32!SelectObject` at `0x180520f21`
- `GDI32!SelectObject` at `0x180520fa8`
- `GDI32!SelectObject` at `0x180520f21`
- `GDI32!SelectObject` at `0x180520fa8`
- `GDI32!DeleteObject` at `0x180520ff0`
- `GDI32!DeleteObject` at `0x180520ff0`
- `GDI32!CreateCompatibleDC` at `0x180520ef5`
- `GDI32!CreateCompatibleDC` at `0x180520f78`
- `GDI32!CreateCompatibleDC` at `0x180520ef5`
- `GDI32!CreateCompatibleDC` at `0x180520f78`
- `GDI32!CreateCompatibleBitmap` at `0x180520f0a`
- `GDI32!CreateCompatibleBitmap` at `0x180520f91`
- `GDI32!CreateCompatibleBitmap` at `0x180520f0a`
- `GDI32!CreateCompatibleBitmap` at `0x180520f91`
- `MSIMG32!AlphaBlend` at `0x18052104d`
- `MSIMG32!AlphaBlend` at `0x18052104d`
- `USER32!FillRect` at `0x180520fe7`
- `USER32!FillRect` at `0x180520fe7`
- `USER32!RedrawWindow` at `0x180520e08`
- `USER32!RedrawWindow` at `0x180521118`
- `USER32!RedrawWindow` at `0x180520e08`
- `USER32!RedrawWindow` at `0x180521118`
- `USER32!SetForegroundWindow` at `0x1805210bc`
- `USER32!SetForegroundWindow` at `0x1805210bc`
- `USER32!SetRectEmpty` at `0x1805210f9`
- `USER32!SetRectEmpty` at `0x1805210f9`
- `USER32!SetRect` at `0x180520e9e`
- `USER32!SetRect` at `0x180520fc5`
- `USER32!SetRect` at `0x180520e9e`
- `USER32!SetRect` at `0x180520fc5`
- `USER32!EnumDisplayMonitors` at `0x180520edd`
- `USER32!EnumDisplayMonitors` at `0x180520edd`
- `USER32!SetCursor` at `0x1805210ec`
- `USER32!SetCursor` at `0x1805210ec`
- `USER32!SetCapture` at `0x1805210d6`
- `USER32!SetCapture` at `0x1805210d6`
- `USER32!GetDC` at `0x180520ea6`
- `USER32!GetDC` at `0x180520ea6`
- `USER32!ReleaseDC` at `0x180521058`
- `USER32!ReleaseDC` at `0x180521058`
- `USER32!SetFocus` at `0x1805210c9`
- `USER32!SetFocus` at `0x1805210c9`
- `USER32!PeekMessageW` at `0x18052116c`
- `USER32!PeekMessageW` at `0x180521249`
- `USER32!PeekMessageW` at `0x1805212e7`
- `USER32!PeekMessageW` at `0x18052116c`
- `USER32!PeekMessageW` at `0x180521249`
- `USER32!PeekMessageW` at `0x1805212e7`
- `USER32!TranslateMessage` at `0x180521130`
- `USER32!TranslateMessage` at `0x18052127a`
- `USER32!TranslateMessage` at `0x1805212f5`
- `USER32!TranslateMessage` at `0x180521130`
- `USER32!TranslateMessage` at `0x18052127a`
- `USER32!TranslateMessage` at `0x1805212f5`
- `USER32!DispatchMessageW` at `0x18052113a`
- `USER32!DispatchMessageW` at `0x180521284`
- `USER32!DispatchMessageW` at `0x1805212ff`
- `USER32!DispatchMessageW` at `0x18052113a`
- `USER32!DispatchMessageW` at `0x180521284`
- `USER32!DispatchMessageW` at `0x1805212ff`
- `USER32!LoadCursorW` at `0x1805210e3`
- `USER32!LoadCursorW` at `0x1805210e3`
- `USER32!ShowWindow` at `0x180521180`
- `USER32!ShowWindow` at `0x18052121b`
- `USER32!ShowWindow` at `0x180521180`
- `USER32!ShowWindow` at `0x18052121b`

## pseudocode

```c
char __fastcall Art::FStartScreenCapture(struct Ofc::CProxyPtrImpl **a1, __int64 a2)
{
  HWND HostHwnd; // r15
  Art *v5; // rcx
  HWND v6; // rdx
  Art *v7; // rcx
  struct Art::IAppHost *AppHost; // rax
  const wchar_t *v9; // rax
  HDC hdcSrc; // r14
  int v11; // edi
  int v12; // ebx
  int v13; // esi
  int yBottom; // edi
  HBRUSH SolidBrush; // rbx
  Art *v16; // rcx
  HWND Window; // rax
  Art *v18; // rcx
  HCURSOR CursorW; // rax
  char v20; // si
  void *Checked; // rax
  unsigned __int64 v22; // rdx
  unsigned int v23; // r8d
  ULONGLONG TickCount64; // rdi
  ULONGLONG v26; // rax
  ULONGLONG v27; // rbx
  ULONGLONG v28; // rax
  Ofc::TempFileJanitor *v29; // rax
  Art *v30; // rcx
  struct _GUID *v31; // r8
  __int64 v32; // rdi
  Ofc::CProxyPtrImpl *v33; // rax
  int *v34; // rbx
  _QWORD *v35; // rax
  void *v36; // rax
  Art::View *v37; // rax
  ULONG_PTR hSrc; // [rsp+48h] [rbp-B8h]
  BLENDFUNCTION ftn[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v40[8]; // [rsp+68h] [rbp-98h] BYREF
  Ofc::CProxyPtrImpl *v41; // [rsp+70h] [rbp-90h] BYREF
  Ofc::CProxyPtrImpl *v42; // [rsp+78h] [rbp-88h] BYREF
  const OLECHAR *v43; // [rsp+80h] [rbp-80h] BYREF
  MSG Msg; // [rsp+90h] [rbp-70h] BYREF
  LPARAM dwData; // [rsp+F0h] [rbp-10h] BYREF
  struct tagRECT *v46; // [rsp+F8h] [rbp-8h]
  HDC *v47; // [rsp+100h] [rbp+0h]
  HGDIOBJ *v48; // [rsp+108h] [rbp+8h]
  Ofc::TempFileJanitor *v49; // [rsp+110h] [rbp+10h]
  WNDCLASSEXW v50; // [rsp+120h] [rbp+20h] BYREF
  struct tagRECT rc; // [rsp+170h] [rbp+70h] BYREF
  wchar_t v52[8]; // [rsp+180h] [rbp+80h] BYREF
  wchar_t Destination[256]; // [rsp+190h] [rbp+90h] BYREF

  v41 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*a1);
  HostHwnd = *(HWND *)(a2 + 8);
  if ( !HostHwnd )
    HostHwnd = (HWND)Art::GetHostHwnd(&v41);
  if ( !(unsigned __int8)Art::FScreenshotFeatureEnabled(a1) )
    goto LABEL_25;
  if ( Art::FDRMContentVisible(v5) )
  {
    Art::ShowDRMContentError(HostHwnd, v6);
    goto LABEL_25;
  }
  if ( Art::g_hwndScreenCapture )
  {
LABEL_25:
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v41);
    return 0;
  }
  if ( HostHwnd )
  {
    Sleep(0x12Cu);
    ShowWindow(HostHwnd, (*(_BYTE *)(a2 + 1) != 0) + 6);
    TickCount64 = GetTickCount64();
    memset(&Msg, 0, sizeof(Msg));
    do
    {
      if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
      v26 = GetTickCount64();
    }
    while ( v26 - TickCount64 < 0x5DC && TickCount64 <= v26 );
  }
  if ( *(_BYTE *)a2 )
  {
    v27 = GetTickCount64();
    memset(&Msg, 0, sizeof(Msg));
    do
    {
      if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
      v28 = GetTickCount64();
    }
    while ( v28 - v27 < 0x1B58 && v27 <= v28 );
  }
  Art::g_fExitOnDeactivate = 1;
  RedrawWindow(0, 0, 0, 0x180u);
  Destination[0] = 0;
  AppHost = Art::GetAppHost(v7);
  v9 = (const wchar_t *)(*(__int64 (__fastcall **)(struct Art::IAppHost *))(*(_QWORD *)AppHost + 40LL))(AppHost);
  wcscpy_s(Destination, 0xFFu, v9);
  memset_0(&v50, 0, sizeof(v50));
  v50.cbSize = 80;
  v50.lpfnWndProc = (WNDPROC)Art::WndProcScreenCapture;
  v50.hInstance = hInst;
  v50.lpszClassName = L"OfficeM.ScreenCapture";
  v50.hIconSm = 0;
  IsolationAwareRegisterClassExW(&v50);
  SetRect(&Art::g_rcScreenCapture, 0, 0, 0, 0);
  hdcSrc = GetDC(0);
  dwData = 0;
  v46 = &Art::g_rcScreenCapture;
  v47 = &Art::g_hdcScreenCapture;
  v48 = &Art::g_bmpScreenCapture;
  EnumDisplayMonitors(hdcSrc, 0, Art::MonitorInfoEnumProc, (LPARAM)&dwData);
  v11 = v46->right - v46->left;
  v12 = v46->bottom - v46->top;
  Art::g_hdcScreenCapture = CreateCompatibleDC(hdcSrc);
  Art::g_bmpScreenCapture = CreateCompatibleBitmap(hdcSrc, v11, v12);
  SelectObject(Art::g_hdcScreenCapture, Art::g_bmpScreenCapture);
  v13 = Art::g_rcScreenCapture.right - Art::g_rcScreenCapture.left;
  yBottom = Art::g_rcScreenCapture.bottom - Art::g_rcScreenCapture.top;
  BitBlt(
    Art::g_hdcScreenCapture,
    0,
    0,
    Art::g_rcScreenCapture.right - Art::g_rcScreenCapture.left,
    Art::g_rcScreenCapture.bottom - Art::g_rcScreenCapture.top,
    hdcSrc,
    Art::g_rcScreenCapture.left,
    Art::g_rcScreenCapture.top,
    0x40CC0020u);
  Art::g_hdcScreenCaptureBlended = CreateCompatibleDC(Art::g_hdcScreenCapture);
  Art::g_bmpScreenCaptureBlended = CreateCompatibleBitmap(Art::g_hdcScreenCapture, v13, yBottom);
  SelectObject(Art::g_hdcScreenCaptureBlended, Art::g_bmpScreenCaptureBlended);
  rc = 0;
  SetRect(&rc, 0, 0, v13, yBottom);
  SolidBrush = CreateSolidBrush(0xFFFFFFu);
  FillRect(Art::g_hdcScreenCaptureBlended, &rc, SolidBrush);
  DeleteObject(SolidBrush);
  *(_WORD *)&ftn[0].BlendOp = 0;
  ftn[0].SourceConstantAlpha = Art::FInHighContrastMode(v16) ? -1 : 85;
  ftn[0].AlphaFormat = 0;
  AlphaBlend(Art::g_hdcScreenCaptureBlended, 0, 0, v13, yBottom, Art::g_hdcScreenCapture, 0, 0, v13, yBottom, ftn[0]);
  ReleaseDC(0, hdcSrc);
  Window = (HWND)IsolationAwareCreateWindowExW(
                   8u,
                   L"OfficeM.ScreenCapture",
                   Destination,
                   0x90000000,
                   Art::g_rcScreenCapture.left,
                   Art::g_rcScreenCapture.top,
                   v13,
                   yBottom,
                   0,
                   hSrc,
                   hInst);
  if ( !Window )
  {
    Art::ExitScreenCapture(v18);
    goto LABEL_25;
  }
  Art::g_hwndScreenCapture = Window;
  SetForegroundWindow(Window);
  SetFocus(Art::g_hwndScreenCapture);
  SetCapture(Art::g_hwndScreenCapture);
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F03);
  SetCursor(CursorW);
  SetRectEmpty(&Art::g_rcCaptureRect);
  Art::g_fInDrag = 0;
  RedrawWindow(Art::g_hwndScreenCapture, 0, 0, 0x100u);
  v20 = 0;
  if ( HostHwnd )
  {
    while ( Art::g_hwndScreenCapture )
    {
      memset(&Msg, 0, sizeof(Msg));
      if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
    }
    ShowWindow(HostHwnd, 9);
    Checked = Ofc::CProxyPtrImpl::GetChecked(v41);
    Art::UserInterface::GetCurrentView(Checked, &v42, 0);
    if ( *((_QWORD *)v42 + 2) && Art::g_pBitmapClip )
    {
      v43 = &word_180A9C374;
      v29 = (Ofc::TempFileJanitor *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v22, v23);
      v49 = v29;
      if ( v29 )
        v32 = Ofc::TempFileJanitor::TempFileJanitor(v29);
      else
        v32 = 0;
      if ( v32 )
      {
        v33 = (Ofc::CProxyPtrImpl *)Mso::Memory::AllocateEx((Mso::Memory *)0x18, 0, (unsigned int)v31);
        v34 = (int *)v33;
        if ( !v33 )
        {
          CrashWithRecoveryOnOOM(0x1F3C0756u);
          __debugbreak();
        }
        Ofc::CProxyPtrImpl::CProxyPtrImpl(v33, Ofc::TDeleteFromProxy<Ofc::TempFileJanitor>);
        *((_QWORD *)v34 + 2) = v32;
      }
      else
      {
        v34 = &`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_proxyPtrSentinel;
      }
      *(_QWORD *)&ftn[0].BlendOp = v34;
      *(_OWORD *)v52 = 0;
      Art::GetEncoderClsid(v30, v52, v31);
      v35 = Ofc::CProxyPtrImpl::GetChecked((Ofc::CProxyPtrImpl *)v34);
      if ( !(unsigned int)Gdiplus::Image::Save(Art::g_pBitmapClip, *v35, v52) )
      {
        Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)&ftn[0].BlendOp);
        Art::InsertPictureInfoCommand::InsertPictureInfoCommand(
          (Art::InfoCommand *)&Msg,
          0,
          0,
          0,
          (__int64)&v41,
          (__int64)ftn,
          -1);
        v36 = Ofc::CProxyPtrImpl::GetChecked(v42);
        if ( (*(_BYTE *)Art::View::GetInfoCommandState(v36, v40, &Msg) & 1) != 0 )
        {
          v37 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v42);
          Art::View::PerformInfoCommand(v37, (const struct Art::InfoCommand *)&Msg, 0, 0);
          v20 = 1;
        }
        Art::InsertPictureInfoCommand::~InsertPictureInfoCommand((Art::InsertPictureInfoCommand *)&Msg);
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease((struct Ofc::CProxyPtrImpl **)ftn);
      Ofc::CVarStr::ReleaseBuffer((Ofc::CVarStr *)&v43);
    }
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v42);
  }
  if ( Art::g_pBitmapClip )
  {
    (**(void (__fastcall ***)(struct Gdiplus::Bitmap *, __int64))Art::g_pBitmapClip)(Art::g_pBitmapClip, 1);
    Art::g_pBitmapClip = 0;
  }
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v41);
  return v20;
}

```

## disassembly

```asm
0x180520d60  mov     [rsp-8+arg_10], rbx
0x180520d65  push    rbp
0x180520d66  push    rsi
0x180520d67  push    rdi
0x180520d68  push    r12
0x180520d6a  push    r13
0x180520d6c  push    r14
0x180520d6e  push    r15
0x180520d70  lea     rbp, [rsp-2A0h]
0x180520d78  sub     rsp, 3A0h
0x180520d7f  mov     rax, cs:__security_cookie
0x180520d86  xor     rax, rsp
0x180520d89  mov     [rbp+2D0h+var_40], rax
0x180520d90  mov     rbx, rdx
0x180520d93  mov     rdi, rcx
0x180520d96  mov     rcx, [rcx]; struct Ofc::CProxyPtrImpl *
0x180520d99  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180520d9e  mov     [rsp+3D0h+var_360], rax
0x180520da3  mov     r15, [rbx+8]
0x180520da7  xor     r13d, r13d
0x180520daa  test    r15, r15
0x180520dad  jz      loc_1805212A3
0x180520db3  mov     rcx, rdi
0x180520db6  call    ?FScreenshotFeatureEnabled@Art@@YA_NAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::FScreenshotFeatureEnabled(Ofc::TWeakPtr<Art::UserInterface> const &)
0x180520dbb  test    al, al
0x180520dbd  jz      loc_180521292
0x180520dc3  call    ?FDRMContentVisible@Art@@YA_NXZ; Art::FDRMContentVisible(void)
0x180520dc8  test    al, al
0x180520dca  jnz     loc_1805212B5
0x180520dd0  cmp     cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA, r13; HWND__ * Art::g_hwndScreenCapture
0x180520dd7  jnz     loc_180521292
0x180520ddd  mov     esi, 1
0x180520de2  test    r15, r15
0x180520de5  jnz     loc_180521201
0x180520deb  cmp     [rbx], r13b
0x180520dee  jnz     loc_1805212BF
0x180520df4  mov     cs:?g_fExitOnDeactivate@Art@@3_NA, sil; bool Art::g_fExitOnDeactivate
0x180520dfb  mov     r9d, 180h; flags
0x180520e01  xor     r8d, r8d; hrgnUpdate
0x180520e04  xor     edx, edx; lprcUpdate
0x180520e06  xor     ecx, ecx; hWnd
0x180520e08  call    cs:__imp_RedrawWindow
0x180520e0e  mov     [rbp+2D0h+Destination], r13w
0x180520e16  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
0x180520e1b  mov     rdx, rax
0x180520e1e  mov     rcx, [rax]
0x180520e21  mov     rax, [rcx+28h]
0x180520e25  mov     rcx, rdx
0x180520e28  call    cs:__guard_dispatch_icall_fptr
0x180520e2e  mov     r8, rax; Source
0x180520e31  mov     edx, 0FFh; SizeInWords
0x180520e36  lea     rcx, [rbp+2D0h+Destination]; Destination
0x180520e3d  call    cs:__imp_wcscpy_s
0x180520e43  mov     ebx, 50h ; 'P'
0x180520e48  mov     r8d, ebx; Size
0x180520e4b  xor     edx, edx; Val
0x180520e4d  lea     rcx, [rbp+2D0h+var_2B0]; void *
0x180520e51  call    memset_0
0x180520e56  mov     [rbp+2D0h+var_2B0.cbSize], ebx
0x180520e59  lea     rax, ?WndProcScreenCapture@Art@@YA_JPEAUHWND__@@I_K_J@Z; Art::WndProcScreenCapture(HWND__ *,uint,unsigned __int64,__int64)
0x180520e60  mov     [rbp+2D0h+var_2B0.lpfnWndProc], rax
0x180520e64  mov     rax, cs:hInst
0x180520e6b  mov     [rbp+2D0h+var_2B0.hInstance], rax
0x180520e6f  lea     r12, ClassName; "OfficeM.ScreenCapture"
0x180520e76  mov     [rbp+2D0h+var_2B0.lpszClassName], r12
0x180520e7a  mov     [rbp+2D0h+var_2B0.hIconSm], r13
0x180520e7e  lea     rcx, [rbp+2D0h+var_2B0]; WNDCLASSEXW *
0x180520e82  call    IsolationAwareRegisterClassExW
0x180520e87  mov     [rsp+3D0h+yBottom], r13d; yBottom
0x180520e8c  xor     r9d, r9d; xRight
0x180520e8f  xor     r8d, r8d; yTop
0x180520e92  xor     edx, edx; xLeft
0x180520e94  lea     rbx, ?g_rcScreenCapture@Art@@3UtagRECT@@A; tagRECT Art::g_rcScreenCapture
0x180520e9b  mov     rcx, rbx; lprc
0x180520e9e  call    cs:__imp_SetRect
0x180520ea4  xor     ecx, ecx; hWnd
0x180520ea6  call    cs:__imp_GetDC
0x180520eac  mov     r14, rax
0x180520eaf  mov     [rbp+2D0h+dwData], r13
0x180520eb3  mov     [rbp+2D0h+var_2D8], rbx
0x180520eb7  lea     rax, ?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcScreenCapture
0x180520ebe  mov     [rbp+2D0h+var_2D0], rax
0x180520ec2  lea     rax, ?g_bmpScreenCapture@Art@@3PEAUHBITMAP__@@EA; HBITMAP__ * Art::g_bmpScreenCapture
0x180520ec9  mov     [rbp+2D0h+var_2C8], rax
0x180520ecd  lea     r9, [rbp+2D0h+dwData]; dwData
0x180520ed1  lea     r8, ?MonitorInfoEnumProc@Art@@YAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x180520ed8  xor     edx, edx; lprcClip
0x180520eda  mov     rcx, r14; hdc
0x180520edd  call    cs:__imp_EnumDisplayMonitors
0x180520ee3  mov     rcx, [rbp+2D0h+var_2D8]
0x180520ee7  mov     edi, [rcx+8]
0x180520eea  sub     edi, [rcx]
0x180520eec  mov     ebx, [rcx+0Ch]
0x180520eef  sub     ebx, [rcx+4]
0x180520ef2  mov     rcx, r14; hdc
0x180520ef5  call    cs:__imp_CreateCompatibleDC
0x180520efb  mov     cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA, rax; HDC__ * Art::g_hdcScreenCapture
0x180520f02  mov     r8d, ebx; cy
0x180520f05  mov     edx, edi; cx
0x180520f07  mov     rcx, r14; hdc
0x180520f0a  call    cs:__imp_CreateCompatibleBitmap
0x180520f10  mov     cs:?g_bmpScreenCapture@Art@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * Art::g_bmpScreenCapture
0x180520f17  mov     rdx, rax; h
0x180520f1a  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; hdc
0x180520f21  call    cs:__imp_SelectObject
0x180520f27  mov     esi, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.right; tagRECT Art::g_rcScreenCapture ...
0x180520f2d  mov     ecx, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.left; tagRECT Art::g_rcScreenCapture ...
0x180520f33  sub     esi, ecx
0x180520f35  mov     edi, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.bottom; tagRECT Art::g_rcScreenCapture ...
0x180520f3b  mov     eax, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.top; tagRECT Art::g_rcScreenCapture ...
0x180520f41  sub     edi, eax
0x180520f43  mov     [rsp+3D0h+rop], 40CC0020h; rop
0x180520f4b  mov     [rsp+3D0h+y1], eax; y1
0x180520f4f  mov     [rsp+3D0h+x1], ecx; x1
0x180520f53  mov     [rsp+3D0h+hdcSrc], r14; hdcSrc
0x180520f58  mov     [rsp+3D0h+yBottom], edi; cy
0x180520f5c  mov     r9d, esi; cx
0x180520f5f  xor     r8d, r8d; y
0x180520f62  xor     edx, edx; x
0x180520f64  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; hdc
0x180520f6b  call    cs:__imp_BitBlt
0x180520f71  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; hdc
0x180520f78  call    cs:__imp_CreateCompatibleDC
0x180520f7e  mov     cs:?g_hdcScreenCaptureBlended@Art@@3PEAUHDC__@@EA, rax; HDC__ * Art::g_hdcScreenCaptureBlended
0x180520f85  mov     r8d, edi; cy
0x180520f88  mov     edx, esi; cx
0x180520f8a  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; hdc
0x180520f91  call    cs:__imp_CreateCompatibleBitmap
0x180520f97  mov     cs:?g_bmpScreenCaptureBlended@Art@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * Art::g_bmpScreenCaptureBlended
0x180520f9e  mov     rdx, rax; h
0x180520fa1  mov     rcx, cs:?g_hdcScreenCaptureBlended@Art@@3PEAUHDC__@@EA; hdc
0x180520fa8  call    cs:__imp_SelectObject
0x180520fae  xorps   xmm0, xmm0
0x180520fb1  movups  xmmword ptr [rbp+2D0h+rc.left], xmm0
0x180520fb5  mov     [rsp+3D0h+yBottom], edi; yBottom
0x180520fb9  mov     r9d, esi; xRight
0x180520fbc  xor     r8d, r8d; yTop
0x180520fbf  xor     edx, edx; xLeft
0x180520fc1  lea     rcx, [rbp+2D0h+rc]; lprc
0x180520fc5  call    cs:__imp_SetRect
0x180520fcb  mov     ecx, 0FFFFFFh; color
0x180520fd0  call    cs:__imp_CreateSolidBrush
0x180520fd6  mov     rbx, rax
0x180520fd9  mov     r8, rax; hbr
0x180520fdc  lea     rdx, [rbp+2D0h+rc]; lprc
0x180520fe0  mov     rcx, cs:?g_hdcScreenCaptureBlended@Art@@3PEAUHDC__@@EA; hDC
0x180520fe7  call    cs:__imp_FillRect
0x180520fed  mov     rcx, rbx; ho
0x180520ff0  call    cs:__imp_DeleteObject
0x180520ff6  mov     word ptr [rsp+3D0h+var_370.BlendOp], r13w
0x180520ffc  call    ?FInHighContrastMode@Art@@YA_NXZ; Art::FInHighContrastMode(void)
0x180521001  neg     al
0x180521003  sbb     cl, cl
0x180521005  and     cl, 0AAh
0x180521008  add     cl, 55h ; 'U'
0x18052100b  mov     [rsp+3D0h+var_370.SourceConstantAlpha], cl
0x18052100f  mov     [rsp+3D0h+var_370.AlphaFormat], r13b
0x180521014  mov     eax, dword ptr [rsp+3D0h+var_370.BlendOp]
0x180521018  mov     dword ptr [rsp+3D0h+ftn.BlendOp], eax; ftn
0x18052101c  mov     dword ptr [rsp+3D0h+hSrc], edi; ulCookie
0x180521020  mov     [rsp+3D0h+rop], esi; wSrc
0x180521024  mov     [rsp+3D0h+y1], r13d; yoriginSrc
0x180521029  mov     [rsp+3D0h+x1], r13d; xoriginSrc
0x18052102e  mov     rax, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcScreenCapture
0x180521035  mov     [rsp+3D0h+hdcSrc], rax; hdcSrc
0x18052103a  mov     [rsp+3D0h+yBottom], edi; hDest
0x18052103e  mov     r9d, esi; wDest
0x180521041  xor     r8d, r8d; yoriginDest
0x180521044  xor     edx, edx; xoriginDest
0x180521046  mov     rcx, cs:?g_hdcScreenCaptureBlended@Art@@3PEAUHDC__@@EA; hdcDest
0x18052104d  call    cs:__imp_AlphaBlend
0x180521053  mov     rdx, r14; hDC
0x180521056  xor     ecx, ecx; hWnd
0x180521058  call    cs:__imp_ReleaseDC
0x18052105e  mov     rax, cs:hInst
0x180521065  mov     ecx, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.top; tagRECT Art::g_rcScreenCapture ...
0x18052106b  mov     r8d, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.left; tagRECT Art::g_rcScreenCapture ...
0x180521072  mov     qword ptr [rsp+3D0h+ftn.BlendOp], rax; HINSTANCE
0x180521077  mov     qword ptr [rsp+3D0h+rop], r13; HWND
0x18052107c  mov     [rsp+3D0h+y1], edi; int
0x180521080  mov     [rsp+3D0h+x1], esi; int
0x180521084  mov     dword ptr [rsp+3D0h+hdcSrc], ecx; int
0x180521088  mov     [rsp+3D0h+yBottom], r8d; int
0x18052108d  mov     r9d, 90000000h; dwStyle
0x180521093  lea     r8, [rbp+2D0h+Destination]; lpWindowName
0x18052109a  mov     rdx, r12; lpClassName
0x18052109d  mov     ebx, 8
0x1805210a2  mov     ecx, ebx; dwExStyle
0x1805210a4  call    IsolationAwareCreateWindowExW
0x1805210a9  test    rax, rax
0x1805210ac  jz      loc_18052128C
0x1805210b2  mov     cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA, rax; HWND__ * Art::g_hwndScreenCapture
0x1805210b9  mov     rcx, rax; hWnd
0x1805210bc  call    cs:__imp_SetForegroundWindow
0x1805210c2  mov     rcx, cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA; hWnd
0x1805210c9  call    cs:__imp_SetFocus
0x1805210cf  mov     rcx, cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA; hWnd
0x1805210d6  call    cs:__imp_SetCapture
0x1805210dc  mov     edx, 7F03h; lpCursorName
0x1805210e1  xor     ecx, ecx; hInstance
0x1805210e3  call    cs:__imp_LoadCursorW
0x1805210e9  mov     rcx, rax; hCursor
0x1805210ec  call    cs:__imp_SetCursor
0x1805210f2  lea     rcx, ?g_rcCaptureRect@Art@@3UtagRECT@@A; lprc
0x1805210f9  call    cs:__imp_SetRectEmpty
0x1805210ff  mov     cs:?g_fInDrag@Art@@3_NA, r13b; bool Art::g_fInDrag
0x180521106  mov     r9d, 100h; flags
0x18052110c  xor     r8d, r8d; hrgnUpdate
0x18052110f  xor     edx, edx; lprcUpdate
0x180521111  mov     rcx, cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA; hWnd
0x180521118  call    cs:__imp_RedrawWindow
0x18052111e  mov     sil, r13b
0x180521121  test    r15, r15
0x180521124  jz      loc_1805211BA
0x18052112a  jmp     short loc_180521140
0x18052112c  lea     rcx, [rbp+2D0h+Msg]; lpMsg
0x180521130  call    cs:__imp_TranslateMessage
0x180521136  lea     rcx, [rbp+2D0h+Msg]; lpMsg
0x18052113a  call    cs:__imp_DispatchMessageW
0x180521140  cmp     cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA, r13; HWND__ * Art::g_hwndScreenCapture
0x180521147  jz      short loc_180521178
0x180521149  xorps   xmm0, xmm0
0x18052114c  movups  xmmword ptr [rbp+2D0h+Msg.hwnd], xmm0
0x180521150  movups  xmmword ptr [rbp+2D0h+Msg.wParam], xmm0
0x180521154  movups  xmmword ptr [rbp+2D0h+Msg.time], xmm0
0x180521158  mov     [rsp+3D0h+yBottom], 1; wRemoveMsg
0x180521160  xor     r9d, r9d; wMsgFilterMax
0x180521163  xor     r8d, r8d; wMsgFilterMin
0x180521166  xor     edx, edx; hWnd
0x180521168  lea     rcx, [rbp+2D0h+Msg]; lpMsg
0x18052116c  call    cs:__imp_PeekMessageW
0x180521172  test    eax, eax
0x180521174  jz      short loc_180521140
0x180521176  jmp     short loc_18052112C
0x180521178  mov     edx, 9; nCmdShow
0x18052117d  mov     rcx, r15; hWnd
0x180521180  call    cs:__imp_ShowWindow
0x180521186  mov     rcx, [rsp+3D0h+var_360]; this
0x18052118b  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180521190  xor     r8d, r8d
0x180521193  lea     rdx, [rsp+3D0h+var_358]
0x180521198  mov     rcx, rax
0x18052119b  call    ?GetCurrentView@UserInterface@Art@@QEAA?AV?$TSharedPtr@VView@Art@@@Ofc@@_N@Z; Art::UserInterface::GetCurrentView(bool)
0x1805211a0  nop
0x1805211a1  mov     rax, [rsp+3D0h+var_358]
0x1805211a6  cmp     [rax+10h], r13
0x1805211aa  jnz     loc_180521328
0x1805211b0  lea     rcx, [rsp+3D0h+var_358]; struct Ofc::CProxyPtrImpl **
0x1805211b5  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1805211ba  mov     rcx, cs:?g_pBitmapClip@Art@@3PEAVBitmap@Gdiplus@@EA; Gdiplus::Bitmap * Art::g_pBitmapClip
0x1805211c1  test    rcx, rcx
0x1805211c4  jnz     loc_18052148E
0x1805211ca  lea     rcx, [rsp+3D0h+var_360]; struct Ofc::CProxyPtrImpl **
0x1805211cf  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1805211d4  mov     al, sil
0x1805211d7  mov     rcx, [rbp+2D0h+var_40]
0x1805211de  xor     rcx, rsp; StackCookie
0x1805211e1  call    __security_check_cookie
0x1805211e6  mov     rbx, [rsp+3D0h+arg_10]
0x1805211ee  add     rsp, 3A0h
0x1805211f5  pop     r15
0x1805211f7  pop     r14
0x1805211f9  pop     r13
0x1805211fb  pop     r12
0x1805211fd  pop     rdi
0x1805211fe  pop     rsi
0x1805211ff  pop     rbp
0x180521200  retn
0x180521201  mov     ecx, 12Ch; dwMilliseconds
0x180521206  call    cs:__imp_Sleep
0x18052120c  mov     al, [rbx+1]
0x18052120f  neg     al
0x180521211  sbb     edx, edx
0x180521213  neg     edx
0x180521215  add     edx, 6; nCmdShow
0x180521218  mov     rcx, r15; hWnd
0x18052121b  call    cs:__imp_ShowWindow
0x180521221  call    cs:__imp_GetTickCount64
0x180521227  mov     rdi, rax
0x18052122a  xorps   xmm0, xmm0
0x18052122d  movups  xmmword ptr [rbp+2D0h+Msg.hwnd], xmm0
0x180521231  movups  xmmword ptr [rbp+2D0h+Msg.wParam], xmm0
0x180521235  movups  xmmword ptr [rbp+2D0h+Msg.time], xmm0
0x180521239  mov     [rsp+3D0h+yBottom], esi; wRemoveMsg
0x18052123d  xor     r9d, r9d; wMsgFilterMax
0x180521240  xor     r8d, r8d; wMsgFilterMin
0x180521243  xor     edx, edx; hWnd
0x180521245  lea     rcx, [rbp+2D0h+Msg]; lpMsg
0x180521249  call    cs:__imp_PeekMessageW
0x18052124f  test    eax, eax
0x180521251  jnz     short loc_180521276
0x180521253  call    cs:__imp_GetTickCount64
0x180521259  mov     rcx, rax
0x18052125c  sub     rcx, rdi
0x18052125f  cmp     rcx, 5DCh
0x180521266  jnb     loc_180520DEB
0x18052126c  cmp     rdi, rax
0x18052126f  jbe     short loc_180521239
0x180521271  jmp     loc_180520DEB
0x180521276  lea     rcx, [rbp+2D0h+Msg]; lpMsg
  ... truncated ...
```
