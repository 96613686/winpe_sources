# _Init_thread_abort

- ea: `0x180002ba0`
- end: `0x180002bdc`
- name: `_Init_thread_abort`
- size: `60`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000cd9f`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180002bd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002bc3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002bc3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002bb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002bb0`

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
0x180002ba0  push    rbx
0x180002ba2  sub     rsp, 20h
0x180002ba6  mov     rbx, rcx
0x180002ba9  lea     rcx, SRWLock; SRWLock
0x180002bb0  call    cs:__imp_AcquireSRWLockExclusive
0x180002bb6  lea     rcx, SRWLock; SRWLock
0x180002bbd  mov     dword ptr [rbx], 0
0x180002bc3  call    cs:__imp_ReleaseSRWLockExclusive
0x180002bc9  lea     rcx, ConditionVariable
0x180002bd0  add     rsp, 20h
0x180002bd4  pop     rbx
0x180002bd5  jmp     cs:__imp_WakeAllConditionVariable
```
