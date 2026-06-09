# Art::FStartScreenCapture(Ofc::TWeakPtr<Art::UserInterface> const &,Art::ScreenCaptureSetting const &)

- ea: `0x1804e5af0`
- end: `0x1804e623a`
- name: `?FStartScreenCapture@Art@@YA_NAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@AEBUScreenCaptureSetting@1@@Z`
- size: `1866`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1804e5ac0`

## callees

- `0x180003c60`
- `0x180011550`
- `0x18001daf0`
- `0x1800445c0`
- `0x180064914`
- `0x1800659a0`
- `0x18006d0a0`
- `0x180070fe0`
- `0x180071720`
- `0x18014bc30`
- `0x1803076bc`
- `0x180329210`
- `0x180329bc0`
- `0x1804e5af0`
- `0x1804e623c`
- `0x1804e6364`
- `0x1804e6420`
- `0x1804e6610`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x1807620c0`
- `0x18093a8f8`
- `0x1809a2804`
- `0x1809a28bc`
- `0x1809a2c50`
- `0x1809a2c78`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x1804e5faf`
- `KERNEL32!GetTickCount64` at `0x1804e5fe1`
- `KERNEL32!GetTickCount64` at `0x1804e604d`
- `KERNEL32!GetTickCount64` at `0x1804e6093`
- `KERNEL32!GetTickCount64` at `0x1804e5faf`
- `KERNEL32!GetTickCount64` at `0x1804e5fe1`
- `KERNEL32!GetTickCount64` at `0x1804e604d`
- `KERNEL32!GetTickCount64` at `0x1804e6093`
- `KERNEL32!Sleep` at `0x1804e5f94`
- `KERNEL32!Sleep` at `0x1804e5f94`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1804e5bcd`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1804e5bcd`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1804e610c`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1804e610c`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1804e60f9`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1804e60f9`
- `GDI32!CreateSolidBrush` at `0x1804e5d60`
- `GDI32!CreateSolidBrush` at `0x1804e5d60`
- `GDI32!BitBlt` at `0x1804e5cfb`
- `GDI32!BitBlt` at `0x1804e5cfb`
- `GDI32!SelectObject` at `0x1804e5cb1`
- `GDI32!SelectObject` at `0x1804e5d38`
- `GDI32!SelectObject` at `0x1804e5cb1`
- `GDI32!SelectObject` at `0x1804e5d38`
- `GDI32!DeleteObject` at `0x1804e5d80`
- `GDI32!DeleteObject` at `0x1804e5d80`
- `GDI32!CreateCompatibleDC` at `0x1804e5c85`
- `GDI32!CreateCompatibleDC` at `0x1804e5d08`
- `GDI32!CreateCompatibleDC` at `0x1804e5c85`
- `GDI32!CreateCompatibleDC` at `0x1804e5d08`
- `GDI32!CreateCompatibleBitmap` at `0x1804e5c9a`
- `GDI32!CreateCompatibleBitmap` at `0x1804e5d21`
- `GDI32!CreateCompatibleBitmap` at `0x1804e5c9a`
- `GDI32!CreateCompatibleBitmap` at `0x1804e5d21`
- `MSIMG32!AlphaBlend` at `0x1804e5ddd`
- `MSIMG32!AlphaBlend` at `0x1804e5ddd`
- `USER32!FillRect` at `0x1804e5d77`
- `USER32!FillRect` at `0x1804e5d77`
- `USER32!RedrawWindow` at `0x1804e5b98`
- `USER32!RedrawWindow` at `0x1804e5ea8`
- `USER32!RedrawWindow` at `0x1804e5b98`
- `USER32!RedrawWindow` at `0x1804e5ea8`
- `USER32!SetForegroundWindow` at `0x1804e5e4c`
- `USER32!SetForegroundWindow` at `0x1804e5e4c`
- `USER32!SetRectEmpty` at `0x1804e5e89`
- `USER32!SetRectEmpty` at `0x1804e5e89`
- `USER32!SetRect` at `0x1804e5c2e`
- `USER32!SetRect` at `0x1804e5d55`
- `USER32!SetRect` at `0x1804e5c2e`
- `USER32!SetRect` at `0x1804e5d55`
- `USER32!EnumDisplayMonitors` at `0x1804e5c6d`
- `USER32!EnumDisplayMonitors` at `0x1804e5c6d`
- `USER32!SetCursor` at `0x1804e5e7c`
- `USER32!SetCursor` at `0x1804e5e7c`
- `USER32!SetCapture` at `0x1804e5e66`
- `USER32!SetCapture` at `0x1804e5e66`
- `USER32!GetDC` at `0x1804e5c36`
- `USER32!GetDC` at `0x1804e5c36`
- `USER32!ReleaseDC` at `0x1804e5de8`
- `USER32!ReleaseDC` at `0x1804e5de8`
- `USER32!SetFocus` at `0x1804e5e59`
- `USER32!SetFocus` at `0x1804e5e59`
- `USER32!PeekMessageW` at `0x1804e5ee6`
- `USER32!PeekMessageW` at `0x1804e5fd7`
- `USER32!PeekMessageW` at `0x1804e6075`
- `USER32!PeekMessageW` at `0x1804e5ee6`
- `USER32!PeekMessageW` at `0x1804e5fd7`
- `USER32!PeekMessageW` at `0x1804e6075`
- `USER32!TranslateMessage` at `0x1804e5ef4`
- `USER32!TranslateMessage` at `0x1804e6008`
- `USER32!TranslateMessage` at `0x1804e6083`
- `USER32!TranslateMessage` at `0x1804e5ef4`
- `USER32!TranslateMessage` at `0x1804e6008`
- `USER32!TranslateMessage` at `0x1804e6083`
- `USER32!DispatchMessageW` at `0x1804e5efe`
- `USER32!DispatchMessageW` at `0x1804e6012`
- `USER32!DispatchMessageW` at `0x1804e608d`
- `USER32!DispatchMessageW` at `0x1804e5efe`
- `USER32!DispatchMessageW` at `0x1804e6012`
- `USER32!DispatchMessageW` at `0x1804e608d`
- `USER32!LoadCursorW` at `0x1804e5e73`
- `USER32!LoadCursorW` at `0x1804e5e73`
- `USER32!ShowWindow` at `0x1804e5f0e`
- `USER32!ShowWindow` at `0x1804e5fa9`
- `USER32!ShowWindow` at `0x1804e5f0e`
- `USER32!ShowWindow` at `0x1804e5fa9`

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
  struct tagMSG Msg; // [rsp+90h] [rbp-70h] BYREF
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
      v43 = &word_180A77374;
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
          CrashWithRecoveryOnOOM(0x1E000188u);
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
0x1804e5af0  mov     [rsp-8+arg_10], rbx
0x1804e5af5  push    rbp
0x1804e5af6  push    rsi
0x1804e5af7  push    rdi
0x1804e5af8  push    r12
0x1804e5afa  push    r13
0x1804e5afc  push    r14
0x1804e5afe  push    r15
0x1804e5b00  lea     rbp, [rsp-2A0h]
0x1804e5b08  sub     rsp, 3A0h
0x1804e5b0f  mov     rax, cs:__security_cookie
0x1804e5b16  xor     rax, rsp
0x1804e5b19  mov     [rbp+2D0h+var_40], rax
0x1804e5b20  mov     rbx, rdx
0x1804e5b23  mov     rdi, rcx
0x1804e5b26  mov     rcx, [rcx]; struct Ofc::CProxyPtrImpl *
0x1804e5b29  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1804e5b2e  mov     [rsp+3D0h+var_360], rax
0x1804e5b33  mov     r15, [rbx+8]
0x1804e5b37  xor     r13d, r13d
0x1804e5b3a  test    r15, r15
0x1804e5b3d  jz      loc_1804E6031
0x1804e5b43  mov     rcx, rdi
0x1804e5b46  call    ?FScreenshotFeatureEnabled@Art@@YA_NAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::FScreenshotFeatureEnabled(Ofc::TWeakPtr<Art::UserInterface> const &)
0x1804e5b4b  test    al, al
0x1804e5b4d  jz      loc_1804E6020
0x1804e5b53  call    ?FDRMContentVisible@Art@@YA_NXZ; Art::FDRMContentVisible(void)
0x1804e5b58  test    al, al
0x1804e5b5a  jnz     loc_1804E6043
0x1804e5b60  cmp     cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA, r13; HWND__ * Art::g_hwndScreenCapture
0x1804e5b67  jnz     loc_1804E6020
0x1804e5b6d  mov     esi, 1
0x1804e5b72  test    r15, r15
0x1804e5b75  jnz     loc_1804E5F8F
0x1804e5b7b  cmp     [rbx], r13b
0x1804e5b7e  jnz     loc_1804E604D
0x1804e5b84  mov     cs:?g_fExitOnDeactivate@Art@@3_NA, sil; bool Art::g_fExitOnDeactivate
0x1804e5b8b  mov     r9d, 180h; flags
0x1804e5b91  xor     r8d, r8d; hrgnUpdate
0x1804e5b94  xor     edx, edx; lprcUpdate
0x1804e5b96  xor     ecx, ecx; hWnd
0x1804e5b98  call    cs:__imp_RedrawWindow
0x1804e5b9e  mov     [rbp+2D0h+Destination], r13w
0x1804e5ba6  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
0x1804e5bab  mov     rdx, rax
0x1804e5bae  mov     rcx, [rax]
0x1804e5bb1  mov     rax, [rcx+28h]
0x1804e5bb5  mov     rcx, rdx
0x1804e5bb8  call    cs:__guard_dispatch_icall_fptr
0x1804e5bbe  mov     r8, rax; Source
0x1804e5bc1  mov     edx, 0FFh; SizeInWords
0x1804e5bc6  lea     rcx, [rbp+2D0h+Destination]; Destination
0x1804e5bcd  call    cs:__imp_wcscpy_s
0x1804e5bd3  mov     ebx, 50h ; 'P'
0x1804e5bd8  mov     r8d, ebx; Size
0x1804e5bdb  xor     edx, edx; Val
0x1804e5bdd  lea     rcx, [rbp+2D0h+var_2B0]; void *
0x1804e5be1  call    memset_0
0x1804e5be6  mov     [rbp+2D0h+var_2B0.cbSize], ebx
0x1804e5be9  lea     rax, ?WndProcScreenCapture@Art@@YA_JPEAUHWND__@@I_K_J@Z; Art::WndProcScreenCapture(HWND__ *,uint,unsigned __int64,__int64)
0x1804e5bf0  mov     [rbp+2D0h+var_2B0.lpfnWndProc], rax
0x1804e5bf4  mov     rax, cs:hInst
0x1804e5bfb  mov     [rbp+2D0h+var_2B0.hInstance], rax
0x1804e5bff  lea     r12, ClassName; "OfficeM.ScreenCapture"
0x1804e5c06  mov     [rbp+2D0h+var_2B0.lpszClassName], r12
0x1804e5c0a  mov     [rbp+2D0h+var_2B0.hIconSm], r13
0x1804e5c0e  lea     rcx, [rbp+2D0h+var_2B0]; WNDCLASSEXW *
0x1804e5c12  call    IsolationAwareRegisterClassExW
0x1804e5c17  mov     [rsp+3D0h+yBottom], r13d; yBottom
0x1804e5c1c  xor     r9d, r9d; xRight
0x1804e5c1f  xor     r8d, r8d; yTop
0x1804e5c22  xor     edx, edx; xLeft
0x1804e5c24  lea     rbx, ?g_rcScreenCapture@Art@@3UtagRECT@@A; tagRECT Art::g_rcScreenCapture
0x1804e5c2b  mov     rcx, rbx; lprc
0x1804e5c2e  call    cs:__imp_SetRect
0x1804e5c34  xor     ecx, ecx; hWnd
0x1804e5c36  call    cs:__imp_GetDC
0x1804e5c3c  mov     r14, rax
0x1804e5c3f  mov     [rbp+2D0h+dwData], r13
0x1804e5c43  mov     [rbp+2D0h+var_2D8], rbx
0x1804e5c47  lea     rax, ?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcScreenCapture
0x1804e5c4e  mov     [rbp+2D0h+var_2D0], rax
0x1804e5c52  lea     rax, ?g_bmpScreenCapture@Art@@3PEAUHBITMAP__@@EA; HBITMAP__ * Art::g_bmpScreenCapture
0x1804e5c59  mov     [rbp+2D0h+var_2C8], rax
0x1804e5c5d  lea     r9, [rbp+2D0h+dwData]; dwData
0x1804e5c61  lea     r8, ?MonitorInfoEnumProc@Art@@YAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; lpfnEnum
0x1804e5c68  xor     edx, edx; lprcClip
0x1804e5c6a  mov     rcx, r14; hdc
0x1804e5c6d  call    cs:__imp_EnumDisplayMonitors
0x1804e5c73  mov     rcx, [rbp+2D0h+var_2D8]
0x1804e5c77  mov     edi, [rcx+8]
0x1804e5c7a  sub     edi, [rcx]
0x1804e5c7c  mov     ebx, [rcx+0Ch]
0x1804e5c7f  sub     ebx, [rcx+4]
0x1804e5c82  mov     rcx, r14; hdc
0x1804e5c85  call    cs:__imp_CreateCompatibleDC
0x1804e5c8b  mov     cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA, rax; HDC__ * Art::g_hdcScreenCapture
0x1804e5c92  mov     r8d, ebx; cy
0x1804e5c95  mov     edx, edi; cx
0x1804e5c97  mov     rcx, r14; hdc
0x1804e5c9a  call    cs:__imp_CreateCompatibleBitmap
0x1804e5ca0  mov     cs:?g_bmpScreenCapture@Art@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * Art::g_bmpScreenCapture
0x1804e5ca7  mov     rdx, rax; h
0x1804e5caa  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; hdc
0x1804e5cb1  call    cs:__imp_SelectObject
0x1804e5cb7  mov     esi, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.right; tagRECT Art::g_rcScreenCapture ...
0x1804e5cbd  mov     ecx, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.left; tagRECT Art::g_rcScreenCapture ...
0x1804e5cc3  sub     esi, ecx
0x1804e5cc5  mov     edi, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.bottom; tagRECT Art::g_rcScreenCapture ...
0x1804e5ccb  mov     eax, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.top; tagRECT Art::g_rcScreenCapture ...
0x1804e5cd1  sub     edi, eax
0x1804e5cd3  mov     [rsp+3D0h+rop], 40CC0020h; rop
0x1804e5cdb  mov     [rsp+3D0h+y1], eax; y1
0x1804e5cdf  mov     [rsp+3D0h+x1], ecx; x1
0x1804e5ce3  mov     [rsp+3D0h+hdcSrc], r14; hdcSrc
0x1804e5ce8  mov     [rsp+3D0h+yBottom], edi; cy
0x1804e5cec  mov     r9d, esi; cx
0x1804e5cef  xor     r8d, r8d; y
0x1804e5cf2  xor     edx, edx; x
0x1804e5cf4  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; hdc
0x1804e5cfb  call    cs:__imp_BitBlt
0x1804e5d01  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; hdc
0x1804e5d08  call    cs:__imp_CreateCompatibleDC
0x1804e5d0e  mov     cs:?g_hdcScreenCaptureBlended@Art@@3PEAUHDC__@@EA, rax; HDC__ * Art::g_hdcScreenCaptureBlended
0x1804e5d15  mov     r8d, edi; cy
0x1804e5d18  mov     edx, esi; cx
0x1804e5d1a  mov     rcx, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; hdc
0x1804e5d21  call    cs:__imp_CreateCompatibleBitmap
0x1804e5d27  mov     cs:?g_bmpScreenCaptureBlended@Art@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * Art::g_bmpScreenCaptureBlended
0x1804e5d2e  mov     rdx, rax; h
0x1804e5d31  mov     rcx, cs:?g_hdcScreenCaptureBlended@Art@@3PEAUHDC__@@EA; hdc
0x1804e5d38  call    cs:__imp_SelectObject
0x1804e5d3e  xorps   xmm0, xmm0
0x1804e5d41  movups  xmmword ptr [rbp+2D0h+rc.left], xmm0
0x1804e5d45  mov     [rsp+3D0h+yBottom], edi; yBottom
0x1804e5d49  mov     r9d, esi; xRight
0x1804e5d4c  xor     r8d, r8d; yTop
0x1804e5d4f  xor     edx, edx; xLeft
0x1804e5d51  lea     rcx, [rbp+2D0h+rc]; lprc
0x1804e5d55  call    cs:__imp_SetRect
0x1804e5d5b  mov     ecx, 0FFFFFFh; color
0x1804e5d60  call    cs:__imp_CreateSolidBrush
0x1804e5d66  mov     rbx, rax
0x1804e5d69  mov     r8, rax; hbr
0x1804e5d6c  lea     rdx, [rbp+2D0h+rc]; lprc
0x1804e5d70  mov     rcx, cs:?g_hdcScreenCaptureBlended@Art@@3PEAUHDC__@@EA; hDC
0x1804e5d77  call    cs:__imp_FillRect
0x1804e5d7d  mov     rcx, rbx; ho
0x1804e5d80  call    cs:__imp_DeleteObject
0x1804e5d86  mov     word ptr [rsp+3D0h+var_370.BlendOp], r13w
0x1804e5d8c  call    ?FInHighContrastMode@Art@@YA_NXZ; Art::FInHighContrastMode(void)
0x1804e5d91  neg     al
0x1804e5d93  sbb     cl, cl
0x1804e5d95  and     cl, 0AAh
0x1804e5d98  add     cl, 55h ; 'U'
0x1804e5d9b  mov     [rsp+3D0h+var_370.SourceConstantAlpha], cl
0x1804e5d9f  mov     [rsp+3D0h+var_370.AlphaFormat], r13b
0x1804e5da4  mov     eax, dword ptr [rsp+3D0h+var_370.BlendOp]
0x1804e5da8  mov     dword ptr [rsp+3D0h+ftn.BlendOp], eax; ftn
0x1804e5dac  mov     dword ptr [rsp+3D0h+hSrc], edi; ulCookie
0x1804e5db0  mov     [rsp+3D0h+rop], esi; wSrc
0x1804e5db4  mov     [rsp+3D0h+y1], r13d; yoriginSrc
0x1804e5db9  mov     [rsp+3D0h+x1], r13d; xoriginSrc
0x1804e5dbe  mov     rax, cs:?g_hdcScreenCapture@Art@@3PEAUHDC__@@EA; HDC__ * Art::g_hdcScreenCapture
0x1804e5dc5  mov     [rsp+3D0h+hdcSrc], rax; hdcSrc
0x1804e5dca  mov     [rsp+3D0h+yBottom], edi; hDest
0x1804e5dce  mov     r9d, esi; wDest
0x1804e5dd1  xor     r8d, r8d; yoriginDest
0x1804e5dd4  xor     edx, edx; xoriginDest
0x1804e5dd6  mov     rcx, cs:?g_hdcScreenCaptureBlended@Art@@3PEAUHDC__@@EA; hdcDest
0x1804e5ddd  call    cs:__imp_AlphaBlend
0x1804e5de3  mov     rdx, r14; hDC
0x1804e5de6  xor     ecx, ecx; hWnd
0x1804e5de8  call    cs:__imp_ReleaseDC
0x1804e5dee  mov     rax, cs:hInst
0x1804e5df5  mov     ecx, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.top; tagRECT Art::g_rcScreenCapture ...
0x1804e5dfb  mov     r8d, cs:?g_rcScreenCapture@Art@@3UtagRECT@@A.left; tagRECT Art::g_rcScreenCapture ...
0x1804e5e02  mov     qword ptr [rsp+3D0h+ftn.BlendOp], rax; HINSTANCE
0x1804e5e07  mov     qword ptr [rsp+3D0h+rop], r13; HWND
0x1804e5e0c  mov     [rsp+3D0h+y1], edi; int
0x1804e5e10  mov     [rsp+3D0h+x1], esi; int
0x1804e5e14  mov     dword ptr [rsp+3D0h+hdcSrc], ecx; int
0x1804e5e18  mov     [rsp+3D0h+yBottom], r8d; int
0x1804e5e1d  mov     r9d, 90000000h; dwStyle
0x1804e5e23  lea     r8, [rbp+2D0h+Destination]; lpWindowName
0x1804e5e2a  mov     rdx, r12; lpClassName
0x1804e5e2d  mov     ebx, 8
0x1804e5e32  mov     ecx, ebx; dwExStyle
0x1804e5e34  call    IsolationAwareCreateWindowExW
0x1804e5e39  test    rax, rax
0x1804e5e3c  jz      loc_1804E601A
0x1804e5e42  mov     cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA, rax; HWND__ * Art::g_hwndScreenCapture
0x1804e5e49  mov     rcx, rax; hWnd
0x1804e5e4c  call    cs:__imp_SetForegroundWindow
0x1804e5e52  mov     rcx, cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA; hWnd
0x1804e5e59  call    cs:__imp_SetFocus
0x1804e5e5f  mov     rcx, cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA; hWnd
0x1804e5e66  call    cs:__imp_SetCapture
0x1804e5e6c  mov     edx, 7F03h; lpCursorName
0x1804e5e71  xor     ecx, ecx; hInstance
0x1804e5e73  call    cs:__imp_LoadCursorW
0x1804e5e79  mov     rcx, rax; hCursor
0x1804e5e7c  call    cs:__imp_SetCursor
0x1804e5e82  lea     rcx, ?g_rcCaptureRect@Art@@3UtagRECT@@A; lprc
0x1804e5e89  call    cs:__imp_SetRectEmpty
0x1804e5e8f  mov     cs:?g_fInDrag@Art@@3_NA, r13b; bool Art::g_fInDrag
0x1804e5e96  mov     r9d, 100h; flags
0x1804e5e9c  xor     r8d, r8d; hrgnUpdate
0x1804e5e9f  xor     edx, edx; lprcUpdate
0x1804e5ea1  mov     rcx, cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA; hWnd
0x1804e5ea8  call    cs:__imp_RedrawWindow
0x1804e5eae  mov     sil, r13b
0x1804e5eb1  test    r15, r15
0x1804e5eb4  jz      loc_1804E5F48
0x1804e5eba  cmp     cs:?g_hwndScreenCapture@Art@@3PEAUHWND__@@EA, r13; HWND__ * Art::g_hwndScreenCapture
0x1804e5ec1  jz      short loc_1804E5F06
0x1804e5ec3  xorps   xmm0, xmm0
0x1804e5ec6  movups  xmmword ptr [rbp+2D0h+Msg.hwnd], xmm0
0x1804e5eca  movups  xmmword ptr [rbp+2D0h+Msg.wParam], xmm0
0x1804e5ece  movups  xmmword ptr [rbp+2D0h+Msg.time], xmm0
0x1804e5ed2  mov     [rsp+3D0h+yBottom], 1; wRemoveMsg
0x1804e5eda  xor     r9d, r9d; wMsgFilterMax
0x1804e5edd  xor     r8d, r8d; wMsgFilterMin
0x1804e5ee0  xor     edx, edx; hWnd
0x1804e5ee2  lea     rcx, [rbp+2D0h+Msg]; lpMsg
0x1804e5ee6  call    cs:__imp_PeekMessageW
0x1804e5eec  test    eax, eax
0x1804e5eee  jz      short loc_1804E5EBA
0x1804e5ef0  lea     rcx, [rbp+2D0h+Msg]; lpMsg
0x1804e5ef4  call    cs:__imp_TranslateMessage
0x1804e5efa  lea     rcx, [rbp+2D0h+Msg]; lpMsg
0x1804e5efe  call    cs:__imp_DispatchMessageW
0x1804e5f04  jmp     short loc_1804E5EBA
0x1804e5f06  mov     edx, 9; nCmdShow
0x1804e5f0b  mov     rcx, r15; hWnd
0x1804e5f0e  call    cs:__imp_ShowWindow
0x1804e5f14  mov     rcx, [rsp+3D0h+var_360]; this
0x1804e5f19  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1804e5f1e  xor     r8d, r8d
0x1804e5f21  lea     rdx, [rsp+3D0h+var_358]
0x1804e5f26  mov     rcx, rax
0x1804e5f29  call    ?GetCurrentView@UserInterface@Art@@QEAA?AV?$TSharedPtr@VView@Art@@@Ofc@@_N@Z; Art::UserInterface::GetCurrentView(bool)
0x1804e5f2e  nop
0x1804e5f2f  mov     rax, [rsp+3D0h+var_358]
0x1804e5f34  cmp     [rax+10h], r13
0x1804e5f38  jnz     loc_1804E60B6
0x1804e5f3e  lea     rcx, [rsp+3D0h+var_358]; struct Ofc::CProxyPtrImpl **
0x1804e5f43  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1804e5f48  mov     rcx, cs:?g_pBitmapClip@Art@@3PEAVBitmap@Gdiplus@@EA; Gdiplus::Bitmap * Art::g_pBitmapClip
0x1804e5f4f  test    rcx, rcx
0x1804e5f52  jnz     loc_1804E621C
0x1804e5f58  lea     rcx, [rsp+3D0h+var_360]; struct Ofc::CProxyPtrImpl **
0x1804e5f5d  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1804e5f62  mov     al, sil
0x1804e5f65  mov     rcx, [rbp+2D0h+var_40]
0x1804e5f6c  xor     rcx, rsp; StackCookie
0x1804e5f6f  call    __security_check_cookie
0x1804e5f74  mov     rbx, [rsp+3D0h+arg_10]
0x1804e5f7c  add     rsp, 3A0h
0x1804e5f83  pop     r15
0x1804e5f85  pop     r14
0x1804e5f87  pop     r13
0x1804e5f89  pop     r12
0x1804e5f8b  pop     rdi
0x1804e5f8c  pop     rsi
0x1804e5f8d  pop     rbp
0x1804e5f8e  retn
0x1804e5f8f  mov     ecx, 12Ch; dwMilliseconds
0x1804e5f94  call    cs:__imp_Sleep
0x1804e5f9a  mov     al, [rbx+1]
0x1804e5f9d  neg     al
0x1804e5f9f  sbb     edx, edx
0x1804e5fa1  neg     edx
0x1804e5fa3  add     edx, 6; nCmdShow
0x1804e5fa6  mov     rcx, r15; hWnd
0x1804e5fa9  call    cs:__imp_ShowWindow
0x1804e5faf  call    cs:__imp_GetTickCount64
0x1804e5fb5  mov     rdi, rax
0x1804e5fb8  xorps   xmm0, xmm0
0x1804e5fbb  movups  xmmword ptr [rbp+2D0h+Msg.hwnd], xmm0
0x1804e5fbf  movups  xmmword ptr [rbp+2D0h+Msg.wParam], xmm0
0x1804e5fc3  movups  xmmword ptr [rbp+2D0h+Msg.time], xmm0
0x1804e5fc7  mov     [rsp+3D0h+yBottom], esi; wRemoveMsg
0x1804e5fcb  xor     r9d, r9d; wMsgFilterMax
0x1804e5fce  xor     r8d, r8d; wMsgFilterMin
0x1804e5fd1  xor     edx, edx; hWnd
0x1804e5fd3  lea     rcx, [rbp+2D0h+Msg]; lpMsg
0x1804e5fd7  call    cs:__imp_PeekMessageW
0x1804e5fdd  test    eax, eax
0x1804e5fdf  jnz     short loc_1804E6004
0x1804e5fe1  call    cs:__imp_GetTickCount64
0x1804e5fe7  mov     rcx, rax
0x1804e5fea  sub     rcx, rdi
0x1804e5fed  cmp     rcx, 5DCh
0x1804e5ff4  jnb     loc_1804E5B7B
0x1804e5ffa  cmp     rdi, rax
0x1804e5ffd  jbe     short loc_1804E5FC7
0x1804e5fff  jmp     loc_1804E5B7B
0x1804e6004  lea     rcx, [rbp+2D0h+Msg]; lpMsg
0x1804e6008  call    cs:__imp_TranslateMessage
  ... truncated ...
```
