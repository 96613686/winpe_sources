# CCertManager::StopCertUpdateThread(void)

- ea: `0x18002b51c`
- end: `0x18002b5d5`
- name: `?StopCertUpdateThread@CCertManager@@AEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(CCertManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800288d0`

## callees

- `0x18002b51c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b578`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b55a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b5b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b55a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b5b7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b56e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b56e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b5a8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b5a8`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002b549`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18002b549`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18002b596`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18002b596`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b53a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b53a`

## pseudocode

```c
__int64 __fastcall CCertManager::StopCertUpdateThread(HANDLE *this)
{
  unsigned int v2; // ebx
  DWORD CurrentThreadId; // ebx
  signed int LastError; // eax

  if ( this[201] )
  {
    CurrentThreadId = GetCurrentThreadId();
    if ( CurrentThreadId == GetThreadId(this[201]) )
    {
      CloseHandle(this[201]);
      v2 = -2147467260;
    }
    else
    {
      if ( SetEvent(this[199]) )
      {
        WaitForSingleObject(this[201], 0xFFFFFFFF);
        v2 = 0;
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        TerminateThread(this[201], 0);
      }
      CloseHandle(this[201]);
    }
    this[201] = 0;
  }
  else
  {
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18002b51c  mov     [rsp+arg_0], rbx
0x18002b521  push    rdi
0x18002b522  sub     rsp, 20h
0x18002b526  cmp     qword ptr [rcx+648h], 0
0x18002b52e  mov     rdi, rcx
0x18002b531  jnz     short loc_18002B53A
0x18002b533  xor     ebx, ebx
0x18002b535  jmp     loc_18002B5C8
0x18002b53a  call    cs:__imp_GetCurrentThreadId
0x18002b540  mov     rcx, [rdi+648h]; Thread
0x18002b547  mov     ebx, eax
0x18002b549  call    cs:__imp_GetThreadId
0x18002b54f  cmp     ebx, eax
0x18002b551  jnz     short loc_18002B567
0x18002b553  mov     rcx, [rdi+648h]; hObject
0x18002b55a  call    cs:__imp_CloseHandle
0x18002b560  mov     ebx, 80004004h
0x18002b565  jmp     short loc_18002B5BD
0x18002b567  mov     rcx, [rdi+638h]; hEvent
0x18002b56e  call    cs:__imp_SetEvent
0x18002b574  test    eax, eax
0x18002b576  jnz     short loc_18002B59E
0x18002b578  call    cs:__imp_GetLastError
0x18002b57e  mov     ebx, eax
0x18002b580  test    eax, eax
0x18002b582  jle     short loc_18002B58D
0x18002b584  movzx   ebx, ax
0x18002b587  or      ebx, 80070000h
0x18002b58d  mov     rcx, [rdi+648h]; hThread
0x18002b594  xor     edx, edx; dwExitCode
0x18002b596  call    cs:__imp_TerminateThread
0x18002b59c  jmp     short loc_18002B5B0
0x18002b59e  mov     rcx, [rdi+648h]; hHandle
0x18002b5a5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b5a8  call    cs:__imp_WaitForSingleObject
0x18002b5ae  xor     ebx, ebx
0x18002b5b0  mov     rcx, [rdi+648h]; hObject
0x18002b5b7  call    cs:__imp_CloseHandle
0x18002b5bd  mov     qword ptr [rdi+648h], 0
0x18002b5c8  mov     eax, ebx
0x18002b5ca  mov     rbx, [rsp+28h+arg_0]
0x18002b5cf  add     rsp, 20h
0x18002b5d3  pop     rdi
0x18002b5d4  retn
```
