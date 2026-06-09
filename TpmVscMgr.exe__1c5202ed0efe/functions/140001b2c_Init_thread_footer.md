# _Init_thread_footer

- ea: `0x140001b2c`
- end: `0x140001b8c`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f54c`
- `0x140010de0`

## callees

- `0x140001c00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140001b7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140001b7c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001b3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001b3c`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&CriticalSection);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x140001b2c  push    rbx
0x140001b2e  sub     rsp, 20h
0x140001b32  mov     rbx, rcx
0x140001b35  lea     rcx, CriticalSection; lpCriticalSection
0x140001b3c  call    cs:__imp_EnterCriticalSection
0x140001b42  mov     eax, cs:_Init_global_epoch
0x140001b48  lea     rcx, CriticalSection; lpCriticalSection
0x140001b4f  mov     edx, cs:_tls_index
0x140001b55  inc     eax
0x140001b57  mov     cs:_Init_global_epoch, eax
0x140001b5d  mov     [rbx], eax
0x140001b5f  mov     rax, gs:58h
0x140001b68  mov     r9d, 4
0x140001b6e  mov     r8, [rax+rdx*8]
0x140001b72  mov     eax, cs:_Init_global_epoch
0x140001b78  mov     [r9+r8], eax
0x140001b7c  call    cs:__imp_LeaveCriticalSection
0x140001b82  add     rsp, 20h
0x140001b86  pop     rbx
0x140001b87  jmp     _Init_thread_notify
```
