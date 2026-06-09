# Jot::FirstRun::CFirstRunDialog::SetupWindow(void)

- ea: `0x1803d4500`
- end: `0x1803d4902`
- name: `?SetupWindow@CFirstRunDialog@FirstRun@Jot@@AEAAXXZ`
- size: `1026`
- prototype: `void __fastcall(Jot::FirstRun::CFirstRunDialog *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180786260`

## callees

- `0x1800200e4`
- `0x1800201f4`
- `0x1800934d0`
- `0x1800935c0`
- `0x1802e2251`
- `0x1802e50d0`
- `0x1802e5170`
- `0x1803d1468`
- `0x1803d2abc`
- `0x1803d3314`
- `0x1803d4500`
- `0x1803d4904`
- `0x1803d4c20`
- `0x1803d4ff8`
- `0x1803d5b4c`
- `0x180913b90`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1803d4587`
- `KERNEL32!GetModuleFileNameW` at `0x1803d4587`
- `GDI32!SelectObject` at `0x1803d4865`
- `GDI32!SelectObject` at `0x1803d4871`
- `GDI32!SelectObject` at `0x1803d4865`
- `GDI32!SelectObject` at `0x1803d4871`
- `GDI32!DeleteObject` at `0x1803d47ce`
- `GDI32!DeleteObject` at `0x1803d48dc`
- `GDI32!DeleteObject` at `0x1803d47ce`
- `GDI32!DeleteObject` at `0x1803d48dc`
- `GDI32!CreateCompatibleDC` at `0x1803d4794`
- `GDI32!CreateCompatibleDC` at `0x1803d47a0`
- `GDI32!CreateCompatibleDC` at `0x1803d4794`
- `GDI32!CreateCompatibleDC` at `0x1803d47a0`
- `GDI32!CreateBitmap` at `0x1803d484d`
- `GDI32!CreateBitmap` at `0x1803d484d`
- `GDI32!CreatePatternBrush` at `0x1803d4810`
- `GDI32!CreatePatternBrush` at `0x1803d48cc`
- `GDI32!CreatePatternBrush` at `0x1803d4810`
- `GDI32!CreatePatternBrush` at `0x1803d48cc`
- `GDI32!DeleteDC` at `0x1803d48e8`
- `GDI32!DeleteDC` at `0x1803d48f6`
- `GDI32!DeleteDC` at `0x1803d48e8`
- `GDI32!DeleteDC` at `0x1803d48f6`
- `GDI32!GetObjectW` at `0x1803d474c`
- `GDI32!GetObjectW` at `0x1803d474c`
- `GDI32!StretchBlt` at `0x1803d48c3`
- `GDI32!StretchBlt` at `0x1803d48c3`
- `SHELL32!ExtractIconExW` at `0x1803d47f1`
- `SHELL32!ExtractIconExW` at `0x1803d47f1`
- `USER32!LoadCursorW` at `0x1803d45e7`
- `USER32!LoadCursorW` at `0x1803d45e7`
- `USER32!DefWindowProcW` at `0x1803d45b0`
- `USER32!ShowWindow` at `0x1803d46bf`
- `USER32!ShowWindow` at `0x1803d46bf`
- `USER32!ReleaseDC` at `0x1803d47be`
- `USER32!ReleaseDC` at `0x1803d47be`
- `USER32!GetDC` at `0x1803d4783`
- `USER32!GetDC` at `0x1803d4783`
- `USER32!LoadBitmapW` at `0x1803d4723`
- `USER32!LoadBitmapW` at `0x1803d4723`
- `USER32!GetClassInfoW` at `0x1803d455c`
- `USER32!GetClassInfoW` at `0x1803d455c`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1803d4599`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1803d4599`

## pseudocode

```c
void __fastcall Jot::FirstRun::CFirstRunDialog::SetupWindow(Jot::FirstRun::CFirstRunDialog *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  HWND (*v4)(const void *); // rdx
  LRESULT (__stdcall *p_pv)(HWND, UINT, WPARAM, LPARAM); // rax
  bool v6; // dl
  HINSTANCE v7; // rax
  HBITMAP BitmapW; // rax
  HBITMAP v9; // rsi
  int WindowWidth; // eax
  HDC DC; // rax
  HDC v12; // r14
  HDC hdcSrc; // r12
  HDC CompatibleDC; // rax
  HDC v15; // r15
  int v16; // eax
  int WindowHeight; // ebx
  int v18; // eax
  HBITMAP Bitmap; // r13
  int v20; // ebx
  int v21; // eax
  WNDCLASSEXW v22; // [rsp+68h] [rbp-A0h] BYREF
  struct tagWNDCLASSW WndClass; // [rsp+C8h] [rbp-40h] BYREF
  __int128 pv; // [rsp+118h] [rbp+10h] BYREF
  __int128 v25; // [rsp+128h] [rbp+20h]
  WCHAR Filename[1024]; // [rsp+138h] [rbp+30h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  if ( !GetClassInfoW(0, L"OneNote::CFirstRunDialog", &WndClass) )
  {
    memset_0(Filename, 0, sizeof(Filename));
    if ( GetModuleFileNameW(0, Filename, 0x400u) )
      ExtractIconExW(Filename, 0, (HICON *)this + 73, (HICON *)this + 74, 1u);
    if ( !MsoFCbvHighContrast() )
    {
      if ( (unsigned __int8)Jot::TheResourceDllExists(1) )
      {
        v7 = (HINSTANCE)Jot::TheResourceDll(1);
        BitmapW = LoadBitmapW(v7, (LPCWSTR)0x1E7);
        v9 = BitmapW;
        if ( BitmapW )
        {
          pv = 0;
          v25 = 0;
          GetObjectW(BitmapW, 32, &pv);
          *((float *)this + 54) = (float)SDWORD1(pv);
          *((float *)this + 55) = (float)SDWORD2(pv);
          WindowWidth = Jot::FirstRun::CFirstRunDialog::GetWindowWidth(this);
          if ( DWORD1(pv) == WindowWidth
            && (v16 = Jot::FirstRun::CFirstRunDialog::GetWindowHeight(this), DWORD2(pv) == v16) )
          {
            *((_QWORD *)this + 72) = CreatePatternBrush(v9);
          }
          else
          {
            DC = GetDC(*((HWND *)this + 15));
            v12 = DC;
            if ( DC )
            {
              hdcSrc = CreateCompatibleDC(DC);
              CompatibleDC = CreateCompatibleDC(v12);
              v15 = CompatibleDC;
              if ( hdcSrc )
              {
                if ( CompatibleDC )
                {
                  WindowHeight = Jot::FirstRun::CFirstRunDialog::GetWindowHeight(this);
                  v18 = Jot::FirstRun::CFirstRunDialog::GetWindowWidth(this);
                  Bitmap = CreateBitmap(v18, WindowHeight, (unsigned __int16)v25, WORD1(v25), 0);
                  if ( Bitmap )
                  {
                    SelectObject(hdcSrc, v9);
                    SelectObject(v15, Bitmap);
                    v20 = Jot::FirstRun::CFirstRunDialog::GetWindowHeight(this);
                    v21 = Jot::FirstRun::CFirstRunDialog::GetWindowWidth(this);
                    StretchBlt(v15, 0, 0, v21, v20, hdcSrc, 0, 0, SDWORD1(pv), SDWORD2(pv), 0xCC0020u);
                    *((_QWORD *)this + 72) = CreatePatternBrush(Bitmap);
                    DeleteObject(Bitmap);
                  }
                }
                DeleteDC(hdcSrc);
              }
              if ( v15 )
                DeleteDC(v15);
              ReleaseDC(*((HWND *)this + 15), v12);
            }
          }
          DeleteObject(v9);
        }
      }
    }
    *(_QWORD *)&v22.cbSize = 80;
    v22.lpfnWndProc = DefWindowProcW;
    *(_QWORD *)&v22.cbClsExtra = 0;
    v22.hInstance = 0;
    v22.hIcon = (HICON)*((_QWORD *)this + 73);
    v22.hIconSm = (HICON)*((_QWORD *)this + 74);
    v22.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
    v2 = 5;
    if ( *((_QWORD *)this + 72) )
      v2 = *((_QWORD *)this + 72);
    v22.hbrBackground = (HBRUSH)v2;
    v22.lpszMenuName = 0;
    v22.lpszClassName = L"OneNote::CFirstRunDialog";
    IsolationAwareRegisterClassExW(&v22);
  }
  v3 = Jot::TheResourceDll(0);
  Jot::LoadStringFromResource(&pv, v3, 1346050460);
  *(_QWORD *)&v22.cbSize = L"OneNote::CFirstRunDialog";
  p_pv = (LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM))&pv;
  if ( *((_QWORD *)&v25 + 1) > 7u )
    p_pv = (LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM))pv;
  v22.lpfnWndProc = p_pv;
  v22.cbClsExtra = 0;
  *(_OWORD *)&v22.cbWndExtra = 0x40000u;
  memset((char *)&v22.hIcon + 4, 0, 20);
  MsoCF::CWindow::Create((Jot::FirstRun::CFirstRunDialog *)((char *)this + 112), v4, &v22);
  if ( *((_QWORD *)&v25 + 1) > 7u )
    std::_Deallocate<16>(pv, 2LL * *((_QWORD *)&v25 + 1) + 2);
  Jot::FirstRun::CFirstRunDialog::SetupControls(this);
  Jot::FirstRun::CFirstRunDialog::SetWindowFont(this);
  Jot::FirstRun::CFirstRunDialog::PositionWindow(this, v6);
  ShowWindow(*((HWND *)this + 15), 5);
  Jot::FirstRun::CFirstRunDialog::ClearScreen(this);
  Jot::FirstRun::CFirstRunDialog::Layout(this);
}

```

## disassembly

```asm
0x1803d4500  mov     rax, rsp
0x1803d4503  mov     [rax+10h], rbx
0x1803d4507  mov     [rax+18h], rsi
0x1803d450b  mov     [rax+20h], rdi
0x1803d450f  push    rbp
0x1803d4510  push    r12
0x1803d4512  push    r13
0x1803d4514  push    r14
0x1803d4516  push    r15
0x1803d4518  lea     rbp, [rax-868h]
0x1803d451f  sub     rsp, 940h
0x1803d4526  mov     rax, cs:__security_cookie
0x1803d452d  xor     rax, rsp
0x1803d4530  mov     [rbp+860h+var_30], rax
0x1803d4537  mov     rdi, rcx
0x1803d453a  xor     r13d, r13d
0x1803d453d  xor     edx, edx; Val
0x1803d453f  lea     r8d, [r13+48h]; Size
0x1803d4543  lea     rcx, [rbp+860h+WndClass]; void *
0x1803d4547  call    memset_0
0x1803d454c  lea     r8, [rbp+860h+WndClass]; lpWndClass
0x1803d4550  lea     r14, aOnenoteCfirstr_0; "OneNote::CFirstRunDialog"
0x1803d4557  mov     rdx, r14; lpClassName
0x1803d455a  xor     ecx, ecx; hInstance
0x1803d455c  call    cs:__imp_GetClassInfoW
0x1803d4562  test    eax, eax
0x1803d4564  jnz     loc_1803D461A
0x1803d456a  xor     edx, edx; Val
0x1803d456c  mov     r8d, 800h; Size
0x1803d4572  lea     rcx, [rbp+860h+Filename]; void *
0x1803d4576  call    memset_0
0x1803d457b  mov     r8d, 400h; nSize
0x1803d4581  lea     rdx, [rbp+860h+Filename]; lpFilename
0x1803d4585  xor     ecx, ecx; hModule
0x1803d4587  call    cs:__imp_GetModuleFileNameW
0x1803d458d  lea     ebx, [r13+1]
0x1803d4591  test    eax, eax
0x1803d4593  jnz     loc_1803D47D9
0x1803d4599  call    cs:__imp_?MsoFCbvHighContrast@@YAHXZ; MsoFCbvHighContrast(void)
0x1803d459f  test    eax, eax
0x1803d45a1  jz      loc_1803D4705
0x1803d45a7  mov     qword ptr [rsp+960h+var_900.cbSize], 50h ; 'P'
0x1803d45b0  mov     rax, cs:__imp_DefWindowProcW
0x1803d45b7  mov     [rsp+960h+var_900.lpfnWndProc], rax
0x1803d45bc  mov     qword ptr [rsp+960h+var_900.cbClsExtra], 0
0x1803d45c5  mov     [rsp+960h+var_900.hInstance], r13
0x1803d45ca  mov     rax, [rdi+248h]
0x1803d45d1  mov     [rbp+860h+var_900.hIcon], rax
0x1803d45d5  mov     rax, [rdi+250h]
0x1803d45dc  mov     [rbp+860h+var_900.hIconSm], rax
0x1803d45e0  mov     edx, 7F00h; lpCursorName
0x1803d45e5  xor     ecx, ecx; hInstance
0x1803d45e7  call    cs:__imp_LoadCursorW
0x1803d45ed  mov     [rbp+860h+var_900.hCursor], rax
0x1803d45f1  mov     rcx, [rdi+240h]
0x1803d45f8  mov     eax, 5
0x1803d45fd  test    rcx, rcx
0x1803d4600  cmovnz  rax, rcx
0x1803d4604  mov     [rbp+860h+var_900.hbrBackground], rax
0x1803d4608  mov     [rbp+860h+var_900.lpszMenuName], r13
0x1803d460c  mov     [rbp+860h+var_900.lpszClassName], r14
0x1803d4610  lea     rcx, [rsp+960h+var_900]; WNDCLASSEXW *
0x1803d4615  call    IsolationAwareRegisterClassExW
0x1803d461a  xor     ecx, ecx
0x1803d461c  call    ?TheResourceDll@Jot@@YAPEAUHINSTANCE__@@W4ResourceModule@1@@Z; Jot::TheResourceDll(Jot::ResourceModule)
0x1803d4621  mov     r8d, 503B199Ch
0x1803d4627  mov     rdx, rax
0x1803d462a  lea     rcx, [rbp+860h+pv]
0x1803d462e  call    ?LoadStringFromResource@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z; Jot::LoadStringFromResource(HINSTANCE__ *,uint)
0x1803d4633  nop
0x1803d4634  cmp     qword ptr [rbp+860h+var_840+8], 7
0x1803d4639  setnbe  cl
0x1803d463c  mov     qword ptr [rsp+960h+var_900.cbSize], r14
0x1803d4641  lea     rax, [rbp+860h+pv]
0x1803d4645  test    cl, cl
0x1803d4647  cmovnz  rax, qword ptr [rbp+860h+pv]
0x1803d464c  mov     [rsp+960h+var_900.lpfnWndProc], rax
0x1803d4651  mov     [rsp+960h+var_900.cbClsExtra], r13d
0x1803d4656  mov     qword ptr [rsp+960h+var_900.cbWndExtra], 40000h
0x1803d465f  mov     [rsp+960h+var_900.hInstance+4], 0
0x1803d4668  mov     dword ptr [rbp+860h+var_900.hIcon+4], r13d
0x1803d466c  xorps   xmm0, xmm0
0x1803d466f  movdqu  xmmword ptr [rbp+860h+var_900.hCursor], xmm0
0x1803d4674  lea     rcx, [rdi+70h]; this
0x1803d4678  lea     r8, [rsp+960h+var_900]; void *
0x1803d467d  call    ?Create@CWindow@MsoCF@@IEAAXP6APEAUHWND__@@PEBX@Z0@Z; MsoCF::CWindow::Create(HWND__ * (*)(void const *),void const *)
0x1803d4682  nop
0x1803d4683  mov     rdx, qword ptr [rbp+860h+var_840+8]
0x1803d4687  cmp     rdx, 7
0x1803d468b  jbe     short loc_1803D469E
0x1803d468d  lea     rdx, ds:2[rdx*2]
0x1803d4695  mov     rcx, qword ptr [rbp+860h+pv]
0x1803d4699  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1803d469e  mov     rcx, rdi; this
0x1803d46a1  call    ?SetupControls@CFirstRunDialog@FirstRun@Jot@@AEAAXXZ; Jot::FirstRun::CFirstRunDialog::SetupControls(void)
0x1803d46a6  mov     rcx, rdi; this
0x1803d46a9  call    ?SetWindowFont@CFirstRunDialog@FirstRun@Jot@@AEAAXXZ; Jot::FirstRun::CFirstRunDialog::SetWindowFont(void)
0x1803d46ae  mov     rcx, rdi; this
0x1803d46b1  call    ?PositionWindow@CFirstRunDialog@FirstRun@Jot@@AEAAX_N@Z; Jot::FirstRun::CFirstRunDialog::PositionWindow(bool)
0x1803d46b6  mov     edx, 5; nCmdShow
0x1803d46bb  mov     rcx, [rdi+78h]; hWnd
0x1803d46bf  call    cs:__imp_ShowWindow
0x1803d46c5  mov     rcx, rdi; this
0x1803d46c8  call    ?ClearScreen@CFirstRunDialog@FirstRun@Jot@@AEAAXXZ; Jot::FirstRun::CFirstRunDialog::ClearScreen(void)
0x1803d46cd  mov     rcx, rdi; this
0x1803d46d0  call    ?Layout@CFirstRunDialog@FirstRun@Jot@@AEAAXXZ; Jot::FirstRun::CFirstRunDialog::Layout(void)
0x1803d46d5  mov     rcx, [rbp+860h+var_30]
0x1803d46dc  xor     rcx, rsp; StackCookie
0x1803d46df  call    __security_check_cookie
0x1803d46e4  lea     r11, [rsp+960h+var_20]
0x1803d46ec  mov     rbx, [r11+38h]
0x1803d46f0  mov     rsi, [r11+40h]
0x1803d46f4  mov     rdi, [r11+48h]
0x1803d46f8  mov     rsp, r11
0x1803d46fb  pop     r15
0x1803d46fd  pop     r14
0x1803d46ff  pop     r13
0x1803d4701  pop     r12
0x1803d4703  pop     rbp
0x1803d4704  retn
0x1803d4705  mov     ecx, ebx
0x1803d4707  call    ?TheResourceDllExists@Jot@@YA_NW4ResourceModule@1@@Z; Jot::TheResourceDllExists(Jot::ResourceModule)
0x1803d470c  test    al, al
0x1803d470e  jz      loc_1803D45A7
0x1803d4714  mov     ecx, ebx
0x1803d4716  call    ?TheResourceDll@Jot@@YAPEAUHINSTANCE__@@W4ResourceModule@1@@Z; Jot::TheResourceDll(Jot::ResourceModule)
0x1803d471b  mov     rcx, rax; hInstance
0x1803d471e  mov     edx, 1E7h; lpBitmapName
0x1803d4723  call    cs:__imp_LoadBitmapW
0x1803d4729  mov     rsi, rax
0x1803d472c  test    rax, rax
0x1803d472f  jz      loc_1803D45A7
0x1803d4735  xorps   xmm0, xmm0
0x1803d4738  movups  [rbp+860h+pv], xmm0
0x1803d473c  movups  [rbp+860h+var_840], xmm0
0x1803d4740  lea     r8, [rbp+860h+pv]; pv
0x1803d4744  mov     edx, 20h ; ' '; c
0x1803d4749  mov     rcx, rax; h
0x1803d474c  call    cs:__imp_GetObjectW
0x1803d4752  movd    xmm0, dword ptr [rbp+860h+pv+4]
0x1803d4757  cvtdq2ps xmm0, xmm0
0x1803d475a  movss   dword ptr [rdi+0D8h], xmm0
0x1803d4762  movd    xmm1, dword ptr [rbp+860h+pv+8]
0x1803d4767  cvtdq2ps xmm1, xmm1
0x1803d476a  movss   dword ptr [rdi+0DCh], xmm1
0x1803d4772  mov     rcx, rdi; this
0x1803d4775  call    ?GetWindowWidth@CFirstRunDialog@FirstRun@Jot@@AEAAHXZ; Jot::FirstRun::CFirstRunDialog::GetWindowWidth(void)
0x1803d477a  cmp     dword ptr [rbp+860h+pv+4], eax
0x1803d477d  jz      short loc_1803D47FC
0x1803d477f  mov     rcx, [rdi+78h]; hWnd
0x1803d4783  call    cs:__imp_GetDC
0x1803d4789  mov     r14, rax
0x1803d478c  test    rax, rax
0x1803d478f  jz      short loc_1803D47C4
0x1803d4791  mov     rcx, rax; hdc
0x1803d4794  call    cs:__imp_CreateCompatibleDC
0x1803d479a  mov     r12, rax
0x1803d479d  mov     rcx, r14; hdc
0x1803d47a0  call    cs:__imp_CreateCompatibleDC
0x1803d47a6  mov     r15, rax
0x1803d47a9  test    r12, r12
0x1803d47ac  jnz     short loc_1803D481F
0x1803d47ae  test    r15, r15
0x1803d47b1  jnz     loc_1803D48F3
0x1803d47b7  mov     rdx, r14; hDC
0x1803d47ba  mov     rcx, [rdi+78h]; hWnd
0x1803d47be  call    cs:__imp_ReleaseDC
0x1803d47c4  lea     r14, aOnenoteCfirstr_0; "OneNote::CFirstRunDialog"
0x1803d47cb  mov     rcx, rsi; ho
0x1803d47ce  call    cs:__imp_DeleteObject
0x1803d47d4  jmp     loc_1803D45A7
0x1803d47d9  lea     r9, [rdi+250h]; phiconSmall
0x1803d47e0  lea     r8, [rdi+248h]; phiconLarge
0x1803d47e7  mov     [rsp+960h+nIcons], ebx; nIcons
0x1803d47eb  xor     edx, edx; nIconIndex
0x1803d47ed  lea     rcx, [rbp+860h+Filename]; lpszFile
0x1803d47f1  call    cs:__imp_ExtractIconExW
0x1803d47f7  jmp     loc_1803D4599
0x1803d47fc  mov     rcx, rdi; this
0x1803d47ff  call    ?GetWindowHeight@CFirstRunDialog@FirstRun@Jot@@AEAAHXZ; Jot::FirstRun::CFirstRunDialog::GetWindowHeight(void)
0x1803d4804  cmp     dword ptr [rbp+860h+pv+8], eax
0x1803d4807  jnz     loc_1803D477F
0x1803d480d  mov     rcx, rsi; hbm
0x1803d4810  call    cs:__imp_CreatePatternBrush
0x1803d4816  mov     [rdi+240h], rax
0x1803d481d  jmp     short loc_1803D47CB
0x1803d481f  test    r15, r15
0x1803d4822  jz      loc_1803D48E5
0x1803d4828  mov     rcx, rdi; this
0x1803d482b  call    ?GetWindowHeight@CFirstRunDialog@FirstRun@Jot@@AEAAHXZ; Jot::FirstRun::CFirstRunDialog::GetWindowHeight(void)
0x1803d4830  mov     ebx, eax
0x1803d4832  mov     rcx, rdi; this
0x1803d4835  call    ?GetWindowWidth@CFirstRunDialog@FirstRun@Jot@@AEAAHXZ; Jot::FirstRun::CFirstRunDialog::GetWindowWidth(void)
0x1803d483a  movzx   r9d, word ptr [rbp+860h+var_840+2]; nBitCount
0x1803d483f  movzx   r8d, word ptr [rbp+860h+var_840]; nPlanes
0x1803d4844  mov     qword ptr [rsp+960h+nIcons], r13; lpBits
0x1803d4849  mov     edx, ebx; nHeight
0x1803d484b  mov     ecx, eax; nWidth
0x1803d484d  call    cs:__imp_CreateBitmap
0x1803d4853  mov     r13, rax
0x1803d4856  test    rax, rax
0x1803d4859  jz      loc_1803D48E2
0x1803d485f  mov     rdx, rsi; h
0x1803d4862  mov     rcx, r12; hdc
0x1803d4865  call    cs:__imp_SelectObject
0x1803d486b  mov     rdx, r13; h
0x1803d486e  mov     rcx, r15; hdc
0x1803d4871  call    cs:__imp_SelectObject
0x1803d4877  mov     rcx, rdi; this
0x1803d487a  call    ?GetWindowHeight@CFirstRunDialog@FirstRun@Jot@@AEAAHXZ; Jot::FirstRun::CFirstRunDialog::GetWindowHeight(void)
0x1803d487f  mov     ebx, eax
0x1803d4881  mov     rcx, rdi; this
0x1803d4884  call    ?GetWindowWidth@CFirstRunDialog@FirstRun@Jot@@AEAAHXZ; Jot::FirstRun::CFirstRunDialog::GetWindowWidth(void)
0x1803d4889  mov     [rsp+960h+rop], 0CC0020h; rop
0x1803d4891  mov     ecx, dword ptr [rbp+860h+pv+8]
0x1803d4894  mov     [rsp+960h+hSrc], ecx; hSrc
0x1803d4898  mov     ecx, dword ptr [rbp+860h+pv+4]
0x1803d489b  mov     [rsp+960h+wSrc], ecx; wSrc
0x1803d489f  mov     [rsp+960h+ySrc], 0; ySrc
0x1803d48a7  mov     [rsp+960h+xSrc], 0; xSrc
0x1803d48af  mov     [rsp+960h+hdcSrc], r12; hdcSrc
0x1803d48b4  mov     [rsp+960h+nIcons], ebx; hDest
0x1803d48b8  mov     r9d, eax; wDest
0x1803d48bb  xor     r8d, r8d; yDest
0x1803d48be  xor     edx, edx; xDest
0x1803d48c0  mov     rcx, r15; hdcDest
0x1803d48c3  call    cs:__imp_StretchBlt
0x1803d48c9  mov     rcx, r13; hbm
0x1803d48cc  call    cs:__imp_CreatePatternBrush
0x1803d48d2  mov     [rdi+240h], rax
0x1803d48d9  mov     rcx, r13; ho
0x1803d48dc  call    cs:__imp_DeleteObject
0x1803d48e2  xor     r13d, r13d
0x1803d48e5  mov     rcx, r12; hdc
0x1803d48e8  call    cs:__imp_DeleteDC
0x1803d48ee  jmp     loc_1803D47AE
0x1803d48f3  mov     rcx, r15; hdc
0x1803d48f6  call    cs:__imp_DeleteDC
0x1803d48fc  jmp     loc_1803D47B7
```
