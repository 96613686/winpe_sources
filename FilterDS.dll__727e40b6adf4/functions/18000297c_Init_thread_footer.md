# _Init_thread_footer

- ea: `0x18000297c`
- end: `0x1800029e5`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a450`
- `0x18001442c`
- `0x180015de4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800029de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000298c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000298c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800029cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800029cc`

## pseudocode

```c
void __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  AcquireSRWLockExclusive(&SRWLock);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  ReleaseSRWLockExclusive(&SRWLock);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x18000297c  push    rbx
0x18000297e  sub     rsp, 20h
0x180002982  mov     rbx, rcx
0x180002985  lea     rcx, SRWLock; SRWLock
0x18000298c  call    cs:__imp_AcquireSRWLockExclusive
0x180002992  mov     eax, cs:_Init_global_epoch
0x180002998  lea     rcx, SRWLock; SRWLock
0x18000299f  mov     edx, cs:_tls_index
0x1800029a5  inc     eax
0x1800029a7  mov     cs:_Init_global_epoch, eax
0x1800029ad  mov     [rbx], eax
0x1800029af  mov     rax, gs:58h
0x1800029b8  mov     r9d, 4
0x1800029be  mov     r8, [rax+rdx*8]
0x1800029c2  mov     eax, cs:_Init_global_epoch
0x1800029c8  mov     [r9+r8], eax
0x1800029cc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800029d2  lea     rcx, ConditionVariable
0x1800029d9  add     rsp, 20h
0x1800029dd  pop     rbx
0x1800029de  jmp     cs:__imp_WakeAllConditionVariable
```
