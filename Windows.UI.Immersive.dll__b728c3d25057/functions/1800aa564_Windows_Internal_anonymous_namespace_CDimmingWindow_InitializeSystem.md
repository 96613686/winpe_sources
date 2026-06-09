# Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InitializeSystem

- ea: `0x1800aa564`
- end: `0x1800aa74f`
- name: `Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InitializeSystem`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180030ef8`

## callees

- `0x180050ba0`
- `0x180051524`
- `0x1800aa0ac`
- `0x1800aa564`

## import_xrefs

- `USER32!CreateWindowInBand` at `0x1800aa683`
- `USER32!CreateWindowInBand` at `0x1800aa683`
- `USER32!GetMonitorInfoW` at `0x1800aa61f`
- `USER32!GetMonitorInfoW` at `0x1800aa61f`
- `USER32!SetPropW` at `0x1800aa6a0`
- `USER32!SetPropW` at `0x1800aa6a0`
- `USER32!CreateWindowExW` at `0x1800aa6fc`
- `USER32!CreateWindowExW` at `0x1800aa6fc`
- `USER32!RegisterClassW` at `0x1800aa5f6`
- `USER32!RegisterClassW` at `0x1800aa5f6`
- `USER32!LoadCursorW` at `0x1800aa5d1`
- `USER32!LoadCursorW` at `0x1800aa5d1`
- `USER32!DestroyWindow` at `0x1800aa71b`
- `USER32!DestroyWindow` at `0x1800aa71b`
- `GDI32!CreateSolidBrush` at `0x1800aa5dd`
- `GDI32!CreateSolidBrush` at `0x1800aa5dd`

## pseudocode

```c
__int64 __fastcall Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InitializeSystem(
        __int64 a1,
        int a2,
        __int64 a3,
        const WCHAR *a4,
        DWORD dwStyle,
        char a6,
        HMONITOR hMonitor,
        char a8)
{
  HWND WindowInBand; // rax
  LONG X; // eax
  LONG Y; // ecx
  WNDCLASSW WndClass; // [rsp+70h] [rbp-79h] BYREF
  struct tagMONITORINFO mi; // [rsp+C0h] [rbp-29h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.style = 512;
  WndClass.lpfnWndProc = (WNDPROC)Windows::Internal::_anonymous_namespace_::CDimmingWindow::s_DimWindowProc;
  WndClass.hInstance = &_ImageBase;
  WndClass.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  WndClass.hbrBackground = CreateSolidBrush(0);
  WndClass.lpszClassName = L"Shell_SystemDim";
  RegisterClassW(&WndClass);
  *(_BYTE *)(a1 + 16) = 1;
  memset(&mi, 0, sizeof(mi));
  mi.cbSize = 40;
  GetMonitorInfoW(hMonitor, &mi);
  WindowInBand = (HWND)CreateWindowInBand(
                         0x80000,
                         L"Shell_SystemDim",
                         0,
                         0x80000000LL,
                         mi.rcMonitor.left,
                         mi.rcMonitor.top,
                         mi.rcMonitor.right - mi.rcMonitor.left,
                         mi.rcMonitor.bottom - mi.rcMonitor.top,
                         0,
                         0,
                         &_ImageBase,
                         a1,
                         a6 != 0 ? 1 : 4);
  *(_QWORD *)(a1 + 8) = WindowInBand;
  if ( WindowInBand )
  {
    SetPropW(WindowInBand, L"Shell_Dimming_Window_Prop", HANDLE_FLAG_INHERIT);
    if ( a8 )
    {
      X = mi.rcMonitor.left;
      Y = mi.rcMonitor.top;
    }
    else
    {
      X = 0x80000000;
      Y = 0x80000000;
    }
    *(_QWORD *)a1 = CreateWindowExW(
                      a2 | 0x40000u,
                      L"Shell_SystemDialog",
                      a4,
                      dwStyle,
                      X,
                      Y,
                      0x80000000,
                      0x80000000,
                      *(HWND *)(a1 + 8),
                      0,
                      &_ImageBase,
                      0);
  }
  if ( *(_QWORD *)a1 )
  {
    Windows::Internal::_anonymous_namespace_::CDimmingWindow::_CreateTaskbarProxyWindow(a1, a4);
  }
  else
  {
    DestroyWindow(*(HWND *)(a1 + 8));
    *(_QWORD *)(a1 + 8) = 0;
  }
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x1800aa564  mov     [rsp-8+arg_10], rbx
0x1800aa569  push    rbp
0x1800aa56a  push    rsi
0x1800aa56b  push    rdi
0x1800aa56c  push    r12
0x1800aa56e  push    r13
0x1800aa570  push    r14
0x1800aa572  push    r15
0x1800aa574  lea     rbp, [rsp-7]
0x1800aa579  sub     rsp, 0F0h
0x1800aa580  mov     rax, cs:__security_cookie
0x1800aa587  xor     rax, rsp
0x1800aa58a  mov     [rbp+37h+var_38], rax
0x1800aa58e  mov     r15d, [rbp+37h+dwStyle]
0x1800aa592  mov     esi, edx
0x1800aa594  mov     rbx, [rbp+37h+hMonitor]
0x1800aa598  xor     edx, edx; Val
0x1800aa59a  mov     rdi, rcx
0x1800aa59d  mov     r14, r9
0x1800aa5a0  lea     rcx, [rbp+37h+WndClass]; void *
0x1800aa5a4  lea     r8d, [rdx+48h]; Size
0x1800aa5a8  call    memset_0
0x1800aa5ad  lea     rax, Windows__Internal___anonymous_namespace___CDimmingWindow__s_DimWindowProc
0x1800aa5b4  mov     [rbp+37h+WndClass.style], 200h
0x1800aa5bb  lea     r13, __ImageBase
0x1800aa5c2  mov     [rbp+37h+WndClass.lpfnWndProc], rax
0x1800aa5c6  mov     edx, 7F00h; lpCursorName
0x1800aa5cb  mov     [rbp+37h+WndClass.hInstance], r13
0x1800aa5cf  xor     ecx, ecx; hInstance
0x1800aa5d1  call    cs:__imp_LoadCursorW
0x1800aa5d7  xor     ecx, ecx; color
0x1800aa5d9  mov     [rbp+37h+WndClass.hCursor], rax
0x1800aa5dd  call    cs:__imp_CreateSolidBrush
0x1800aa5e3  lea     r12, aShellSystemdim; "Shell_SystemDim"
0x1800aa5ea  mov     [rbp+37h+WndClass.hbrBackground], rax
0x1800aa5ee  lea     rcx, [rbp+37h+WndClass]; lpWndClass
0x1800aa5f2  mov     [rbp+37h+WndClass.lpszClassName], r12
0x1800aa5f6  call    cs:__imp_RegisterClassW
0x1800aa5fc  xorps   xmm0, xmm0
0x1800aa5ff  mov     byte ptr [rdi+10h], 1
0x1800aa603  xor     eax, eax
0x1800aa605  lea     rdx, [rbp+37h+mi]; lpmi
0x1800aa609  movups  xmmword ptr [rbp+37h+mi.cbSize], xmm0
0x1800aa60d  mov     rcx, rbx; hMonitor
0x1800aa610  mov     [rbp+37h+mi.cbSize], 28h ; '('
0x1800aa617  movups  xmmword ptr [rbp+37h+mi.rcMonitor.bottom], xmm0
0x1800aa61b  mov     qword ptr [rbp+37h+mi.rcWork.bottom], rax
0x1800aa61f  call    cs:__imp_GetMonitorInfoW
0x1800aa625  mov     r9d, [rbp+37h+mi.rcMonitor.left]
0x1800aa629  mov     rdx, r12
0x1800aa62c  mov     r8d, [rbp+37h+mi.rcMonitor.bottom]
0x1800aa630  mov     r10d, [rbp+37h+mi.rcMonitor.top]
0x1800aa634  mov     ecx, [rbp+37h+mi.rcMonitor.right]
0x1800aa637  neg     [rbp+37h+arg_28]
0x1800aa63a  sbb     eax, eax
0x1800aa63c  sub     ecx, r9d
0x1800aa63f  sub     r8d, r10d
0x1800aa642  and     eax, 0FFFFFFFDh
0x1800aa645  add     eax, 4
0x1800aa648  xor     ebx, ebx
0x1800aa64a  mov     [rsp+120h+var_C0], eax
0x1800aa64e  mov     [rsp+120h+lpParam], rdi
0x1800aa653  mov     [rsp+120h+hInstance], r13
0x1800aa658  mov     [rsp+120h+hMenu], rbx
0x1800aa65d  mov     [rsp+120h+hWndParent], rbx
0x1800aa662  mov     [rsp+120h+nHeight], r8d
0x1800aa667  xor     r8d, r8d
0x1800aa66a  mov     [rsp+120h+nWidth], ecx
0x1800aa66e  mov     ecx, 80000h
0x1800aa673  mov     [rsp+120h+Y], r10d
0x1800aa678  mov     [rsp+120h+X], r9d
0x1800aa67d  mov     r9d, 80000000h
0x1800aa683  call    cs:__imp_CreateWindowInBand
0x1800aa689  mov     [rdi+8], rax
0x1800aa68d  test    rax, rax
0x1800aa690  jz      short loc_1800AA705
0x1800aa692  lea     r8d, [rbx+1]; hData
0x1800aa696  mov     rcx, rax; hWnd
0x1800aa699  lea     rdx, aShellDimmingWi; "Shell_Dimming_Window_Prop"
0x1800aa6a0  call    cs:__imp_SetPropW
0x1800aa6a6  mov     r8d, 80000000h
0x1800aa6ac  mov     rdx, [rdi+8]
0x1800aa6b0  cmp     [rbp+37h+arg_38], bl
0x1800aa6b3  jz      short loc_1800AA6BD
0x1800aa6b5  mov     eax, [rbp+37h+mi.rcMonitor.left]
0x1800aa6b8  mov     ecx, [rbp+37h+mi.rcMonitor.top]
0x1800aa6bb  jmp     short loc_1800AA6C3
0x1800aa6bd  mov     eax, r8d
0x1800aa6c0  mov     ecx, r8d
0x1800aa6c3  mov     [rsp+120h+lpParam], rbx; lpParam
0x1800aa6c8  bts     esi, 12h
0x1800aa6cc  mov     [rsp+120h+hInstance], r13; hInstance
0x1800aa6d1  mov     r9d, r15d; dwStyle
0x1800aa6d4  mov     [rsp+120h+hMenu], rbx; hMenu
0x1800aa6d9  mov     [rsp+120h+hWndParent], rdx; hWndParent
0x1800aa6de  lea     rdx, aShellSystemdia_0; "Shell_SystemDialog"
0x1800aa6e5  mov     [rsp+120h+nHeight], r8d; nHeight
0x1800aa6ea  mov     [rsp+120h+nWidth], r8d; nWidth
0x1800aa6ef  mov     r8, r14; lpWindowName
0x1800aa6f2  mov     [rsp+120h+Y], ecx; Y
0x1800aa6f6  mov     ecx, esi; dwExStyle
0x1800aa6f8  mov     [rsp+120h+X], eax; X
0x1800aa6fc  call    cs:__imp_CreateWindowExW
0x1800aa702  mov     [rdi], rax
0x1800aa705  cmp     [rdi], rbx
0x1800aa708  jz      short loc_1800AA717
0x1800aa70a  mov     rdx, r14
0x1800aa70d  mov     rcx, rdi
0x1800aa710  call    Windows__Internal___anonymous_namespace___CDimmingWindow___CreateTaskbarProxyWindow
0x1800aa715  jmp     short loc_1800AA725
0x1800aa717  mov     rcx, [rdi+8]; hWnd
0x1800aa71b  call    cs:__imp_DestroyWindow
0x1800aa721  mov     [rdi+8], rbx
0x1800aa725  mov     rax, [rdi]
0x1800aa728  mov     rcx, [rbp+37h+var_38]
0x1800aa72c  xor     rcx, rsp; StackCookie
0x1800aa72f  call    __security_check_cookie
0x1800aa734  mov     rbx, [rsp+120h+arg_10]
0x1800aa73c  add     rsp, 0F0h
0x1800aa743  pop     r15
0x1800aa745  pop     r14
0x1800aa747  pop     r13
0x1800aa749  pop     r12
0x1800aa74b  pop     rdi
0x1800aa74c  pop     rsi
0x1800aa74d  pop     rbp
0x1800aa74e  retn
```
