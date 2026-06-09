# Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InitializeOnDesktop

- ea: `0x1800aa3b4`
- end: `0x1800aa55c`
- name: `Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InitializeOnDesktop`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800a9adc`

## callees

- `0x180050ba0`
- `0x1800aa020`
- `0x1800aa3b4`
- `0x1800aa90c`

## import_xrefs

- `USER32!CreateWindowInBandEx` at `0x1800aa4a2`
- `USER32!CreateWindowInBandEx` at `0x1800aa4a2`
- `USER32!GetMonitorInfoW` at `0x1800aa438`
- `USER32!GetMonitorInfoW` at `0x1800aa438`
- `USER32!SetPropW` at `0x1800aa4c3`
- `USER32!SetPropW` at `0x1800aa4c3`
- `USER32!CreateWindowExW` at `0x1800aa502`
- `USER32!CreateWindowExW` at `0x1800aa502`
- `USER32!DestroyWindow` at `0x1800aa52b`
- `USER32!DestroyWindow` at `0x1800aa52b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::_anonymous_namespace_::CDimmingWindow::_InitializeOnDesktop(
        __int64 a1,
        DWORD a2,
        const WCHAR *a3,
        const WCHAR *a4,
        DWORD dwStyle,
        __int64 a6,
        int a7,
        HMONITOR hMonitor)
{
  HWND WindowInBand; // rax
  HWND Window; // rax
  struct tagMONITORINFO mi; // [rsp+70h] [rbp-78h] BYREF

  Windows::Internal::_anonymous_namespace_::CDimmingWindow::_RegisterDimmingWindowClass();
  *(_BYTE *)(a1 + 16) = 1;
  memset(&mi, 0, sizeof(mi));
  mi.cbSize = 40;
  GetMonitorInfoW(hMonitor, &mi);
  WindowInBand = (HWND)CreateWindowInBandEx(
                         0x80000,
                         L"Shell_Dim",
                         0,
                         0x80000000LL,
                         mi.rcMonitor.left,
                         mi.rcMonitor.top,
                         mi.rcMonitor.right - mi.rcMonitor.left,
                         mi.rcMonitor.bottom - mi.rcMonitor.top,
                         a6,
                         0,
                         &_ImageBase,
                         a1,
                         0,
                         a7);
  *(_QWORD *)(a1 + 8) = WindowInBand;
  if ( WindowInBand )
  {
    SetPropW(WindowInBand, L"Shell_Dimming_Window_Prop", HANDLE_FLAG_INHERIT);
    Window = CreateWindowExW(
               a2,
               a3,
               a4,
               dwStyle,
               0x80000000,
               0x80000000,
               0x80000000,
               0x80000000,
               *(HWND *)(a1 + 8),
               0,
               &_ImageBase,
               0);
    *(_QWORD *)a1 = Window;
    if ( Window )
    {
      if ( a6 )
        Windows::Internal::_anonymous_namespace_::CWindowWaiter::Wait(a1 + 40, a6, *(_QWORD *)(a1 + 8));
    }
    else
    {
      DestroyWindow(*(HWND *)(a1 + 8));
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x1800aa3b4  push    rbx
0x1800aa3b6  push    rbp
0x1800aa3b7  push    rsi
0x1800aa3b8  push    rdi
0x1800aa3b9  push    r12
0x1800aa3bb  push    r13
0x1800aa3bd  push    r14
0x1800aa3bf  push    r15
0x1800aa3c1  sub     rsp, 0A8h
0x1800aa3c8  mov     rax, cs:__security_cookie
0x1800aa3cf  xor     rax, rsp
0x1800aa3d2  mov     [rsp+0E8h+var_50], rax
0x1800aa3da  mov     r13d, [rsp+0E8h+dwStyle]
0x1800aa3e2  mov     r12, r9
0x1800aa3e5  mov     rbp, [rsp+0E8h+arg_28]
0x1800aa3ed  mov     r15, r8
0x1800aa3f0  mov     edi, [rsp+0E8h+arg_30]
0x1800aa3f7  mov     r14d, edx
0x1800aa3fa  mov     rbx, [rsp+0E8h+hMonitor]
0x1800aa402  mov     rsi, rcx
0x1800aa405  call    Windows__Internal___anonymous_namespace___CDimmingWindow___RegisterDimmingWindowClass
0x1800aa40a  xorps   xmm0, xmm0
0x1800aa40d  mov     byte ptr [rsi+10h], 1
0x1800aa411  xor     eax, eax
0x1800aa413  lea     rdx, [rsp+0E8h+mi]; lpmi
0x1800aa418  movups  xmmword ptr [rsp+0E8h+mi.cbSize], xmm0
0x1800aa41d  mov     rcx, rbx; hMonitor
0x1800aa420  mov     [rsp+0E8h+mi.cbSize], 28h ; '('
0x1800aa428  movups  xmmword ptr [rsp+0E8h+mi.rcMonitor.bottom], xmm0
0x1800aa430  mov     qword ptr [rsp+0E8h+mi.rcWork.bottom], rax
0x1800aa438  call    cs:__imp_GetMonitorInfoW
0x1800aa43e  mov     r8d, [rsp+0E8h+mi.rcMonitor.top]
0x1800aa443  xor     ebx, ebx
0x1800aa445  mov     ecx, [rsp+0E8h+mi.rcMonitor.left]
0x1800aa449  mov     r9d, 80000000h
0x1800aa44f  mov     edx, [rsp+0E8h+mi.rcMonitor.bottom]
0x1800aa456  mov     eax, [rsp+0E8h+mi.rcMonitor.right]
0x1800aa45a  sub     edx, r8d
0x1800aa45d  mov     [rsp+0E8h+var_80], edi
0x1800aa461  sub     eax, ecx
0x1800aa463  mov     [rsp+0E8h+var_88], ebx
0x1800aa467  lea     rdi, __ImageBase
0x1800aa46e  mov     [rsp+0E8h+lpParam], rsi
0x1800aa473  mov     [rsp+0E8h+hInstance], rdi
0x1800aa478  mov     [rsp+0E8h+hMenu], rbx
0x1800aa47d  mov     [rsp+0E8h+hWndParent], rbp
0x1800aa482  mov     [rsp+0E8h+nHeight], edx
0x1800aa486  lea     rdx, aShellDim; "Shell_Dim"
0x1800aa48d  mov     [rsp+0E8h+nWidth], eax
0x1800aa491  mov     [rsp+0E8h+Y], r8d
0x1800aa496  xor     r8d, r8d
0x1800aa499  mov     [rsp+0E8h+X], ecx
0x1800aa49d  mov     ecx, 80000h
0x1800aa4a2  call    cs:__imp_CreateWindowInBandEx
0x1800aa4a8  mov     [rsi+8], rax
0x1800aa4ac  test    rax, rax
0x1800aa4af  jz      loc_1800AA535
0x1800aa4b5  lea     r8d, [rbx+1]; hData
0x1800aa4b9  mov     rcx, rax; hWnd
0x1800aa4bc  lea     rdx, aShellDimmingWi; "Shell_Dimming_Window_Prop"
0x1800aa4c3  call    cs:__imp_SetPropW
0x1800aa4c9  mov     rax, [rsi+8]
0x1800aa4cd  mov     r9d, r13d; dwStyle
0x1800aa4d0  mov     [rsp+0E8h+lpParam], rbx; lpParam
0x1800aa4d5  mov     r8, r12; lpWindowName
0x1800aa4d8  mov     [rsp+0E8h+hInstance], rdi; hInstance
0x1800aa4dd  mov     rdx, r15; lpClassName
0x1800aa4e0  mov     [rsp+0E8h+hMenu], rbx; hMenu
0x1800aa4e5  mov     ecx, r14d; dwExStyle
0x1800aa4e8  mov     [rsp+0E8h+hWndParent], rax; hWndParent
0x1800aa4ed  mov     eax, 80000000h
0x1800aa4f2  mov     [rsp+0E8h+nHeight], eax; nHeight
0x1800aa4f6  mov     [rsp+0E8h+nWidth], eax; nWidth
0x1800aa4fa  mov     [rsp+0E8h+Y], eax; Y
0x1800aa4fe  mov     [rsp+0E8h+X], eax; X
0x1800aa502  call    cs:__imp_CreateWindowExW
0x1800aa508  mov     [rsi], rax
0x1800aa50b  test    rax, rax
0x1800aa50e  jz      short loc_1800AA527
0x1800aa510  test    rbp, rbp
0x1800aa513  jz      short loc_1800AA535
0x1800aa515  mov     r8, [rsi+8]
0x1800aa519  lea     rcx, [rsi+28h]
0x1800aa51d  mov     rdx, rbp
0x1800aa520  call    Windows__Internal___anonymous_namespace___CWindowWaiter__Wait
0x1800aa525  jmp     short loc_1800AA535
0x1800aa527  mov     rcx, [rsi+8]; hWnd
0x1800aa52b  call    cs:__imp_DestroyWindow
0x1800aa531  mov     [rsi+8], rbx
0x1800aa535  mov     rax, [rsi]
0x1800aa538  mov     rcx, [rsp+0E8h+var_50]
0x1800aa540  xor     rcx, rsp; StackCookie
0x1800aa543  call    __security_check_cookie
0x1800aa548  add     rsp, 0A8h
0x1800aa54f  pop     r15
0x1800aa551  pop     r14
0x1800aa553  pop     r13
0x1800aa555  pop     r12
0x1800aa557  pop     rdi
0x1800aa558  pop     rsi
0x1800aa559  pop     rbp
0x1800aa55a  pop     rbx
0x1800aa55b  retn
```
