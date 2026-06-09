# _Init_thread_abort

- ea: `0x180003104`
- end: `0x180003140`
- name: `_Init_thread_abort`
- size: `60`
- prototype: ``
- caller_count: `22`
- callee_count: `0`
- tags: ``

## callers

- `0x1800595c2`
- `0x1800595d4`
- `0x1800595e6`
- `0x1800595f8`
- `0x18005960a`
- `0x18005961c`
- `0x18005962e`
- `0x180059640`
- `0x180059652`
- `0x180059664`
- `0x180059676`
- `0x18005c3d2`
- `0x18005c3e4`
- `0x18005c3f6`
- `0x18005c408`
- `0x18005c41a`
- `0x18005c42c`
- `0x18005c43e`
- `0x18005c450`
- `0x18005c462`
- `0x18005c474`
- `0x18005c486`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003127`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003127`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003114`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003114`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180003139`

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
0x180003104  push    rbx
0x180003106  sub     rsp, 20h
0x18000310a  mov     rbx, rcx
0x18000310d  lea     rcx, SRWLock; SRWLock
0x180003114  call    cs:__imp_AcquireSRWLockExclusive
0x18000311a  lea     rcx, SRWLock; SRWLock
0x180003121  mov     dword ptr [rbx], 0
0x180003127  call    cs:__imp_ReleaseSRWLockExclusive
0x18000312d  lea     rcx, ConditionVariable
0x180003134  add     rsp, 20h
0x180003138  pop     rbx
0x180003139  jmp     cs:__imp_WakeAllConditionVariable
```
