# CDwmAppHost::InitializeWindow(void)

- ea: `0x140001fb0`
- end: `0x140002153`
- name: `?InitializeWindow@CDwmAppHost@@AEAAJXZ`
- size: `419`
- prototype: `__int64 __fastcall(CDwmAppHost *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140002fbc`

## callees

- `0x140001fb0`
- `0x140002e6c`
- `0x1400061b8`
- `0x140006224`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140001ffe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002059`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140001ffe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400020ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400020ae`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x140002009`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassExW` at `0x140002009`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000209c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000209c`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x1400020f4`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x14000210a`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x140002122`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x14000213a`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x1400020f4`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x14000210a`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x140002122`
- `ext-ms-win-ntuser-gui-l1-3-0!ChangeWindowMessageFilterEx` at `0x14000213a`

## pseudocode

```c
__int64 __fastcall CDwmAppHost::InitializeWindow(CDwmAppHost *this)
{
  signed int LastError; // eax
  unsigned int v2; // ebx
  signed int v3; // eax
  unsigned int X; // [rsp+20h] [rbp-98h]
  WNDCLASSEXW v6; // [rsp+60h] [rbp-58h] BYREF

  memset_0(&v6, 0, sizeof(v6));
  v6.cbSize = 80;
  v6.lpfnWndProc = (WNDPROC)CDwmAppHost::s_NotifyWndProc;
  v6.hInstance = hInstance;
  v6.lpszClassName = L"Dwm";
  SetLastError(0);
  if ( !RegisterClassExW(&v6) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    X = 278;
LABEL_5:
    if ( (v2 & 0x80000000) == 0 )
      v2 = -2003304445;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v2, X, 0);
    return v2;
  }
  SetLastError(0);
  hWnd = CreateWindowExW(0, L"Dwm", L"DWM Notification Window", 0xA0000000, 0, 0, 0, 0, 0, 0, hInstance, 0);
  if ( !hWnd )
  {
    v3 = GetLastError();
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    X = 291;
    goto LABEL_5;
  }
  v2 = 0;
  if ( (unsigned __int8)IsChangeWindowMessageFilterExPresent() )
  {
    ChangeWindowMessageFilterEx(hWnd, 0x1Au, 1u, 0);
    ChangeWindowMessageFilterEx(hWnd, 0x15u, 1u, 0);
    ChangeWindowMessageFilterEx(hWnd, 0x31Au, 1u, 0);
    ChangeWindowMessageFilterEx(hWnd, 0x31Bu, 1u, 0);
  }
  return v2;
}

```

## disassembly

```asm
0x140001fb0  mov     [rsp+arg_0], rbx
0x140001fb5  push    rdi
0x140001fb6  sub     rsp, 0B0h
0x140001fbd  mov     ebx, 50h ; 'P'
0x140001fc2  lea     rcx, [rsp+0B8h+var_58]; void *
0x140001fc7  mov     r8d, ebx; Size
0x140001fca  xor     edx, edx; Val
0x140001fcc  call    memset_0
0x140001fd1  lea     rax, ?s_NotifyWndProc@CDwmAppHost@@CA_JPEAUHWND__@@I_K_J@Z; CDwmAppHost::s_NotifyWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x140001fd8  mov     [rsp+0B8h+var_58.cbSize], ebx
0x140001fdc  mov     [rsp+0B8h+var_58.lpfnWndProc], rax
0x140001fe1  lea     rbx, ClassName; "Dwm"
0x140001fe8  mov     rax, qword ptr cs:hInstance
0x140001fef  xor     ecx, ecx; dwErrCode
0x140001ff1  mov     [rsp+0B8h+var_58.hInstance], rax
0x140001ff6  mov     [rsp+0B8h+var_58.lpszClassName], rbx
0x140001ffe  call    cs:__imp_SetLastError
0x140002004  lea     rcx, [rsp+0B8h+var_58]; WNDCLASSEXW *
0x140002009  call    cs:__imp_RegisterClassExW
0x14000200f  xor     edi, edi
0x140002011  test    ax, ax
0x140002014  jnz     short loc_140002057
0x140002016  call    cs:__imp_GetLastError
0x14000201c  mov     ebx, eax
0x14000201e  test    eax, eax
0x140002020  jle     short loc_14000202B
0x140002022  movzx   ebx, ax
0x140002025  or      ebx, 80070000h
0x14000202b  mov     qword ptr [rsp+0B8h+Y], rdi; void *
0x140002030  mov     [rsp+0B8h+X], 116h; unsigned int
0x140002038  test    ebx, ebx
0x14000203a  mov     eax, 88980003h
0x14000203f  cmovns  ebx, eax
0x140002042  xor     edx, edx; int *
0x140002044  mov     r9d, ebx; int
0x140002047  xor     r8d, r8d; unsigned int
0x14000204a  lea     ecx, [rdx+14h]; unsigned int
0x14000204d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x140002052  jmp     loc_140002140
0x140002057  xor     ecx, ecx; dwErrCode
0x140002059  call    cs:__imp_SetLastError
0x14000205f  mov     rax, qword ptr cs:hInstance
0x140002066  lea     r8, WindowName; "DWM Notification Window"
0x14000206d  mov     [rsp+0B8h+lpParam], rdi; lpParam
0x140002072  mov     r9d, 0A0000000h; dwStyle
0x140002078  mov     [rsp+0B8h+hInstance], rax; hInstance
0x14000207d  mov     rdx, rbx; lpClassName
0x140002080  mov     [rsp+0B8h+hMenu], rdi; hMenu
0x140002085  xor     ecx, ecx; dwExStyle
0x140002087  mov     [rsp+0B8h+hWndParent], rdi; hWndParent
0x14000208c  mov     [rsp+0B8h+nHeight], edi; nHeight
0x140002090  mov     [rsp+0B8h+nWidth], edi; nWidth
0x140002094  mov     [rsp+0B8h+Y], edi; Y
0x140002098  mov     [rsp+0B8h+X], edi; X
0x14000209c  call    cs:__imp_CreateWindowExW
0x1400020a2  mov     cs:hWnd, rax
0x1400020a9  test    rax, rax
0x1400020ac  jnz     short loc_1400020D5
0x1400020ae  call    cs:__imp_GetLastError
0x1400020b4  mov     ebx, eax
0x1400020b6  test    eax, eax
0x1400020b8  jle     short loc_1400020C3
0x1400020ba  movzx   ebx, ax
0x1400020bd  or      ebx, 80070000h
0x1400020c3  mov     qword ptr [rsp+0B8h+Y], rdi
0x1400020c8  mov     [rsp+0B8h+X], 123h
0x1400020d0  jmp     loc_140002038
0x1400020d5  mov     ebx, edi
0x1400020d7  call    IsChangeWindowMessageFilterExPresent
0x1400020dc  test    al, al
0x1400020de  jz      short loc_140002140
0x1400020e0  mov     rcx, cs:hWnd; hwnd
0x1400020e7  xor     r9d, r9d; pChangeFilterStruct
0x1400020ea  lea     edi, [r9+1]
0x1400020ee  mov     r8d, edi; action
0x1400020f1  lea     edx, [rdi+19h]; message
0x1400020f4  call    cs:__imp_ChangeWindowMessageFilterEx
0x1400020fa  mov     rcx, cs:hWnd; hwnd
0x140002101  lea     edx, [rdi+14h]; message
0x140002104  xor     r9d, r9d; pChangeFilterStruct
0x140002107  mov     r8d, edi; action
0x14000210a  call    cs:__imp_ChangeWindowMessageFilterEx
0x140002110  mov     rcx, cs:hWnd; hwnd
0x140002117  xor     r9d, r9d; pChangeFilterStruct
0x14000211a  mov     r8d, edi; action
0x14000211d  mov     edx, 31Ah; message
0x140002122  call    cs:__imp_ChangeWindowMessageFilterEx
0x140002128  mov     rcx, cs:hWnd; hwnd
0x14000212f  xor     r9d, r9d; pChangeFilterStruct
0x140002132  mov     r8d, edi; action
0x140002135  mov     edx, 31Bh; message
0x14000213a  call    cs:__imp_ChangeWindowMessageFilterEx
0x140002140  mov     eax, ebx
0x140002142  mov     rbx, [rsp+0B8h+arg_0]
0x14000214a  add     rsp, 0B0h
0x140002151  pop     rdi
0x140002152  retn
```
