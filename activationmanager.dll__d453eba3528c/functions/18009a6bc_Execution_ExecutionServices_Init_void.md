# Execution::ExecutionServices::Init(void)

- ea: `0x18009a6bc`
- end: `0x18009a7c5`
- name: `?Init@ExecutionServices@Execution@@IEAAJXZ`
- size: `265`
- prototype: `__int64 __fastcall(Execution::ExecutionServices *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18009a5a4`

## callees

- `0x18004c6c8`
- `0x18009a6bc`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009a6d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009a70e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009a6d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009a70e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a796`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009a75d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009a75d`

## pseudocode

```c
__int64 __fastcall Execution::ExecutionServices::Init(Execution::ExecutionServices *this)
{
  HANDLE *v2; // rsi
  HANDLE EventW; // rbx
  signed int v4; // ebx
  HANDLE *v5; // rsi
  HANDLE v6; // rbx
  HANDLE *v7; // r14
  HANDLE Thread; // rsi
  signed int LastError; // eax

  v2 = (HANDLE *)((char *)this + 112);
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW == *v2 )
  {
    EventW = *v2;
  }
  else
  {
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 112);
    *v2 = EventW;
  }
  if ( EventW
    && ((v5 = (HANDLE *)((char *)this + 120), v6 = CreateEventW(0, 0, 0, 0), v6 == *((HANDLE *)this + 15))
      ? (v6 = *v5)
      : (tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 120), *v5 = v6),
        v6) )
  {
    v4 = 0;
    (*(void (__fastcall **)(Execution::ExecutionServices *))(*(_QWORD *)this + 8LL))(this);
    v7 = (HANDLE *)((char *)this + 128);
    Thread = CreateThread(0, 0, Execution::ExecutionServices::_WorkerThread, this, 0, 0);
    if ( Thread == *((HANDLE *)this + 16) )
    {
      Thread = *v7;
    }
    else
    {
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((char *)this + 128);
      *v7 = Thread;
    }
    if ( Thread )
      goto LABEL_17;
    (*(void (__fastcall **)(Execution::ExecutionServices *))(*(_QWORD *)this + 16LL))(this);
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
LABEL_17:
      *((_DWORD *)this + 34) = 1;
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18009a6bc  push    rbx
0x18009a6be  push    rsi
0x18009a6bf  push    rdi
0x18009a6c0  push    r14
0x18009a6c2  sub     rsp, 38h
0x18009a6c6  mov     rdi, rcx
0x18009a6c9  xor     r9d, r9d; lpName
0x18009a6cc  xor     ecx, ecx; lpEventAttributes
0x18009a6ce  xor     r8d, r8d; bInitialState
0x18009a6d1  xor     edx, edx; bManualReset
0x18009a6d3  call    cs:__imp_CreateEventW
0x18009a6d9  lea     rsi, [rdi+70h]
0x18009a6dd  mov     rbx, rax
0x18009a6e0  cmp     rax, [rsi]
0x18009a6e3  jz      short loc_18009A6F2
0x18009a6e5  mov     rcx, rsi
0x18009a6e8  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18009a6ed  mov     [rsi], rbx
0x18009a6f0  jmp     short loc_18009A6F5
0x18009a6f2  mov     rbx, [rsi]
0x18009a6f5  test    rbx, rbx
0x18009a6f8  jnz     short loc_18009A704
0x18009a6fa  mov     ebx, 80004005h
0x18009a6ff  jmp     loc_18009A7B9
0x18009a704  xor     r9d, r9d; lpName
0x18009a707  xor     r8d, r8d; bInitialState
0x18009a70a  xor     edx, edx; bManualReset
0x18009a70c  xor     ecx, ecx; lpEventAttributes
0x18009a70e  call    cs:__imp_CreateEventW
0x18009a714  lea     rsi, [rdi+78h]
0x18009a718  mov     rbx, rax
0x18009a71b  cmp     rax, [rsi]
0x18009a71e  jz      short loc_18009A72D
0x18009a720  mov     rcx, rsi
0x18009a723  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18009a728  mov     [rsi], rbx
0x18009a72b  jmp     short loc_18009A730
0x18009a72d  mov     rbx, [rsi]
0x18009a730  test    rbx, rbx
0x18009a733  jz      short loc_18009A6FA
0x18009a735  mov     rax, [rdi]
0x18009a738  mov     rcx, rdi
0x18009a73b  xor     ebx, ebx
0x18009a73d  mov     rax, [rax+8]
0x18009a741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a746  mov     r9, rdi; lpParameter
0x18009a749  mov     [rsp+58h+lpThreadId], rbx; lpThreadId
0x18009a74e  lea     r8, ?_WorkerThread@ExecutionServices@Execution@@KAKPEAX@Z; lpStartAddress
0x18009a755  mov     [rsp+58h+dwCreationFlags], ebx; dwCreationFlags
0x18009a759  xor     edx, edx; dwStackSize
0x18009a75b  xor     ecx, ecx; lpThreadAttributes
0x18009a75d  call    cs:__imp_CreateThread
0x18009a763  lea     r14, [rdi+80h]
0x18009a76a  mov     rsi, rax
0x18009a76d  cmp     rax, [r14]
0x18009a770  jz      short loc_18009A77F
0x18009a772  mov     rcx, r14
0x18009a775  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18009a77a  mov     [r14], rsi
0x18009a77d  jmp     short loc_18009A782
0x18009a77f  mov     rsi, [r14]
0x18009a782  test    rsi, rsi
0x18009a785  jnz     short loc_18009A7AF
0x18009a787  mov     rax, [rdi]
0x18009a78a  mov     rcx, rdi
0x18009a78d  mov     rax, [rax+10h]
0x18009a791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a796  call    cs:__imp_GetLastError
0x18009a79c  mov     ebx, eax
0x18009a79e  test    eax, eax
0x18009a7a0  jle     short loc_18009A7AB
0x18009a7a2  movzx   ebx, ax
0x18009a7a5  or      ebx, 80070000h
0x18009a7ab  test    ebx, ebx
0x18009a7ad  js      short loc_18009A7B9
0x18009a7af  mov     dword ptr [rdi+88h], 1
0x18009a7b9  mov     eax, ebx
0x18009a7bb  add     rsp, 38h
0x18009a7bf  pop     r14
0x18009a7c1  pop     rdi
0x18009a7c2  pop     rsi
0x18009a7c3  pop     rbx
0x18009a7c4  retn
```
