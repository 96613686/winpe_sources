# CVSyncServiceHelper::StartProvider(ulong)

- ea: `0x180512a74`
- end: `0x180512d42`
- name: `?StartProvider@CVSyncServiceHelper@@AEAAJK@Z`
- size: `718`
- prototype: `__int64 __fastcall(CVSyncServiceHelper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, installer_update`

## callers

- `0x1805129e0`

## callees

- `0x180512a74`
- `0x180513390`
- `0x1807b5008`
- `0x1810c2cb6`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180512b19`
- `KERNEL32!GetCurrentProcessId` at `0x180512b19`
- `KERNEL32!MapViewOfFile` at `0x180512cfb`
- `KERNEL32!MapViewOfFile` at `0x180512cfb`
- `KERNEL32!CreateFileMappingW` at `0x180512c2b`
- `KERNEL32!CreateFileMappingW` at `0x180512c2b`
- `KERNEL32!UnmapViewOfFile` at `0x180512d0d`
- `KERNEL32!UnmapViewOfFile` at `0x180512d0d`
- `KERNEL32!GetCurrentThreadId` at `0x180512b23`
- `KERNEL32!GetCurrentThreadId` at `0x180512b23`
- `KERNEL32!SetEvent` at `0x180512b70`
- `KERNEL32!SetEvent` at `0x180512b70`
- `KERNEL32!CreateEventW` at `0x180512c5a`
- `KERNEL32!CreateEventW` at `0x180512c5a`
- `KERNEL32!CloseHandle` at `0x180512cd6`
- `KERNEL32!CloseHandle` at `0x180512cde`
- `KERNEL32!CloseHandle` at `0x180512cd6`
- `KERNEL32!CloseHandle` at `0x180512cde`
- `USER32!RegisterClassW` at `0x180512bf6`
- `USER32!RegisterClassW` at `0x180512bf6`
- `USER32!SetWindowLongPtrW` at `0x180512ccb`
- `USER32!SetWindowLongPtrW` at `0x180512ccb`
- `USER32!CreateWindowExW` at `0x180512cad`
- `USER32!CreateWindowExW` at `0x180512cad`

## pseudocode

```c
__int64 __fastcall CVSyncServiceHelper::StartProvider(CVSyncServiceHelper *this, unsigned int a2)
{
  ATOM v4; // ax
  DWORD dwMaximumSizeLow; // eax
  void *v6; // rbx
  SIZE_T v7; // rsi
  __int64 v8; // rsi
  int v9; // ebx
  BOOL v10; // eax
  unsigned int v11; // ecx
  unsigned __int64 QPCInUs; // rax
  HANDLE FileMappingW; // rax
  void *v15; // rcx
  HANDLE EventW; // rax
  void *v17; // rcx
  HANDLE v18; // rbx
  HWND Window; // rax
  _DWORD *v20; // rax
  const void *v21; // rcx
  _DWORD *v22; // rbx
  _DWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+78h] [rbp-88h]
  WNDCLASSW WndClass; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v27[80]; // [rsp+D0h] [rbp-30h] BYREF

  v4 = *((_WORD *)this + 16);
  if ( !v4 )
  {
    QPCInUs = CVSyncServiceHelper::GetQPCInUs();
    StringCbPrintfW(v27, 0xA0u, L"VSyncHelper-%p-%I64x", this, QPCInUs);
    memset_0(&WndClass, 0, sizeof(WndClass));
    WndClass.lpfnWndProc = (WNDPROC)CVSyncServiceHelper::MsgWindowProc;
    WndClass.lpszClassName = v27;
    v4 = RegisterClassW(&WndClass);
    *((_WORD *)this + 16) = v4;
    if ( !v4 )
      return (unsigned int)-2147418113;
  }
  if ( !*((_QWORD *)this + 3) )
  {
    Window = CreateWindowExW(0, (LPCWSTR)v4, 0, 0, 0, 0, 0, 0, 0, 0, 0, this);
    *((_QWORD *)this + 3) = Window;
    if ( !Window )
      return (unsigned int)-2147418113;
    SetWindowLongPtrW(Window, -21, (LONG_PTR)this);
  }
  if ( !*((_QWORD *)this + 5) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v17 = (void *)*((_QWORD *)this + 5);
    v18 = EventW;
    if ( v17 )
      CloseHandle(v17);
    *((_QWORD *)this + 5) = v18;
    if ( !v18 )
      return (unsigned int)-2147418113;
  }
  dwMaximumSizeLow = (*(__int64 (__fastcall **)(CVSyncServiceHelper *))(*(_QWORD *)this + 80LL))(this);
  v6 = (void *)*((_QWORD *)this + 6);
  v7 = dwMaximumSizeLow;
  if ( !v6 )
  {
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x8000004u, 0, dwMaximumSizeLow, 0);
    v15 = (void *)*((_QWORD *)this + 6);
    v6 = FileMappingW;
    if ( v15 )
      CloseHandle(v15);
    *((_QWORD *)this + 6) = v6;
    if ( !v6 )
      return (unsigned int)-2147418113;
  }
  if ( !*((_QWORD *)this + 7) )
  {
    v20 = MapViewOfFile(v6, 6u, 0, 0, v7);
    v21 = (const void *)*((_QWORD *)this + 7);
    v22 = v20;
    if ( v21 )
      UnmapViewOfFile(v21);
    *((_QWORD *)this + 7) = v22;
    if ( !v22 )
      return (unsigned int)-2147418113;
    memset_0(v22, 0, v7);
    *v22 = -838796627;
    v22[1] = 1;
    v22[2] = v7;
  }
  v8 = *((_QWORD *)this + 7);
  v24 = 0;
  v25 = 0;
  v23[0] = GetCurrentProcessId();
  v23[1] = GetCurrentThreadId();
  *(_QWORD *)&v24 = *((_QWORD *)this + 6);
  *((_QWORD *)&v24 + 1) = *((_QWORD *)this + 5);
  v25 = *((_QWORD *)this + 3);
  v9 = (*(__int64 (__fastcall **)(CVSyncServiceHelper *, _DWORD *, _QWORD))(*(_QWORD *)this + 64LL))(this, v23, a2);
  if ( v9 >= 0 )
  {
    *(_DWORD *)(v8 + 12) = 1;
    v10 = SetEvent(*((HANDLE *)this + 5));
    v11 = v9;
    if ( !v10 )
      return (unsigned int)-2147418113;
    return v11;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180512a74  mov     rax, rsp
0x180512a77  mov     [rax+18h], rbx
0x180512a7b  mov     [rax+20h], rsi
0x180512a7f  mov     [rax+10h], edx
0x180512a82  mov     [rax+8], rcx
0x180512a86  push    rbp
0x180512a87  push    rdi
0x180512a88  push    r12
0x180512a8a  push    r14
0x180512a8c  push    r15
0x180512a8e  lea     rbp, [rsp-80h]
0x180512a93  sub     rsp, 180h
0x180512a9a  mov     rax, cs:__security_cookie
0x180512aa1  xor     rax, rsp
0x180512aa4  mov     [rbp+0A0h+var_30], rax
0x180512aa8  mov     rdi, [rbp+0A0h+dwNewLong]
0x180512aaf  xor     r12d, r12d
0x180512ab2  mov     r15d, [rbp+0A0h+arg_8]
0x180512ab9  movzx   eax, word ptr [rdi+20h]
0x180512abd  test    ax, ax
0x180512ac0  jz      loc_180512BAE
0x180512ac6  cmp     [rdi+18h], r12
0x180512aca  jz      loc_180512C7A
0x180512ad0  cmp     [rdi+28h], r12
0x180512ad4  jz      loc_180512C50
0x180512ada  mov     rax, [rdi]
0x180512add  mov     rcx, rdi
0x180512ae0  mov     rax, [rax+50h]
0x180512ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180512ae9  mov     rbx, [rdi+30h]
0x180512aed  mov     esi, eax
0x180512aef  test    rbx, rbx
0x180512af2  jz      loc_180512C13
0x180512af8  cmp     [rdi+38h], r12
0x180512afc  jz      loc_180512CE9
0x180512b02  mov     rsi, [rdi+38h]
0x180512b06  xorps   xmm0, xmm0
0x180512b09  movdqu  [rsp+1A0h+var_138], xmm0
0x180512b0f  mov     [rsp+1A0h+var_140], r12
0x180512b14  mov     [rsp+1A0h+var_128], r12
0x180512b19  call    cs:__imp_GetCurrentProcessId
0x180512b1f  mov     dword ptr [rsp+1A0h+var_140], eax
0x180512b23  call    cs:__imp_GetCurrentThreadId
0x180512b29  mov     dword ptr [rsp+1A0h+var_140+4], eax
0x180512b2d  mov     r8d, r15d
0x180512b30  mov     rax, [rdi+30h]
0x180512b34  lea     rdx, [rsp+1A0h+var_140]
0x180512b39  mov     qword ptr [rsp+1A0h+var_138], rax
0x180512b3e  mov     rcx, rdi
0x180512b41  mov     rax, [rdi+28h]
0x180512b45  mov     qword ptr [rsp+1A0h+var_138+8], rax
0x180512b4a  mov     rax, [rdi+18h]
0x180512b4e  mov     [rsp+1A0h+var_128], rax
0x180512b53  mov     rax, [rdi]
0x180512b56  mov     rax, [rax+40h]
0x180512b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180512b5f  mov     ebx, eax
0x180512b61  test    eax, eax
0x180512b63  js      short loc_180512B84
0x180512b65  mov     dword ptr [rsi+0Ch], 1
0x180512b6c  mov     rcx, [rdi+28h]; hEvent
0x180512b70  call    cs:__imp_SetEvent
0x180512b76  mov     ecx, ebx
0x180512b78  mov     ebx, 8000FFFFh
0x180512b7d  test    eax, eax
0x180512b7f  cmovz   ecx, ebx
0x180512b82  mov     ebx, ecx
0x180512b84  mov     eax, ebx
0x180512b86  mov     rcx, [rbp+0A0h+var_30]
0x180512b8a  xor     rcx, rsp; StackCookie
0x180512b8d  call    __security_check_cookie
0x180512b92  lea     r11, [rsp+1A0h+var_20]
0x180512b9a  mov     rbx, [r11+40h]
0x180512b9e  mov     rsi, [r11+48h]
0x180512ba2  mov     rsp, r11
0x180512ba5  pop     r15
0x180512ba7  pop     r14
0x180512ba9  pop     r12
0x180512bab  pop     rdi
0x180512bac  pop     rbp
0x180512bad  retn
0x180512bae  call    ?GetQPCInUs@CVSyncServiceHelper@@SA_KXZ; CVSyncServiceHelper::GetQPCInUs(void)
0x180512bb3  mov     r9, rdi
0x180512bb6  mov     qword ptr [rsp+1A0h+dwMaximumSizeLow], rax
0x180512bbb  lea     r8, aVsynchelperPI6; "VSyncHelper-%p-%I64x"
0x180512bc2  mov     edx, 0A0h; unsigned __int64
0x180512bc7  lea     rcx, [rbp+0A0h+var_D0]; unsigned __int16 *
0x180512bcb  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180512bd0  xor     edx, edx; Val
0x180512bd2  lea     rcx, [rbp+0A0h+WndClass]; void *
0x180512bd6  lea     r8d, [rdx+48h]; Size
0x180512bda  call    memset_0
0x180512bdf  lea     rax, ?MsgWindowProc@CVSyncServiceHelper@@CA_JPEAUHWND__@@I_K_J@Z; CVSyncServiceHelper::MsgWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x180512be6  mov     [rbp+0A0h+WndClass.lpfnWndProc], rax
0x180512bea  lea     rcx, [rbp+0A0h+WndClass]; lpWndClass
0x180512bee  lea     rax, [rbp+0A0h+var_D0]
0x180512bf2  mov     [rbp+0A0h+WndClass.lpszClassName], rax
0x180512bf6  call    cs:__imp_RegisterClassW
0x180512bfc  mov     [rdi+20h], ax
0x180512c00  test    ax, ax
0x180512c03  jnz     loc_180512AC6
0x180512c09  mov     ebx, 8000FFFFh
0x180512c0e  jmp     loc_180512B84
0x180512c13  mov     [rsp+1A0h+lpName], r12; lpName
0x180512c18  xor     r9d, r9d; dwMaximumSizeHigh
0x180512c1b  xor     edx, edx; lpFileMappingAttributes
0x180512c1d  mov     [rsp+1A0h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x180512c21  mov     r8d, 8000004h; flProtect
0x180512c27  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180512c2b  call    cs:__imp_CreateFileMappingW
0x180512c31  mov     rcx, [rdi+30h]; hObject
0x180512c35  mov     rbx, rax
0x180512c38  test    rcx, rcx
0x180512c3b  jnz     loc_180512CDE
0x180512c41  mov     [rdi+30h], rbx
0x180512c45  test    rbx, rbx
0x180512c48  jnz     loc_180512AF8
0x180512c4e  jmp     short loc_180512C09
0x180512c50  xor     r9d, r9d; lpName
0x180512c53  xor     r8d, r8d; bInitialState
0x180512c56  xor     edx, edx; bManualReset
0x180512c58  xor     ecx, ecx; lpEventAttributes
0x180512c5a  call    cs:__imp_CreateEventW
0x180512c60  mov     rcx, [rdi+28h]; hObject
0x180512c64  mov     rbx, rax
0x180512c67  test    rcx, rcx
0x180512c6a  jnz     short loc_180512CD6
0x180512c6c  mov     [rdi+28h], rbx
0x180512c70  test    rbx, rbx
0x180512c73  jz      short loc_180512C09
0x180512c75  jmp     loc_180512ADA
0x180512c7a  mov     [rsp+1A0h+lpParam], rdi; lpParam
0x180512c7f  xor     r9d, r9d; dwStyle
0x180512c82  mov     [rsp+1A0h+hInstance], r12; hInstance
0x180512c87  xor     r8d, r8d; lpWindowName
0x180512c8a  mov     [rsp+1A0h+hMenu], r12; hMenu
0x180512c8f  xor     ecx, ecx; dwExStyle
0x180512c91  mov     [rsp+1A0h+hWndParent], r12; hWndParent
0x180512c96  mov     [rsp+1A0h+nHeight], r12d; nHeight
0x180512c9b  mov     [rsp+1A0h+nWidth], r12d; nWidth
0x180512ca0  mov     dword ptr [rsp+1A0h+lpName], r12d; Y
0x180512ca5  movzx   edx, ax; lpClassName
0x180512ca8  mov     [rsp+1A0h+dwMaximumSizeLow], r12d; X
0x180512cad  call    cs:__imp_CreateWindowExW
0x180512cb3  mov     [rdi+18h], rax
0x180512cb7  test    rax, rax
0x180512cba  jz      loc_180512C09
0x180512cc0  mov     r8, rdi; dwNewLong
0x180512cc3  mov     edx, 0FFFFFFEBh; nIndex
0x180512cc8  mov     rcx, rax; hWnd
0x180512ccb  call    cs:__imp_SetWindowLongPtrW
0x180512cd1  jmp     loc_180512AD0
0x180512cd6  call    cs:__imp_CloseHandle
0x180512cdc  jmp     short loc_180512C6C
0x180512cde  call    cs:__imp_CloseHandle
0x180512ce4  jmp     loc_180512C41
0x180512ce9  xor     r9d, r9d; dwFileOffsetLow
0x180512cec  mov     qword ptr [rsp+1A0h+dwMaximumSizeLow], rsi; dwNumberOfBytesToMap
0x180512cf1  xor     r8d, r8d; dwFileOffsetHigh
0x180512cf4  mov     rcx, rbx; hFileMappingObject
0x180512cf7  lea     edx, [r9+6]; dwDesiredAccess
0x180512cfb  call    cs:__imp_MapViewOfFile
0x180512d01  mov     rcx, [rdi+38h]; lpBaseAddress
0x180512d05  mov     rbx, rax
0x180512d08  test    rcx, rcx
0x180512d0b  jz      short loc_180512D13
0x180512d0d  call    cs:__imp_UnmapViewOfFile
0x180512d13  mov     [rdi+38h], rbx
0x180512d17  test    rbx, rbx
0x180512d1a  jz      loc_180512C09
0x180512d20  mov     r8, rsi; Size
0x180512d23  xor     edx, edx; Val
0x180512d25  mov     rcx, rbx; void *
0x180512d28  call    memset_0
0x180512d2d  mov     dword ptr [rbx], 0CE00FAADh
0x180512d33  mov     dword ptr [rbx+4], 1
0x180512d3a  mov     [rbx+8], esi
0x180512d3d  jmp     loc_180512B02
```
