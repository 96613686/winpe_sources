# CExecutionManager::Initialize(void)

- ea: `0x180027e1c`
- end: `0x180027f45`
- name: `?Initialize@CExecutionManager@@QEAAJXZ`
- size: `297`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fd94`
- `0x18003f550`

## callees

- `0x180027e1c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ee7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f00`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180027e86`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180027e86`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180027e40`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180027e40`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180027edd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180027edd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CExecutionManager::Initialize(char *Context)
{
  char *v2; // rdi
  HANDLE TimerQueue; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  HANDLE SemaphoreW; // rax
  signed int v8; // eax
  signed int v9; // eax

  v2 = Context + 8;
  (**((void (__fastcall ***)(char *))Context + 1))(Context + 8);
  TimerQueue = CreateTimerQueue();
  *((_QWORD *)Context + 9) = TimerQueue;
  if ( !TimerQueue )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_4:
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
    return v5;
  }
  SemaphoreW = CreateSemaphoreW(0, 0, 1, 0);
  *((_QWORD *)Context + 7) = SemaphoreW;
  if ( !SemaphoreW )
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_4;
  }
  if ( !RegisterWaitForSingleObject(
          (PHANDLE)Context + 8,
          SemaphoreW,
          CExecutionManager::StaticProcessWorkItem,
          Context,
          0xFFFFFFFF,
          0) )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    CloseHandle(*((HANDLE *)Context + 7));
    *((_QWORD *)Context + 7) = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
    return v5;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x180027e1c  mov     [rsp+arg_0], rbx
0x180027e21  mov     [rsp+arg_8], rsi
0x180027e26  push    rdi
0x180027e27  sub     rsp, 30h
0x180027e2b  mov     rsi, rcx
0x180027e2e  lea     rdi, [rcx+8]
0x180027e32  mov     rax, [rdi]
0x180027e35  mov     rcx, rdi
0x180027e38  mov     rax, [rax]
0x180027e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e40  call    cs:__imp_CreateTimerQueue
0x180027e46  mov     [rsi+48h], rax
0x180027e4a  test    rax, rax
0x180027e4d  jnz     short loc_180027E7B
0x180027e4f  call    cs:__imp_GetLastError
0x180027e55  mov     ebx, eax
0x180027e57  test    eax, eax
0x180027e59  jle     short loc_180027E64
0x180027e5b  movzx   ebx, ax
0x180027e5e  or      ebx, 80070000h
0x180027e64  mov     rdx, [rdi]
0x180027e67  mov     rcx, rdi
0x180027e6a  mov     rax, [rdx+8]
0x180027e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e73  nop
0x180027e74  mov     eax, ebx
0x180027e76  jmp     loc_180027F35
0x180027e7b  xor     r9d, r9d; lpName
0x180027e7e  xor     edx, edx; lInitialCount
0x180027e80  xor     ecx, ecx; lpSemaphoreAttributes
0x180027e82  lea     r8d, [r9+1]; lMaximumCount
0x180027e86  call    cs:__imp_CreateSemaphoreW
0x180027e8c  mov     [rsi+38h], rax
0x180027e90  test    rax, rax
0x180027e93  jnz     short loc_180027EBC
0x180027e95  call    cs:__imp_GetLastError
0x180027e9b  mov     ebx, eax
0x180027e9d  test    eax, eax
0x180027e9f  jle     short loc_180027EAA
0x180027ea1  movzx   ebx, ax
0x180027ea4  or      ebx, 80070000h
0x180027eaa  mov     rcx, [rdi]
0x180027ead  mov     rax, [rcx+8]
0x180027eb1  mov     rcx, rdi
0x180027eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027eb9  nop
0x180027eba  jmp     short loc_180027E74
0x180027ebc  lea     rcx, [rsi+40h]; phNewWaitObject
0x180027ec0  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180027ec8  mov     [rsp+38h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180027ed0  mov     r9, rsi; Context
0x180027ed3  lea     r8, ?StaticProcessWorkItem@CExecutionManager@@SAXPEAXE@Z; Callback
0x180027eda  mov     rdx, rax; hObject
0x180027edd  call    cs:__imp_RegisterWaitForSingleObject
0x180027ee3  test    eax, eax
0x180027ee5  jnz     short loc_180027F23
0x180027ee7  call    cs:__imp_GetLastError
0x180027eed  mov     ebx, eax
0x180027eef  test    eax, eax
0x180027ef1  jle     short loc_180027EFC
0x180027ef3  movzx   ebx, ax
0x180027ef6  or      ebx, 80070000h
0x180027efc  mov     rcx, [rsi+38h]; hObject
0x180027f00  call    cs:__imp_CloseHandle
0x180027f06  mov     qword ptr [rsi+38h], 0
0x180027f0e  mov     rcx, [rdi]
0x180027f11  mov     rax, [rcx+8]
0x180027f15  mov     rcx, rdi
0x180027f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f1d  nop
0x180027f1e  jmp     loc_180027E74
0x180027f23  mov     rax, [rdi]
0x180027f26  mov     rcx, rdi
0x180027f29  mov     rax, [rax+8]
0x180027f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027f32  nop
0x180027f33  xor     eax, eax
0x180027f35  mov     rbx, [rsp+38h+arg_0]
0x180027f3a  mov     rsi, [rsp+38h+arg_8]
0x180027f3f  add     rsp, 30h
0x180027f43  pop     rdi
0x180027f44  retn
```
