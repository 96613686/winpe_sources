# av_thread_message_queue_set_err_recv

- ea: `0x180051da0`
- end: `0x180051de5`
- name: `av_thread_message_queue_set_err_recv`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180051dc5`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180051dc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051dde`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051db8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051db8`

## pseudocode

```c
void __fastcall av_thread_message_queue_set_err_recv(__int64 a1, int a2)
{
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  *(_DWORD *)(a1 + 36) = a2;
  WakeAllConditionVariable((PCONDITION_VARIABLE)(a1 + 16));
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 8));
}

```

## disassembly

```asm
0x180051da0  mov     [rsp+arg_0], rbx
0x180051da5  mov     [rsp+arg_8], rsi
0x180051daa  push    rdi
0x180051dab  sub     rsp, 20h
0x180051daf  mov     rdi, rcx
0x180051db2  mov     ebx, edx
0x180051db4  add     rcx, 8; SRWLock
0x180051db8  call    cs:AcquireSRWLockExclusive
0x180051dbe  lea     rcx, [rdi+10h]; ConditionVariable
0x180051dc2  mov     [rdi+24h], ebx
0x180051dc5  call    cs:WakeAllConditionVariable
0x180051dcb  lea     rcx, [rdi+8]
0x180051dcf  mov     rbx, [rsp+28h+arg_0]
0x180051dd4  mov     rsi, [rsp+28h+arg_8]
0x180051dd9  add     rsp, 20h
0x180051ddd  pop     rdi
0x180051dde  jmp     cs:ReleaseSRWLockExclusive
```
