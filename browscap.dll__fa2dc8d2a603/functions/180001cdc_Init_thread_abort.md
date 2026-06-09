# _Init_thread_abort

- ea: `0x180001cdc`
- end: `0x180001d18`
- name: `_Init_thread_abort`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bff0`

## import_xrefs

- `KERNEL32!WakeAllConditionVariable` at `0x180001d11`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001cec`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001cec`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001cff`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001cff`

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
0x180001cdc  push    rbx
0x180001cde  sub     rsp, 20h
0x180001ce2  mov     rbx, rcx
0x180001ce5  lea     rcx, SRWLock; SRWLock
0x180001cec  call    cs:__imp_AcquireSRWLockExclusive
0x180001cf2  lea     rcx, SRWLock; SRWLock
0x180001cf9  mov     dword ptr [rbx], 0
0x180001cff  call    cs:__imp_ReleaseSRWLockExclusive
0x180001d05  lea     rcx, ConditionVariable
0x180001d0c  add     rsp, 20h
0x180001d10  pop     rbx
0x180001d11  jmp     cs:__imp_WakeAllConditionVariable
```
