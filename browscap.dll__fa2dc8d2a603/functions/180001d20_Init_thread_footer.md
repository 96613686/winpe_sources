# _Init_thread_footer

- ea: `0x180001d20`
- end: `0x180001d89`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180008bc4`

## import_xrefs

- `KERNEL32!WakeAllConditionVariable` at `0x180001d82`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001d30`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001d30`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001d70`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001d70`

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
0x180001d20  push    rbx
0x180001d22  sub     rsp, 20h
0x180001d26  mov     rbx, rcx
0x180001d29  lea     rcx, SRWLock; SRWLock
0x180001d30  call    cs:__imp_AcquireSRWLockExclusive
0x180001d36  mov     eax, cs:_Init_global_epoch
0x180001d3c  lea     rcx, SRWLock; SRWLock
0x180001d43  mov     edx, cs:_tls_index
0x180001d49  inc     eax
0x180001d4b  mov     cs:_Init_global_epoch, eax
0x180001d51  mov     [rbx], eax
0x180001d53  mov     rax, gs:58h
0x180001d5c  mov     r9d, 4
0x180001d62  mov     r8, [rax+rdx*8]
0x180001d66  mov     eax, cs:_Init_global_epoch
0x180001d6c  mov     [r9+r8], eax
0x180001d70  call    cs:__imp_ReleaseSRWLockExclusive
0x180001d76  lea     rcx, ConditionVariable
0x180001d7d  add     rsp, 20h
0x180001d81  pop     rbx
0x180001d82  jmp     cs:__imp_WakeAllConditionVariable
```
