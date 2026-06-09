# _Init_thread_footer

- ea: `0x1800022a0`
- end: `0x180002300`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c314`

## callees

- `0x180002374`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022b0`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_180023528);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_180023528);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x1800022a0  push    rbx
0x1800022a2  sub     rsp, 20h
0x1800022a6  mov     rbx, rcx
0x1800022a9  lea     rcx, stru_180023528; lpCriticalSection
0x1800022b0  call    cs:__imp_EnterCriticalSection
0x1800022b6  mov     eax, cs:_Init_global_epoch
0x1800022bc  lea     rcx, stru_180023528; lpCriticalSection
0x1800022c3  mov     edx, cs:_tls_index
0x1800022c9  inc     eax
0x1800022cb  mov     cs:_Init_global_epoch, eax
0x1800022d1  mov     [rbx], eax
0x1800022d3  mov     rax, gs:58h
0x1800022dc  mov     r9d, 4
0x1800022e2  mov     r8, [rax+rdx*8]
0x1800022e6  mov     eax, cs:_Init_global_epoch
0x1800022ec  mov     [r9+r8], eax
0x1800022f0  call    cs:__imp_LeaveCriticalSection
0x1800022f6  add     rsp, 20h
0x1800022fa  pop     rbx
0x1800022fb  jmp     _Init_thread_notify
```
