# av_thread_message_queue_recv

- ea: `0x180051c30`
- end: `0x180051ce9`
- name: `av_thread_message_queue_recv`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180039af0`
- `0x180039d60`
- `0x180051c30`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180051cbd`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180051cbd`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180051c84`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180051c84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051cc6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051cc6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051c59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051c59`

## pseudocode

```c
__int64 __fastcall av_thread_message_queue_recv(__int64 a1, int a2, char a3)
{
  RTL_SRWLOCK *v3; // rsi
  unsigned int v7; // ebx

  v3 = (RTL_SRWLOCK *)(a1 + 8);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  v7 = 0;
  while ( !*(_DWORD *)(a1 + 36) && !av_fifo_can_read(*(_QWORD *)a1) )
  {
    if ( (a3 & 1) != 0 )
    {
      v7 = -11;
      goto LABEL_10;
    }
    SleepConditionVariableSRW((PCONDITION_VARIABLE)(a1 + 16), v3, 0xFFFFFFFF, 0);
  }
  if ( av_fifo_can_read(*(_QWORD *)a1) )
  {
    av_fifo_read(*(_QWORD *)a1, a2, 1);
    WakeConditionVariable((PCONDITION_VARIABLE)(a1 + 24));
  }
  else
  {
    v7 = *(_DWORD *)(a1 + 36);
  }
LABEL_10:
  ReleaseSRWLockExclusive(v3);
  return v7;
}

```

## disassembly

```asm
0x180051c30  mov     rax, rsp
0x180051c33  mov     [rax+8], rbx
0x180051c37  mov     [rax+10h], rbp
0x180051c3b  mov     [rax+18h], rsi
0x180051c3f  mov     [rax+20h], rdi
0x180051c43  push    r14
0x180051c45  sub     rsp, 20h
0x180051c49  lea     rsi, [rcx+8]
0x180051c4d  mov     rdi, rcx
0x180051c50  mov     rcx, rsi; SRWLock
0x180051c53  mov     ebp, r8d
0x180051c56  mov     r14, rdx
0x180051c59  call    cs:AcquireSRWLockExclusive
0x180051c5f  xor     ebx, ebx
0x180051c61  jmp     short loc_180051C8A
0x180051c63  mov     rcx, [rdi]
0x180051c66  call    av_fifo_can_read
0x180051c6b  test    rax, rax
0x180051c6e  jnz     short loc_180051C8F
0x180051c70  test    bpl, 1
0x180051c74  jnz     short loc_180051CA1
0x180051c76  lea     rcx, [rdi+10h]; ConditionVariable
0x180051c7a  xor     r9d, r9d; Flags
0x180051c7d  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180051c81  mov     rdx, rsi; SRWLock
0x180051c84  call    cs:SleepConditionVariableSRW
0x180051c8a  cmp     [rdi+24h], ebx
0x180051c8d  jz      short loc_180051C63
0x180051c8f  mov     rcx, [rdi]
0x180051c92  call    av_fifo_can_read
0x180051c97  test    rax, rax
0x180051c9a  jnz     short loc_180051CA8
0x180051c9c  mov     ebx, [rdi+24h]
0x180051c9f  jmp     short loc_180051CC3
0x180051ca1  mov     ebx, 0FFFFFFF5h
0x180051ca6  jmp     short loc_180051CC3
0x180051ca8  mov     rcx, [rdi]
0x180051cab  mov     r8d, 1
0x180051cb1  mov     rdx, r14
0x180051cb4  call    av_fifo_read
0x180051cb9  lea     rcx, [rdi+18h]; ConditionVariable
0x180051cbd  call    cs:WakeConditionVariable
0x180051cc3  mov     rcx, rsi; SRWLock
0x180051cc6  call    cs:ReleaseSRWLockExclusive
0x180051ccc  mov     rbp, [rsp+28h+arg_8]
0x180051cd1  mov     eax, ebx
0x180051cd3  mov     rbx, [rsp+28h+arg_0]
0x180051cd8  mov     rsi, [rsp+28h+arg_10]
0x180051cdd  mov     rdi, [rsp+28h+arg_18]
0x180051ce2  add     rsp, 20h
0x180051ce6  pop     r14
0x180051ce8  retn
```
