# WinSATWaitngThread

- ea: `0x18001c1a0`
- end: `0x18001c31c`
- name: `WinSATWaitngThread`
- size: `380`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180012c06`
- `0x18001bf9c`
- `0x18001c1a0`
- `0x18002fb50`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001c207`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001c207`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c257`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001c257`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001c223`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001c295`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001c223`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001c295`
- `USER32!PostMessageW` at `0x18001c2eb`
- `USER32!PostMessageW` at `0x18001c2eb`
- `USER32!IsWindow` at `0x18001c2c0`
- `USER32!IsWindow` at `0x18001c2c0`

## pseudocode

```c
__int64 __fastcall WinSATWaitngThread(PVOID Parameter)
{
  DWORD v1; // esi
  void (__fastcall *v2)(__int64, void *); // rdi
  void (__fastcall *v3)(__int64, _QWORD); // rax
  HANDLE Handles[2]; // [rsp+30h] [rbp-28h] BYREF
  HANDLE v6; // [rsp+40h] [rbp-18h]

  v6 = 0;
  v1 = 2;
  Handles[0] = qword_18004FFE0;
  Handles[1] = g_WinSATProcessInfo;
  if ( qword_18004FF90 )
  {
    v6 = qword_18004FF90;
    v1 = 3;
  }
  while ( !WaitForMultipleObjectsEx(v1, Handles, 0, 0xFFFFFFFF, 0) )
  {
    if ( Ptr )
    {
      v2 = (void (__fastcall *)(__int64, void *))DecodePointer(Ptr);
      if ( Src )
        memcpy_0(&s_LocalStatus, Src, 0x80Cu);
      SetEvent(hEvent);
      if ( v2 )
        v2(qword_18004FF68, &s_LocalStatus);
    }
  }
  _InterlockedExchange(&g_RunState, 2);
  if ( Ptr )
  {
    v3 = (void (__fastcall *)(__int64, _QWORD))DecodePointer(Ptr);
    if ( v3 )
      v3(qword_18004FF68, 0);
  }
  if ( hWnd && IsWindow(hWnd) )
    PostMessageW(hWnd, *((UINT *)&hWnd + 2), wParam, *(&wParam + 1));
  ResetGlobalState();
  return 0;
}

```

## disassembly

```asm
0x18001c1a0  mov     r11, rsp
0x18001c1a3  mov     [r11+8], rbx
0x18001c1a7  mov     [r11+10h], rsi
0x18001c1ab  push    rdi
0x18001c1ac  sub     rsp, 50h
0x18001c1b0  mov     rax, cs:__security_cookie
0x18001c1b7  xor     rax, rsp
0x18001c1ba  mov     [rsp+58h+var_10], rax
0x18001c1bf  mov     rax, cs:qword_18004FFE0
0x18001c1c6  mov     ebx, 2
0x18001c1cb  and     qword ptr [r11-18h], 0
0x18001c1d0  mov     esi, ebx
0x18001c1d2  mov     [r11-28h], rax
0x18001c1d6  mov     rax, qword ptr cs:?g_WinSATProcessInfo@@3U_PROCESS_INFORMATION@@A; _PROCESS_INFORMATION g_WinSATProcessInfo
0x18001c1dd  mov     [r11-20h], rax
0x18001c1e1  mov     rax, cs:qword_18004FF90
0x18001c1e8  test    rax, rax
0x18001c1eb  jz      short loc_18001C1F4
0x18001c1ed  mov     [r11-18h], rax
0x18001c1f1  lea     esi, [rbx+1]
0x18001c1f4  and     [rsp+58h+var_38], 0
0x18001c1f9  lea     rdx, [rsp+58h+Handles]; lpHandles
0x18001c1fe  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001c202  xor     r8d, r8d; bWaitAll
0x18001c205  mov     ecx, esi; nCount
0x18001c207  call    cs:__imp_WaitForMultipleObjectsEx
0x18001c20e  nop     dword ptr [rax+rax+00h]
0x18001c213  test    eax, eax
0x18001c215  jnz     short loc_18001C283
0x18001c217  mov     rcx, cs:Ptr; Ptr
0x18001c21e  test    rcx, rcx
0x18001c221  jz      short loc_18001C1F4
0x18001c223  call    cs:__imp_DecodePointer
0x18001c22a  nop     dword ptr [rax+rax+00h]
0x18001c22f  mov     rdx, cs:Src; Src
0x18001c236  mov     rdi, rax
0x18001c239  test    rdx, rdx
0x18001c23c  jz      short loc_18001C250
0x18001c23e  lea     rcx, ?s_LocalStatus@@3U_WinSATStatus@@A; void *
0x18001c245  mov     r8d, 80Ch; Size
0x18001c24b  call    memcpy_0
0x18001c250  mov     rcx, cs:hEvent; hEvent
0x18001c257  call    cs:__imp_SetEvent
0x18001c25e  nop     dword ptr [rax+rax+00h]
0x18001c263  test    rdi, rdi
0x18001c266  jz      short loc_18001C1F4
0x18001c268  mov     rcx, cs:qword_18004FF68
0x18001c26f  lea     rdx, ?s_LocalStatus@@3U_WinSATStatus@@A; _WinSATStatus s_LocalStatus
0x18001c276  mov     rax, rdi
0x18001c279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c27e  jmp     loc_18001C1F4
0x18001c283  xchg    ebx, cs:?g_RunState@@3JA; long g_RunState
0x18001c289  mov     rcx, cs:Ptr; Ptr
0x18001c290  test    rcx, rcx
0x18001c293  jz      short loc_18001C2B4
0x18001c295  call    cs:__imp_DecodePointer
0x18001c29c  nop     dword ptr [rax+rax+00h]
0x18001c2a1  test    rax, rax
0x18001c2a4  jz      short loc_18001C2B4
0x18001c2a6  mov     rcx, cs:qword_18004FF68
0x18001c2ad  xor     edx, edx
0x18001c2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2b4  mov     rcx, qword ptr cs:hWnd; hWnd
0x18001c2bb  test    rcx, rcx
0x18001c2be  jz      short loc_18001C2F7
0x18001c2c0  call    cs:__imp_IsWindow
0x18001c2c7  nop     dword ptr [rax+rax+00h]
0x18001c2cc  test    eax, eax
0x18001c2ce  jz      short loc_18001C2F7
0x18001c2d0  mov     r9, qword ptr cs:wParam+8; lParam
0x18001c2d7  mov     r8, qword ptr cs:wParam; wParam
0x18001c2de  mov     edx, dword ptr cs:hWnd+8; Msg
0x18001c2e4  mov     rcx, qword ptr cs:hWnd; hWnd
0x18001c2eb  call    cs:__imp_PostMessageW
0x18001c2f2  nop     dword ptr [rax+rax+00h]
0x18001c2f7  call    ResetGlobalState
0x18001c2fc  xor     eax, eax
0x18001c2fe  mov     rcx, [rsp+58h+var_10]
0x18001c303  xor     rcx, rsp; StackCookie
0x18001c306  call    __security_check_cookie
0x18001c30b  mov     rbx, [rsp+58h+arg_0]
0x18001c310  mov     rsi, [rsp+58h+arg_8]
0x18001c315  add     rsp, 50h
0x18001c319  pop     rdi
0x18001c31a  retn
```
