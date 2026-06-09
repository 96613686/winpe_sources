# CSyncTrayIconManager::ShutdownTrayIconThread(ulong)

- ea: `0x180022f90`
- end: `0x18002302b`
- name: `?ShutdownTrayIconThread@CSyncTrayIconManager@@QEAAJK@Z`
- size: `155`
- prototype: `__int64 __fastcall(CSyncTrayIconManager *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180002130`
- `0x180013ae0`

## callees

- `0x180022f90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022fef`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022fef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180022fb8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180022fb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023013`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023013`
- `USER32!PostMessageW` at `0x180022fd0`
- `USER32!PostMessageW` at `0x180022fd0`
- `USER32!GetWindowThreadProcessId` at `0x180022fa8`
- `USER32!GetWindowThreadProcessId` at `0x180022fa8`
- `USER32!SendMessageW` at `0x18002300a`
- `USER32!SendMessageW` at `0x18002300a`

## pseudocode

```c
__int64 __fastcall CSyncTrayIconManager::ShutdownTrayIconThread(HWND *this)
{
  DWORD WindowThreadProcessId; // eax
  HANDLE v3; // rbx
  unsigned int v4; // edi

  WindowThreadProcessId = GetWindowThreadProcessId(this[3], 0);
  v3 = OpenThread(0x100000u, 0, WindowThreadProcessId);
  v4 = !PostMessageW(this[3], 0x8000u, 0, 0) ? 0x80004005 : 0;
  if ( v3 )
  {
    if ( WaitForSingleObject(v3, 0x3E8u) == 258 )
      SendMessageW(this[3], 0x10u, 0, 0);
    CloseHandle(v3);
  }
  return v4;
}

```

## disassembly

```asm
0x180022f90  mov     [rsp+arg_0], rbx
0x180022f95  mov     [rsp+arg_8], rsi
0x180022f9a  push    rdi
0x180022f9b  sub     rsp, 20h
0x180022f9f  mov     rsi, rcx
0x180022fa2  xor     edx, edx; lpdwProcessId
0x180022fa4  mov     rcx, [rcx+18h]; hWnd
0x180022fa8  call    cs:__imp_GetWindowThreadProcessId
0x180022fae  xor     edx, edx; bInheritHandle
0x180022fb0  mov     ecx, 100000h; dwDesiredAccess
0x180022fb5  mov     r8d, eax; dwThreadId
0x180022fb8  call    cs:__imp_OpenThread
0x180022fbe  mov     rcx, [rsi+18h]; hWnd
0x180022fc2  xor     r9d, r9d; lParam
0x180022fc5  xor     r8d, r8d; wParam
0x180022fc8  mov     edx, 8000h; Msg
0x180022fcd  mov     rbx, rax
0x180022fd0  call    cs:__imp_PostMessageW
0x180022fd6  neg     eax
0x180022fd8  sbb     edi, edi
0x180022fda  not     edi
0x180022fdc  and     edi, 80004005h
0x180022fe2  test    rbx, rbx
0x180022fe5  jz      short loc_180023019
0x180022fe7  mov     edx, 3E8h; dwMilliseconds
0x180022fec  mov     rcx, rbx; hHandle
0x180022fef  call    cs:__imp_WaitForSingleObject
0x180022ff5  cmp     eax, 102h
0x180022ffa  jnz     short loc_180023010
0x180022ffc  mov     rcx, [rsi+18h]; hWnd
0x180023000  xor     r9d, r9d; lParam
0x180023003  xor     r8d, r8d; wParam
0x180023006  lea     edx, [r9+10h]; Msg
0x18002300a  call    cs:__imp_SendMessageW
0x180023010  mov     rcx, rbx; hObject
0x180023013  call    cs:__imp_CloseHandle
0x180023019  mov     rbx, [rsp+28h+arg_0]
0x18002301e  mov     eax, edi
0x180023020  mov     rsi, [rsp+28h+arg_8]
0x180023025  add     rsp, 20h
0x180023029  pop     rdi
0x18002302a  retn
```
