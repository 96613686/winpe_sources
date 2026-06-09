# av_thread_message_flush

- ea: `0x180051aa0`
- end: `0x180051b01`
- name: `av_thread_message_flush`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180051bc0`

## callees

- `0x180039af0`
- `0x180039db0`
- `0x180051aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180051ae6`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180051ae6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051af0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051af0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051ab1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051ab1`

## pseudocode

```c
void __fastcall av_thread_message_flush(_QWORD *a1)
{
  unsigned __int64 v2; // rax
  bool v3; // zf
  unsigned __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  AcquireSRWLockExclusive((PSRWLOCK)a1 + 1);
  v2 = av_fifo_can_read(*a1);
  v3 = a1[6] == 0;
  v4 = v2;
  if ( !v3 )
    av_fifo_read_to_cb(*a1, sub_180051E40, a1, &v4);
  WakeAllConditionVariable((PCONDITION_VARIABLE)a1 + 3);
  ReleaseSRWLockExclusive((PSRWLOCK)a1 + 1);
}

```

## disassembly

```asm
0x180051aa0  mov     [rsp+arg_8], rbx
0x180051aa5  push    rdi
0x180051aa6  sub     rsp, 20h
0x180051aaa  mov     rbx, rcx
0x180051aad  add     rcx, 8; SRWLock
0x180051ab1  call    cs:AcquireSRWLockExclusive
0x180051ab7  mov     rcx, [rbx]
0x180051aba  call    av_fifo_can_read
0x180051abf  cmp     qword ptr [rbx+30h], 0
0x180051ac4  mov     [rsp+28h+arg_0], rax
0x180051ac9  jz      short loc_180051AE2
0x180051acb  mov     rcx, [rbx]
0x180051ace  lea     r9, [rsp+28h+arg_0]
0x180051ad3  mov     r8, rbx
0x180051ad6  lea     rdx, sub_180051E40
0x180051add  call    av_fifo_read_to_cb
0x180051ae2  lea     rcx, [rbx+18h]; ConditionVariable
0x180051ae6  call    cs:WakeAllConditionVariable
0x180051aec  lea     rcx, [rbx+8]; SRWLock
0x180051af0  call    cs:ReleaseSRWLockExclusive
0x180051af6  mov     rbx, [rsp+28h+arg_8]
0x180051afb  add     rsp, 20h
0x180051aff  pop     rdi
0x180051b00  retn
```
