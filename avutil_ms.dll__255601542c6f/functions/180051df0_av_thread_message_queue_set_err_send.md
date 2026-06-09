# av_thread_message_queue_set_err_send

- ea: `0x180051df0`
- end: `0x180051e35`
- name: `av_thread_message_queue_set_err_send`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180051e15`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180051e15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051e2e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051e08`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051e08`

## pseudocode

```c
void __fastcall av_thread_message_queue_set_err_send(__int64 a1, int a2)
{
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  *(_DWORD *)(a1 + 32) = a2;
  WakeAllConditionVariable((PCONDITION_VARIABLE)(a1 + 24));
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
}

```

## disassembly

```asm
0x180051df0  mov     [rsp+arg_0], rbx
0x180051df5  mov     [rsp+arg_8], rsi
0x180051dfa  push    rdi
0x180051dfb  sub     rsp, 20h
0x180051dff  mov     rdi, rcx
0x180051e02  mov     ebx, edx
0x180051e04  add     rcx, 8; SRWLock
0x180051e08  call    cs:AcquireSRWLockExclusive
0x180051e0e  lea     rcx, [rdi+18h]; ConditionVariable
0x180051e12  mov     [rdi+20h], ebx
0x180051e15  call    cs:WakeAllConditionVariable
0x180051e1b  lea     rcx, [rdi+8]
0x180051e1f  mov     rbx, [rsp+28h+arg_0]
0x180051e24  mov     rsi, [rsp+28h+arg_8]
0x180051e29  add     rsp, 20h
0x180051e2d  pop     rdi
0x180051e2e  jmp     cs:ReleaseSRWLockExclusive
```
