# _Init_thread_footer

- ea: `0x180002584`
- end: `0x1800025ed`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000836c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800025d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800025d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002594`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002594`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800025e6`

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
0x180002584  push    rbx
0x180002586  sub     rsp, 20h
0x18000258a  mov     rbx, rcx
0x18000258d  lea     rcx, SRWLock; SRWLock
0x180002594  call    cs:__imp_AcquireSRWLockExclusive
0x18000259a  mov     eax, cs:_Init_global_epoch
0x1800025a0  lea     rcx, SRWLock; SRWLock
0x1800025a7  mov     edx, cs:_tls_index
0x1800025ad  inc     eax
0x1800025af  mov     cs:_Init_global_epoch, eax
0x1800025b5  mov     [rbx], eax
0x1800025b7  mov     rax, gs:58h
0x1800025c0  mov     r9d, 4
0x1800025c6  mov     r8, [rax+rdx*8]
0x1800025ca  mov     eax, cs:_Init_global_epoch
0x1800025d0  mov     [r9+r8], eax
0x1800025d4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800025da  lea     rcx, ConditionVariable
0x1800025e1  add     rsp, 20h
0x1800025e5  pop     rbx
0x1800025e6  jmp     cs:__imp_WakeAllConditionVariable
```
