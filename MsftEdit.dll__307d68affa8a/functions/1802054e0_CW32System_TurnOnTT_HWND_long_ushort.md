# CW32System::TurnOnTT(HWND__ *,long,ushort *)

- ea: `0x1802054e0`
- end: `0x180205762`
- name: `?TurnOnTT@CW32System@@SAPEAUHWND__@@PEAU2@JPEAG@Z`
- size: `642`
- prototype: `HWND __fastcall(HWND hWndParent, int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007a5ec`
- `0x1800b3400`

## callees

- `0x180071a84`
- `0x180079678`
- `0x1800eca80`
- `0x1800ff674`
- `0x18013bad0`
- `0x18013c916`
- `0x1802054e0`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180205581`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180205581`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180205568`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180205568`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x180205632`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x180205632`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x180205600`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x180205600`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x180205521`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x180205521`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x180205699`
- `ext-ms-win-gdi-font-l1-1-0!CreateFontIndirectW` at `0x180205699`
- `ext-ms-win-ntuser-mouse-l1-1-0!GetDoubleClickTime` at `0x1802056d6`
- `ext-ms-win-ntuser-mouse-l1-1-0!GetDoubleClickTime` at `0x1802056d6`

## string_xrefs

- `0x180205561`: `COMCTL32.DLL`
- `0x180205577`: `InitCommonControlsEx`

## pseudocode

```c
HWND __fastcall CW32System::TurnOnTT(HWND hWndParent, int a2, unsigned __int16 *a3)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  const unsigned __int16 *FontName; // rax
  HFONT v9; // rax
  UINT DoubleClickTime; // eax
  _DWORD v12[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v13[3]; // [rsp+70h] [rbp-90h] BYREF
  struct tagRECT Rect; // [rsp+88h] [rbp-78h] BYREF
  HINSTANCE v15; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v16; // [rsp+A0h] [rbp-60h]
  LOGFONTW lf; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(v13, 0, 0x48u);
  GetClientRect(hWndParent, &Rect);
  v15 = hinstRE;
  v13[0] = 0x100000002CLL;
  v13[1] = (__int64)hWndParent;
  v13[2] = 0;
  v16 = a3;
  if ( CW32System::_hwndTT )
  {
    if ( CW32System::_cpMostURL )
      CW32System::TurnOffTT();
LABEL_9:
    CW32System::SendMessage(CW32System::_hwndTT, 0x433u, 0, (__int64)v13);
    if ( a2 == -1 )
    {
      memset_0(&lf, 0, sizeof(lf));
      FontName = CFICache::GetFontName(5);
      CopyLFFontName(&lf, FontName, 0);
      v9 = CreateFontIndirectW(&lf);
      CW32System::SendMessage(CW32System::_hwndTT, 0x30u, (unsigned __int64)v9, 0);
    }
    if ( !CW32System::SendMessage(CW32System::_hwndTT, 0x432u, 0, (__int64)v13) )
      return 0;
    DoubleClickTime = GetDoubleClickTime();
    CW32System::SendMessage(CW32System::_hwndTT, 0x403u, 3u, DoubleClickTime / 5);
    CW32System::SendMessage(CW32System::_hwndTT, 0x403u, 2u, 1000);
    CW32System::SendMessage(CW32System::_hwndTT, 0x411u, 1u, (__int64)v13);
    CW32System::_cpMostURL = a2;
    return CW32System::_hwndTT;
  }
  ModuleHandleW = GetModuleHandleW(L"COMCTL32.DLL");
  if ( !ModuleHandleW )
    return 0;
  ProcAddress = GetProcAddress(ModuleHandleW, "InitCommonControlsEx");
  if ( !ProcAddress )
    return 0;
  v12[0] = 8;
  v12[1] = 4;
  if ( !((unsigned int (__fastcall *)(_DWORD *))ProcAddress)(v12) )
    return 0;
  CW32System::_hwndTT = CreateWindowExW(
                          0,
                          L"tooltips_class32",
                          &WindowName,
                          0x80000000,
                          0x80000000,
                          0x80000000,
                          0x80000000,
                          0x80000000,
                          hWndParent,
                          0,
                          hinstRE,
                          0);
  SetWindowPos(CW32System::_hwndTT, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x213u);
  if ( a2 == -1 )
    goto LABEL_9;
  return CW32System::_hwndTT;
}

```

## disassembly

```asm
0x1802054e0  mov     [rsp-8+arg_8], rbx
0x1802054e5  push    rbp
0x1802054e6  push    rsi
0x1802054e7  push    rdi
0x1802054e8  lea     rbp, [rsp-30h]
0x1802054ed  sub     rsp, 130h
0x1802054f4  mov     rax, cs:__security_cookie
0x1802054fb  xor     rax, rsp
0x1802054fe  mov     [rbp+40h+var_20], rax
0x180205502  mov     edi, edx
0x180205504  mov     rbx, r8
0x180205507  xor     edx, edx; Val
0x180205509  mov     rsi, rcx
0x18020550c  lea     rcx, [rsp+140h+var_D0]; void *
0x180205511  lea     r8d, [rdx+48h]; Size
0x180205515  call    memset_0
0x18020551a  lea     rdx, [rbp+40h+Rect]; lpRect
0x18020551e  mov     rcx, rsi; hWnd
0x180205521  call    cs:__imp_GetClientRect
0x180205527  cmp     cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA, 0; HWND__ * CW32System::_hwndTT
0x18020552f  mov     rax, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hinstRE
0x180205536  mov     [rbp+40h+var_A8], rax
0x18020553a  mov     dword ptr [rsp+140h+var_D0], 2Ch ; ','
0x180205542  mov     dword ptr [rsp+140h+var_D0+4], 10h
0x18020554a  mov     [rsp+140h+var_C8], rsi
0x18020554f  mov     [rbp+40h+var_C0], 0
0x180205557  mov     [rbp+40h+var_A0], rbx
0x18020555b  jnz     loc_180205643
0x180205561  lea     rcx, aComctl32Dll; "COMCTL32.DLL"
0x180205568  call    cs:__imp_GetModuleHandleW
0x18020556e  test    rax, rax
0x180205571  jz      loc_1802056D2
0x180205577  lea     rdx, aInitcommoncont; "InitCommonControlsEx"
0x18020557e  mov     rcx, rax; hModule
0x180205581  call    cs:__imp_GetProcAddress
0x180205587  test    rax, rax
0x18020558a  jz      loc_1802056D2
0x180205590  lea     rcx, [rsp+140h+var_E0]
0x180205595  mov     [rsp+140h+var_E0], 8
0x18020559d  mov     [rsp+140h+var_DC], 4
0x1802055a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802055aa  test    eax, eax
0x1802055ac  jz      loc_1802056D2
0x1802055b2  mov     rax, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hinstRE
0x1802055b9  lea     r8, WindowName; lpWindowName
0x1802055c0  mov     [rsp+140h+lpParam], 0; lpParam
0x1802055c9  lea     rdx, aTooltipsClass3; "tooltips_class32"
0x1802055d0  mov     [rsp+140h+hInstance], rax; hInstance
0x1802055d5  mov     r9d, 80000000h; dwStyle
0x1802055db  mov     [rsp+140h+hMenu], 0; hMenu
0x1802055e4  mov     eax, 80000000h
0x1802055e9  mov     [rsp+140h+hWndParent], rsi; hWndParent
0x1802055ee  xor     ecx, ecx; dwExStyle
0x1802055f0  mov     [rsp+140h+nHeight], eax; nHeight
0x1802055f4  mov     [rsp+140h+nWidth], eax; nWidth
0x1802055f8  mov     [rsp+140h+Y], eax; Y
0x1802055fc  mov     [rsp+140h+X], eax; X
0x180205600  call    cs:__imp_CreateWindowExW
0x180205606  mov     [rsp+140h+nWidth], 213h; uFlags
0x18020560e  xor     r9d, r9d; Y
0x180205611  mov     rcx, rax; hWnd
0x180205614  mov     [rsp+140h+Y], 0; cy
0x18020561c  xor     r8d, r8d; X
0x18020561f  mov     cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA, rax; HWND__ * CW32System::_hwndTT
0x180205626  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x18020562a  mov     [rsp+140h+X], 0; cx
0x180205632  call    cs:__imp_SetWindowPos
0x180205638  cmp     edi, 0FFFFFFFFh
0x18020563b  jnz     loc_18020573C
0x180205641  jmp     short loc_180205651
0x180205643  cmp     cs:?_cpMostURL@CW32System@@2JA, 0; long CW32System::_cpMostURL
0x18020564a  jz      short loc_180205651
0x18020564c  call    ?TurnOffTT@CW32System@@SAXXZ; CW32System::TurnOffTT(void)
0x180205651  mov     rcx, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; hWnd
0x180205658  lea     r9, [rsp+140h+var_D0]; __int64
0x18020565d  xor     r8d, r8d; unsigned __int64
0x180205660  mov     edx, 433h; unsigned int
0x180205665  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x18020566a  cmp     edi, 0FFFFFFFFh
0x18020566d  jnz     short loc_1802056B4
0x18020566f  xor     edx, edx; Val
0x180205671  lea     r8d, [rdi+5Dh]; Size
0x180205675  lea     rcx, [rbp+40h+lf]; void *
0x180205679  call    memset_0
0x18020567e  lea     ecx, [rdi+6]; __int16
0x180205681  call    ?GetFontName@CFICache@@SAPEBGF@Z; CFICache::GetFontName(short)
0x180205686  mov     rdx, rax; unsigned __int16 *
0x180205689  lea     rcx, [rbp+40h+lf]; struct tagLOGFONTW *
0x18020568d  xor     r8d, r8d; bool
0x180205690  call    ?CopyLFFontName@@YAXAEAUtagLOGFONTW@@PEBG_N@Z; CopyLFFontName(tagLOGFONTW &,ushort const *,bool)
0x180205695  lea     rcx, [rbp+40h+lf]; lplf
0x180205699  call    cs:__imp_CreateFontIndirectW
0x18020569f  mov     rcx, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; hWnd
0x1802056a6  lea     edx, [rdi+31h]; unsigned int
0x1802056a9  mov     r8, rax; unsigned __int64
0x1802056ac  xor     r9d, r9d; __int64
0x1802056af  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x1802056b4  mov     rcx, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; hWnd
0x1802056bb  lea     r9, [rsp+140h+var_D0]; __int64
0x1802056c0  xor     r8d, r8d; unsigned __int64
0x1802056c3  mov     edx, 432h; unsigned int
0x1802056c8  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x1802056cd  test    rax, rax
0x1802056d0  jnz     short loc_1802056D6
0x1802056d2  xor     eax, eax
0x1802056d4  jmp     short loc_180205743
0x1802056d6  call    cs:__imp_GetDoubleClickTime
0x1802056dc  mov     ebx, 403h
0x1802056e1  mov     r8d, 3; unsigned __int64
0x1802056e7  mov     ecx, eax
0x1802056e9  mov     eax, 0CCCCCCCDh
0x1802056ee  mul     ecx
0x1802056f0  mov     rcx, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; hWnd
0x1802056f7  shr     edx, 2
0x1802056fa  mov     r9d, edx; __int64
0x1802056fd  mov     edx, ebx; unsigned int
0x1802056ff  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x180205704  mov     rcx, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; hWnd
0x18020570b  lea     r9d, [rbx-1Bh]; __int64
0x18020570f  mov     r8d, 2; unsigned __int64
0x180205715  mov     edx, ebx; unsigned int
0x180205717  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x18020571c  mov     rcx, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; hWnd
0x180205723  lea     r9, [rsp+140h+var_D0]; __int64
0x180205728  lea     edx, [rbx+0Eh]; unsigned int
0x18020572b  mov     r8d, 1; unsigned __int64
0x180205731  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x180205736  mov     cs:?_cpMostURL@CW32System@@2JA, edi; long CW32System::_cpMostURL
0x18020573c  mov     rax, cs:?_hwndTT@CW32System@@2PEAUHWND__@@EA; HWND__ * CW32System::_hwndTT
0x180205743  mov     rcx, [rbp+40h+var_20]
0x180205747  xor     rcx, rsp; StackCookie
0x18020574a  call    __security_check_cookie
0x18020574f  mov     rbx, [rsp+140h+arg_8]
0x180205757  add     rsp, 130h
0x18020575e  pop     rdi
0x18020575f  pop     rsi
0x180205760  pop     rbp
0x180205761  retn
```
