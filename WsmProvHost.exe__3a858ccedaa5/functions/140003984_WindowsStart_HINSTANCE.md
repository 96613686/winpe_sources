# WindowsStart(HINSTANCE__ *)

- ea: `0x140003984`
- end: `0x140003ab0`
- name: `?WindowsStart@@YAPEAUHWND__@@PEAUHINSTANCE__@@@Z`
- size: `300`
- prototype: `HWND __fastcall(HINSTANCE hInstance)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140003cf8`

## callees

- `0x1400021cf`
- `0x140003984`

## import_xrefs

- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x140003a75`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x140003a75`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadCursorW` at `0x1400039e2`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadCursorW` at `0x1400039e2`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x1400039cd`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x1400039cd`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x140003a96`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x140003a96`
- `ext-ms-win-ntuser-menu-l1-1-0!GetSystemMenu` at `0x140003a80`
- `ext-ms-win-ntuser-menu-l1-1-0!GetSystemMenu` at `0x140003a80`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x140003a6c`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x140003a6c`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x140003a5e`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x140003a5e`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassW` at `0x140003a15`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassW` at `0x140003a15`

## pseudocode

```c
HWND __fastcall WindowsStart(HINSTANCE hInstance)
{
  HCURSOR CursorW; // rax
  HWND Window; // rbx
  HMENU SystemMenu; // rax
  WNDCLASSW WndClass; // [rsp+60h] [rbp-58h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.style = 3;
  WndClass.lpfnWndProc = (WNDPROC)WindowsMainProc;
  *(_QWORD *)&WndClass.cbClsExtra = 0;
  WndClass.hInstance = hInstance;
  WndClass.hIcon = LoadIconW(0, (LPCWSTR)0x7F01);
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F00);
  *(__m128i *)&WndClass.hbrBackground = _mm_load_si128((const __m128i *)&_xmm);
  WndClass.hCursor = CursorW;
  WndClass.lpszClassName = L"WSMan Provider Host";
  RegisterClassW(&WndClass);
  Window = CreateWindowExW(
             0,
             L"WSMan Provider Host",
             L"WSMan Provider Host",
             0x20CF0000u,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             0,
             0,
             hInstance,
             0);
  ShowWindow(Window, 0);
  UpdateWindow(Window);
  SystemMenu = GetSystemMenu(Window, 0);
  if ( SystemMenu )
    DeleteMenu(SystemMenu, 0xF120u, 0);
  return Window;
}

```

## disassembly

```asm
0x140003984  mov     [rsp+arg_0], rbx
0x140003989  push    rdi
0x14000398a  sub     rsp, 0B0h
0x140003991  xor     edx, edx; Val
0x140003993  mov     rbx, rcx
0x140003996  lea     rcx, [rsp+0B8h+WndClass]; void *
0x14000399b  lea     r8d, [rdx+48h]; Size
0x14000399f  call    memset_0
0x1400039a4  lea     rax, ?WindowsMainProc@@YA_JPEAUHWND__@@I_K_J@Z; WindowsMainProc(HWND__ *,uint,unsigned __int64,__int64)
0x1400039ab  mov     [rsp+0B8h+WndClass.style], 3
0x1400039b3  mov     edx, 7F01h; lpIconName
0x1400039b8  mov     [rsp+0B8h+WndClass.lpfnWndProc], rax
0x1400039bd  xor     ecx, ecx; hInstance
0x1400039bf  mov     qword ptr [rsp+0B8h+WndClass.cbClsExtra], 0
0x1400039c8  mov     [rsp+0B8h+WndClass.hInstance], rbx
0x1400039cd  call    cs:__imp_LoadIconW
0x1400039d3  mov     edx, 7F00h; lpCursorName
0x1400039d8  xor     ecx, ecx; hInstance
0x1400039da  mov     [rsp+0B8h+WndClass.hIcon], rax
0x1400039e2  call    cs:__imp_LoadCursorW
0x1400039e8  movdqa  xmm0, cs:__xmm@00000000000000000000000000000006
0x1400039f0  lea     rdi, ClassName; "WSMan Provider Host"
0x1400039f7  lea     rcx, [rsp+0B8h+WndClass]; lpWndClass
0x1400039fc  movdqa  xmmword ptr [rsp+0B8h+WndClass.hbrBackground], xmm0
0x140003a05  mov     [rsp+0B8h+WndClass.hCursor], rax
0x140003a0d  mov     [rsp+0B8h+WndClass.lpszClassName], rdi
0x140003a15  call    cs:__imp_RegisterClassW
0x140003a1b  mov     [rsp+0B8h+lpParam], 0; lpParam
0x140003a24  mov     eax, 80000000h
0x140003a29  mov     [rsp+0B8h+hInstance], rbx; hInstance
0x140003a2e  mov     r9d, 20CF0000h; dwStyle
0x140003a34  mov     [rsp+0B8h+hMenu], 0; hMenu
0x140003a3d  mov     r8, rdi; lpWindowName
0x140003a40  mov     [rsp+0B8h+hWndParent], 0; hWndParent
0x140003a49  mov     rdx, rdi; lpClassName
0x140003a4c  mov     [rsp+0B8h+nHeight], eax; nHeight
0x140003a50  xor     ecx, ecx; dwExStyle
0x140003a52  mov     [rsp+0B8h+nWidth], eax; nWidth
0x140003a56  mov     [rsp+0B8h+Y], eax; Y
0x140003a5a  mov     [rsp+0B8h+X], eax; X
0x140003a5e  call    cs:__imp_CreateWindowExW
0x140003a64  mov     rcx, rax; hWnd
0x140003a67  xor     edx, edx; nCmdShow
0x140003a69  mov     rbx, rax
0x140003a6c  call    cs:__imp_ShowWindow
0x140003a72  mov     rcx, rbx; hWnd
0x140003a75  call    cs:__imp_UpdateWindow
0x140003a7b  xor     edx, edx; bRevert
0x140003a7d  mov     rcx, rbx; hWnd
0x140003a80  call    cs:__imp_GetSystemMenu
0x140003a86  test    rax, rax
0x140003a89  jz      short loc_140003A9C
0x140003a8b  xor     r8d, r8d; uFlags
0x140003a8e  mov     edx, 0F120h; uPosition
0x140003a93  mov     rcx, rax; hMenu
0x140003a96  call    cs:__imp_DeleteMenu
0x140003a9c  mov     rax, rbx
0x140003a9f  mov     rbx, [rsp+0B8h+arg_0]
0x140003aa7  add     rsp, 0B0h
0x140003aae  pop     rdi
0x140003aaf  retn
```
