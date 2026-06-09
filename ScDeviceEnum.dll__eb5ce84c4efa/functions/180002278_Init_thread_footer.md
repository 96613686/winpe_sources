# _Init_thread_footer

- ea: `0x180002278`
- end: `0x1800022e1`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180008070`
- `0x180009f18`
- `0x18000ba94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002288`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002288`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800022c8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800022c8`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800022da`

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
0x180002278  push    rbx
0x18000227a  sub     rsp, 20h
0x18000227e  mov     rbx, rcx
0x180002281  lea     rcx, SRWLock; SRWLock
0x180002288  call    cs:__imp_AcquireSRWLockExclusive
0x18000228e  mov     eax, cs:_Init_global_epoch
0x180002294  lea     rcx, SRWLock; SRWLock
0x18000229b  mov     edx, cs:_tls_index
0x1800022a1  inc     eax
0x1800022a3  mov     cs:_Init_global_epoch, eax
0x1800022a9  mov     [rbx], eax
0x1800022ab  mov     rax, gs:58h
0x1800022b4  mov     r9d, 4
0x1800022ba  mov     r8, [rax+rdx*8]
0x1800022be  mov     eax, cs:_Init_global_epoch
0x1800022c4  mov     [r9+r8], eax
0x1800022c8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800022ce  lea     rcx, ConditionVariable
0x1800022d5  add     rsp, 20h
0x1800022d9  pop     rbx
0x1800022da  jmp     cs:__imp_WakeAllConditionVariable
```
