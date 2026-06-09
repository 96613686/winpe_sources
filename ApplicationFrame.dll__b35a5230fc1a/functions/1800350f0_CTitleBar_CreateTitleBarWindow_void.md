# CTitleBar::_CreateTitleBarWindow(void)

- ea: `0x1800350f0`
- end: `0x1800352e0`
- name: `?_CreateTitleBarWindow@CTitleBar@@AEAAJXZ`
- size: `496`
- prototype: `__int64 __fastcall(CTitleBar *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002c164`

## callees

- `0x1800350f0`
- `0x18003fbc0`
- `0x180043c30`

## import_xrefs

- `UxTheme!SetWindowThemeAttribute` at `0x1800352b9`
- `UxTheme!SetWindowThemeAttribute` at `0x1800352b9`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x180035220`
- `ext-ms-win-ntuser-window-l1-1-0!GetClientRect` at `0x180035220`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x180035169`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800351de`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x180035286`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x180035169`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800351de`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x180035286`

## pseudocode

```c
__int64 __fastcall CTitleBar::_CreateTitleBarWindow(CTitleBar *this)
{
  HWND Window; // rax
  const char *v3; // r9
  HWND v5; // rcx
  HWND v6; // rax
  HWND v7; // rcx
  _DWORD pvAttribute[2]; // [rsp+60h] [rbp-28h] BYREF
  struct tagRECT Rect; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *((_QWORD *)this + 65) = CreateWindowExW(
                             0x280000u,
                             L"ApplicationFrameTitleBarWindow",
                             0,
                             0x40030000u,
                             0,
                             0,
                             0,
                             0,
                             *((HWND *)this + 63),
                             0,
                             &_ImageBase,
                             this);
  Window = CreateWindowExW(
             0x280000u,
             L"ApplicationFrameTitleBarWindow",
             0,
             0x40030000u,
             *((_DWORD *)this + 213),
             *((_DWORD *)this + 214),
             *((_DWORD *)this + 215) - *((_DWORD *)this + 213),
             *((_DWORD *)this + 216) - *((_DWORD *)this + 214),
             *((HWND *)this + 63),
             0,
             &_ImageBase,
             this);
  *((_QWORD *)this + 1) = Window;
  if ( !Window )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xF6C,
             (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebar.cpp",
             v3);
  v5 = (HWND)*((_QWORD *)this + 63);
  Rect = 0;
  GetClientRect(v5, &Rect);
  v6 = CreateWindowExW(
         0x280000u,
         L"ApplicationFrameInputSinkWindow",
         0,
         0x40000000u,
         Rect.left,
         Rect.top,
         Rect.right - Rect.left,
         Rect.bottom - Rect.top,
         *((HWND *)this + 63),
         0,
         &_ImageBase,
         this);
  v7 = (HWND)*((_QWORD *)this + 63);
  *((_QWORD *)this + 64) = v6;
  pvAttribute[0] = 65543;
  pvAttribute[1] = 65551;
  SetWindowThemeAttribute(v7, WTA_NONCLIENT, pvAttribute, 8u);
  return 0;
}

```

## disassembly

```asm
0x1800350f0  mov     r11, rsp
0x1800350f3  mov     [r11+10h], rbx
0x1800350f7  push    r14
0x1800350f9  sub     rsp, 80h
0x180035100  mov     rax, cs:__security_cookie
0x180035107  xor     rax, rsp
0x18003510a  mov     [rsp+88h+var_10], rax
0x18003510f  mov     rax, [rcx+1F8h]
0x180035116  lea     r14, __ImageBase
0x18003511d  mov     [r11-30h], rcx
0x180035121  lea     rdx, ClassName; "ApplicationFrameTitleBarWindow"
0x180035128  mov     [r11-38h], r14
0x18003512c  mov     rbx, rcx
0x18003512f  mov     qword ptr [r11-40h], 0
0x180035137  mov     r9d, 40030000h; dwStyle
0x18003513d  mov     [r11-48h], rax
0x180035141  xor     r8d, r8d; lpWindowName
0x180035144  mov     [rsp+88h+nHeight], 0; nHeight
0x18003514c  mov     ecx, 280000h; dwExStyle
0x180035151  mov     [rsp+88h+nWidth], 0; nWidth
0x180035159  mov     [rsp+88h+Y], 0; Y
0x180035161  mov     [rsp+88h+X], 0; X
0x180035169  call    cs:__imp_CreateWindowExW
0x18003516f  mov     [rsp+88h+lpParam], rbx; lpParam
0x180035174  lea     rdx, ClassName; "ApplicationFrameTitleBarWindow"
0x18003517b  mov     [rbx+208h], rax
0x180035182  mov     r9d, 40030000h; dwStyle
0x180035188  mov     r8d, [rbx+360h]
0x18003518f  mov     r11d, [rbx+358h]
0x180035196  sub     r8d, r11d
0x180035199  mov     r10d, [rbx+354h]
0x1800351a0  mov     ecx, [rbx+35Ch]
0x1800351a6  mov     rax, [rbx+1F8h]
0x1800351ad  sub     ecx, r10d
0x1800351b0  mov     [rsp+88h+hInstance], r14; hInstance
0x1800351b5  mov     [rsp+88h+hMenu], 0; hMenu
0x1800351be  mov     [rsp+88h+hWndParent], rax; hWndParent
0x1800351c3  mov     [rsp+88h+nHeight], r8d; nHeight
0x1800351c8  xor     r8d, r8d; lpWindowName
0x1800351cb  mov     [rsp+88h+nWidth], ecx; nWidth
0x1800351cf  mov     ecx, 280000h; dwExStyle
0x1800351d4  mov     [rsp+88h+Y], r11d; Y
0x1800351d9  mov     [rsp+88h+X], r10d; X
0x1800351de  call    cs:__imp_CreateWindowExW
0x1800351e4  mov     [rbx+8], rax
0x1800351e8  test    rax, rax
0x1800351eb  jnz     short loc_18003520B
0x1800351ed  mov     rcx, [rsp+88h]; this
0x1800351f5  lea     r8, aPcshellShellAp_12; "pcshell\\shell\\applicationframe\\frame"...
0x1800351fc  mov     edx, 0F6Ch; void *
0x180035201  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035206  jmp     loc_1800352C1
0x18003520b  mov     rcx, [rbx+1F8h]; hWnd
0x180035212  lea     rdx, [rsp+88h+Rect]; lpRect
0x180035217  xorps   xmm0, xmm0
0x18003521a  movdqu  xmmword ptr [rsp+88h+Rect.left], xmm0
0x180035220  call    cs:__imp_GetClientRect
0x180035226  mov     r8d, [rsp+88h+Rect.left]
0x18003522b  mov     ecx, 280000h; dwExStyle
0x180035230  mov     r10d, [rsp+88h+Rect.top]
0x180035235  mov     edx, [rsp+88h+Rect.right]
0x180035239  mov     r9d, [rsp+88h+Rect.bottom]
0x18003523e  sub     edx, r8d
0x180035241  mov     rax, [rbx+1F8h]
0x180035248  sub     r9d, r10d
0x18003524b  mov     [rsp+88h+lpParam], rbx; lpParam
0x180035250  mov     [rsp+88h+hInstance], r14; hInstance
0x180035255  mov     [rsp+88h+hMenu], 0; hMenu
0x18003525e  mov     [rsp+88h+hWndParent], rax; hWndParent
0x180035263  mov     [rsp+88h+nHeight], r9d; nHeight
0x180035268  mov     r9d, 40000000h; dwStyle
0x18003526e  mov     [rsp+88h+nWidth], edx; nWidth
0x180035272  lea     rdx, aApplicationfra_3; "ApplicationFrameInputSinkWindow"
0x180035279  mov     [rsp+88h+Y], r10d; Y
0x18003527e  mov     [rsp+88h+X], r8d; X
0x180035283  xor     r8d, r8d; lpWindowName
0x180035286  call    cs:__imp_CreateWindowExW
0x18003528c  mov     rcx, [rbx+1F8h]; hwnd
0x180035293  lea     r8, [rsp+88h+pvAttribute]; pvAttribute
0x180035298  mov     r9d, 8; cbAttribute
0x18003529e  mov     [rbx+200h], rax
0x1800352a5  mov     [rsp+88h+pvAttribute], 10007h
0x1800352ad  mov     [rsp+88h+var_24], 1000Fh
0x1800352b5  lea     edx, [r9-7]; eAttribute
0x1800352b9  call    cs:__imp_SetWindowThemeAttribute
0x1800352bf  xor     eax, eax
0x1800352c1  mov     rcx, [rsp+88h+var_10]
0x1800352c6  xor     rcx, rsp; StackCookie
0x1800352c9  call    __security_check_cookie
0x1800352ce  mov     rbx, [rsp+88h+arg_8]
0x1800352d6  add     rsp, 80h
0x1800352dd  pop     r14
0x1800352df  retn
```
