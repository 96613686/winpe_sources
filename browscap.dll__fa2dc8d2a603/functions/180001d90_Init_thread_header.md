# _Init_thread_header

- ea: `0x180001d90`
- end: `0x180001e0b`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008bc4`

## callees

- `0x180001d90`

## import_xrefs

- `KERNEL32!SleepConditionVariableSRW` at `0x180001dc8`
- `KERNEL32!SleepConditionVariableSRW` at `0x180001dc8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001da0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001da0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001e04`

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
0x180001d90  push    rbx
0x180001d92  sub     rsp, 20h
0x180001d96  mov     rbx, rcx
0x180001d99  lea     rcx, SRWLock; SRWLock
0x180001da0  call    cs:__imp_AcquireSRWLockExclusive
0x180001da6  cmp     dword ptr [rbx], 0
0x180001da9  jnz     short loc_180001DD0
0x180001dab  mov     dword ptr [rbx], 0FFFFFFFFh
0x180001db1  jmp     short loc_180001DF8
0x180001db3  xor     r9d, r9d; Flags
0x180001db6  lea     rdx, SRWLock; SRWLock
0x180001dbd  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180001dc1  lea     rcx, ConditionVariable; ConditionVariable
0x180001dc8  call    cs:__imp_SleepConditionVariableSRW
0x180001dce  jmp     short loc_180001DA6
0x180001dd0  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180001dd3  jz      short loc_180001DB3
0x180001dd5  mov     rax, gs:58h
0x180001dde  mov     ecx, cs:_tls_index
0x180001de4  mov     r8d, 4
0x180001dea  mov     rdx, [rax+rcx*8]
0x180001dee  mov     eax, cs:_Init_global_epoch
0x180001df4  mov     [r8+rdx], eax
0x180001df8  lea     rcx, SRWLock
0x180001dff  add     rsp, 20h
0x180001e03  pop     rbx
0x180001e04  jmp     cs:__imp_ReleaseSRWLockExclusive
```
