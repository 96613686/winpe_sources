# _Init_thread_abort

- ea: `0x18003e7a8`
- end: `0x18003e7e4`
- name: `_Init_thread_abort`
- size: `60`
- prototype: ``
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x1800a30ba`
- `0x1800a7bdb`
- `0x1800af269`
- `0x1800af27b`
- `0x1800af28d`
- `0x1800af29f`
- `0x1800af2b1`
- `0x1800af2c3`
- `0x1800af42f`
- `0x1800af441`
- `0x1800af453`
- `0x1800af465`
- `0x1800af477`
- `0x1800af489`
- `0x1800af49b`
- `0x1800af4ad`
- `0x1800af4bf`
- `0x1800af4d1`
- `0x1800af4e3`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e7cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e7cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e7b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003e7b8`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18003e7dd`

## pseudocode

```c
void __fastcall Init_thread_abort(_DWORD *a1)
{
  AcquireSRWLockExclusive(&SRWLock);
  *a1 = 0;
  ReleaseSRWLockExclusive(&SRWLock);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x18003e7a8  push    rbx
0x18003e7aa  sub     rsp, 20h
0x18003e7ae  mov     rbx, rcx
0x18003e7b1  lea     rcx, SRWLock; SRWLock
0x18003e7b8  call    cs:__imp_AcquireSRWLockExclusive
0x18003e7be  lea     rcx, SRWLock; SRWLock
0x18003e7c5  mov     dword ptr [rbx], 0
0x18003e7cb  call    cs:__imp_ReleaseSRWLockExclusive
0x18003e7d1  lea     rcx, ConditionVariable
0x18003e7d8  add     rsp, 20h
0x18003e7dc  pop     rbx
0x18003e7dd  jmp     cs:__imp_WakeAllConditionVariable
```
