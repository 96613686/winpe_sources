# WindowsInit(HINSTANCE__ *)

- ea: `0x140025f74`
- end: `0x1400260a0`
- name: `?WindowsInit@@YAPEAUHWND__@@PEAUHINSTANCE__@@@Z`
- size: `300`
- prototype: `HWND __fastcall(HINSTANCE hInstance)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14002e680`

## callees

- `0x140025f74`
- `0x14002ba53`

## import_xrefs

- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x140026065`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x140026065`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x140025fbd`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x140025fbd`
- `ext-ms-win-ntuser-menu-l1-1-0!GetSystemMenu` at `0x140026070`
- `ext-ms-win-ntuser-menu-l1-1-0!GetSystemMenu` at `0x140026070`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x140026086`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x140026086`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x14002604e`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x14002604e`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x14002605c`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x14002605c`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassW` at `0x140026005`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassW` at `0x140026005`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x140025fd2`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x140025fd2`

## pseudocode

```c
HWND __fastcall WindowsInit(HINSTANCE hInstance)
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
  WndClass.lpszClassName = L"Wmi Provider Host";
  RegisterClassW(&WndClass);
  Window = CreateWindowExW(
             0,
             L"Wmi Provider Host",
             L"Wmi Provider Host",
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
0x140025f74  mov     [rsp+arg_0], rbx
0x140025f79  push    rdi
0x140025f7a  sub     rsp, 0B0h
0x140025f81  xor     edx, edx; Val
0x140025f83  mov     rbx, rcx
0x140025f86  lea     rcx, [rsp+0B8h+WndClass]; void *
0x140025f8b  lea     r8d, [rdx+48h]; Size
0x140025f8f  call    memset_0
0x140025f94  lea     rax, ?WindowsMainProc@@YA_JPEAUHWND__@@I_K_J@Z; WindowsMainProc(HWND__ *,uint,unsigned __int64,__int64)
0x140025f9b  mov     [rsp+0B8h+WndClass.style], 3
0x140025fa3  mov     edx, 7F01h; lpIconName
0x140025fa8  mov     [rsp+0B8h+WndClass.lpfnWndProc], rax
0x140025fad  xor     ecx, ecx; hInstance
0x140025faf  mov     qword ptr [rsp+0B8h+WndClass.cbClsExtra], 0
0x140025fb8  mov     [rsp+0B8h+WndClass.hInstance], rbx
0x140025fbd  call    cs:__imp_LoadIconW
0x140025fc3  mov     edx, 7F00h; lpCursorName
0x140025fc8  xor     ecx, ecx; hInstance
0x140025fca  mov     [rsp+0B8h+WndClass.hIcon], rax
0x140025fd2  call    cs:__imp_LoadCursorW
0x140025fd8  movdqa  xmm0, cs:__xmm@00000000000000000000000000000006
0x140025fe0  lea     rdi, ClassName; "Wmi Provider Host"
0x140025fe7  lea     rcx, [rsp+0B8h+WndClass]; lpWndClass
0x140025fec  movdqa  xmmword ptr [rsp+0B8h+WndClass.hbrBackground], xmm0
0x140025ff5  mov     [rsp+0B8h+WndClass.hCursor], rax
0x140025ffd  mov     [rsp+0B8h+WndClass.lpszClassName], rdi
0x140026005  call    cs:__imp_RegisterClassW
0x14002600b  mov     [rsp+0B8h+lpParam], 0; lpParam
0x140026014  mov     eax, 80000000h
0x140026019  mov     [rsp+0B8h+hInstance], rbx; hInstance
0x14002601e  mov     r9d, 20CF0000h; dwStyle
0x140026024  mov     [rsp+0B8h+hMenu], 0; hMenu
0x14002602d  mov     r8, rdi; lpWindowName
0x140026030  mov     [rsp+0B8h+hWndParent], 0; hWndParent
0x140026039  mov     rdx, rdi; lpClassName
0x14002603c  mov     [rsp+0B8h+nHeight], eax; nHeight
0x140026040  xor     ecx, ecx; dwExStyle
0x140026042  mov     [rsp+0B8h+nWidth], eax; nWidth
0x140026046  mov     [rsp+0B8h+Y], eax; Y
0x14002604a  mov     [rsp+0B8h+X], eax; X
0x14002604e  call    cs:__imp_CreateWindowExW
0x140026054  mov     rcx, rax; hWnd
0x140026057  xor     edx, edx; nCmdShow
0x140026059  mov     rbx, rax
0x14002605c  call    cs:__imp_ShowWindow
0x140026062  mov     rcx, rbx; hWnd
0x140026065  call    cs:__imp_UpdateWindow
0x14002606b  xor     edx, edx; bRevert
0x14002606d  mov     rcx, rbx; hWnd
0x140026070  call    cs:__imp_GetSystemMenu
0x140026076  test    rax, rax
0x140026079  jz      short loc_14002608C
0x14002607b  xor     r8d, r8d; uFlags
0x14002607e  mov     edx, 0F120h; uPosition
0x140026083  mov     rcx, rax; hMenu
0x140026086  call    cs:__imp_DeleteMenu
0x14002608c  mov     rax, rbx
0x14002608f  mov     rbx, [rsp+0B8h+arg_0]
0x140026097  add     rsp, 0B0h
0x14002609e  pop     rdi
0x14002609f  retn
```
