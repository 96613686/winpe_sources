# _Init_thread_abort

- ea: `0x180002234`
- end: `0x180002270`
- name: `_Init_thread_abort`
- size: `60`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001e977`
- `0x18001eca8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002244`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002244`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002257`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002257`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180002269`

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
0x180002234  push    rbx
0x180002236  sub     rsp, 20h
0x18000223a  mov     rbx, rcx
0x18000223d  lea     rcx, SRWLock; SRWLock
0x180002244  call    cs:__imp_AcquireSRWLockExclusive
0x18000224a  lea     rcx, SRWLock; SRWLock
0x180002251  mov     dword ptr [rbx], 0
0x180002257  call    cs:__imp_ReleaseSRWLockExclusive
0x18000225d  lea     rcx, ConditionVariable
0x180002264  add     rsp, 20h
0x180002268  pop     rbx
0x180002269  jmp     cs:__imp_WakeAllConditionVariable
```
