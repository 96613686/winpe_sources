# ShutdownControlHandler::CreateMsgWindow(void)

- ea: `0x140005038`
- end: `0x140005137`
- name: `?CreateMsgWindow@ShutdownControlHandler@@CAJXZ`
- size: `255`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400058a0`

## callees

- `0x140005038`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000504c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000504c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140005107`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140005107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400050f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400050f8`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x1400050e6`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x1400050e6`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassW` at `0x1400050a7`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassW` at `0x1400050a7`

## pseudocode

```c
__int64 ShutdownControlHandler::CreateMsgWindow(void)
{
  HINSTANCE ModuleHandleW; // rax
  HINSTANCE hInstance; // rdi
  signed int LastError; // ebx
  WNDCLASSW WndClass; // [rsp+60h] [rbp-58h] BYREF

  ModuleHandleW = GetModuleHandleW(0);
  hInstance = ModuleHandleW;
  if ( !ModuleHandleW )
    goto LABEL_3;
  LastError = 0;
  WndClass.hInstance = ModuleHandleW;
  *(_QWORD *)&WndClass.style = 0;
  WndClass.lpfnWndProc = (WNDPROC)ShutdownControlHandler::MsgWndProc;
  *(_QWORD *)&WndClass.cbClsExtra = 0;
  memset(&WndClass.hIcon, 0, 32);
  WndClass.lpszClassName = L"WinMSGWMIADAP";
  RegisterClassW(&WndClass);
  ShutdownControlHandler::mg_hWnd = CreateWindowExW(
                                      8u,
                                      L"WinMSGWMIADAP",
                                      L"WMIADAP Msg window",
                                      0,
                                      0x80000000,
                                      0x80000000,
                                      0x80000000,
                                      0x80000000,
                                      0,
                                      0,
                                      hInstance,
                                      0);
  if ( !ShutdownControlHandler::mg_hWnd )
LABEL_3:
    LastError = GetLastError();
  SetEvent(ShutdownControlHandler::mg_hReadyEvent);
  if ( !LastError )
    return 0;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140005038  mov     [rsp+arg_0], rbx
0x14000503d  mov     [rsp+arg_8], rsi
0x140005042  push    rdi
0x140005043  sub     rsp, 0B0h
0x14000504a  xor     ecx, ecx; lpModuleName
0x14000504c  call    cs:__imp_GetModuleHandleW
0x140005052  mov     rdi, rax
0x140005055  test    rax, rax
0x140005058  jz      loc_1400050F8
0x14000505e  xor     ebx, ebx
0x140005060  mov     [rsp+0B8h+WndClass.hInstance], rdi
0x140005065  lea     rax, ?MsgWndProc@ShutdownControlHandler@@CA_JPEAUHWND__@@I_K_J@Z; ShutdownControlHandler::MsgWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x14000506c  mov     qword ptr [rsp+0B8h+WndClass.style], rbx
0x140005071  xorps   xmm0, xmm0
0x140005074  mov     [rsp+0B8h+WndClass.lpfnWndProc], rax
0x140005079  xorps   xmm1, xmm1
0x14000507c  mov     qword ptr [rsp+0B8h+WndClass.cbClsExtra], rbx
0x140005081  lea     rsi, ClassName; "WinMSGWMIADAP"
0x140005088  movdqa  xmmword ptr [rsp+0B8h+WndClass.hIcon], xmm0
0x140005091  lea     rcx, [rsp+0B8h+WndClass]; lpWndClass
0x140005096  movdqa  xmmword ptr [rsp+0B8h+WndClass.hbrBackground], xmm1
0x14000509f  mov     [rsp+0B8h+WndClass.lpszClassName], rsi
0x1400050a7  call    cs:__imp_RegisterClassW
0x1400050ad  mov     [rsp+0B8h+lpParam], rbx; lpParam
0x1400050b2  lea     r8, WindowName; "WMIADAP Msg window"
0x1400050b9  mov     [rsp+0B8h+hInstance], rdi; hInstance
0x1400050be  lea     ecx, [rbx+8]; dwExStyle
0x1400050c1  mov     [rsp+0B8h+hMenu], rbx; hMenu
0x1400050c6  mov     eax, 80000000h
0x1400050cb  mov     [rsp+0B8h+hWndParent], rbx; hWndParent
0x1400050d0  xor     r9d, r9d; dwStyle
0x1400050d3  mov     [rsp+0B8h+nHeight], eax; nHeight
0x1400050d7  mov     rdx, rsi; lpClassName
0x1400050da  mov     [rsp+0B8h+nWidth], eax; nWidth
0x1400050de  mov     [rsp+0B8h+Y], eax; Y
0x1400050e2  mov     [rsp+0B8h+X], eax; X
0x1400050e6  call    cs:__imp_CreateWindowExW
0x1400050ec  mov     cs:?mg_hWnd@ShutdownControlHandler@@0PEAUHWND__@@EA, rax; HWND__ * ShutdownControlHandler::mg_hWnd
0x1400050f3  test    rax, rax
0x1400050f6  jnz     short loc_140005100
0x1400050f8  call    cs:__imp_GetLastError
0x1400050fe  mov     ebx, eax
0x140005100  mov     rcx, cs:?mg_hReadyEvent@ShutdownControlHandler@@0PEAXEA; hEvent
0x140005107  call    cs:__imp_SetEvent
0x14000510d  test    ebx, ebx
0x14000510f  jnz     short loc_140005115
0x140005111  xor     eax, eax
0x140005113  jmp     short loc_140005122
0x140005115  jle     short loc_140005120
0x140005117  movzx   ebx, bx
0x14000511a  or      ebx, 80070000h
0x140005120  mov     eax, ebx
0x140005122  lea     r11, [rsp+0B8h+var_8]
0x14000512a  mov     rbx, [r11+10h]
0x14000512e  mov     rsi, [r11+18h]
0x140005132  mov     rsp, r11
0x140005135  pop     rdi
0x140005136  retn
```
