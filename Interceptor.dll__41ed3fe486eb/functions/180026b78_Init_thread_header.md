# _Init_thread_header

- ea: `0x180026b78`
- end: `0x180026bf3`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180006d14`
- `0x18000866c`
- `0x18000ab48`
- `0x18001410c`
- `0x18001fec4`
- `0x18002023c`

## callees

- `0x180026b78`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026bec`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026b88`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026b88`
- `KERNEL32!SleepConditionVariableSRW` at `0x180026bb0`
- `KERNEL32!SleepConditionVariableSRW` at `0x180026bb0`

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
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL) = Init_global_epoch;
LABEL_7:
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x180026b78  push    rbx
0x180026b7a  sub     rsp, 20h
0x180026b7e  mov     rbx, rcx
0x180026b81  lea     rcx, SRWLock; SRWLock
0x180026b88  call    cs:__imp_AcquireSRWLockExclusive
0x180026b8e  cmp     dword ptr [rbx], 0
0x180026b91  jnz     short loc_180026BB8
0x180026b93  mov     dword ptr [rbx], 0FFFFFFFFh
0x180026b99  jmp     short loc_180026BE0
0x180026b9b  xor     r9d, r9d; Flags
0x180026b9e  lea     rdx, SRWLock; SRWLock
0x180026ba5  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180026ba9  lea     rcx, ConditionVariable; ConditionVariable
0x180026bb0  call    cs:__imp_SleepConditionVariableSRW
0x180026bb6  jmp     short loc_180026B8E
0x180026bb8  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180026bbb  jz      short loc_180026B9B
0x180026bbd  mov     rax, gs:58h
0x180026bc6  mov     ecx, cs:_tls_index
0x180026bcc  mov     r8d, 10h
0x180026bd2  mov     rdx, [rax+rcx*8]
0x180026bd6  mov     eax, cs:_Init_global_epoch
0x180026bdc  mov     [r8+rdx], eax
0x180026be0  lea     rcx, SRWLock
0x180026be7  add     rsp, 20h
0x180026beb  pop     rbx
0x180026bec  jmp     cs:__imp_ReleaseSRWLockExclusive
```
