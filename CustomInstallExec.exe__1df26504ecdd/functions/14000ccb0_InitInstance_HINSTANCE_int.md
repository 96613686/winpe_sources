# InitInstance(HINSTANCE__ *,int)

- ea: `0x14000ccb0`
- end: `0x14000cde4`
- name: `?InitInstance@@YAHPEAUHINSTANCE__@@H@Z`
- size: `308`
- prototype: `__int64 __fastcall(HINSTANCE hInstance, int nCmdShow)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000d884`

## callees

- `0x1400033b0`
- `0x14000ccb0`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000cd94`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000cd94`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x14000cdae`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x14000cdae`
- `ext-ms-win-ntuser-sysparams-ext-l1-1-0!GetSystemMetrics` at `0x14000cd0b`
- `ext-ms-win-ntuser-sysparams-ext-l1-1-0!GetSystemMetrics` at `0x14000cd26`
- `ext-ms-win-ntuser-sysparams-ext-l1-1-0!GetSystemMetrics` at `0x14000cd0b`
- `ext-ms-win-ntuser-sysparams-ext-l1-1-0!GetSystemMetrics` at `0x14000cd26`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x14000cdb7`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x14000cdb7`
- `ext-ms-win-ntuser-window-l1-1-0!AdjustWindowRectEx` at `0x14000ccf8`
- `ext-ms-win-ntuser-window-l1-1-0!AdjustWindowRectEx` at `0x14000ccf8`

## pseudocode

```c
__int64 __fastcall InitInstance(HINSTANCE hInstance, int nCmdShow)
{
  int Y; // ebx
  int SystemMetrics; // eax
  HWND Window; // rax
  HWND v7; // rbx
  tagRECT Rect; // [rsp+60h] [rbp-38h] BYREF

  g_instance = hInstance;
  Rect = (tagRECT)_mm_load_si128((const __m128i *)&_xmm);
  if ( !AdjustWindowRectEx(&Rect, 0xC80000u, 0, 0) )
    return 0;
  Y = GetSystemMetrics(1) / 2 - Rect.bottom / 2;
  SystemMetrics = GetSystemMetrics(0);
  Window = CreateWindowExW(
             0,
             &g_windowClass,
             &g_title,
             0xC80000u,
             SystemMetrics / 2 - Rect.right / 2,
             Y,
             Rect.right - Rect.left,
             Rect.bottom - Rect.top,
             0,
             0,
             hInstance,
             0);
  v7 = Window;
  if ( !Window )
    return 0;
  g_mainWindow = Window;
  ShowWindow(Window, nCmdShow);
  UpdateWindow(v7);
  return 1;
}

```

## disassembly

```asm
0x14000ccb0  mov     [rsp+arg_10], rbx
0x14000ccb5  push    rbp
0x14000ccb6  push    rsi
0x14000ccb7  push    rdi
0x14000ccb8  sub     rsp, 80h
0x14000ccbf  mov     rax, cs:__security_cookie
0x14000ccc6  xor     rax, rsp
0x14000ccc9  mov     [rsp+98h+var_28], rax
0x14000ccce  movdqa  xmm0, cs:__xmm@000000b4000001f40000000000000000
0x14000ccd6  mov     edi, edx
0x14000ccd8  mov     rsi, rcx
0x14000ccdb  mov     cs:?g_instance@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_instance
0x14000cce2  mov     edx, 0C80000h; dwStyle
0x14000cce7  lea     rcx, [rsp+98h+Rect]; lpRect
0x14000ccec  xor     r9d, r9d; dwExStyle
0x14000ccef  xor     r8d, r8d; bMenu
0x14000ccf2  movdqu  xmmword ptr [rsp+98h+Rect.left], xmm0
0x14000ccf8  call    cs:__imp_AdjustWindowRectEx
0x14000ccfe  test    eax, eax
0x14000cd00  jz      loc_14000CDC2
0x14000cd06  mov     ecx, 1; nIndex
0x14000cd0b  call    cs:__imp_GetSystemMetrics
0x14000cd11  mov     ebp, 2
0x14000cd16  xor     ecx, ecx; nIndex
0x14000cd18  cdq
0x14000cd19  idiv    ebp
0x14000cd1b  mov     ebx, eax
0x14000cd1d  mov     eax, [rsp+98h+Rect.bottom]
0x14000cd21  cdq
0x14000cd22  idiv    ebp
0x14000cd24  sub     ebx, eax
0x14000cd26  call    cs:__imp_GetSystemMetrics
0x14000cd2c  mov     r8d, [rsp+98h+Rect.bottom]
0x14000cd31  mov     r9d, 0C80000h; dwStyle
0x14000cd37  sub     r8d, [rsp+98h+Rect.top]
0x14000cd3c  cdq
0x14000cd3d  idiv    ebp
0x14000cd3f  mov     [rsp+98h+lpParam], 0; lpParam
0x14000cd48  mov     r10d, eax
0x14000cd4b  mov     [rsp+98h+hInstance], rsi; hInstance
0x14000cd50  mov     eax, [rsp+98h+Rect.right]
0x14000cd54  mov     ecx, eax
0x14000cd56  sub     ecx, [rsp+98h+Rect.left]
0x14000cd5a  cdq
0x14000cd5b  mov     [rsp+98h+hMenu], 0; hMenu
0x14000cd64  idiv    ebp
0x14000cd66  mov     [rsp+98h+hWndParent], 0; hWndParent
0x14000cd6f  lea     rdx, ?g_windowClass@@3PAGA; lpClassName
0x14000cd76  mov     [rsp+98h+nHeight], r8d; nHeight
0x14000cd7b  sub     r10d, eax
0x14000cd7e  mov     [rsp+98h+nWidth], ecx; nWidth
0x14000cd82  lea     r8, ?g_title@@3PAGA; lpWindowName
0x14000cd89  mov     [rsp+98h+Y], ebx; Y
0x14000cd8d  xor     ecx, ecx; dwExStyle
0x14000cd8f  mov     [rsp+98h+X], r10d; X
0x14000cd94  call    cs:__imp_CreateWindowExW
0x14000cd9a  mov     rbx, rax
0x14000cd9d  test    rax, rax
0x14000cda0  jz      short loc_14000CDC2
0x14000cda2  mov     edx, edi; nCmdShow
0x14000cda4  mov     cs:?g_mainWindow@@3PEAUHWND__@@EA, rax; HWND__ * g_mainWindow
0x14000cdab  mov     rcx, rax; hWnd
0x14000cdae  call    cs:__imp_ShowWindow
0x14000cdb4  mov     rcx, rbx; hWnd
0x14000cdb7  call    cs:__imp_UpdateWindow
0x14000cdbd  lea     eax, [rbp-1]
0x14000cdc0  jmp     short loc_14000CDC4
0x14000cdc2  xor     eax, eax
0x14000cdc4  mov     rcx, [rsp+98h+var_28]
0x14000cdc9  xor     rcx, rsp; StackCookie
0x14000cdcc  call    __security_check_cookie
0x14000cdd1  mov     rbx, [rsp+98h+arg_10]
0x14000cdd9  add     rsp, 80h
0x14000cde0  pop     rdi
0x14000cde1  pop     rsi
0x14000cde2  pop     rbp
0x14000cde3  retn
```
