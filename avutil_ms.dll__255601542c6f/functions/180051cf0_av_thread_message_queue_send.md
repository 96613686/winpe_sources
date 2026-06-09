# av_thread_message_queue_send

- ea: `0x180051cf0`
- end: `0x180051d98`
- name: `av_thread_message_queue_send`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180039b20`
- `0x180039e20`
- `0x180051cf0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180051d72`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180051d72`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180051d40`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180051d40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051d7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051d7b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051d14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051d14`

## pseudocode

```c
__int64 __fastcall av_thread_message_queue_send(__int64 a1, int a2, char a3)
{
  RTL_SRWLOCK *v3; // rsi
  unsigned int v7; // ebx

  v3 = (RTL_SRWLOCK *)(a1 + 8);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  if ( !*(_DWORD *)(a1 + 32) )
  {
    while ( !av_fifo_can_write(*(_QWORD *)a1) )
    {
      if ( (a3 & 1) != 0 )
      {
        v7 = -11;
        goto LABEL_9;
      }
      SleepConditionVariableSRW((PCONDITION_VARIABLE)(a1 + 24), v3, 0xFFFFFFFF, 0);
      if ( *(_DWORD *)(a1 + 32) )
      {
        v7 = *(_DWORD *)(a1 + 32);
        goto LABEL_9;
      }
    }
  }
  v7 = *(_DWORD *)(a1 + 32);
  if ( !v7 )
  {
    av_fifo_write(*(_QWORD *)a1, a2, 1);
    WakeConditionVariable((PCONDITION_VARIABLE)(a1 + 16));
  }
LABEL_9:
  ReleaseSRWLockExclusive(v3);
  return v7;
}

```

## disassembly

```asm
0x180051cf0  mov     [rsp+arg_0], rbx
0x180051cf5  mov     [rsp+arg_8], rbp
0x180051cfa  mov     [rsp+arg_10], rsi
0x180051cff  push    rdi
0x180051d00  sub     rsp, 20h
0x180051d04  lea     rsi, [rcx+8]
0x180051d08  mov     rdi, rcx
0x180051d0b  mov     rcx, rsi; SRWLock
0x180051d0e  mov     ebx, r8d
0x180051d11  mov     rbp, rdx
0x180051d14  call    cs:AcquireSRWLockExclusive
0x180051d1a  cmp     dword ptr [rdi+20h], 0
0x180051d1e  jnz     short loc_180051D58
0x180051d20  mov     rcx, [rdi]
0x180051d23  call    av_fifo_can_write
0x180051d28  test    rax, rax
0x180051d2b  jnz     short loc_180051D58
0x180051d2d  test    bl, 1
0x180051d30  jnz     short loc_180051D51
0x180051d32  lea     rcx, [rdi+18h]; ConditionVariable
0x180051d36  xor     r9d, r9d; Flags
0x180051d39  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180051d3d  mov     rdx, rsi; SRWLock
0x180051d40  call    cs:SleepConditionVariableSRW
0x180051d46  cmp     dword ptr [rdi+20h], 0
0x180051d4a  jz      short loc_180051D20
0x180051d4c  mov     ebx, [rdi+20h]
0x180051d4f  jmp     short loc_180051D78
0x180051d51  mov     ebx, 0FFFFFFF5h
0x180051d56  jmp     short loc_180051D78
0x180051d58  mov     ebx, [rdi+20h]
0x180051d5b  test    ebx, ebx
0x180051d5d  jnz     short loc_180051D78
0x180051d5f  mov     rcx, [rdi]
0x180051d62  lea     r8d, [rbx+1]
0x180051d66  mov     rdx, rbp
0x180051d69  call    av_fifo_write
0x180051d6e  lea     rcx, [rdi+10h]; ConditionVariable
0x180051d72  call    cs:WakeConditionVariable
0x180051d78  mov     rcx, rsi; SRWLock
0x180051d7b  call    cs:ReleaseSRWLockExclusive
0x180051d81  mov     rbp, [rsp+28h+arg_8]
0x180051d86  mov     eax, ebx
0x180051d88  mov     rbx, [rsp+28h+arg_0]
0x180051d8d  mov     rsi, [rsp+28h+arg_10]
0x180051d92  add     rsp, 20h
0x180051d96  pop     rdi
0x180051d97  retn
```
