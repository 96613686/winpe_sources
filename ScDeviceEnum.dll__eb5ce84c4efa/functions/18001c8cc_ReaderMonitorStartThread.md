# ReaderMonitorStartThread

- ea: `0x18001c8cc`
- end: `0x18001c967`
- name: `ReaderMonitorStartThread`
- size: `155`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d8f0`

## callees

- `0x18001c8cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001c8e0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001c8e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c8ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c952`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001c938`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001c938`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001c947`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001c947`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001c914`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001c914`

## pseudocode

```c
DWORD __fastcall ReaderMonitorStartThread(char *lpParameter)
{
  HANDLE Thread; // rax
  HANDLE *v4; // rdi
  int v5; // ebx

  if ( !ResetEvent(*((HANDLE *)lpParameter + 30)) )
    return GetLastError();
  Thread = CreateThread(
             0,
             0,
             (LPTHREAD_START_ROUTINE)I_ReaderMonitorThreadProc,
             lpParameter,
             4u,
             (LPDWORD)lpParameter + 55);
  v4 = (HANDLE *)(lpParameter + 224);
  *((_QWORD *)lpParameter + 28) = Thread;
  if ( !Thread )
    return GetLastError();
  if ( *(_DWORD *)lpParameter && !SetThreadToken((PHANDLE)lpParameter + 28, *((HANDLE *)lpParameter + 31)) )
    return GetLastError();
  v5 = 0;
  if ( ResumeThread(*v4) == -1 )
    return GetLastError();
  return v5;
}

```

## disassembly

```asm
0x18001c8cc  mov     [rsp+arg_0], rbx
0x18001c8d1  push    rdi
0x18001c8d2  sub     rsp, 30h
0x18001c8d6  mov     rbx, rcx
0x18001c8d9  mov     rcx, [rcx+0F0h]; hEvent
0x18001c8e0  call    cs:__imp_ResetEvent
0x18001c8e6  test    eax, eax
0x18001c8e8  jnz     short loc_18001C8F2
0x18001c8ea  call    cs:__imp_GetLastError
0x18001c8f0  jmp     short loc_18001C95C
0x18001c8f2  lea     rax, [rbx+0DCh]
0x18001c8f9  mov     r9, rbx; lpParameter
0x18001c8fc  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18001c901  lea     r8, I_ReaderMonitorThreadProc; lpStartAddress
0x18001c908  xor     edx, edx; dwStackSize
0x18001c90a  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18001c912  xor     ecx, ecx; lpThreadAttributes
0x18001c914  call    cs:__imp_CreateThread
0x18001c91a  lea     rdi, [rbx+0E0h]
0x18001c921  mov     [rdi], rax
0x18001c924  test    rax, rax
0x18001c927  jz      short loc_18001C8EA
0x18001c929  cmp     dword ptr [rbx], 0
0x18001c92c  jz      short loc_18001C942
0x18001c92e  mov     rdx, [rbx+0F8h]; Token
0x18001c935  mov     rcx, rdi; Thread
0x18001c938  call    cs:__imp_SetThreadToken
0x18001c93e  test    eax, eax
0x18001c940  jz      short loc_18001C952
0x18001c942  mov     rcx, [rdi]; hThread
0x18001c945  xor     ebx, ebx
0x18001c947  call    cs:__imp_ResumeThread
0x18001c94d  cmp     eax, 0FFFFFFFFh
0x18001c950  jnz     short loc_18001C95A
0x18001c952  call    cs:__imp_GetLastError
0x18001c958  mov     ebx, eax
0x18001c95a  mov     eax, ebx
0x18001c95c  mov     rbx, [rsp+38h+arg_0]
0x18001c961  add     rsp, 30h
0x18001c965  pop     rdi
0x18001c966  retn
```
