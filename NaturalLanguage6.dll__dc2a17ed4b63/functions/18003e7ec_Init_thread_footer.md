# _Init_thread_footer

- ea: `0x18003e7ec`
- end: `0x18003e855`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x18003b080`
- `0x18004bf10`
- `0x180080710`
- `0x1800807ac`
- `0x18008083c`
- `0x1800808cc`
- `0x180080968`
- `0x1800809f8`
- `0x18008a5b0`
- `0x18008a628`
- `0x18008a6a0`
- `0x18008a718`
- `0x18008a790`
- `0x18008a808`
- `0x18008a880`
- `0x18008a8f8`
- `0x18008a970`
- `0x18008a9e8`
- `0x18008aa60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e83c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e83c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e7fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e7fc`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18003e84e`

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
0x18003e7ec  push    rbx
0x18003e7ee  sub     rsp, 20h
0x18003e7f2  mov     rbx, rcx
0x18003e7f5  lea     rcx, SRWLock; SRWLock
0x18003e7fc  call    cs:__imp_AcquireSRWLockExclusive
0x18003e802  mov     eax, cs:_Init_global_epoch
0x18003e808  lea     rcx, SRWLock; SRWLock
0x18003e80f  mov     edx, cs:_tls_index
0x18003e815  inc     eax
0x18003e817  mov     cs:_Init_global_epoch, eax
0x18003e81d  mov     [rbx], eax
0x18003e81f  mov     rax, gs:58h
0x18003e828  mov     r9d, 4
0x18003e82e  mov     r8, [rax+rdx*8]
0x18003e832  mov     eax, cs:_Init_global_epoch
0x18003e838  mov     [r9+r8], eax
0x18003e83c  call    cs:__imp_ReleaseSRWLockExclusive
0x18003e842  lea     rcx, ConditionVariable
0x18003e849  add     rsp, 20h
0x18003e84d  pop     rbx
0x18003e84e  jmp     cs:__imp_WakeAllConditionVariable
```
