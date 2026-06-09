# _Init_thread_footer

- ea: `0x180003148`
- end: `0x1800031b1`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `23`
- callee_count: `0`
- tags: ``

## callers

- `0x18000ae0c`
- `0x18000c98c`
- `0x18000ca78`
- `0x18000cb64`
- `0x18000cc50`
- `0x18000cd3c`
- `0x18000ce28`
- `0x18000cf14`
- `0x18000d000`
- `0x18000d0ec`
- `0x18000d1d8`
- `0x18000d2c4`
- `0x18003d2dc`
- `0x18003d3c8`
- `0x18003d4b4`
- `0x18003d5a0`
- `0x18003d68c`
- `0x18003d778`
- `0x18003d864`
- `0x18003d950`
- `0x18003da3c`
- `0x18003db28`
- `0x18003dc14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003198`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003198`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003158`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003158`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800031aa`

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
0x180003148  push    rbx
0x18000314a  sub     rsp, 20h
0x18000314e  mov     rbx, rcx
0x180003151  lea     rcx, SRWLock; SRWLock
0x180003158  call    cs:__imp_AcquireSRWLockExclusive
0x18000315e  mov     eax, cs:_Init_global_epoch
0x180003164  lea     rcx, SRWLock; SRWLock
0x18000316b  mov     edx, cs:_tls_index
0x180003171  inc     eax
0x180003173  mov     cs:_Init_global_epoch, eax
0x180003179  mov     [rbx], eax
0x18000317b  mov     rax, gs:58h
0x180003184  mov     r9d, 4
0x18000318a  mov     r8, [rax+rdx*8]
0x18000318e  mov     eax, cs:_Init_global_epoch
0x180003194  mov     [r9+r8], eax
0x180003198  call    cs:__imp_ReleaseSRWLockExclusive
0x18000319e  lea     rcx, ConditionVariable
0x1800031a5  add     rsp, 20h
0x1800031a9  pop     rbx
0x1800031aa  jmp     cs:__imp_WakeAllConditionVariable
```
