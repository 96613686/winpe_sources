# BasicHwndUtils::GetDescendantFromPointInternal(HWND__ *,tagPOINT,UIA_TIMEOUTDATA &,uint)

- ea: `0x18017ace8`
- end: `0x18017b175`
- name: `?GetDescendantFromPointInternal@BasicHwndUtils@@CAPEAUHWND__@@PEAU2@UtagPOINT@@AEAUUIA_TIMEOUTDATA@@I@Z`
- size: `1165`
- prototype: `HWND __fastcall(HWND, struct tagPOINT, struct UIA_TIMEOUTDATA *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18017ace8`
- `0x1801acf48`

## callees

- `0x180032724`
- `0x18003a640`
- `0x1800db24c`
- `0x18017ace8`
- `0x1801e8320`
- `0x1802c04e0`
- `0x1802c2d88`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x18017af1a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x18017af76`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x18017af1a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowLongW` at `0x18017af76`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18017ad53`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18017ad53`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClientRect` at `0x18017af93`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClientRect` at `0x18017af93`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x18017afa8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x18017afa8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x18017ad3d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x18017ad3d`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowRect` at `0x18017ae49`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowRect` at `0x18017ae49`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18017adbc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18017ade3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18017ae79`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18017ae91`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18017aea9`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18017aecb`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18017adbc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18017ade3`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18017ae79`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18017ae91`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18017aea9`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetPropW` at `0x18017aecb`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x18017adcd`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x18017ae0c`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x18017adcd`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x18017ae0c`
- `ext-ms-win-ntuser-draw-l1-1-2!GetWindowRgn` at `0x18017af34`
- `ext-ms-win-ntuser-draw-l1-1-2!GetWindowRgn` at `0x18017af34`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgn` at `0x18017ad88`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgn` at `0x18017ad88`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-1!PtInRegion` at `0x18017af60`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-1!PtInRegion` at `0x18017af60`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!PtInRect` at `0x18017af04`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!PtInRect` at `0x18017afb5`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!PtInRect` at `0x18017af04`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!PtInRect` at `0x18017afb5`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18017b0f2`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18017b105`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18017b137`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18017b14a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18017b0f2`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18017b105`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18017b137`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18017b14a`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalGetWindow` at `0x18017ada4`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalGetWindow` at `0x18017adf6`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalGetWindow` at `0x18017b0d7`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalGetWindow` at `0x18017ada4`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalGetWindow` at `0x18017adf6`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalGetWindow` at `0x18017b0d7`

## string_xrefs

- `0x18017b113`: `onecore\windows\accessibletech\common\basichwndutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HWND __fastcall BasicHwndUtils::GetDescendantFromPointInternal(
        HWND a1,
        struct tagPOINT a2,
        struct UIA_TIMEOUTDATA *a3,
        unsigned int a4)
{
  __int64 v6; // rcx
  HWND v7; // r12
  HRGN RectRgn; // rbx
  int v9; // r15d
  HWND Window; // rsi
  HWND PropW; // rax
  HWND v12; // rax
  int WindowVisibility; // eax
  int v14; // r15d
  unsigned int v15; // r13d
  int v16; // eax
  int v17; // r15d
  int v18; // eax
  LONG WindowLongW; // eax
  int WindowRgn; // eax
  LONG v21; // r13d
  HWND DescendantFromPointInternal; // r15
  struct UIA_TIMEOUTDATA *v23; // r15
  int v24; // eax
  int v26; // [rsp+20h] [rbp-E0h]
  DWORD dwProcessId; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  LONG left; // [rsp+40h] [rbp-C0h]
  LONG top; // [rsp+44h] [rbp-BCh]
  LONG right; // [rsp+48h] [rbp-B8h]
  unsigned int v32; // [rsp+4Ch] [rbp-B4h]
  int v33; // [rsp+50h] [rbp-B0h]
  struct tagPOINT v34; // [rsp+58h] [rbp-A8h]
  struct UIA_TIMEOUTDATA *v35; // [rsp+60h] [rbp-A0h]
  HRGN v36; // [rsp+68h] [rbp-98h]
  struct tagRECT Rect; // [rsp+70h] [rbp-90h] BYREF
  RECT rc; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ClassName[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v32 = a4;
  v35 = a3;
  v34 = a2;
  if ( a4 >= 0x100 )
  {
    GetClassNameW(a1, ClassName, 260);
    dwProcessId = 0;
    GetWindowThreadProcessId(a1, &dwProcessId);
    MicrosoftTelemetryAssertTriggeredArgs(v6, dwProcessId);
    return 0;
  }
  v7 = 0;
  left = 0;
  top = 0;
  right = 0;
  dwProcessId = 0;
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  v36 = RectRgn;
  v9 = 1024;
  Window = (HWND)InternalGetWindow(a1, 5);
  if ( Window )
    goto LABEL_12;
  PropW = (HWND)GetPropW(a1, L"CrossProcessChildHWND");
  Window = PropW;
  if ( PropW )
  {
    if ( IsWindow(PropW) )
      goto LABEL_12;
    Window = 0;
  }
  if ( GetPropW(a1, L"UIA_UseSiblingAsChildForHitTesting") )
  {
    v12 = (HWND)InternalGetWindow(a1, 2);
    Window = v12;
    if ( v12 )
    {
      if ( v12 == a1 || !IsWindow(v12) )
        Window = 0;
    }
  }
LABEL_12:
  while ( Window )
  {
    v33 = --v9;
    if ( !v9 )
      goto LABEL_61;
    if ( Window == a1 )
      break;
    Rect = 0;
    GetWindowRect(Window, &Rect);
    WindowVisibility = BasicHwndUtils::GetWindowVisibility(Window);
    v14 = WindowVisibility;
    LODWORD(v28) = WindowVisibility;
    if ( !WindowVisibility )
      goto LABEL_48;
    if ( WindowVisibility != 1 )
    {
      v15 = (unsigned int)GetPropW(Window, L"UIA_HWNDXOffset");
      Rect.left += v15;
      *(_QWORD *)&rc.left = GetPropW(Window, L"UIA_HWNDYOffset");
      Rect.top += rc.left;
      v16 = (unsigned int)GetPropW(Window, L"UIA_HWNDWidth");
      v17 = v16;
      if ( v16 > 0 )
        Rect.right = v16 + Rect.left;
      v18 = (unsigned int)GetPropW(Window, L"UIA_HWNDHeight");
      if ( v18 > 0 )
        Rect.bottom = v18 + Rect.top;
      if ( !v15 && !rc.left && !v17 && !v18 )
        goto LABEL_48;
      v14 = v28;
    }
    if ( PtInRect(&Rect, a2) )
    {
      WindowLongW = GetWindowLongW(Window, -20);
      if ( (WindowLongW & 0x80000) == 0 || (WindowLongW & 0x20) == 0 )
      {
        WindowRgn = GetWindowRgn(Window, RectRgn);
        if ( (unsigned int)(WindowRgn - 2) <= 1 )
        {
          if ( !PtInRegion(RectRgn, a2.x - Rect.left, v34.y - Rect.top) )
            goto LABEL_48;
        }
        else if ( WindowRgn == 1 )
        {
          goto LABEL_48;
        }
        v21 = GetWindowLongW(Window, -16);
        if ( (v21 & 0x20000000) == 0 )
        {
          rc = 0;
          GetClientRect(Window, &rc);
          MapWindowPoints(Window, 0, (LPPOINT)&rc, 2u);
          if ( PtInRect(&rc, a2) || v14 != 1 )
          {
            DescendantFromPointInternal = BasicHwndUtils::GetDescendantFromPointInternal(Window, a2, v35, v32 + 1);
            if ( DescendantFromPointInternal )
            {
              if ( RectRgn )
                DeleteObject(RectRgn);
              return DescendantFromPointInternal;
            }
          }
        }
        v28 = 0;
        v23 = v35;
        v24 = BasicHwndUtils::UIASendMessageTimeout(
                v35,
                Window,
                0x84u,
                0,
                LOWORD(a2.x) | (unsigned __int64)(LOWORD(v34.y) << 16),
                &v28);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x69D,
            (unsigned int)"onecore\\windows\\accessibletech\\common\\basichwndutils.cpp",
            (const char *)(unsigned int)v24,
            v26);
        if ( v28 != -1 )
        {
          if ( RectRgn )
            DeleteObject(RectRgn);
          return Window;
        }
        if ( BasicHwndUtils::IsTransparentWindowAccProvider(Window, v21, v23) )
        {
          if ( !v7 )
          {
            left = Rect.left;
            top = Rect.top;
            right = Rect.right;
            dwProcessId = Rect.bottom;
LABEL_47:
            v7 = Window;
            goto LABEL_48;
          }
          if ( Rect.left >= left && Rect.top >= top && Rect.right <= right && Rect.bottom <= (int)dwProcessId )
          {
            left = Rect.left;
            top = Rect.top;
            right = Rect.right;
            dwProcessId = Rect.bottom;
            goto LABEL_47;
          }
        }
      }
    }
LABEL_48:
    Window = (HWND)InternalGetWindow(Window, 2);
    v9 = v33;
  }
  if ( v9 && v7 )
  {
    if ( RectRgn )
      DeleteObject(RectRgn);
    return v7;
  }
LABEL_61:
  if ( RectRgn )
    DeleteObject(RectRgn);
  return 0;
}

```

## disassembly

```asm
0x18017ace8  push    rbp
0x18017acea  push    rbx
0x18017aceb  push    rsi
0x18017acec  push    rdi
0x18017aced  push    r12
0x18017acef  push    r13
0x18017acf1  push    r14
0x18017acf3  push    r15
0x18017acf5  lea     rbp, [rsp-1B8h]
0x18017acfd  sub     rsp, 2B8h
0x18017ad04  mov     rax, cs:__security_cookie
0x18017ad0b  xor     rax, rsp
0x18017ad0e  mov     [rbp+1F0h+var_50], rax
0x18017ad15  mov     [rsp+2F0h+var_2A4], r9d
0x18017ad1a  mov     [rsp+2F0h+var_290], r8
0x18017ad1f  mov     rdi, rdx
0x18017ad22  mov     r14, rcx
0x18017ad25  mov     [rsp+2F0h+var_298], rdx
0x18017ad2a  cmp     r9d, 100h
0x18017ad31  jb      short loc_18017AD67
0x18017ad33  mov     r8d, 104h; nMaxCount
0x18017ad39  lea     rdx, [rbp+1F0h+ClassName]; lpClassName
0x18017ad3d  call    cs:__imp_GetClassNameW
0x18017ad43  mov     [rsp+2F0h+dwProcessId], 0
0x18017ad4b  lea     rdx, [rsp+2F0h+dwProcessId]; lpdwProcessId
0x18017ad50  mov     rcx, r14; hWnd
0x18017ad53  call    cs:__imp_GetWindowThreadProcessId
0x18017ad59  mov     edx, [rsp+2F0h+dwProcessId]
0x18017ad5d  call    MicrosoftTelemetryAssertTriggeredArgs
0x18017ad62  jmp     loc_18017B150
0x18017ad67  xor     r12d, r12d
0x18017ad6a  mov     [rsp+2F0h+var_2B0], r12d
0x18017ad6f  mov     [rsp+2F0h+var_2AC], r12d
0x18017ad74  mov     [rsp+2F0h+var_2A8], r12d
0x18017ad79  mov     [rsp+2F0h+dwProcessId], r12d
0x18017ad7e  xor     r9d, r9d; y2
0x18017ad81  xor     r8d, r8d; x2
0x18017ad84  xor     edx, edx; y1
0x18017ad86  xor     ecx, ecx; x1
0x18017ad88  call    cs:__imp_CreateRectRgn
0x18017ad8e  mov     rbx, rax
0x18017ad91  mov     [rsp+2F0h+var_288], rax
0x18017ad96  lea     edx, [r12+5]
0x18017ad9b  mov     r15d, 400h
0x18017ada1  mov     rcx, r14
0x18017ada4  call    cs:__imp_InternalGetWindow
0x18017adaa  mov     rsi, rax
0x18017adad  test    rax, rax
0x18017adb0  jnz     short loc_18017AE18
0x18017adb2  lea     rdx, aCrossprocessch; "CrossProcessChildHWND"
0x18017adb9  mov     rcx, r14; hWnd
0x18017adbc  call    cs:__imp_GetPropW
0x18017adc2  mov     rsi, rax
0x18017adc5  test    rax, rax
0x18017adc8  jz      short loc_18017ADD9
0x18017adca  mov     rcx, rax; hWnd
0x18017adcd  call    cs:__imp_IsWindow
0x18017add3  test    eax, eax
0x18017add5  jnz     short loc_18017AE18
0x18017add7  xor     esi, esi
0x18017add9  lea     rdx, aUiaUsesiblinga; "UIA_UseSiblingAsChildForHitTesting"
0x18017ade0  mov     rcx, r14; hWnd
0x18017ade3  call    cs:__imp_GetPropW
0x18017ade9  test    rax, rax
0x18017adec  jz      short loc_18017AE18
0x18017adee  mov     edx, 2
0x18017adf3  mov     rcx, r14
0x18017adf6  call    cs:__imp_InternalGetWindow
0x18017adfc  mov     rsi, rax
0x18017adff  test    rax, rax
0x18017ae02  jz      short loc_18017AE18
0x18017ae04  cmp     rax, r14
0x18017ae07  jz      short loc_18017AE16
0x18017ae09  mov     rcx, rax; hWnd
0x18017ae0c  call    cs:__imp_IsWindow
0x18017ae12  test    eax, eax
0x18017ae14  jnz     short loc_18017AE18
0x18017ae16  xor     esi, esi
0x18017ae18  test    rsi, rsi
0x18017ae1b  jz      loc_18017B125
0x18017ae21  sub     r15d, 1
0x18017ae25  mov     [rsp+2F0h+var_2A0], r15d
0x18017ae2a  jz      loc_18017B142
0x18017ae30  cmp     rsi, r14
0x18017ae33  jz      loc_18017B125
0x18017ae39  xorps   xmm0, xmm0
0x18017ae3c  movups  xmmword ptr [rsp+2F0h+Rect.left], xmm0
0x18017ae41  lea     rdx, [rsp+2F0h+Rect]; lpRect
0x18017ae46  mov     rcx, rsi; hWnd
0x18017ae49  call    cs:__imp_GetWindowRect
0x18017ae4f  mov     rcx, rsi
0x18017ae52  call    ?GetWindowVisibility@BasicHwndUtils@@SA?AW4WindowVisibility@1@PEAUHWND__@@@Z; BasicHwndUtils::GetWindowVisibility(HWND__ *)
0x18017ae57  mov     r15d, eax
0x18017ae5a  mov     dword ptr [rsp+2F0h+var_2B8], eax
0x18017ae5e  test    eax, eax
0x18017ae60  jz      loc_18017B0CF
0x18017ae66  cmp     eax, 1
0x18017ae69  jz      loc_18017AEFC
0x18017ae6f  lea     rdx, aUiaHwndxoffset; "UIA_HWNDXOffset"
0x18017ae76  mov     rcx, rsi; hWnd
0x18017ae79  call    cs:__imp_GetPropW
0x18017ae7f  mov     r13, rax
0x18017ae82  add     [rsp+2F0h+Rect.left], r13d
0x18017ae87  lea     rdx, aUiaHwndyoffset; "UIA_HWNDYOffset"
0x18017ae8e  mov     rcx, rsi; hWnd
0x18017ae91  call    cs:__imp_GetPropW
0x18017ae97  mov     qword ptr [rbp+1F0h+rc.left], rax
0x18017ae9b  add     [rsp+2F0h+Rect.top], eax
0x18017ae9f  lea     rdx, aUiaHwndwidth; "UIA_HWNDWidth"
0x18017aea6  mov     rcx, rsi; hWnd
0x18017aea9  call    cs:__imp_GetPropW
0x18017aeaf  mov     r15, rax
0x18017aeb2  test    eax, eax
0x18017aeb4  jle     short loc_18017AEC1
0x18017aeb6  mov     edx, [rsp+2F0h+Rect.left]
0x18017aeba  add     edx, r15d
0x18017aebd  mov     [rsp+2F0h+Rect.right], edx
0x18017aec1  lea     rdx, aUiaHwndheight; "UIA_HWNDHeight"
0x18017aec8  mov     rcx, rsi; hWnd
0x18017aecb  call    cs:__imp_GetPropW
0x18017aed1  test    eax, eax
0x18017aed3  jle     short loc_18017AEDF
0x18017aed5  mov     edx, [rsp+2F0h+Rect.top]
0x18017aed9  add     edx, eax
0x18017aedb  mov     [rsp+2F0h+Rect.bottom], edx
0x18017aedf  test    r13d, r13d
0x18017aee2  jnz     short loc_18017AEF7
0x18017aee4  cmp     [rbp+1F0h+rc.left], r13d
0x18017aee8  jnz     short loc_18017AEF7
0x18017aeea  test    r15d, r15d
0x18017aeed  jnz     short loc_18017AEF7
0x18017aeef  test    eax, eax
0x18017aef1  jz      loc_18017B0CF
0x18017aef7  mov     r15d, dword ptr [rsp+2F0h+var_2B8]
0x18017aefc  mov     rdx, rdi; pt
0x18017aeff  lea     rcx, [rsp+2F0h+Rect]; lprc
0x18017af04  call    cs:__imp_PtInRect
0x18017af0a  test    eax, eax
0x18017af0c  jz      loc_18017B0CF
0x18017af12  mov     edx, 0FFFFFFECh; nIndex
0x18017af17  mov     rcx, rsi; hWnd
0x18017af1a  call    cs:__imp_GetWindowLongW
0x18017af20  bt      eax, 13h
0x18017af24  jnb     short loc_18017AF2E
0x18017af26  test    al, 20h
0x18017af28  jnz     loc_18017B0CF
0x18017af2e  mov     rdx, rbx; hRgn
0x18017af31  mov     rcx, rsi; hWnd
0x18017af34  call    cs:__imp_GetWindowRgn
0x18017af3a  lea     ecx, [rax-2]
0x18017af3d  cmp     ecx, 1
0x18017af40  jbe     short loc_18017AF4D
0x18017af42  cmp     eax, 1
0x18017af45  jz      loc_18017B0CF
0x18017af4b  jmp     short loc_18017AF6E
0x18017af4d  mov     r8d, dword ptr [rsp+2F0h+var_298+4]
0x18017af52  sub     r8d, [rsp+2F0h+Rect.top]; y
0x18017af57  mov     edx, edi
0x18017af59  sub     edx, [rsp+2F0h+Rect.left]; x
0x18017af5d  mov     rcx, rbx; hrgn
0x18017af60  call    cs:__imp_PtInRegion
0x18017af66  test    eax, eax
0x18017af68  jz      loc_18017B0CF
0x18017af6e  mov     edx, 0FFFFFFF0h; nIndex
0x18017af73  mov     rcx, rsi; hWnd
0x18017af76  call    cs:__imp_GetWindowLongW
0x18017af7c  mov     r13d, eax
0x18017af7f  bt      eax, 1Dh
0x18017af83  jb      short loc_18017AFE9
0x18017af85  xorps   xmm0, xmm0
0x18017af88  movups  xmmword ptr [rbp+1F0h+rc.left], xmm0
0x18017af8c  lea     rdx, [rbp+1F0h+rc]; lpRect
0x18017af90  mov     rcx, rsi; hWnd
0x18017af93  call    cs:__imp_GetClientRect
0x18017af99  mov     r9d, 2; cPoints
0x18017af9f  lea     r8, [rbp+1F0h+rc]; lpPoints
0x18017afa3  xor     edx, edx; hWndTo
0x18017afa5  mov     rcx, rsi; hWndFrom
0x18017afa8  call    cs:__imp_MapWindowPoints
0x18017afae  mov     rdx, rdi; pt
0x18017afb1  lea     rcx, [rbp+1F0h+rc]; lprc
0x18017afb5  call    cs:__imp_PtInRect
0x18017afbb  test    eax, eax
0x18017afbd  jnz     short loc_18017AFC5
0x18017afbf  cmp     r15d, 1
0x18017afc3  jz      short loc_18017AFE9
0x18017afc5  mov     r9d, [rsp+2F0h+var_2A4]
0x18017afca  inc     r9d; unsigned int
0x18017afcd  mov     r8, [rsp+2F0h+var_290]; struct UIA_TIMEOUTDATA *
0x18017afd2  mov     rdx, rdi; struct tagPOINT
0x18017afd5  mov     rcx, rsi; HWND
0x18017afd8  call    ?GetDescendantFromPointInternal@BasicHwndUtils@@CAPEAUHWND__@@PEAU2@UtagPOINT@@AEAUUIA_TIMEOUTDATA@@I@Z; BasicHwndUtils::GetDescendantFromPointInternal(HWND__ *,tagPOINT,UIA_TIMEOUTDATA &,uint)
0x18017afdd  mov     r15, rax
0x18017afe0  test    rax, rax
0x18017afe3  jnz     loc_18017B0EA
0x18017afe9  mov     [rsp+2F0h+var_2B8], 0
0x18017aff2  movzx   ecx, word ptr [rsp+2F0h+var_298+4]
0x18017aff7  shl     ecx, 10h
0x18017affa  movzx   eax, di
0x18017affd  or      rcx, rax
0x18017b000  lea     rax, [rsp+2F0h+var_2B8]
0x18017b005  mov     [rsp+2F0h+var_2C8], rax; __int64 *
0x18017b00a  mov     [rsp+2F0h+var_2D0], rcx; int
0x18017b00f  xor     r9d, r9d; unsigned __int64
0x18017b012  mov     r8d, 84h; unsigned int
0x18017b018  mov     rdx, rsi; HWND
0x18017b01b  mov     r15, [rsp+2F0h+var_290]
0x18017b020  mov     rcx, r15; struct UIA_TIMEOUTDATA *
0x18017b023  call    ?UIASendMessageTimeout@BasicHwndUtils@@SAJAEBUUIA_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; BasicHwndUtils::UIASendMessageTimeout(UIA_TIMEOUTDATA const &,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18017b028  mov     rcx, [rbp+1F8h]; this
0x18017b02f  test    eax, eax
0x18017b031  js      loc_18017B110
0x18017b037  cmp     [rsp+2F0h+var_2B8], 0FFFFFFFFFFFFFFFFh
0x18017b03d  jnz     loc_18017B0FD
0x18017b043  mov     r8, r15; struct UIA_TIMEOUTDATA *
0x18017b046  mov     edx, r13d; unsigned int
0x18017b049  mov     rcx, rsi; HWND
0x18017b04c  call    ?IsTransparentWindowAccProvider@BasicHwndUtils@@CA_NPEAUHWND__@@KAEAUUIA_TIMEOUTDATA@@@Z; BasicHwndUtils::IsTransparentWindowAccProvider(HWND__ *,ulong,UIA_TIMEOUTDATA &)
0x18017b051  test    al, al
0x18017b053  jz      short loc_18017B0CF
0x18017b055  test    r12, r12
0x18017b058  jnz     short loc_18017B084
0x18017b05a  mov     r15d, [rsp+2F0h+Rect.left]
0x18017b05f  mov     [rsp+2F0h+var_2B0], r15d
0x18017b064  mov     r15d, [rsp+2F0h+Rect.top]
0x18017b069  mov     [rsp+2F0h+var_2AC], r15d
0x18017b06e  mov     r15d, [rsp+2F0h+Rect.right]
0x18017b073  mov     [rsp+2F0h+var_2A8], r15d
0x18017b078  mov     r15d, [rsp+2F0h+Rect.bottom]
0x18017b07d  mov     [rsp+2F0h+dwProcessId], r15d
0x18017b082  jmp     short loc_18017B0CC
0x18017b084  mov     eax, [rsp+2F0h+var_2B0]
0x18017b088  cmp     [rsp+2F0h+Rect.left], eax
0x18017b08c  jl      short loc_18017B0CF
0x18017b08e  mov     eax, [rsp+2F0h+var_2AC]
0x18017b092  cmp     [rsp+2F0h+Rect.top], eax
0x18017b096  jl      short loc_18017B0CF
0x18017b098  mov     eax, [rsp+2F0h+var_2A8]
0x18017b09c  cmp     [rsp+2F0h+Rect.right], eax
0x18017b0a0  jg      short loc_18017B0CF
0x18017b0a2  mov     eax, [rsp+2F0h+dwProcessId]
0x18017b0a6  cmp     [rsp+2F0h+Rect.bottom], eax
0x18017b0aa  jg      short loc_18017B0CF
0x18017b0ac  mov     eax, [rsp+2F0h+Rect.left]
0x18017b0b0  mov     [rsp+2F0h+var_2B0], eax
0x18017b0b4  mov     eax, [rsp+2F0h+Rect.top]
0x18017b0b8  mov     [rsp+2F0h+var_2AC], eax
0x18017b0bc  mov     eax, [rsp+2F0h+Rect.right]
0x18017b0c0  mov     [rsp+2F0h+var_2A8], eax
0x18017b0c4  mov     eax, [rsp+2F0h+Rect.bottom]
0x18017b0c8  mov     [rsp+2F0h+dwProcessId], eax
0x18017b0cc  mov     r12, rsi
0x18017b0cf  mov     edx, 2
0x18017b0d4  mov     rcx, rsi
0x18017b0d7  call    cs:__imp_InternalGetWindow
0x18017b0dd  mov     rsi, rax
0x18017b0e0  mov     r15d, [rsp+2F0h+var_2A0]
0x18017b0e5  jmp     loc_18017AE18
0x18017b0ea  test    rbx, rbx
0x18017b0ed  jz      short loc_18017B0F8
0x18017b0ef  mov     rcx, rbx; ho
0x18017b0f2  call    cs:__imp_DeleteObject
0x18017b0f8  mov     rax, r15
0x18017b0fb  jmp     short loc_18017B152
0x18017b0fd  test    rbx, rbx
0x18017b100  jz      short loc_18017B10B
0x18017b102  mov     rcx, rbx; ho
0x18017b105  call    cs:__imp_DeleteObject
0x18017b10b  mov     rax, rsi
0x18017b10e  jmp     short loc_18017B152
0x18017b110  mov     r9d, eax; char *
0x18017b113  lea     r8, aOnecoreWindows_88; "onecore\\windows\\accessibletech\\commo"...
0x18017b11a  mov     edx, 69Dh; void *
0x18017b11f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017b125  test    r15d, r15d
0x18017b128  jz      short loc_18017B142
0x18017b12a  test    r12, r12
0x18017b12d  jz      short loc_18017B142
0x18017b12f  test    rbx, rbx
0x18017b132  jz      short loc_18017B13D
0x18017b134  mov     rcx, rbx; ho
0x18017b137  call    cs:__imp_DeleteObject
0x18017b13d  mov     rax, r12
0x18017b140  jmp     short loc_18017B152
0x18017b142  test    rbx, rbx
0x18017b145  jz      short loc_18017B150
0x18017b147  mov     rcx, rbx; ho
0x18017b14a  call    cs:__imp_DeleteObject
0x18017b150  xor     eax, eax
0x18017b152  mov     rcx, [rbp+1F0h+var_50]
0x18017b159  xor     rcx, rsp; StackCookie
0x18017b15c  call    __security_check_cookie
0x18017b161  add     rsp, 2B8h
0x18017b168  pop     r15
0x18017b16a  pop     r14
0x18017b16c  pop     r13
0x18017b16e  pop     r12
0x18017b170  pop     rdi
0x18017b171  pop     rsi
0x18017b172  pop     rbx
  ... truncated ...
```
