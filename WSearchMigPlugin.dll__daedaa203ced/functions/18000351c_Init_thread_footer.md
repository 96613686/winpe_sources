# _Init_thread_footer

- ea: `0x18000351c`
- end: `0x18000357c`
- name: `_Init_thread_footer`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800156a4`

## callees

- `0x1800035f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000352c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000352c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000356c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000356c`

## pseudocode

```c
int __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&stru_180025C90);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&stru_180025C90);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x18000351c  push    rbx
0x18000351e  sub     rsp, 20h
0x180003522  mov     rbx, rcx
0x180003525  lea     rcx, stru_180025C90; lpCriticalSection
0x18000352c  call    cs:__imp_EnterCriticalSection
0x180003532  mov     eax, cs:_Init_global_epoch
0x180003538  lea     rcx, stru_180025C90; lpCriticalSection
0x18000353f  mov     edx, cs:_tls_index
0x180003545  inc     eax
0x180003547  mov     cs:_Init_global_epoch, eax
0x18000354d  mov     [rbx], eax
0x18000354f  mov     rax, gs:58h
0x180003558  mov     r9d, 4
0x18000355e  mov     r8, [rax+rdx*8]
0x180003562  mov     eax, cs:_Init_global_epoch
0x180003568  mov     [r9+r8], eax
0x18000356c  call    cs:__imp_LeaveCriticalSection
0x180003572  add     rsp, 20h
0x180003576  pop     rbx
0x180003577  jmp     _Init_thread_notify
```
