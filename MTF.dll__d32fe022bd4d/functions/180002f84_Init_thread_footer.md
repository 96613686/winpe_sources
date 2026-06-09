# _Init_thread_footer

- ea: `0x180002f84`
- end: `0x180002fed`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002a3d0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180002fe6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002f94`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002f94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002fd4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002fd4`

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
0x180002f84  push    rbx
0x180002f86  sub     rsp, 20h
0x180002f8a  mov     rbx, rcx
0x180002f8d  lea     rcx, SRWLock; SRWLock
0x180002f94  call    cs:__imp_AcquireSRWLockExclusive
0x180002f9a  mov     eax, cs:_Init_global_epoch
0x180002fa0  lea     rcx, SRWLock; SRWLock
0x180002fa7  mov     edx, cs:_tls_index
0x180002fad  inc     eax
0x180002faf  mov     cs:_Init_global_epoch, eax
0x180002fb5  mov     [rbx], eax
0x180002fb7  mov     rax, gs:58h
0x180002fc0  mov     r9d, 4
0x180002fc6  mov     r8, [rax+rdx*8]
0x180002fca  mov     eax, cs:_Init_global_epoch
0x180002fd0  mov     [r9+r8], eax
0x180002fd4  call    cs:__imp_ReleaseSRWLockExclusive
0x180002fda  lea     rcx, ConditionVariable
0x180002fe1  add     rsp, 20h
0x180002fe5  pop     rbx
0x180002fe6  jmp     cs:__imp_WakeAllConditionVariable
```
