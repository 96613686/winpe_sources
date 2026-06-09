# _Init_thread_header

- ea: `0x180002ff4`
- end: `0x18000306f`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a3d0`

## callees

- `0x180002ff4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000302c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000302c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003004`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003004`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003068`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  AcquireSRWLockExclusive(&SRWLock);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    SleepConditionVariableSRW(&ConditionVariable, &SRWLock, 0xFFFFFFFF, 0);
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x180002ff4  push    rbx
0x180002ff6  sub     rsp, 20h
0x180002ffa  mov     rbx, rcx
0x180002ffd  lea     rcx, SRWLock; SRWLock
0x180003004  call    cs:__imp_AcquireSRWLockExclusive
0x18000300a  cmp     dword ptr [rbx], 0
0x18000300d  jnz     short loc_180003034
0x18000300f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180003015  jmp     short loc_18000305C
0x180003017  xor     r9d, r9d; Flags
0x18000301a  lea     rdx, SRWLock; SRWLock
0x180003021  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180003025  lea     rcx, ConditionVariable; ConditionVariable
0x18000302c  call    cs:__imp_SleepConditionVariableSRW
0x180003032  jmp     short loc_18000300A
0x180003034  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180003037  jz      short loc_180003017
0x180003039  mov     rax, gs:58h
0x180003042  mov     ecx, cs:_tls_index
0x180003048  mov     r8d, 4
0x18000304e  mov     rdx, [rax+rcx*8]
0x180003052  mov     eax, cs:_Init_global_epoch
0x180003058  mov     [r8+rdx], eax
0x18000305c  lea     rcx, SRWLock
0x180003063  add     rsp, 20h
0x180003067  pop     rbx
0x180003068  jmp     cs:__imp_ReleaseSRWLockExclusive
```
