# Windows::Internal::FlyoutWindowTrait::CreatePopupWindow(ulong,ushort const *,ulong,HWND__ *,HMONITOR__ *,POPUP_OPTIONS)

- ea: `0x18009a444`
- end: `0x18009a708`
- name: `?CreatePopupWindow@FlyoutWindowTrait@Internal@Windows@@QEAAPEAUHWND__@@KPEBGKPEAU4@PEAUHMONITOR__@@W4POPUP_OPTIONS@@@Z`
- size: `708`
- prototype: `HWND __high(unsigned int, const unsigned __int16 *, unsigned int, HWND, HMONITOR, enum POPUP_OPTIONS)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180089bb0`

## callees

- `0x18002ebe0`
- `0x180050ba0`
- `0x180051524`
- `0x18009a444`

## import_xrefs

- `USER32!CreateWindowInBandEx` at `0x18009a605`
- `USER32!CreateWindowInBandEx` at `0x18009a605`
- `USER32!GetMonitorInfoW` at `0x18009a59c`
- `USER32!GetMonitorInfoW` at `0x18009a59c`
- `USER32!CreateWindowExW` at `0x18009a679`
- `USER32!CreateWindowExW` at `0x18009a679`
- `USER32!RegisterClassW` at `0x18009a4f5`
- `USER32!RegisterClassW` at `0x18009a4f5`
- `USER32!LoadCursorW` at `0x18009a4d4`
- `USER32!LoadCursorW` at `0x18009a4d4`
- `USER32!GetWindowRect` at `0x18009a621`
- `USER32!GetWindowRect` at `0x18009a621`
- `USER32!SendMessageW` at `0x18009a6df`
- `USER32!SendMessageW` at `0x18009a6df`
- `dwmapi!DwmSetWindowAttribute` at `0x18009a6af`
- `dwmapi!DwmSetWindowAttribute` at `0x18009a6af`

## pseudocode

```c
HWND __fastcall Windows::Internal::FlyoutWindowTrait::CreatePopupWindow(
        __int64 a1,
        DWORD a2,
        const WCHAR *a3,
        DWORD a4,
        HWND hWnd,
        __int64 a6,
        int a7)
{
  DWORD v7; // eax
  bool v8; // zf
  HCURSOR CursorW; // rax
  LONG X; // ebx
  LONG Y; // r15d
  int nWidth; // edi
  int nHeight; // esi
  int v16; // ecx
  int v17; // eax
  int v18; // r14d
  HMONITOR v19; // rcx
  HWND WindowInBand; // rax
  HWND v21; // rbx
  int pvAttribute; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+74h] [rbp-8Ch]
  DWORD dwExStyle; // [rsp+78h] [rbp-88h]
  LPCWSTR lpWindowName; // [rsp+80h] [rbp-80h]
  WNDCLASSW WndClass; // [rsp+90h] [rbp-70h] BYREF
  struct tagRECT Rect; // [rsp+E0h] [rbp-20h] BYREF
  struct tagMONITORINFO mi; // [rsp+F0h] [rbp-10h] BYREF

  v7 = a2 | 0x8000000;
  v8 = *(_BYTE *)(a1 + 8) == 0;
  lpWindowName = a3;
  if ( v8 )
    v7 = a2;
  *(_DWORD *)(a1 + 36) = a7;
  dwExStyle = v7;
  *(_QWORD *)(a1 + 40) = a6;
  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.style = 520;
  WndClass.lpfnWndProc = (WNDPROC)NoUIAWindowProc;
  WndClass.hInstance = &_ImageBase;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  WndClass.hbrBackground = (HBRUSH)6;
  WndClass.hCursor = CursorW;
  WndClass.lpszClassName = L"Shell_Flyout";
  RegisterClassW(&WndClass);
  pvAttribute = a7 & 0x40000000;
  if ( (a7 & 0x40000000) != 0 && (a7 & 0x40000) == 0 )
    a4 |= 0x800000u;
  X = 0x80000000;
  Y = 0x80000000;
  nWidth = 0x80000000;
  nHeight = 0x80000000;
  if ( !hWnd )
  {
    v16 = *(_DWORD *)(a1 + 36);
    v17 = v16 & 0x800000;
    if ( (v16 & 4) != 0 )
    {
      v18 = 1;
    }
    else
    {
      if ( !v17 )
      {
        v18 = (v16 & 0x10000000) != 0 ? 18 : 4;
        goto LABEL_14;
      }
      v18 = 13;
    }
    if ( v17 == 0x800000 )
    {
      v24 = 1;
      goto LABEL_15;
    }
LABEL_14:
    v24 = 0;
LABEL_15:
    v19 = *(HMONITOR *)(a1 + 40);
    if ( v19 )
    {
      if ( *(_BYTE *)(a1 + 49) )
      {
        mi.cbSize = 40;
        memset(&mi.rcMonitor, 0, 36);
        if ( GetMonitorInfoW(v19, &mi) )
        {
          X = mi.rcWork.left;
          nWidth = mi.rcWork.right - mi.rcWork.left;
          Y = mi.rcWork.top;
          nHeight = mi.rcWork.bottom - mi.rcWork.top;
        }
      }
    }
    WindowInBand = (HWND)CreateWindowInBandEx(
                           dwExStyle,
                           L"Shell_Flyout",
                           lpWindowName,
                           a4,
                           X,
                           Y,
                           nWidth,
                           nHeight,
                           0,
                           0,
                           &_ImageBase,
                           0,
                           v18,
                           v24);
    goto LABEL_23;
  }
  if ( *(_BYTE *)(a1 + 48) )
  {
    Rect = 0;
    GetWindowRect(hWnd, &Rect);
    X = Rect.left;
    nWidth = Rect.right - Rect.left;
    Y = Rect.top;
    nHeight = Rect.bottom - Rect.top;
  }
  WindowInBand = CreateWindowExW(
                   dwExStyle,
                   L"Shell_Flyout",
                   lpWindowName,
                   a4,
                   X,
                   Y,
                   nWidth,
                   nHeight,
                   hWnd,
                   0,
                   &_ImageBase,
                   0);
LABEL_23:
  v21 = WindowInBand;
  if ( pvAttribute && (a7 & 0x40000) == 0 )
  {
    pvAttribute = 2;
    DwmSetWindowAttribute(WindowInBand, 0x21u, &pvAttribute, 4u);
  }
  if ( v21 )
  {
    if ( (*(_DWORD *)(a1 + 36) & 0x4000) != 0 )
      SetIhmRequireTouchInEditField(1, v21);
    SendMessageW(v21, 0x127u, 0x30001u, 0);
  }
  return v21;
}

```

## disassembly

```asm
0x18009a444  push    rbp
0x18009a446  push    rbx
0x18009a447  push    rsi
0x18009a448  push    rdi
0x18009a449  push    r12
0x18009a44b  push    r13
0x18009a44d  push    r14
0x18009a44f  push    r15
0x18009a451  lea     rbp, [rsp-28h]
0x18009a456  sub     rsp, 128h
0x18009a45d  mov     rax, cs:__security_cookie
0x18009a464  xor     rax, rsp
0x18009a467  mov     [rbp+60h+var_48], rax
0x18009a46b  mov     ebx, [rbp+60h+arg_30]
0x18009a471  mov     eax, edx
0x18009a473  mov     r14, [rbp+60h+hWnd]
0x18009a47a  bts     eax, 1Bh
0x18009a47e  cmp     byte ptr [rcx+8], 0
0x18009a482  mov     r13, rcx
0x18009a485  mov     [rbp+60h+lpWindowName], r8
0x18009a489  mov     r12d, r9d
0x18009a48c  cmovz   eax, edx
0x18009a48f  mov     [rcx+24h], ebx
0x18009a492  xor     edx, edx; Val
0x18009a494  mov     [rsp+160h+dwExStyle], eax
0x18009a498  mov     rax, [rbp+60h+arg_28]
0x18009a49f  mov     [rcx+28h], rax
0x18009a4a3  lea     rcx, [rbp+60h+WndClass]; void *
0x18009a4a7  lea     r8d, [rdx+48h]; Size
0x18009a4ab  call    memset_0
0x18009a4b0  lea     rax, ?NoUIAWindowProc@@YA_JPEAUHWND__@@I_K_J@Z; NoUIAWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x18009a4b7  mov     [rbp+60h+WndClass.style], 208h
0x18009a4be  mov     [rbp+60h+WndClass.lpfnWndProc], rax
0x18009a4c2  mov     edx, 7F00h; lpCursorName
0x18009a4c7  lea     rax, __ImageBase
0x18009a4ce  xor     ecx, ecx; hInstance
0x18009a4d0  mov     [rbp+60h+WndClass.hInstance], rax
0x18009a4d4  call    cs:__imp_LoadCursorW
0x18009a4da  lea     rcx, [rbp+60h+WndClass]; lpWndClass
0x18009a4de  mov     [rbp+60h+WndClass.hbrBackground], 6
0x18009a4e6  mov     [rbp+60h+WndClass.hCursor], rax
0x18009a4ea  lea     rax, ClassName; "Shell_Flyout"
0x18009a4f1  mov     [rbp+60h+WndClass.lpszClassName], rax
0x18009a4f5  call    cs:__imp_RegisterClassW
0x18009a4fb  mov     eax, ebx
0x18009a4fd  mov     r8d, 800000h
0x18009a503  and     eax, 40000000h
0x18009a508  mov     [rsp+160h+pvAttribute], eax
0x18009a50c  jz      short loc_18009A517
0x18009a50e  bt      ebx, 12h
0x18009a512  jb      short loc_18009A517
0x18009a514  or      r12d, r8d
0x18009a517  mov     ebx, 80000000h
0x18009a51c  xor     edx, edx
0x18009a51e  mov     r15d, ebx
0x18009a521  mov     edi, ebx
0x18009a523  mov     esi, ebx
0x18009a525  lea     r9d, [rdx+1]
0x18009a529  test    r14, r14
0x18009a52c  jnz     loc_18009A60D
0x18009a532  mov     ecx, [r13+24h]
0x18009a536  mov     eax, ecx
0x18009a538  and     eax, r8d
0x18009a53b  test    cl, 4
0x18009a53e  jz      short loc_18009A545
0x18009a540  mov     r14d, r9d
0x18009a543  jmp     short loc_18009A54F
0x18009a545  test    eax, eax
0x18009a547  jz      short loc_18009A55B
0x18009a549  mov     r14d, 0Dh
0x18009a54f  cmp     eax, r8d
0x18009a552  jnz     short loc_18009A56E
0x18009a554  mov     [rsp+160h+var_EC], r9d
0x18009a559  jmp     short loc_18009A572
0x18009a55b  and     ecx, 10000000h
0x18009a561  neg     ecx
0x18009a563  sbb     r14d, r14d
0x18009a566  and     r14d, 0Eh
0x18009a56a  add     r14d, 4
0x18009a56e  mov     [rsp+160h+var_EC], edx
0x18009a572  mov     rcx, [r13+28h]; hMonitor
0x18009a576  test    rcx, rcx
0x18009a579  jz      short loc_18009A5BA
0x18009a57b  cmp     [r13+31h], dl
0x18009a57f  jz      short loc_18009A5BA
0x18009a581  xorps   xmm0, xmm0
0x18009a584  mov     [rbp+60h+mi.cbSize], 28h ; '('
0x18009a58b  xor     eax, eax
0x18009a58d  lea     rdx, [rbp+60h+mi]; lpmi
0x18009a591  movups  xmmword ptr [rbp+60h+mi.rcMonitor.left], xmm0
0x18009a595  mov     [rbp+60h+mi.dwFlags], eax
0x18009a598  movups  xmmword ptr [rbp+60h+mi.rcWork.left], xmm0
0x18009a59c  call    cs:__imp_GetMonitorInfoW
0x18009a5a2  xor     edx, edx
0x18009a5a4  test    eax, eax
0x18009a5a6  jz      short loc_18009A5BA
0x18009a5a8  mov     edi, [rbp+60h+mi.rcWork.right]
0x18009a5ab  mov     ebx, [rbp+60h+mi.rcWork.left]
0x18009a5ae  sub     edi, ebx
0x18009a5b0  mov     esi, [rbp+60h+mi.rcWork.bottom]
0x18009a5b3  mov     r15d, [rbp+60h+mi.rcWork.top]
0x18009a5b7  sub     esi, r15d
0x18009a5ba  mov     eax, [rsp+160h+var_EC]
0x18009a5be  mov     r9d, r12d
0x18009a5c1  mov     r8, [rbp+60h+lpWindowName]
0x18009a5c5  mov     ecx, [rsp+160h+dwExStyle]
0x18009a5c9  mov     [rsp+160h+var_F8], eax
0x18009a5cd  lea     rax, __ImageBase
0x18009a5d4  mov     [rsp+160h+var_100], r14d
0x18009a5d9  mov     [rsp+160h+lpParam], rdx
0x18009a5de  mov     [rsp+160h+hInstance], rax
0x18009a5e3  mov     [rsp+160h+hMenu], rdx
0x18009a5e8  mov     [rsp+160h+hWndParent], rdx
0x18009a5ed  lea     rdx, ClassName; "Shell_Flyout"
0x18009a5f4  mov     [rsp+160h+nHeight], esi
0x18009a5f8  mov     [rsp+160h+nWidth], edi
0x18009a5fc  mov     [rsp+160h+Y], r15d
0x18009a601  mov     [rsp+160h+X], ebx
0x18009a605  call    cs:__imp_CreateWindowInBandEx
0x18009a60b  jmp     short loc_18009A67F
0x18009a60d  cmp     [r13+30h], dl
0x18009a611  jz      short loc_18009A63B
0x18009a613  xorps   xmm0, xmm0
0x18009a616  lea     rdx, [rbp+60h+Rect]; lpRect
0x18009a61a  mov     rcx, r14; hWnd
0x18009a61d  movups  xmmword ptr [rbp+60h+Rect.left], xmm0
0x18009a621  call    cs:__imp_GetWindowRect
0x18009a627  mov     edi, [rbp+60h+Rect.right]
0x18009a62a  mov     esi, [rbp+60h+Rect.bottom]
0x18009a62d  mov     ebx, [rbp+60h+Rect.left]
0x18009a630  sub     edi, ebx
0x18009a632  mov     r15d, [rbp+60h+Rect.top]
0x18009a636  sub     esi, r15d
0x18009a639  xor     edx, edx
0x18009a63b  mov     r8, [rbp+60h+lpWindowName]; lpWindowName
0x18009a63f  lea     rax, __ImageBase
0x18009a646  mov     ecx, [rsp+160h+dwExStyle]; dwExStyle
0x18009a64a  mov     r9d, r12d; dwStyle
0x18009a64d  mov     [rsp+160h+lpParam], rdx; lpParam
0x18009a652  mov     [rsp+160h+hInstance], rax; hInstance
0x18009a657  mov     [rsp+160h+hMenu], rdx; hMenu
0x18009a65c  lea     rdx, ClassName; "Shell_Flyout"
0x18009a663  mov     [rsp+160h+hWndParent], r14; hWndParent
0x18009a668  mov     [rsp+160h+nHeight], esi; nHeight
0x18009a66c  mov     [rsp+160h+nWidth], edi; nWidth
0x18009a670  mov     [rsp+160h+Y], r15d; Y
0x18009a675  mov     [rsp+160h+X], ebx; X
0x18009a679  call    cs:__imp_CreateWindowExW
0x18009a67f  cmp     [rsp+160h+pvAttribute], 0
0x18009a684  mov     rbx, rax
0x18009a687  jz      short loc_18009A6B5
0x18009a689  test    [rbp+60h+arg_30], 40000h
0x18009a693  jnz     short loc_18009A6B5
0x18009a695  mov     r9d, 4; cbAttribute
0x18009a69b  mov     [rsp+160h+pvAttribute], 2
0x18009a6a3  lea     r8, [rsp+160h+pvAttribute]; pvAttribute
0x18009a6a8  mov     rcx, rax; hwnd
0x18009a6ab  lea     edx, [r9+1Dh]; dwAttribute
0x18009a6af  call    cs:__imp_DwmSetWindowAttribute
0x18009a6b5  test    rbx, rbx
0x18009a6b8  jz      short loc_18009A6E5
0x18009a6ba  test    dword ptr [r13+24h], 4000h
0x18009a6c2  jz      short loc_18009A6CE
0x18009a6c4  mov     rdx, rbx; HWND
0x18009a6c7  mov     cl, 1; bool
0x18009a6c9  call    ?SetIhmRequireTouchInEditField@@YA_N_NPEAUHWND__@@@Z; SetIhmRequireTouchInEditField(bool,HWND__ *)
0x18009a6ce  xor     r9d, r9d; lParam
0x18009a6d1  mov     edx, 127h; Msg
0x18009a6d6  mov     r8d, 30001h; wParam
0x18009a6dc  mov     rcx, rbx; hWnd
0x18009a6df  call    cs:__imp_SendMessageW
0x18009a6e5  mov     rax, rbx
0x18009a6e8  mov     rcx, [rbp+60h+var_48]
0x18009a6ec  xor     rcx, rsp; StackCookie
0x18009a6ef  call    __security_check_cookie
0x18009a6f4  add     rsp, 128h
0x18009a6fb  pop     r15
0x18009a6fd  pop     r14
0x18009a6ff  pop     r13
0x18009a701  pop     r12
0x18009a703  pop     rdi
0x18009a704  pop     rsi
0x18009a705  pop     rbx
0x18009a706  pop     rbp
0x18009a707  retn
```
