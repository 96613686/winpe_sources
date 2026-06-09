# BasicHwndUtils::GetDescendantFromPointInternal(HWND__ *,tagPOINT,UIA_TIMEOUTDATA &,uint)

- ea: `0x180022fbc`
- end: `0x180023448`
- name: `?GetDescendantFromPointInternal@BasicHwndUtils@@CAPEAUHWND__@@PEAU2@UtagPOINT@@AEAUUIA_TIMEOUTDATA@@I@Z`
- size: `1164`
- prototype: `HWND __fastcall(HWND, struct tagPOINT, struct UIA_TIMEOUTDATA *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022f10`
- `0x180022fbc`

## callees

- `0x180022fbc`
- `0x180023d0c`
- `0x180031540`
- `0x180043680`
- `0x18007b8a0`
- `0x18007bdc4`
- `0x180089f6c`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x1800231ee`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x180023249`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x1800231ee`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x180023249`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x180023011`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x180023011`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18002311d`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x18002311d`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180023027`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180023027`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800230a1`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800230e0`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800230a1`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x1800230e0`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x180023090`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x1800230b7`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18002314d`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x180023165`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18002317d`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18002319f`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x180023090`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x1800230b7`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18002314d`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x180023165`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18002317d`
- `ext-ms-win-ntuser-window-l1-1-0!GetPropW` at `0x18002319f`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgn` at `0x18002305c`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgn` at `0x18002305c`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-1!PtInRegion` at `0x180023233`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-1!PtInRegion` at `0x180023233`
- `ext-ms-win-ntuser-draw-l1-1-2!GetWindowRgn` at `0x180023208`
- `ext-ms-win-ntuser-draw-l1-1-2!GetWindowRgn` at `0x180023208`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!PtInRect` at `0x1800231d8`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!PtInRect` at `0x180023288`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!PtInRect` at `0x1800231d8`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!PtInRect` at `0x180023288`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClientRect` at `0x180023266`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClientRect` at `0x180023266`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x18002327b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!MapWindowPoints` at `0x18002327b`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800233c5`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800233d8`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18002340a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18002341d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800233c5`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800233d8`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18002340a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18002341d`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalGetWindow` at `0x180023078`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalGetWindow` at `0x1800230ca`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalGetWindow` at `0x1800233aa`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalGetWindow` at `0x180023078`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalGetWindow` at `0x1800230ca`
- `api-ms-win-rtcore-ntuser-private-l1-1-1!__imp_InternalGetWindow` at `0x1800233aa`

## string_xrefs

- `0x1800233e6`: `onecore\windows\accessibletech\common\basichwndutils.cpp`

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
  tagRECT Rect; // [rsp+70h] [rbp-90h] BYREF
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
0x180022fbc  push    rbp
0x180022fbe  push    rbx
0x180022fbf  push    rsi
0x180022fc0  push    rdi
0x180022fc1  push    r12
0x180022fc3  push    r13
0x180022fc5  push    r14
0x180022fc7  push    r15
0x180022fc9  lea     rbp, [rsp-1B8h]
0x180022fd1  sub     rsp, 2B8h
0x180022fd8  mov     rax, cs:__security_cookie
0x180022fdf  xor     rax, rsp
0x180022fe2  mov     [rbp+1F0h+var_50], rax
0x180022fe9  mov     [rsp+2F0h+var_2A4], r9d
0x180022fee  mov     [rsp+2F0h+var_290], r8
0x180022ff3  mov     rdi, rdx
0x180022ff6  mov     r14, rcx
0x180022ff9  mov     [rsp+2F0h+var_298], rdx
0x180022ffe  cmp     r9d, 100h
0x180023005  jb      short loc_18002303B
0x180023007  mov     r8d, 104h; nMaxCount
0x18002300d  lea     rdx, [rbp+1F0h+ClassName]; lpClassName
0x180023011  call    cs:__imp_GetClassNameW
0x180023017  mov     [rsp+2F0h+dwProcessId], 0
0x18002301f  lea     rdx, [rsp+2F0h+dwProcessId]; lpdwProcessId
0x180023024  mov     rcx, r14; hWnd
0x180023027  call    cs:__imp_GetWindowThreadProcessId
0x18002302d  mov     edx, [rsp+2F0h+dwProcessId]
0x180023031  call    MicrosoftTelemetryAssertTriggeredArgs
0x180023036  jmp     loc_180023423
0x18002303b  xor     r12d, r12d
0x18002303e  mov     [rsp+2F0h+var_2B0], r12d
0x180023043  mov     [rsp+2F0h+var_2AC], r12d
0x180023048  mov     [rsp+2F0h+var_2A8], r12d
0x18002304d  mov     [rsp+2F0h+dwProcessId], r12d
0x180023052  xor     r9d, r9d; y2
0x180023055  xor     r8d, r8d; x2
0x180023058  xor     edx, edx; y1
0x18002305a  xor     ecx, ecx; x1
0x18002305c  call    cs:__imp_CreateRectRgn
0x180023062  mov     rbx, rax
0x180023065  mov     [rsp+2F0h+var_288], rax
0x18002306a  lea     edx, [r12+5]
0x18002306f  mov     r15d, 400h
0x180023075  mov     rcx, r14
0x180023078  call    cs:__imp_InternalGetWindow
0x18002307e  mov     rsi, rax
0x180023081  test    rax, rax
0x180023084  jnz     short loc_1800230EC
0x180023086  lea     rdx, String; "CrossProcessChildHWND"
0x18002308d  mov     rcx, r14; hWnd
0x180023090  call    cs:__imp_GetPropW
0x180023096  mov     rsi, rax
0x180023099  test    rax, rax
0x18002309c  jz      short loc_1800230AD
0x18002309e  mov     rcx, rax; hWnd
0x1800230a1  call    cs:__imp_IsWindow
0x1800230a7  test    eax, eax
0x1800230a9  jnz     short loc_1800230EC
0x1800230ab  xor     esi, esi
0x1800230ad  lea     rdx, aUiaUsesiblinga; "UIA_UseSiblingAsChildForHitTesting"
0x1800230b4  mov     rcx, r14; hWnd
0x1800230b7  call    cs:__imp_GetPropW
0x1800230bd  test    rax, rax
0x1800230c0  jz      short loc_1800230EC
0x1800230c2  mov     edx, 2
0x1800230c7  mov     rcx, r14
0x1800230ca  call    cs:__imp_InternalGetWindow
0x1800230d0  mov     rsi, rax
0x1800230d3  test    rax, rax
0x1800230d6  jz      short loc_1800230EC
0x1800230d8  cmp     rax, r14
0x1800230db  jz      short loc_1800230EA
0x1800230dd  mov     rcx, rax; hWnd
0x1800230e0  call    cs:__imp_IsWindow
0x1800230e6  test    eax, eax
0x1800230e8  jnz     short loc_1800230EC
0x1800230ea  xor     esi, esi
0x1800230ec  test    rsi, rsi
0x1800230ef  jz      loc_1800233F8
0x1800230f5  sub     r15d, 1
0x1800230f9  mov     [rsp+2F0h+var_2A0], r15d
0x1800230fe  jz      loc_180023415
0x180023104  cmp     rsi, r14
0x180023107  jz      loc_1800233F8
0x18002310d  xorps   xmm0, xmm0
0x180023110  movups  xmmword ptr [rsp+2F0h+Rect.left], xmm0
0x180023115  lea     rdx, [rsp+2F0h+Rect]; lpRect
0x18002311a  mov     rcx, rsi; hWnd
0x18002311d  call    cs:__imp_GetWindowRect
0x180023123  mov     rcx, rsi
0x180023126  call    ?GetWindowVisibility@BasicHwndUtils@@SA?AW4WindowVisibility@1@PEAUHWND__@@@Z; BasicHwndUtils::GetWindowVisibility(HWND__ *)
0x18002312b  mov     r15d, eax
0x18002312e  mov     dword ptr [rsp+2F0h+var_2B8], eax
0x180023132  test    eax, eax
0x180023134  jz      loc_1800233A2
0x18002313a  cmp     eax, 1
0x18002313d  jz      loc_1800231D0
0x180023143  lea     rdx, aUiaHwndxoffset; "UIA_HWNDXOffset"
0x18002314a  mov     rcx, rsi; hWnd
0x18002314d  call    cs:__imp_GetPropW
0x180023153  mov     r13, rax
0x180023156  add     [rsp+2F0h+Rect.left], r13d
0x18002315b  lea     rdx, aUiaHwndyoffset; "UIA_HWNDYOffset"
0x180023162  mov     rcx, rsi; hWnd
0x180023165  call    cs:__imp_GetPropW
0x18002316b  mov     qword ptr [rbp+1F0h+rc.left], rax
0x18002316f  add     [rsp+2F0h+Rect.top], eax
0x180023173  lea     rdx, aUiaHwndwidth; "UIA_HWNDWidth"
0x18002317a  mov     rcx, rsi; hWnd
0x18002317d  call    cs:__imp_GetPropW
0x180023183  mov     r15, rax
0x180023186  test    eax, eax
0x180023188  jle     short loc_180023195
0x18002318a  mov     edx, [rsp+2F0h+Rect.left]
0x18002318e  add     edx, r15d
0x180023191  mov     [rsp+2F0h+Rect.right], edx
0x180023195  lea     rdx, aUiaHwndheight; "UIA_HWNDHeight"
0x18002319c  mov     rcx, rsi; hWnd
0x18002319f  call    cs:__imp_GetPropW
0x1800231a5  test    eax, eax
0x1800231a7  jle     short loc_1800231B3
0x1800231a9  mov     edx, [rsp+2F0h+Rect.top]
0x1800231ad  add     edx, eax
0x1800231af  mov     [rsp+2F0h+Rect.bottom], edx
0x1800231b3  test    r13d, r13d
0x1800231b6  jnz     short loc_1800231CB
0x1800231b8  cmp     [rbp+1F0h+rc.left], r13d
0x1800231bc  jnz     short loc_1800231CB
0x1800231be  test    r15d, r15d
0x1800231c1  jnz     short loc_1800231CB
0x1800231c3  test    eax, eax
0x1800231c5  jz      loc_1800233A2
0x1800231cb  mov     r15d, dword ptr [rsp+2F0h+var_2B8]
0x1800231d0  mov     rdx, rdi; pt
0x1800231d3  lea     rcx, [rsp+2F0h+Rect]; lprc
0x1800231d8  call    cs:__imp_PtInRect
0x1800231de  test    eax, eax
0x1800231e0  jz      loc_1800233A2
0x1800231e6  mov     edx, 0FFFFFFECh; nIndex
0x1800231eb  mov     rcx, rsi; hWnd
0x1800231ee  call    cs:__imp_GetWindowLongW
0x1800231f4  bt      eax, 13h
0x1800231f8  jnb     short loc_180023202
0x1800231fa  test    al, 20h
0x1800231fc  jnz     loc_1800233A2
0x180023202  mov     rdx, rbx; hRgn
0x180023205  mov     rcx, rsi; hWnd
0x180023208  call    cs:__imp_GetWindowRgn
0x18002320e  lea     ecx, [rax-2]
0x180023211  cmp     ecx, 1
0x180023214  jbe     short loc_180023220
0x180023216  cmp     eax, 1
0x180023219  jnz     short loc_180023241
0x18002321b  jmp     loc_1800233A2
0x180023220  mov     r8d, dword ptr [rsp+2F0h+var_298+4]
0x180023225  sub     r8d, [rsp+2F0h+Rect.top]; y
0x18002322a  mov     edx, edi
0x18002322c  sub     edx, [rsp+2F0h+Rect.left]; x
0x180023230  mov     rcx, rbx; hrgn
0x180023233  call    cs:__imp_PtInRegion
0x180023239  test    eax, eax
0x18002323b  jz      loc_1800233A2
0x180023241  mov     edx, 0FFFFFFF0h; nIndex
0x180023246  mov     rcx, rsi; hWnd
0x180023249  call    cs:__imp_GetWindowLongW
0x18002324f  mov     r13d, eax
0x180023252  bt      eax, 1Dh
0x180023256  jb      short loc_1800232BC
0x180023258  xorps   xmm0, xmm0
0x18002325b  movups  xmmword ptr [rbp+1F0h+rc.left], xmm0
0x18002325f  lea     rdx, [rbp+1F0h+rc]; lpRect
0x180023263  mov     rcx, rsi; hWnd
0x180023266  call    cs:__imp_GetClientRect
0x18002326c  mov     r9d, 2; cPoints
0x180023272  lea     r8, [rbp+1F0h+rc]; lpPoints
0x180023276  xor     edx, edx; hWndTo
0x180023278  mov     rcx, rsi; hWndFrom
0x18002327b  call    cs:__imp_MapWindowPoints
0x180023281  mov     rdx, rdi; pt
0x180023284  lea     rcx, [rbp+1F0h+rc]; lprc
0x180023288  call    cs:__imp_PtInRect
0x18002328e  test    eax, eax
0x180023290  jnz     short loc_180023298
0x180023292  cmp     r15d, 1
0x180023296  jz      short loc_1800232BC
0x180023298  mov     r9d, [rsp+2F0h+var_2A4]
0x18002329d  inc     r9d; unsigned int
0x1800232a0  mov     r8, [rsp+2F0h+var_290]; struct UIA_TIMEOUTDATA *
0x1800232a5  mov     rdx, rdi; struct tagPOINT
0x1800232a8  mov     rcx, rsi; HWND
0x1800232ab  call    ?GetDescendantFromPointInternal@BasicHwndUtils@@CAPEAUHWND__@@PEAU2@UtagPOINT@@AEAUUIA_TIMEOUTDATA@@I@Z; BasicHwndUtils::GetDescendantFromPointInternal(HWND__ *,tagPOINT,UIA_TIMEOUTDATA &,uint)
0x1800232b0  mov     r15, rax
0x1800232b3  test    rax, rax
0x1800232b6  jnz     loc_1800233BD
0x1800232bc  mov     [rsp+2F0h+var_2B8], 0
0x1800232c5  movzx   ecx, word ptr [rsp+2F0h+var_298+4]
0x1800232ca  shl     ecx, 10h
0x1800232cd  movzx   eax, di
0x1800232d0  or      rcx, rax
0x1800232d3  lea     rax, [rsp+2F0h+var_2B8]
0x1800232d8  mov     [rsp+2F0h+var_2C8], rax; __int64 *
0x1800232dd  mov     [rsp+2F0h+var_2D0], rcx; int
0x1800232e2  xor     r9d, r9d; unsigned __int64
0x1800232e5  mov     r8d, 84h; unsigned int
0x1800232eb  mov     rdx, rsi; HWND
0x1800232ee  mov     r15, [rsp+2F0h+var_290]
0x1800232f3  mov     rcx, r15; struct UIA_TIMEOUTDATA *
0x1800232f6  call    ?UIASendMessageTimeout@BasicHwndUtils@@SAJAEBUUIA_TIMEOUTDATA@@PEAUHWND__@@I_K_JPEA_J@Z; BasicHwndUtils::UIASendMessageTimeout(UIA_TIMEOUTDATA const &,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x1800232fb  mov     rcx, [rbp+1F8h]; this
0x180023302  test    eax, eax
0x180023304  js      loc_1800233E3
0x18002330a  cmp     [rsp+2F0h+var_2B8], 0FFFFFFFFFFFFFFFFh
0x180023310  jnz     loc_1800233D0
0x180023316  mov     r8, r15; struct UIA_TIMEOUTDATA *
0x180023319  mov     edx, r13d; unsigned int
0x18002331c  mov     rcx, rsi; HWND
0x18002331f  call    ?IsTransparentWindowAccProvider@BasicHwndUtils@@CA_NPEAUHWND__@@KAEAUUIA_TIMEOUTDATA@@@Z; BasicHwndUtils::IsTransparentWindowAccProvider(HWND__ *,ulong,UIA_TIMEOUTDATA &)
0x180023324  test    al, al
0x180023326  jz      short loc_1800233A2
0x180023328  test    r12, r12
0x18002332b  jnz     short loc_180023357
0x18002332d  mov     r15d, [rsp+2F0h+Rect.left]
0x180023332  mov     [rsp+2F0h+var_2B0], r15d
0x180023337  mov     r15d, [rsp+2F0h+Rect.top]
0x18002333c  mov     [rsp+2F0h+var_2AC], r15d
0x180023341  mov     r15d, [rsp+2F0h+Rect.right]
0x180023346  mov     [rsp+2F0h+var_2A8], r15d
0x18002334b  mov     r15d, [rsp+2F0h+Rect.bottom]
0x180023350  mov     [rsp+2F0h+dwProcessId], r15d
0x180023355  jmp     short loc_18002339F
0x180023357  mov     eax, [rsp+2F0h+var_2B0]
0x18002335b  cmp     [rsp+2F0h+Rect.left], eax
0x18002335f  jl      short loc_1800233A2
0x180023361  mov     eax, [rsp+2F0h+var_2AC]
0x180023365  cmp     [rsp+2F0h+Rect.top], eax
0x180023369  jl      short loc_1800233A2
0x18002336b  mov     eax, [rsp+2F0h+var_2A8]
0x18002336f  cmp     [rsp+2F0h+Rect.right], eax
0x180023373  jg      short loc_1800233A2
0x180023375  mov     eax, [rsp+2F0h+dwProcessId]
0x180023379  cmp     [rsp+2F0h+Rect.bottom], eax
0x18002337d  jg      short loc_1800233A2
0x18002337f  mov     eax, [rsp+2F0h+Rect.left]
0x180023383  mov     [rsp+2F0h+var_2B0], eax
0x180023387  mov     eax, [rsp+2F0h+Rect.top]
0x18002338b  mov     [rsp+2F0h+var_2AC], eax
0x18002338f  mov     eax, [rsp+2F0h+Rect.right]
0x180023393  mov     [rsp+2F0h+var_2A8], eax
0x180023397  mov     eax, [rsp+2F0h+Rect.bottom]
0x18002339b  mov     [rsp+2F0h+dwProcessId], eax
0x18002339f  mov     r12, rsi
0x1800233a2  mov     edx, 2
0x1800233a7  mov     rcx, rsi
0x1800233aa  call    cs:__imp_InternalGetWindow
0x1800233b0  mov     rsi, rax
0x1800233b3  mov     r15d, [rsp+2F0h+var_2A0]
0x1800233b8  jmp     loc_1800230EC
0x1800233bd  test    rbx, rbx
0x1800233c0  jz      short loc_1800233CB
0x1800233c2  mov     rcx, rbx; ho
0x1800233c5  call    cs:__imp_DeleteObject
0x1800233cb  mov     rax, r15
0x1800233ce  jmp     short loc_180023425
0x1800233d0  test    rbx, rbx
0x1800233d3  jz      short loc_1800233DE
0x1800233d5  mov     rcx, rbx; ho
0x1800233d8  call    cs:__imp_DeleteObject
0x1800233de  mov     rax, rsi
0x1800233e1  jmp     short loc_180023425
0x1800233e3  mov     r9d, eax; char *
0x1800233e6  lea     r8, aOnecoreWindows_10; "onecore\\windows\\accessibletech\\commo"...
0x1800233ed  mov     edx, 69Dh; void *
0x1800233f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800233f8  test    r15d, r15d
0x1800233fb  jz      short loc_180023415
0x1800233fd  test    r12, r12
0x180023400  jz      short loc_180023415
0x180023402  test    rbx, rbx
0x180023405  jz      short loc_180023410
0x180023407  mov     rcx, rbx; ho
0x18002340a  call    cs:__imp_DeleteObject
0x180023410  mov     rax, r12
0x180023413  jmp     short loc_180023425
0x180023415  test    rbx, rbx
0x180023418  jz      short loc_180023423
0x18002341a  mov     rcx, rbx; ho
0x18002341d  call    cs:__imp_DeleteObject
0x180023423  xor     eax, eax
0x180023425  mov     rcx, [rbp+1F0h+var_50]
0x18002342c  xor     rcx, rsp; StackCookie
0x18002342f  call    __security_check_cookie
0x180023434  add     rsp, 2B8h
0x18002343b  pop     r15
0x18002343d  pop     r14
0x18002343f  pop     r13
0x180023441  pop     r12
0x180023443  pop     rdi
0x180023444  pop     rsi
0x180023445  pop     rbx
  ... truncated ...
```
